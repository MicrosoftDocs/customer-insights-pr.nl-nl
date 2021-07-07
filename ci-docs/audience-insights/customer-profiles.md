---
title: Klantprofielen weergeven
description: Krijg een gecombineerd overzicht van uw geharmoniseerde klantgegevens.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: c9adb4d7db74573d0512ae7a68a0e7ab51c994a0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304598"
---
# <a name="customer-profiles"></a>Klantprofielen

De pagina **Klanten** toont een gecombineerd overzicht van uw klanten, gebaseerd op profielgegevens die zijn verzameld uit [alle gegevensbronnen](data-sources.md). Klantprofielen zijn beschikbaar zodra u [de geharmoniseerde entiteit Klant hebt gemaakt](data-unification.md). Zorg ervoor dat u het gegevensharmonisatieproces voltooit om een rijker beeld van uw klanten te krijgen. Op de pagina kunt u ook naar klanten zoeken.

Klanten kunnen individuen of organisaties zijn (preview). Elk klant- of organisatieprofiel wordt weergegeven door een tegel. Selecteer een tegel om extra informatie over die specifieke klant of organisatie te zien. Gebruik de paginatoetsen onder aan de pagina om aanvullende records te bekijken.

> [!div class="mx-imgBorder"] 
> ![B2C-klantprofielen](media/profiles-customers.png "B2C-klantprofielen")

Organisaties (preview)
> [!div class="mx-imgBorder"] 
> ![B2B-klantprofielen](media/profile-customers-b2b.png "B2B-klantprofielen")

> [!NOTE]
> Als u de tegels niet kunt zien wanneer u **Klanten** selecteert in navigatie, moet uw beheerder [minstens één doorzoekbaar kenmerk definiëren](search-filter-index.md) in de **Zoek- en filterindex**.

## <a name="search-for-customers"></a>Zoeken naar klanten

Zoek naar klanten door een naam of een ander kenmerk in het zoekvak in te voeren. De zoekopdracht werkt alleen binnen de entiteit Klantprofiel die is gemaakt tijdens het gegevensharmonisatieproces.

Als beheerder kunt u de doorzoekbare kenmerken configureren met via de pagina **Index voor zoeken en filteren**. Zie [Index voor zoeken en filteren beheren](search-filter-index.md) voor meer informatie.

## <a name="filter-customers"></a>Klanten filteren

U kunt klanten filteren op de velden van de entiteit Klantprofiel. Net als bij zoeken, moet uw beheerder eerst de velden definiëren als filterbaar met behulp van de pagina **Index voor zoeken en filteren**.

1. Selecteer **Filter** op de pagina **Klanten**.

2. Schakel de selectievakjes in naast de kenmerken waarop u klanten wilt filteren.

   > [!div class="mx-imgBorder"] 
   > ![Klantprofielen](media/profiles-customers3.png "Klantprofielen")

3. Verwijder uw filters door **Filters wissen** op de pagina **Klanten** te selecteren.

##  <a name="customer-details-page"></a>Detailpagina van klant

Selecteer een van de klanttegels om de **Detailpagina van klant** te openen. Deze weergave bevat geharmoniseerde informatie voor de geselecteerde klant.

Klantdetails zijn onder meer:

-   **Klantprofieltegel**: deze tegel toont de verschillende waarden van de geharmoniseerde klantprofielentiteit. Deze details kunnen een e-mailadres, naam, woonplaats, enzovoort bevatten. 

-   **Potentiële interesses, potentiële merken**: geeft aan of u een eigen verrijking hebt geconfigureerd. Het staat voor potentiële interesses en affiniteit met merken die een klant met een vergelijkbaar profiel als deze klant zou kunnen hebben. Zie [Klantprofielen verrijken met merk- en interesseaffiniteiten](enrichment-microsoft.md) voor meer informatie.

-   **Metingen**: geeft aan of u een of meer metingen van een specifiek type hebt geconfigureerd: klantkenmerkmetingen. Ze omvatten berekende KPI's rond uw klanten op individueel klantniveau. Zie [Metingen definiëren en beheren](measures.md) voor meer informatie.

-   **Activiteitentijdlijn**: geeft aan of u activiteiten hebt geconfigureerd. De tijdlijnweergave bevat activiteiten van deze klant op chronologische volgorde, te beginnen met de meest recente activiteit. Zie [Klantactiviteiten](activities.md) voor meer informatie.

Selecteer **Terug naar Klanten** om terug te gaan naar de zoekpagina voor klanten.

## <a name="next-steps"></a>Volgende stappen

[Voeg meer gegevensbronnen toe](data-sources.md) of [maak klantsegmenten](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
