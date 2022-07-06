---
title: Entiteiten in Customer Insights
description: Gegevens weergeven op de pagina Entiteiten.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: 4abb7704710ac269a4f3c9463fe905fa6eec3234
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081117"
---
# <a name="entities-in-customer-insights"></a>Entiteiten in Customer Insights

Ga, na het [configureren van uw gegevensbronnen](data-sources.md), naar de pagina **Entiteiten** om de kwaliteit van de opgenomen gegevens te evalueren. Entiteiten worden beschouwd als gegevenssets. Meerdere mogelijkheden van Dynamics 365 Customer Insights zijn gebouwd rond deze entiteiten. Door ze nauwkeurig te bekijken, kunt u de uitvoer van die mogelijkheden valideren.

De pagina **Entiteiten** bevat entiteiten en de volgende kolommen:

- **Naam**: de naam van de gegevensentiteit. Als u een waarschuwingssymbool naast een entiteitsnaam ziet, betekent dit dat de gegevens voor die entiteit niet zijn geladen.
- **Bron**: type gegevensbron dat de entiteit heeft opgenomen.
- **Bijgewerkt**: het tijdstip waar de entiteit voor het laatst is bijgewerkt.
- **Status**: details over de laatste update van de entiteit.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>De gegevens van een specifieke entiteit verkennen

1. Ga naar **Gegevens** > **Entiteiten**.
1. Selecteer op de pagina **Entiteiten** een entiteit om de detailpagina te openen.  
1. Verken de verschillende velden die zijn opgenomen voor die entiteit.

- Het tabblad **Kenmerken** is standaard geselecteerd en bevat een tabel om details voor de geselecteerde entiteit te controleren, zoals veldnamen, gegevenstypen en typen. In de kolom **Type** worden aan het Common Data Model gekoppelde typen weergegeven, die automatisch worden geïdentificeerd door het systeem of [handmatig worden toegewezen](map-entities.md) door gebruikers. Deze typen zijn semantische typen die kunnen verschillen van de gegevenstypen van de kenmerken. Het veld *E-mail* hieronder heeft bijvoorbeeld het gegevenstype *Tekst*, maar het (semantische) Common Data Model-type zou *E-mail* of *E-mailadres* kunnen zijn.

> [!div class="mx-imgBorder"]
> ![Veldentabel.](media/data-manager-entities-fields.PNG "Veldentabel")

> [!NOTE]
> Deze pagina toont slechts een voorbeeld van de gegevens van uw entiteit. Als u de volledige gegevensset wilt bekijken, gaat u naar de pagina **Gegevensbronnen**, selecteert u **Bewerken** en bekijkt u de gegevens van deze entiteit met de Power Query-editor, zoals wordt uitgelegd in [Gegevensbronnen](data-sources.md).

Voor meer informatie over de gegevens die zijn opgenomen in de entiteit biedt de kolom **Overzicht** u een aantal belangrijke kenmerken van de gegevens, zoals nullen, ontbrekende waarden, unieke waarden, tellingen en distributies, zoals van toepassing op uw gegevens. Selecteer het grafiekpictogram om het overzicht van de gegevens weer te geven.

> [!div class="mx-imgBorder"]
> ![Overzichtssymbool.](media/data-manager-entities-summary.png "Aanvraagoverzichtstabel")

- Op het tabblad **Gegevens** wordt een tabel weergegeven met details over individuele records van de entiteit. De vermelde details zijn afhankelijk van het gegevenstype van de entiteit.

> [!div class="mx-imgBorder"]
> ![Selecteer een entiteit.](media/data-manager-entities-data.png "Selecteer een entiteit")

- Het tabblad **Rapporten** (beschikbaar voor sommige entiteiten) stelt u in staat uw gegevens te visualiseren door een rapport te maken. Dit bevat de volgende kolommen:

  - **Naam rapport**: naam van het rapport.
  - **Gemaakt door**: naam van de gebruiker die de entiteit heeft gemaakt.
  - **Gemaakt**: datum en tijdstip waarop de entiteit is gemaakt.
  - **Bewerkt door**: naam van de gebruiker die de entiteit heeft gewijzigd.
  - **Bewerkt**: datum en tijdstip waarop de entiteit is gewijzigd. 

## <a name="entity-specific-information"></a>Entiteitsspecifieke informatie

De volgende sectie bevat informatie over enkele door het systeem gemaakte entiteiten.

### <a name="corrupted-data-sources"></a>Beschadigde gegevensbronnen

Velden van een opgenomen gegevensbron kunnen beschadigde gegevens bevatten. Records met beschadigde velden worden weergegeven in door het systeem gemaakte entiteiten. Als u weet dat er beschadigde records zijn, kunt u bepalen welke gegevens u op het bronsysteem moet bekijken en bijwerken. Na de volgende vernieuwing van de gegevensbron worden de gecorrigeerde records opgenomen in Customer Insights en doorgegeven aan downstream processen. 

In een kolom 'verjaardag' bijvoorbeeld is het gegevenstype ingesteld op 'datum'. Voor een klantrecord is de verjaardag ingevoerd als '01/01/19777'. Het systeem markeert dit record als beschadigd. Iemand kan nu in het bronsysteem de geboortedatum wijzigen in '1977'. Na een automatische vernieuwing van gegevensbronnen heeft het veld nu een geldige indeling en wordt het record verwijderd uit de beschadigde entiteit. 

Ga naar **Gegevens** > **Entiteiten** en zoek naar de beschadigde entiteiten in de sectie **Systeem**. Naamgevingsschema van beschadigde entiteiten: 'DataSourceName_EntityName_corrupt'. Selecteer een beschadigde entiteit om alle beschadigde velden en de reden op individueel recordniveau te identificeren.
> [!div class="mx-imgBorder"]
> ![Reden van beschadiging.](media/corruption-reason.png "Reden van beschadiging")

Customer Insights verwerkt nog steeds beschadigde records. Zij kunnen echter problemen veroorzaken wanneer met de uniforme gegevens wordt gewerkt.

De volgende controles worden uitgevoerd op de opgenomen gegevens om beschadigde records te onthullen: 

- De waarde van een veld komt niet overeen met het gegevenstype van de kolom.
- Velden bevatten tekens waardoor de kolommen niet overeenkomen met het verwachte schema. Bijvoorbeeld: onjuist opgemaakte aanhalingstekens, aanhalingstekens zonder escape of tekens voor nieuwe regels.
- Als er kolommen voor datetime/date/datetimeoffset zijn, moet hun indeling in het model worden gespecificeerd als niet de standaard ISO-indeling wordt gevolgd.


[!INCLUDE [footer-include](includes/footer-banner.md)]
