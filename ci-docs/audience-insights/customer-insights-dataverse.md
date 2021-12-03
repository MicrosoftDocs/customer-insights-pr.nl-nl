---
title: Customer Insights-gegevens in Microsoft Dataverse
description: Gebruik Customer Insights-entiteiten als tabellen in Microsoft Dataverse.
ms.date: 11/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6f74559b34a95ed976a4e353c2dbabe59e1a8839
ms.sourcegitcommit: 9558ff772ee6c944fcb8db4bfc8cda13b38a1bff
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/29/2021
ms.locfileid: "7866928"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Werken met Customer Insights-gegevens in Microsoft Dataverse

Customer Insights biedt de mogelijkheid om uitvoerentiteiten beschikbaar te maken in [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Deze integratie maakt eenvoudig delen van gegevens en aangepaste ontwikkeling mogelijk via een low-code/no-code-aanpak. De uitvoerentiteiten zullen beschikbaar zijn als tabellen in Dataverse. Deze tabellen maken scenario's mogelijk zoals [geautomatiseerde werkstromen via Power Automate](/power-automate/getting-started), [modelgestuurde apps](/powerapps/maker/model-driven-apps/) en [canvas-apps](/powerapps/maker/canvas-apps/) via Power Apps. U kunt de gegevens gebruiken voor elke andere toepassing die is gebaseerd op Dataverse-tabellen. De huidige implementatie ondersteunt voornamelijk zoekacties waarbij gegevens van de beschikbare entiteiten voor doelgroepinzichten kunnen worden opgehaald voor een bepaalde klant-id.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Een Dataverse-omgeving toevoegen aan Customer Insights

**Organisaties met bestaande Dataverse-omgevingen**

Organisaties die al gebruikmaken van Dataverse kunnen [een van hun bestaande Dataverse-omgevingen gebruiken](create-environment.md) wanneer een beheerder doelgroepinzichten instelt. Door de URL voor de Dataverse-omgeving te verstrekken, wordt deze gekoppeld aan hun nieuwe omgeving voor doelgroepinzichten. Om de best mogelijke prestaties te garanderen, moeten Customer Insights en Dataverse-omgevingen in dezelfde regio worden gehost.

**Nieuwe organisatie**

Als u een nieuwe organisatie maakt bij het instellen van Customer Insights, krijgt u automatisch een nieuwe Dataverse-omgeving.

> [!NOTE]
> Als uw organisaties al gebruikmaken van Dataverse in hun tenant, is het belangrijk om te onthouden dat [het maken van Dataverse-omgevingen wordt geregeld door een beheerder](/power-platform/admin/control-environment-creation.md). Als u bijvoorbeeld een nieuwe omgeving voor doelgroepinzichten instelt met uw organisatieaccount en de beheerder het maken van Dataverse-proefomgevingen voor iedereen behalve beheerders heeft uitgeschakeld, kunt u geen nieuwe proefomgeving maken.
> 
> De Dataverse-proefomgevingen die zijn gemaakt in Customer Insights hebben 3 GB opslagruimte die niet meetelt voor de totale capaciteit waarop de tenant recht heeft. Betaalde abonnementen krijgen een Dataverse-recht van 15 GB voor database en 20 GB voor bestandsopslag.

## <a name="output-entities"></a>Uitvoerentiteiten

Sommige uitvoerentiteiten van doelgroepinzichten zijn beschikbaar als tabellen in Dataverse. In de onderstaande secties wordt het verwachte schema van deze tabellen beschreven.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Enrichment](#enrichment)
- [Prediction](#prediction)
- [Segmentlidmaatschap](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

Deze tabel bevat het geharmoniseerde klantprofiel van Customer Insights. Het schema voor een geharmoniseerd klantprofiel is afhankelijk van de entiteiten en kenmerken die in het samenvoegproces worden gebruikt. Een klantprofielschema bevat meestal een subset van de kenmerken uit de [Common Data Model-definitie van CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

De tabel AlternateKey bevat sleutels van de entiteiten die hebben deelgenomen aan het harmonisatieproces.

|Column  |Type  |Beschrijving  |
|---------|---------|---------|
|DataSourceName    |String         | Naam van de gegevensbron. Bijvoorbeeld: `datasource5`        |
|EntityName        | String        | Naam van de entiteit in doelgroepinzichten. Bijvoorbeeld: `contact1`        |
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
| SegmentProvider      | String       | App die de segmenten publiceert. Standaardinstelling: Doelgroepinzichten         |
| SegmentMembershipType | String       | Type van de klant van deze segmentlidmaatschapsrecord. Ondersteunt meerdere typen, zoals Klant, Contactpersoon of Account. Standaardinstelling: Klant  |
| Segmenten       | JSON-tekenreeks  | Lijst met unieke segmenten waarvan het klantprofiel lid is      |
| msdynci_identifier  | String   | De unieke id van de segmentlidmaatschapsrecord. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Deterministische GUID gegenereerd uit `msdynci_identifier`          |
