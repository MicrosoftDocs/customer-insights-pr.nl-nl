---
title: Metrische gegevens weergeven en maken
description: Procedure voor het maken, bewerken en verwijderen van metrische gegevens.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 97189168e0f5586aad8be8089a1f9e27893c2115c7e805ddaab1efc00e11b860
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034263"
---
# <a name="view-and-create-metrics"></a>Metrische gegevens weergeven en maken

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Metrische gegevens helpen het gedrag van uw bezoekers te begrijpen. Zij aggregeren gebeurteniseigenschappen en meten statistieken en prestaties van uw webeigenschappen.  

Stel dat u een marketingactie op uw website uitvoert. U kunt metrische gegevens gebruiken om het aantal unieke bezoekers of gebruikers bij te houden dat tijdens de promotie naar uw website is gekomen. Door metrische gegevens te analyseren, krijgt u een beter inzicht in de doelgroep van uw website. Door metrische gegevens te combineren met [dimensies](dimensions.md) in een [aangepast rapport](custom-reports.md) kunt u gedrag meten om uw gebruikers te begrijpen. U kunt bezoekers bijvoorbeeld opsplitsen in nieuwe en terugkerende categorieën om de verschillen in interesse en intentie tussen de groepen te identificeren.

## <a name="view-metrics"></a>Metrische gegevens bekijken

Betrokkenheidsinzichten omvat veelgebruikte aggregaties van gebeurteniseigenschappen als metrische gegevens van het systeem: 

- Bezoekers
- Bezoeken
- Paginaweergaven
- Klikken

Deze metrische gegevens van het systeem zijn gebaseerd op bestaande gebeurteniseigenschappen in basisgebeurtenissen.

1. Ga naar **Gegevens** in het linkernavigatievenster. 
1. Selecteer het tabblad **Metrische gegevens** om een lijst met alle metrische gegevens in de werkruimte te zien. 
   > [!NOTE]
   > Door het systeem gegenereerde metrische gegevens zijn alleen-lezen. U kunt ze niet wijzigen of verwijderen. U kunt alleen aangepaste metrische gegevens maken en bewerken.

## <a name="create-a-metric"></a>Een metrisch gegeven maken

Beheerders van omgevingen en werkruimten kunnen metrische gegevens maken. Gebeurteniseigenschappen moeten naar de werkruimte worden verzonden voordat u een metrisch gegeven maakt. U kunt metrische gegevens maken op basis van gebeurteniseigenschappen die worden verzonden door basisgebeurtenissen of die de web-SDK gebruiken om [aangepaste gebeurteniseigenschappen te verzenden](advanced-SDK-implementation.md).

1. Ga naar **Gegevens** > **Metrische gegevens**.
1. Selecteer **Nieuw metrisch gegeven**.

   :::image type="content" source="media/new-metric.png" alt-text="Een metrisch gegeven toevoegen aan een gebeurtenis.":::

1. Selecteer voor indeling het gegevenstype **Integer** of **Double**. Integer is een geheel getal. Voor Double kunt u kiezen tussen één tot drie decimalen.
1. Zoek in het deelvenster **Resourcebibliotheek** de gebeurteniseigenschap waarop u het metrische gegeven wilt baseren.
1. Selecteer het **plusteken (+)** naast de eigenschap om deze in de formule te gebruiken. U kunt slechts een formule maken op basis van één eigenschap. 
1. Kies een van de volgende statistische functies. 

   - Som: het rekenkundig totaal van alle waarden 
   - Gemiddelde: het gemiddelde van alle waarden
   - Aantal: het totale aantal waarden
   - Uniek aantal: het totale aantal unieke waarden

   Nadat u het metrische gegeven hebt gedefinieerd, ziet u een activiteitsvoorbeeld van het metrische gegeven voor het afgelopen uur.

1. Selecteer **Opslaan**. 
1. Voer een naam in voor het metrische gegeven en selecteer **Opslaan**.

Het kan tot een minuut duren voordat u het metrische statistiek kunt gebruiken om [aangepaste rapporten te maken](custom-reports.md).

## <a name="edit-a-metric"></a>Een metrisch gegeven bewerken

1. Ga naar **Gegevens** > **Metrische gegevens**.
1. Selecteer het metrische gegeven in de lijst.
1. De definitie van het metrische gegeven wijzigen
1. Selecteer **Opslaan**.

## <a name="change-the-name-of-a-metric"></a>De naam van een metrisch gegeven wijzigen

1. Ga naar **Gegevens** > **Metrische gegevens**.
1. Selecteer **Meer [...]** voor een metrisch gegeven en kies vervolgens **Naam bewerken**.
1. Wijzig de naam. 
1. Selecteer **Naam wijzigen**.

## <a name="delete-a-metric"></a>Een metrisch gegeven verwijderen

1. Ga naar **Gegevens** > **Metrische gegevens**.
1. Selecteer **Meer [...]** voor een metrisch gegeven en kies vervolgens **Verwijderen**.

   :::image type="content" source="media/delete-metric.png" alt-text="Een metrisch gegeven verwijderen uit een gebeurtenis.":::

1. Selecteer **Verwijderen** om het verwijderen te bevestigen.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
