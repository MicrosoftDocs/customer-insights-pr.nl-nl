---
title: Segmenten maken en beheren
description: Maak segmenten van klanten om deze te groeperen op basis van verschillende kenmerken.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 6931110c2ae93cd2792d319aa5a34f0df3088552
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405517"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="a2c9a-103">Segmenten maken en beheren</span><span class="sxs-lookup"><span data-stu-id="a2c9a-103">Create and manage segments</span></span>

<span data-ttu-id="a2c9a-104">Met segmenten kunt u uw klanten groeperen op basis van demografische, transactionele of gedragskenmerken.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="a2c9a-105">U kunt segmenten gebruiken om promotiecampagnes, verkoopactiviteiten en acties voor klantenondersteuning te targeten om uw zakelijke doelstellingen te bereiken.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="a2c9a-106">U kunt complexe filters definiëren rondom de entiteit Klantprofiel en de bijbehorende entiteiten.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="a2c9a-107">Elk segment maakt na verwerking een set klantrecords die u kunt exporteren en waarop u actie kunt ondernemen.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="a2c9a-108">Er zijn enkele [servicelimieten](service-limits.md) van toepassing.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="a2c9a-109">Tenzij anders vermeld, zijn alle segmenten **Dynamische segmenten**, die worden vernieuwd volgens een terugkerend schema.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="a2c9a-110">Het volgende voorbeeld illustreert de segmentatiemogelijkheid.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="a2c9a-111">We hebben een segment gedefinieerd voor klanten die in de afgelopen 90 dagen voor ten minste $ 500 aan goederen hebben besteld *en* die betrokken waren bij een klantenserviceoproep die werd geëscaleerd.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a2c9a-112">![Meerdere groepen](media/segmentation-group1-2.png "Meerdere groepen")</span><span class="sxs-lookup"><span data-stu-id="a2c9a-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="a2c9a-113">Een nieuw segment maken</span><span class="sxs-lookup"><span data-stu-id="a2c9a-113">Create a new segment</span></span>

<span data-ttu-id="a2c9a-114">Segmenten worden beheerd op de pagina **Segmenten**.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="a2c9a-115">Ga in doelgroepinzichten naar de pagina **Segmenten**.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-115">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="a2c9a-116">Selecteer **Nieuw** > **Leeg segment**.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-116">Select **New** > **Blank segment**.</span></span>

3. <span data-ttu-id="a2c9a-117">Kies in het deelvenster **Nieuw segment** een segmenttype en geef een **Naam** op.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="a2c9a-118">Geef optioneel een weergavenaam op en een beschrijving die helpt bij het identificeren van het segment.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

4. <span data-ttu-id="a2c9a-119">Selecteer **Volgende** om naar de pagina **Segmentbouwer** te gaan waar u een groep definieert.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="a2c9a-120">Een groep is een set klanten.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-120">A group is a set of customers.</span></span>

5. <span data-ttu-id="a2c9a-121">Kies de entiteit die het kenmerk bevat waarop u wilt segmenteren.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-121">Choose the entity that includes the attribute you want to segment by.</span></span>

6. <span data-ttu-id="a2c9a-122">Kies het kenmerk waarop u wilt segmenteren.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="a2c9a-123">Dit kenmerk kan een van de volgende vier waardetypen hebben: numeriek, tekenreeks, datum of booleaans.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

7. <span data-ttu-id="a2c9a-124">Kies een operator en een waarde voor het geselecteerde kenmerk.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a2c9a-125">![Aangepast groepsfilter](media/customer-group-numbers.png "Klantgroepsfilter")</span><span class="sxs-lookup"><span data-stu-id="a2c9a-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="a2c9a-126">Getal</span><span class="sxs-lookup"><span data-stu-id="a2c9a-126">Number</span></span> |<span data-ttu-id="a2c9a-127">Definitie</span><span class="sxs-lookup"><span data-stu-id="a2c9a-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="a2c9a-128">1</span><span class="sxs-lookup"><span data-stu-id="a2c9a-128">1</span></span>     |<span data-ttu-id="a2c9a-129">Entity</span><span class="sxs-lookup"><span data-stu-id="a2c9a-129">Entity</span></span>          |
   |<span data-ttu-id="a2c9a-130">2</span><span class="sxs-lookup"><span data-stu-id="a2c9a-130">2</span></span>     |<span data-ttu-id="a2c9a-131">Kenmerk</span><span class="sxs-lookup"><span data-stu-id="a2c9a-131">Attribute</span></span>          |
   |<span data-ttu-id="a2c9a-132">3</span><span class="sxs-lookup"><span data-stu-id="a2c9a-132">3</span></span>    |<span data-ttu-id="a2c9a-133">Operator</span><span class="sxs-lookup"><span data-stu-id="a2c9a-133">Operator</span></span>         |
   |<span data-ttu-id="a2c9a-134">4</span><span class="sxs-lookup"><span data-stu-id="a2c9a-134">4</span></span>    |<span data-ttu-id="a2c9a-135">waarde</span><span class="sxs-lookup"><span data-stu-id="a2c9a-135">Value</span></span>         |

8. <span data-ttu-id="a2c9a-136">Als de entiteit via [relaties](relationships.md) met de geharmoniseerde klantentiteit is verbonden, moet u het relatiepad definiëren om een geldig segment te maken.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="a2c9a-137">Voeg de entiteiten uit het relatiepad toe totdat u de entiteit **Klant : CustomerInsights** in de vervolgkeuzelijst kunt selecteren.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="a2c9a-138">Kies vervolgens **Alle records** voor elke conditie.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a2c9a-139">![Relatiepad tijdens het maken van segmenten](media/segments-multiple-relationships.png "Relatiepad tijdens het maken van segmenten")</span><span class="sxs-lookup"><span data-stu-id="a2c9a-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

9. <span data-ttu-id="a2c9a-140">Selecteer **Opslaan** om uw segment op te slaan.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-140">Select **Save** to save your segment.</span></span> <span data-ttu-id="a2c9a-141">Uw segment wordt opgeslagen en verwerkt als alle vereisten zijn gevalideerd.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-141">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="a2c9a-142">Anders wordt het opgeslagen als concept.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-142">Otherwise, it will be saved as a draft.</span></span>

10. <span data-ttu-id="a2c9a-143">Selecteer **Terug naar segmenten** om terug te gaan naar de pagina **Segmenten**.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-143">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="a2c9a-144">Bestaande segmenten beheren</span><span class="sxs-lookup"><span data-stu-id="a2c9a-144">Manage existing segments</span></span>

<span data-ttu-id="a2c9a-145">Op de pagina **Segmenten** kunt u al uw opgeslagen segmenten bekijken en beheren.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-145">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="a2c9a-146">Elk segment wordt weergegeven door een rij met aanvullende informatie over het segment.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-146">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="a2c9a-147">U kunt de segmenten in een kolom sorteren door de kolomkop te selecteren.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-147">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="a2c9a-148">Gebruik het vak **Zoeken** in de rechterbovenhoek om de segmenten te filteren.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-148">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a2c9a-149">![Opties voor het beheren van een bestaand segment](media/segments-selected-segment.png "Opties voor het beheren van een bestaand segment")</span><span class="sxs-lookup"><span data-stu-id="a2c9a-149">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="a2c9a-150">De volgende actie is beschikbaar wanneer u een segment selecteert:</span><span class="sxs-lookup"><span data-stu-id="a2c9a-150">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="a2c9a-151">**Bekijk** de segmentdetails, inclusief trend van ledentelling en voorbeeld van segmentleden.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-151">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="a2c9a-152">**Bewerk** het segment om de eigenschappen te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-152">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="a2c9a-153">**Vernieuw** het segment om de nieuwste gegevens op te nemen.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-153">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="a2c9a-154">**Activeer** of **Deactiveer** het segment.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-154">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="a2c9a-155">Segmenten hebben twee mogelijke statussen: actief of inactief.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-155">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="a2c9a-156">Deze statussen zijn handig bij het bewerken van een segment.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-156">These states come in handy when editing a segment.</span></span> <span data-ttu-id="a2c9a-157">Voor inactieve segmenten bestaat de segmentdefinitie, maar bevat deze nog geen klanten.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-157">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="a2c9a-158">Wanneer u een segment activeert, verandert de status van 'inactief' in 'actief' en wordt gezocht naar klanten die voldoen aan de segmentdefinitie.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-158">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="a2c9a-159">Als een [geplande vernieuwing](system.md#schedule-tab) is geconfigureerd, hebben inactieve segmenten de **Status** **Overgeslagen**, wat aangeeft dat er niet eens is geprobeerd te vernieuwen.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-159">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="a2c9a-160">Wanneer een inactief segment wordt geactiveerd, wordt het vernieuwd en opgenomen in geplande vernieuwingen.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-160">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="a2c9a-161">U kunt ook de functionaliteit **Later plannen** in de vervolgkeuzelisjt **Activeren/Deactiveren** gebruiken om een toekomstige datum en tijd op te geven voor activering en deactivering van een bepaald segment.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-161">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="a2c9a-162">**Wijzig de naam** van het segment.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-162">**Rename** the segment.</span></span>
- <span data-ttu-id="a2c9a-163">**Download** de lijst van leden als .CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-163">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="a2c9a-164">**Toevoegen aan** verzendt de lijst met klant-id's in het segment voor verwerking in een andere applicatie.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-164">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="a2c9a-165">**Verwijder** het segment.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-165">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="a2c9a-166">Segmenten vernieuwen</span><span class="sxs-lookup"><span data-stu-id="a2c9a-166">Refresh segments</span></span>

<span data-ttu-id="a2c9a-167">U kunt alle segmenten tegelijk vernieuwen door **Alles vernieuwen** te selecteren op de pagina **Segmenten** of u kunt een of meerdere segmenten vernieuwen wanneer u deze selecteert en **Vernieuwen** uit de opties kiezen.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-167">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="a2c9a-168">U kunt ook een terugkerende vernieuwing configureren via **Beheerder** > **Systeem** > **Schema**.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-168">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="a2c9a-169">Er zijn [zes soorten status](system.md#status-types) voor taken/processen.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-169">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="a2c9a-170">Bovendien zijn de meeste processen [afhankelijk van andere stroomafwaartse processen](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="a2c9a-170">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="a2c9a-171">U kunt de status van een proces selecteren om voortgangsdetails te zien van de volledige taak.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-171">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="a2c9a-172">Na het selecteren van **Details bekijken** voor een van de taken vindt u aanvullende informatie: verwerkingstijd, de laatste verwerkingsdatum en alle fouten en waarschuwingen die bij de taak horen.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-172">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="a2c9a-173">Segmenten downloaden en exporteren</span><span class="sxs-lookup"><span data-stu-id="a2c9a-173">Download and export segments</span></span>

<span data-ttu-id="a2c9a-174">U kunt uw segmenten downloaden naar een CSV-bestand of ze exporteren naar Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-174">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="a2c9a-175">Segmenten downloaden naar een CSV-bestand</span><span class="sxs-lookup"><span data-stu-id="a2c9a-175">Download segments to a CSV file</span></span>

1. <span data-ttu-id="a2c9a-176">Ga in doelgroepinzichten naar de pagina **Segmenten**.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-176">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="a2c9a-177">Selecteer het beletselteken in de tegel van een specifiek segment.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-177">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="a2c9a-178">Selecteer **Downloaden als CSV** in de vervolgkeuzelijst Acties.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-178">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="a2c9a-179">Segmenten exporteren naar Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="a2c9a-179">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="a2c9a-180">Voordat een beheerder segmenten gaat exporteren naar Dynamics 365 Sales, moet deze [de exportbestemming maken](export-destinations.md) voor Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-180">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="a2c9a-181">Ga in doelgroepinzichten naar de pagina **Segmenten**.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-181">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="a2c9a-182">Selecteer het beletselteken in de tegel van een specifiek segment.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-182">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="a2c9a-183">Selecteer **Toevoegen aan** in de vervolgkeuzelijst met acties en selecteer de exportbestemming waarnaar u de gegevens wilt verzenden.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-183">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="a2c9a-184">Conceptmodus voor segmenten</span><span class="sxs-lookup"><span data-stu-id="a2c9a-184">Draft mode for segments</span></span>

<span data-ttu-id="a2c9a-185">Als niet aan alle vereisten voor het verwerken van een segment is voldaan, kunt u het segment als concept opslaan en openen vanaf de pagina **Segmenten**.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-185">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="a2c9a-186">Het wordt opgeslagen als een inactief segment en kan niet worden geactiveerd totdat het geldig is.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-186">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="a2c9a-187">Meer voorwaarden toevoegen aan een groep</span><span class="sxs-lookup"><span data-stu-id="a2c9a-187">Add more conditions to a group</span></span>

<span data-ttu-id="a2c9a-188">Als u meer voorwaarden aan een groep wilt toevoegen, kunt u twee logische operators gebruiken:</span><span class="sxs-lookup"><span data-stu-id="a2c9a-188">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="a2c9a-189">**EN**-operator: er moet aan beide voorwaarden worden voldaan als onderdeel van het segmentatieproces.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-189">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="a2c9a-190">Deze optie is vooral handig wanneer u voorwaarden definieert voor verschillende entiteiten.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-190">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="a2c9a-191">**OF**-operator: er moet aan een van beide voorwaarden worden voldaan als onderdeel van het segmentatieproces.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-191">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="a2c9a-192">Deze optie is vooral handig wanneer u meerdere voorwaarden definieert voor dezelfde entiteit.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-192">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a2c9a-193">![OF-operator waarbij aan een van beide voorwaarden moet worden voldaan](media/segmentation-either-condition.png "OF-operator waarbij aan een van beide voorwaarden moet worden voldaan")</span><span class="sxs-lookup"><span data-stu-id="a2c9a-193">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="a2c9a-194">Het is momenteel mogelijk om een **OF**-operator te nesten onder een **EN**-operator, maar niet andersom.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-194">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="a2c9a-195">Meerdere groepen combineren</span><span class="sxs-lookup"><span data-stu-id="a2c9a-195">Combine multiple groups</span></span>

<span data-ttu-id="a2c9a-196">Elke groep produceert een specifieke set klanten.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-196">Each group produces a specific set of customers.</span></span> <span data-ttu-id="a2c9a-197">U kunt deze groepen combineren om de klanten op te nemen die nodig zijn voor uw bedrijfsscenario.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-197">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="a2c9a-198">Ga in doelgroepinzichten naar de pagina **Segmenten** en selecteer een segment.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-198">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="a2c9a-199">Selecteer **Groep toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-199">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a2c9a-200">![Klantengroep - Groep toevoegen](media/customer-group-add-group.png "Klantengroep - Groep toevoegen")</span><span class="sxs-lookup"><span data-stu-id="a2c9a-200">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="a2c9a-201">Selecteer een van de volgende set-operators: **Verbinding**, **Overlappen** of **Behalve**.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-201">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a2c9a-202">![Klantengroep - Verbinding toevoegen](media/customer-group-union.png "Klantengroep - Verbinding toevoegen")</span><span class="sxs-lookup"><span data-stu-id="a2c9a-202">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="a2c9a-203">Selecteer een setoperator om een nieuwe groep te definiëren.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-203">Select a set operator to define a new group.</span></span> <span data-ttu-id="a2c9a-204">Sla verschillende groepen op om te bepalen welke gegevens moeten worden behouden:</span><span class="sxs-lookup"><span data-stu-id="a2c9a-204">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="a2c9a-205">**Verbinding** verbindt de twee groepen.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-205">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="a2c9a-206">**Overlappen** overlapt de twee groepen.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-206">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="a2c9a-207">Alleen gegevens die *gemeenschappelijk* zijn voor beide groepen, worden behouden in de geharmoniseerde groep.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-207">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="a2c9a-208">**Behalve** combineert de twee groepen.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-208">**Except** combines the two groups.</span></span> <span data-ttu-id="a2c9a-209">Alleen gegevens in groep A die *niet gemeenschappelijk* zijn voor gegevens in groep B, worden behouden.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-209">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="a2c9a-210">Verwerkingsgeschiedenis en segmentleden weergeven</span><span class="sxs-lookup"><span data-stu-id="a2c9a-210">View processing history and segment members</span></span>

<span data-ttu-id="a2c9a-211">U kunt geconsolideerde gegevens over een segment bekijken door de details te controleren.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-211">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="a2c9a-212">Selecteer op de pagina **Segmenten** het segment dat u wilt controleren.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-212">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="a2c9a-213">Het bovenste deel van de pagina bevat een trendgrafiek waarin wijzigingen in het aantal leden worden gevisualiseerd.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-213">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="a2c9a-214">Beweeg over gegevenspunten om het aantal leden op een specifieke datum te bekijken.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-214">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="a2c9a-215">U kunt het tijdsbereik van de visualisatie bijwerken.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-215">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a2c9a-216">![Tijdsbereik van segment](media/segment-time-range.png "Tijdsbereik van segment")</span><span class="sxs-lookup"><span data-stu-id="a2c9a-216">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="a2c9a-217">Het onderste gedeelte bevat een lijst met de segmentleden.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-217">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="a2c9a-218">Velden die in deze lijst worden weergegeven, zijn gebaseerd op de kenmerken van de entiteiten van uw segment.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-218">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="a2c9a-219">De lijst is een voorbeeld van de overeenkomende segmentleden en toont de eerste 100 records van uw segment, zodat u het snel kunt evalueren en indien nodig de definities kunt bekijken.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-219">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="a2c9a-220">Als u alle overeenkomende records wilt bekijken, moet u [het segment exporteren](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="a2c9a-220">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="a2c9a-221">Snelle segmenten</span><span class="sxs-lookup"><span data-stu-id="a2c9a-221">Quick segments</span></span>

<span data-ttu-id="a2c9a-222">Naast de segment-builder is er nog een ander pad om segmenten te maken.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-222">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="a2c9a-223">Met snelle segmenten kunt u snel met een enkele operator en met directe inzichten eenvoudige segmenten bouwen.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-223">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="a2c9a-224">Selecteer op de pagina **Segmenten** de optie **Nieuw** > **Snel maken van**.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-224">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="a2c9a-225">Selecteer de optie **Profielen** om een segment te bouwen dat is gebaseerd op de geharmoniseerde entiteit Klant.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-225">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="a2c9a-226">Selecteer de optie **Meetcriteria** om een segment te bouwen rond elk van de typen meetcriteria voor klantkenmerken die u eerder hebt gemaakt op de pagina **Meetcriteria**.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-226">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="a2c9a-227">Selecteer de optie **Intelligentie** om een segment op te bouwen rond een van de uitvoerentiteiten die u hebt gegenereerd met behulp van de mogelijkheden **Voorspellingen** of **Aangepaste modellen**.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-227">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="a2c9a-228">Selecteer in het dialoogvenster **Nieuw snel segment** een kenmerk uit de vervolgkeuzelijst **Veld**.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-228">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="a2c9a-229">Het systeem biedt enkele aanvullende inzichten waarmee u betere segmenten van uw klanten kunt maken.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-229">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="a2c9a-230">Voor categorievelden geven we tien topposities van klanten weer.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-230">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="a2c9a-231">Kies een **Waarde** en selecteer **Evalueren**.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-231">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="a2c9a-232">Voor een numeriek kenmerk laat het systeem zien welke kenmerkwaarde onder het percentiel van elke klant valt.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-232">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="a2c9a-233">Kies een **Operator** en een **Waarde** en selecteer vervolgens **Evalueren**.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-233">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="a2c9a-234">Het systeem zal u van een **Geschatte segmentgrootte** voorzien.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-234">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="a2c9a-235">U kunt kiezen of u het door u gedefinieerde segment wilt genereren of het eerst opnieuw wilt bezoeken om een andere segmentgrootte te krijgen.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-235">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a2c9a-236">![Naam en schatting voor een snel segment](media/quick-segment-name.png "Naam en schatting voor een snel segment")</span><span class="sxs-lookup"><span data-stu-id="a2c9a-236">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="a2c9a-237">Geef een **Naam** op voor uw segment.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-237">Provide a **Name** for your segment.</span></span> <span data-ttu-id="a2c9a-238">Voer desgewenst een **Weergavenaam** in.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-238">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="a2c9a-239">Selecteer **Opslaan** om uw segment te maken.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-239">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="a2c9a-240">Nadat de verwerking van segment is voltooid, kunt u het bekijken zoals elk ander segment dat u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-240">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="a2c9a-241">Voor de volgende scenario's adviseren wij het gebruik van de segmentbouwer in plaats van de mogelijkheid voor aanbevolen segmenten:</span><span class="sxs-lookup"><span data-stu-id="a2c9a-241">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="a2c9a-242">Segmenten maken met filters voor categorievelden waarbij de operator anders is dan de **Is**-operator</span><span class="sxs-lookup"><span data-stu-id="a2c9a-242">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="a2c9a-243">Segmenten maken met filters voor numerieke velden waarvan de operator anders is dan de operators **Tussen**, **Groter dan** en **Kleiner dan**</span><span class="sxs-lookup"><span data-stu-id="a2c9a-243">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="a2c9a-244">Segmenten maken met filters op datumtypevelden</span><span class="sxs-lookup"><span data-stu-id="a2c9a-244">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="a2c9a-245">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="a2c9a-245">Next steps</span></span>

<span data-ttu-id="a2c9a-246">[Exporteer een segment](export-destinations.md) en verken de [klantenkaart](customer-card-add-in.md) en [connectors](export-power-bi.md) om inzichten op klantniveau te verkrijgen.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-246">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>
