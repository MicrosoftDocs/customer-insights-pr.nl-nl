---
title: Voorgestelde segmenten op basis van activiteit.
description: Laat Machine Learning u helpen nieuwe en interessante segmenten te vinden op basis van klantactiviteit.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: 9c10a32b770ea110a1166f20f72116a3a12cb92e
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354457"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a>Voorgestelde segmenten op basis van activiteitsgegevens (preview)

Ontdek interessante segmenten van uw klanten op basis van klantactiviteitsgegevens die worden opgenomen in Customer Insights. Voorbeelden van activiteitsgegevens zijn transacties, duur van ondersteuningsgesprekken, aankopen of retouren. Als u segmenten wilt voorstellen, worden activiteitsgegevens geanalyseerd op recentheid, frequentie en geldwaarde (of duur). Als alternatief kunt u [voorgestelde segmenten genereren om een meting te verbeteren of om beter te begrijpen waardoor een kenmerk wordt beïnvloed](suggested-segments.md).

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Tabblad Voorgestelde segmenten met segmentsuggesties voor op activiteit gebaseerde en kenmerkgebaseerde segmenten.":::

## <a name="categorize-customers-by-activity"></a>Klanten op activiteit categoriseren

Met [activiteitsgegevens](activities.md) die beschikbaar zijn in Customer Insights, kunnen we suggesties genereren die klantgroepen vertegenwoordigen:

- meest actieve klanten 
- klanten die de meeste aankopen hebben gedaan 
- klanten die de meeste inkomsten hebben gegenereerd 
- klanten die de laatste tijd niet actief zijn geweest 
- klanten die regelmatig contact hebben met uw bedrijf  

Als u een detailhandel hebt, kunt u erachter komen welke klanten de meeste inkomsten genereren en hen belonen met een kortingsbon. Of u kunt incidentele klanten identificeren en hen aanbieden om deel te nemen aan een beloningsprogramma, zodat ze uw bedrijf vaker bezoeken.
Als u in de gezondheidszorg werkt en het uw doel is om de kosten voor individuele patiënten te minimaliseren. Een manier zou zijn om het aantal terugkerende bezoeken terug te brengen door in zo min mogelijk bezoeken de best mogelijke zorg te bieden. In dit geval is het uw doel om de bezoekfrequentie laag te houden en terugkerende kosten voor de patiënten te minimaliseren. Of u kunt segmenten van patiënten identificeren die frequente afspraken en hoge terugkerende kosten hebben en deze gevallen analyseren om de behandeling van het individu te verbeteren. 

## <a name="required-data"></a>Vereiste gegevens

Suggesties worden gegenereerd op basis van de geselecteerde invoergegevens. 

- Klantprofielen: alle klanten of leden van een specifiek segment. 

- Tijdsperiode: vorige maand, vorig jaar of een aangepast tijdsbestek.

- Type activiteit: aankopen, detailhandelstransacties, online transacties, klantondersteuningsgevallen, abonnementen, enzovoort.  

- Entiteit in Customer Insights die de activiteitsgegevens bevat: de UnifiedActivity-entiteit of de entiteit voor een specifieke activiteit. 

- Op te nemen dimensies: recentheid, frequentie of geldelijke dimensie, afhankelijk van uw zakelijke vereisten.

## <a name="generate-suggested-segments"></a>Voorgestelde segmenten genereren

1. Ga naar **Segmenten**.

1. Selecteer het tabblad **Suggesties (preview)**.

1. Selecteer **Nieuwe suggesties zoeken** en kies **Klantgedrag bekijken of erop anticiperen**. Selecteer **Starten** om de begeleide ervaring uit te voeren.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Eerste stap van de configuratiewizard voor een voorgesteld segment op basis van activiteit.":::

1. Geef de vereiste invoergegevens op en selecteer **Volgende** om door te gaan.

   - Kies klanten: neem alle klanten of een specifiek segment op.
   - Kies activiteit: selecteer het activiteitstype en de entiteiten die de activiteit beschrijven.
   - Voorkeuren: stel de te overwegen tijdsperiode in, de factoren voor suggesties en breng de kenmerken in kaart.

1. Controleer uw invoer en selecteer **Uitvoeren** om het model uit te voeren en suggesties te genereren.

1. Afhankelijk van het aantal klantprofielen en geselecteerde activiteiten kan het voltooien enkele minuten duren. 

Nadat u de suggesties hebt gegenereerd, kunt u ze filteren op de dimensie of waarde waarin u het meest geïnteresseerd bent. 

## <a name="view-details-of-a-suggested-segment"></a>Details van een voorgesteld segment weergeven

Zodra de suggesties zijn gegenereerd, vindt u ze vermeld in **Segmenten** > **Suggesties (preview)** in de sectie **Op activiteiten gebaseerde suggesties**.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Uitgebreid zijvenster met gedetailleerde gegevens van een voorgesteld segment.":::

Selecteer **Suggestie bekijken** in een voorgesteld segment om de details van dat segment te bekijken. Het zijvenster bevat details zoals de omvang van elke dimensie in vergelijking met de doelgroep. Het benadrukt ook het aantal potentiële leden in het segment en het overeenkomstige percentage van de totale klanten. Als u de suggestie als segment wilt behouden, selecteert u **Segment maken**.    

## <a name="save-a-suggestion-as-a-segment"></a>Een suggestie als een segment opslaan

1. Ga naar **Segmenten** > **Suggesties (preview)** ​.

1. Selecteer het segment dat u wilt opslaan. 

1. Selecteer in het zijvenster **Segment maken**. 

1. Nadat het segment is opgeslagen, wordt het weergegeven in de lijst met segmenten op het tabblad **Alle segmenten**. Het kan nu worden [vernieuwd of verwijderd zoals elk ander segment ](segments.md). U kunt de segmentdetails niet bewerken. U kunt echter de invoercriteria voor de suggesties wijzigen en verschillende suggesties genereren.

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Een reeks suggesties vernieuwen of bewerken

1. Ga naar **Segmenten** > **Suggesties (preview)** en zoek het segment in de sectie **Op activiteiten gebaseerde suggesties**.

1. Selecteer **Suggesties vernieuwen** om de suggesties te vernieuwen en tegelijk de geconfigureerde kenmerken te behouden. Of selecteer **Suggesties bewerken** om de geconfigureerde kenmerken te wijzigen. Het proces wordt opnieuw uitgevoerd, segmentsuggesties worden gegenereerd op basis van de nieuwste gegevens en de huidige suggesties worden vervangen.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
