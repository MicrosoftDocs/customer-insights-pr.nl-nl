---
title: Exportbestemmingen
description: Gegevens exporteren en exportbestemmingen beheren.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643857"
---
# <a name="export-destinations-preview"></a><span data-ttu-id="c577f-103">Exportbestemmingen (voorbeeld)</span><span class="sxs-lookup"><span data-stu-id="c577f-103">Export destinations (preview)</span></span>

<span data-ttu-id="c577f-104">De pagina **Exportbestemmingen** bevat alle locaties die u hebt ingesteld om gegevens naar te exporteren.</span><span class="sxs-lookup"><span data-stu-id="c577f-104">The **Export destinations** page shows you all locations you've set up to export data to.</span></span> <span data-ttu-id="c577f-105">U kunt ook nieuwe bestemmingen toevoegen voor export.</span><span class="sxs-lookup"><span data-stu-id="c577f-105">You can also add new destinations for export.</span></span> <span data-ttu-id="c577f-106">Hierin worden verder de momenteel beschikbare exportopties weergegeven.</span><span class="sxs-lookup"><span data-stu-id="c577f-106">Additionally, it shows export currently available options.</span></span> <span data-ttu-id="c577f-107">Krijg een snel overzicht, een beschrijving en ontdek wat u kunt doen met elke uitbreidingsoptie.</span><span class="sxs-lookup"><span data-stu-id="c577f-107">Get a quick overview, description, and find out what you can do with each extensibility option.</span></span> <span data-ttu-id="c577f-108">Exporteer uniforme profielen, meetwaarden en segmenten naar ondersteunde apps die relevant zijn voor uw bedrijf.</span><span class="sxs-lookup"><span data-stu-id="c577f-108">Export unified profiles, measures, and segments to supported apps relevant for your business.</span></span>

<span data-ttu-id="c577f-109">Ga naar **Beheer** > **Exportbestemmingen** om de volgende uitbreidingsopties te vinden:</span><span class="sxs-lookup"><span data-stu-id="c577f-109">Go to **Admin** > **Export destinations** to find the following extensibility options:</span></span>

- [<span data-ttu-id="c577f-110">Invoegtoepassing Dynamics 365-klantkaart</span><span class="sxs-lookup"><span data-stu-id="c577f-110">Dynamics 365 Customer Card Add-in</span></span>](customer-card-add-in.md)
- [<span data-ttu-id="c577f-111">Facebook Ads Manager-connector</span><span class="sxs-lookup"><span data-stu-id="c577f-111">Facebook Ads Manager connector</span></span>](export-facebook.md)
- [<span data-ttu-id="c577f-112">Power Automate-connector</span><span class="sxs-lookup"><span data-stu-id="c577f-112">Power Automate connector</span></span>](export-power-automate.md)
- [<span data-ttu-id="c577f-113">Power Apps-connector</span><span class="sxs-lookup"><span data-stu-id="c577f-113">Power Apps connector</span></span>](export-power-apps.md)
- [<span data-ttu-id="c577f-114">Power BI-connector</span><span class="sxs-lookup"><span data-stu-id="c577f-114">Power BI connector</span></span>](export-power-bi.md)
- [<span data-ttu-id="c577f-115">DotDigital</span><span class="sxs-lookup"><span data-stu-id="c577f-115">DotDigital</span></span>](export-dotdigital.md)
- [<span data-ttu-id="c577f-116">Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="c577f-116">Dynamics 365 Sales</span></span>](export-dynamics365-sales.md)
- [<span data-ttu-id="c577f-117">Dynamics 365 Marketing</span><span class="sxs-lookup"><span data-stu-id="c577f-117">Dynamics 365 Marketing</span></span>](export-dynamics365-marketing.md)
- [<span data-ttu-id="c577f-118">Azure Blob-opslag</span><span class="sxs-lookup"><span data-stu-id="c577f-118">Azure Blob Storage</span></span>](export-azure-blob-storage.md)
- [<span data-ttu-id="c577f-119">LiveRamp&reg;-connector</span><span class="sxs-lookup"><span data-stu-id="c577f-119">LiveRamp&reg; connector</span></span>](export-liveramp.md)
- [<span data-ttu-id="c577f-120">Bot voor Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c577f-120">Bot for Microsoft Teams</span></span>](export-teams-bot.md)
- [<span data-ttu-id="c577f-121">Mailchimp</span><span class="sxs-lookup"><span data-stu-id="c577f-121">Mailchimp</span></span>](export-mailchimp.md)
- [<span data-ttu-id="c577f-122">Customer Insights-API</span><span class="sxs-lookup"><span data-stu-id="c577f-122">Customer Insights API</span></span>](apis.md)

## <a name="add-a-new-export-destination"></a><span data-ttu-id="c577f-123">Een nieuwe exportbestemming toevoegen</span><span class="sxs-lookup"><span data-stu-id="c577f-123">Add a new export destination</span></span>

<span data-ttu-id="c577f-124">Om exportbestemmingen toe te voegen, hebt u [Beheerdersmachtigingen](permissions.md) nodig.</span><span class="sxs-lookup"><span data-stu-id="c577f-124">To add export destinations, you have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="c577f-125">Als u exporteert naar Microsoft-services, gaan we ervan uit dat beide services zich in dezelfde organisatie bevinden.</span><span class="sxs-lookup"><span data-stu-id="c577f-125">If you export to Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="c577f-126">Ga naar **Beheer** > **Exportbestemmingen**.</span><span class="sxs-lookup"><span data-stu-id="c577f-126">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c577f-127">Schakel over naar het tabblad **Mijn exportbestemmingen**.</span><span class="sxs-lookup"><span data-stu-id="c577f-127">Switch to the **My export destinations** tab.</span></span>

1. <span data-ttu-id="c577f-128">Selecteer **Bestemming toevoegen** om een nieuwe exportbestemming te maken.</span><span class="sxs-lookup"><span data-stu-id="c577f-128">Select **Add destination** to create a new export destination.</span></span>

1. <span data-ttu-id="c577f-129">Selecteer in het deelvenster **Bestemming toevoegen** het **Type** exportbestemming in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="c577f-129">In the **Add destination** pane, select the **Type** of export destination in the drop-down.</span></span>

1. <span data-ttu-id="c577f-130">Geef de vereiste details op en selecteer **Volgende** om de exportbestemming te maken.</span><span class="sxs-lookup"><span data-stu-id="c577f-130">Provide the required details and select **Next** to create the export destination.</span></span>

<span data-ttu-id="c577f-131">U kunt ook **Instellen** selecteren op een tegel op het tabblad **Ontdekken**.</span><span class="sxs-lookup"><span data-stu-id="c577f-131">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

## <a name="view-export-destinations"></a><span data-ttu-id="c577f-132">Exportbestemmingen weergeven</span><span class="sxs-lookup"><span data-stu-id="c577f-132">View Export destinations</span></span>

<span data-ttu-id="c577f-133">Nadat u exportbestemmingen hebt gemaakt, vindt u deze in een tabel op het tabblad **Mijn exportbestemmingen**. Deze tabel heeft drie kolommen:</span><span class="sxs-lookup"><span data-stu-id="c577f-133">After creating export destinations, you'll find them in a table on the **My export destinations** tab. This table has three columns:</span></span>

- <span data-ttu-id="c577f-134">**Weergavenaam**: de naam die u hebt ingevoerd bij het maken van de bestemming.</span><span class="sxs-lookup"><span data-stu-id="c577f-134">**Display name**: The name you entered when creating the destination.</span></span>
- <span data-ttu-id="c577f-135">**Type**: het type exportbestemming dat u hebt ingesteld bij het maken van de bestemming.</span><span class="sxs-lookup"><span data-stu-id="c577f-135">**Type**: The export destination type you set when creating the destination.</span></span>
- <span data-ttu-id="c577f-136">**Gemaakt**: de datum waarop de bestemming is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="c577f-136">**Created**: The date you created the destination.</span></span>

## <a name="edit-an-export-destination"></a><span data-ttu-id="c577f-137">Een exportbestemming bewerken</span><span class="sxs-lookup"><span data-stu-id="c577f-137">Edit an export destination</span></span>

1. <span data-ttu-id="c577f-138">Selecteer het verticale weglatingsteken voor de exportbestemming die u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="c577f-138">Select the vertical ellipsis for the Export destination you want to edit.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c577f-139">![Verticaal weglatingsteken](media/export-destinations-page-ellipsis.png "Verticaal weglatingsteken")</span><span class="sxs-lookup"><span data-stu-id="c577f-139">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

1. <span data-ttu-id="c577f-140">Selecteer **Bewerken** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="c577f-140">Select **Edit** from the dropdown menu.</span></span>

1. <span data-ttu-id="c577f-141">Wijzig de waarden die moeten worden bijgewerkt en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="c577f-141">Change the values that require update and select **Save**.</span></span>

## <a name="export-data-on-demand"></a><span data-ttu-id="c577f-142">Gegevens op aanvraag exporteren</span><span class="sxs-lookup"><span data-stu-id="c577f-142">Export data on demand</span></span>

<span data-ttu-id="c577f-143">Na het configureren van een connector voor een exportbestemming, worden exports uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c577f-143">After configuring a connector for an export destination, exports will run with every [scheduled refresh](system.md#schedule-tab).</span></span>

<span data-ttu-id="c577f-144">Als u gegevens wilt exporteren zonder te wachten op een geplande vernieuwing, gaat u naar het tabblad **Mijn exportbestemmingen** onder **Beheer** > **Exportbestemmingen**.</span><span class="sxs-lookup"><span data-stu-id="c577f-144">To export data without waiting for a scheduled refresh, go the **My export destinations** tab on **Admin** > **Export destinations**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c577f-145">![Verticaal weglatingsteken](media/export-destinations-page-ellipsis.png "Verticaal weglatingsteken")</span><span class="sxs-lookup"><span data-stu-id="c577f-145">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

- <span data-ttu-id="c577f-146">Selecteer **Exporteren** boven de lijst om de export uit te voeren naar alle exportbestemmingen tegelijk.</span><span class="sxs-lookup"><span data-stu-id="c577f-146">Select **Export** above the list to run the export to all export destinations simultaneously.</span></span>
- <span data-ttu-id="c577f-147">Selecteer het beletselteken (...) na een lijstitem en kies vervolgens de optie **Exporteren** om de export uit te voeren voor een enkele exportbestemming.</span><span class="sxs-lookup"><span data-stu-id="c577f-147">Select the ellipsis (...) after a list item and then choose the **Export** option to run the export for a single export destination.</span></span>

## <a name="remove-an-export-destination"></a><span data-ttu-id="c577f-148">Exportbestemming verwijderen</span><span class="sxs-lookup"><span data-stu-id="c577f-148">Remove an Export destination</span></span>

<span data-ttu-id="c577f-149">Als u een exportbestemming wilt verwijderen, begint u op de pagina **Exportbestemmingen**.</span><span class="sxs-lookup"><span data-stu-id="c577f-149">To remove an Export destination, start from the main **Export destinations** page.</span></span>

1. <span data-ttu-id="c577f-150">Selecteer het verticale weglatingsteken voor de exportbestemming die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="c577f-150">Select the vertical ellipsis for the Export destination you want to remove.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c577f-151">![Verticaal weglatingsteken](media/export-destinations-page-ellipsis.png "Verticaal weglatingsteken")</span><span class="sxs-lookup"><span data-stu-id="c577f-151">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

2. <span data-ttu-id="c577f-152">Selecteer **Verwijderen** in het vervolgkeuzemenu.</span><span class="sxs-lookup"><span data-stu-id="c577f-152">Select **Remove** from the dropdown menu.</span></span>

3. <span data-ttu-id="c577f-153">Bevestig de verwijdering door **Verwijderen** te selecteren op het bevestigingsscherm.</span><span class="sxs-lookup"><span data-stu-id="c577f-153">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>
