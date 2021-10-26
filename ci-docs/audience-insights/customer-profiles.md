---
title: Klantprofielen weergeven
description: Krijg een gecombineerd overzicht van uw geharmoniseerde klantgegevens.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 07d2206372f89cd7dcd9df84c87024a6f87d5eac
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623263"
---
# <a name="customer-profiles"></a>Klantprofielen

Op de pagina **Klanten** wordt een gecombineerde weergave getoond van uw geharmoniseerde klantprofielen. De klantprofielen zijn beschikbaar zodra u [de geharmoniseerde klantentiteit heeft gemaakt](data-unification.md). Op de pagina kunt u naar klanten zoeken en de index voor die zoekopdracht definiëren.

Klanten kunnen individuen of organisaties zijn. Elk klantprofiel wordt weergegeven door een tegel. Gebruik de pagineringsknoppen om meer records te krijgen. De kaart geeft velden weer van de entiteit *Klant* zoals gedefinieerd in de **Zoek- en filterindex**. Selecteer een tegel om gegevens voor de geselecteerde klant te zien op een speciale pagina met de naam [Klantdetails](customer-profiles.md#customer-details-page).

> [!div class="mx-imgBorder"] 
> ![Klantenpagina met resultaattegels](media/customers-page-result-tiles-B2C.png "Klantenpagina met resultaattegels")

> [!NOTE]
> Als u de tegels niet kunt zien wanneer u **Klanten** selecteert in de navigatie, moet de beheerder [minimaal één doorzoekbaar kenmerk definiëren](search-filter-index.md) in de **Zoek- en filterindex**.

## <a name="search-for-customers"></a>Zoeken naar klanten

Zoek naar klanten door een naam of een ander kenmerk in het zoekvak in te voeren. De zoekopdracht werkt alleen binnen de entiteit _Klant_ die is gemaakt tijdens het proces van gegevensharmonisering.

Als beheerder kunt u de doorzoekbare kenmerken configureren met via de pagina **Index voor zoeken en filteren**. Ga voor meer informatie naar [Zoek- en filterindex beheren](search-filter-index.md).

## <a name="filter-customers"></a>Klanten filteren

U kunt klanten filteren op velden van de entiteit _Klant_. Net als bij zoeken, moet uw beheerder eerst de velden definiëren als filterbaar met behulp van de pagina **Index voor zoeken en filteren**.

1. Selecteer **Filters weergeven** op de pagina **Klanten**.

1. Schakel de selectievakjes in naast de kenmerken waarop u klanten wilt filteren.

1. Verwijder uw filters door **Filters wissen** op de pagina **Klanten** te selecteren.

## <a name="customer-details-page"></a>Detailpagina van klant

Selecteer een van de klanttegels om de **Detailpagina van klant** te openen. Deze weergave bevat geharmoniseerde informatie voor de geselecteerde klant. Klantgegevens omvatten de volgende inhoud:

**Tegel Klantprofiel**: deze tegel toont de verschillende waarden van de geharmoniseerde entiteit _Klant_. Als een veld geen waarde heeft voor het geselecteerde klantprofiel, wordt het niet weergegeven. De tegel is gestructureerd in secties:  
  - De eerste sectie toont een vooraf gedefinieerde set velden, gevolgd door alle velden die deel uitmaken van de zoek- en filterindex. Alle adresgerelateerde velden worden gecombineerd in één regel als het profiel dergelijke velden bevat. 
  - **Contactpersonen voor deze klant**: in omgevingen voor zakelijke accounts ziet u alle gerelateerde contactpersonen voor deze klant als het tweede gedeelte. Iedere contactpersoon wordt getoond met de eigen velden. Lege velden zijn verborgen.
  - **Extra velden** : toont de overige velden van de geselecteerde klant, behalve id's. 
  - **ID's**: geeft alle id's weer onder de bijbehorende entiteitsnaam. Velden worden geïdentificeerd als ID door hun semantiek, waardoor ze als zodanig worden gecategoriseerd.

**Activiteitentijdlijn**: toont gegevens als u activiteiten heeft geconfigureerd. De tijdlijnweergave bevat chronologisch gesorteerde activiteiten van de geselecteerde klant, te beginnen met de meest recente activiteit. Ga voor meer informatie naar [Klantactiviteiten](activities.md).

**Inzichten**:  
  - **Meetcriteria**: Geeft aan of u een of meer meetcriteria heeft geconfigureerd voor klantkenmerken. Ze omvatten berekende KPI's rond uw klanten op individueel klantniveau. Ga voor meer informatie naar [Meetcriteria definiëren en beheren](measures.md).

  - **Potentiële interesses, potentiële merken**: geeft aan of u een verrijking voor een merk- of interesseaffiniteit heeft geconfigureerd. Dit vertegenwoordigt potentiële interesses en affiniteiten voor merken op basis van andere klanten van wie het profiel vergelijkbaar is met het geselecteerde klantprofiel. Ga voor meer informatie naar [Klantprofielen verrijken met merk- en interesse-affiniteiten](enrichment-microsoft.md).

Om terug te keren naar de klantzoekpagina, selecteert u **Terug naar Klanten**.

## <a name="next-steps"></a>Volgende stappen

[Meer gegevensbronnen toevoegen](data-sources.md), [geharmoniseerde profielen verrijken](enrichment-hub.md) of [segmenten maken](segments.md) om te werken met geharmoniseerde klantprofielen in andere toepassingen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
