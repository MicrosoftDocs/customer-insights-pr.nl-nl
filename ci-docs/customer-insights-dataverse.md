---
title: Werken met Customer Insights-gegevens in Microsoft Dataverse
description: Leer hoe u Customer Insights en Microsoft Dataverse verbindt en krijg inzicht in de uitvoerentiteiten die worden geëxporteerd naar Dataverse.
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 0d536259f310b41fe12922baeebdc4569937db08
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303823"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Werken met Customer Insights-gegevens in Microsoft Dataverse

Customer Insights biedt de mogelijkheid om uitvoerentiteiten beschikbaar te maken in [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Deze integratie maakt eenvoudig delen van gegevens en aangepaste ontwikkeling mogelijk via een low-code/no-code-aanpak. De [uitvoerentiteiten](#output-entities) zijn beschikbaar als tabellen in een Dataverse-omgeving. U kunt de gegevens voor elke andere toepassing gebruiken op basis van Dataverse-tabellen. Deze tabellen maken scenario's zoals geautomatiseerde werkstromen via Power Automate of het bouwen van apps met Power Apps mogelijk.

Verbinding maken met uw Dataverse-omgeving stelt u ook in staat om [gegevens op te nemen uit on-premises gegevensbronnen met behulp van Power Platform-gegevensstromen en -gateways](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Vereisten

- Customer Insights en Dataverse-omgevingen moeten in dezelfde regio worden gehost.
- Een rol van algemene beheerder die is ingesteld in de Dataverse-omgeving. Controleer of deze [Dataverse-omgeving is gekoppeld](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) aan bepaalde beveiligingsgroepen en zorg ervoor dat u aan die beveiligingsgroepen wordt toegevoegd.
- Er is nog geen andere Customer Insights-omgeving aan de Dataverse-omgeving gekoppeld waarmee u verbinding wilt maken. Leren hoe u [een bestaande verbinding met een Dataverse omgeving kunt verwijderen](#remove-an-existing-connection-to-a-dataverse-environment).
- Een Microsoft Dataverse-omgeving die is verbonden met een enkel opslagaccount als u de omgeving configureert om [uw Azure Data Lake Storage te gebruiken](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse-opslagcapaciteitsrecht

Een Customer Insights-abonnement geeft u recht op extra capaciteit voor de bestaande [Dataverse-opslagcapaciteit](/power-platform/admin/capacity-storage) van uw organisatie. De toegevoegde capaciteit is afhankelijk van het aantal profielen dat uw abonnement gebruikt.

**Voorbeeld:**

Ervan uitgaande dat u 15 GB databaseopslag en 20 GB bestandsopslag krijgt per 100.000 klantprofielen. Als uw abonnement 300.000 klantprofielen omvat, is uw totale opslagcapaciteit 45 GB (3 x 15 GB) databaseopslag en 60 GB bestandsopslag (3 x 20 GB). En als u een B2B-abonnement hebt met 30K-accounts, bedraagt uw totale opslagcapaciteit 45 GB (3 x 15 GB) databaseopslag en 60 GB bestandsopslag (3 x 20 GB).

Logboekcapaciteit is niet incrementeel en vast voor uw organisatie.

Zie de [Licentiehandleiding voor Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544) voor meer informatie over de gedetailleerde capaciteitsrechten.

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Een Dataverse-omgeving verbinden met Customer Insights

Via de **Microsoft Dataverse**-stap kunt u Customer Insights verbinden met uw Dataverse-omgeving terwijl [u een Customer Insights-omgeving maakt](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="gegevens delen met Microsoft Dataverse automatisch ingeschakeld voor nieuwe omgevingen.":::

1. Geef de URL naar uw Dataverse-omgeving op of laat deze leeg om er een voor u te laten maken.

   > [!NOTE]
   > Na het tot stand brengen van de verbinding tussen Customer Insights en Dataverse, moet u de naam van de organisatie voor de Dataverse-omgeving niet veranderen. De naam van de organisatie wordt gebruikt in de Dataverse-URL en een gewijzigde naam verbreekt de verbinding met Customer Insights.

   [Power Platform-beheerders kunnen bepalen wie nieuwe Dataverse-omgevingen kan maken](/power-platform/admin/control-environment-creation). Wanneer u een nieuwe Customer Insights-omgeving probeert in te stellen en dit niet lukt, heeft de beheerder mogelijk het maken van Dataverse-omgevingen uitgeschakeld voor iedereen behalve beheerders.

1. Als u uw eigen Data Lake Storage-account gebruikt:
   1. Selecteer **Het delen van gegevens met Dataverse inschakelen**.
   1. Voer de **Id van machtigingen** in. U kunt de id van machtigingen ophalen door [het delen van gegevens met Dataverse vanuit uw eigen Azure Data Lake Storage in te schakelen](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Het delen van gegevens met Dataverse inschakelen vanuit uw eigen Azure Data Lake Storage (preview)

Controleer in [uw eigen Azure Data Lake Storage-account](own-data-lake-storage.md) of de gebruiker die de Customer Insights-omgeving instelt minimaal machtigingen **Storage Blob-gegevenslezer** heeft voor de `customerinsights`-container in het opslagaccount.

### <a name="limitations"></a>Beperkingen

- Er is slechts één een-op-een toewijzing tussen een Dataverse-organisatie en een Azure Data Lake Storage-account. Wanneer een Dataverse-organisatie eenmaal is verbonden met een opslagaccount, kan deze geen verbinding maken met een ander opslagaccount. Deze beperking zorgt ervoor dat een Dataverse niet meerdere opslagaccounts vult.
- Het delen van gegevens werkt niet als een Azure Private Link-installatie nodig is om toegang te krijgen tot uw Azure Data Lake Storage-account, omdat deze zich achter een firewall bevindt. Dataverse ondersteunt momenteel geen verbinding met privé-eindpunten via Private Link.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Beveiligingsgroepen instellen voor uw eigen Azure Data Lake Storage

1. Maak twee beveiligingsgroepen op uw Azure-abonnement - één beveiligingsgroep **Lezer** en één beveiligingsgroep **Inzender** en stel de Microsoft Dataverse-service in als eigenaar voor beide beveiligingsgroepen.

1. Beheer de Access Control List (ACL) voor de `customerinsights`-container in uw opslagaccount via deze beveiligingsgroepen.
   1. Voeg de Microsoft Dataverse-service en eventuele op Dataverse gebaseerde bedrijfstoepassingen zoals Dynamics 365 Marketing toe aan de beveiligingsgroep **Lezer** met **alleen lezen**-machtigingen.
   1. Voeg *alleen* de Customers Insights-toepassing toe aan de beveiligingsgroep **Inzender** om **zowel lees- als schrijfmachtigingen** te verlenen voor het wegschrijven van profielen en inzichten.

### <a name="set-up-powershell"></a>PowerShell instellen

Stel PowerShell in om PowerShell-scripts uit te voeren.

1. Installeer de meest recente versie van [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).
   1. Selecteer op uw pc de Windows-toets op uw toetsenbord en zoek naar **Windows PowerShell**. Selecteer vervolgens **Uitvoeren als beheerder**.
   1. Voer `Install-Module AzureAD` in het PowerShell-venster dat wordt geopend in.

1. Importeer drie modules.
   1. Voer `Install-Module -Name Az.Accounts` in het PowerShell-venster in en volg de stappen.
   1. Herhaal dit voor `Install-Module -Name Az.Resources` en `Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>PowerShell-scripts uitvoeren en Id van machtigingen ophalen

1. Download de twee PowerShell-scripts die u moet uitvoeren vanuit onze [GitHub-opslagplaats](https://github.com/trin-msft/byol) voor technici.
   - `CreateSecurityGroups.ps1`: vereist machtigingen voor tenantbeheerders.
   - `ByolSetup.ps1`: vereist machtigingen voor Opslag-blobgegevens eigenaar op het niveau van opslagaccount/container. Dit script maakt de machtiging voor u. Uw roltoewijzing kan handmatig worden verwijderd nadat het script met succes is uitgevoerd.

1. Voer `CreateSecurityGroups.ps1` uit in Windows PowerShell door de Azure-abonnements-id op te geven die uw Azure Data Lake Storage bevat. Open het PowerShell-script in een editor om aanvullende informatie en de geïmplementeerde logica te bekijken.

   Met dit script worden twee beveiligingsgroepen gemaakt voor uw Azure-abonnement: één voor de groep Lezer en een andere voor de groep Inzender. Microsoft Dataverse-service is de eigenaar van beide beveiligingsgroepen.

1. Bewaar beide beveiligingsgroep-id-waarden die door dit script zijn gegenereerd voor gebruik in het script `ByolSetup.ps1`.

   > [!NOTE]
   > Het maken van beveiligingsgroepen kan worden uitgeschakeld op uw tenant. In dat geval is een handmatige configuratie nodig en moet uw Azure AD-beheerder [het maken van beveiligingsgroepen inschakelen](/azure/active-directory/enterprise-users/groups-self-service-management).

1. Voer `ByolSetup.ps1` uit in Windows PowerShell door de Azure-abonnements-id op te geven met uw Azure Data Lake Storage, opslagaccountnaam, resourcegroepnaam en de waarden voor de beveiligingsgroep-id voor Lezer en Inzender. Open het PowerShell-script in een editor om aanvullende informatie en de geïmplementeerde logica te bekijken.

   Dit script voegt de vereiste op rollen gebaseerd toegangsbeheer toe voor de Microsoft Dataverse-service en eventuele op Dataverse gebaseerde zakelijke toepassingen. Het werkt ook de Access Control List (ACL) in de `customerinsights`-container bij voor de beveiligingsgroepen die zijn gemaakt met het `CreateSecurityGroups.ps1`-script. De groep Inzender krijgt *rwx*-machtiging en de groep Lezer krijgt alleen *rx*-machtiging.

1. Kopieer de uitvoertekenreeks die er als volgt uitziet: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Voer de gekopieerde uitvoertekenreeks in het veld **Id van machtigingen** van de stap voor omgevingsconfiguratie voor Microsoft Dataverse in.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Configuratieopties om het delen van gegevens van uw eigen Azure Data Lake Storage met Microsoft Dataverse in te schakelen.":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Een bestaande verbinding met een Dataverse-omgeving verwijderen

Bij een verbinding met een Dataverse-omgeving betekent de foutmelding **Deze CDS-organisatie is al aan een ander Customer Insights-exemplaar gekoppeld** dat de Dataverse-omgeving al wordt gebruikt in een Customer Insights-omgeving. U kunt de bestaande verbinding verwijderen als een algemene beheerder in de Dataverse-omgeving. Het kan een paar uur duren voordat de wijzigingen worden doorgevoerd.

1. Ga naar [Power Apps](https://make.powerapps.com).
1. Selecteer de omgeving met de omgevingskiezer.
1. Ga naar **Oplossingen**.
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

| Column            | Type        | Omschrijving                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | Klantprofiel-id                                                                      |
| ActivityId        | String      | Interne id van de klantactiviteit (primaire sleutel)                                       |
| SourceEntityName  | String      | Naam van de bronentiteit                                                                |
| SourceActivityId  | String      | Primaire sleutel van de bronentiteit                                                       |
| ActivityType      | String      | Semantisch activiteitstype of naam van aangepaste activiteit                                        |
| ActivityTimeStamp | DATETIME    | Tijdstempel voor activiteit                                                                      |
| Title             | String      | Titel of naam van de activiteit                                                               |
| Omschrijving       | String      | Beschrijving van activiteit                                                                     |
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

| Column               | Type        | Omschrijving                                          |
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
| SegmentMembershipType | String       | Type klant voor deze segmentlidmaatschapsrecord. Ondersteunt meerdere typen, zoals Klant, Contactpersoon of Account. Standaardinstelling: Klant  |
| Segmenten       | JSON-tekenreeks  | Lijst met unieke segmenten waarvan het klantprofiel lid is      |
| msdynci_identifier  | String   | De unieke id van de segmentlidmaatschapsrecord. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Deterministische GUID gegenereerd uit `msdynci_identifier`          |


[!INCLUDE [footer-include](includes/footer-banner.md)]
