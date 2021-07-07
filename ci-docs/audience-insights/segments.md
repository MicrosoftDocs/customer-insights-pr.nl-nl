---
title: Segmenten in doelgroepinzichten
description: Overzicht van segmenten en hoe u segmenten kunt maken en beheren.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 336cab8619c0b80b7b8a38035cae99620baf2873
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306251"
---
# <a name="segments-overview"></a><span data-ttu-id="9c32b-103">Overzicht van segmenten</span><span class="sxs-lookup"><span data-stu-id="9c32b-103">Segments overview</span></span>

<span data-ttu-id="9c32b-104">Met segmenten kunt u uw klanten groeperen op basis van demografische, transactionele of gedragskenmerken.</span><span class="sxs-lookup"><span data-stu-id="9c32b-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="9c32b-105">U kunt segmenten gebruiken om promotiecampagnes, verkoopactiviteiten en acties voor klantenondersteuning te targeten om uw zakelijke doelstellingen te bereiken.</span><span class="sxs-lookup"><span data-stu-id="9c32b-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="9c32b-106">Klantprofielen die overeenkomen met de filters van een segmentdefinitie worden aangeduid als *leden* van een segment.</span><span class="sxs-lookup"><span data-stu-id="9c32b-106">Customer profiles that match the filters of a segment definition are referred as *members* of a segment.</span></span> <span data-ttu-id="9c32b-107">Er zijn enkele [servicelimieten](service-limits.md) van toepassing.</span><span class="sxs-lookup"><span data-stu-id="9c32b-107">Some [service limits](service-limits.md) apply.</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="9c32b-108">Een nieuw segment maken</span><span class="sxs-lookup"><span data-stu-id="9c32b-108">Create a new segment</span></span>

<span data-ttu-id="9c32b-109">Er zijn meerdere manieren om een nieuw segment te maken:</span><span class="sxs-lookup"><span data-stu-id="9c32b-109">There are multiple ways to create a new segment:</span></span> 

- <span data-ttu-id="9c32b-110">Complex segment met segmentbouwer: [Leeg segment](segment-builder.md#create-a-new-segment)</span><span class="sxs-lookup"><span data-stu-id="9c32b-110">Complex segment with segment builder: [Blank segment](segment-builder.md#create-a-new-segment)</span></span>
- <span data-ttu-id="9c32b-111">Eenvoudige segmenten met één operator: [Snel segment](segment-builder.md#quick-segments)</span><span class="sxs-lookup"><span data-stu-id="9c32b-111">Simple segments with one operator: [Quick segment](segment-builder.md#quick-segments)</span></span>
- <span data-ttu-id="9c32b-112">Via AI mogelijk gemaakte manier om vergelijkbare klanten te vinden: [Vergelijkbare klanten](find-similar-customer-segments.md)</span><span class="sxs-lookup"><span data-stu-id="9c32b-112">AI-powered way to find similar customers: [Similar Customers](find-similar-customer-segments.md)</span></span>
- <span data-ttu-id="9c32b-113">Via AI mogelijk gemaakte suggesties op basis van meetcriteria of kenmerken: [Voorgestelde segmenten om meetcriteria te verbeteren](suggested-segments.md)</span><span class="sxs-lookup"><span data-stu-id="9c32b-113">AI-powered suggestions based on measures or attributes: [Suggested segments to improve measures](suggested-segments.md)</span></span>
- <span data-ttu-id="9c32b-114">Suggesties op basis van activiteiten: [Voorgestelde segmenten op basis van klantactiviteit](suggested-segments-activity.md)</span><span class="sxs-lookup"><span data-stu-id="9c32b-114">Suggestions based on activities: [Suggested segments based on customer activity](suggested-segments-activity.md)</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="9c32b-115">Bestaande segmenten beheren</span><span class="sxs-lookup"><span data-stu-id="9c32b-115">Manage existing segments</span></span>

<span data-ttu-id="9c32b-116">Ga naar de pagina **Segmenten** om al uw opgeslagen segmenten te bekijken en te beheren.</span><span class="sxs-lookup"><span data-stu-id="9c32b-116">Go to the **Segments** page, to view all your saved segments and manage them.</span></span>

<span data-ttu-id="9c32b-117">Elk segment wordt weergegeven door een rij met aanvullende informatie over het segment.</span><span class="sxs-lookup"><span data-stu-id="9c32b-117">Each segment is represented by a row that includes additional information about the segment.</span></span>

:::image type="content" source="media/segments-selected-segment.png" alt-text="Geselecteerd segment met vervolgkeuzelijst met opties en beschikbare opties.":::

<span data-ttu-id="9c32b-119">De volgende actie is beschikbaar wanneer u een segment selecteert:</span><span class="sxs-lookup"><span data-stu-id="9c32b-119">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="9c32b-120">**Bekijk** de segmentdetails, inclusief trend van ledentelling en voorbeeld van segmentleden.</span><span class="sxs-lookup"><span data-stu-id="9c32b-120">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="9c32b-121">**Bewerk** het segment om de eigenschappen te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="9c32b-121">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="9c32b-122">**Maak een duplicaat** van een segment.</span><span class="sxs-lookup"><span data-stu-id="9c32b-122">**Create duplicate** of a segment.</span></span> <span data-ttu-id="9c32b-123">U kunt ervoor kiezen om de eigenschappen meteen te bewerken of gewoon het duplicaat op te slaan.</span><span class="sxs-lookup"><span data-stu-id="9c32b-123">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="9c32b-124">**Vernieuw** het segment om de nieuwste gegevens op te nemen.</span><span class="sxs-lookup"><span data-stu-id="9c32b-124">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="9c32b-125">**Activeer** of **Deactiveer** het segment.</span><span class="sxs-lookup"><span data-stu-id="9c32b-125">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="9c32b-126">Segmenten hebben twee mogelijke statussen: actief of inactief.</span><span class="sxs-lookup"><span data-stu-id="9c32b-126">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="9c32b-127">Deze statussen zijn handig bij het bewerken van een segment.</span><span class="sxs-lookup"><span data-stu-id="9c32b-127">These states come in handy when editing a segment.</span></span> <span data-ttu-id="9c32b-128">Voor inactieve segmenten bestaat de segmentdefinitie, maar bevat deze nog geen klanten.</span><span class="sxs-lookup"><span data-stu-id="9c32b-128">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="9c32b-129">Wanneer u een segment activeert, verandert de status van 'inactief' in 'actief' en wordt gezocht naar klanten die voldoen aan de segmentdefinitie.</span><span class="sxs-lookup"><span data-stu-id="9c32b-129">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="9c32b-130">Als een [geplande vernieuwing](system.md#schedule-tab) is geconfigureerd, hebben inactieve segmenten de **Status** **Overgeslagen**, wat aangeeft dat er niet eens is geprobeerd te vernieuwen.</span><span class="sxs-lookup"><span data-stu-id="9c32b-130">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="9c32b-131">Wanneer een inactief segment wordt geactiveerd, wordt het vernieuwd en opgenomen in geplande vernieuwingen.</span><span class="sxs-lookup"><span data-stu-id="9c32b-131">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="9c32b-132">U kunt ook de functionaliteit **Later plannen** in de vervolgkeuzelisjt **Activeren/Deactiveren** gebruiken om een toekomstige datum en tijd op te geven voor activering en deactivering van een bepaald segment.</span><span class="sxs-lookup"><span data-stu-id="9c32b-132">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="9c32b-133">**Wijzig de naam** van het segment.</span><span class="sxs-lookup"><span data-stu-id="9c32b-133">**Rename** the segment.</span></span>
- <span data-ttu-id="9c32b-134">**Download** de lijst van leden als .CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="9c32b-134">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="9c32b-135">**Exports beheren** om exportgerelateerde segmenten te bekijken en te beheren.</span><span class="sxs-lookup"><span data-stu-id="9c32b-135">**Manage exports** to see exports related segment and manage them.</span></span> [<span data-ttu-id="9c32b-136">Meer informatie over exports.</span><span class="sxs-lookup"><span data-stu-id="9c32b-136">Learn more about exports.</span></span>](export-destinations.md)
- <span data-ttu-id="9c32b-137">**Verwijder** het segment.</span><span class="sxs-lookup"><span data-stu-id="9c32b-137">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="9c32b-138">Segmenten vernieuwen</span><span class="sxs-lookup"><span data-stu-id="9c32b-138">Refresh segments</span></span>

<span data-ttu-id="9c32b-139">U kunt alle segmenten tegelijk vernieuwen door **Alles vernieuwen** te selecteren op de pagina **Segmenten** of u kunt een of meerdere segmenten vernieuwen wanneer u deze selecteert en **Vernieuwen** uit de opties kiezen.</span><span class="sxs-lookup"><span data-stu-id="9c32b-139">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="9c32b-140">U kunt ook een terugkerende vernieuwing configureren via **Beheerder** > **Systeem** > **Schema**.</span><span class="sxs-lookup"><span data-stu-id="9c32b-140">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="9c32b-141">Er zijn [zes soorten status](system.md#status-types) voor taken/processen.</span><span class="sxs-lookup"><span data-stu-id="9c32b-141">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="9c32b-142">Bovendien zijn de meeste processen [afhankelijk van andere stroomafwaartse processen](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="9c32b-142">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="9c32b-143">U kunt de status van een proces selecteren om voortgangsdetails te zien van de volledige taak.</span><span class="sxs-lookup"><span data-stu-id="9c32b-143">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="9c32b-144">Na het selecteren van **Details bekijken** voor een van de taken vindt u aanvullende informatie: verwerkingstijd, de laatste verwerkingsdatum en alle fouten en waarschuwingen die bij de taak horen.</span><span class="sxs-lookup"><span data-stu-id="9c32b-144">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="export-segments"></a><span data-ttu-id="9c32b-145">Segmenten exporteren</span><span class="sxs-lookup"><span data-stu-id="9c32b-145">Export segments</span></span>

<span data-ttu-id="9c32b-146">U kunt een segment exporteren vanaf de pagina met segmenten of de [pagina met exports](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="9c32b-146">You can export a segment from the segments page or the [exports page](export-destinations.md).</span></span> 

1. <span data-ttu-id="9c32b-147">Ga naar de pagina **Segmenten**.</span><span class="sxs-lookup"><span data-stu-id="9c32b-147">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="9c32b-148">Selecteer **Meer weergeven [...]** voor het segment dat u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="9c32b-148">Select **Show more [...]** for the segment you want to export.</span></span>

1. <span data-ttu-id="9c32b-149">Selecteer **Exports beheren** uit de vervolgkeuzelijst met acties.</span><span class="sxs-lookup"><span data-stu-id="9c32b-149">Select **Manage exports** from the actions dropdown list.</span></span>

1. <span data-ttu-id="9c32b-150">De pagina **Exports (preview) voor segment** wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="9c32b-150">The page **Exports (preview) for segment** opens.</span></span> <span data-ttu-id="9c32b-151">U kunt alle geconfigureerde exports zien gegroepeerd op exports die het huidige segment wel of niet bevatten.</span><span class="sxs-lookup"><span data-stu-id="9c32b-151">You can see all configured exports grouped by by exports that contain the current segment or don't contain it.</span></span>

   1. <span data-ttu-id="9c32b-152">Als u het geselecteerde segment aan een export wilt toevoegen, selecteert u de export in de lijst en selecteert u **Segment toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="9c32b-152">To add the selected segment to an export, select the export in the list and select **Add segment**.</span></span>

   1. <span data-ttu-id="9c32b-153">Als u een nieuwe export wilt maken met het geselecteerde segment, selecteert u **Export toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="9c32b-153">To create a new export with the selected segment, select **Add export**.</span></span> <span data-ttu-id="9c32b-154">Zie [Een nieuwe export instellen](export-destinations.md#set-up-a-new-export) voor meer informatie over het maken van exports..</span><span class="sxs-lookup"><span data-stu-id="9c32b-154">For more information about creating exports, see [Set up a new export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="9c32b-155">Selecteer **Vorige** om terug te gaan naar de hoofdpagina voor segmenten.</span><span class="sxs-lookup"><span data-stu-id="9c32b-155">Select **Back** to return to the main page for segments.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="9c32b-156">Verwerkingsgeschiedenis en segmentleden weergeven</span><span class="sxs-lookup"><span data-stu-id="9c32b-156">View processing history and segment members</span></span>

<span data-ttu-id="9c32b-157">U kunt geconsolideerde gegevens over een segment bekijken door de details te controleren.</span><span class="sxs-lookup"><span data-stu-id="9c32b-157">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="9c32b-158">Selecteer op de pagina **Segmenten** het segment dat u wilt controleren.</span><span class="sxs-lookup"><span data-stu-id="9c32b-158">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="9c32b-159">Het bovenste deel van de pagina bevat een trendgrafiek waarin wijzigingen in het aantal leden worden gevisualiseerd.</span><span class="sxs-lookup"><span data-stu-id="9c32b-159">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="9c32b-160">Beweeg over gegevenspunten om het aantal leden op een specifieke datum te bekijken.</span><span class="sxs-lookup"><span data-stu-id="9c32b-160">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="9c32b-161">U kunt het tijdsbereik van de visualisatie bijwerken.</span><span class="sxs-lookup"><span data-stu-id="9c32b-161">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9c32b-162">![Tijdsbereik van segment](media/segment-time-range.png "Tijdsbereik van segment")</span><span class="sxs-lookup"><span data-stu-id="9c32b-162">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="9c32b-163">Het onderste gedeelte bevat een lijst met de segmentleden.</span><span class="sxs-lookup"><span data-stu-id="9c32b-163">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="9c32b-164">Velden die in deze lijst worden weergegeven, zijn gebaseerd op de kenmerken van de entiteiten van uw segment.</span><span class="sxs-lookup"><span data-stu-id="9c32b-164">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="9c32b-165">De lijst is een voorbeeld van de overeenkomende segmentleden en toont de eerste 100 records van uw segment, zodat u het snel kunt evalueren en indien nodig de definities kunt bekijken.</span><span class="sxs-lookup"><span data-stu-id="9c32b-165">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="9c32b-166">Als u alle overeenkomende records wilt bekijken, moet u [het segment exporteren](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="9c32b-166">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
