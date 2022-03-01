---
title: Verbinding maken met een Azure Data Lake Storage Gen2-account met een Service Principal
description: Gebruik een Azure Service-principal voor doelgroepinzichten om verbinding te maken met uw eigen data lake wanneer u deze koppelt aan doelgroepinzichten.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: cc94ad49f12067d513db4663bff60620d6501eb0
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692107"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>Verbinding maken met een Azure Data Lake Storage Gen2-account met een Azure Service Principal voor doelgroepinzichten

Geautomatiseerde hulpmiddelen die Azure-services gebruiken, moeten altijd beperkte machtigingen hebben. In plaats van toepassingen zich te laten aanmelden als een gebruiker met volledige rechten, biedt Azure Service Principals. Lees verder om te zien hoe u doelgroepinzichten kunt verbinden met een Azure Data Lake Storage Gen2-account met behulp van een Azure Service Principal in plaats van opslagaccountsleutels. 

U kunt de Service Principal gebruiken om veilig [een Common Data Model-map toe te voegen of te bewerken als een gegevensbron](connect-common-data-model.md) of [een nieuwe omgeving te maken of een bestaande te bewerken](get-started-paid.md).

> [!IMPORTANT]
> - Voor het Azure Data Lake Gen2-opslagaccount dat de service-principal wil gebruiken, moet [Hierarchical Name Space (HNS) ingeschakeld zijn](/azure/storage/blobs/data-lake-storage-namespace)​.
> - U hebt beheerdersmachtigingen nodig om uw Azure-abonnement de Service Principal te laten maken.

## <a name="create-azure-service-principal-for-audience-insights"></a>Een Azure Service Principal voor doelgroepinzichten maken

Voordat u een nieuwe Service Principal voor doelgroepinzichten maakt, controleert u of deze al bestaat in uw organisatie.

### <a name="look-for-an-existing-service-principal"></a>Een bestaande Service Principal zoeken

1. Ga naar de [Azure-beheerportal](https://portal.azure.com) en meld u aan bij uw organisatie.

2. Selecteer **Azure Active Directory** bij de Azure-services.

3. Selecteer onder **Beheer** de optie **Ondernemingstoepassingen**.

4. Zoek de toepassings-id van doelgroepinzichten `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` of de naam `Dynamics 365 AI for Customer Insights`.

5. Als u een overeenkomend record vindt, betekent dit dat de service principal voor doelgroepinzichten bestaat. U hoeft deze niet opnieuw te maken.
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Schermafbeelding met de bestaande service principal.":::
   
6. Als er geen resultaten worden geretourneerd, maakt u een nieuwe service principal.

### <a name="create-a-new-service-principal"></a>Een nieuwe service principal maken

1. Installeer de nieuwste versie van **Azure Active Directory PowerShell voor Graph**. Zie [Microsoft Azure Active Directory PowerShell voor Graph installeren](/powershell/azure/active-directory/install-adv2) voor meer informatie.
   - Selecteer op uw pc de Windows-toets op het toetsenbord en zoek **Windows PowerShell** en **Uitvoeren als beheerder**.
   
   - Voer `Install-Module AzureAD` in het PowerShell-venster dat wordt geopend in.

2. Maak de service principal voor doelgroepinzichten met de Azure AD PowerShell-module.
   - Voer `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure` in het PowerShell-venster in. Vervang 'uw tenant-id' door de werkelijke id van uw tenant waar u de service principal wilt maken. De omgevingsnaamparameter `AzureEnvironmentName` is optioneel.
  
   - Voer `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"` in. Met deze opdracht wordt de service principal gemaakt voor doelgroepinzichten voor de geselecteerde tenant.  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Machtigingen verlenen aan de service principal om toegang te krijgen tot het opslagaccount

Ga naar de Azure Portal om machtigingen te verlenen aan de service principal voor het opslagaccount dat u wilt gebruiken in doelgroepinzichten.

1. Ga naar de [Azure-beheerportal](https://portal.azure.com) en meld u aan bij uw organisatie.

1. Open het opslagaccount waartoe u de service principal voor doelgroepinzichten toegang wilt geven.

1. Selecteer **Toegangscontrole (IAM)** in het navigatiedeelvenster en selecteer **Toevoegen** > **Roltoewijzing toevoegen**.
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Schermafbeelding met Azure Portal tijdens het toevoegen van een roltoewijzing.":::
   
1. Stel in het deelvenster **Roltoewijzing toevoegen** de volgende eigenschappen in:
   - Rol: *Inzender van opslagblob-gegevens*
   - Wijs toegang toe aan: *Gebruiker, groep of service principal*
   - Selecteer: *Dynamics 365 AI voor Customer Insights* (de [service principal die u hebt gemaakt](#create-a-new-service-principal))

1.  Selecteer **Opslaan**.

Het kan tot 15 minuten duren om de wijzigingen door te geven.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Voer de Azure-resource-id of de Azure-abonnementsgegevens in de opslagaccountbijlage bij doelgroepinzichten in.

Koppel een Azure Data Lake-opslagaccount in doelgroepinzichten aan [opslaguitvoergegevens](manage-environments.md) of [gebruik het als een gegevensbron](connect-dataverse-managed-lake.md). Als u de optie Azure Data Lake kiest, kunt u kiezen tussen de resource- of de abonnementenbenadering.

Volg de onderstaande stappen om de vereiste informatie over de geselecteerde benadering te verstrekken.

### <a name="resource-based-storage-account-connection"></a>Verbinding voor resource-opslagaccount

1. Ga naar de [Azure-beheerportal](https://portal.azure.com), meld u aan bij uw abonnement en open het opslagaccount.

1. Ga naar **Instellingen** > **Eigenschappen** in het navigatiedeelvenster.

1. Kopieer de waarde voor de resource-id van het opslagaccount.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopieer de resource-id van het opslagaccount.":::

1. Voeg in doelgroepinzichten de resource-id in het resourceveld in dat wordt weergegeven in het opslagaccountverbindingsscherm.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Voer de informatie voor de resource-id van het opslagaccount in.":::   
   
1. Ga door met de resterende stappen in doelgroepinzichten om het opslagaccount te koppelen.

### <a name="subscription-based-storage-account-connection"></a>Verbinding voor abonnement-opslagaccount

1. Ga naar de [Azure-beheerportal](https://portal.azure.com), meld u aan bij uw abonnement en open het opslagaccount.

1. Ga naar **Instellingen** > **Eigenschappen** in het navigatiedeelvenster.

1. Controleer of bij **Abonnement**, **Resourcegroep** en **Naam** van het opslagaccount de juiste waarden zijn geselecteerd in doelgroepinzichten.

1. Kies in doelgroepinzichten de waarden of de overeenkomstige velden wanneer u het opslagaccount koppelt.
   
1. Ga door met de resterende stappen in doelgroepinzichten om het opslagaccount te koppelen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]