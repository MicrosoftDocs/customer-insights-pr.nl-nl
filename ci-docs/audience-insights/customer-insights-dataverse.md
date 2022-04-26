---
title: Customer Insights-gegevens in Microsoft Dataverse
description: Gebruik Customer Insights-entiteiten als tabellen in Microsoft Dataverse.
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: bbbbf2a7f5edb81ee75f6e33988cd4721134b6e7
ms.sourcegitcommit: 0363559a1af7ae16da2a96b09d6a4a8a53a8cbb8
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/05/2022
ms.locfileid: "8547620"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Werken met Customer Insights-gegevens in Microsoft Dataverse

Customer Insights biedt de mogelijkheid om uitvoerentiteiten beschikbaar te maken in [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Deze integratie maakt eenvoudig delen van gegevens en aangepaste ontwikkeling mogelijk via een low-code/no-code-aanpak. De [uitvoerentiteiten](#output-entities) zijn beschikbaar als tabellen in een Dataverse-omgeving. U kunt de gegevens voor elke andere toepassing gebruiken op basis van Dataverse-tabellen. Deze tabellen maken scenario's zoals geautomatiseerde werkstromen via Power Automate of het bouwen van apps met Power Apps mogelijk. De huidige implementatie ondersteunt voornamelijk zoekopdrachten waarbij gegevens van de beschikbare Customer Insights-entiteiten kunnen worden opgehaald voor een bepaald klant-id.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Een Dataverse-omgeving toevoegen aan Customer Insights

**Bestaande organisatie**

Beheerders kunnen Customer Insights configureren om [een bestaande Dataverse-omgeving te gebruiken](create-environment.md) bij het maken van een Customer Insights-omgeving. Door de URL voor de Dataverse-omgeving te verstrekken, wordt deze gekoppeld aan hun nieuwe omgeving voor doelgroepinzichten. Customer Insights en Dataverse-omgevingen moeten in dezelfde regio worden gehost. 

Als u geen gebruik wilt maken van een bestaande Dataverse-omgeving, maakt het systeem een nieuwe omgeving voor de Customer Insights-gegevens in uw tenant. 

> [!NOTE]
> Als uw organisaties al gebruikmaken van Dataverse in hun tenant, is het belangrijk om te onthouden dat [het maken van Dataverse-omgevingen wordt geregeld door een beheerder](/power-platform/admin/control-environment-creation). Als u bijvoorbeeld een nieuwe omgeving voor doelgroepinzichten instelt met uw organisatieaccount en de beheerder het maken van Dataverse-proefomgevingen voor iedereen behalve beheerders heeft uitgeschakeld, kunt u geen nieuwe proefomgeving maken.
> 
> De Dataverse-proefomgevingen die zijn gemaakt in Customer Insights hebben 3 GB opslagruimte die niet meetelt voor de totale capaciteit waarop de tenant recht heeft. Betaalde abonnementen krijgen een Dataverse-recht van 15 GB voor database en 20 GB voor bestandsopslag.

**Nieuwe organisatie**

Als u een nieuwe organisatie maakt bij het instellen van Customer Insights, maakt het systeem automatisch een nieuwe Dataverse-omgeving in uw organisatie voor u.

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

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | Klantprofiel-id        |
| SegmentProvider      | String       | App die de segmenten publiceert. Standaardinstelling: Doelgroepinzichten         |
| SegmentMembershipType | String       | Type van de klant van deze segmentlidmaatschapsrecord. Ondersteunt meerdere typen, zoals Klant, Contactpersoon of Account. Standaardinstelling: Klant  |
| Segmenten       | JSON-tekenreeks  | Lijst met unieke segmenten waarvan het klantprofiel lid is      |
| msdynci_identifier  | String   | Unieke id van de segmentlidmaatschapsrecord. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Deterministische GUID gegenereerd uit `msdynci_identifier`          |
