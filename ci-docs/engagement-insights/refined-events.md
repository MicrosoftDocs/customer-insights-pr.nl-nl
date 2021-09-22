---
title: Verfijnde gebeurtenissen maken en wijzigen
description: Procedure om verfijnde gebeurtenissen te maken en te wijzigen.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 0344bac5f4d43df853309f43c94d95f962937f77c936ed7305c5de4a08835f04
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034768"
---
# <a name="create-and-modify-refined-events"></a>Verfijnde gebeurtenissen maken en wijzigen

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]


Een gebeurtenis bestaat uit gegevens die het gebruikersgedrag weergeven, zoals activiteit op een website.

- Een *basis* gebeurtenis registreert wanneer een gebruiker een pagina bekijkt (weergavegebeurtenis) of interactie heeft met inhoud (actiegebeurtenis).
- Een *verfijnde* gebeurtenis is een virtuele weergave van een basisgebeurtenis. U definieert verfijnde gebeurtenissen door eigenschappen te verwijderen en toe te voegen of door gebeurtenissen te filteren op basis van eigenschapwaarden.

Gebruik verfijnde gebeurtenissen om de reikwijdte van een basisgebeurtenis voor [exporteren](export-events.md) te verkleinen of om eigenschappen te verwijderen die niet nodig zijn voor blootstelling.

## <a name="create-refined-events"></a>Verfijnde gebeurtenissen maken

Er zijn drie manieren om een verfijnde gebeurtenis te maken op basis van een basisgebeurtenis. 

1. Ga naar **Gegevens**> **Gebeurtenissen** en kies een van de volgende opties:
    - Selecteer **Nieuwe gebeurtenissen** en selecteer **Verfijnde gebeurtenissen maken**.
    - Selecteer een basisgebeurtenis om een gedetailleerde weergave te openen en selecteer **Verfijnde gebeurtenissen maken** in het bovenste menu.
    - Selecteer **Meer [...]** om het snelmenu voor een basisgebeurtenis te openen. Selecteer vervolgens **Verfijnde gebeurtenissen maken**.
    
    :::image type="content" source="media/create-refined-events-options.png" alt-text="Opties om verfijnde gebeurtenissen te maken.":::

1. Voer in het dialoogvenster **Verfijnde gebeurtenissen maken** de volgende informatie in:

- Selecteer een gebeurtenis in de vervolgkeuzelijst **Basisgebeurtenissen** als u een nieuwe gebeurtenis maakt.
- Voer een naam in het vak **Weergavenaam verfijnde gebeurtenissen** in.
- Werk eventueel de voorgestelde **Werkelijke naam** bij zonder spaties te gebruiken.

3. Selecteer **Maken** om uw instellingen toe te passen.

1. Selecteer in de gedetailleerde weergave van uw verfijnde evenement **Eigenschappen toevoegen en verwijderen** om het deelvenster **Eigenschappen bewerken** te openen. 

1. Gebruik de selectievakjes om de eigenschappen te selecteren die u wilt weergeven of verbergen. 
   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Eigenschappen voor verfijnde gebeurtenissen bewerken.":::

1. Selecteer **Bevestigen** om uw selectie toe te passen.

1. Selecteer **Opslaan** om de configuratie op te slaan.

## <a name="edit-refined-events"></a>Verfijnde gebeurtenissen bewerken

U kunt de naam en de eigenschappen van een verfijnde gebeurtenis wijzigen.

### <a name="edit-event-name"></a>Gebeurtenisnaam bewerken

1. Ga naar **Gegevens** > **Gebeurtenissen**. 
1. Selecteer **Meer [...]** voor een gebeurtenis en selecteer **Naam bewerken**.
1. Werk de naam van de gebeurtenis bij en selecteer **Naam wijzigen**.

### <a name="edit-selected-properties"></a>Geselecteerde eigenschappen bewerken

1. Ga naar **Gegevens** > **Gebeurtenissen** en selecteer de verfijnde gebeurtenissen om de gedetailleerde weergave te openen.
1. Selecteer **Eigenschappen toevoegen en verwijderen**. 
1. Bewerk de selectie van de selectievakjes.
1. Selecteer **Bevestigen** en daarna **Opslaan** om de wijzigingen toe te passen.

Zie [Gebeurtenissen exporteren](export-events.md) voor informatie over het exporteren van gebeurtenissen.
[!INCLUDE[footer-include](../includes/footer-banner.md)]
