---
title: Vergelijkbare klanten zoeken met AI (met video)
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
ms.openlocfilehash: 7877349817829f7486a63a1355a81361e1cb2c13
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646197"
---
# <a name="similar-customers-preview"></a>Vergelijkbare klanten (preview)

Met deze functie kunt u vergelijkbare klanten in uw klantenbestand zoeken met behulp van kunstmatige intelligentie. U moet ten minste één segment hebben gemaakt om deze functie te kunnen gebruiken. Door de criteria van een bestaand segment uit te breiden, kunt u klanten vinden die vergelijkbaar zijn met dat segment.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Vergelijkbare klanten zoeken* gebruikt geautomatiseerde middelen om gegevens te evalueren en voorspellingen te doen op basis van die gegevens, en heeft daarom de mogelijkheid om te worden gebruikt als profileringsmethode, zoals die term wordt gedefinieerd door de Algemene verordening gegevensbescherming ("AVG"). Op het gebruik door de klant van deze functie om gegevens te verwerken, zijn mogelijk de AVG of andere wetten of voorschriften van toepassing. U bent ervoor verantwoordelijk dat uw gebruik van Dynamics 365 Customer Insights, inclusief voorspellingen, voldoet aan alle toepasselijke wet- en regelgeving, inclusief wetten met betrekking tot privacy, persoonsgegevens, biometrische gegevens, gegevensbescherming en vertrouwelijkheid van communicatie.

## <a name="finding-similar-customers"></a>Vergelijkbare klanten zoeken

1. Ga naar **Segmenten** en selecteer het segment waarop u uw nieuwe segment wilt baseren. Dat is uw *bronsegment*.

1. Selecteer in de actiebalk **Vergelijkbare klanten zoeken**.

1. Bekijk de voorgestelde naam voor uw nieuwe segment en wijzig deze indien nodig.

1. Voeg optioneel [tags](work-with-tags-columns.md#manage-tags) toe aan het nieuwe segment.

1. Bekijk de velden die uw nieuwe segment definiëren. Deze velden definiëren de basis waarop het systeem zal proberen vergelijkbare klanten te vinden voor uw bronsegment. Het systeem selecteert standaard aanbevolen velden.
  Velden die de modelprestaties aanzienlijk kunnen verminderen, worden automatisch uitgesloten:
  
   - Velden met de volgende gegevenstypen: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Velden met een kardinaliteit (het aantal elementen in een veld) van minder dan 2 of meer dan 30

1. Kies of u **Alle klanten** wilt opnemen of alleen klanten in een **Specifiek bestaand segment** in uw nieuwe segment.

1. Standaard stelt het systeem voor om slechts 20% van de doelgroep op te nemen in uw uitvoer. Bewerk deze drempelwaarde indien nodig. Als de drempelwaarde wordt verhoogd, neemt de precisie af.

1. Neem klanten op in uw bronsegment door het selectievakje **Neem naast klanten met vergelijkbare kenmerken ook leden uit bronsegment op** in te schakelen.

1. Selecteer **Uitvoeren** onder aan de pagina om een binaire classificatietaak te starten (een methode van Machine Learning) die de gegevensset analyseert.

## <a name="view-the-similar-segment"></a>Het vergelijkbare segment bekijken

Na het verwerken van het vergelijkbare segment, vindt u het nieuwe segment vermeld op de pagina **Segmenten**.

> [!div class="mx-imgBorder"]
> ![Segment van vergelijkbare klanten.](media/expanded-segment.png "Segment van vergelijkbare klanten")

Selecteer **Weergeven** op de actiebalk om het segmentdetail te openen. Deze weergave bevat informatie over de resultaatverdeling tussen [overeenkomstscores](#about-similarity-scores). U vindt de waarden voor de overeenkomstscore ook in **Voorbeeld van segmentleden**.

## <a name="use-the-output-of-a-similar-segment"></a>De uitvoer van een vergelijkbaar segment gebruiken

U kunt [werken met de uitvoer van een vergelijkbaar segment](segments.md) zoals u doet met andere segmenten. U kunt bijvoorbeeld het segment exporteren of een meting bouwen.

## <a name="refresh-and-edit-a-similar-segment"></a>Een vergelijkbaar segment vernieuwen en bewerken

Als u een vergelijkbaar segment wilt vernieuwen, selecteert u het op de pagina **Segmenten** en selecteert u **Vernieuwen** op de actiebalk.

Als u een vergelijkbaar segment bewerkt, worden uw gegevens opnieuw verwerkt. Het eerder gemaakte segment wordt bijgewerkt met vernieuwde gegevens.
Als u een vergelijkbaar segment wilt bewerken, selecteert u het op de pagina **Segmenten** en selecteert u **Bewerken** op de actiebalk. Pas uw wijzigingen toe en selecteer **Uitvoeren** om de verwerking te starten.

## <a name="delete-a-similar-segment"></a>Een vergelijkbaar segment verwijderen

Selecteer het segment op de pagina **Segmenten** en selecteer vervolgens **Verwijderen** op de actiebalk. Bevestig vervolgens uw verwijdering.

## <a name="about-similarity-scores"></a>Info over overeenkomstscores

Het Machine Learning-model voor binaire classificatie kent een score toe aan klanten in het vergelijkbare segment. De score is gebaseerd op de overeenkomst met klanten in het bronsegment.

- Klanten met vergelijkbaarheidsscores onder 0,55 zijn klanten die door het systeem worden geclassificeerd *niet vergelijkbaar* met klanten in het bronsegment
- Klanten met overeenkomstscores tussen 0,55 en 0,7 worden geclassificeerd als *enigszins vergelijkbaar*
- Klanten met overeenkomstscores tussen 0,7 en 0,85 worden geclassificeerd als *vergelijkbaar*
- Klanten met overeenkomstscores tussen 0,85 en 1 zijn klanten die door het systeem als *zeer vergelijkbaar* worden geclassificeerd

Klanten met een overeenkomstscore onder de 0,4 worden niet opgenomen in de modeluitvoer. Het systeem beschouwt ze niet als vergelijkbaar genoeg met het bronsegment.

[!INCLUDE [footer-include](includes/footer-banner.md)]
