---
title: Werken met Customer Insights-gegevens in Microsoft Dataverse
description: Leer hoe u Customer Insights en Microsoft Dataverse verbindt en krijg inzicht in de uitvoerentiteiten die worden geëxporteerd naar Dataverse.
ms.date: 05/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 3848e143bc7cb2f345bc698a274b92148ef00669
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833670"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Werken met Customer Insights-gegevens in Microsoft Dataverse

Customer Insights biedt de mogelijkheid om uitvoerentiteiten beschikbaar te stellen als [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Deze integratie maakt eenvoudig delen van gegevens en aangepaste ontwikkeling mogelijk via een low-code/no-code-aanpak. De [uitvoerentiteiten](#output-entities) zijn beschikbaar als tabellen in een Dataverse-omgeving. U kunt de gegevens voor elke andere toepassing gebruiken op basis van Dataverse-tabellen. Deze tabellen maken scenario's zoals geautomatiseerde werkstromen via Power Automate of het bouwen van apps met Power Apps mogelijk.

Verbinding maken met uw Dataverse-omgeving stelt u ook in staat om [gegevens op te nemen uit on-premises gegevensbronnen met behulp van Power Platform-gegevensstromen en -gateways](data-sources.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Vereisten

- Customer Insights en Dataverse-omgevingen moeten in dezelfde regio worden gehost.
- U moet de rol van algemene beheerder hebben in de Dataverse-omgeving. Controleer of deze [Dataverse-omgeving is gekoppeld](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) aan bepaalde beveiligingsgroepen en zorg ervoor dat u aan die beveiligingsgroepen wordt toegevoegd.
- Er is nog geen andere Customer Insights-omgeving aan de Dataverse-omgeving gekoppeld waarmee u verbinding wilt maken. Leren hoe u [een bestaande verbinding met een Dataverse omgeving kunt verwijderen](#remove-an-existing-connection-to-a-dataverse-environment).
- Een Microsoft Dataverse-omgeving kan alleen verbinding maken met één opslagaccount. Het is alleen van toepassing als u de omgeving configureert om [gebruik te maken van uw Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Een Dataverse-omgeving verbinden met Customer Insights

Via de **Microsoft Dataverse**-stap kunt u Customer Insights verbinden met uw Dataverse-omgeving terwijl [u een Customer Insights-omgeving maakt](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="gegevens delen met Microsoft Dataverse automatisch ingeschakeld voor netto nieuwe omgevingen.":::

Beheerders kunnen Customer Insights configureren om een bestaande Dataverse-omgeving te verbinden. Door de URL te verstrekken aan de Dataverse-omgeving, wordt het gekoppeld aan hun nieuwe Customer Insights-omgeving.

Als u geen gebruik wilt maken van een bestaande Dataverse-omgeving, maakt het systeem een nieuwe omgeving voor de Customer Insights-gegevens in uw tenant. [Power Platform-beheerders kunnen bepalen wie omgevingen kan maken](/power-platform/admin/control-environment-creation). Wanneer u een nieuwe Customer Insights-omgeving instelt en de beheerder het maken van Dataverse-omgevingen heeft uitgeschakeld voor iedereen behalve beheerders, kunt u mogelijk geen nieuwe omgeving maken.

**Schakel het delen van gegevens in** met Dataverse door het selectievakje voor het delen van gegevens te selecteren.

Als u uw eigen Data Lake Storage-account gebruikt, hebt u ook de **machtigings-id** nodig. Raadpleeg de volgende sectie voor meer informatie over het verkrijgen van de machtigings-id.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Gegevens delen met Dataverse inschakelen vanuit uw eigen Azure Data Lake Storage (preview)

Als u gegevens delen met Microsoft Dataverse inschakelt wanneer uw omgeving [gebruikmaakt van uw eigen Azure Data Lake Storage-account](own-data-lake-storage.md) is wat extra configuratie vereist. De gebruiker die de Customer Insights-omgeving instelt, moet minimaal machtigingen **Storage Blob-gegevenslezer** hebben voor de *CustomerInsights*-container in het Azure Data Lake Storage-account.

1. Maak twee beveiligingsgroepen op uw Azure-abonnement - één beveiligingsgroep **Lezer** en één beveiligingsgroep **Inzender** en stel de Microsoft Dataverse-service in als eigenaar voor beide beveiligingsgroepen.
2. Beheer de Access Control List (ACL) voor de Customer Insights-container in uw opslagaccount via deze beveiligingsgroepen. Voeg de Microsoft Dataverse-service en eventuele op Dataverse gebaseerde bedrijfstoepassingen zoals Dynamics 365 Marketing toe aan de beveiligingsgroep **Lezer** met **alleen lezen**-machtigingen. Voeg *alleen* de Customers Insights-toepassing toe aan de beveiligingsgroep **Inzender** om **zowel lees- als schrijfmachtigingen** te verlenen voor het wegschrijven van profielen en inzichten.

### <a name="limitations"></a>Beperkingen

Er gelden twee beperkingen bij het gebruik van Dataverse met uw eigen Azure Data Lake Storage-account:

- Er is sprake van een één-op-één toewijzing tussen een Dataverse-organisatie en een Azure Data Lake Storage-account. Wanneer een Dataverse-organisatie eenmaal is verbonden met een opslagaccount, kan deze geen verbinding maken met een ander opslagaccount. Deze beperking zorgt ervoor dat een Dataverse niet meerdere opslagaccounts vult.
- Het delen van gegevens werkt niet als een Azure Private Link-installatie nodig is om toegang te krijgen tot uw Azure Data Lake Storage-account, omdat deze zich achter een firewall bevindt. Dataverse ondersteunt momenteel geen verbinding met privé-eindpunten via Private Link.

### <a name="set-up-powershell"></a>PowerShell instellen

Als u de PowerShell-scripts wilt uitvoeren, moet u eerst PowerShell hiervoor instellen.

1. Installeer de meest recente versie van [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).
   1. Selecteer op uw pc de Windows-toets op uw toetsenbord en zoek naar **Windows PowerShell**. Selecteer vervolgens **Uitvoeren als beheerder**.
   1. Voer `Install-Module AzureAD` in het PowerShell-venster dat wordt geopend in.
2. Importeer drie modules.
    1. Voer `Install-Module -Name Az.Accounts` in het PowerShell-venster in en volg de stappen.
    1. Herhaal dit voor `Install-Module -Name Az.Resources` en `Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>Configuratiestappen

1. Download de twee PowerShell-scripts die u moet uitvoeren vanuit onze [GitHub-opslagplaats](https://github.com/trin-msft/byol) voor technici.
    1. `CreateSecurityGroups.ps1`
       - U hebt machtigingen voor *tenantbeheer* nodig om dit PowerShell-script te kunnen uitvoeren.
       - Dit PowerShell-script maakt twee beveiligingsgroepen in uw Azure-abonnement. Eén voor de groep Lezer en een andere voor de groep Inzender, met de Microsoft Dataverse-service als eigenaar voor beide beveiligingsgroepen.
       - Voer dit PowerShell-script uit in Windows PowerShell door de Azure-abonnements-id op te geven die uw Azure Data Lake Storage bevat. Open het PowerShell-script in een editor om aanvullende informatie en de geïmplementeerde logica te bekijken.
       - Bewaar beide beveiligingsgroep-id-waarden die door dit script zijn gegenereerd omdat we deze zullen gebruiken in het script `ByolSetup.ps1`.

        > [!NOTE]
        > Het maken van beveiligingsgroepen kan worden uitgeschakeld op uw tenant. In dat geval is een handmatige configuratie nodig en moet uw Azure AD-beheerder [het maken van beveiligingsgroepen inschakelen](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - U hebt machtigingen *Eigenaar van Storage Blob-gegevens* op opslagaccount-/containerniveau nodig om dit script te kunnen uitvoeren, anders maakt dit script er een voor u. Uw roltoewijzing kan handmatig worden verwijderd nadat het script met succes is uitgevoerd.
        - Dit PowerShell-script voegt de vereiste op rollen gebaseerd toegangsbeheer (RBAC) toe voor de Microsoft Dataverse-service en eventuele op Dataverse gebaseerde bedrijfstoepassingen. Het werkt ook de Access Control List (ACL) in de CustomerInsights-container bij voor de beveiligingsgroepen die zijn gemaakt met het script `CreateSecurityGroups.ps1`. De groep Inzender zal *rwx*-machtiging hebben en de groep Lezer zal alleen *rx*-machtiging hebben.
        - Voer dit PowerShell-script uit in Windows PowerShell door de Azure-abonnements-id op te geven met uw Azure Data Lake Storage, opslagaccountnaam, resourcegroepnaam en de waarden voor de beveiligingsgroep-id voor Lezer en Inzender. Open het PowerShell-script in een editor om aanvullende informatie en de geïmplementeerde logica te bekijken.
        - Kopieer de uitvoertekenreeks nadat het script is uitgevoerd. De uitvoertekenreeks ziet er als volgt uit: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Voer de uitvoertekenreeks die hierboven is gekopieerd in het veld **Id van machtigingen** van de stap voor omgevingsconfiguratie voor Microsoft Dataverse in.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Configuratieopties om het delen van gegevens van uw eigen Azure Data Lake Storage met Microsoft Dataverse in te schakelen.":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Een bestaande verbinding met een Dataverse-omgeving verwijderen

Bij een verbinding met een Dataverse-omgeving betekent de foutmelding **Deze CDS-organisatie is al aan een ander Customer Insights-exemplaar gekoppeld** dat de Dataverse-omgeving al wordt gebruikt in een Customer Insights-omgeving. U kunt de bestaande verbinding verwijderen als een algemene beheerder in de Dataverse-omgeving. Het kan een paar uur duren voordat de wijzigingen worden doorgevoerd.

1. Ga naar [Power Apps](https://make.powerapps.com).
1. Selecteer de omgeving met de omgevingskiezer.
1. Ga naar **Oplossingen**
1. Verwijder de oplossing met de naam **Invoegtoepassing Klantkaart voor Dynamics 365 Customer Insights (preview)**.

OF

1. Open uw Dataverse-omgeving.
1. Ga naar **Geavanceerde instellingen** > **Oplossingen**.
1. Verwijder de oplossing **CustomerInsightsCustomerCard**.

Als het verwijderen van de verbinding mislukt vanwege afhankelijkheden, moet u ook de afhankelijkheden verwijderen. Zie [Afhankelijkheden verwijderen](/power-platform/alm/removing-dependencies) voor meer informatie.

## <a name="output-entities"></a>Uitvoerentiteiten

Sommige uitvoerentiteiten van Customer Insights zijn beschikbaar als tabellen in Dataverse. In de onderstaande secties wordt het verwachte schema van deze tabellen beschreven.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Enrichment](#enrichment)
- [Prediction](#prediction)
- [Segmentlidmaatschap](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Deze tabel bevat het geharmoniseerde klantprofiel van Customer Insights. Het schema voor een geharmoniseerd klantprofiel is afhankelijk van de entiteiten en kenmerken die in het gegevensharmonisatieproces worden gebruikt. Een klantprofielschema bevat meestal een subset van de kenmerken uit de [Common Data Model-definitie van CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

De tabel AlternateKey bevat sleutels van de entiteiten die hebben deelgenomen aan het harmonisatieproces.

|Column  |Type  |Beschrijving  |
|---------|---------|---------|
|DataSourceName    |String         | Naam van de gegevensbron. Bijvoorbeeld: `datasource5`        |
|EntityName        | String        | Naam van de entiteit in Customer Insights. Bijvoorbeeld: `contact1`        |
|AlternateValue    |String         |Alternatieve id die is toegewezen aan de klant-id. Voorbeeld: `cntid_1078`         |
|KeyRing           | Tekst met meerdere regels        | JSON-waarde  </br> Voorbeeld: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | String        | Id van het geharmoniseerd klantprofiel.         |
|AlternateKeyId     | GUID         |  Deterministische GUID voor AlternateKey gebaseerd op msdynci_identifier       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Voorbeeld: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Deze tabel bevat activiteiten van gebruikers die beschikbaar zijn in Customer Insights.

| Column            | Type        | Beschrijving                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | Klantprofiel-id                                                                      |
| ActivityId        | String      | Interne id van de klantactiviteit (primaire sleutel)                                       |
| SourceEntityName  | String      | Naam van de bronentiteit                                                                |
| SourceActivityId  | String      | Primaire sleutel van de bronentiteit                                                       |
| ActivityType      | String      | Semantisch activiteitstype of naam van aangepaste activiteit                                        |
| ActivityTimeStamp | DATETIME    | Timestamp voor activiteit                                                                      |
| Titel             | String      | Titel of naam van de activiteit                                                               |
| Beschrijving       | String      | Beschrijving van activiteit                                                                     |
| URL               | String      | Koppeling naar een externe URL die specifiek is voor de activiteit                                         |
| SemanticData      | JSON-tekenreeks | Bevat een lijst met sleutelwaardeparen voor semantische toewijzingsvelden die specifiek zijn voor het type activiteit |
| RangeIndex        | String      | Unix-timestamp die wordt gebruikt voor het sorteren van de tijdlijn van activiteiten en effectieve bereikquery's |
| mydynci_unifiedactivityid   | GUID | Interne id van de klantactiviteit (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Deze tabel bevat de uitvoergegevens van op klantkenmerken gebaseerde meetcriteria.

| Column             | Type             | Beschrijving                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | String           | Klantprofiel-id        |
| Meetcriteria           | JSON-tekenreeks      | Bevat een lijst met sleutelwaardeparen voor de naam van de meetcriteria en waarden voor de gegeven klant | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | Klantprofiel-id |


### <a name="enrichment"></a>Enrichment

Deze tabel bevat de uitvoer van het verrijkingsproces.

| Column               | Type             |  Beschrijving                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | String           | Klantprofiel-id                                 |
| EnrichmentProvider   | String           | Naam van de provider van de verrijking                                  |
| EnrichmentType       | String           | Type verrijking                                      |
| Waarden               | JSON-tekenreeks      | Lijst met kenmerken die wordt geproduceerd door het verrijkingsproces |
| msdynci_enrichmentid | GUID             | Deterministische GUID die wordt gegenereerd op basis van msdynci_identifier |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Prediction

Deze tabel bevat de uitvoer van de modelvoorspellingen.

| Column               | Type        | Beschrijving                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | String      | Klantprofiel-id                                  |
| ModelProvider        | String      | Naam van de provider van het model                                      |
| Model                | String      | Modelnaam                                                |
| Waarden               | JSON-tekenreeks | Lijst met kenmerken die wordt geproduceerd door het model |
| msdynci_predictionid | GUID        | Deterministische GUID die wordt gegenereerd op basis van msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Segmentlidmaatschap

Deze tabel bevat informatie over het segmentlidmaatschap van de klantprofielen.

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | Klantprofiel-id        |
| SegmentProvider      | String       | App die de segmenten publiceert.      |
| SegmentMembershipType | String       | Type van de klant van deze segmentlidmaatschapsrecord. Ondersteunt meerdere typen, zoals Klant, Contactpersoon of Account. Standaardinstelling: Klant  |
| Segmenten       | JSON-tekenreeks  | Lijst met unieke segmenten waarvan het klantprofiel lid is      |
| msdynci_identifier  | String   | De unieke id van de segmentlidmaatschapsrecord. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Deterministische GUID gegenereerd uit `msdynci_identifier`          |

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
