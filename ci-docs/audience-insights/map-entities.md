---
title: Entiteiten toewijzen voor gegevensharmonisatie
description: Wijs gegevens toe om geharmoniseerde klantprofielen te maken.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: e98c7717f7707d43a9fd1fc6f6b0e9c49e4e7ee0
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405502"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="6b598-103">Entiteiten en attributen toewijzen</span><span class="sxs-lookup"><span data-stu-id="6b598-103">Map entities and attributes</span></span>

<span data-ttu-id="6b598-104">**Toewijzen** is de eerste fase in het gegevensharmonisatieproces van doelgroepinzichten.</span><span class="sxs-lookup"><span data-stu-id="6b598-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="6b598-105">Toewijzing bestaat uit drie fasen:</span><span class="sxs-lookup"><span data-stu-id="6b598-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="6b598-106">*Entiteitsselectie*: identificeer de combineerbare entiteiten die leiden tot een gegevensset met meer volledige informatie over uw klanten.</span><span class="sxs-lookup"><span data-stu-id="6b598-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="6b598-107">*Kenmerkselectie:* identificeer voor elke entiteit de kolommen die u wilt combineren en op elkaar afstemmen in de fasen voor *afstemmen* en *samenvoegen*.</span><span class="sxs-lookup"><span data-stu-id="6b598-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="6b598-108">Deze kolommen worden *Kenmerken* genoemd.</span><span class="sxs-lookup"><span data-stu-id="6b598-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="6b598-109">*Selectie van primaire sleutel en semantisch type*: identificeer voor elke entiteit een kenmerk dat u wilt definiëren als de primaire sleutel voor die entiteit en identificeer voor elk kenmerk een semantisch type dat dit kenmerk het beste beschrijft.</span><span class="sxs-lookup"><span data-stu-id="6b598-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="6b598-110">Zie [Harmoniseren](data-unification.md) voor meer informatie over de algemene stroom van gegevensharmonisatie.</span><span class="sxs-lookup"><span data-stu-id="6b598-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="6b598-111">De eerste entiteiten selecteren</span><span class="sxs-lookup"><span data-stu-id="6b598-111">Select the first entities</span></span>

1. <span data-ttu-id="6b598-112">Ga in doelgroepinzichten naar **Gegevens** > **Unify** > **Toewijzen**.</span><span class="sxs-lookup"><span data-stu-id="6b598-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="6b598-113">Start de toewijzingsfase door **Entiteiten selecteren** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="6b598-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="6b598-114">Selecteer de entiteiten en kenmerken die u wilt gebruiken in de fasen voor *afstemmen* en *samenvoegen*.</span><span class="sxs-lookup"><span data-stu-id="6b598-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="6b598-115">U kunt de vereiste kenmerken van een entiteit afzonderlijk selecteren of alle kenmerken van een entiteit opnemen door het selectievakje **Alle velden opnemen** in te schakelen op entiteitsniveau.</span><span class="sxs-lookup"><span data-stu-id="6b598-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="6b598-116">We raden u aan ten minste twee entiteiten te selecteren om te profiteren van het proces voor gegevensharmonisatie.</span><span class="sxs-lookup"><span data-stu-id="6b598-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6b598-117">![Voorbeeld van toevoegen van entiteiten](media/data-manager-configure-map-add-entities-example.png "Voorbeeld van toevoegen van entiteiten")</span><span class="sxs-lookup"><span data-stu-id="6b598-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="6b598-118">In dit voorbeeld voegen we de entiteiten **eCommerceContacten** en **loyCustomers** toe.</span><span class="sxs-lookup"><span data-stu-id="6b598-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="6b598-119">Door deze entiteiten te kiezen, kunt u inzicht krijgen in welke van de online zakelijke klanten leden van het loyaliteitsprogramma zijn.</span><span class="sxs-lookup"><span data-stu-id="6b598-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="6b598-120">U kunt zoeken op trefwoorden in alle kenmerken en entiteiten om de vereiste kenmerken te selecteren die u wilt toewijzen.</span><span class="sxs-lookup"><span data-stu-id="6b598-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6b598-121">![Voorbeeld van zoekvelden](media/data-manager-configure-map-search-fields-example.png "Voorbeeld van zoekvelden")</span><span class="sxs-lookup"><span data-stu-id="6b598-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="6b598-122">Selecteer **Toepassen** om uw selecties te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="6b598-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="6b598-123">De primaire sleutel en het semantische type voor kenmerken selecteren</span><span class="sxs-lookup"><span data-stu-id="6b598-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="6b598-124">Nadat u uw entiteiten hebt geselecteerd, bevat de pagina **Toewijzen** de geselecteerde entiteiten voor uw beoordeling.</span><span class="sxs-lookup"><span data-stu-id="6b598-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="6b598-125">Definieer de primaire sleutel voor een entiteit en identificeer het semantische type voor een kenmerk in de entiteit.</span><span class="sxs-lookup"><span data-stu-id="6b598-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="6b598-126">**Primaire sleutel**: selecteer één kenmerk als primaire sleutel voor elk van uw entiteiten.</span><span class="sxs-lookup"><span data-stu-id="6b598-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="6b598-127">Als een kenmerk een geldige primaire sleutel is, mag het geen dubbele waarden, ontbrekende waarden of null-waarden bevatten.</span><span class="sxs-lookup"><span data-stu-id="6b598-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="6b598-128">Kenmerken van het gegevenstype tekenreeks, geheel getal en GUID worden ondersteund als primaire sleutels en worden weergegeven in een veld waaruit u kunt kiezen.</span><span class="sxs-lookup"><span data-stu-id="6b598-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="6b598-129">**Semantische type van kenmerk**: categorieën van uw kenmerken, zoals e-mailadres of naam.</span><span class="sxs-lookup"><span data-stu-id="6b598-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="6b598-130">Als u AI-modellen wilt gebruiken voor slimme voorspelling van semantiek, tijdsbesparing en verbeterde nauwkeurigheid, zet u **Intelligente toewijzing** op **AAN**.</span><span class="sxs-lookup"><span data-stu-id="6b598-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="6b598-131">Met Intelligente toewijzing markeert u op AI gebaseerde semantische aanbevelingen in het veld **Type**.</span><span class="sxs-lookup"><span data-stu-id="6b598-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="6b598-132">Als u dit instelt op **UIT**, ziet u onze normale aanbevelingen voor toewijzingen.</span><span class="sxs-lookup"><span data-stu-id="6b598-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="6b598-133">U kunt elk semantisch type uit de beschikbare lijst met opties selecteren en de voorgestelde selectie negeren.</span><span class="sxs-lookup"><span data-stu-id="6b598-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6b598-134">![Kenmerktype en semantische voorspelling](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Kenmerktype en semantische voorspelling")</span><span class="sxs-lookup"><span data-stu-id="6b598-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="6b598-135">Het toevoegen van een aangepast semantisch type is eveneens mogelijk.</span><span class="sxs-lookup"><span data-stu-id="6b598-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="6b598-136">Selecteer het type veld voor een kenmerk en typ de aangepaste naam van het semantische type.</span><span class="sxs-lookup"><span data-stu-id="6b598-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="6b598-137">Zo kunt u ook de kenmerktypen wijzigen die door het systeem zijn geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="6b598-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="6b598-138">Alle kenmerken waarvoor een semantisch type automatisch wordt geïdentificeerd, worden gegroepeerd in de sectie **Toegewezen velden beoordelen**.</span><span class="sxs-lookup"><span data-stu-id="6b598-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="6b598-139">Bekijk deze kenmerken en hun semantische typen, want ze zullen worden gebruikt om uw entiteiten te combineren in de samenvoegstap van gegevensharmonisering.</span><span class="sxs-lookup"><span data-stu-id="6b598-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="6b598-140">Kenmerken die niet automatisch worden toegewezen aan een semantisch type, worden gegroepeerd in de sectie **De gegevens in de niet-toegewezen velden definiëren**.</span><span class="sxs-lookup"><span data-stu-id="6b598-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="6b598-141">Selecteer het semantische typeveld voor de niet-toegewezen kenmerken of voer uw aangepaste naam voor het kenmerktype in.</span><span class="sxs-lookup"><span data-stu-id="6b598-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6b598-142">![Primaire sleutel en kenmerktype](media/data-manager-configure-map-add-attributes.png "Primaire sleutel en kenmerktype")</span><span class="sxs-lookup"><span data-stu-id="6b598-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="6b598-143">Eén veld moet worden toegewezen aan het semantische type Person.FullName om de klantnaam in de klantenkaart te vullen.</span><span class="sxs-lookup"><span data-stu-id="6b598-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="6b598-144">Anders verschijnen de klantenkaarten zonder naam.</span><span class="sxs-lookup"><span data-stu-id="6b598-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="6b598-145">Kenmerken en entiteiten toevoegen en verwijderen</span><span class="sxs-lookup"><span data-stu-id="6b598-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="6b598-146">Selecteer in **Harmoniseren** > **Toewijzen** de optie **Velden bewerken**.</span><span class="sxs-lookup"><span data-stu-id="6b598-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="6b598-147">Voeg in het deelvenster **Velden bewerken** kenmerken en entiteiten toe of verwijder deze.</span><span class="sxs-lookup"><span data-stu-id="6b598-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="6b598-148">Gebruik de zoekopdracht of schuif om de kenmerken en entiteiten waarin u bent interessante te zoeken en te selecteren.</span><span class="sxs-lookup"><span data-stu-id="6b598-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="6b598-149">U kunt een kenmerk of entiteit niet verwijderen als deze al zijn afgestemd.</span><span class="sxs-lookup"><span data-stu-id="6b598-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6b598-150">![Kenmerken toevoegen of verwijderen](media/configure-data-map-edit.png "Kenmerken toevoegen of verwijderen")</span><span class="sxs-lookup"><span data-stu-id="6b598-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="6b598-151">Selecteer **Toepassen**.</span><span class="sxs-lookup"><span data-stu-id="6b598-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="6b598-152">Afbeeldingen toevoegen aan profielen</span><span class="sxs-lookup"><span data-stu-id="6b598-152">Add images to profiles</span></span>

<span data-ttu-id="6b598-153">Als een entiteit URL's bevat naar openbaar beschikbare profielafbeeldingen of logo's, kunt u deze toevoegen aan het geharmoniseerde klantprofiel.</span><span class="sxs-lookup"><span data-stu-id="6b598-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="6b598-154">Selecteer de entiteit en zoek het veld dat de URL naar de profielafbeelding bevat.</span><span class="sxs-lookup"><span data-stu-id="6b598-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="6b598-155">Voer in het invoerveld **Type** handmatig de volgende waarde in:</span><span class="sxs-lookup"><span data-stu-id="6b598-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="6b598-156">Voor een persoon: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="6b598-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="6b598-157">Voor een organisatie: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="6b598-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="6b598-158">Ga verder met de harmoniseringsstappen en zorg ervoor dat het kenmerk dat de afbeeldings-URL bevat ook wordt toegevoegd aan de stap [Samenvoegen](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="6b598-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="6b598-159">Kenmerken instellen voor organisaties</span><span class="sxs-lookup"><span data-stu-id="6b598-159">Set attributes for organizations</span></span>

<span data-ttu-id="6b598-160">Voor organisaties (preview) moet het kenmerktype worden toegewezen aan 'Organization.Name'</span><span class="sxs-lookup"><span data-stu-id="6b598-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="6b598-161">![Primaire sleutel en kenmerktype B2B](media/configure-data-map-edit-b2b.png "Primaire sleutel en kenmerktype B2B")</span><span class="sxs-lookup"><span data-stu-id="6b598-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="6b598-162">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="6b598-162">Next step</span></span>

<span data-ttu-id="6b598-163">Als onderdeel van het proces voor gegevensharmonisatie gaat u naar de pagina **Afstemmen**.</span><span class="sxs-lookup"><span data-stu-id="6b598-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="6b598-164">Bezoek [**Afstemmen**](match-entities.md) voor meer informatie over deze fase.</span><span class="sxs-lookup"><span data-stu-id="6b598-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="6b598-165">Bekijk de volgende video: [Aan de slag: Een geharmoniseerd klantprofiel maken](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="6b598-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>
