---
title: Entiteiten en gegevenssets
description: Gegevens weergeven op de pagina Entiteiten.
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e3f41c0424b2cd756d72ae6af9d5225ebba92628
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405476"
---
# <a name="entities-in-audience-insights"></a>Entiteiten in doelgroepinzichten

Ga, na het [configureren van uw gegevensbronnen](data-sources.md), naar de pagina **Entiteiten** om de kwaliteit van de opgenomen gegevens te evalueren. Entiteiten worden beschouwd als gegevenssets. Meerdere mogelijkheden van Dynamics 365 Customer Insights zijn gebouwd rond deze entiteiten. Door ze nauwkeurig te bekijken, kunt u de uitvoer van die mogelijkheden valideren.

Op de pagina **Entiteiten** worden entiteiten vermeld. Deze worden weergegeven in verschillende kolommen:

- **Naam**: de naam van uw gegevensentiteit. Als u een waarschuwingssymbool naast een entiteitsnaam ziet, betekent dit dat de gegevens voor die entiteit niet zijn geladen.
- **Bron**: het type gegevensbron waarin de entiteit is opgenomen
- **Gemaakt door**: naam van de gebruiker die de entiteit heeft gemaakt.
- **Gemaakt**: datum en tijdstip waarop de entiteit is gemaakt
- **Bijgewerkt door**: naam van de gebruiker die de entiteit heeft bijgewerkt.
- **Laatst bijgewerkt**: datum en tijd van de laatste update van de entiteit
- **Laatste vernieuwing**: datum en tijd van de laatste gegevensvernieuwing

## <a name="exploring-a-specific-entitys-data"></a>De gegevens van een specifieke entiteit verkennen

Selecteer een entiteit om de verschillende velden en records in die entiteit te verkennen.

> [!div class="mx-imgBorder"]
> ![Selecteer een entiteit](media/data-manager-entities-data.png "Een entiteit selecteren")

- Het tabblad **Gegevens** is standaard geselecteerd en toont een tabel met details over afzonderlijke records van de entiteit.

> [!div class="mx-imgBorder"]
> ![Veldentabel](media/data-manager-entities-fields.PNG "Veldentabel")

- Op het tabblad **Velden** wordt een tabel weergegeven voor het bekijken van details voor de geselecteerde entiteit, zoals veldnamen, gegevenstypen en typen. In de kolom **Type** worden aan het Common Data Model gekoppelde typen weergegeven, die automatisch worden geïdentificeerd door het systeem of [handmatig worden toegewezen](map-entities.md) door gebruikers. Dit zijn semantische typen die kunnen verschillen van de gegevenstypen van de kenmerken. Zo heeft bijvoorbeeld het veld *E-mail* een gegevenstype *Tekst*, maar is het (semantische) Common Data Model-type mogelijk *E-mail* of *E-mailadres*.

> [!NOTE]
> In beide tabellen wordt slechts een voorbeeld van de gegevens van uw entiteit weergegeven. Als u de volledige gegevensset wilt bekijken, gaat u naar de pagina **Gegevensbronnen**, selecteert u **Bewerken** en bekijkt u de gegevens van deze entiteit met de Power Query-editor, zoals uitgelegd in [Gegevensbronnen](data-sources.md).

Voor meer informatie over de gegevens die zijn opgenomen in de entiteit biedt de kolom **Overzicht** u een aantal belangrijke kenmerken van de gegevens, zoals nullen, ontbrekende waarden, unieke waarden, tellingen en distributies, zoals van toepassing op uw gegevens.

Selecteer het grafiekpictogram om het overzicht van de gegevens weer te geven.

> [!div class="mx-imgBorder"]
> ![Overzichtssymbool](media/data-manager-entities-summary.png "Aanvraagoverzichtstabel")

### <a name="next-step"></a>Volgende stap

Bekijk het onderwerp [Harmoniseren](data-unification.md) om meer te weten te komen over het *toewijzen*, *afstemmen* en *samenvoegen* van de opgenomen gegevens.
