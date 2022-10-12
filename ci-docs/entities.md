---
title: Entiteiten in Customer Insights
description: Gegevens weergeven op de pagina Entiteiten.
ms.date: 08/04/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: e365945b27e7c985ca5371c6b72619610b6f3af1
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610092"
---
# <a name="entities-in-customer-insights"></a>Entiteiten in Customer Insights

Ga, na het [configureren van uw gegevensbronnen](data-sources.md), naar de pagina **Entiteiten** om de kwaliteit van de opgenomen gegevens te evalueren. Entiteiten worden beschouwd als gegevenssets. Meerdere mogelijkheden van Dynamics 365 Customer Insights zijn gebouwd rond deze entiteiten. Door ze nauwkeurig te bekijken, kunt u de uitvoer van die mogelijkheden valideren.

Wanneer u in Customer Insights werkt om uw gegevens te verrijken of segmenten, meetwaarden en activiteiten te maken, worden de entiteiten die op basis van die acties zijn gemaakt, weergegeven op de pagina **Entiteiten**.

## <a name="view-a-list-of-entities"></a>Een lijst met entiteiten weergeven

Ga naar **Gegevens** > **Entiteiten** om een lijst met entiteiten te bekijken. De volgende gegevens worden voor elke entiteit weergegeven.

- **Naam**: de naam van de gegevensentiteit. Als u een waarschuwingssymbool naast een entiteitsnaam ziet, betekent dit dat de gegevens voor die entiteit niet zijn geladen.
- **Bron**: type gegevensbron dat de entiteit heeft opgenomen.
- **Bijgewerkt**: het tijdstip waar de entiteit voor het laatst is bijgewerkt.
- **Status**: details over de laatste update van de entiteit.

## <a name="explore-a-specific-entitys-data"></a>De gegevens van een specifieke entiteit verkennen

1. Ga naar **Gegevens** > **Entiteiten**.
1. Selecteer een entiteit om de pagina met details te openen.  
1. Verken de verschillende velden die zijn opgenomen voor die entiteit.

- Het tabblad **Kenmerken** is standaard geselecteerd en bevat een details voor de geselecteerde entiteit, zoals veldnamen, gegevenstypen en typen. In de kolom **Type** worden aan het Common Data Model gekoppelde typen weergegeven, die automatisch worden geïdentificeerd door het systeem of [handmatig worden toegewezen](map-entities.md) door gebruikers. Deze typen zijn semantische typen die kunnen verschillen van de gegevenstypen van de kenmerken. Het veld *E-mail* hieronder heeft bijvoorbeeld het gegevenstype *Tekenreeks*, maar het bijbehorende (semantische) type Common Data Model zou *Email*, *EmailAddress* of *Identity.Service.Email* kunnen zijn.

   :::image type="content" source="media/data-manager-entities-fields.png" alt-text="Veldentabel.":::

   > [!NOTE]
   > Deze pagina toont slechts een voorbeeld van de gegevens van uw entiteit. Als u de volledige gegevensset wilt bekijken, gaat u naar de pagina **Gegevensbronnen**, selecteert u **Bewerken** en bekijkt u de gegevens van deze entiteit met de Power Query-editor, zoals wordt uitgelegd in [Gegevensbronnen](data-sources.md).

   Voor meer informatie over de gegevens die zijn opgenomen in de entiteit biedt de kolom **Overzicht** u een aantal belangrijke gegevenskenmerken, zoals nullen, ontbrekende waarden, unieke waarden, tellingen en distributies, zoals van toepassing op uw gegevens. Selecteer het grafiekpictogram om het overzicht van de gegevens weer te geven.

   :::image type="content" source="media/data-manager-entities-summary.png" alt-text="Gegevensoverzichtstabel.":::

- Op het tabblad **Gegevens** wordt een tabel weergegeven met details over afzonderlijke records van de entiteit. De vermelde details zijn afhankelijk van het gegevenstype van de entiteit.

   :::image type="content" source="media/data-manager-entities-data.png" alt-text="Selecteer een entiteit.":::

- Het tabblad **Rapporten** (beschikbaar voor sommige entiteiten) stelt u in staat uw gegevens te visualiseren door een rapport te maken dat de volgende kolommen bevat:

  - **Naam rapport**: naam van het rapport.
  - **Gemaakt door**: naam van de gebruiker die de entiteit heeft gemaakt.
  - **Gemaakt**: datum en tijdstip waarop de entiteit is gemaakt.
  - **Bewerkt door**: naam van de gebruiker die de entiteit heeft gewijzigd.
  - **Bewerkt**: datum en tijdstip waarop de entiteit is gewijzigd.

[!INCLUDE [footer-include](includes/footer-banner.md)]
