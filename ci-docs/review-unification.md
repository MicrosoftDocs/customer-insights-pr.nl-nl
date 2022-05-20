---
title: Gegevensharmonisatie bekijken
description: Bekijk de stappen voor gegevensharmonisatie, maak geharmoniseerde klantprofielen en bekijk de resultaten
ms.date: 05/04/2022
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
ms.openlocfilehash: 4c709dfb55bf079dd2fe99e41adb4c77c2bece4b
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741659"
---
# <a name="review-data-unification"></a>Gegevensharmonisatie bekijken

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Deze laatste stap in het harmonisatieproces toont een samenvatting van de stappen in het proces en biedt de mogelijkheid om wijzigingen aan te brengen voordat u het geharmoniseerde profiel maakt.

:::image type="content" source="media/m3_review.png" alt-text="Schermopname van klantprofielen beoordelen en maken":::

## <a name="review-the-data-unification-steps"></a>De stappen voor gegevensharmonisatie bekijken

1. Selecteer **Bewerken** in een van de stappen voor gegevensharmonisatie om te controleren en eventuele wijzigingen aan te brengen.

1. Als u tevreden bent met uw selecties, selecteert u **Klantprofielen maken**. Op de pagina **Harmoniseren** wordt weergegeven terwijl het geharmoniseerde klantprofiel wordt gemaakt. Het harmonisatie-algoritme duurt enige tijd om te voltooien en u kunt de configuratie niet wijzigen totdat het is voltooid.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]

Wanneer het harmonisatieproces is voltooid, wordt de geharmoniseerde-klantprofielentiteit, genaamd *Customer*, vermeld op de pagina **Entiteiten** in de sectie **Profielen**. De eerste succesvolle harmonisatie-uitvoering creëert de geharmoniseerde *Customer*-entiteit. Alle volgende uitvoeringen breiden die entiteit uit.

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
