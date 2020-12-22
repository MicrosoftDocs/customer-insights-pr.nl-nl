---
title: Klantprofielen weergeven
description: Krijg een gecombineerd overzicht van uw geharmoniseerde klantgegevens.
ms.date: 12/01/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 13308c2f40cda0d7e813b4d94ab47d53b5ce2115
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/01/2020
ms.locfileid: "4653884"
---
# <a name="customer-profiles"></a><span data-ttu-id="9af22-103">Klantprofielen</span><span class="sxs-lookup"><span data-stu-id="9af22-103">Customer profiles</span></span>

<span data-ttu-id="9af22-104">De pagina **Klanten** toont een gecombineerd overzicht van uw klanten, gebaseerd op profielgegevens die zijn verzameld uit [alle gegevensbronnen](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="9af22-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="9af22-105">Klantprofielen zijn beschikbaar zodra u [de geharmoniseerde entiteit Klant hebt gemaakt](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="9af22-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="9af22-106">Zorg ervoor dat u het gegevensharmonisatieproces voltooit om een rijker beeld van uw klanten te krijgen.</span><span class="sxs-lookup"><span data-stu-id="9af22-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="9af22-107">Op de pagina kunt u ook naar klanten zoeken.</span><span class="sxs-lookup"><span data-stu-id="9af22-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="9af22-108">Klanten kunnen individuen of organisaties zijn (preview).</span><span class="sxs-lookup"><span data-stu-id="9af22-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="9af22-109">Elk klant- of organisatieprofiel wordt weergegeven door een tegel.</span><span class="sxs-lookup"><span data-stu-id="9af22-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="9af22-110">Selecteer een tegel om extra informatie over die specifieke klant of organisatie te zien.</span><span class="sxs-lookup"><span data-stu-id="9af22-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="9af22-111">Gebruik de paginatoetsen onder aan de pagina om aanvullende records te bekijken.</span><span class="sxs-lookup"><span data-stu-id="9af22-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="9af22-112">![B2C-klantprofielen](media/profiles-customers.png "B2C-klantprofielen")</span><span class="sxs-lookup"><span data-stu-id="9af22-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="9af22-113">Organisaties (preview)</span><span class="sxs-lookup"><span data-stu-id="9af22-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="9af22-114">![B2B-klantprofielen](media/profile-customers-b2b.png "B2B-klantprofielen")</span><span class="sxs-lookup"><span data-stu-id="9af22-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="9af22-115">Als u de tegels niet kunt zien wanneer u **Klanten** selecteert in navigatie, moet uw beheerder [minstens één doorzoekbaar kenmerk definiëren](search-filter-index.md) in de **Zoek- en filterindex**.</span><span class="sxs-lookup"><span data-stu-id="9af22-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="9af22-116">Zoeken naar klanten</span><span class="sxs-lookup"><span data-stu-id="9af22-116">Search for customers</span></span>

<span data-ttu-id="9af22-117">Zoek naar klanten door een naam of een ander kenmerk in het zoekvak in te voeren.</span><span class="sxs-lookup"><span data-stu-id="9af22-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="9af22-118">De zoekopdracht werkt alleen binnen de entiteit Klantprofiel die is gemaakt tijdens het gegevensharmonisatieproces.</span><span class="sxs-lookup"><span data-stu-id="9af22-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="9af22-119">Als beheerder kunt u de doorzoekbare kenmerken configureren met via de pagina **Index voor zoeken en filteren**.</span><span class="sxs-lookup"><span data-stu-id="9af22-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="9af22-120">Zie [Index voor zoeken en filteren beheren](search-filter-index.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9af22-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="9af22-121">Klanten filteren</span><span class="sxs-lookup"><span data-stu-id="9af22-121">Filter customers</span></span>

<span data-ttu-id="9af22-122">U kunt klanten filteren op de velden van de entiteit Klantprofiel.</span><span class="sxs-lookup"><span data-stu-id="9af22-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="9af22-123">Net als bij zoeken, moet uw beheerder eerst de velden definiëren als filterbaar met behulp van de pagina **Index voor zoeken en filteren**.</span><span class="sxs-lookup"><span data-stu-id="9af22-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="9af22-124">Selecteer **Filter** op de pagina **Klanten**.</span><span class="sxs-lookup"><span data-stu-id="9af22-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="9af22-125">Schakel de selectievakjes in naast de kenmerken waarop u klanten wilt filteren.</span><span class="sxs-lookup"><span data-stu-id="9af22-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="9af22-126">![Klantprofielen](media/profiles-customers3.png "Klantprofielen")</span><span class="sxs-lookup"><span data-stu-id="9af22-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="9af22-127">Verwijder uw filters door **Filters wissen** op de pagina **Klanten** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="9af22-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="9af22-128">Detailpagina van klant</span><span class="sxs-lookup"><span data-stu-id="9af22-128">Customer details page</span></span>

<span data-ttu-id="9af22-129">Selecteer een van de klanttegels om de **Detailpagina van klant** te openen.</span><span class="sxs-lookup"><span data-stu-id="9af22-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="9af22-130">Deze weergave bevat geharmoniseerde informatie voor de geselecteerde klant.</span><span class="sxs-lookup"><span data-stu-id="9af22-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="9af22-131">Klantdetails zijn onder meer:</span><span class="sxs-lookup"><span data-stu-id="9af22-131">Customer details include:</span></span>

-   <span data-ttu-id="9af22-132">**Klantprofieltegel:** deze tegel toont de verschillende waarden van de geharmoniseerde klantprofielentiteit.</span><span class="sxs-lookup"><span data-stu-id="9af22-132">**Customer profile tile:** This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="9af22-133">Deze details kunnen een e-mailadres, naam, woonplaats, enzovoort bevatten.</span><span class="sxs-lookup"><span data-stu-id="9af22-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="9af22-134">**Potentiële interesses, potentiële merken:** geeft aan of u een eigen verrijking hebt geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="9af22-134">**Potential interests, potential brands:** Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="9af22-135">Het staat voor potentiële interesses en affiniteit met merken die een klant met een vergelijkbaar profiel als deze klant zou kunnen hebben.</span><span class="sxs-lookup"><span data-stu-id="9af22-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="9af22-136">Zie [Klantprofielen verrijken met merk- en interesseaffiniteiten](enrichment-microsoft-graph.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9af22-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

-   <span data-ttu-id="9af22-137">**Metingen:** geeft aan of u een of meer metingen van een specifiek type hebt geconfigureerd: klantkenmerkmetingen.</span><span class="sxs-lookup"><span data-stu-id="9af22-137">**Measures:** Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="9af22-138">Ze omvatten berekende KPI's rond uw klanten op individueel klantniveau.</span><span class="sxs-lookup"><span data-stu-id="9af22-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="9af22-139">Zie [Metingen definiëren en beheren](measures.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9af22-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="9af22-140">**Activiteitentijdlijn:** geeft aan of u activiteiten hebt geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="9af22-140">**Activity timeline:** Shows if you have configured activities.</span></span> <span data-ttu-id="9af22-141">De tijdlijnweergave bevat activiteiten van deze klant op chronologische volgorde, te beginnen met de meest recente activiteit.</span><span class="sxs-lookup"><span data-stu-id="9af22-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="9af22-142">Zie [Klantactiviteiten](activities.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9af22-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="9af22-143">Selecteer **Terug naar Klanten** om terug te gaan naar de zoekpagina voor klanten.</span><span class="sxs-lookup"><span data-stu-id="9af22-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9af22-144">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="9af22-144">Next steps</span></span>

<span data-ttu-id="9af22-145">[Voeg meer gegevensbronnen toe](data-sources.md) of [maak klantsegmenten](segments.md).</span><span class="sxs-lookup"><span data-stu-id="9af22-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>
