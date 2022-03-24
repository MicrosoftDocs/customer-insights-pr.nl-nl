---
title: Dynamics 365 Customer Insights controleren met Azure Monitor
description: Leer hoe u logboeken naar Microsoft Azure Monitor kunt verzenden.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: d84ae8301bdf384c2484cdb1e7dd8eb75d406769
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376410"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Logboeken doorsturen in Dynamics 365 Customer Insights met Azure Monitor (preview)

Dynamics 365 Customer Insights biedt een directe integratie met Azure Monitor. Met Azure Monitor-resourcelogboeken kunt u logboeken bewaken en naar [Azure-opslag](https://azure.microsoft.com/services/storage/), [Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview) verzenden of deze naar [Azure Event Hubs](https://azure.microsoft.com/services/event-hubs/) streamen.

Customer Insights stuurt de volgende gebeurtenislogboeken:

- **Controlegebeurtenissen**
  - **APIEvent** - maakt het bijhouden van wijzigingen via de gebruikersinterface van Dynamics 365 Customer Insights mogelijk.
- **Operationele gebeurtenissen**
  - **WorkflowEvent** - De workflow maakt het mogelijk om [Gegevensbronnen](data-sources.md) in te stellen en gegevens te [harmoniseren](data-unification.md) en [verrijken](enrichment-hub.md) en tot slot te [exporteren](export-destinations.md) naar andere systemen. Al deze stappen kunnen afzonderlijk worden uitgevoerd (bijvoorbeeld een enkele export activeren) of georkestreerd (bijvoorbeeld gegevens vernieuwen van gegevensbronnen die het harmoniseringsproces activeren dat extra verrijkingen zal opleveren en, eenmaal gedaan, de gegevens naar een ander systeem exporteren). Raadpleeg het [WorkflowEvent-schema](#workflow-event-schema) voor nadere details.
  - **APIEvent** - alle API-aanroepen van het klantexemplaar van Dynamics 365 Customer Insights. Raadpleeg het [APIEvent-schema](#api-event-schema) voor nadere details.

## <a name="set-up-the-diagnostic-settings"></a>De diagnose-instellingen uitvoeren

### <a name="prerequisites"></a>Vereisten

Als u diagnoses wilt configureren in Customer Insights, moet aan de volgende vereisten worden voldaan:

- U hebt een actief [Azure-abonnement](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- U hebt machtigingen voor [beheerders](permissions.md#admin) in Customer Insights.
- U hebt de rol van **inzender** en **beheerder voor gebruikerstoegang** voor de doelresource in Azure. De resource kan een Azure Storage-account, een Azure Event Hub of een Azure Log Analytics-werkruimte zijn. Zie [Azure-roltoewijzingen toevoegen of verwijderen met behulp van de Azure-portal](/azure/role-based-access-control/role-assignments-portal) voor meer informatie.
- [Bestemmingsvereisten](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) voor Azure Storage, Azure Event Hub of Azure Log Analytics met.
- U hebt in ieder geval de rol **Lezer** in de resourcegroep waartoe de resource behoort.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Diagnoses instellen met Azure Monitor

1. Selecteer in Customer Insights de optie **Systeem** > **Diagnose** om de diagnostische bestemmingen te zien die voor dit exemplaar zijn geconfigureerd.

1. Selecteer **Bestemming toevoegen**.

   > [!div class="mx-imgBorder"]
   > ![Diagnoseverbinding](media/diagnostics-pane.png "Diagnoseverbinding")

1. Geef een naam op in het veld **Naam van bestemming van diagnostische gegevens**.

1. Kies de **tenant** van het Azure-abonnement met de doelresources bron en selecteer **Aanmelden**.

1. Selecteer het **resourcetype** (opslagaccount, Event Hub of logboekanalyse).

1. Selecteer het **abonnement** voor de doelresource.

1. Selecteer de **resourcegroep** voor de doelresource.

1. Selecteer de **resource**.

1. Bevestig de verklaring **Gegevensprivacy en naleving**.

1. Selecteer **Verbinden met systeem** om verbinding te maken met de doelresource. De logboeken verschijnen na 15 minuten op de bestemming, als de API in gebruik is en gebeurtenissen genereert.

### <a name="remove-a-destination"></a>Een bestemming verwijderen

1. Ga naar **Systeem** > **Diagnose**.

1. Selecteer de diagnosebestemming in de lijst.

1. Selecteer in de kolom **Acties** het picotgram **Verwijderen**.

1. Bevestig de verwijdering om het doorsturen van het logboek te stoppen. De resource in het Azure-abonnement wordt niet verwijderd. U kunt de koppeling in de kolom **Acties** selecteren om de Azure-portal te openen voor de geselecteerde resource en deze daar te verwijderen.

## <a name="log-categories-and-event-schemas"></a>Logboekcategorieën en gebeurtenisschema's

Momenteel worden [API-gebeurtenissen](apis.md) en werkstroomgebeurtenissen ondersteund en zijn de volgende categorieën en schema's van toepassing.
Het logboekschema volgt het [algemene schema van Azure Monitor](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Categorieën

Customer Insights biedt twee categorieën:

- **Controlegebeurtenissen**: [API-gebeurtenissen](#api-event-schema) om de configuratiewijzigingen voor de service bij te houden. `POST|PUT|DELETE|PATCH`-bewerkingen vallen in deze categorie.
- **Operationele gebeurtenissen**: [API-gebeurtenissen](#api-event-schema) of [werkstroomgebeurtenissen](#workflow-event-schema) die worden gegenereerd tijdens het gebruik van de service.  Bijvoorbeeld, `GET`-aanvragen of de uitvoeringsgebeurtenissen van een werkstroom.

## <a name="configuration-on-the-destination-resource"></a>Configuratie op de doelresource

Op basis van uw keuze van het resourcetype worden automatisch de volgende stappen toegepast:

### <a name="storage-account"></a>Storage account

Customer Insights-service-principal krijgt de machtiging **Inzender opslagaccount** voor de geselecteerde resource en maakt twee containers onder de geselecteerde naamruimte:

- `insight-logs-audit` die **controlegebeurtenissen** bevat
- `insight-logs-operational` die **operationele gebeurtenissen** bevat

### <a name="event-hub"></a>Event Hub

Customer Insights-service-principal krijgt de machtiging **Eigenaar van gegevens van Azure Event Hubs** voor de resource en maakt twee Event Hubs onder de geselecteerde naamruimte:

- `insight-logs-audit` die **controlegebeurtenissen** bevat
- `insight-logs-operational` die **operationele gebeurtenissen** bevat

### <a name="log-analytics"></a>Log Analytics

Customer Insights-service-principal krijgt de machtiging **Inzender van Log Analytics** voor de resource. De logboeken zijn beschikbaar onder **Logboeken** > **Tabellen** > **Logboekbeheer** in de geselecteerde Log Analytics-werkruimte. Vouw de oplossing **Logboekbeheer** uit en zoek de tabellen `CIEventsAudit` en `CIEventsOperational`.

- `CIEventsAudit` die **controlegebeurtenissen** bevat
- `CIEventsOperational` die **operationele gebeurtenissen** bevat

Vouw onder het venster **Query's** de oplossing **Controleren** uit en zoek de voorbeeldquery's op door te zoeken naar `CIEvents`.

## <a name="event-schemas"></a>Gebeurtenisschema's

API-gebeurtenissen en werkstroomgebeurtenissen hebben een gemeenschappelijke structuur en verschillen op detailniveau, zie [API-gebeurtenisschema](#api-event-schema) of [werkstroomgebeurtenisschema](#workflow-event-schema).

### <a name="api-event-schema"></a>API-gebeurtenisschema

| Veld             | DataType  | Vereist/Optioneel | Description       | Voorbeeld        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Tijdstempel | Vereist          | Timestamp van de gebeurtenis (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Vereist          | ResourceId van het exemplaar dat de gebeurtenis heeft verzonden         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Vereist          | Naam van de bewerking die door deze gebeurtenis wordt vertegenwoordigd.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Vereist          | Logboekcategorie van de gebeurtenis. `Operational` of `Audit`. Alle POST/PUT/PATCH/DELETE HTTP-aanvragen zijn getagd met `Audit`, alle andere met `Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Vereist          | Status van de gebeurtenis. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Optioneel          | Resultaatstatus van de gebeurtenis. Als de bewerking overeenkomt met een REST API-aanroep, is dit de HTTP-statuscode.        | `200`             |
| `durationMs`      | Lang      | Optioneel          | Duur van de bewerking in milliseconden.     | `133`     |
| `callerIpAddress` | String    | Optioneel          | IP-adres van beller, als de bewerking overeenkomt met een API-aanroep die afkomstig is van een openbaar beschikbaar IP-adres.                                                 | `144.318.99.233`         |
| `identity`        | String    | Optioneel          | JSON-object dat de identiteit beschrijft van de gebruiker of toepassing die de bewerking heeft uitgevoerd.       | Zie de sectie [Identiteit](#identity-schema).     |  
| `properties`      | String    | Optioneel          | JSON-object met meer eigenschappen voor de specifieke categorie gebeurtenissen.      | Zie de sectie [Eigenschappen](#api-properties-schema).    |
| `level`           | String    | Vereist          | Ernstniveau van de gebeurtenis.    | `Informational`, `Warning`, `Error` of `Critical`.           |
| `uri`             | String    | Optioneel          | Absolute aanvraag-URI.    |               |

#### <a name="identity-schema"></a>Identiteitsschema

Het JSON-object `identity` heeft de volgende structuur.

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Veld                         | Description                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Toegewezen rol voor de gebruiker of app. Zie [gebruikersmachtigingen](permissions.md) voor meer informatie.                                     |
| `Authorization.RequiredRoles` | Vereiste rollen om de bewerking uit te voeren. De rol `Admin` mag alle bewerkingen uitvoeren.                                                    |
| `Claims`                      | Claims van het JSON-webtoken (JWT) voor de gebruiker of app. Claimeigenschappen verschillen per organisatie en de Azure Active Directory-configuratie. |

#### <a name="api-properties-schema"></a>API-eigenschappenschema

[API-gebeurtenissen](apis.md) hebben de volgende eigenschappen.

| Veld                        | Description                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Altijd `ApiEvent`, waarbij de logboekgebeurtenis als API-gebeurtenis wordt gemarkeerd.                                                                 |
| `properties.userAgent`       | Browseragent die de aanvraag verzendt of `unknown`.                                                                        |
| `properties.method`          | HTTP-methode: `GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Relatief pad van de aanvraag.                                                                                          |
| `properties.origin`          | URI die aangeeft waar een ophaalactie vandaan komt of `unknown`.                                                                  |
| `properties.operationStatus` | `Success` voor HTTP-statuscode < 400 <br> `ClientError` voor HTTP-statuscode < 500 <br> `Error` voor HTTP-status >= 500 |
| `properties.tenantId`        | Organisatie-id                                                                                                        |
| `properties.tenantName`      | Naam van de organisatie.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory-ObjectId van de beller.                                                                         |
| `properties.instanceId`      | `instanceId` van Customer Insights                                                                                         |

### <a name="workflow-event-schema"></a>Werkstroomgebeurtenisschema

De werkstroom bevat meerdere stappen. [Gegevensbronnen opnemen](data-sources.md), gegevens [harmoniseren](data-unification.md), [verrijken](enrichment-hub.md) en [exporteren](export-destinations.md). Al die stappen kunnen afzonderlijk of georkestreerd worden uitgevoerd via de volgende processen. 

#### <a name="operation-types"></a>Bewerkingstypen

| OperationType     | Groeperen                                     |
| ----------------- | ----------------------------------------- |
| Opname         | [Gegevensbronnen](data-sources.md)           |
| DataPreparation   | [Gegevensbronnen](data-sources.md)           |
| Overzicht               | [Gegevensharmonisatie](data-unification.md)   |
| Vergelijken             | [Gegevensharmonisatie](data-unification.md)   |
| Samenvoeging             | [Gegevensharmonisatie](data-unification.md)   |
| ProfileStore      | [Klantprofielen](customer-profiles.md) |
| Zoeken            | [Klantprofielen](customer-profiles.md) |
| Activiteit          | [Activiteiten](activities.md)                  |
| AttributeMeasures | [Segmenten en meetcriteria](segments.md)      |
| EntityMeasures    | [Segmenten en meetcriteria](segments.md)      |
| Meetcriteria          | [Segmenten en meetcriteria](segments.md)      |
| Segmentatie      | [Segmenten en meetcriteria](segments.md)      |
| Enrichment        | [Enrichment](enrichment-hub.md)                                          |
| Intelligentie      | [Voorspellingen](predictions-overview.md)                                          |
| AiBuilder         | [Voorspellingen](predictions-overview.md)                                          |
| Inzichten          | [Voorspellingen](predictions-overview.md)                                          |
| Export            | [Exports](export-destinations.md)                                          |
| ModelManagement   | [Voorspellingen](custom-models.md)                                           |
| relatie      | [Gegevensharmonisatie](relationships.md)                                           |

#### <a name="field-description"></a>Veldbeschrijving

| Veld           | DataType  | Vereist/Optioneel | Description                                                                                                                                                   | Voorbeeld                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Tijdstempel | Vereist          | Timestamp van de gebeurtenis (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Vereist          | ResourceId van het exemplaar dat de gebeurtenis heeft verzonden.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Vereist          | Naam van de bewerking die door deze gebeurtenis wordt vertegenwoordigd. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Zie [Bewerkingstypen](#operation-types) ter referentie. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Vereist          | Logboekcategorie van de gebeurtenis. Altijd `Operational` voor werkstroomgebeurtenissen                                                                                           | `Operational`                                                                                                                                                            | 
| `resultType`    | String    | Vereist          | Status van de gebeurtenis. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Lang      | Optioneel          | Duur van de bewerking in milliseconden.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Optioneel          | JSON-object met meer eigenschappen voor de specifieke categorie gebeurtenissen.                                                                                        | Zie subsectie [Werkstroomeigenschappen](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Vereist          | Ernstniveau van de gebeurtenis.                                                                                                                                  | `Informational`, `Warning` of `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Schema van werkstroomeigenschappen

Werkstroomgebeurtenissen hebben de volgende eigenschappen.

| Veld              | Workflow | Opdracht | Description            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Ja      | Ja  | Altijd `WorkflowEvent`, waarbij de gebeurtenis als werkstroomgebeurtenis wordt gemarkeerd.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Ja      | Ja  | Id van de werkstroomuitvoering. Alle werkstroom- en taakgebeurtenissen binnen de werkstroomuitvoering hebben hetzelfde `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Ja      | Ja  | Zie [Bewerkingstypen].(#operation-types) voor de id van de bewerking                                                                                                                                                                                       |
| `properties.tasksCount`                      | Ja      | No   | Uitsluitend werkstroom. Aantal taken dat door de werkstroom wordt geactiveerd.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Ja      | No   | Optioneel. Alleen werkstroomgebeurtenissen. De Azure Active Directory-[object-id van de gebruiker](/azure/marketplace/find-tenant-object-id#find-user-object-id) die de werkstroom heeft geactiveerd. Zie ook `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Ja      | No   | `full` of `incremental` vernieuwing.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Ja      | No   | `OnDemand` of `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Ja      | No   | `Running` of `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Ja      | Ja  | UTC-tijdstempel `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Ja      | Ja  | UTC-tijdstempel `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Ja      | Ja  | UTC-tijdstempel `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Ja      | Ja  | `instanceId` van Customer Insights                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Ja  | - Voor OperationType = `Export` vormt de guid van de exportconfiguratie de id. <br> - Voor OperationType = `Enrichment` is dit de guid van de verrijking <br> - Voor OperationType `Measures` en `Segmentation` vormt de naam van de entiteit de id. |
| `properties.friendlyName`                    | No       | Ja  | Gebruiksvriendelijke naam van de export of de entiteit die wordt verwerkt.                                                                                                                                                                                           |
| `properties.error`                           | No       | Ja  | Optioneel. Foutbericht met nadere details.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Ja  | Optioneel. Alleen voor OperationType `Export`. Identificeert het type export. Zie [overzicht van exportbestemmingen](export-destinations.md) voor meer informatie.                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Ja  | Optioneel. Alleen voor OperationType `Export`. Bevat een lijst met geconfigureerde entiteiten in de export.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Ja  | Optioneel. Alleen voor OperationType `Export`. Gedetailleerd bericht voor de export.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Ja  | Optioneel. Alleen voor OperationType `Segmentation`. Geeft het totale aantal leden aan dat het segment heeft.                                                                                                                                                    |
