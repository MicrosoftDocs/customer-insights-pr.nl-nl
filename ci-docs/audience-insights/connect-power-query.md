---
title: Gegevens opnemen via een Power Query-connector
description: Connectors voor databronnen op basis van Power Query.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8a170cc5b64b4b383501021232c83948e838a0e2
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405489"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="46b61-103">Verbinden met een Power Query-gegevensbron</span><span class="sxs-lookup"><span data-stu-id="46b61-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="46b61-104">Power Query biedt een brede set connectors om gegevens op te nemen.</span><span class="sxs-lookup"><span data-stu-id="46b61-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="46b61-105">De meeste van deze connectors worden ondersteund door Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="46b61-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="46b61-106">Bij het toevoegen van gegevensbronnen op basis van Power Query-connectors worden gewoonlijk de stappen gevolgd die in de volgende sectie worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="46b61-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="46b61-107">Afhankelijk van de connector die u gebruikt, kan echter andere informatie vereist zijn.</span><span class="sxs-lookup"><span data-stu-id="46b61-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="46b61-108">Zie voor meer informatie de documentatie over afzonderlijke connectors in [Referentie voor Power Query-connectors](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="46b61-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="46b61-109">Een nieuwe gegevensbron maken</span><span class="sxs-lookup"><span data-stu-id="46b61-109">Create a new data source</span></span>

1. <span data-ttu-id="46b61-110">Ga in doelgroepinzichten naar **Gegevens** > **Gegevensbronnen**.</span><span class="sxs-lookup"><span data-stu-id="46b61-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="46b61-111">Selecteer **Gegevensbron toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="46b61-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="46b61-112">Kies de methode **Gegevens importeren** en selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="46b61-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="46b61-113">Geef een **Naam** op voor de gegevensbron en selecteer **Volgende** om de gegevensbron te maken.</span><span class="sxs-lookup"><span data-stu-id="46b61-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span>

1. <span data-ttu-id="46b61-114">Kies een van de [beschikbare connectors](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="46b61-114">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="46b61-115">Voor dit voorbeeld selecteren we de connector **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="46b61-115">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="46b61-116">Voer de vereiste gegevens in voor de **Verbindingsinstellingen** voor de geselecteerde connector en selecteer **Volgende** om een voorbeeld van de gegevens te zien.</span><span class="sxs-lookup"><span data-stu-id="46b61-116">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="46b61-117">Selecteer **Gegevens transformeren**.</span><span class="sxs-lookup"><span data-stu-id="46b61-117">Select **Transform data**.</span></span> <span data-ttu-id="46b61-118">In deze stap voegt u entiteiten toe aan uw gegevensbron.</span><span class="sxs-lookup"><span data-stu-id="46b61-118">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="46b61-119">Entiteiten zijn gegevenssets.</span><span class="sxs-lookup"><span data-stu-id="46b61-119">Entities are datasets.</span></span> <span data-ttu-id="46b61-120">Als u een database hebt die meerdere gegevenssets bevat, is elke gegevensset zijn eigen entiteit.</span><span class="sxs-lookup"><span data-stu-id="46b61-120">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="46b61-121">In het dialoogvenster **Power Query - Query's bewerken** kunt u de gegevens bekijken en verfijnen.</span><span class="sxs-lookup"><span data-stu-id="46b61-121">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="46b61-122">De entiteiten die de systemen in uw geselecteerde gegevensbron hebben geïdentificeerd, verschijnen in het linkerdeelvenster.</span><span class="sxs-lookup"><span data-stu-id="46b61-122">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="46b61-123">![Dialoogvenster Query's bewerken](media/data-manager-configure-edit-queries.png "Dialoogvenster Query's bewerken")</span><span class="sxs-lookup"><span data-stu-id="46b61-123">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="46b61-124">U kunt uw gegevens ook transformeren.</span><span class="sxs-lookup"><span data-stu-id="46b61-124">You can also transform your data.</span></span> <span data-ttu-id="46b61-125">Selecteer een entiteit om te bewerken of transformeren.</span><span class="sxs-lookup"><span data-stu-id="46b61-125">Select an entity to edit or transform.</span></span> <span data-ttu-id="46b61-126">Gebruik de opties in het venster Power Query om transformaties toe te passen.</span><span class="sxs-lookup"><span data-stu-id="46b61-126">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="46b61-127">Elke transformatie wordt vermeld onder **Toegepaste stappen**.</span><span class="sxs-lookup"><span data-stu-id="46b61-127">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="46b61-128">Power Query biedt tal van vooraf gebouwde transformatie-opties.</span><span class="sxs-lookup"><span data-stu-id="46b61-128">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="46b61-129">Zie [Power Query-transformaties](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="46b61-129">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="46b61-130">U kunt extra entiteiten toevoegen aan uw gegevensbron door **Gegevens ophalen** te selecteren in het dialoogvenster **Query's bewerken**.</span><span class="sxs-lookup"><span data-stu-id="46b61-130">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="46b61-131">Deze transformaties worden sterk aanbevolen:</span><span class="sxs-lookup"><span data-stu-id="46b61-131">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="46b61-132">Als u gegevens opneemt uit een CSV-bestand, bevat de eerste rij vaak kopteksten.</span><span class="sxs-lookup"><span data-stu-id="46b61-132">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="46b61-133">Ga naar **Tabel transformeren** en selecteer **Gebruik kopteksten als eerste rij**.</span><span class="sxs-lookup"><span data-stu-id="46b61-133">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="46b61-134">Zorg ervoor dat het gegevenstype correct is ingesteld.</span><span class="sxs-lookup"><span data-stu-id="46b61-134">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="46b61-135">Selecteer **Opslaan** onderin het venster Power Query om de transformaties op te slaan.</span><span class="sxs-lookup"><span data-stu-id="46b61-135">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="46b61-136">Nadat u hebt opgeslagen, ziet u gegevensbron onder **Gegevens** > **Gegevensbronnen**.</span><span class="sxs-lookup"><span data-stu-id="46b61-136">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="46b61-137">Op de pagina **Gegevensbronen** ziet u dat de nieuwe gegevensbron de status **Vernieuwen** heeft.</span><span class="sxs-lookup"><span data-stu-id="46b61-137">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="46b61-138">Beschikbare Power Query-gegevensbronnen</span><span class="sxs-lookup"><span data-stu-id="46b61-138">Available Power Query data sources</span></span>

<span data-ttu-id="46b61-139">Zie [Referentie voor Power Query-connectors](https://docs.microsoft.com/power-query/connectors/) voor een up-to-date lijst met connectors die u kunt selecteren om gegevens te importeren in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="46b61-139">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="46b61-140">Connectors met een vinkje in de kolom **Customer Insights (gegevensstromen)** zijn beschikbaar om nieuwe gegevensbronnen te maken op basis van Power Query.</span><span class="sxs-lookup"><span data-stu-id="46b61-140">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="46b61-141">Bekijk de documentatie van een specifieke connector voor meer informatie over de vereisten, beperkingen en andere details.</span><span class="sxs-lookup"><span data-stu-id="46b61-141">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="46b61-142">Power Query-gegevensbronnen bewerken</span><span class="sxs-lookup"><span data-stu-id="46b61-142">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="46b61-143">Het is misschien niet mogelijk om wijzigingen aan te brengen in gegevensbronnen die momenteel worden gebruikt in een van de processen van de app (bijvoorbeeld *segmentatie*, *afstemming* of *samenvoeging*).</span><span class="sxs-lookup"><span data-stu-id="46b61-143">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="46b61-144">Met de pagina **Instellingen** kunt u de voortgang van elk van de actieve processen volgen.</span><span class="sxs-lookup"><span data-stu-id="46b61-144">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="46b61-145">Wanneer een proces is voltooid, kunt u terugkeren naar de pagina **Gegevensbronnen** en uw wijzigingen aanbrengen.</span><span class="sxs-lookup"><span data-stu-id="46b61-145">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="46b61-146">Ga in doelgroepinzichten naar **Gegevens** > **Gegevensbronnen**.</span><span class="sxs-lookup"><span data-stu-id="46b61-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="46b61-147">Selecteer het verticale weglatingsteken naast de gegevensbron die u wilt wijzigen en selecteer **Bewerken** uit het vervolgkeuzemenu.</span><span class="sxs-lookup"><span data-stu-id="46b61-147">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="46b61-148">![Optie bewerken](media/edit-option-data-sources.png "Optie bewerken")</span><span class="sxs-lookup"><span data-stu-id="46b61-148">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="46b61-149">Pas uw wijzigingen en transformaties toe in het dialoogvenster **Power Query - Query's bewerken** zoals beschreven in de sectie [Een nieuwe gegevensbron maken](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="46b61-149">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="46b61-150">Selecteer **Opslaan** in Power Query na het voltooien van uw bewerkingen om uw wijzigingen op te slaan.</span><span class="sxs-lookup"><span data-stu-id="46b61-150">Select **Save** in Power Query after completing your edits to save your changes.</span></span>
