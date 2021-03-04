---
title: Klantprofielen zoeken en filteren
description: Vind snel informatie over geharmoniseerde klantprofielen en filter op opgegeven kenmerken.
ms.date: 01/19/2021
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d675738c43cbdb5f9b478d53d6124db38ba3004d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270060"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="b4191-103">Klantprofielen: zoek- en filterindex</span><span class="sxs-lookup"><span data-stu-id="b4191-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="b4191-104">Het resultaat van het harmoniseren van uw klantgegevens is een entiteit Klantprofiel die een geharmoniseerde weergave biedt van uw totale klantenbestand.</span><span class="sxs-lookup"><span data-stu-id="b4191-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="b4191-105">Als u snel [informatie wilt vinden over een specifieke klant of groep klanten](customer-profiles.md), kunt u de mogelijkheden **Zoeken** en **Filteren** configureren op de pagina **Klanten**.</span><span class="sxs-lookup"><span data-stu-id="b4191-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="b4191-106">Lees verder om te zien hoe beheerders de kenmerken op de pagina **Index voor zoeken en filteren** kunnen bewerken, die beschikbaar zijn voor gebruikers om te zoeken en te filteren.</span><span class="sxs-lookup"><span data-stu-id="b4191-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b4191-107">![Zoekfilter](media/search-filter.png "Zoekfilter")</span><span class="sxs-lookup"><span data-stu-id="b4191-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="b4191-108">Velden toevoegen en kenmerken opgeven</span><span class="sxs-lookup"><span data-stu-id="b4191-108">Add fields and specify attributes</span></span>

<span data-ttu-id="b4191-109">Als het de eerste keer is dat u doorzoekbare kenmerken definieert als een beheerder, moet u eerst geïndexeerde velden definiëren.</span><span class="sxs-lookup"><span data-stu-id="b4191-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="b4191-110">We raden u aan alle kenmerken te kiezen waarmee gebruikers klanten kunnen zoeken en filteren op de pagina **Klanten**.</span><span class="sxs-lookup"><span data-stu-id="b4191-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="b4191-111">U kunt alleen kenmerken opgeven die bestaan in de entiteit Klantprofiel die u tijdens het gegevensharmonisatieproces hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="b4191-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="b4191-112">Open de pagina **Klanten** en selecteer **Zoek- en filterindex**.</span><span class="sxs-lookup"><span data-stu-id="b4191-112">Open the **Customers** page and select **Search & filter index**.</span></span>

2. <span data-ttu-id="b4191-113">Selecteer **+ Toevoegen** om de geïndexeerde velden op te geven.</span><span class="sxs-lookup"><span data-stu-id="b4191-113">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="b4191-114">Selecteer de kenmerken in de lijst die u als geïndexeerde velden wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="b4191-114">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="b4191-115">U kunt altijd meer kenmerken toevoegen door **Toevoegen** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="b4191-115">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="b4191-116">U kunt ook alle geselecteerde kenmerken verwijderen door het symbool **Verwijderen** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="b4191-116">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="b4191-117">De tabel Geïndexeerde klantvelden verkennen</span><span class="sxs-lookup"><span data-stu-id="b4191-117">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="b4191-118">De volgende informatie wordt weergegeven in de tabel.</span><span class="sxs-lookup"><span data-stu-id="b4191-118">The following information is presented in the table.</span></span>

- <span data-ttu-id="b4191-119">**Naam**: vertegenwoordigt de naam van het kenmerk zoals deze wordt weergegeven in de entiteit Klantprofiel.</span><span class="sxs-lookup"><span data-stu-id="b4191-119">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="b4191-120">**Gegevenstype**: geeft aan of het gegevenstype een tekenreeks, een getal of een datum is.</span><span class="sxs-lookup"><span data-stu-id="b4191-120">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="b4191-121">**Opgenomen in zoekactie**: geeft aan of dit kenmerk kan worden gebruikt om te zoeken naar klanten op de pagina **Klanten** met het veld **Zoeken**.</span><span class="sxs-lookup"><span data-stu-id="b4191-121">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="b4191-122">**Filter toevoegen**: besturingselement om te definiëren hoe dit kenmerk kan worden gebruikt voor het filteren op de pagina **Klanten**.</span><span class="sxs-lookup"><span data-stu-id="b4191-122">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="b4191-123">Filteropties voor een bepaald kenmerk bewerken</span><span class="sxs-lookup"><span data-stu-id="b4191-123">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="b4191-124">Het menu **Filteren** op de pagina **Klanten** kan een verschillend aantal kenmerkniveaus bevatten (bijvoorbeeld verschillende leeftijdsgroepen om klanten op te filteren).</span><span class="sxs-lookup"><span data-stu-id="b4191-124">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="b4191-125">Selecteer **Filter toevoegen** voor een bepaald kenmerk op de pagina **Index voor zoeken en filteren**.</span><span class="sxs-lookup"><span data-stu-id="b4191-125">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="b4191-126">U kunt het aantal resultaten en de volgorde waarin deze worden georganiseerd definiëren.</span><span class="sxs-lookup"><span data-stu-id="b4191-126">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="b4191-127">Afhankelijk van het gegevenstype van het kenmerk wordt een van de volgende deelvensters weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b4191-127">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="b4191-128">Kenmerken van het type Tekenreeks: geef het aantal gewenste resultaten op in het deelvenster **Filteropties voor tekenreeksen** en het volgordebeleid waarmee ze worden georganiseerd.</span><span class="sxs-lookup"><span data-stu-id="b4191-128">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="b4191-129">Kenmerken van het type Numeriek: geef de opgenomen intervallen op in het deelvenster **Filteropties voor getallen** en het volgordebeleid waarmee ze worden georganiseerd.</span><span class="sxs-lookup"><span data-stu-id="b4191-129">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="b4191-130">Kenmerken van het type Datum: geef de opgenomen intervallen op in het deelvenster **Filteropties voor datums** en het volgordebeleid waarmee ze worden georganiseerd.</span><span class="sxs-lookup"><span data-stu-id="b4191-130">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="b4191-131">Selecteer **Opslaan** om uw wijzigingen toe te passen.</span><span class="sxs-lookup"><span data-stu-id="b4191-131">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="b4191-132">Selecteer **Uitvoeren** zodra u klaar bent om uw instellingen toe te passen.</span><span class="sxs-lookup"><span data-stu-id="b4191-132">Select **Run** once you're ready to apply your settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b4191-133">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="b4191-133">Next steps</span></span>

<span data-ttu-id="b4191-134">Ga naar de pagina **Klanten** om naar klantprofielen te zoeken of gebruik de geïndexeerde velden om een subset van alle klantprofielen te zien.</span><span class="sxs-lookup"><span data-stu-id="b4191-134">Go to the **Customers** page to search for customer profiles or use the indexed fields to see a subset of all customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]