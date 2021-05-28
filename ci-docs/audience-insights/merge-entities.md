---
title: Entiteiten samenvoegen in gegevensharmonisatie
description: Voeg entiteiten samen om geharmoniseerde klantprofielen te maken.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2cab702509596dd87c0c9b9769d1af8ba8387f9d
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085570"
---
# <a name="merge-entities"></a><span data-ttu-id="08a53-103">Entiteiten samenvoegen</span><span class="sxs-lookup"><span data-stu-id="08a53-103">Merge entities</span></span>

<span data-ttu-id="08a53-104">De samenvoegingsfase is de laatste fase in het proces voor gegevensharmonisatie.</span><span class="sxs-lookup"><span data-stu-id="08a53-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="08a53-105">Het doel is het afstemmen van conflicterende gegevens.</span><span class="sxs-lookup"><span data-stu-id="08a53-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="08a53-106">Voorbeelden van conflicterende gegevens kunnen een klantnaam zijn die in twee van uw gegevenssets is gevonden, maar in elk een beetje anders verschijnt ("Grant Marshall" versus "Grant Marshal"), of een telefoonnummer met een andere indeling(617-803-091X versus 617803091X).</span><span class="sxs-lookup"><span data-stu-id="08a53-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="08a53-107">Het samenvoegen van die conflicterende gegevenspunten gebeurt op een kenmerk-per-kenmerkbasis.</span><span class="sxs-lookup"><span data-stu-id="08a53-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Samenvoegpagina in het gegevensharmonisatieproces waarop een tabel wordt weergegeven met samengevoegde velden die het uniforme klantprofiel definiëren.":::

<span data-ttu-id="08a53-109">Na het voltooien van de [afstemmingsfase](match-entities.md), kunt u de samenvoegingsfase starten door de tegel **Samenvoegen** te selecteren op de pagina **Harmoniseren**.</span><span class="sxs-lookup"><span data-stu-id="08a53-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="08a53-110">Systeemaanbevelingen bekijken</span><span class="sxs-lookup"><span data-stu-id="08a53-110">Review system recommendations</span></span>

<span data-ttu-id="08a53-111">Bij **Gegevens** > **Harmoniseren** > **Samenvoegen** kiest u welke kenmerken u wel en niet wilt opnemen voor samenvoeging in uw uniforme klantprofielentiteit.</span><span class="sxs-lookup"><span data-stu-id="08a53-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="08a53-112">Het uniforme klantprofiel is het resultaat van het gegevensharmonisatieproces.</span><span class="sxs-lookup"><span data-stu-id="08a53-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="08a53-113">Sommige kenmerken worden automatisch door het systeem samengevoegd.</span><span class="sxs-lookup"><span data-stu-id="08a53-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="08a53-114">Als u de kenmerken wilt weergeven die zijn opgenomen in een van uw automatisch samengevoegde kenmerken, selecteert u dat samengevoegde kenmerk op het tabblad **Klantvelden** van de tabel.</span><span class="sxs-lookup"><span data-stu-id="08a53-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="08a53-115">De kenmerken waaruit dat samengevoegde kenmerk is samengesteld, worden weergegeven in twee nieuwe rijen onder het samengevoegde kenmerk.</span><span class="sxs-lookup"><span data-stu-id="08a53-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="08a53-116">Samengevoegde velden scheiden, hernoemen, uitsluiten en bewerken</span><span class="sxs-lookup"><span data-stu-id="08a53-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="08a53-117">U kunt wijzigen hoe in het systeem samengevoegde kenmerken worden verwerkt om het uniforme klantprofiel te genereren.</span><span class="sxs-lookup"><span data-stu-id="08a53-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="08a53-118">Selecteer **Meer weergeven** en kies wat u wilt veranderen.</span><span class="sxs-lookup"><span data-stu-id="08a53-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Opties in het vervolgkeuzemenu Meer weergeven om samengevoegde kenmerken te beheren.":::

<span data-ttu-id="08a53-120">Zie de volgende gedeelten voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="08a53-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="08a53-121">Aparte samengevoegde velden</span><span class="sxs-lookup"><span data-stu-id="08a53-121">Separate merged fields</span></span>

<span data-ttu-id="08a53-122">Zoek het kenmerk in de tabel om samengevoegde velden te scheiden.</span><span class="sxs-lookup"><span data-stu-id="08a53-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="08a53-123">Gescheiden velden worden weergegeven als individuele gegevenspunten in het uniforme klantprofiel.</span><span class="sxs-lookup"><span data-stu-id="08a53-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="08a53-124">Selecteer het samengevoegde veld.</span><span class="sxs-lookup"><span data-stu-id="08a53-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="08a53-125">Selecteer **Meer weergeven** en kies **Afzonderlijke velden**.</span><span class="sxs-lookup"><span data-stu-id="08a53-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="08a53-126">Bevestig de scheiding.</span><span class="sxs-lookup"><span data-stu-id="08a53-126">Confirm the separation.</span></span>

1. <span data-ttu-id="08a53-127">Selecteer **Opslaan** en **Uitvoeren** om de wijzigingen te verwerken.</span><span class="sxs-lookup"><span data-stu-id="08a53-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="08a53-128">Samengevoegde velden hernoemen</span><span class="sxs-lookup"><span data-stu-id="08a53-128">Rename merged fields</span></span>

<span data-ttu-id="08a53-129">Wijzig de weergavenaam van samengevoegde kenmerken.</span><span class="sxs-lookup"><span data-stu-id="08a53-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="08a53-130">U kunt de naam van de uitvoerentiteit niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="08a53-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="08a53-131">Selecteer het samengevoegde veld.</span><span class="sxs-lookup"><span data-stu-id="08a53-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="08a53-132">Selecteer **Meer weergeven** en kies **Naam wijzigen**.</span><span class="sxs-lookup"><span data-stu-id="08a53-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="08a53-133">Bevestig de gewijzigde weergavenaam.</span><span class="sxs-lookup"><span data-stu-id="08a53-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="08a53-134">Selecteer **Opslaan** en **Uitvoeren** om de wijzigingen te verwerken.</span><span class="sxs-lookup"><span data-stu-id="08a53-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="08a53-135">Samengevoegde velden uitsluiten</span><span class="sxs-lookup"><span data-stu-id="08a53-135">Exclude merged fields</span></span>

<span data-ttu-id="08a53-136">Sluit een kenmerk uit van het uniforme klantprofiel.</span><span class="sxs-lookup"><span data-stu-id="08a53-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="08a53-137">Als het veld in andere processen wordt gebruikt, bijvoorbeeld in een segment, verwijder het dan uit deze processen voordat u het uitsluit van het klantprofiel.</span><span class="sxs-lookup"><span data-stu-id="08a53-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="08a53-138">Selecteer het samengevoegde veld.</span><span class="sxs-lookup"><span data-stu-id="08a53-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="08a53-139">Selecteer **Meer weergeven** en kies **Uitsluiten**.</span><span class="sxs-lookup"><span data-stu-id="08a53-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="08a53-140">Bevestig de uitsluiting.</span><span class="sxs-lookup"><span data-stu-id="08a53-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="08a53-141">Selecteer **Opslaan** en **Uitvoeren** om de wijzigingen te verwerken.</span><span class="sxs-lookup"><span data-stu-id="08a53-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="08a53-142">Selecteer op de pagina **Samenvoegen** **Uitgesloten velden** om de lijst met alle uitgesloten velden te zien.</span><span class="sxs-lookup"><span data-stu-id="08a53-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="08a53-143">In dit deelvenster kunt u uitgesloten velden weer toevoegen.</span><span class="sxs-lookup"><span data-stu-id="08a53-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="08a53-144">Velden handmatig combineren</span><span class="sxs-lookup"><span data-stu-id="08a53-144">Manually combine fields</span></span>

<span data-ttu-id="08a53-145">Geef handmatig een samengevoegd kenmerk op.</span><span class="sxs-lookup"><span data-stu-id="08a53-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="08a53-146">Selecteer op de pagina **Samenvoegen** **Velden combineren**.</span><span class="sxs-lookup"><span data-stu-id="08a53-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="08a53-147">Geef informatie op voor **Naam** en **Naam van uitvoerveld**.</span><span class="sxs-lookup"><span data-stu-id="08a53-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="08a53-148">Kies een veld dat u wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="08a53-148">Choose a field to add.</span></span> <span data-ttu-id="08a53-149">Selecteer **Velden toevoegen** om meer velden te combineren.</span><span class="sxs-lookup"><span data-stu-id="08a53-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="08a53-150">Bevestig de uitsluiting.</span><span class="sxs-lookup"><span data-stu-id="08a53-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="08a53-151">Selecteer **Opslaan** en **Uitvoeren** om de wijzigingen te verwerken.</span><span class="sxs-lookup"><span data-stu-id="08a53-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="08a53-152">De volgorde van velden wijzigen</span><span class="sxs-lookup"><span data-stu-id="08a53-152">Change the order of fields</span></span>

<span data-ttu-id="08a53-153">Sommige entiteiten bevatten meer details dan andere.</span><span class="sxs-lookup"><span data-stu-id="08a53-153">Some entities contain more details than others.</span></span> <span data-ttu-id="08a53-154">Als een entiteit de nieuwste gegevens over een veld bevat, kunt u deze prioriteit geven boven andere entiteiten bij het samenvoegen van waarden.</span><span class="sxs-lookup"><span data-stu-id="08a53-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="08a53-155">Selecteer het samengevoegde veld.</span><span class="sxs-lookup"><span data-stu-id="08a53-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="08a53-156">Selecteer **Meer weergeven** en kies **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="08a53-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="08a53-157">Selecteer in het deelvenster **Velden combineren** **Omhoog/omlaag** om de volgorde in te stellen of gebruik slepen en neerzetten om de velden op de gewenste positie te plaatsen.</span><span class="sxs-lookup"><span data-stu-id="08a53-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="08a53-158">Bevestig de wijziging.</span><span class="sxs-lookup"><span data-stu-id="08a53-158">Confirm the change.</span></span>

1. <span data-ttu-id="08a53-159">Selecteer **Opslaan** en **Uitvoeren** om de wijzigingen te verwerken.</span><span class="sxs-lookup"><span data-stu-id="08a53-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="08a53-160">Uw samenvoeging uitvoeren</span><span class="sxs-lookup"><span data-stu-id="08a53-160">Run your merge</span></span>

<span data-ttu-id="08a53-161">Of u kenmerken handmatig samenvoegt of deze laat samenvoegen door het systeem, u kunt altijd uw samenvoeging uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="08a53-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="08a53-162">Selecteer **Uitvoeren** op de pagina **Samenvoegen** om het proces te starten.</span><span class="sxs-lookup"><span data-stu-id="08a53-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="08a53-163">![Samenvoegen van gegevens opslaan en uitvoeren](media/configure-data-merge-save-run.png "Samenvoegen van gegevens opslaan en uitvoeren")</span><span class="sxs-lookup"><span data-stu-id="08a53-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="08a53-164">Kies **Alleen samenvoegen uitvoeren** als u alleen de uitvoer weerspiegeld wilt zien in de uniforme klantentiteit.</span><span class="sxs-lookup"><span data-stu-id="08a53-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="08a53-165">Downstreamprocessen worden vernieuwd zoals dat is [gedefinieerd in de vernieuwingsplanning](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="08a53-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="08a53-166">Kies **Samenvoegen en downstreamprocessen uitvoeren** om het systeem te vernieuwen met uw wijzigingen.</span><span class="sxs-lookup"><span data-stu-id="08a53-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="08a53-167">Alle processen, inclusief verrijking, segmenten en metingen, worden automatisch opnieuw uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="08a53-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="08a53-168">Nadat alle downstreamprocessen zijn voltooid, weerspiegelen de klantprofielen alle wijzigingen die u hebt aangebracht.</span><span class="sxs-lookup"><span data-stu-id="08a53-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="08a53-169">Als u meer wijzigingen wilt aanbrengen en de stap opnieuw wilt uitvoeren, kunt u een samenvoeging in uitvoering annuleren.</span><span class="sxs-lookup"><span data-stu-id="08a53-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="08a53-170">Selecteer **Vernieuwen...** en selecteer **Taak annuleren** in het zijvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="08a53-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="08a53-171">Er zijn [zes soorten status](system.md#status-types) voor taken/processen.</span><span class="sxs-lookup"><span data-stu-id="08a53-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="08a53-172">Bovendien zijn de meeste processen [afhankelijk van andere stroomafwaartse processen](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="08a53-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="08a53-173">U kunt de status van een proces selecteren om voortgangsdetails te zien van de volledige taak.</span><span class="sxs-lookup"><span data-stu-id="08a53-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="08a53-174">Na het selecteren van **Details bekijken** voor een van de taken vindt u aanvullende informatie: verwerkingstijd, de laatste verwerkingsdatum en alle fouten en waarschuwingen die bij de taak horen.</span><span class="sxs-lookup"><span data-stu-id="08a53-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="08a53-175">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="08a53-175">Next Step</span></span>

<span data-ttu-id="08a53-176">Configureer [activiteiten](activities.md), [verrijking](enrichment-hub.md) of [relaties](relationships.md) voor meer inzichten over uw klanten.</span><span class="sxs-lookup"><span data-stu-id="08a53-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="08a53-177">Als u al activiteiten, een verrijking of segmenten hebt geconfigureerd, worden deze automatisch verwerkt om de nieuwste klantgegevens te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="08a53-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
