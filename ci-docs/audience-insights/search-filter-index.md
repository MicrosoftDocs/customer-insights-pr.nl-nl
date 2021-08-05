---
title: Klantprofielen zoeken en filteren
description: Vind snel informatie over geharmoniseerde klantprofielen en filter op opgegeven kenmerken.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: a6131d4dddce48b0fba153bcefe5631e0d22d808
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554015"
---
# <a name="customer-profiles-search--filter-index"></a>Klantprofielen: zoek- en filterindex

Het resultaat van het harmoniseren van uw klantgegevens is een entiteit Klantprofiel die een geharmoniseerde weergave biedt van uw totale klantenbestand. Als u snel [informatie wilt vinden over een specifieke klant of groep klanten](customer-profiles.md), kunt u de mogelijkheden **Zoeken** en **Filteren** configureren op de pagina **Klanten**. Lees verder om te zien hoe beheerders de kenmerken op de pagina **Index voor zoeken en filteren** kunnen bewerken, die beschikbaar zijn voor gebruikers om te zoeken en te filteren.

> [!div class="mx-imgBorder"]
> ![Zoekfilter.](media/search-filter.png "Zoekfilter")

## <a name="add-fields-and-specify-attributes"></a>Velden toevoegen en kenmerken opgeven

Als het de eerste keer is dat u doorzoekbare kenmerken definieert als een beheerder, moet u eerst geïndexeerde velden definiëren. We raden u aan alle kenmerken te kiezen waarmee gebruikers klanten kunnen zoeken en filteren op de pagina **Klanten**. U kunt alleen kenmerken opgeven die bestaan in de entiteit Klantprofiel die u tijdens het gegevensharmonisatieproces hebt gemaakt.

1. Open de pagina **Klanten** en selecteer **Zoek- en filterindex**.

2. Selecteer **+ Toevoegen** om de geïndexeerde velden op te geven.

3. Selecteer de kenmerken in de lijst die u als geïndexeerde velden wilt toevoegen. U kunt altijd meer kenmerken toevoegen door **Toevoegen** te selecteren. U kunt ook alle geselecteerde kenmerken verwijderen door het symbool **Verwijderen** te selecteren.

## <a name="explore-the-indexed-customer-fields-table"></a>De tabel Geïndexeerde klantvelden verkennen

De volgende informatie wordt weergegeven in de tabel.

- **Naam**: vertegenwoordigt de naam van het kenmerk zoals deze wordt weergegeven in de entiteit Klantprofiel.
- **Gegevenstype**: geeft aan of het gegevenstype een tekenreeks, een getal of een datum is.
- **Opgenomen in zoekactie**: geeft aan of dit kenmerk kan worden gebruikt om te zoeken naar klanten op de pagina **Klanten** met het veld **Zoeken**.
- **Filter toevoegen**: besturingselement om te definiëren hoe dit kenmerk kan worden gebruikt voor het filteren op de pagina **Klanten**.

## <a name="editing-filtering-options-for-a-given-attribute"></a>Filteropties voor een bepaald kenmerk bewerken

Het menu **Filteren** op de pagina **Klanten** kan een verschillend aantal kenmerkniveaus bevatten (bijvoorbeeld verschillende leeftijdsgroepen om klanten op te filteren).

1. Selecteer **Filter toevoegen** voor een bepaald kenmerk op de pagina **Index voor zoeken en filteren**. U kunt het aantal resultaten en de volgorde waarin deze worden georganiseerd definiëren. Afhankelijk van het gegevenstype van het kenmerk wordt een van de volgende deelvensters weergegeven.

- Kenmerken van het type Tekenreeks: geef het aantal gewenste resultaten op in het deelvenster **Filteropties voor tekenreeksen** en het volgordebeleid waarmee ze worden georganiseerd.

- Kenmerken van het type Numeriek: geef de opgenomen intervallen op in het deelvenster **Filteropties voor getallen** en het volgordebeleid waarmee ze worden georganiseerd.

- Kenmerken van het type Datum: geef de opgenomen intervallen op in het deelvenster **Filteropties voor datums** en het volgordebeleid waarmee ze worden georganiseerd.

2. Selecteer **Opslaan** om uw wijzigingen toe te passen.

3. Selecteer **Uitvoeren** zodra u klaar bent om uw instellingen toe te passen.

## <a name="next-steps"></a>Volgende stappen

Ga naar de pagina **Klanten** om naar klantprofielen te zoeken of gebruik de geïndexeerde velden om een subset van alle klantprofielen te zien.


[!INCLUDE[footer-include](../includes/footer-banner.md)]