---
title: Eenvoudige segmenten met snelle segmenten maken
description: Maak eenvoudige segmenten van klanten om deze te groeperen op basis van verschillende kenmerken.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 98260371a17ff8a05912cc1bc08c67fbe9755727
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171130"
---
# <a name="create-simple-segments-with-quick-segments"></a>Eenvoudige segmenten met snelle segmenten maken

Met snelle segmenten kunt u snel eenvoudige segmenten bouwen met één operator voor snellere inzichten. Snelle segmenten worden alleen ondersteund in omgevingen voor **individuele klanten**.

## <a name="create-a-new-segment-with-quick-segments"></a>Een nieuw segment met snelle segmenten maken

1. Ga naar **Segmenten**.

1. Selecteer **Nieuw** > **Geheel nieuw maken**.
   - Selecteer de optie **Profielen** om een segment te bouwen dat is gebaseerd op de entiteit *geharmoniseerde klant*.
   - Selecteer de optie **Meetcriteria** om een segment te bouwen rond meetcriteria die u eerder hebt gemaakt.
   - Selecteer de optie **Intelligentie** om een segment op te bouwen rond een van de uitvoerentiteiten die u hebt gegenereerd met behulp van de mogelijkheden **Voorspellingen** of **Aangepaste modellen**.

1. Selecteer in het dialoogvenster **Nieuw snel segment** een kenmerk uit de vervolgkeuzelijst **Veld**. Op basis van uw selectie biedt het systeem verschillende waarden.
   - Voor categorievelden worden de tien topaantallen van klanten weergegeven. Kies een **Waarde** en selecteer **Evalueren**.
   - Voor een numeriek kenmerk laat het systeem zien welke kenmerkwaarde onder het percentiel van elke klant valt. Kies een **Operator** en een **Waarde** en selecteer vervolgens **Evalueren**.

1. Er wordt een **Geschatte segmentgrootte** gegeven. Geef aan of u het door u gedefinieerde segment wilt genereren of ga terug om een ander veld te kiezen.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Naam en schatting voor een snel segment.":::

1. Geef een waarde voor **Naam** en **Naam van uitvoerentiteit** op voor uw segment. Voeg optioneel [tags](work-with-tags-columns.md#manage-tags) toe.

1. Selecteer **Opslaan** om uw segment te maken. De pagina **Segmenten** wordt weergegeven.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-steps"></a>Volgende stappen

[Exporteer een segment](export-destinations.md) en verken de [Klantenkaartintegratie](customer-card-add-in.md) om segmenten in andere toepassingen te gebruiken.

[!INCLUDE [footer-include](includes/footer-banner.md)]
