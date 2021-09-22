---
title: Code toevoegen aan uw website
description: Procedure om een codefragment toe te voegen om gebeurtenissen op uw website vast te leggen.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b5467da775a621c436bd9ddedb272506acc1e2b31dcf7c87feb5dd11e2daae2b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035088"
---
# <a name="install-the-code-snippet-on-a-website"></a>Het codefragment op een website installeren

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dit artikel beschrijft hoe een beheerder het codefragment op een website installeert. Kort nadat u het script aan uw website hebt toegevoegd, ziet u gebeurtenissen in uw werkruimte verschijnen. Zie [Werkruimten en omgeving beheren](manage-environments-workspaces.md) voor meer informatie. Zie [Overzicht van resources voor ontwikkelaars](developer-resources.md) voor het vastleggen van gebeurtenissen in mobiele apps.


### <a name="prerequisites"></a>Vereisten

* U moet beheerdersmachtigingen voor de werkruimte hebben om de gegevens op te slaan.
* Uw website of project moet online worden gehost om activiteitsgegevens te verzenden. Gegevens die vanuit een lokaal bestand worden verzonden, worden niet door de server geaccepteerd.


## <a name="add-code-to-your-website"></a>Code toevoegen aan uw website
1.  Ga naar **Beheer** > **Werkruimte** en selecteer **Installatiegids**.
1. Selecteer **Code kopiëren** om het codefragment te kopiëren. Standaard is de opnamesleutel voor uw werkruimte ingesloten in het codefragment.
:::image type="content" source="media/copy-code.png" alt-text="Schermafbeelding van de codefragmentpagina.":::
3. Voeg het gekopieerde codefragment toe aan uw website, in de buurt van de <head> tag en vóór elk ander script of CSS-tags.
4.  Publiceer uw bijgewerkte website en wacht een paar minuten om het inkomende webverkeer vast te leggen.
5.  Om uw gegevens te zien, selecteert u uw werkruimte met de werkruimteschakelaar in het navigatiedeelvenster. Selecteer vervolgens een van de rapporten in de sectie **Ontdekken**.

## <a name="configuration-options"></a>Configuratieopties

U kunt de volgende configuratieopties wijzigen in het codefragment:

- **ingestionKey**: de verwerkingssleutel die wordt gebruikt om gebeurtenissen naar uw werkruimte te verzenden. U kunt de opnamesleutel wijzigen om gebeurtenissen naar een andere werkruimte te verzenden. Een opnamesleutel is uniek voor elke werkruimte. 
- **autoCapture**: geeft aan of paginaweergaven en interacties met de website worden vastgelegd. Er zijn twee opties:
    - **view**: ingesteld op *waar* om paginaweergaven vast te leggen. Paginaweergaven worden vastgelegd als *Weergave* [gebeurtenissen](glossary.md#event), een type [basisgebeurtenis](glossary.md#base-event).
    - **click**: ingesteld op *waar* om bezoekersinteracties op de website vast te leggen. Interacties worden vastgelegd als *Actie* [gebeurtenissen](glossary.md#event), een type [basisgebeurtenis](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
