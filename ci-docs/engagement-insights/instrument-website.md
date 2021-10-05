---
title: Code toevoegen aan uw website
description: Procedure om een codefragment toe te voegen om Dynamics 365 Customer Insights-gebeurtenissen op uw website vast te leggen.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: ad835f762226d62fdb0f544627f2a76ff09a1ffd
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558787"
---
# <a name="install-the-web-sdk-on-a-website"></a>Installeer de web-SDK op een website

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dit artikel beschrijft hoe een beheerder de software development toolkit (SDK) op een website installeert. Kort nadat u uw website heeft ingericht, ziet u gebeurtenissen in uw werkruimte. Zie [Werkruimten en omgeving beheren](manage-environments-workspaces.md) voor meer informatie. Zie [Overzicht van resources voor ontwikkelaars](developer-resources.md) voor het vastleggen van gebeurtenissen in mobiele apps.


### <a name="prerequisites"></a>Vereisten

* U moet beheerdersmachtigingen voor de werkruimte hebben om de gegevens op te slaan.
* Uw website of project moet online worden gehost om activiteitsgegevens te verzenden. Gegevens die vanuit een lokaal bestand worden verzonden, worden niet door de server geaccepteerd.


## <a name="add-web-sdk-to-your-website"></a>Web-SDK toevoegen aan uw website

Ga naar **Beheer** > **Werkruimte** en selecteer **Installatiegids**. Er zijn twee opties om web-SDK te installeren. De eerste is om een download-koppeling te gebruiken en de tweede is om een knooppunt-pakketbeheer (NPM) te installeren.

### <a name="option-1-using-the-download-link"></a>Optie 1: de downloadkoppeling gebruiken

1. Selecteer **Code kopiëren** om het codefragment te kopiëren. Standaard is de opnamesleutel voor uw werkruimte ingesloten in het codefragment.
  :::image type="content" source="media/copy-code.png" alt-text="Schermafbeelding van de codefragmentpagina.":::

1. Voeg de gekopieerde code toe aan uw website, in de buurt van de <head> tag en vóór elk ander script of CSS-tags.
1. Publiceer uw bijgewerkte website en wacht een paar minuten om het inkomende webverkeer vast te leggen.
1. Om uw gegevens te zien, selecteert u uw werkruimte met de werkruimteschakelaar in het navigatiedeelvenster. Selecteer vervolgens een van de rapporten in de sectie **Ontdekken**.

### <a name="option-2-using-the-npm-package-recommended-for-javascript-based-web-apps"></a>Optie 2: het NPM-pakket gebruiken (aanbevolen voor Web Apps die op JavaScript zijn gebaseerd)

1. Ga naar onze [NPM-webpagina](https://www.npmjs.com/package/engagementinsights-web) en volg de instructies om het web-SDK NPM-pakket te installeren en in te stellen.
1. Publiceer uw bijgewerkte website en wacht een paar minuten om het inkomende webverkeer vast te leggen.
1. Om uw gegevens te zien, selecteert u uw werkruimte met de werkruimteschakelaar in het navigatiedeelvenster. Selecteer vervolgens een van de rapporten in de sectie **Ontdekken**.

## <a name="configuration-options"></a>Configuratieopties

U kunt de volgende configuratieopties wijzigen in het codefragment:

- **ingestionKey**: de verwerkingssleutel die wordt gebruikt om gebeurtenissen naar uw werkruimte te verzenden. U kunt de opnamesleutel wijzigen om gebeurtenissen naar een andere werkruimte te verzenden. Een opnamesleutel is uniek voor elke werkruimte.
- **autoCapture**: geeft aan of paginaweergaven en interacties met de website worden vastgelegd. Er zijn twee opties:
    - **view**: ingesteld op *waar* om paginaweergaven vast te leggen. Paginaweergaven worden vastgelegd als *Weergave* [gebeurtenissen](glossary.md#event), een type [basisgebeurtenis](glossary.md#base-event).
    - **click**: ingesteld op *waar* om bezoekersinteracties op de website vast te leggen. Interacties worden vastgelegd als *Actie* [gebeurtenissen](glossary.md#event), een type [basisgebeurtenis](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
