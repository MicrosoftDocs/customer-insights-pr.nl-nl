---
title: Uw ervaringen personaliseren met gegevens over bekende en onbekende gebruikers
description: Verwerk de informatie over voorheen onbekende gebruikers wanneer u hun identiteit kent.
ms.date: 07/07/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 8e3477750d82f965dc2d62174fb35554d9447b7b
ms.sourcegitcommit: 52eca81c36e93d553140f5a37cf6013aaa42623a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/03/2022
ms.locfileid: "9224289"
---
# <a name="personalize-your-experiences-with-data-about-known-and-unknown-users"></a>Uw ervaringen personaliseren met gegevens over bekende en onbekende gebruikers

Het beheren van klantgegevens is geen nieuwe uitdaging, maar het wordt steeds moeilijker naarmate gebruikers navigeren door de verschillende digitale kanalen die merken bieden. Een gebruiker die bekend (geverifieerd) is in het ene kanaal, wordt onbekend (niet-geverifieerd) in een ander kanaal als hij/zij niet is aangemeld. Het probleem is vaak dat niet-geverifieerde (onbekende) gebruikers geen algemene id hebben. De id kan worden gebruikt om betekenisvolle profielkenmerken te koppelen en geharmoniseerde klantprofielen te genereren. Customer Insights helpt dit probleem op te lossen door gegevens van bijhoudmethoden in uw bronsystemen op te nemen. Consolideer onbekende en bekende profielen om organisaties een compleet overzicht te bieden van actuele profielen en hun historische transacties, gedragingen en demografische gegevens. Het gaat zelfs nog een stap verder door identiteitsresolutie te bieden waarmee u klantactiviteiten via meerdere kanalen kunt harmoniseren, waaronder uw website, aankopen in de winkel, loyaliteitsprogramma's, enzovoort.

## <a name="sample-scenario"></a>Voorbeeldscenario

Laten we als voorbeeld een koffieketen nemen, die een breed bestand heeft van klanten die koffie en eten in winkels kopen en producten online bestellen. Vaak worden online bezoekers niet geverifieerd wanneer ze door de producten bladeren, waardoor ze "onbekende gebruikers" zijn. Het is moeilijk voor de koffieketen om gepersonaliseerde aanbiedingen en ervaringen te leveren als gebruikers onbekend zijn. Aan de andere kant kunnen klanten inloggen op hun account en "bekende gebruikers" van het bedrijf worden door lid te worden van een loyaliteitssysteem, dat op zijn beurt meer gepersonaliseerde ervaringen mogelijk maakt. Customer Insights kan de koffieketen helpen inzicht te krijgen in bekende en voorheen onbekende gebruikers.

Met Customer Insights kan het bedrijf klantprofielen combineren met activiteitsgegevens van niet-geverifieerde (onbekende) sessies nadat een gebruiker zich heeft aangemeld en bekend wordt. De koffieketen kan gegevens uit andere gegevensbronnen gebruiken met behulp van ingebouwde connectoren in Customer Insights om identiteiten voor klanten uit verschillende kanalen samen te voegen.

## <a name="prerequisites"></a>Vereisten

- Webgegevens worden verzameld en bevatten "bezoekers-ID's" voor alle bezoekers.
- Webgegevens bevatten "geverifieerde gebruikers-id's" voor ingelogde bezoekers. Deze id's zijn gekoppeld aan het loyaliteitssysteem.
- Hoogwaardige gebeurtenisgegevens zoals 'productweergave' en 'afrekenen' worden gedefinieerd en opgenomen in de brongegevens, samen met de tijdstempel van de gebeurtenis en een gebeurtenis-id.

In de volgende tabel ziet u een vereenvoudigd voorbeeld van hoe webgebeurtenissen met een hoge waarde kunnen worden vastgelegd.

|EventID|EventTimeStamp|UserID|LoyaltyID|EventName|
|--|--|--|--|--|
|0|23-07-2022 10:00:00|abc123|--|Productweergave|
|2|23-07-2022 10:05:00|abc123|707|Loyaliteitsaanmelding|
|5|23-07-2022 10:10:00|abc123|707|Uitchecken|
|4|23-07-2022 10:20:00|xyz789|--|Productweergave|

## <a name="data-ingestion"></a>Gegevensopname

Gegevens over klanten kunnen afkomstig zijn van uw website als gebeurtenisgegevens en kunnen worden opgeslagen in uw eigen interne of externe gegevensanalyseservices. De webgegevens bevatten bekende en onbekende gebruikers als de website een verificatiestroom heeft die is geïntegreerd met een verificatieservice. Bijvoorbeeld een eCommerce-systeem waarbij gebruikers hun volledige gegevens moeten verstrekken om een aankooptransactie af te ronden. Of een loyaliteitssysteem dat verificatie vereist om een geldige ontvanger van de rewards-kortingen te bevestigen.

De gebeurtenisgegevens in ons voorbeeld hierboven bevatten de verschillende profiel-id's van de bekende en onbekende gebruikers. In gebeurtenis 1 en 4 zijn de gebruikers onbekend, terwijl in gebeurtenis 2 en 3 de gebruiker met de id abc123 zich aanmeldt voor een loyaliteitsprogramma.

:::image type="content" source="media/website-data-source.png" alt-text="Gegevensbronnen waaronder de Contoso-website.":::

Zie voor meer informatie over de beschikbare opties voor gegevensopname [Overzicht gegevensbronnen](data-sources.md).

## <a name="data-unification"></a>Gegevensharmonisatie

Het convergeren van onbekende identiteiten met bekende identiteiten helpt personalisatie mogelijk te maken op basis van gebruikersgedrag, ongeacht hun profielstatus (bekend of onbekend). Gepersonaliseerde inhoud voor alle gebruikers helpt klanten snel bij de meest relevante producten of diensten te komen waarin ze op dat moment geïnteresseerd zijn.

Aangezien sommige gebruikers in onze gegevens bekend zijn, kunnen we Customer Insights gebruiken om die gegevens te combineren met het gebruikersprofiel. Zie [Overzicht van gegevensharmonisatie](data-unification.md) voor meer informatie over het harmoniseren van klantprofielen.

1. Selecteer de bronvelden uit de webgegevensentiteit. Gebruik de profielgegevens die zijn opgeslagen in uw webgegevens en selecteer de velden die id's met demografische gegevens vertegenwoordigen.

   :::image type="content" source="media/website-source-fields.png" alt-text="Bronvelden selecteren voor de webgegevensbron.":::

1. Regels toevoegen om dubbele records samen te voegen. Kies voor webgegevens de meest gevulde gegevens.

1. Regels en voorwaarden voor overeenkomsten configureren. De gebeurtenisgegevens van webprofielen in dit voorbeeld worden op id's gematcht met de profielen uit de andere gegevensbronnen die klantinformatie bevatten. Stel exacte overeenkomstregels voor id's in als afzonderlijke regels met elk van de andere profielentiteiten die een overeenkomstige primaire sleutel of id-overeenkomst hebben. In het voorbeeld worden profielgegevens van webgebeurtenissen gebruikt als de laatste overeenkomende entiteit, zodat eerst andere profielgegevens worden gecombineerd.
   1. Als **Alle records opnemen** niet wordt geselecteerd, worden geharmoniseerde profielen gemaakt voor bekende gebruikers en worden hun bijbehorende onbekende gebruikers-id's opgenomen. Het is handig in scenario's waarin u geïnteresseerd bent in het bekijken van eerdere gedragsactiviteiten van bekende gebruikers toen ze nog onbekend waren.
   1. Als **Alle records opnemen** is geselecteerd, worden aparte profielrecords voor onbekende gebruikers gemaakt. Onbekende gebruikers krijgen een unieke klant-id. Wanneer in de toekomst een bekend profiel wordt gekoppeld aan de profielgegevens van webgebeurtenissen, kan het traject van de nieuwe bekende gebruiker ook worden bekeken en gebruikt voor personalisatie op basis van onbekende gedragsgegevens uit het verleden.

:::image type="content" source="media/website-match-rule.png" alt-text="Overeenkomstregel voor de gegevensbronentiteit van de website.":::

## <a name="get-insights"></a>Inzichten verwerven

Als klantprofielen worden gemaakt voor onbekende en bekende gebruikers, kunnen de webgebeurtenisgegevens van hoge waarde worden gebruikt als [activiteiten](activities.md). Deze activiteiten kunnen worden gebruikt om meer inzichten te creëren. Klanten die bijvoorbeeld zes maanden geleden een website bezochten (toen ze nog onbekend waren) of klanten die geen loyaliteits-id hebben, hebben nooit afgerekend.

:::image type="content" source="media/website-known-unknown.png" alt-text="Schermopnamen van de klantenpagina met bekende en onbekende klanten.":::

[Verrijk](enrichment-hub.md) uw gegevens, maak [metingen](measures.md) en maak [segmenten](segments.md) voor verdere activering.

U kunt bijvoorbeeld segmenten maken van bekende gebruikers die sommige producten hebben bekeken, maar nooit hebben afgerekend.

Zie voor meer informatie [Overzicht van segmenten](segments.md).

## <a name="activate-insights"></a>Inzichten activeren

Er zijn verschillende manieren om uw gegevens te exporteren en actie te ondernemen op basis van de onderliggende inzichten.

Zie [Overzicht van exports](export-destinations.md) voor meer informatie.
