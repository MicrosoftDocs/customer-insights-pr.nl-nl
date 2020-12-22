---
title: Metingen maken en bewerken
description: Definieer klantgerelateerde meetcriteria om de prestaties van bepaalde bedrijfsgebieden te analyseren en weer te geven.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405508"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="87942-103">Meetcriteria definiëren en beheren</span><span class="sxs-lookup"><span data-stu-id="87942-103">Define and manage measures</span></span>

<span data-ttu-id="87942-104">**Meetcriteria** vertegenwoordigen key performance indicators (KPI's) die de prestaties en gezondheid van specifieke bedrijfsgebieden weerspiegelen.</span><span class="sxs-lookup"><span data-stu-id="87942-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="87942-105">Doelgroepinzichten bieden een intuïtieve ervaring voor het bouwen van verschillende soorten metingen, met behulp van een querybuilder waarvoor u uw metingen niet handmatig hoeft te coderen of te valideren.</span><span class="sxs-lookup"><span data-stu-id="87942-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="87942-106">U kunt uw zakelijke meetcriteria bijhouden op de pagina **Start**, meetcriteria voor specifieke klanten bekijken op de **Klantkaart** en meetcriteria gebruiken om klantsegmenten op de pagina **Segmenten** te definiëren.</span><span class="sxs-lookup"><span data-stu-id="87942-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="87942-107">Een meetcriterium maken</span><span class="sxs-lookup"><span data-stu-id="87942-107">Create a measure</span></span>

<span data-ttu-id="87942-108">In deze sectie wordt u begeleid bij het maken van een geheel nieuw meetcriteria.</span><span class="sxs-lookup"><span data-stu-id="87942-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="87942-109">U kunt meetcriteria samenstellen met gegevens uit meerdere gegevensbronnen die zijn verbonden via de entiteit Klant.</span><span class="sxs-lookup"><span data-stu-id="87942-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="87942-110">Er zijn enkele [servicelimieten](service-limits.md) van toepassing.</span><span class="sxs-lookup"><span data-stu-id="87942-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="87942-111">Ga in doelgroepinzichten naar **Metingen**.</span><span class="sxs-lookup"><span data-stu-id="87942-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="87942-112">Selecteer **Nieuw meetcriterium**.</span><span class="sxs-lookup"><span data-stu-id="87942-112">Select **New measure**.</span></span>

3. <span data-ttu-id="87942-113">Kies het meetcriteria **Type**:</span><span class="sxs-lookup"><span data-stu-id="87942-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="87942-114">**Klantkenmerk**: een enkel veld per klant dat een score, waarde of status voor de klant aangeeft.</span><span class="sxs-lookup"><span data-stu-id="87942-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="87942-115">Klantkenmerken worden gemaakt als kenmerken in een nieuwe, door het systeem gegenereerde entiteit genaamd **Customer_Measure**.</span><span class="sxs-lookup"><span data-stu-id="87942-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="87942-116">**Meetcriterium klant**: inzichten in klantgedrag met uitsplitsing naar geselecteerde dimensies.</span><span class="sxs-lookup"><span data-stu-id="87942-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="87942-117">Voor elk meetcriterium wordt een nieuwe entiteit gegenereerd, mogelijk met meerdere records per klant.</span><span class="sxs-lookup"><span data-stu-id="87942-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="87942-118">**Zakelijk meetcriterium**: houdt uw bedrijfsprestaties en de gezondheid van het bedrijf bij.</span><span class="sxs-lookup"><span data-stu-id="87942-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="87942-119">Zakelijke meetcriteria kunnen twee verschillende uitvoeren hebben: een numerieke uitvoer die wordt weergegeven op de pagina **Start** of een nieuwe entiteit die u vindt op de pagina **Entiteiten**.</span><span class="sxs-lookup"><span data-stu-id="87942-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="87942-120">Geef een **naam** en een optionele **weergavenaam** op en selecteer daarna **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="87942-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="87942-121">Selecteer in de sectie **Entiteiten** de eerste entiteit in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="87942-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="87942-122">Op dit punt moet u beslissen of aanvullende entiteiten nodig zijn als onderdeel van de definitie van uw meetcriterium.</span><span class="sxs-lookup"><span data-stu-id="87942-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="87942-123">![Definitie van meetcriterium](media/measure-definition.png "Definitie van meetcriterium")</span><span class="sxs-lookup"><span data-stu-id="87942-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="87942-124">Als u meer entiteiten wilt toevoegen, selecteert u **Entiteit toevoegen** en selecteert u entiteiten die u voor het meetcriterium wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="87942-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="87942-125">U kunt alleen entiteiten selecteren die relaties hebben met uw eerste entiteit.</span><span class="sxs-lookup"><span data-stu-id="87942-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="87942-126">Zie [Relaties](relationships.md) voor meer informatie over het definiëren van relaties.</span><span class="sxs-lookup"><span data-stu-id="87942-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="87942-127">Optioneel kunt u variabelen configureren.</span><span class="sxs-lookup"><span data-stu-id="87942-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="87942-128">Selecteer in de sectie **Variabelen** de optie **Nieuwe variabele**.</span><span class="sxs-lookup"><span data-stu-id="87942-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="87942-129">Variabelen zijn berekeningen die worden uitgevoerd op elk van uw geselecteerde records.</span><span class="sxs-lookup"><span data-stu-id="87942-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="87942-130">Bijvoorbeeld het optellen van verkopen via point-of-sale (POS) en online verkopen voor elk van de records van uw klanten.</span><span class="sxs-lookup"><span data-stu-id="87942-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="87942-131">Geef een **naam** op voor de variabele.</span><span class="sxs-lookup"><span data-stu-id="87942-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="87942-132">Kies in het gebied **Expressie** een veld waarmee u uw berekening wilt beginnen.</span><span class="sxs-lookup"><span data-stu-id="87942-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="87942-133">Typ een expressie in het gebied **Expressie** terwijl u meer velden kiest om in uw berekening op te nemen.</span><span class="sxs-lookup"><span data-stu-id="87942-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="87942-134">Momenteel worden alleen rekenkundige expressies ondersteund.</span><span class="sxs-lookup"><span data-stu-id="87942-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="87942-135">Bovendien wordt variabele berekening niet ondersteund voor entiteiten uit verschillende [entiteitspaden](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="87942-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="87942-136">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="87942-136">Select **Done**.</span></span>

11. <span data-ttu-id="87942-137">In de sectie **Definitie van meetcriterium** definieert u hoe uw gekozen entiteiten en berekende variabelen worden geaggregeerd in een nieuwe entiteit Meetcriterium of een nieuw kenmerk Meetcriterium.</span><span class="sxs-lookup"><span data-stu-id="87942-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="87942-138">Selecteer **Nieuwe dimensie**.</span><span class="sxs-lookup"><span data-stu-id="87942-138">Select **New dimension**.</span></span> <span data-ttu-id="87942-139">Een dimensie kan worden beschouwd als een functie *groeperen op*.</span><span class="sxs-lookup"><span data-stu-id="87942-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="87942-140">De gegevensuitvoer van uw entiteit of kenmerk Meetcriterium wordt gegroepeerd op basis van al uw gedefinieerde dimensies.</span><span class="sxs-lookup"><span data-stu-id="87942-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="87942-141">![Aggregatiecyclus kiezen](media/measures-businessreport-measure-definition2.png "Aggregatiecyclus kiezen")</span><span class="sxs-lookup"><span data-stu-id="87942-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="87942-142">Selecteer of voer de volgende informatie in als onderdeel van de definitie van uw dimensie:</span><span class="sxs-lookup"><span data-stu-id="87942-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="87942-143">**Entiteit**: als u een entiteit Meetcriterium definieert, moet dit ten minste één kenmerk bevatten.</span><span class="sxs-lookup"><span data-stu-id="87942-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="87942-144">Als u een kenmerk Meetcriterium definieert, bevat dit standaard slechts één kenmerk.</span><span class="sxs-lookup"><span data-stu-id="87942-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="87942-145">Deze selectie gaat over het kiezen van de entiteit die dat kenmerk bevat.</span><span class="sxs-lookup"><span data-stu-id="87942-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="87942-146">**Veld**: kies het specifieke kenmerk dat u wilt opnemen in uw entiteit of kenmerk Meetcriterium.</span><span class="sxs-lookup"><span data-stu-id="87942-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="87942-147">**Bucket**: kies of u gegevens wilt samenvoegen op dagelijkse, maandelijkse of jaarlijkse basis.</span><span class="sxs-lookup"><span data-stu-id="87942-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="87942-148">Dit is alleen een vereiste selectie als u een kenmerk Datumtype hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="87942-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="87942-149">**Als**: definieert de naam van uw nieuwe veld.</span><span class="sxs-lookup"><span data-stu-id="87942-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="87942-150">**Weergavenaam**: definieert de weergavenaam van uw veld.</span><span class="sxs-lookup"><span data-stu-id="87942-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="87942-151">Uw zakelijke meetcriterium wordt opgeslagen als een entiteit met één nummer en verschijnt op de pagina **Start** tenzij u meer dimensies toevoegt aan uw meetcriterium.</span><span class="sxs-lookup"><span data-stu-id="87942-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="87942-152">Na het toevoegen van meer dimensies zal het meetcriterium *niet* worden weergegeven op de pagina **Start**.</span><span class="sxs-lookup"><span data-stu-id="87942-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="87942-153">Voeg optioneel aggregatiefuncties toe.</span><span class="sxs-lookup"><span data-stu-id="87942-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="87942-154">Elke aggregatie die u maakt, resulteert in een nieuwe waarde binnen uw entiteit of kenmerk Meetcriterium.</span><span class="sxs-lookup"><span data-stu-id="87942-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="87942-155">Ondersteunde aggregatiefuncties zijn: **Min**, **Max**, **Gemiddelde**, **Mediaan**, **Som**, **Aantal unieke**, **Eerste** (neemt de eerste record van een dimensiewaarde) en **Laatste** (neemt de laatste record die aan een dimensiewaarde is toegevoegd).</span><span class="sxs-lookup"><span data-stu-id="87942-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="87942-156">Selecteer **Opslaan** om uw wijzigingen toe te passen op het meetcriterium.</span><span class="sxs-lookup"><span data-stu-id="87942-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="87942-157">Uw meetcriteria beheren</span><span class="sxs-lookup"><span data-stu-id="87942-157">Manage your measures</span></span>

<span data-ttu-id="87942-158">Nadat u ten minste één meting hebt gemaakt, ziet u een lijst met metingen op de pagina **Metingen**.</span><span class="sxs-lookup"><span data-stu-id="87942-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="87942-159">U vindt informatie over het type meetcriterium, de maker, de aanmaakdatum en -tijd, de datum en tijd van laatste bewerking, de status (of het meetcriterium actief, inactief of mislukt is) en de meest recente vernieuwingsdatum en -tijd.</span><span class="sxs-lookup"><span data-stu-id="87942-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="87942-160">Wanneer u een meetcriterium uit de lijst selecteert, kunt u een voorbeeld van de uitvoer bekijken.</span><span class="sxs-lookup"><span data-stu-id="87942-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="87942-161">Selecteer om al uw meetcriteria tegelijkertijd te vernieuwen de optie **Alles vernieuwen** zonder een specifiek meetcriterium te selecteren.</span><span class="sxs-lookup"><span data-stu-id="87942-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="87942-162">![Acties om afzonderlijke meetcriteria te beheren](media/measure-actions.png "Acties om afzonderlijke meetcriteria te beheren")</span><span class="sxs-lookup"><span data-stu-id="87942-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="87942-163">U kunt ook een meetcriterium uit de lijst selecteren en een van de volgende acties uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="87942-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="87942-164">Selecteer de naam van het meetcriterium om de details te zien.</span><span class="sxs-lookup"><span data-stu-id="87942-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="87942-165">**Bewerk** de configuratie van het meetcriterium.</span><span class="sxs-lookup"><span data-stu-id="87942-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="87942-166">**Hernoem** het meetcriterium.</span><span class="sxs-lookup"><span data-stu-id="87942-166">**Rename** the measure.</span></span>
- <span data-ttu-id="87942-167">**Verwijder** het meetcriterium.</span><span class="sxs-lookup"><span data-stu-id="87942-167">**Delete** the measure.</span></span>
- <span data-ttu-id="87942-168">Selecteer het beletselteken (...) en vervolgens **Vernieuwen** om het vernieuwingsproces voor het meetcriterium te starten.</span><span class="sxs-lookup"><span data-stu-id="87942-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="87942-169">Selecteer het beletselteken (...) en vervolgens **Downloaden** om een .CSV-bestand van het meetcriterium op te halen.</span><span class="sxs-lookup"><span data-stu-id="87942-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="87942-170">Er zijn [zes soorten status](system.md#status-types) voor taken/processen.</span><span class="sxs-lookup"><span data-stu-id="87942-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="87942-171">Bovendien zijn de meeste processen [afhankelijk van andere stroomafwaartse processen](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="87942-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="87942-172">U kunt de status van een proces selecteren om voortgangsdetails te zien van de volledige taak.</span><span class="sxs-lookup"><span data-stu-id="87942-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="87942-173">Na het selecteren van **Details bekijken** voor een van de taken vindt u aanvullende informatie: verwerkingstijd, de laatste verwerkingsdatum en alle fouten en waarschuwingen die bij de taak horen.</span><span class="sxs-lookup"><span data-stu-id="87942-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="87942-174">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="87942-174">Next step</span></span>

<span data-ttu-id="87942-175">U kunt bestaande meetcriteria gebruiken om uw eerste klantensegment ter maken op de pagina **Segmenten**.</span><span class="sxs-lookup"><span data-stu-id="87942-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="87942-176">Zie [Segmenten](segments.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="87942-176">For more information, see [Segments](segments.md).</span></span>
