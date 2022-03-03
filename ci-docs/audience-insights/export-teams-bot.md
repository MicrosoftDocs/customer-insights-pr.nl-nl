---
title: Bot voor Microsoft Teams
description: Zoek geharmoniseerde klantprofielen op in Microsoft Teams met behulp van een bot.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d6b016c1ec35e26ce6449333234edfd218bc9354
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232096"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Teams-bot voor Dynamics 365 Customer Insights (preview)

Maak verbinding met Microsoft Teams om een bot geharmoniseerde klantprofielen in Teams-kanalen te laten opzoeken.

> [!div class="mx-imgBorder"]
> ![Teams-bot die een klantrecord weergeeft.](media/teams-bot.png "Teams-bot die een klantrecord weergeeft")

## <a name="prerequisites"></a>Vereisten

Als u de bot wilt instellen en configureren, moet aan de volgende voorwaarden worden voldaan:

- Er is minimaal één [gegevensbron toegevoegd](data-sources.md).
- Het [harmoniseringsproces](data-unification.md) is voltooid.
- Er zijn velden toegevoegd aan de [zoek- en filterindex](search-filter-index.md).
- Customer Insights en Teams bevinden zich in dezelfde organisatie.
- Uw omgeving heeft de primaire doelgroep ingesteld op individuele klanten. Zakelijke accounts worden niet ondersteund.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]
## <a name="configure-the-bot"></a>De bot configureren

1. Ga in doelgroepinzichten naar **Beheer** > **Exportbestemmingen**.
1. Selecteer op de tegel Microsoft Teams de optie **Instellen**.
1. U wordt doorgestuurd naar het gebied **Apps** in Teams. U kunt Teams ook openen en **Apps** selecteren in de linkerbenedenhoek of dit rechtstreeks [ophalen vanuit AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).
1. Zoek naar **Customer Insights** en selecteer de app.
1. Selecteer **Toevoegen**.
1. Nadat u zich hebt aangemeld bij Customer Insights in Teams, ziet u een welkomstbericht en kunt u aan de slag.

## <a name="things-you-can-do-with-the-bot"></a>Dingen die u kunt doen met de bot

De bot biedt zoekmogelijkheden voor geharmoniseerde klantprofielen.

- Voer **zoeken** in gevolgd door een naam, e-mailadres of ander veld in het geharmoniseerde klantprofiel dat is toegevoegd aan de zoek- en filterindex.

  U krijgt een kaart met maximaal 15 velden uit het resulterende klantprofiel. Meerdere overeenkomsten retourneren een lijst met resultaten waarin u een profiel kunt selecteren. U kunt de zoekterm tussen dubbele aanhalingstekens plaatsen om een exacte overeenkomst op te zoeken.

- Als uw organisatie meerdere Customer Insights-omgevingen in dezelfde organisatie heeft, kunt u **switchinstance** invoeren om te kiezen met welke omgeving u de bot wilt verbinden.

- VOer **help** in om een lijst met beschikbare opdrachten voor de bot te bekijken.  


[!INCLUDE[footer-include](../includes/footer-banner.md)]