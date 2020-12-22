---
title: Entiteiten samenvoegen in gegevensharmonisatie
description: Voeg entiteiten samen om geharmoniseerde klantprofielen te maken.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 045fd8d8f65161b91caabed2ac52494dc4fb3910
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405505"
---
# <a name="merge-entities"></a><span data-ttu-id="4ca19-103">Entiteiten samenvoegen</span><span class="sxs-lookup"><span data-stu-id="4ca19-103">Merge entities</span></span>

<span data-ttu-id="4ca19-104">De samenvoegingsfase is de laatste fase in het proces voor gegevensharmonisatie.</span><span class="sxs-lookup"><span data-stu-id="4ca19-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="4ca19-105">Het doel is het afstemmen van conflicterende gegevens.</span><span class="sxs-lookup"><span data-stu-id="4ca19-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="4ca19-106">Voorbeelden van conflicterende gegevens kunnen een klantnaam zijn die in twee van uw gegevenssets is gevonden, maar in elk een beetje anders verschijnt ("Grant Marshall" versus "Grant Marshal"), of een telefoonnummer met een andere indeling(617-803-091X versus 617803091X).</span><span class="sxs-lookup"><span data-stu-id="4ca19-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="4ca19-107">Het samenvoegen van die conflicterende gegevenspunten gebeurt op een kenmerk-per-kenmerkbasis.</span><span class="sxs-lookup"><span data-stu-id="4ca19-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="4ca19-108">Na het voltooien van de [afstemmingsfase](match-entities.md), kunt u de samenvoegingsfase starten door de tegel **Samenvoegen** te selecteren op de pagina **Harmoniseren**.</span><span class="sxs-lookup"><span data-stu-id="4ca19-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="4ca19-109">Systeemaanbevelingen bekijken</span><span class="sxs-lookup"><span data-stu-id="4ca19-109">Review system recommendations</span></span>

<span data-ttu-id="4ca19-110">Op de pagina **Samenvoegen** kunt u kenmerken kiezen en uitsluiten die moeten worden samengevoegd binnen uw geharmoniseerde klantprofielentiteit (het resultaat van het configuratieproces).</span><span class="sxs-lookup"><span data-stu-id="4ca19-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="4ca19-111">Sommige kenmerken worden automatisch door het systeem samengevoegd.</span><span class="sxs-lookup"><span data-stu-id="4ca19-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="4ca19-112">Samengevoegde kenmerken bekijken</span><span class="sxs-lookup"><span data-stu-id="4ca19-112">View merged attributes</span></span>

<span data-ttu-id="4ca19-113">Selecteer het samengevoegde kenmerk om de kenmerken te bekijken die zijn opgenomen in een van uw automatisch samengevoegde kenmerken.</span><span class="sxs-lookup"><span data-stu-id="4ca19-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="4ca19-114">De twee kenmerken waaruit dat samengevoegde kenmerk is samengesteld, verschijnen in twee nieuwe rijen onder het samengevoegde kenmerk.</span><span class="sxs-lookup"><span data-stu-id="4ca19-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4ca19-115">![Samengevoegd kenmerk selecteren](media/configure-data-merge-profile-attributes.png "Samengevoegd kenmerk selecteren")</span><span class="sxs-lookup"><span data-stu-id="4ca19-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="4ca19-116">Aparte samengevoegde kenmerken</span><span class="sxs-lookup"><span data-stu-id="4ca19-116">Separate merged attributes</span></span>

<span data-ttu-id="4ca19-117">Als u een van de automatisch samengevoegde kenmerken wilt scheiden of de samenvoeging ongedaan wilt maken, zoekt u het kenmerk in de tabel **Profielkenmerken**.</span><span class="sxs-lookup"><span data-stu-id="4ca19-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="4ca19-118">Selecteer de knop met de drie puntjes (…).</span><span class="sxs-lookup"><span data-stu-id="4ca19-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="4ca19-119">Selecteer **Afzonderlijke velden** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="4ca19-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="4ca19-120">Samengevoegde kenmerken verwijderen</span><span class="sxs-lookup"><span data-stu-id="4ca19-120">Remove merged attributes</span></span>

<span data-ttu-id="4ca19-121">Als u een kenmerk wilt uitsluiten van de uiteindelijke klantprofielentiteit, kunt u deze vinden in de tabel **Profielkenmerken**.</span><span class="sxs-lookup"><span data-stu-id="4ca19-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="4ca19-122">Selecteer de knop met de drie puntjes (…).</span><span class="sxs-lookup"><span data-stu-id="4ca19-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="4ca19-123">Selecteer **Niet samenvoegen** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="4ca19-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="4ca19-124">Het kenmerk wordt verplaatst naar de sectie **Verwijderd uit klantenrecord**.</span><span class="sxs-lookup"><span data-stu-id="4ca19-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="4ca19-125">Handmatig een samengevoegd kenmerk toevoegen</span><span class="sxs-lookup"><span data-stu-id="4ca19-125">Manually add a merged attribute</span></span>

<span data-ttu-id="4ca19-126">Ga naar de pagina **Samenvoegen** om een samengevoegd kenmerk toe te voegen .</span><span class="sxs-lookup"><span data-stu-id="4ca19-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="4ca19-127">Selecteer **Samengevoegd kenmerk toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="4ca19-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="4ca19-128">Geef een **naam** op om het later te kunnen identificeren op de pagina **Samenvoegen**.</span><span class="sxs-lookup"><span data-stu-id="4ca19-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="4ca19-129">Geef desgewenst een **weergavenaam** op die verschijnt in de geharmoniseerde entiteit Klantprofiel.</span><span class="sxs-lookup"><span data-stu-id="4ca19-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="4ca19-130">Configureeer **Dubbele kenmerken selecteren** om de kenmerken te selecteren die u wilt samenvoegen uit de afgestemde entiteiten.</span><span class="sxs-lookup"><span data-stu-id="4ca19-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="4ca19-131">U kunt ook naar kenmerken zoeken.</span><span class="sxs-lookup"><span data-stu-id="4ca19-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="4ca19-132">Stel de optie **Rangschikken op basis van belang** in om het ene kenmerk een hogere prioriteit te geven dan de andere.</span><span class="sxs-lookup"><span data-stu-id="4ca19-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="4ca19-133">Als bijvoorbeeld de entiteit *WebAccountCSV* de meest nauwkeurige gegevens over het kenmerk *Volledige namen* bevat, kunt u deze entiteit prioriteit geven boven *ContactCSV* door *WebAccountCSV* te selecteren.</span><span class="sxs-lookup"><span data-stu-id="4ca19-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="4ca19-134">Het resultaat is dat *WebAccountCSV* de hoogste prioriteit krijgt, terwijl *ContactCSV* de tweede prioriteit krijgt bij het ophalen van waarden voor het kenmerk *Volledige naam*.</span><span class="sxs-lookup"><span data-stu-id="4ca19-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="4ca19-135">Uw samenvoeging uitvoeren</span><span class="sxs-lookup"><span data-stu-id="4ca19-135">Run your merge</span></span>

<span data-ttu-id="4ca19-136">Of u kenmerken handmatig samenvoegt of deze laat samenvoegen door het systeem, u kunt altijd uw samenvoeging uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="4ca19-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="4ca19-137">Selecteer **Uitvoeren** op de pagina **Samenvoegen** om het proces te starten.</span><span class="sxs-lookup"><span data-stu-id="4ca19-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4ca19-138">![Samenvoegen van gegevens opslaan en uitvoeren](media/configure-data-merge-save-run.png "Samenvoegen van gegevens opslaan en uitvoeren")</span><span class="sxs-lookup"><span data-stu-id="4ca19-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="4ca19-139">Om aanvullende wijzigingen aan te brengen en de stap opnieuw uit te voeren, kunt u een lopende samenvoeging annuleren.</span><span class="sxs-lookup"><span data-stu-id="4ca19-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="4ca19-140">Selecteer **Vernieuwen...** en selecteer **Taak annuleren** in het zijvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="4ca19-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="4ca19-141">Nadat de tekst **Vernieuwen...** is gewijzigd in **Geslaagd**, is de samenvoeging voltooid en zijn tegenstrijdigheden in uw gegevens opgelost volgens het door u gedefinieerde beleid.</span><span class="sxs-lookup"><span data-stu-id="4ca19-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="4ca19-142">Samengevoegde en niet-samengevoegde kenmerken worden opgenomen in de geharmoniseerde profielentiteit.</span><span class="sxs-lookup"><span data-stu-id="4ca19-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="4ca19-143">Uitgesloten kenmerken worden niet opgenomen in de geharmoniseerde profielentiteit.</span><span class="sxs-lookup"><span data-stu-id="4ca19-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="4ca19-144">Als het niet de eerste keer was dat u met succes een samenvoeging hebt uitgevoerd, worden alle stroomafwaartse processen, inclusief verrijking, segmentatie en meetcriteria, automatisch opnieuw uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="4ca19-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="4ca19-145">Nadat alle stroomafwaartse processen opnieuw zijn uitgevoerd, weerspiegelen de klantprofielen alle wijzigingen die u hebt aangebracht.</span><span class="sxs-lookup"><span data-stu-id="4ca19-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="4ca19-146">Er zijn [zes soorten status](system.md#status-types) voor taken/processen.</span><span class="sxs-lookup"><span data-stu-id="4ca19-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="4ca19-147">Bovendien zijn de meeste processen [afhankelijk van andere stroomafwaartse processen](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="4ca19-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="4ca19-148">U kunt de status van een proces selecteren om voortgangsdetails te zien van de volledige taak.</span><span class="sxs-lookup"><span data-stu-id="4ca19-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="4ca19-149">Na het selecteren van **Details bekijken** voor een van de taken vindt u aanvullende informatie: verwerkingstijd, de laatste verwerkingsdatum en alle fouten en waarschuwingen die bij de taak horen.</span><span class="sxs-lookup"><span data-stu-id="4ca19-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="4ca19-150">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="4ca19-150">Next Step</span></span>

<span data-ttu-id="4ca19-151">Configureer [activiteiten](activities.md), [verrijking](enrichment-microsoft-graph.md) of [relaties](relationships.md) voor meer inzichten over uw klanten.</span><span class="sxs-lookup"><span data-stu-id="4ca19-151">Configure [activities](activities.md), [enrichment](enrichment-microsoft-graph.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="4ca19-152">Als u al activiteiten, verrijking of relaties hebt geconfigureerd of segmenten hebt gedefinieerd, worden deze automatisch verwerkt om de nieuwste klantgegevens te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="4ca19-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>


