---
title: Demografische dimensies gebruiken voor het opsplitsen van gedragsgegevens (samengestelde dimensies)
description: Gebruik geharmoniseerde samengestelde profieldimensies om klantprofieleigenschappen voro doelgroepinzichten in te schakelen.
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 95395e09bc0ba5ba93138957c62105f31c709e91
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8233041"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>Demografische dimensies gebruiken voor het opsplitsen van gedragsgegevens

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Door gebruik te maken van geharmoniseerde demografische profieldimensies hebben gebruikers van betrokkenheidsinzichten toegang tot profieleigenschappen van doelgroepeigenschappen. U kunt deze eigenschappen vervolgens gebruiken in interactieve analyses van gedragsgegevens, met inbegrip van gegevens die zijn vastgelegd door betrokkenheidsinzichten op uw website of in uw mobiele app.

>[!NOTE]
> Betrokkenheidsinzichten omvat kant-en-klare dimensies voor gebeurteniseigenschappen. Meer informatie: [Dimensies weergeven en maken](dimensions.md)

## <a name="prerequisite"></a>Vereiste

- Een omgeving voor betrokkenheidsinzichten waarin u klantprofielgegevens hebt gekoppeld aan de omgeving voor doelgroepinzichten waar de klantprofielen worden gemaakt. Meer informatie: [Een koppeling tot stand brengen tussen doelgroepinzichten en betrokkenheidsinzichten](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> Nadat u een koppeling hebt gemaakt tussen de omgeving voor doelgroepinzichten en de omgeving voor betrokkenheidsinzichten, wilt u misschien alleen gegevens die specifiek zijn voor klantprofieleigenschappen, wat handig kan zijn als dimensies in betrokkenheidsinzichten. Ga naar [Geharmoniseerde profielkenmerken en segmenten instellen voor doelgroepinzichten](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments) voor meer informatie.

## <a name="create-a-new-custom-report"></a>Een nieuw aangepast rapport maken

1. Selecteer in het linkerdeelvenster **Aangepast** > **Nieuw rapport** en selecteer vervolgens het gewenste metrische gegeven. (Voor dit voorbeeld hebben we **Paginaweergaven per uur** gekozen.)

    :::image type="content" source="media/curated-dimensions1.png" alt-text="Een metrisch gegeven selecteren.":::

2. Selecteer in de Visualisatie-editor de optie **Dimensies** en selecteer vervolgens **Demografisch** in het vervolgkeuzemenu **Dimensietype**.

    :::image type="content" source="media/curated-dimensions2.png" alt-text="Selecteer Demografisch.":::

3. Selecteer een dimensie **Signaal.Klant.*xxx***. (Dit voorbeeld laat Signaal.Klant.Land zien.)

    :::image type="content" source="media/curated-dimensions3.png" alt-text="Een dimensie selecteren.":::
  
## <a name="limitations"></a>Beperkingen

Momenteel kunt u alleen demografische dimensies gebruiken voor het opsplitsen van gedragsgegevens.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
