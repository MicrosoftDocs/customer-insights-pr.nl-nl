---
title: Voorgestelde segmenten op basis van activiteit.
description: Laat Machine Learning u helpen nieuwe en interessante segmenten te vinden op basis van klantactiviteit.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034063"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="708b6-103">Voorgestelde segmenten op basis van activiteitsgegevens (preview)</span><span class="sxs-lookup"><span data-stu-id="708b6-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="708b6-104">Ontdek interessante segmenten van uw klanten op basis van klantactiviteitsgegevens die worden opgenomen in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="708b6-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="708b6-105">Voorbeelden van activiteitsgegevens zijn transacties, duur van ondersteuningsgesprekken, aankopen of retouren.</span><span class="sxs-lookup"><span data-stu-id="708b6-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="708b6-106">Als u segmenten wilt voorstellen, worden activiteitsgegevens geanalyseerd op recentheid, frequentie en geldwaarde (of duur).</span><span class="sxs-lookup"><span data-stu-id="708b6-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="708b6-107">Als alternatief kunt u [voorgestelde segmenten genereren om een meting te verbeteren of om beter te begrijpen waardoor een kenmerk wordt beïnvloed](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="708b6-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Tabblad Voorgestelde segmenten met segmentsuggesties voor op activiteit gebaseerde en kenmerkgebaseerde segmenten.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="708b6-109">Klanten op activiteit categoriseren</span><span class="sxs-lookup"><span data-stu-id="708b6-109">Categorize customers by activity</span></span>

<span data-ttu-id="708b6-110">Met [activiteitsgegevens](activities.md) die beschikbaar zijn in Customer Insights, kunnen we suggesties genereren die klantgroepen vertegenwoordigen:</span><span class="sxs-lookup"><span data-stu-id="708b6-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="708b6-111">meest actieve klanten</span><span class="sxs-lookup"><span data-stu-id="708b6-111">most active customers</span></span> 
- <span data-ttu-id="708b6-112">klanten die de meeste aankopen hebben gedaan</span><span class="sxs-lookup"><span data-stu-id="708b6-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="708b6-113">klanten die de meeste inkomsten hebben gegenereerd</span><span class="sxs-lookup"><span data-stu-id="708b6-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="708b6-114">klanten die de laatste tijd niet actief zijn geweest</span><span class="sxs-lookup"><span data-stu-id="708b6-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="708b6-115">klanten die regelmatig contact hebben met uw bedrijf</span><span class="sxs-lookup"><span data-stu-id="708b6-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="708b6-116">Als u een detailhandel hebt, kunt u erachter komen welke klanten de meeste inkomsten genereren en hen belonen met een kortingsbon.</span><span class="sxs-lookup"><span data-stu-id="708b6-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="708b6-117">Of u kunt incidentele klanten identificeren en hen aanbieden om deel te nemen aan een beloningsprogramma, zodat ze uw bedrijf vaker bezoeken.</span><span class="sxs-lookup"><span data-stu-id="708b6-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="708b6-118">Als u in de gezondheidszorg werkt en het uw doel is om de kosten voor individuele patiënten te minimaliseren.</span><span class="sxs-lookup"><span data-stu-id="708b6-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="708b6-119">Een manier zou zijn om het aantal terugkerende bezoeken terug te brengen door in zo min mogelijk bezoeken de best mogelijke zorg te bieden.</span><span class="sxs-lookup"><span data-stu-id="708b6-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="708b6-120">In dit geval is het uw doel om de bezoekfrequentie laag te houden en terugkerende kosten voor de patiënten te minimaliseren.</span><span class="sxs-lookup"><span data-stu-id="708b6-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="708b6-121">Of u kunt segmenten van patiënten identificeren die frequente afspraken en hoge terugkerende kosten hebben en deze gevallen analyseren om de behandeling van het individu te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="708b6-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="708b6-122">Vereiste gegevens</span><span class="sxs-lookup"><span data-stu-id="708b6-122">Required data</span></span>

<span data-ttu-id="708b6-123">Suggesties worden gegenereerd op basis van de geselecteerde invoergegevens.</span><span class="sxs-lookup"><span data-stu-id="708b6-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="708b6-124">Klantprofielen: alle klanten of leden van een specifiek segment.</span><span class="sxs-lookup"><span data-stu-id="708b6-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="708b6-125">Tijdsperiode: vorige maand, vorig jaar of een aangepast tijdsbestek.</span><span class="sxs-lookup"><span data-stu-id="708b6-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="708b6-126">Type activiteit: aankopen, detailhandelstransacties, online transacties, klantondersteuningsgevallen, abonnementen, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="708b6-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="708b6-127">Entiteit in Customer Insights die de activiteitsgegevens bevat: de UnifiedActivity-entiteit of de entiteit voor een specifieke activiteit.</span><span class="sxs-lookup"><span data-stu-id="708b6-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="708b6-128">Op te nemen dimensies: recentheid, frequentie of geldelijke dimensie, afhankelijk van uw zakelijke vereisten.</span><span class="sxs-lookup"><span data-stu-id="708b6-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="708b6-129">Voorgestelde segmenten genereren</span><span class="sxs-lookup"><span data-stu-id="708b6-129">Generate suggested segments</span></span>

1. <span data-ttu-id="708b6-130">Ga naar **Segmenten**.</span><span class="sxs-lookup"><span data-stu-id="708b6-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="708b6-131">Selecteer het tabblad **Suggesties (preview)**.</span><span class="sxs-lookup"><span data-stu-id="708b6-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="708b6-132">Selecteer **Nieuwe suggesties zoeken** en kies **Klantgedrag bekijken of erop anticiperen**.</span><span class="sxs-lookup"><span data-stu-id="708b6-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="708b6-133">Selecteer **Starten** om de begeleide ervaring uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="708b6-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Eerste stap van de configuratiewizard voor een voorgesteld segment op basis van activiteit.":::

1. <span data-ttu-id="708b6-135">Geef de vereiste invoergegevens op en selecteer **Volgende** om door te gaan.</span><span class="sxs-lookup"><span data-stu-id="708b6-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="708b6-136">Kies klanten: neem alle klanten of een specifiek segment op.</span><span class="sxs-lookup"><span data-stu-id="708b6-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="708b6-137">Kies activiteit: selecteer het activiteitstype en de entiteiten die de activiteit beschrijven.</span><span class="sxs-lookup"><span data-stu-id="708b6-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="708b6-138">Voorkeuren: stel de te overwegen tijdsperiode in, de factoren voor suggesties en breng de kenmerken in kaart.</span><span class="sxs-lookup"><span data-stu-id="708b6-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="708b6-139">Controleer uw invoer en selecteer **Uitvoeren** om het model uit te voeren en suggesties te genereren.</span><span class="sxs-lookup"><span data-stu-id="708b6-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="708b6-140">Afhankelijk van het aantal klantprofielen en geselecteerde activiteiten kan het voltooien enkele minuten duren.</span><span class="sxs-lookup"><span data-stu-id="708b6-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="708b6-141">Nadat u de suggesties hebt gegenereerd, kunt u ze filteren op de dimensie of waarde waarin u het meest geïnteresseerd bent.</span><span class="sxs-lookup"><span data-stu-id="708b6-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="708b6-142">Details van een voorgesteld segment weergeven</span><span class="sxs-lookup"><span data-stu-id="708b6-142">View details of a suggested segment</span></span>

<span data-ttu-id="708b6-143">Zodra de suggesties zijn gegenereerd, vindt u ze vermeld in **Segmenten** > **Suggesties (preview)** in de sectie **Op activiteiten gebaseerde suggesties**.</span><span class="sxs-lookup"><span data-stu-id="708b6-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Uitgebreid zijvenster met gedetailleerde gegevens van een voorgesteld segment.":::

<span data-ttu-id="708b6-145">Selecteer **Suggestie bekijken** in een voorgesteld segment om de details van dat segment te bekijken.</span><span class="sxs-lookup"><span data-stu-id="708b6-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="708b6-146">Het zijvenster bevat details zoals de omvang van elke dimensie in vergelijking met de doelgroep.</span><span class="sxs-lookup"><span data-stu-id="708b6-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="708b6-147">Het benadrukt ook het aantal potentiële leden in het segment en het overeenkomstige percentage van de totale klanten.</span><span class="sxs-lookup"><span data-stu-id="708b6-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="708b6-148">Als u de suggestie als segment wilt behouden, selecteert u **Segment maken**.</span><span class="sxs-lookup"><span data-stu-id="708b6-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="708b6-149">Een suggestie als een segment opslaan</span><span class="sxs-lookup"><span data-stu-id="708b6-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="708b6-150">Ga naar **Segmenten** > **Suggesties (preview)** ​.</span><span class="sxs-lookup"><span data-stu-id="708b6-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="708b6-151">Selecteer het segment dat u wilt opslaan.</span><span class="sxs-lookup"><span data-stu-id="708b6-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="708b6-152">Selecteer in het zijvenster **Segment maken**.</span><span class="sxs-lookup"><span data-stu-id="708b6-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="708b6-153">Nadat het segment is opgeslagen, wordt het weergegeven in de lijst met segmenten op het tabblad **Alle segmenten**. Het kan nu worden [vernieuwd of verwijderd zoals elk ander segment ](segments.md).</span><span class="sxs-lookup"><span data-stu-id="708b6-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="708b6-154">U kunt de segmentdetails niet bewerken.</span><span class="sxs-lookup"><span data-stu-id="708b6-154">You can't edit the segment details.</span></span> <span data-ttu-id="708b6-155">U kunt echter de invoercriteria voor de suggesties wijzigen en verschillende suggesties genereren.</span><span class="sxs-lookup"><span data-stu-id="708b6-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="708b6-156">Een reeks suggesties vernieuwen of bewerken</span><span class="sxs-lookup"><span data-stu-id="708b6-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="708b6-157">Ga naar **Segmenten** > **Suggesties (preview)** en zoek het segment in de sectie **Op activiteiten gebaseerde suggesties**.</span><span class="sxs-lookup"><span data-stu-id="708b6-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="708b6-158">Selecteer **Suggesties vernieuwen** om de suggesties te vernieuwen en tegelijk de geconfigureerde kenmerken te behouden.</span><span class="sxs-lookup"><span data-stu-id="708b6-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="708b6-159">Of selecteer **Suggesties bewerken** om de geconfigureerde kenmerken te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="708b6-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="708b6-160">Het proces wordt opnieuw uitgevoerd, segmentsuggesties worden gegenereerd op basis van de nieuwste gegevens en de huidige suggesties worden vervangen.</span><span class="sxs-lookup"><span data-stu-id="708b6-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
