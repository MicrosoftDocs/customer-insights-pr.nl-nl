---
title: Teams-bot voor Dynamics 365 Customer Insights (preview)
description: Zoek geharmoniseerde klantprofielen op in Microsoft Teams met behulp van een bot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195836"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Teams-bot voor Dynamics 365 Customer Insights (preview)

Maak verbinding met Microsoft Teams om een bot geharmoniseerde klantprofielen in Teams-kanalen te laten opzoeken.

:::image type="content" source="media/teams-bot.png" alt-text="Teams-bot die een klantrecord weergeeft":::

## <a name="prerequisites"></a>Vereisten

- Minimaal één [gegevensbron toegevoegd](data-sources.md).
- Het [harmoniseringsproces](data-unification.md) is voltooid.
- Velden toegevoegd aan de [zoek- en filterindex](search-filter-index.md).
- Customer Insights en Teams bevinden zich in dezelfde organisatie.
- Uw omgeving heeft de primaire doelgroep ingesteld op individuele klanten. Zakelijke accounts worden niet ondersteund.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>De bot configureren

1. Ga naar **Beheerder** > **Verbindingen**.
1. Selecteer op de tegel Microsoft Teams de optie **Instellen**.
1. U wordt doorgestuurd naar het gebied **Apps** in Teams. U kunt Teams ook openen en **Apps** selecteren in de linkerbenedenhoek of dit rechtstreeks [ophalen vanuit AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).
1. Zoek naar **Customer Insights** en selecteer de app.
1. Selecteer **Toevoegen**.
1. Meld u aan bij Customer Insights in Teams. Een welkomstbericht wordt weergegeven.

## <a name="things-you-can-do-with-the-bot"></a>Dingen die u kunt doen met de bot

De bot biedt zoekmogelijkheden voor geharmoniseerde klantprofielen.

- Voer **zoeken** in gevolgd door een naam, e-mailadres of ander veld in het geharmoniseerde klantprofiel dat is toegevoegd aan de zoek- en filterindex.

  U krijgt een kaart met maximaal 15 velden uit het resulterende klantprofiel. Meerdere overeenkomsten retourneren een lijst met resultaten waarin u een profiel kunt selecteren. U kunt de zoekterm tussen dubbele aanhalingstekens plaatsen om een exacte overeenkomst op te zoeken.

- Als uw organisatie meerdere Customer Insights-omgevingen in dezelfde organisatie heeft, voert u **switchinstance** in om te kiezen met welke omgeving u de bot wilt verbinden.

- VOer **help** in om een lijst met beschikbare opdrachten voor de bot te bekijken.  

[!INCLUDE [footer-include](includes/footer-banner.md)]