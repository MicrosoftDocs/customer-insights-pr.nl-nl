---
title: Overzicht van metingen
description: Ontdek hoe metingen helpen bij het analyseren en weergeven van de prestaties van uw bedrijf.
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: 99368a7ab2e8d7b3e53c04fbf25bb23bd2e550a9
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245367"
---
# <a name="measures-overview"></a>Overzicht van metingen

Meetcriteria helpen u het klantgedrag en de bedrijfsprestaties beter te begrijpen. Ze kijken naar relevante waarden uit [geharmoniseerde profielen](data-unification.md). Een bedrijf wil bijvoorbeeld de *totale uitgaven per klant* bekijken om de aankoopgeschiedenis van een individuele klant te begrijpen of de *totale omzet van het bedrijf* meten om inzicht te krijgen in de omzet op geaggregeerd niveau in het hele bedrijf.

Maak metingen om bedrijfsactiviteiten te plannen door klantgegevens op te vragen en inzichten te verkrijgen. Maak bijvoorbeeld een meting van *totale uitgaven per klant* en *totaal rendement per klant* om zo een groep klanten te identificeren met hoge uitgaven en toch een hoog rendement. Vervolgens [maakt u een segment](segments.md) op basis van deze metingen om de volgende beste acties uit te voeren.

## <a name="create-a-measure"></a>Een meetcriterium maken

Kies hoe een meting moet worden gemaakt op basis van uw doelgroep.

# <a name="individual-consumers-b-to-c"></a>[Individuele consumenten (B-to-C)](#tab/b2c)

- Geheel nieuwe metingen maken: [Uw eigen metingen bouwen](measure-builder.md).
- Metingen maken op basis van veelgebruikte metingen: [Vooraf gedefinieerde sjablonen gebruiken](measure-templates.md).

# <a name="business-accounts-b-to-b"></a>[Zakelijke accounts (B-to-B)](#tab/b2b)

Geheel nieuwe metingen maken: [Uw eigen metingen bouwen](measure-builder.md).

---

## <a name="manage-existing-measures"></a>Bestaande metingen beheren

Ga naar de pagina **Metingen** om de door u gemaakte metingen te bekijken, de status en type van de meting en de laatste keer dat de gegevens zijn vernieuwd. U kunt de lijst met metingen sorteren op elke kolom of het zoekvak gebruiken om de meting te vinden die u wilt beheren.

Selecteer de meting om beschikbare acties te bekijken. Selecteer de naam van de meting om een voorbeeld van de uitvoer bekijken en een CSV-bestand te downloaden.

:::image type="content" source="media/measures-actions.png" alt-text="Acties om afzonderlijke meetcriteria te beheren."lightbox="media/measures-actions.png":::

- **Bewerk** de meting om de eigenschappen te wijzigen.
- **Vernieuw** de meting om de nieuwste gegevens op te nemen.
- **Hernoem** het meetcriterium.
- **Activeer** of **deactiveer** de meting. Inactieve metingen worden niet vernieuwd gedurende een [geplande vernieuwing](schedule-refresh.md) en hebben de **Status** **Overgeslagen**, wat aangeeft dat er niet eens is geprobeerd te vernieuwen.
- **Tag** om [tags te beheren](work-with-tags-columns.md#manage-tags) voor de meting.
- **Verwijder** het meetcriterium.
- **Kolommen** om de [kolommen aan te passen](work-with-tags-columns.md#customize-columns) die worden weergegeven.
- **Filter** om te [filteren op tags](work-with-tags-columns.md#filter-on-tags).
- Selecteer **Naam zoeken** om op metingnaam te zoeken.

## <a name="refresh-measures"></a>Metingen vernieuwen

Metingen kunnen volgens een automatische planning worden vernieuwd of kunnen op aanvraag handmatig worden vernieuwd. Als u een of meer metingen handmatig wilt vernieuwen, selecteert u ze en kiest u **Vernieuwen**. Om [een automatische vernieuwing te plannen](schedule-refresh.md), gaat u naar **Beheerder** > **Systeem** > **Planning**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
