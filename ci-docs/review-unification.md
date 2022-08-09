---
title: Gegevensharmonisatie bekijken
description: Bekijk de stappen voor gegevensharmonisatie, maak geharmoniseerde klantprofielen en bekijk de resultaten
ms.date: 06/02/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 20728ffaef9bb705410b3ac22d19868ffd5d1243
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139571"
---
# <a name="review-data-unification"></a>Gegevensharmonisatie bekijken

Deze laatste stap in het harmonisatieproces toont een samenvatting van de stappen in het proces en biedt de mogelijkheid om wijzigingen aan te brengen voordat u het geharmoniseerde profiel maakt.

:::image type="content" source="media/m3_review.png" alt-text="Schermopname van klantprofielen beoordelen en maken":::

## <a name="review-the-data-unification-steps"></a>De stappen voor gegevensharmonisatie bekijken

1. Selecteer **Bewerken** in een van de stappen voor gegevensharmonisatie om te controleren en eventuele wijzigingen aan te brengen.

1. Als u tevreden bent met uw selecties, selecteert u **Klantprofielen maken**. Op de pagina **Harmoniseren** wordt weergegeven terwijl het geharmoniseerde klantprofiel wordt gemaakt. Alle tegels behalve **Bronvelden** tonen de status **In wachtrij** of **Vernieuwen**.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Schermopname van Unify-pagina met tegels met de status In wachtrij of Vernieuwen.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Het harmonisatie-algoritme duurt enige tijd om te voltooien en u kunt de configuratie niet wijzigen totdat het is voltooid. Wanneer het harmonisatieproces is voltooid, wordt de geharmoniseerde-klantprofielentiteit, genaamd *Customer*, vermeld op de pagina **Entiteiten** in de sectie **Profielen**. De eerste succesvolle harmonisatie-uitvoering creëert de geharmoniseerde *Customer*-entiteit. Alle volgende uitvoeringen breiden die entiteit uit.

## <a name="review-the-results-of-data-unification"></a>De resultaten van gegevensharmonisatie bekijken

Na de harmonisatie, toont de pagina **Gegevens** > **Harmoniseren** het aantal geharmoniseerde klantprofielen. De resultaten van elke stap in het unificatieproces worden op elke tegel weergegeven. Bijvoorbeeld, **Bronvelden** toont het aantal toegewezen kenmerken (velden) en **Dubbele records** toont het aantal gevonden dubbele records.

:::image type="content" source="media/m3_unified.png" alt-text="Schermopname van de pagina Gegevens harmoniseren nadat de gegevens zijn geharmoniseerd.":::

> [!TIP]
> De tegel **Overeenkomende voorwaarden** wordt alleen weergegeven als er meerdere entiteiten zijn geselecteerd.

We raden u aan de resultaten te bekijken, met name de kwaliteit van uw [regels voor overeenkomsten](data-unification-update.md#manage-match-rules) en verfijn ze indien nodig.

Wanneer nodig [brengt u wijzigingen aan in de harmonisatie-instellingen](data-unification-update.md) en vervolgens voert u het geharmoniseerde profiel opnieuw uit.

## <a name="next-step"></a>Volgende stap

Configureer [activiteiten](activities.md), [verrijking](enrichment-hub.md), [relaties](relationships.md), of [meetcriteria](measures.md) om meer inzicht te krijgen in uw klanten.

[!INCLUDE[footer-include](includes/footer-banner.md)]
