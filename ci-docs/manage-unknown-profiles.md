---
title: Onbekende profielen beheren met Customer Insights
description: Werk met onbekende klantprofielen die worden gemaakt en beheerd in Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: 0e12f64a22b93d117009fb8aee76d02a7583e699
ms.sourcegitcommit: 24627d53dcdf607baaab1cc3c299a3584c386173
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/15/2022
ms.locfileid: "9776815"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Onbekende profielen beheren met Customer Insights

Internetgebruikers zijn vaak ongeïdentificeerd of anoniem online. Zelfs de meest loyale klanten kunnen "onbekend" lijken als ze niet op verschillende apparaten zijn aangemeld. Voor veel merken zijn bekende of geverifieerde gebruikers de minderheid, ondanks de groeiende verwachtingen van klanten ten aanzien van personalisatie. Omdat de toekomst van cookies van derden ter discussie staat, is het beheren van first party-gegevens cruciaal om gedifferentieerde gepersonaliseerde ervaringen te bereiken.

Memorabele personalisatie hangt af van hoe goed u uw klant kent en Customer Insights helpt u daarbij door al uw klanten te volgen.  U hoeft het gebruik van gegevens die aan het begin van de klantreis zijn verzameld, niet te beperken of te stoppen. Met Customer Insights kunt u uw eigen gegevens gebruiken om een klantprofiel te maken voor onbekende gebruikers. U kunt dat profiel vervolgens gebruiken voor verdere acties, ondanks ontbrekende contactgegevens. Importeer first party-gegevens uit bronnen zoals web-, mobiele of CRM-systemen in Customer Insights om klantprofielen continu te verrijken. Naarmate u meer interacties samenvoegt, [maakt u van de *onbekende* klant een *bekende* klant](unknown-to-known.md).

## <a name="sample-scenario"></a>Voorbeeldscenario

Stel dat een gebruiker zijn mobiele apparaat gebruikt om door uw e-commercesite te bladeren. De website geeft de bezoeker de naam mobile_guest123 als een unieke id en u begint gedragsactiviteiten te verzamelen op basis van zijn/haar online activiteit. Hierbij gaat het bijvoorbeeld om welke pagina's ze hebben bezocht, hoeveel tijd ze op die pagina's hebben doorgebracht of op welke koppelingen ze hebben geklikt. U kent hun naam of e-mailadres niet, maar deze gegevens kunnen merken zinvolle inzichten geven over deze specifieke gebruiker. Op uw beurt kunt u die inzichten gebruiken wanneer die gebruiker de site weer bezoekt. Zoek in Customer Insights naar mobile_guest123 om de lijst met segmenten van de gebruiker, met bijvoorbeeld 'organisch', 'mobiele klanten vooraf bestellen' of 'hoogwaardige klanten' op te halen. Of haal het profiel op om gepersonaliseerde webervaringen te maken. U kunt de gegevens ook exporteren naar een activeringssysteem om hetzelfde te doen.

## <a name="prerequisites"></a>Vereisten

- First party-gegevens opnemen in Customer Insights
- Elke entiteit heeft een unieke id die is ingesteld als primaire sleutel
- Elke entiteit met een primaire sleutel voor personalisatie wordt samengevoegd
- Het contentmanagementsysteem van uw website kan API's gebruiken (voor webpersonalisatie op basis van directe communicatie met Customer Insights)

In de volgende tabel ziet u een vereenvoudigd voorbeeld van hoe webgebeurtenissen met een hoge waarde kunnen worden vastgelegd.

|EventID|EventTimeStamp|UserID|PrimaryKey|EventName|
|--|--|--|--|--|
|0|15-09-2022 9:00:00|abc123|CookieID1|Productweergave|
|2|18-09-2022 10:05:00|abc123|CookieID1|Productweergave|
|5|18-09-2022 10:10:00|abc123|CookieID1|Toevoegen aan winkelwagen|
|4|21-09-2022 09:05:00|abc123|CookieID1|Productweergave|

## <a name="data-ingestion"></a>Gegevensopname

Zie voor meer informatie over de beschikbare opties voor gegevensopname [Overzicht gegevensbronnen](data-sources.md).

## <a name="data-unification"></a>Gegevensharmonisatie

Zie [Overzicht van gegevensharmonisatie](data-unification.md) voor meer informatie over het harmoniseren van klantprofielen.

## <a name="get-insights"></a>Inzichten verwerven

[Verrijk](enrichment-hub.md) uw gegevens, maak [metingen](measures.md) en maak [segmenten](segments.md) voor verdere activering.

U kunt bijvoorbeeld segmenten maken van onbekende gebruikers die door dezelfde productpagina's hebben gebladerd, maar nooit hebben afgerekend.

## <a name="activation"></a>Activering

Met uw gegevens in Customer Insights en uw inzichten klaar om aan de slag te gaan, kunt u Customer Insights gebruiken voor personalisatie:

1. Gebruik de [OData-API](apis.md) om een segmentlidmaatschap of klantprofiel op te halen. Zie [Voorbeelden van OData-query's voor Customer Insights-API's](odata-examples.md) voor meer informatie.

1. [Exporteer](export-destinations.md) uw gegevens naar uw activeringssystemen.

Voorbeeld: een onbekende gebruiker bezoekt een website meerdere keren en bezoekt productpagina's voor verschillende modellen leren schoenen. Met die gegevens beschikbaar in Customer Insights kunt u de onbekende gebruiker opnemen in het segment van mensen die geïnteresseerd zijn in leren schoenen. Gebruik dit segment om de oplossing voor personalisatie van uw website te informeren voor terugkerende bezoekers. Bij het volgende bezoek herkent de site de onbekende gebruiker en kan een kortingsbon van 10% op leren schoenen worden aangeboden.

[!INCLUDE [footer-include](includes/footer-banner.md)]
