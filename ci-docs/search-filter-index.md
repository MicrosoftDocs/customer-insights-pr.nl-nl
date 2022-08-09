---
title: De zoek- en filterindex voor klantprofielen beheren
description: Vind snel informatie over geharmoniseerde klantprofielen en filter op opgegeven kenmerken.
ms.date: 07/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: dfbfcbff3ffb3e4483252377e591229631d38556
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/22/2022
ms.locfileid: "9187903"
---
# <a name="manage-the-search--filter-index-for-customer-profiles"></a>De zoek- en filterindex voor klantprofielen beheren

Het resultaat van het harmoniseren van uw klantgegevens is de entiteit *Klant* die een geharmoniseerde weergave biedt van uw totale klantenbestand. Als gebruikers snel [informatie willen vinden over een specifieke klant of groep klanten](customer-profiles.md), moet een beheerder de mogelijkheden **Zoeken** en **Filteren** configureren voor de pagina **Klanten**.

   :::image type="content" source="media/search-filter.png" alt-text="Zoekfilter":::

## <a name="define-searchable-attributes-and-indexed-fields"></a>Doorzoekbare kenmerken en geïndexeerde velden definiëren

Als het de eerste keer is dat u doorzoekbare kenmerken definieert als een beheerder, definieert u eerst geïndexeerde velden. We raden u aan alle kenmerken te kiezen waarmee gebruikers klanten kunnen zoeken en filteren op de pagina **Klanten**. Alleen kenmerken die bestaan in de entiteit *Klant* die u tijdens het gegevensharmonisatieproces hebt gemaakt, kunnen worden opgegeven.

1. Ga naar **Klanten** en selecteer **Zoek- en filterindex**.

1. Selecteer **+Toevoegen**.

1. Selecteer de kenmerken in de lijst die u als geïndexeerde velden wilt toevoegen en klik op **Toepassen**.

1. Selecteer **Toevoegen** om meer kenmerken toe te voegen. Als u een geselecteerd kenmerk wilt verwijderen, selecteert u het kenmerk en selecteert u vervolgens **Verwijderen**.

   :::image type="content" source="media/search-filter-index.png" alt-text="Pagina Zoek- en filterindex":::

1. Selecteer **Uitvoeren** zodra u klaar bent om uw instellingen voor zoeken en filteren toe te passen. Nadat de wijzigingen zijn verwerkt, vindt u ze in de [klantenkaarten op de pagina Klant](customer-profiles.md).

## <a name="define-filtering-options-for-a-given-attribute"></a>Filteropties voor een bepaald kenmerk definiëren

Stel de velden in die kunnen worden gebruikt voor het filteren van klanten op de pagina **Klanten**.

1. Ga naar **Klanten** en selecteer **Zoek- en filterindex**.

1. Selecteer een kenmerk en **Filter toevoegen**. Definieer het aantal resultaten en de volgorde waarin deze worden georganiseerd. Afhankelijk van het gegevenstype van het kenmerk wordt een van de volgende deelvensters weergegeven.

   - Kenmerken van het type Tekenreeks: geef het aantal gewenste resultaten op in het deelvenster **Filter voor tekenreeksen** en het volgordebeleid waarmee ze worden georganiseerd.

   - Kenmerken van het type Numeriek: geef de opgenomen intervallen op in het deelvenster **Filter voor getallen** en het volgordebeleid waarmee ze worden georganiseerd.

   - Kenmerken van het type Datum: geef de opgenomen intervallen op in het deelvenster **Filter voor datums** en het volgordebeleid waarmee ze worden georganiseerd.

1. Selecteer **OK**. Herhaal dit voor alle kenmerken waarop u wilt filteren.

1. Selecteer **Uitvoeren** zodra u klaar bent om uw instellingen voor zoeken en filteren toe te passen. Nadat de wijzigingen zijn verwerkt, vindt u ze in de [klantenkaarten op de pagina Klant](customer-profiles.md).

## <a name="view-indexed-customer-fields"></a>Geïndexeerde klantvelden weergeven

Op de pagina **Zoek- en filterindex** worden de volgende gegevens weergegeven:

- **Naam**: staat voor de naam van het kenmerk zoals deze wordt weergegeven in de entiteit *Klant*.
- **Gegevenstype**: geeft aan of het gegevenstype een tekenreeks, een getal of een datum is.
- **Opgenomen in zoekactie**: geeft aan of dit kenmerk kan worden gebruikt om te zoeken naar klanten op de pagina **Klanten** met het veld **Zoeken**.
- **Filter toevoegen**: besturingselement om te definiëren hoe dit kenmerk kan worden gebruikt voor het filteren op de pagina **Klanten**.

## <a name="next-steps"></a>Volgende stappen

Bekijk de [pagina met geharmoniseerde profielen](customer-profiles.md) om naar profielen te zoeken of gebruik de geïndexeerde velden om een subset van alle geharmoniseerde profielen te zien.

[!INCLUDE [footer-include](includes/footer-banner.md)]
