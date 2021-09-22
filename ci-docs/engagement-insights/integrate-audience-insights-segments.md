---
title: Segmenten van doelgroepinzichten gebruiken om rapporten over betrokkenheidsinzichten te filteren
description: Gebruik segmenten van doelgroepinzichten in interactieve analyses van gedragsgegevens die zijn vastgelegd door betrokkenheidsinzichten op de website van een klant.
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: bdd5641bb17384725491f22f70ae967ad90b1696
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461052"
---
# <a name="use-audience-insights-segments-to-filter-engagement-insights-reports"></a>Segmenten van doelgroepinzichten gebruiken om rapporten over betrokkenheidsinzichten te filteren

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Met betrokkenheidsinzichten kunt u segmenten van doelgroepinzichten gebruiken in interactieve analyses van gedragsgegevens die zijn vastgelegd door betrokkenheidsinzichten op uw websites.

## <a name="prerequisite"></a>Vereiste

- Een omgeving voor betrokkenheidsinzichten waarin u gegevens over segmenten van doelgroepinzichten hebt gekoppeld aan de omgeving voor doelgroepinzichten waar de segmenten en klantprofielen worden gemaakt. Meer informatie: [Een koppeling tot stand brengen tussen doelgroepinzichten en betrokkenheidsinzichten](integrate-audience-insights-engagement-insights.md)

## <a name="create-audience-insights-segments"></a>Segmenten van doelgroepinzichten maken 

> [!IMPORTANT]
> Als u segmenten van doelgroepinzichten in betrokkenheidsinzichten wilt laten verschijnen, moet u eerst [samenvoeg- en downstreamprocessen uitvoeren](../audience-insights/merge-entities.md). Downstreamprocessen zijn belangrijk omdat ze een unieke tabel genereren die segmenten van doelgroepinzichten voorbereidt om te worden gedeeld met betrokkenheidsinzichten. (Als een systeemvernieuwing is gepland, omvat deze automatisch downstreamprocessen.)

U kunt segmenten van doelgroepinzichten gebruiken in kant-en-klare rapporten voor betrokkenheidsinzichten of aangepaste rapporten die u hebt gemaakt. Ga naar [Kant-en-klare profielrapporten](profile-reports.md) en [Aangepaste rapporten maken en bewerken](custom-reports.md) voor meer informatie.

**Segmenten van doelgroepinzichten gebruiken in rapporten over betrokkenheidsinzichten**

1. Ga naar uw pagina **Werkruimte**, selecteer **Gegevens** en selecteer vervolgens het tabblad **Segmenten**.

    :::image type="content" source="media/integrate-audience-insights-segments1.png" alt-text="Het tabblad Segmenten selecteren.":::

   >[!NOTE]
   > Als u een segment van doelgroepinzichten selecteert, gaat u naar doelgroepinzichten, waar u kunt zien hoe dat segment is gemaakt in termen van regels en logica. Ga voor meer informatie over segmenten van doelgroepinzichten naar [Segmenten weergeven en maken](../audience-insights/segments.md).

2. Selecteer een kant-en-klaar rapport of [maak een aangepast rapport](custom-reports.md) en selecteer vervolgens **Voorwaarde toevoegen**. (Voor dit voorbeeld hebben we het rapport **Paginaweergaven** gekozen.)

    :::image type="content" source="media/integrate-audience-insights-segments2.png" alt-text="Een voorwaarde toevoegen.":::

3. Selecteer **Filteren op segment**, vouw de lijst **Segmenttype** uit en selecteer vervolgens **Demografisch**.

    :::image type="content" source="media/integrate-audience-insights-segments3.png" alt-text="Selecteer het sgementtype Demografisch.":::

4. Vouw de lijst **Segmentnaam** uit en kies vervolgens een segment van doelgroepinzichten.

    :::image type="content" source="media/integrate-audience-insights-segments4.png" alt-text="Een segment kiezen.":::

5. U kunt een of meer segmenten toepassen, waaronder gedrags- (betrokkenheidsinzichten) en demografische (doelgroepinzichten) segmenten. 

    :::image type="content" source="media/integrate-audience-insights-segments6.png" alt-text="Rapport over paginaweergaven beperkt tot de segmenten Amerikaanse klanten en Startpagina.":::

In de voorgaande afbeelding zijn de segmenten **Amerikaanse klanten** en **Startpagina** geselecteerd, waardoor het rapport **Paginaweergaven** is beperkt tot die twee segmenten. 


>[!NOTE]
> U kunt segmenten van doelgroepinzichten gebruiken om kant-en-klare rapporten, aangepaste rapporten en trechters te filteren in betrokkenheidsinzichten. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]