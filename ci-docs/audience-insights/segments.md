---
title: Segmenten maken en beheren
description: Maak segmenten van klanten om deze te groeperen op basis van verschillende kenmerken.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597045"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="96286-103">Segmenten maken en beheren</span><span class="sxs-lookup"><span data-stu-id="96286-103">Create and manage segments</span></span>

<span data-ttu-id="96286-104">Met segmenten kunt u uw klanten groeperen op basis van demografische, transactionele of gedragskenmerken.</span><span class="sxs-lookup"><span data-stu-id="96286-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="96286-105">U kunt segmenten gebruiken om promotiecampagnes, verkoopactiviteiten en acties voor klantenondersteuning te targeten om uw zakelijke doelstellingen te bereiken.</span><span class="sxs-lookup"><span data-stu-id="96286-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="96286-106">U kunt complexe filters definiëren rondom de entiteit Klantprofiel en de bijbehorende entiteiten.</span><span class="sxs-lookup"><span data-stu-id="96286-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="96286-107">Elk segment maakt na verwerking een set klantrecords die u kunt exporteren en waarop u actie kunt ondernemen.</span><span class="sxs-lookup"><span data-stu-id="96286-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="96286-108">Er zijn enkele [servicelimieten](service-limits.md) van toepassing.</span><span class="sxs-lookup"><span data-stu-id="96286-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="96286-109">Tenzij anders vermeld, zijn alle segmenten **Dynamische segmenten**, die worden vernieuwd volgens een terugkerend schema.</span><span class="sxs-lookup"><span data-stu-id="96286-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="96286-110">Het volgende voorbeeld illustreert de segmentatiemogelijkheid.</span><span class="sxs-lookup"><span data-stu-id="96286-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="96286-111">We hebben een segment gedefinieerd voor klanten die in de afgelopen 90 dagen voor ten minste $ 500 aan goederen hebben besteld *en* die betrokken waren bij een klantenserviceoproep die werd geëscaleerd.</span><span class="sxs-lookup"><span data-stu-id="96286-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="96286-112">![Meerdere groepen](media/segmentation-group1-2.png "Meerdere groepen")</span><span class="sxs-lookup"><span data-stu-id="96286-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="96286-113">Een nieuw segment maken</span><span class="sxs-lookup"><span data-stu-id="96286-113">Create a new segment</span></span>

<span data-ttu-id="96286-114">Segmenten worden beheerd op de pagina **Segmenten**.</span><span class="sxs-lookup"><span data-stu-id="96286-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="96286-115">Ga in doelgroepinzichten naar de pagina **Segmenten**.</span><span class="sxs-lookup"><span data-stu-id="96286-115">In audience insights, go to the **Segments** page.</span></span>

1. <span data-ttu-id="96286-116">Selecteer **Nieuw** > **Leeg segment**.</span><span class="sxs-lookup"><span data-stu-id="96286-116">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="96286-117">Kies in het deelvenster **Nieuw segment** een segmenttype en geef een **Naam** op.</span><span class="sxs-lookup"><span data-stu-id="96286-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="96286-118">Geef optioneel een weergavenaam op en een beschrijving die helpt bij het identificeren van het segment.</span><span class="sxs-lookup"><span data-stu-id="96286-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="96286-119">Selecteer **Volgende** om naar de pagina **Segmentbouwer** te gaan waar u een groep definieert.</span><span class="sxs-lookup"><span data-stu-id="96286-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="96286-120">Een groep is een set klanten.</span><span class="sxs-lookup"><span data-stu-id="96286-120">A group is a set of customers.</span></span>

1. <span data-ttu-id="96286-121">Kies de entiteit die het kenmerk bevat waarop u wilt segmenteren.</span><span class="sxs-lookup"><span data-stu-id="96286-121">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="96286-122">Kies het kenmerk waarop u wilt segmenteren.</span><span class="sxs-lookup"><span data-stu-id="96286-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="96286-123">Dit kenmerk kan een van de volgende vier waardetypen hebben: numeriek, tekenreeks, datum of booleaans.</span><span class="sxs-lookup"><span data-stu-id="96286-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="96286-124">Kies een operator en een waarde voor het geselecteerde kenmerk.</span><span class="sxs-lookup"><span data-stu-id="96286-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="96286-125">![Aangepast groepsfilter](media/customer-group-numbers.png "Klantgroepsfilter")</span><span class="sxs-lookup"><span data-stu-id="96286-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="96286-126">Getal</span><span class="sxs-lookup"><span data-stu-id="96286-126">Number</span></span> |<span data-ttu-id="96286-127">Definitie</span><span class="sxs-lookup"><span data-stu-id="96286-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="96286-128">1</span><span class="sxs-lookup"><span data-stu-id="96286-128">1</span></span>     |<span data-ttu-id="96286-129">Entity</span><span class="sxs-lookup"><span data-stu-id="96286-129">Entity</span></span>          |
   |<span data-ttu-id="96286-130">2</span><span class="sxs-lookup"><span data-stu-id="96286-130">2</span></span>     |<span data-ttu-id="96286-131">Kenmerk</span><span class="sxs-lookup"><span data-stu-id="96286-131">Attribute</span></span>          |
   |<span data-ttu-id="96286-132">3</span><span class="sxs-lookup"><span data-stu-id="96286-132">3</span></span>    |<span data-ttu-id="96286-133">Operator</span><span class="sxs-lookup"><span data-stu-id="96286-133">Operator</span></span>         |
   |<span data-ttu-id="96286-134">4</span><span class="sxs-lookup"><span data-stu-id="96286-134">4</span></span>    |<span data-ttu-id="96286-135">waarde</span><span class="sxs-lookup"><span data-stu-id="96286-135">Value</span></span>         |

8. <span data-ttu-id="96286-136">Als de entiteit via [relaties](relationships.md) met de geharmoniseerde klantentiteit is verbonden, moet u het relatiepad definiëren om een geldig segment te maken.</span><span class="sxs-lookup"><span data-stu-id="96286-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="96286-137">Voeg de entiteiten uit het relatiepad toe totdat u de entiteit **Klant : CustomerInsights** in de vervolgkeuzelijst kunt selecteren.</span><span class="sxs-lookup"><span data-stu-id="96286-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="96286-138">Kies vervolgens **Alle records** voor elke conditie.</span><span class="sxs-lookup"><span data-stu-id="96286-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="96286-139">![Relatiepad tijdens het maken van segmenten](media/segments-multiple-relationships.png "Relatiepad tijdens het maken van segmenten")</span><span class="sxs-lookup"><span data-stu-id="96286-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="96286-140">Segmenten genereren standaard een uitvoerentiteit die alle kenmerken van klantprofielen bevat die overeenkomen met de gedefinieerde filters.</span><span class="sxs-lookup"><span data-stu-id="96286-140">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="96286-141">Als een segment is gebaseerd op andere entiteiten dan de entiteit *Klant*, kunt u meer attributen van deze entiteiten aan de uitvoerentiteit toevoegen.</span><span class="sxs-lookup"><span data-stu-id="96286-141">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="96286-142">Selecteer **Projectkernmerken** om de kenmerken te kiezen die aan de uitvoerentiteit worden toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="96286-142">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  

   
   <span data-ttu-id="96286-143">Voorbeeld: een segment is gebaseerd op een entiteit die gegevens over klantactiviteit bevat die gerelateerd zijn aan de entiteit *Klant*.</span><span class="sxs-lookup"><span data-stu-id="96286-143">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="96286-144">Het segment zoekt naar alle klanten die de helpdesk de afgelopen 60 dagen hebben gebeld.</span><span class="sxs-lookup"><span data-stu-id="96286-144">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="96286-145">U kunt ervoor kiezen om de gespreksduur en het aantal gesprekken toe te voegen aan alle overeenkomende klantrecords in de uitvoerentiteit.</span><span class="sxs-lookup"><span data-stu-id="96286-145">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="96286-146">Deze gegevens kunnen handig zijn om een e-mail met handige koppelingen naar Help-artikelen en FAQ's te sturen naar klanten die vaak hebben gebeld.</span><span class="sxs-lookup"><span data-stu-id="96286-146">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

1. <span data-ttu-id="96286-147">Selecteer **Opslaan** om uw segment op te slaan.</span><span class="sxs-lookup"><span data-stu-id="96286-147">Select **Save** to save your segment.</span></span> <span data-ttu-id="96286-148">Uw segment wordt opgeslagen en verwerkt als alle vereisten zijn gevalideerd.</span><span class="sxs-lookup"><span data-stu-id="96286-148">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="96286-149">Anders wordt het opgeslagen als concept.</span><span class="sxs-lookup"><span data-stu-id="96286-149">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="96286-150">Selecteer **Terug naar segmenten** om terug te gaan naar de pagina **Segmenten**.</span><span class="sxs-lookup"><span data-stu-id="96286-150">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="96286-151">Bestaande segmenten beheren</span><span class="sxs-lookup"><span data-stu-id="96286-151">Manage existing segments</span></span>

<span data-ttu-id="96286-152">Op de pagina **Segmenten** kunt u al uw opgeslagen segmenten bekijken en beheren.</span><span class="sxs-lookup"><span data-stu-id="96286-152">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="96286-153">Elk segment wordt weergegeven door een rij met aanvullende informatie over het segment.</span><span class="sxs-lookup"><span data-stu-id="96286-153">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="96286-154">U kunt de segmenten in een kolom sorteren door de kolomkop te selecteren.</span><span class="sxs-lookup"><span data-stu-id="96286-154">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="96286-155">Gebruik het vak **Zoeken** in de rechterbovenhoek om de segmenten te filteren.</span><span class="sxs-lookup"><span data-stu-id="96286-155">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="96286-156">![Opties voor het beheren van een bestaand segment](media/segments-selected-segment.png "Opties voor het beheren van een bestaand segment")</span><span class="sxs-lookup"><span data-stu-id="96286-156">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="96286-157">De volgende actie is beschikbaar wanneer u een segment selecteert:</span><span class="sxs-lookup"><span data-stu-id="96286-157">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="96286-158">**Bekijk** de segmentdetails, inclusief trend van ledentelling en voorbeeld van segmentleden.</span><span class="sxs-lookup"><span data-stu-id="96286-158">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="96286-159">**Bewerk** het segment om de eigenschappen te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="96286-159">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="96286-160">**Maak een duplicaat** van een segment.</span><span class="sxs-lookup"><span data-stu-id="96286-160">**Create duplicate** of a segment.</span></span> <span data-ttu-id="96286-161">U kunt ervoor kiezen om de eigenschappen meteen te bewerken of gewoon het duplicaat op te slaan.</span><span class="sxs-lookup"><span data-stu-id="96286-161">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="96286-162">**Vernieuw** het segment om de nieuwste gegevens op te nemen.</span><span class="sxs-lookup"><span data-stu-id="96286-162">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="96286-163">**Activeer** of **Deactiveer** het segment.</span><span class="sxs-lookup"><span data-stu-id="96286-163">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="96286-164">Segmenten hebben twee mogelijke statussen: actief of inactief.</span><span class="sxs-lookup"><span data-stu-id="96286-164">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="96286-165">Deze statussen zijn handig bij het bewerken van een segment.</span><span class="sxs-lookup"><span data-stu-id="96286-165">These states come in handy when editing a segment.</span></span> <span data-ttu-id="96286-166">Voor inactieve segmenten bestaat de segmentdefinitie, maar bevat deze nog geen klanten.</span><span class="sxs-lookup"><span data-stu-id="96286-166">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="96286-167">Wanneer u een segment activeert, verandert de status van 'inactief' in 'actief' en wordt gezocht naar klanten die voldoen aan de segmentdefinitie.</span><span class="sxs-lookup"><span data-stu-id="96286-167">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="96286-168">Als een [geplande vernieuwing](system.md#schedule-tab) is geconfigureerd, hebben inactieve segmenten de **Status** **Overgeslagen**, wat aangeeft dat er niet eens is geprobeerd te vernieuwen.</span><span class="sxs-lookup"><span data-stu-id="96286-168">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="96286-169">Wanneer een inactief segment wordt geactiveerd, wordt het vernieuwd en opgenomen in geplande vernieuwingen.</span><span class="sxs-lookup"><span data-stu-id="96286-169">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="96286-170">U kunt ook de functionaliteit **Later plannen** in de vervolgkeuzelisjt **Activeren/Deactiveren** gebruiken om een toekomstige datum en tijd op te geven voor activering en deactivering van een bepaald segment.</span><span class="sxs-lookup"><span data-stu-id="96286-170">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="96286-171">**Wijzig de naam** van het segment.</span><span class="sxs-lookup"><span data-stu-id="96286-171">**Rename** the segment.</span></span>
- <span data-ttu-id="96286-172">**Download** de lijst van leden als .CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="96286-172">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="96286-173">**Toevoegen aan** verzendt de lijst met klant-id's in het segment voor verwerking in een andere applicatie.</span><span class="sxs-lookup"><span data-stu-id="96286-173">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="96286-174">**Verwijder** het segment.</span><span class="sxs-lookup"><span data-stu-id="96286-174">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="96286-175">Segmenten vernieuwen</span><span class="sxs-lookup"><span data-stu-id="96286-175">Refresh segments</span></span>

<span data-ttu-id="96286-176">U kunt alle segmenten tegelijk vernieuwen door **Alles vernieuwen** te selecteren op de pagina **Segmenten** of u kunt een of meerdere segmenten vernieuwen wanneer u deze selecteert en **Vernieuwen** uit de opties kiezen.</span><span class="sxs-lookup"><span data-stu-id="96286-176">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="96286-177">U kunt ook een terugkerende vernieuwing configureren via **Beheerder** > **Systeem** > **Schema**.</span><span class="sxs-lookup"><span data-stu-id="96286-177">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="96286-178">Er zijn [zes soorten status](system.md#status-types) voor taken/processen.</span><span class="sxs-lookup"><span data-stu-id="96286-178">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="96286-179">Bovendien zijn de meeste processen [afhankelijk van andere stroomafwaartse processen](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="96286-179">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="96286-180">U kunt de status van een proces selecteren om voortgangsdetails te zien van de volledige taak.</span><span class="sxs-lookup"><span data-stu-id="96286-180">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="96286-181">Na het selecteren van **Details bekijken** voor een van de taken vindt u aanvullende informatie: verwerkingstijd, de laatste verwerkingsdatum en alle fouten en waarschuwingen die bij de taak horen.</span><span class="sxs-lookup"><span data-stu-id="96286-181">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="96286-182">Segmenten downloaden en exporteren</span><span class="sxs-lookup"><span data-stu-id="96286-182">Download and export segments</span></span>

<span data-ttu-id="96286-183">U kunt uw segmenten downloaden naar een CSV-bestand of ze exporteren naar Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="96286-183">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="96286-184">Segmenten downloaden naar een CSV-bestand</span><span class="sxs-lookup"><span data-stu-id="96286-184">Download segments to a CSV file</span></span>

1. <span data-ttu-id="96286-185">Ga in doelgroepinzichten naar de pagina **Segmenten**.</span><span class="sxs-lookup"><span data-stu-id="96286-185">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="96286-186">Selecteer het beletselteken in de tegel van een specifiek segment.</span><span class="sxs-lookup"><span data-stu-id="96286-186">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="96286-187">Selecteer **Downloaden als CSV** in de vervolgkeuzelijst Acties.</span><span class="sxs-lookup"><span data-stu-id="96286-187">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="96286-188">Segmenten exporteren naar Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="96286-188">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="96286-189">Voordat een beheerder segmenten gaat exporteren naar Dynamics 365 Sales, moet deze [de exportbestemming maken](export-destinations.md) voor Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="96286-189">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="96286-190">Ga in doelgroepinzichten naar de pagina **Segmenten**.</span><span class="sxs-lookup"><span data-stu-id="96286-190">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="96286-191">Selecteer het beletselteken in de tegel van een specifiek segment.</span><span class="sxs-lookup"><span data-stu-id="96286-191">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="96286-192">Selecteer **Toevoegen aan** in de vervolgkeuzelijst met acties en selecteer de exportbestemming waarnaar u de gegevens wilt verzenden.</span><span class="sxs-lookup"><span data-stu-id="96286-192">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="96286-193">Conceptmodus voor segmenten</span><span class="sxs-lookup"><span data-stu-id="96286-193">Draft mode for segments</span></span>

<span data-ttu-id="96286-194">Als niet aan alle vereisten voor het verwerken van een segment is voldaan, kunt u het segment als concept opslaan en openen vanaf de pagina **Segmenten**.</span><span class="sxs-lookup"><span data-stu-id="96286-194">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="96286-195">Het wordt opgeslagen als een inactief segment en kan niet worden geactiveerd totdat het geldig is.</span><span class="sxs-lookup"><span data-stu-id="96286-195">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="96286-196">Meer voorwaarden toevoegen aan een groep</span><span class="sxs-lookup"><span data-stu-id="96286-196">Add more conditions to a group</span></span>

<span data-ttu-id="96286-197">Als u meer voorwaarden aan een groep wilt toevoegen, kunt u twee logische operators gebruiken:</span><span class="sxs-lookup"><span data-stu-id="96286-197">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="96286-198">**EN**-operator: er moet aan beide voorwaarden worden voldaan als onderdeel van het segmentatieproces.</span><span class="sxs-lookup"><span data-stu-id="96286-198">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="96286-199">Deze optie is vooral handig wanneer u voorwaarden definieert voor verschillende entiteiten.</span><span class="sxs-lookup"><span data-stu-id="96286-199">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="96286-200">**OF**-operator: er moet aan een van beide voorwaarden worden voldaan als onderdeel van het segmentatieproces.</span><span class="sxs-lookup"><span data-stu-id="96286-200">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="96286-201">Deze optie is vooral handig wanneer u meerdere voorwaarden definieert voor dezelfde entiteit.</span><span class="sxs-lookup"><span data-stu-id="96286-201">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="96286-202">![OF-operator waarbij aan een van beide voorwaarden moet worden voldaan](media/segmentation-either-condition.png "OF-operator waarbij aan een van beide voorwaarden moet worden voldaan")</span><span class="sxs-lookup"><span data-stu-id="96286-202">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="96286-203">Het is momenteel mogelijk om een **OF**-operator te nesten onder een **EN**-operator, maar niet andersom.</span><span class="sxs-lookup"><span data-stu-id="96286-203">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="96286-204">Meerdere groepen combineren</span><span class="sxs-lookup"><span data-stu-id="96286-204">Combine multiple groups</span></span>

<span data-ttu-id="96286-205">Elke groep produceert een specifieke set klanten.</span><span class="sxs-lookup"><span data-stu-id="96286-205">Each group produces a specific set of customers.</span></span> <span data-ttu-id="96286-206">U kunt deze groepen combineren om de klanten op te nemen die nodig zijn voor uw bedrijfsscenario.</span><span class="sxs-lookup"><span data-stu-id="96286-206">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="96286-207">Ga in doelgroepinzichten naar de pagina **Segmenten** en selecteer een segment.</span><span class="sxs-lookup"><span data-stu-id="96286-207">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="96286-208">Selecteer **Groep toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="96286-208">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="96286-209">![Klantengroep - Groep toevoegen](media/customer-group-add-group.png "Klantengroep - Groep toevoegen")</span><span class="sxs-lookup"><span data-stu-id="96286-209">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="96286-210">Selecteer een van de volgende set-operators: **Verbinding**, **Overlappen** of **Behalve**.</span><span class="sxs-lookup"><span data-stu-id="96286-210">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="96286-211">![Klantengroep - Verbinding toevoegen](media/customer-group-union.png "Klantengroep - Verbinding toevoegen")</span><span class="sxs-lookup"><span data-stu-id="96286-211">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="96286-212">Selecteer een setoperator om een nieuwe groep te definiëren.</span><span class="sxs-lookup"><span data-stu-id="96286-212">Select a set operator to define a new group.</span></span> <span data-ttu-id="96286-213">Sla verschillende groepen op om te bepalen welke gegevens moeten worden behouden:</span><span class="sxs-lookup"><span data-stu-id="96286-213">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="96286-214">**Verbinding** verbindt de twee groepen.</span><span class="sxs-lookup"><span data-stu-id="96286-214">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="96286-215">**Overlappen** overlapt de twee groepen.</span><span class="sxs-lookup"><span data-stu-id="96286-215">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="96286-216">Alleen gegevens die *gemeenschappelijk* zijn voor beide groepen, worden behouden in de geharmoniseerde groep.</span><span class="sxs-lookup"><span data-stu-id="96286-216">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="96286-217">**Behalve** combineert de twee groepen.</span><span class="sxs-lookup"><span data-stu-id="96286-217">**Except** combines the two groups.</span></span> <span data-ttu-id="96286-218">Alleen gegevens in groep A die *niet gemeenschappelijk* zijn voor gegevens in groep B, worden behouden.</span><span class="sxs-lookup"><span data-stu-id="96286-218">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="96286-219">Verwerkingsgeschiedenis en segmentleden weergeven</span><span class="sxs-lookup"><span data-stu-id="96286-219">View processing history and segment members</span></span>

<span data-ttu-id="96286-220">U kunt geconsolideerde gegevens over een segment bekijken door de details te controleren.</span><span class="sxs-lookup"><span data-stu-id="96286-220">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="96286-221">Selecteer op de pagina **Segmenten** het segment dat u wilt controleren.</span><span class="sxs-lookup"><span data-stu-id="96286-221">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="96286-222">Het bovenste deel van de pagina bevat een trendgrafiek waarin wijzigingen in het aantal leden worden gevisualiseerd.</span><span class="sxs-lookup"><span data-stu-id="96286-222">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="96286-223">Beweeg over gegevenspunten om het aantal leden op een specifieke datum te bekijken.</span><span class="sxs-lookup"><span data-stu-id="96286-223">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="96286-224">U kunt het tijdsbereik van de visualisatie bijwerken.</span><span class="sxs-lookup"><span data-stu-id="96286-224">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="96286-225">![Tijdsbereik van segment](media/segment-time-range.png "Tijdsbereik van segment")</span><span class="sxs-lookup"><span data-stu-id="96286-225">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="96286-226">Het onderste gedeelte bevat een lijst met de segmentleden.</span><span class="sxs-lookup"><span data-stu-id="96286-226">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="96286-227">Velden die in deze lijst worden weergegeven, zijn gebaseerd op de kenmerken van de entiteiten van uw segment.</span><span class="sxs-lookup"><span data-stu-id="96286-227">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="96286-228">De lijst is een voorbeeld van de overeenkomende segmentleden en toont de eerste 100 records van uw segment, zodat u het snel kunt evalueren en indien nodig de definities kunt bekijken.</span><span class="sxs-lookup"><span data-stu-id="96286-228">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="96286-229">Als u alle overeenkomende records wilt bekijken, moet u [het segment exporteren](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="96286-229">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="96286-230">Snelle segmenten</span><span class="sxs-lookup"><span data-stu-id="96286-230">Quick segments</span></span>

<span data-ttu-id="96286-231">Naast de segment-builder is er nog een ander pad om segmenten te maken.</span><span class="sxs-lookup"><span data-stu-id="96286-231">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="96286-232">Met snelle segmenten kunt u snel met een enkele operator en met directe inzichten eenvoudige segmenten bouwen.</span><span class="sxs-lookup"><span data-stu-id="96286-232">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="96286-233">Selecteer op de pagina **Segmenten** de optie **Nieuw** > **Snel maken van**.</span><span class="sxs-lookup"><span data-stu-id="96286-233">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="96286-234">Selecteer de optie **Profielen** om een segment te bouwen dat is gebaseerd op de geharmoniseerde entiteit Klant.</span><span class="sxs-lookup"><span data-stu-id="96286-234">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="96286-235">Selecteer de optie **Meetcriteria** om een segment te bouwen rond elk van de typen meetcriteria voor klantkenmerken die u eerder hebt gemaakt op de pagina **Meetcriteria**.</span><span class="sxs-lookup"><span data-stu-id="96286-235">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="96286-236">Selecteer de optie **Intelligentie** om een segment op te bouwen rond een van de uitvoerentiteiten die u hebt gegenereerd met behulp van de mogelijkheden **Voorspellingen** of **Aangepaste modellen**.</span><span class="sxs-lookup"><span data-stu-id="96286-236">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="96286-237">Selecteer in het dialoogvenster **Nieuw snel segment** een kenmerk uit de vervolgkeuzelijst **Veld**.</span><span class="sxs-lookup"><span data-stu-id="96286-237">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="96286-238">Het systeem biedt enkele aanvullende inzichten waarmee u betere segmenten van uw klanten kunt maken.</span><span class="sxs-lookup"><span data-stu-id="96286-238">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="96286-239">Voor categorievelden geven we tien topposities van klanten weer.</span><span class="sxs-lookup"><span data-stu-id="96286-239">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="96286-240">Kies een **Waarde** en selecteer **Evalueren**.</span><span class="sxs-lookup"><span data-stu-id="96286-240">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="96286-241">Voor een numeriek kenmerk laat het systeem zien welke kenmerkwaarde onder het percentiel van elke klant valt.</span><span class="sxs-lookup"><span data-stu-id="96286-241">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="96286-242">Kies een **Operator** en een **Waarde** en selecteer vervolgens **Evalueren**.</span><span class="sxs-lookup"><span data-stu-id="96286-242">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="96286-243">Het systeem zal u van een **Geschatte segmentgrootte** voorzien.</span><span class="sxs-lookup"><span data-stu-id="96286-243">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="96286-244">U kunt kiezen of u het door u gedefinieerde segment wilt genereren of het eerst opnieuw wilt bezoeken om een andere segmentgrootte te krijgen.</span><span class="sxs-lookup"><span data-stu-id="96286-244">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="96286-245">![Naam en schatting voor een snel segment](media/quick-segment-name.png "Naam en schatting voor een snel segment")</span><span class="sxs-lookup"><span data-stu-id="96286-245">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="96286-246">Geef een **Naam** op voor uw segment.</span><span class="sxs-lookup"><span data-stu-id="96286-246">Provide a **Name** for your segment.</span></span> <span data-ttu-id="96286-247">Voer desgewenst een **Weergavenaam** in.</span><span class="sxs-lookup"><span data-stu-id="96286-247">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="96286-248">Selecteer **Opslaan** om uw segment te maken.</span><span class="sxs-lookup"><span data-stu-id="96286-248">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="96286-249">Nadat de verwerking van segment is voltooid, kunt u het bekijken zoals elk ander segment dat u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="96286-249">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="96286-250">Voor de volgende scenario's adviseren wij het gebruik van de segmentbouwer in plaats van de mogelijkheid voor aanbevolen segmenten:</span><span class="sxs-lookup"><span data-stu-id="96286-250">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="96286-251">Segmenten maken met filters voor categorievelden waarbij de operator anders is dan de **Is**-operator</span><span class="sxs-lookup"><span data-stu-id="96286-251">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="96286-252">Segmenten maken met filters voor numerieke velden waarvan de operator anders is dan de operators **Tussen**, **Groter dan** en **Kleiner dan**</span><span class="sxs-lookup"><span data-stu-id="96286-252">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="96286-253">Segmenten maken met filters op datumtypevelden</span><span class="sxs-lookup"><span data-stu-id="96286-253">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="96286-254">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="96286-254">Next steps</span></span>

<span data-ttu-id="96286-255">[Exporteer een segment](export-destinations.md) en verken de [klantenkaart](customer-card-add-in.md) en [connectors](export-power-bi.md) om inzichten op klantniveau te verkrijgen.</span><span class="sxs-lookup"><span data-stu-id="96286-255">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]