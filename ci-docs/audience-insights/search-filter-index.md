---
title: Klantprofielen zoeken en filteren
description: Vind snel informatie over geharmoniseerde klantprofielen en filter op opgegeven kenmerken.
ms.date: 04/16/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1842ad333c23bb155abc89167556163ae79cdd34
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405512"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="4f7c4-103">Klantprofielen: zoek- en filterindex</span><span class="sxs-lookup"><span data-stu-id="4f7c4-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="4f7c4-104">Het resultaat van het harmoniseren van uw klantgegevens is een entiteit Klantprofiel die een geharmoniseerde weergave biedt van uw totale klantenbestand.</span><span class="sxs-lookup"><span data-stu-id="4f7c4-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="4f7c4-105">Als u snel [informatie wilt vinden over een specifieke klant of groep klanten](customer-profiles.md), kunt u de mogelijkheden **Zoeken** en **Filteren** configureren op de pagina **Klanten**.</span><span class="sxs-lookup"><span data-stu-id="4f7c4-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="4f7c4-106">Lees verder om te zien hoe beheerders de kenmerken op de pagina **Index voor zoeken en filteren** kunnen bewerken, die beschikbaar zijn voor gebruikers om te zoeken en te filteren.</span><span class="sxs-lookup"><span data-stu-id="4f7c4-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4f7c4-107">![Zoekfilter](media/search-filter.png "Zoekfilter")</span><span class="sxs-lookup"><span data-stu-id="4f7c4-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="4f7c4-108">Velden toevoegen en kenmerken opgeven</span><span class="sxs-lookup"><span data-stu-id="4f7c4-108">Add fields and specify attributes</span></span>

<span data-ttu-id="4f7c4-109">Als het de eerste keer is dat u doorzoekbare kenmerken definieert als een beheerder, moet u eerst geïndexeerde velden definiëren.</span><span class="sxs-lookup"><span data-stu-id="4f7c4-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="4f7c4-110">We raden u aan alle kenmerken te kiezen waarmee gebruikers klanten kunnen zoeken en filteren op de pagina **Klanten**.</span><span class="sxs-lookup"><span data-stu-id="4f7c4-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="4f7c4-111">U kunt alleen kenmerken opgeven die bestaan in de entiteit Klantprofiel die u tijdens het gegevensharmonisatieproces hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="4f7c4-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="4f7c4-112">Open de pagina **Klanten** en selecteer **Zoek- en filterindex**.</span><span class="sxs-lookup"><span data-stu-id="4f7c4-112">Open the **Customers** page and select **Search & filter index**.</span></span>

> [!NOTE]
> <span data-ttu-id="4f7c4-113">We maken een standaard zoekindexconfiguratie op de beschikbare kenmerken in de klantentiteit van de volgende semantische typen zoals gedefinieerd op de pagina Toewijzing.</span><span class="sxs-lookup"><span data-stu-id="4f7c4-113">We create a default search index configuration on the available attributes in the Customer entity from the following semantic types as defined on the Map page.</span></span>
> - <span data-ttu-id="4f7c4-114">Voornaam, Achternaam, Middelste naam, Volledige naam van persoon</span><span class="sxs-lookup"><span data-stu-id="4f7c4-114">Person First name, Last name, Middle name, Full Name</span></span>
> - <span data-ttu-id="4f7c4-115">Organisatienaam</span><span class="sxs-lookup"><span data-stu-id="4f7c4-115">Organization Name</span></span>
> - <span data-ttu-id="4f7c4-116">E-mailadres</span><span class="sxs-lookup"><span data-stu-id="4f7c4-116">Email address</span></span>
> - <span data-ttu-id="4f7c4-117">Telefoonnummer</span><span class="sxs-lookup"><span data-stu-id="4f7c4-117">Phone number</span></span>
> - <span data-ttu-id="4f7c4-118">Locatiegegevens</span><span class="sxs-lookup"><span data-stu-id="4f7c4-118">Location information</span></span>

2. <span data-ttu-id="4f7c4-119">Selecteer **+ Toevoegen** om de geïndexeerde velden op te geven.</span><span class="sxs-lookup"><span data-stu-id="4f7c4-119">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="4f7c4-120">Selecteer de kenmerken in de lijst die u als geïndexeerde velden wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="4f7c4-120">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="4f7c4-121">U kunt altijd meer kenmerken toevoegen door **Toevoegen** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="4f7c4-121">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="4f7c4-122">U kunt ook alle geselecteerde kenmerken verwijderen door het symbool **Verwijderen** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="4f7c4-122">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="4f7c4-123">De tabel Geïndexeerde klantvelden verkennen</span><span class="sxs-lookup"><span data-stu-id="4f7c4-123">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="4f7c4-124">De volgende informatie wordt weergegeven in de tabel.</span><span class="sxs-lookup"><span data-stu-id="4f7c4-124">The following information is presented in the table.</span></span>

- <span data-ttu-id="4f7c4-125">**Naam**: vertegenwoordigt de naam van het kenmerk zoals deze wordt weergegeven in de entiteit Klantprofiel.</span><span class="sxs-lookup"><span data-stu-id="4f7c4-125">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="4f7c4-126">**Gegevenstype**: geeft aan of het gegevenstype een tekenreeks, een getal of een datum is.</span><span class="sxs-lookup"><span data-stu-id="4f7c4-126">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="4f7c4-127">**Opgenomen in zoekactie**: geeft aan of dit kenmerk kan worden gebruikt om te zoeken naar klanten op de pagina **Klanten** met het veld **Zoeken**.</span><span class="sxs-lookup"><span data-stu-id="4f7c4-127">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="4f7c4-128">**Filter toevoegen**: besturingselement om te definiëren hoe dit kenmerk kan worden gebruikt voor het filteren op de pagina **Klanten**.</span><span class="sxs-lookup"><span data-stu-id="4f7c4-128">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="4f7c4-129">Filteropties voor een bepaald kenmerk bewerken</span><span class="sxs-lookup"><span data-stu-id="4f7c4-129">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="4f7c4-130">Het menu **Filteren** op de pagina **Klanten** kan een verschillend aantal kenmerkniveaus bevatten (bijvoorbeeld verschillende leeftijdsgroepen om klanten op te filteren).</span><span class="sxs-lookup"><span data-stu-id="4f7c4-130">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="4f7c4-131">Selecteer **Filter toevoegen** voor een bepaald kenmerk op de pagina **Index voor zoeken en filteren**.</span><span class="sxs-lookup"><span data-stu-id="4f7c4-131">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="4f7c4-132">U kunt het aantal resultaten en de volgorde waarin deze worden georganiseerd definiëren.</span><span class="sxs-lookup"><span data-stu-id="4f7c4-132">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="4f7c4-133">Afhankelijk van het gegevenstype van het kenmerk wordt een van de volgende deelvensters weergegeven.</span><span class="sxs-lookup"><span data-stu-id="4f7c4-133">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="4f7c4-134">Kenmerken van het type Tekenreeks: geef het aantal gewenste resultaten op in het deelvenster **Filteropties voor tekenreeksen** en het volgordebeleid waarmee ze worden georganiseerd.</span><span class="sxs-lookup"><span data-stu-id="4f7c4-134">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="4f7c4-135">Kenmerken van het type Numeriek: geef de opgenomen intervallen op in het deelvenster **Filteropties voor getallen** en het volgordebeleid waarmee ze worden georganiseerd.</span><span class="sxs-lookup"><span data-stu-id="4f7c4-135">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="4f7c4-136">Kenmerken van het type Datum: geef de opgenomen intervallen op in het deelvenster **Filteropties voor datums** en het volgordebeleid waarmee ze worden georganiseerd.</span><span class="sxs-lookup"><span data-stu-id="4f7c4-136">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="4f7c4-137">Selecteer **Opslaan** om uw wijzigingen toe te passen.</span><span class="sxs-lookup"><span data-stu-id="4f7c4-137">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="4f7c4-138">Selecteer **Uitvoeren** zodra u klaar bent om uw instellingen toe te passen.</span><span class="sxs-lookup"><span data-stu-id="4f7c4-138">Select **Run** once you're ready to apply your settings.</span></span>
