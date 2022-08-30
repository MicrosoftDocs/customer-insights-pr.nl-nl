---
title: Gegevensharmonisatie bekijken
description: Bekijk de stappen voor gegevensharmonisatie, maak geharmoniseerde klantprofielen en bekijk de resultaten
ms.date: 08/12/2022
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
ms.openlocfilehash: b4d77effc347e40fecde625a1a42a24900456471
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303961"
---
# <a name="review-data-unification"></a>Gegevensharmonisatie bekijken

Bekijk het overzicht van wijzigingen, maak het geharmoniseerde profiel en beoordeel de resultaten.

## <a name="review-and-create-customer-profiles"></a>Klantprofielen beoordelen en maken

Deze laatste stap in het harmonisatieproces toont een samenvatting van de stappen in het proces en biedt de mogelijkheid om wijzigingen aan te brengen voordat u het geharmoniseerde profiel maakt.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

:::image type="content" source="media/m3_review.png" alt-text="Schermopname van het beoordelen en maken van klantprofielen":::

1. Selecteer **Bewerken** in een van de stappen voor gegevensharmonisatie om te controleren en eventuele wijzigingen aan te brengen.

1. Als u tevreden bent met uw selecties, selecteert u **Klantprofielen maken** (of **Accountprofielen maken** voor B2B). Op de pagina **Harmoniseren** wordt weergegeven terwijl het geharmoniseerde klantprofiel wordt gemaakt.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Schermopname van Unify-pagina met tegels met de status In wachtrij of Vernieuwen.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Het harmonisatie-algoritme duurt enige tijd om te voltooien en u kunt de configuratie niet wijzigen totdat het is voltooid.

## <a name="view-the-results-of-data-unification"></a>De resultaten van gegevensharmonisatie bekijken

Na de harmonisatie wordt op de pagina **Gegevens** > **Harmoniseren** het aantal geharmoniseerde klantprofielen (of accountprofielen voor B2B) weergegeven. De resultaten van elke stap in het unificatieproces worden op elke tegel weergegeven. Bijvoorbeeld, **Bronvelden** toont het aantal toegewezen kenmerken (velden) en **Dubbele records** toont het aantal gevonden dubbele records.

:::image type="content" source="media/m3_unified.png" alt-text="Schermopname van de pagina Gegevens harmoniseren nadat de gegevens zijn geharmoniseerd.":::

> [!TIP]
> De tegel **Overeenkomende voorwaarden** wordt alleen weergegeven als er meerdere entiteiten zijn geselecteerd.

We raden u aan de resultaten te bekijken, met name de kwaliteit van uw [regels voor overeenkomsten](data-unification-update.md#manage-match-rules) en verfijn ze indien nodig.

Wanneer nodig [brengt u wijzigingen aan in de harmonisatie-instellingen](data-unification-update.md) en vervolgens voert u het geharmoniseerde profiel opnieuw uit.

### <a name="verify-output-entities-from-data-unification"></a>Uitvoerentiteiten van gegevensharmonisatie verifiëren

Ga naar **Gegevens** > **Entiteiten** om de uitvoerentiteiten te verifiëren.

De geharmoniseerde klantprofielentiteit met de naam *Customer* wordt weergegeven in de sectie **Profielen**. De eerste succesvolle harmonisatie-uitvoering creëert de geharmoniseerde *Customer*-entiteit. Alle volgende uitvoeringen breiden die entiteit uit.

Ontdubbelings- en samenvoegingsentiteiten worden gemaakt en weergegeven in de sectie **Systeem**. Er wordt een ontdubbelingsentiteit gemaakt voor elk van de bronentiteiten met de naam **Deduplication_DataSource_Entity**. De entiteit **ConflationMatchPairs** bevat informatie over overeenkomsten tussen entiteiten.

Een entiteit voor ontdubbelingsuitvoer bevat de volgende informatie:
- Id's/sleutels
  - Velden Primaire sleutel en Alternatieve id. Het veld Alternatieve id bestaat uit alle alternatieve id's die voor een record zijn geïdentificeerd.
  - Het veld Deduplication_GroupId toont de groep of cluster die is geïdentificeerd binnen een entiteit die alle vergelijkbare records groepeert op basis van de opgegeven ontdubbelingsvelden. Dit wordt gebruikt voor systeemverwerkingsdoeleinden. Als er geen handmatige ontdubbelingsregels zijn opgegeven en door het systeem gedefinieerde ontdubbelingsregels van toepassing zijn, is het mogelijk dat u dit veld niet in de uitvoerentiteit voor ontdubbeling vindt.
  - Deduplication_WinnerId: dit veld bevat de winnende id van de geïdentificeerde groepen of clusters. Als de Deduplication_WinnerId hetzelfde is als de primaire sleutelwaarde voor een record, betekent dit dat de record de winnende record is.
- Velden die worden gebruikt om de ontdubbelingsregels te definiëren.
- Regel- en scorevelden om aan te geven welke van de ontdubbelingsregels zijn toegepast en welke score is geretourneerd door het matching-algoritme.

## <a name="next-step"></a>Volgende stap

- Voer desgewenst [harmonisatie van contactpersonen](data-unification-contacts.md) uit voor B2B.

- Configureer [activiteiten](activities.md), [verrijkingen](enrichment-hub.md), [relaties](relationships.md) of [meetcriteria](measures.md) voor B2B om meer inzicht te krijgen in uw klanten.

[!INCLUDE[footer-include](includes/footer-banner.md)]
