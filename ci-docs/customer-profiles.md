---
title: Klantprofielen weergeven
description: Uw geharmoniseerde klantgegevens bekijken, waaronder het gebruik van zoek- en filterfuncties
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-customer-card
- ci-activities
- ci-activities-wizard
- customerInsights
ms.openlocfilehash: 6cdf47e6997f230811dcb0f2cf5542f3a6db2367
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188087"
---
# <a name="view-customer-profiles"></a>Klantprofielen weergeven

Klantprofielen zijn beschikbaar zodra u de [geharmoniseerde entiteit *Klant* maakt](data-unification.md). Op de pagina **Klanten** wordt de gecombineerde weergave van uw geharmoniseerde klantprofielen weergegeven. Klanten kunnen individuen of organisaties zijn.

Ga naar de pagina **Klanten** om uw klanten en hun profielen te bekijken. Elk klantprofiel wordt weergegeven door een tegel. Gebruik de pagineringsknoppen om meer records te krijgen. De kaart geeft velden weer van de entiteit *Klant* zoals gedefinieerd in de **Zoek- en filterindex**. De volgorde van de velden binnen elke kaart wordt door het systeem gekozen.

> [!NOTE]
> Als u de tegels niet kunt zien wanneer u **Klanten** selecteert in de navigatie, moet uw beheerder [minimaal één doorzoekbaar kenmerk definiëren](search-filter-index.md) in de **Zoek- en filterindex**.

:::image type="content" source="media/customers-page-result-tiles-B2C.png" alt-text="Pagina Klanten met resultaattegels.":::

Selecteer een van de volgende acties:
- [Klantdetails weergeven](#view-customer-details)
- [De zoek- en filterindex beheren](search-filter-index.md) (alleen beheerders)
- [Klanten filteren](#filter-customers)
- Selecteer **Kaarten uitvouwen** of **Kaarten samenvouwen** om de informatie op de klanttegel uit te vouwen of samen te vouwen
- **Sorteren op** een bepaald kenmerk
- [Zoeken naar klanten](#search-for-customers)

  > [!NOTE]
  > Als u zoeken en filteren wilt gebruiken, moet een beheerder de doorzoekbare kenmerken configureren en de filterbare velden definiëren met behulp van de zoek- en filterindex.

## <a name="search-for-customers"></a>Zoeken naar klanten

Zoek naar klanten door een naam of een ander kenmerk in **Klanten zoeken** in te voeren. De doorzoekbare kenmerken worden gedefinieerd door de beheerder en komen uit de geharmoniseerde entiteit *Klant*.

> [!NOTE]
> **Tekenreeks** is het enige gegevenstype dat is opgenomen in de zoekopdracht. Gebruik het in het veld **Klanten zoeken** op de pagina Klanten om naar klanten te zoeken.

## <a name="filter-customers"></a>Klanten filteren

Filter klanten filteren op de velden van de entiteit *Klant*. Filterbare velden worden gedefinieerd door de beheerder.

1. Selecteer **Filters weergeven** op de pagina **Klanten**. Het deelvenster Filter wordt weergegeven.

1. Schakel de selectievakjes in naast de kenmerken waarop u klanten wilt filteren.

1. Verwijder alle filters door **Filters wissen** te verwijderen of schakel een selectievakje naast een geselecteerd kenmerk uit.

1. Selecteer **Filters verbergen** om het filtervenster te sluiten.

1. Als u de filterresultaten wilt opslaan als een [segment](segments.md), selecteert u **Filters opslaan als segment**.
   1. Voer een naam in voor het segment.
   1. Als u het segment wilt opslaan, selecteert u **Opslaan**.
   1. Kies of u het segment nu wilt uitvoeren door **Activeren** te selecteren of voer het **Later** uit.

## <a name="view-customer-details"></a>Klantdetails weergeven

Selecteer op de pagina **Klanten** een klanttegel om details voor de geselecteerde klant te bekijken.

:::image type="content" source="media/customers-details-B2C.png" alt-text="Pagina Klantdetails.":::

Klantdetails zijn onder meer:

**Tegel Klantprofiel**: deze tegel toont de verschillende waarden van de geharmoniseerde entiteit *Klant*. Als een veld geen waarde heeft voor het geselecteerde klantprofiel, wordt het niet weergegeven. Dit geldt niet voor het adresveld. De tegel is gestructureerd in secties:

- De eerste sectie toont een vooraf gedefinieerde set velden, gevolgd door alle velden die deel uitmaken van de zoek- en filterindex. Alle adresgerelateerde velden worden gecombineerd in één regel, die altijd wordt weergegeven, zelfs als het profiel geen adresgegevens bevat.
- **Contactpersonen voor deze klant** worden in omgevingen voor zakelijke accounts weergegeven. Iedere contactpersoon wordt getoond met de eigen velden. Lege velden zijn verborgen.
- **Extra velden**: toont de overige velden van de geselecteerde klant, behalve id's.
- **Id's**: geeft alle id's weer onder de bijbehorende entiteitsnaam. Velden worden op basis van de semantiek ervan geïdentificeerd als id's.

**Activiteitentijdlijn**: toont gegevens als u [activiteiten](activities.md) hebt geconfigureerd. De tijdlijnweergave bevat chronologisch gesorteerde activiteiten van de geselecteerde klant, te beginnen met de meest recente activiteit.

**Inzichten**:

- **Metingen** geven aan of u [metingen van het type klantkenmerk](measures.md) hebt geconfigureerd. Ze omvatten berekende KPI's rond uw klanten op individueel klantniveau.

- **Potentiële interesses, potentiële merken** geven aan of u een [verrijking voor een merk- of interesseaffiniteit](enrichment-microsoft.md) hebt geconfigureerd. Dit vertegenwoordigt potentiële interesses en affiniteiten voor merken op basis van andere klanten van wie het profiel vergelijkbaar is met het geselecteerde klantprofiel.

Selecteer **Terug naar Klanten** om terug te gaan naar de pagina **Klanten**.

## <a name="next-steps"></a>Volgende stappen

[Meer gegevensbronnen toevoegen](data-sources.md), [geharmoniseerde profielen verrijken](enrichment-hub.md) of [segmenten maken](segments.md) om te werken met geharmoniseerde klantprofielen in andere toepassingen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
