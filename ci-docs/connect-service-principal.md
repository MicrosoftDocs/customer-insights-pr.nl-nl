---
title: Verbinding met een Azure Data Lake Storage-account maken met behulp van een service-principal
description: Gebruik een Azure-service-principal om verbinding te maken met uw eigen data lake.
ms.date: 04/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 1dd99edc327bd41b0442b390f2e4f8664269f553
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646177"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Verbinding met een Azure Data Lake Storage-account maken met behulp van een Azure-service-principal

In dit artikel wordt beschreven hoe u verbinding kunt maken tussen Dynamics 365 Customer Insights en een Azure Data Lake Storage-account met behulp van een Azure-service-principal in plaats van opslagaccountsleutels. 

Geautomatiseerde hulpmiddelen die Azure-services gebruiken, moeten altijd beperkte machtigingen hebben. In plaats van toepassingen zich te laten aanmelden als een gebruiker met volledige rechten, biedt Azure Service Principals. U kunt service-principals gebruiken om veilig [een Common Data Model-map toe te voegen of te bewerken als een gegevensbron](connect-common-data-model.md) of [een omgeving te maken of bij te werken](create-environment.md).

> [!IMPORTANT]
> - Het Data Lake Storage-account dat de service-principal gaat gebruiken, moet Gen2 zijn en moet [hiërarchische naamruimte hebben ingeschakeld](/azure/storage/blobs/data-lake-storage-namespace). Azure Data Lake Gen1-opslagaccounts worden niet ondersteund.
> - U hebt beheerdersmachtigingen nodig voor uw Azure-abonnement om een service-principal te maken.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Een Azure-service-principal maken voor Customer Insights

Voordat u een nieuwe service-principal voor Customer Insights maakt, moet u controleren of deze al in uw organisatie bestaat.

### <a name="look-for-an-existing-service-principal"></a>Een bestaande Service Principal zoeken

1. Ga naar de [Azure-beheerportal](https://portal.azure.com) en meld u aan bij uw organisatie.

2. Ga naar **Azure-services** en selecteer **Azure Active Directory**.

3. Selecteer onder **Beheer** de optie **Ondernemingstoepassingen**.

4. Zoek naar de id `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` voor de Microsoft-toepassing met de naam `Dynamics 365 AI for Customer Insights`.

5. Als u een overeenkomende record vindt, betekent dit dat de service-principal al bestaat. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Schermopname van een bestaande service-principal.":::
   
6. Als er geen resultaten worden geretourneerd, maakt u een nieuwe service principal.

### <a name="create-a-new-service-principal"></a>Een nieuwe service principal maken

1. Installeer de meest recente versie van Azure Active Directory PowerShell for Graph. Ga voor meer informatie naar [Azure Active Directory PowerShell for Graph installeren](/powershell/azure/active-directory/install-adv2).

   1. Selecteer op uw pc de Windows-toets op uw toetsenbord en zoek naar **Windows PowerShell**. Selecteer vervolgens **Uitvoeren als beheerder**.
   
   1. Voer `Install-Module AzureAD` in het PowerShell-venster dat wordt geopend in.

2. Maak de service-principal voor Customer Insights met de Azure AD PowerShell-module.

   1. Voer `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure` in het PowerShell-venster in. Vervang *[uw directory-id]* met de daadwerkelijke directory-id van uw Azure-abonnement waar u de service-principal wilt maken. De omgevingsnaamparameter, `AzureEnvironmentName`, is optioneel.
  
   1. Voer `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"` in. Met deze opdracht wordt de service-principal voor Customer Insights gemaakt voor het geselecteerde Azure-abonnement. 

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Machtigingen verlenen aan de service principal om toegang te krijgen tot het opslagaccount

Ga naar de Azure-portal om machtigingen te verlenen aan de service-principal voor het opslagaccount dat u wilt gebruiken in Customer Insights.

1. Ga naar de [Azure-beheerportal](https://portal.azure.com) en meld u aan bij uw organisatie.

1. Open het opslagaccount waartoe u de service-principal voor Customer Insights toegang wilt geven.

1. Selecteer in het linkerdeelvenster **Toegangscontrole (IAM)** en selecteer vervolgens **Toevoegen** > **Roltoewijzing toevoegen**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Schermopname die de Azure Portal weergeeft tijdens het toevoegen van een roltoewijzing.":::

1. Stel in het deelvenster **Roltoewijzing toevoegen** de volgende eigenschappen in:
   - Rol: **Inzender van opslagblob-gegevens**
   - Wijs toegang toe aan: **Gebruiker, groep of service principal**
   - Selecteer leden: **Dynamics 365 AI voor Customer Insights** (de [service-principal](#create-a-new-service-principal) die u eerder in deze procedure hebt gemaakt)

1.  Selecteer **Controleren + toewijzen**.

Het kan tot 15 minuten duren om de wijzigingen door te geven.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Voer de Azure-resource-id of de details van het Azure-abonnement in de bijlage van het opslagaccount in bij Customer Insights

U kunt een Data Lake Storage-account in Customer Insights koppelen om [uitvoergegevens op te slaan](manage-environments.md) of [het te gebruiken als een gegevensbron](connect-dataverse-managed-lake.md). Met deze optie kunt u kiezen tussen een op resources gebaseerde of een op abonnementen gebaseerde benadering. Afhankelijk van de aanpak die u kiest, volgt u de procedure in een van de volgende secties.

### <a name="resource-based-storage-account-connection"></a>Verbinding voor resource-opslagaccount

1. Ga naar de [Azure-beheerportal](https://portal.azure.com), meld u aan bij uw abonnement en open het opslagaccount.

1. Ga in het linkerdeelvenster naar **Instellingen** > **Eigenschappen**.

1. Kopieer de waarde voor de resource-id van het opslagaccount.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopieer de resource-id van het opslagaccount.":::

1. Voeg in Customer Insights de resource-id in het resourceveld in dat wordt weergegeven op het verbindingsscherm van het opslagaccount.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Voer de informatie voor de resource-id van het opslagaccount in.":::   

1. Ga verder met de resterende stappen in Customer Insights om het opslagaccount te koppelen.

### <a name="subscription-based-storage-account-connection"></a>Verbinding voor abonnement-opslagaccount

1. Ga naar de [Azure-beheerportal](https://portal.azure.com), meld u aan bij uw abonnement en open het opslagaccount.

1. Ga in het linkerdeelvenster naar **Instellingen** > **Eigenschappen**.

1. Bekijk **Abonnement**, **Resourcegroep** en **Naam** van het opslagaccount om ervoor te zorgen dat u de juiste waarden selecteert in Customer Insights.

1. Kies in Customer Insights de waarden voor de bijbehorende velden wanneer u het opslagaccount koppelt.

1. Ga verder met de resterende stappen in Customer Insights om het opslagaccount te koppelen.


[!INCLUDE [footer-include](includes/footer-banner.md)]