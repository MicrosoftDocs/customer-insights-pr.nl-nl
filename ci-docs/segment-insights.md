---
title: Segmentinzichten (preview)
description: Krijg inzicht in bestaande segmenten om verschillen en overeenkomsten te zien.
ms.date: 06/10/2020
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-segment-insights
- customerInsights
ms.openlocfilehash: ccb33594a3a92e87d307f3300c77772ef8b4a82f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170997"
---
# <a name="segment-insights-preview"></a>Segmentinzichten (preview)

Ontdek aanvullende informatie en inzichten met betrekking tot uw bestaande segmenten. Ontdek wat twee segmenten van elkaar onderscheidt en wat ze gemeen hebben.

## <a name="segment-overlap"></a>Overlapping van segmenten

Segmentoverlappingsanalyse laat zien hoeveel en welke klanten gemeenschappelijk zijn in twee of meer segmenten. Bijvoorbeeld hoe een segment van frequente klanten overlapt met een segment dat klanten bevat die tevreden zijn met uw service of product.
U kunt ook analyseren hoe de overlapping verandert voor specifieke kenmerken.

### <a name="run-an-overlap-analysis"></a>Een overlappingsanalyse uitvoeren

1. Ga naar **Segmenten** en selecteer het tabblad **Inzichten (preview)**.

1. Selecteer **Nieuw** en kies de optie **Overlappen** in het deelvenster **Inzichttype kiezen**.

1. Kies de segmenten waarin u bent geïnteresseerd en selecteer **Volgende**.

1. Kies optioneel een of meer interessegebieden om overlappingen voor elke mogelijke veldwaarde te analyseren en selecteer **Volgende**.

1. Geef een naam op voor uw overlappingsanalyse, een optionele weergavenaam en een beschrijving.

1. Selecteer **Opslaan** om de analyse te starten. De overlappingsanalyse is gereed wanneer de status verandert van Vernieuwen in Geslaagd.

### <a name="view-and-optimize-an-overlap-analysis"></a>Een overlappingsanalyse bekijken en optimaliseren

1. Zoek na het voltooien van de analyse naar details over dit inzicht in **Segmenten** > **Inzichten (preview)**.

   :::image type="content" source="media/segment-overlap.png" alt-text="Inzichtdetails voor overlapping van segmenten.":::

1. Selecteer een inzicht om de analyseresultaten te bekijken:

   - Het aantal leden dat segmenten overlapt die zijn geselecteerd voor analyse.
   - Het aantal leden dat is opgenomen in een van de segmenten, maar niet in de rest van de segmenten.
   - Als u velden hebt geselecteerd tijdens het configureren van de overlappingsanalyse, vindt u deze op de bijbehorende tabbladen. U kunt de vervolgkeuzelijst voor filteren gebruiken om elk kenmerkniveau van belang te selecteren en de tabel onderaan toont de bijbehorende gegevens.

## <a name="segment-differentiators"></a>Segmentdifferentiators

Segmentonderscheiders helpen u te achterhalen wat een segment onderscheidt van de rest van uw klanten of van een ander segment. Selecteer een segment en het systeem identificeert profielkenmerken en metingen die het geselecteerde segment onderscheiden.

### <a name="run-a-differentiator-analysis"></a>Een onderscheidingsanalyse uitvoeren

1. Ga naar **Segmenten** en selecteer het tabblad **Inzichten (preview)**.

1. Selecteer **Nieuw** en kies de optie **Onderscheidende factoren** in het deelvenster **Inzichttype kiezen**.

1. Kies het segment dat u wilt analyseren als **Primair segment** en selecteer daarna **Volgende**.

1. Kies **Alle klanten** of een **secundair segment** om uw primaire segment mee te vergelijken en selecteer daarna **Volgende**.

1. Kies optioneel een of meer interessegebieden om de analyse op specifieke kenmerken te concentreren en selecteer **Volgende**.

1. Geef een naam op voor uw analyse van onderscheidende factoren, een optionele weergavenaam en een beschrijving.

1. Selecteer **Opslaan** om de analyse te starten. De analyse van onderscheidende factoren is gereed wanneer de status verandert van Vernieuwen in Geslaagd.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Een onderscheidingsanalyse bekijken en optimaliseren

1. Ga na het voltooien van de analyse naar **Segmenten** > **Inzichten (preview)**.

   :::image type="content" source="media/segment-differentiators.png" alt-text="Inzichtdetails voor het onderscheiden van segmenten.":::

1. Selecteer een inzicht om de analyseresultaten te bekijken. Een onderscheidingsanalyse bevat twee tabbladen. Het tabblad **Kenmerken** geeft profielkenmerken weer die als onderscheidende factoren worden beschouwd. Het tabblad **Metingen** geeft onderscheidende factoren aan. Elk tabblad bevat de volgende details:

   - Gerangschikte lijst van onderscheidende factoren, gesorteerd op verschilscore.
   - De **verschilscore** voor elke onderscheidende factor. De verschilscore vertegenwoordigt de mate van verschil van een kenmerk tussen twee segmenten. Hoe hoger de verschilscore, hoe meer de kenmerken verschillen tussen de twee segmenten. Selecteer een score om het deelvenster **Verschilscore** te openen met de verdelingen van waarden voor dat kenmerk.

## <a name="manage-segment-insights"></a>Segmentinzichten beheren

Ga naar **Segmenten** > **Inzichten (preview)** om uw segmentinzichten te bekijken en te beheren. Selecteer een segmentinzicht om beschikbare acties te bekijken.

- De inzichtanalyse **bekijken**
- Het inzicht **bewerken** om de eigenschappen ervan te wijzigen
- Het inzicht **vernieuwen** om de analyse opnieuw uit te voeren
- **De naam wijzigen** van het inzicht
- Het inzicht **verwijderen**

[!INCLUDE [footer-include](includes/footer-banner.md)]
