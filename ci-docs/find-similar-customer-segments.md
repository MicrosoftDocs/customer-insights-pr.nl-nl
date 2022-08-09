---
title: Vergelijkbare klanten zoeken met AI (preview) (met video)
description: Vergelijkbare klantsegmenten zoeken met kunstmatige intelligentie.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segment-builder
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 09fe36a4da45d114cbfccf8dad1e7b80b4b7e320
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170721"
---
# <a name="find-similar-customers-with-ai-preview"></a>Vergelijkbare klanten zoeken met AI (preview) (video)

Vind vergelijkbare klanten in uw klantenbestand met behulp van kunstmatige intelligentie. U moet ten minste één segment hebben gemaakt om deze functie te kunnen gebruiken. Door de criteria van een bestaand segment uit te breiden, kunt u gemakkelijker klanten vinden die vergelijkbaar zijn met dat segment.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> Met *Vergelijkbare klanten zoeken* worden geautomatiseerde middelen gebruikt om gegevens te evalueren en voorspellingen te doen op basis van die gegevens. Daarom kan het worden gebruikt als een methode voor profilering, zoals die term is gedefinieerd door de Algemene Verordening Gegevensbescherming ("AVG"). Op het gebruik door de klant van deze functie om gegevens te verwerken, zijn mogelijk de AVG of andere wetten of voorschriften van toepassing. U bent ervoor verantwoordelijk dat uw gebruik van Dynamics 365 Customer Insights, inclusief voorspellingen, voldoet aan alle toepasselijke wet- en regelgeving, inclusief wetten met betrekking tot privacy, persoonsgegevens, biometrische gegevens, gegevensbescherming en vertrouwelijkheid van communicatie.

## <a name="find-similar-customers"></a>Vergelijkbare klanten zoeken

1. Ga naar **Segmenten** en selecteer het segment waarop u uw nieuwe segment wilt baseren. Dat is uw *bronsegment*.

1. Selecteer **Vergelijkbare klanten zoeken**.

1. Bekijk de voorgestelde naam voor uw nieuwe segment en wijzig deze indien nodig.

1. Voeg optioneel [tags](work-with-tags-columns.md#manage-tags) toe aan het nieuwe segment.

1. Bekijk de velden die uw nieuwe segment definiëren. Deze velden definiëren de basis waarop het systeem zal proberen vergelijkbare klanten te vinden voor uw bronsegment. Standaard worden aanbevolen velden geselecteerd. Voeg indien nodig meer velden toe.
  Velden die de modelprestaties aanzienlijk kunnen verminderen, worden automatisch uitgesloten:
  
   - Velden met de volgende gegevenstypen: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Velden met een kardinaliteit (het aantal elementen in een veld) van minder dan 2 of meer dan 30

1. Kies of u **Alle klanten** wilt opnemen behalve het bronsegment of alleen klanten in een **ander segment** in uw nieuwe segment.

1. Standaard stelt het systeem voor om slechts 20% van de doelgroep op te nemen in uw uitvoer. Bewerk deze drempelwaarde indien nodig. Als de drempelwaarde wordt verhoogd, neemt de precisie af.

1. Neem klanten op in uw bronsegment door het selectievakje **Neem naast klanten met vergelijkbare kenmerken ook leden uit bronsegment op** in te schakelen.

1. Selecteer **Uitvoeren** onder aan de pagina om een [binaire classificatietaak](#about-similarity-scores) te starten (een methode van Machine Learning) waarmee de gegevensset worden geanalyseerd.

## <a name="view-the-similar-segment"></a>Het vergelijkbare segment bekijken

Na het verwerken van het vergelijkbare segment vindt u het nieuwe segment vermeld op de pagina **Segmenten** met het type **Uitbreiding**.

Selecteer **Weergeven** om de resultaatverdeling tussen [overeenkomstscores](#about-similarity-scores) en waarden van overeenkomstscores onder **Voorbeeld van segmentleden** te bekijken.

:::image type="content" source="media/expanded-segment.png" alt-text="Segment van vergelijkbare klanten.":::

## <a name="manage-a-similar-segment"></a>Een vergelijkbaar segment beheren

[Werk met en beheer een vergelijkbaar segment](segments.md#manage-existing-segments) zoals u met andere segmenten doet. U kunt bijvoorbeeld het segment exporteren of een meting bouwen.

Een vergelijkbaar segment bewerken, vernieuwen, hernoemen, downloaden en verwijderen. Als u een vergelijkbaar segment bewerkt, worden uw gegevens opnieuw verwerkt. Het eerder gemaakte segment wordt bijgewerkt met vernieuwde gegevens.

## <a name="about-similarity-scores"></a>Info over overeenkomstscores

Het Machine Learning-model voor binaire classificatie kent een score toe aan klanten in het vergelijkbare segment. De score is gebaseerd op de overeenkomst met klanten in het bronsegment.

- Klanten met vergelijkbaarheidsscores onder 0,55 zijn klanten die door het systeem worden geclassificeerd *niet vergelijkbaar* met klanten in het bronsegment
- Klanten met overeenkomstscores tussen 0,55 en 0,7 worden geclassificeerd als *enigszins vergelijkbaar*
- Klanten met overeenkomstscores tussen 0,7 en 0,85 worden geclassificeerd als *vergelijkbaar*
- Klanten met overeenkomstscores tussen 0,85 en 1 zijn klanten die door het systeem als *zeer vergelijkbaar* worden geclassificeerd

Klanten met een overeenkomstscore onder de 0,4 worden niet opgenomen in de modeluitvoer. Het systeem beschouwt ze niet als vergelijkbaar genoeg met het bronsegment.

[!INCLUDE [footer-include](includes/footer-banner.md)]
