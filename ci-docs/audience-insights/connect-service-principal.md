---
title: Verbinding met een Azure Data Lake Storage-account maken met behulp van een service-principal
description: Gebruik een Azure-service-principal om verbinding te maken met uw eigen data lake.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 845d1f55eb99f2adf9b437124addec4f6d016fec
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461142"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Verbinding met een Azure Data Lake Storage-account maken met behulp van een Azure-service-principal
<!--note from editor: The Cloud Style Guide would have us just use "Azure Data Lake Storage" to mean the current version, unless the old version (Gen1) is mentioned. I've followed this guidance, even though it seems that our docs and Azure docs are all over the map on this.-->
Geautomatiseerde hulpmiddelen die Azure-services gebruiken, moeten altijd beperkte machtigingen hebben. In plaats van toepassingen zich te laten aanmelden als een gebruiker met volledige rechten, biedt Azure Service Principals. Lees verder om te leren hoe u Dynamics 365 Customer Insights kunt verbinden met een Azure Data Lake Storage-account met behulp van een Azure-service-principal in plaats van opslagaccountsleutels. 

U kunt de service-principal gebruiken om veilig [een Common Data Model-map toe te voegen of te bewerken als een gegevensbron](connect-common-data-model.md) of om [een omgeving te maken of bij te werken](get-started-paid.md).<!--note from editor: Suggested. Or it could be ", or create a new environment or update an existing one". I think "new" is implied with "create". The comma is necessary.-->

> [!IMPORTANT]
> - Het Data Lake Storage-account dat gebruik zal maken van<!--note from editor: Suggested. Or perhaps it could be "The Data Lake Storage account to which you want to give access to the service principal..."--> de service-principal moet [hiërarchische naamruimte hebben ingeschakeld](/azure/storage/blobs/data-lake-storage-namespace).
> - U hebt beheerdersmachtigingen nodig om uw Azure-abonnement de Service Principal te laten maken.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Een Azure-service-principal maken voor Customer Insights

Voordat u een nieuwe service-principal maakt voor doelgroepinzichten of betrokkenheidsinzichten, moet u controleren of deze al bestaat in uw organisatie.

### <a name="look-for-an-existing-service-principal"></a>Een bestaande Service Principal zoeken

1. Ga naar de [Azure-beheerportal](https://portal.azure.com) en meld u aan bij uw organisatie.

2. Ga naar **Azure-services** en selecteer **Azure Active Directory**.

3. Selecteer onder **Beheer** de optie **Ondernemingstoepassingen**.

4. Zoek naar de Microsoft-<!--note from editor: Via Microsoft Writing Style Guide.--> toepassings-id:
   - Doelgroepinzichten: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` met de naam `Dynamics 365 AI for Customer Insights`
   - Betrokkenheidsinzichten: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` met de naam `Dynamics 365 AI for Customer Insights engagement insights`

5. Als u een overeenkomende record vindt, betekent dit dat de service-principal al bestaat. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Schermopname van een bestaande service-principal.":::
   
6. Als er geen resultaten worden geretourneerd, maakt u een nieuwe service principal.

>[!NOTE]
>Als u gebruik wilt maken van de volledige kracht van Dynamics 365 Customer Insights, raden we u aan beide apps toe te voegen aan de service-principal.<!--note from editor: Using the note format is suggested, just so this doesn't get lost by being tucked up in the step.-->

### <a name="create-a-new-service-principal"></a>Een nieuwe service principal maken
<!--note from editor: Some general formatting notes: The MWSG wants bold for text the user enters (in addition to UI strings and the settings users select), but there's plenty of precedent for using code format for entering text in PowerShell so I didn't change that. Note that italic should be used for placeholders, but not much else.-->
1. Installeer de meest recente versie van Azure Active Directory PowerShell for Graph. Ga voor meer informatie naar [Azure Active Directory PowerShell for Graph installeren](/powershell/azure/active-directory/install-adv2).

   1. Selecteer op uw pc de Windows-toets op uw toetsenbord en zoek naar **Windows PowerShell**. Selecteer vervolgens **Uitvoeren als beheerder**.<!--note from editor: Or should this be something like "search for **Windows PowerShell** and, if asked, select **Run as administrator**."?-->
   
   1. Voer `Install-Module AzureAD` in het PowerShell-venster dat wordt geopend in.

2. Maak de service-principal voor Customer Insights met de Azure AD PowerShell-module.

   1. Voer `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure` in het PowerShell-venster in. Vervang *"[uw tenant-id]"*<!--note from editor: Edit okay? Or should the quotation marks stay in the command line, in which case it would be "Replace *[your tenant ID]* --> door de werkelijke id van uw tenant waar u de service-principal wilt maken. De omgevingsnaamparameter, `AzureEnvironmentName`, is optioneel.
  
   1. Voer `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"` in. Met deze opdracht wordt de service principal gemaakt voor doelgroepinzichten voor de geselecteerde tenant. 

   1. Voer `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"` in. Met deze opdracht wordt de service-principal gemaakt voor betrokkenheidsinzichten<!--note from editor: Edit okay?--> op de geselecteerde tenant.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Machtigingen verlenen aan de service principal om toegang te krijgen tot het opslagaccount

Ga naar de Azure Portal om machtigingen te verlenen aan de service principal voor het opslagaccount dat u wilt gebruiken in doelgroepinzichten.

1. Ga naar de [Azure-beheerportal](https://portal.azure.com) en meld u aan bij uw organisatie.

1. Open het opslagaccount waartoe u de service principal voor doelgroepinzichten toegang wilt geven.

1. Selecteer in het linkerdeelvenster **Toegangscontrole (IAM)** en selecteer vervolgens **Toevoegen** > **Roltoewijzing toevoegen**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Schermopname die de Azure Portal weergeeft tijdens het toevoegen van een roltoewijzing.":::

1. Stel in het deelvenster **Roltoewijzing toevoegen** de volgende eigenschappen in:
   - Rol: **Inzender van opslagblob-gegevens**
   - Wijs toegang toe aan: **Gebruiker, groep of service principal**
   - Selecteer **Dynamics 365 AI for Customer Insights** en **Dynamics 365 AI for Customer Insights-betrokkenheidsinzichten** (de twee [service-principals](#create-a-new-service-principal) die u eerder in deze procedure hebt gemaakt)

1.  Selecteer **Opslaan**.

Het kan tot 15 minuten duren om de wijzigingen door te geven.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Voer de Azure-resource-id of de Azure-abonnementsgegevens in de opslagaccountbijlage bij doelgroepinzichten in.

U kunt<!--note from editor: Edit suggested only if this section is optional.--> een Data Lake Storage-account in doelgroepinzichten aan [uitvoergegevens opslaan](manage-environments.md) of [gebruik het als een gegevensbron](connect-common-data-service-lake.md) koppelen. Met deze optie kunt u kiezen tussen een op resources gebaseerde of een op abonnementen gebaseerde benadering. Afhankelijk van de aanpak die u kiest, volgt u de procedure in een van de volgende secties.<!--note from editor: Suggested.-->

### <a name="resource-based-storage-account-connection"></a>Verbinding voor resource-opslagaccount

1. Ga naar de [Azure-beheerportal](https://portal.azure.com), meld u aan bij uw abonnement en open het opslagaccount.

1. Ga in het linkerdeelvenster naar **Instellingen** > **Eigenschappen**.

1. Kopieer de waarde voor de resource-id van het opslagaccount.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopieer de resource-id van het opslagaccount.":::

1. Voeg in doelgroepinzichten de resource-id in het resourceveld in dat wordt weergegeven op het verbindingsscherm van het opslagaccount.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Voer de informatie voor de resource-id van het opslagaccount in.":::   

1. Ga door met de resterende stappen in doelgroepinzichten om het opslagaccount te koppelen.

### <a name="subscription-based-storage-account-connection"></a>Verbinding voor abonnement-opslagaccount

1. Ga naar de [Azure-beheerportal](https://portal.azure.com), meld u aan bij uw abonnement en open het opslagaccount.

1. Ga in het linkerdeelvenster naar **Instellingen** > **Eigenschappen**.

1. Controleer of bij **Abonnement**, **Resourcegroep** en **Naam** van het opslagaccount de juiste waarden zijn geselecteerd in doelgroepinzichten.

1. Kies in doelgroepinzichten de waarden voor de bijbehorende velden bij het koppelen van het opslagaccount.

1. Ga door met de resterende stappen in doelgroepinzichten om het opslagaccount te koppelen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]