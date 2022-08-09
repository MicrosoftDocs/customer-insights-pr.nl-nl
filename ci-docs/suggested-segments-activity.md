---
title: Voorgestelde segmenten op basis van activiteit (preview)
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
ms.openlocfilehash: df4f5f4b5c9a3ad66d57a6b349e18a0d714aff62
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170583"
---
# <a name="suggested-segments-based-on-activity-preview"></a>Voorgestelde segmenten op basis van activiteit (preview)

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
Als u in de gezondheidszorg werkt en uw doel is om de kosten voor individuele patiënten te minimaliseren, kunt u proberen terugkerende bezoeken te verminderen door de best mogelijke zorg te bieden in een zo klein mogelijk aantal bezoeken. In dit geval is het uw doel om de bezoekfrequentie laag te houden en terugkerende kosten voor de patiënten te minimaliseren. Of u kunt segmenten van patiënten identificeren die frequente afspraken en hoge terugkerende kosten hebben en deze gevallen analyseren om de behandeling van het individu te verbeteren.

## <a name="required-data"></a>Vereiste gegevens

Suggesties worden gegenereerd op basis van de geselecteerde invoergegevens.

- Klantprofielen: alle klanten of leden van een specifiek segment.

- Tijdsperiode: vorige maand, vorig jaar of een aangepast tijdsbestek.

- Type activiteit: aankopen, detailhandelstransacties, online transacties, klantondersteuningsgevallen, abonnementen, enzovoort.  

- Entiteit in Customer Insights die de activiteitsgegevens bevat: de UnifiedActivity-entiteit of de entiteit voor een specifieke activiteit.

- Op te nemen dimensies: recentheid, frequentie of geldelijke dimensie, afhankelijk van uw zakelijke vereisten.

## <a name="generate-suggested-segments"></a>Voorgestelde segmenten genereren

1. Ga naar **Segmenten** en selecteer het tabblad **Suggesties (preview)**.

1. Selecteer **Nieuwe suggesties zoeken** en kies **Klantgedrag bekijken of erop anticiperen**. Selecteer **Starten**.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Eerste stap van de configuratiewizard voor een voorgesteld segment op basis van activiteit.":::

1. Geef de vereiste invoergegevens op en selecteer **Volgende**.

   - Kies klanten: neem alle klanten of een specifiek segment op.
   - Kies activiteit: selecteer het activiteitstype en de entiteiten die de activiteit beschrijven.
   - Voorkeuren: stel de te overwegen tijdsperiode in, de factoren voor suggesties en breng de kenmerken in kaart.

1. Controleer uw invoer en selecteer **Uitvoeren** om het model uit te voeren en suggesties te genereren.

Afhankelijk van het aantal klantprofielen en geselecteerde activiteiten kan het voltooien enkele minuten duren.

Nadat u de suggesties hebt gegenereerd, kunt u ze filteren op de dimensie of waarde waarin u het meest geïnteresseerd bent.

## <a name="manage-suggested-segments"></a>Voorgestelde segmenten beheren

Ga naar **Segmenten** en selecteer het tabblad **Suggesties (preview)**. Selecteer in de sectie **Op activiteiten gebaseerde suggesties** een voorgesteld segment om beschikbare acties te bekijken.

- Selecteer **Suggestie bekijken** om de details van dat segment te bekijken, zoals de omvang van elke dimensie in vergelijking met de doelgroep. Het benadrukt ook het aantal potentiële leden in het segment en het overeenkomstige percentage van de totale klanten.
- Selecteer **Segment maken** om de suggestie als een segment op te slaan. Het wordt weergegeven op het tabblad **Alle segmenten** en kan worden [vernieuwd of verwijderd](segments.md). U kunt de segmentdetails niet bewerken. U kunt echter de invoercriteria voor de suggesties wijzigen en verschillende suggesties genereren.
- Selecteer **Suggesties bewerken** om de geconfigureerde kenmerken te wijzigen die de huidige suggesties vervangen.
- Selecteer **Suggesties vernieuwen** om de suggesties te vernieuwen en tegelijkertijd de geconfigureerde kenmerken te behouden.

[!INCLUDE [footer-include](includes/footer-banner.md)]
