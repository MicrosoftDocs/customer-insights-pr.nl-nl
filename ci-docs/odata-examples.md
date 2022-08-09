---
title: Voorbeelden van OData-query's voor Customer Insights-API's
description: Veelgebruikte voorbeelden van voor het Open Data Protocol (OData) om een query uit te voeren op de Customer Insights-API's om gegevens te beoordelen.
ms.date: 05/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8843fc04e4e6eaba0019d932c54f62561ffbdb92
ms.sourcegitcommit: f3c12ad445d5f91a88f91a7bbc40790ebcfaa826
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/06/2022
ms.locfileid: "9121556"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>Voorbeelden van OData-query's voor Customer Insights-API's

Het Open Data Protocol (OData) is een gegevenstoegangsprotocol dat is gebaseerd op kernprotocollen zoals HTTP. Het maakt gebruik van algemeen aanvaarde methodologieën zoals REST voor het web. Er zijn verschillende soorten bibliotheken en hulpprogramma's die kunnen worden gebruikt om OData-services te gebruiken.

Dit artikel bevat enkele veelgevraagde voorbeeldquery's om u te helpen bij het bouwen van uw eigen implementaties op basis van de [Customer Insights-API's](apis.md).

U moet de queryvoorbeelden wijzigen om ze te laten werken in de doelomgevingen: 

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}/data` waar {instanceId} is de GUID van de Customer Insights-omgeving waarop u een query wilt uitvoeren. De [ListAllInstances-bewerking](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) laat u de {InstanceId} vinden waartoe u toegang hebt.
- {CID}: GUID van een geharmoniseerde klantenrecord. Voorbeeld: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: id van de primaire sleutel van een klantenrecord in een gegevensbron. Voorbeeld: `CNTID_1002`
- {DSname}: tekenreeks met de entiteitsnaam van een gegevensbron die wordt opgenomen in Customer Insights. Voorbeeld: `Website_contacts`.
- {SegmentName}: tekenreeks met de naam van de uitvoerentiteit van een segment in Customer Insights. Voorbeeld: `Male_under_40`.

## <a name="customer"></a>klant

De volgende tabel bevat een set voorbeeldquery's voor de entiteit *Customer*.

|Querytype |Voorbeeld  | Notitie  |
|---------|---------|---------|
|Eén klant-id     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Alternatieve sleutel    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  Alternatieve sleutels blijven bestaan in de geharmoniseerde klantentiteit       |
|Select   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|Over    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Alternatieve sleutel + In   | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Zoeken  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Retourneert top 10 resultaten voor een zoekreeks      |
|Segmentlidmaatschap  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Retourneert een vooraf ingesteld aantal rijen van de segmentatie-entiteit.      |
|Segmentlidmaatschap voor een klant | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'&IsMemberOfSegment('{SegmentName}')`     | Retourneert het klantprofiel als ze lid zijn van het opgegeven segment     |

## <a name="unified-activity"></a>Geharmoniseerde activiteit

De volgende tabel bevat een set voorbeeldquery's voor de entiteit *UnifiedActivity*.

|Querytype |Voorbeeld  | Notitie  |
|---------|---------|---------|
|Activiteit van cid     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Geeft activiteiten van een specifiek klantprofiel weer |
|Tijdsbestek van activiteit    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Activiteiten van een klantprofiel binnen een tijdsbestek       |
|Type activiteit    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Activiteit per weergavenaam     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Activiteiten sorteren    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  In oplopende of aflopende volgorde activiteiten sorteren       |
|Activiteit uitgebreid uit segmentlidmaatschap  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Andere voorbeelden

De volgende tabel bevat een set voorbeeldquery's voor andere entiteiten.

|Querytype |Voorbeeld  | Notitie  |
|---------|---------|---------|
|Meetcriteria van cid    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Verrijkte merken van cid    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Verrijkte interesses van cid    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|In-component + uitbreiden     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>Niet ondersteunde OData-query's

De volgende query's worden niet ondersteund door Customer Insights:

- `$filter` in opgenomen bronentiteiten. U kunt alleen $filter-query's uitvoeren op systeementiteiten die door Customer Insights worden gemaakt.
- `$expand` bij een `$search`-query. Voorbeeld: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` bij `$select` als alleen een subset van kenmerken is geselecteerd. Voorbeeld: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- Met `$expand` verrijkte merk- of interesseaffiniteiten voor een bepaalde klant. Voorbeeld: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Uitvoerentiteiten voor queryvoorspellingsmodel via alternatieve sleutel. Voorbeeld: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
