---
title: Gebeurtenissen maken en wijzigen
description: Gebeurtenissen maken en wijzigen.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 935dc4cd41218842e8406b747daef47de04e337a
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606196"
---
# <a name="create-and-modify-events"></a>Gebeurtenissen maken en wijzigen

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Een gebeurtenis bestaat uit gegevens die het gebruikersgedrag weergeven, zoals activiteit op een website.

- Een *basis* gebeurtenis registreert wanneer een gebruiker een pagina bekijkt (weergavegebeurtenis) of interactie heeft met inhoud (actiegebeurtenis).
- Een *verfijnde* gebeurtenis is een virtuele weergave van een basisgebeurtenis. U definieert verfijnde gebeurtenissen door eigenschappen te verwijderen en toe te voegen of door gebeurtenissen te filteren op basis van eigenschapwaarden.

## <a name="prerequisites"></a>Vereisten

Als u gebeurtenissen wilt bekijken, moeten de websitegegevens eerst worden verbonden met betrokkenheidsinzichten met een codefragment. Voor meer informatie, zie [Installeer de web-SDK op een website](instrument-website.md).

 :::image type="content" source="media/new-events-connect-data.png" alt-text="Verbind eerst uw gegevens.":::

## <a name="create-refined-events"></a>Verfijnde gebeurtenissen maken

Gebruik verfijnde gebeurtenissen om de reikwijdte van een basisgebeurtenis voor [exporteren](export-events.md) te verkleinen of om eigenschappen te verwijderen die niet nodig zijn voor blootstelling.

> [!NOTE]
> Nadat u de web-SDK aan uw website heeft toegevoegd, kunt u uw basisgebeurtenissen bekijken en verfijnde gebeurtenissen maken. 

Uw basisgebeurtenissen bekijken:

1. Ga naar **Gegevens** in het linkernavigatievenster.

1. Selecteer **Gebeurtenissen** om een lijst met alle gebeurtenissen in de werkruimte te zien.

    :::image type="content" source="media/data-events.png" alt-text="Bekijk gebeurtenissen.":::

Een verfijnde gebeurtenis maken op basis van een basisgebeurtenis: 

1. Ga naar **Gegevens** > **Gebeurtenissen** en selecteer **+ Nieuwe gebeurtenissen** boven in het scherm.

1. In het dialoogvenster **Nieuwe gebeurtenissen** selecteer **Verfijnde gebeurtenissen maken** en selecteer vervolgens **Volgende**.
   
     :::image type="content" source="media/new-events-wizard.png" alt-text="Wizard Nieuwe gebeurtenissen.":::
     
1. Voer in het dialoogvenster **Nieuwe gebeurtenissen** de volgende informatie in:

   - Selecteer een gebeurtenis in de keuzelijst **Basisgebeurtenissen**.
   - Voer een naam in het vak **Weergavenaam verfijnde gebeurtenissen** in.
   - Werk eventueel de voorgestelde **Werkelijke naam** bij zonder spaties te gebruiken.

1. Selecteer **Maken** om uw instellingen toe te passen.

De verfijnde gebeurtenis verschijnt nu in de lijst **Gebeurtenissen**.

### <a name="edit-event-name"></a>Gebeurtenisnaam bewerken

U kunt de naam en de eigenschappen van een basis- of verfijnde gebeurtenis wijzigen.

1. Ga naar **Gegevens** > **Gebeurtenissen**. 

1. Selecteer **Meer [...]** voor een gebeurtenis en selecteer **Naam bewerken**.
    
     :::image type="content" source="media/create-refined-events-options.png" alt-text="Opties om verfijnde gebeurtenissen te maken.":::

3. Werk de naam van de gebeurtenis bij en selecteer **Naam wijzigen**.

### <a name="view-the-details-of-a-refined-event"></a>De details van een verfijnde gebeurtenis bekijken:

1. Selecteer in de lijst **Gebeurtenis** de basis- of verfijnde gebeurtenis. 

1. Selecteer **Eigenschappen toevoegen en verwijderen** boven aan het scherm om het deelvenster **Eigenschappen bewerken** te openen. 

     :::image type="content" source="media/add-remove-properties.png" alt-text="Eigenschappen toevoegen en verwijderen.":::

1. Gebruik de selectievakjes om de eigenschappen te selecteren die u wilt weergeven of verbergen. 

   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Eigenschappen voor verfijnde gebeurtenissen bewerken.":::

1. Selecteer **Bevestigen** om uw selectie toe te passen en selecteer vervolgens **Opslaan**.


### <a name="edit-selected-properties-for-a-refined-event"></a>Geselecteerde eigenschappen bewerken voor een verfijnde gebeurtenis

1. Ga naar **Gegevens** > **Gebeurtenissen** en selecteer de verfijnde gebeurtenissen om de gedetailleerde weergave te openen.
1. Selecteer **Eigenschappen toevoegen en verwijderen**. 
1. Bewerk de selectie van de selectievakjes.
1. Selecteer **Bevestigen** en daarna **Opslaan** om de wijzigingen toe te passen.

Zie [Gebeurtenissen exporteren](export-events.md) voor informatie over het exporteren van gebeurtenissen.
[!INCLUDE[footer-include](../includes/footer-banner.md)]
