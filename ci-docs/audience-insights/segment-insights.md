---
title: Segmentinzichten voor bestaande segmenten
description: Krijg inzicht in bestaande segmenten om verschillen en overeenkomsten te zien.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 977d250e5f8c52551b9f3ae9c5e805e946f2579fbe7b04f97fbac880debbac2a
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035865"
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

Zoek na het voltooien van de analyse naar details over dit inzicht in **Segmenten** > **Inzichten (preview)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Inzichtdetails voor overlapping van segmenten.":::

Selecteer een inzicht om de analyseresultaten te bekijken:

- Het aantal leden dat segmenten overlapt die zijn geselecteerd voor analyse.
- Het aantal leden dat is opgenomen in een van de segmenten, maar niet in de rest van de segmenten.
- Als u velden hebt geselecteerd tijdens het configureren van de overlappingsanalyse, vindt u deze op de bijbehorende tabbladen. U kunt de vervolgkeuzelijst voor filteren gebruiken om elk kenmerkniveau van belang te selecteren en de tabel onderaan toont de bijbehorende gegevens.

## <a name="segment-differentiators"></a>Segmentdifferentiators

Segmentonderscheiders helpen u te achterhalen wat een segment onderscheidt van de rest van uw klanten of van een ander segment. U hoeft alleen maar een segment te selecteren en het systeem identificeert profielkenmerken en metingen die het geselecteerde segment onderscheiden.

### <a name="run-a-differentiator-analysis"></a>Een onderscheidingsanalyse uitvoeren

1. Ga naar **Segmenten** en selecteer het tabblad **Inzichten (preview)**.

1. Selecteer **Nieuw** en kies de optie **Overlappen** in het deelvenster **Inzichttype kiezen**.

1. Kies het segment dat u wilt analyseren als **Primair segment** en selecteer daarna **Volgende**.

1. Kies **Alle klanten** of een **secundair segment** om uw primaire segment mee te vergelijken en selecteer daarna **Volgende**.

1. Kies optioneel een of meer interessegebieden om de analyse op specifieke kenmerken te concentreren en selecteer **Volgende**.

1. Geef een naam op voor uw overlappingsanalyse, een optionele weergavenaam en een beschrijving.

1. Selecteer **Opslaan** om de analyse te starten. De overlappingsanalyse is gereed wanneer de status verandert van Vernieuwen in Geslaagd.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Een onderscheidingsanalyse bekijken en optimaliseren

Zoek na het voltooien van de analyse naar details over dit inzicht in **Segmenten** > **Inzichten (preview)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Inzichtdetails voor het onderscheiden van segmenten.":::

Selecteer een inzicht om de analyseresultaten te bekijken. Een onderscheidingsanalyse bevat twee tabbladen. Het tabblad **Kenmerken** geeft profielkenmerken weer die als onderscheidende factoren worden beschouwd. Het tabblad **Metingen** geeft onderscheidende factoren aan. Elk tabblad bevat de volgende details:

- Gerangschikte lijst van onderscheidende factoren, gesorteerd op verschilscore.
- De **verschilscore** voor elke onderscheidende factor. De verschilscore vertegenwoordigt de mate van verschil van een kenmerk tussen twee segmenten. Hoe hoger de verschilscore, hoe meer de kenmerken verschillen tussen de twee segmenten. Selecteer een score om het deelvenster **Verschilscore** te openen met de verdelingen van waarden voor dat kenmerk.

## <a name="manage-segment-insights"></a>Segmentinzichten beheren

U kunt de volgende opties gebruiken voor uw inzichten vanaf de opdrachtbalk:

- **Terug** om terug te gaan naar de lijst met inzichten
- **Vernieuwen** om de analyse opnieuw uit te voeren
- **Verwijderen** om dit inzicht te verwijderen


[!INCLUDE[footer-include](../includes/footer-banner.md)]