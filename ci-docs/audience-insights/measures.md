---
title: Metingen maken en beheren
description: Definieer maatregelen om de prestaties van uw bedrijf te analyseren en weer te geven.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 202ea22d290be04e54ce9676b6b693162354607f
ms.sourcegitcommit: d3eb07dcc72624a2d5cfc95c7ea9faaa2c1b6001
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/16/2021
ms.locfileid: "5654726"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="e42d5-103">Meetcriteria definiëren en beheren</span><span class="sxs-lookup"><span data-stu-id="e42d5-103">Define and manage measures</span></span>

<span data-ttu-id="e42d5-104">Metingen helpen u het klantgedrag en de bedrijfsprestaties beter te begrijpen door relevante waarden te halen uit [geharmoniseerde profielen](data-unification.md)​.</span><span class="sxs-lookup"><span data-stu-id="e42d5-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="e42d5-105">Een bedrijf wil bijvoorbeeld de *totale uitgaven per klant* zien om inzicht te krijgen in de aankoopgeschiedenis van individuele klanten.</span><span class="sxs-lookup"><span data-stu-id="e42d5-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="e42d5-106">Of meet *totale verkoop van het bedrijf* om inzicht te krijgen in de totale inkomsten van het hele bedrijf.</span><span class="sxs-lookup"><span data-stu-id="e42d5-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="e42d5-107">Metingen worden gemaakt met behulp van de metingenbouwer, een gegevensqueryplatform met verschillende operators en eenvoudige toewijzingsopties.</span><span class="sxs-lookup"><span data-stu-id="e42d5-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="e42d5-108">Hiermee kunt u de gegevens filteren, resultaten groeperen, [entiteitsrelatiepaden](relationships.md) detecteren en een voorbeeld van de uitvoer bekijken.</span><span class="sxs-lookup"><span data-stu-id="e42d5-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="e42d5-109">Gebruik de metingenbouwer om bedrijfsactiviteiten te plannen door klantgegevens op te vragen en inzichten te verkrijgen.</span><span class="sxs-lookup"><span data-stu-id="e42d5-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="e42d5-110">Als u bijvoorbeeld een meting maakt van *totale uitgaven per klant* en *totaal rendement per klant*, helpt dit u een groep klanten met hoge uitgaven en toch een hoog rendement te identificeren.</span><span class="sxs-lookup"><span data-stu-id="e42d5-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="e42d5-111">U kunt [een segment maken](segments.md) om de volgende beste acties aan te sturen.</span><span class="sxs-lookup"><span data-stu-id="e42d5-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="e42d5-112">Een meetcriterium maken</span><span class="sxs-lookup"><span data-stu-id="e42d5-112">Create a measure</span></span>

<span data-ttu-id="e42d5-113">In deze sectie wordt uitgelegd hoe u een geheel nieuwe meting maakt.</span><span class="sxs-lookup"><span data-stu-id="e42d5-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="e42d5-114">U kunt een meting bouwen met gegevenskenmerken van gegevensentiteiten waarvoor een relatie is ingesteld om verbinding te maken met de entiteit Klant.</span><span class="sxs-lookup"><span data-stu-id="e42d5-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="e42d5-115">Ga in doelgroepinzichten naar **Metingen**.</span><span class="sxs-lookup"><span data-stu-id="e42d5-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="e42d5-116">Selecteer **Nieuw**.</span><span class="sxs-lookup"><span data-stu-id="e42d5-116">Select **New**.</span></span>

1. <span data-ttu-id="e42d5-117">Selecteer **Naam bewerken** en geef een **Naam** op voor de meting.</span><span class="sxs-lookup"><span data-stu-id="e42d5-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="e42d5-118">Als uw nieuwe meetconfiguratie slechts twee velden heeft, bijvoorbeeld CustomerID en één berekening, wordt de uitvoer als een nieuwe kolom toegevoegd aan de door het systeem gegenereerde entiteit met de naam Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="e42d5-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="e42d5-119">En u kunt de waarde van de meting zien in het geharmoniseerde klantprofiel.</span><span class="sxs-lookup"><span data-stu-id="e42d5-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="e42d5-120">Andere metingen zullen hun eigen entiteiten genereren.</span><span class="sxs-lookup"><span data-stu-id="e42d5-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="e42d5-121">Kies in het configuratiegebied de aggregatiefunctie in het vervolgkeuzemenu **Functie selecteren**.</span><span class="sxs-lookup"><span data-stu-id="e42d5-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="e42d5-122">Aggregatiefuncties omvatten:</span><span class="sxs-lookup"><span data-stu-id="e42d5-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="e42d5-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="e42d5-123">**Sum**</span></span>
   - <span data-ttu-id="e42d5-124">**Gemiddeld**</span><span class="sxs-lookup"><span data-stu-id="e42d5-124">**Average**</span></span>
   - <span data-ttu-id="e42d5-125">**Tellen**</span><span class="sxs-lookup"><span data-stu-id="e42d5-125">**Count**</span></span>
   - <span data-ttu-id="e42d5-126">**Aantal unieke**</span><span class="sxs-lookup"><span data-stu-id="e42d5-126">**Count Unique**</span></span>
   - <span data-ttu-id="e42d5-127">**Max.**</span><span class="sxs-lookup"><span data-stu-id="e42d5-127">**Max**</span></span>
   - <span data-ttu-id="e42d5-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="e42d5-128">**Min**</span></span>
   - <span data-ttu-id="e42d5-129">**Eerste**: neemt de eerste waarde van de gegevensrecord</span><span class="sxs-lookup"><span data-stu-id="e42d5-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="e42d5-130">**Laatste**: neemt de laatste waarde die aan de gegevensrecord is toegevoegd</span><span class="sxs-lookup"><span data-stu-id="e42d5-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operators voor de berekening van metingen.":::

1. <span data-ttu-id="e42d5-132">Selecteer **Kenmerk toevoegen** om de gegevens te selecteren die u nodig hebt om deze meting te maken.</span><span class="sxs-lookup"><span data-stu-id="e42d5-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="e42d5-133">Selecteer het tabblad **Kenmerken**.</span><span class="sxs-lookup"><span data-stu-id="e42d5-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="e42d5-134">Gegevensentiteit: kies de entiteit die het kenmerk bevat dat u wilt meten.</span><span class="sxs-lookup"><span data-stu-id="e42d5-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="e42d5-135">Gegevenskenmerk: kies het kenmerk dat u in de aggregatiefunctie wilt gebruiken om de meting te berekenen.</span><span class="sxs-lookup"><span data-stu-id="e42d5-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="e42d5-136">U kunt slechts één kenmerk tegelijk selecteren.</span><span class="sxs-lookup"><span data-stu-id="e42d5-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="e42d5-137">U kunt ook een gegevenskenmerk van een bestaande meting selecteren door het tabblad **Metingen** te selecteren. Of u kunt zoeken naar de naam van een entiteit of meting.</span><span class="sxs-lookup"><span data-stu-id="e42d5-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="e42d5-138">Selecteer **Toevoegen** om het geselecteerde kenmerk aan de meting toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="e42d5-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Selecteer een kenmerk om in berekeningen te gebruiken.":::

1. <span data-ttu-id="e42d5-140">Om complexere metingen te bouwen, kunt u meer kenmerken toevoegen of wiskundige operatoren gebruiken voor uw meetfunctie.</span><span class="sxs-lookup"><span data-stu-id="e42d5-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Maak een complexe meting met wiskundige operatoren.":::

1. <span data-ttu-id="e42d5-142">Om filters toe te voegen, selecteert u het **Filter** in het configuratiegebied.</span><span class="sxs-lookup"><span data-stu-id="e42d5-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="e42d5-143">Selecteer in de sectie **Kenmerk toevoegen** van het deelvenster **Filters** het kenmerk dat u wilt gebruiken om filters te maken.</span><span class="sxs-lookup"><span data-stu-id="e42d5-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="e42d5-144">Stel de filteroperatoren in om het filter voor elk geselecteerd kenmerk te definiëren.</span><span class="sxs-lookup"><span data-stu-id="e42d5-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="e42d5-145">Selecteer **Toepassen** om de filters aan de meting toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="e42d5-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="e42d5-146">Om dimensies toe te voegen, selecteert u **Dimensie** in het configuratiegebied.</span><span class="sxs-lookup"><span data-stu-id="e42d5-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="e42d5-147">Dimensies worden weergegeven als kolommen in de entiteit voor metingenuitvoer.</span><span class="sxs-lookup"><span data-stu-id="e42d5-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="e42d5-148">Selecteer **Dimensies bewerken** om gegevenskenmerken toe te voegen waarop u de meetwaarden wilt groeperen.</span><span class="sxs-lookup"><span data-stu-id="e42d5-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="e42d5-149">Bijvoorbeeld plaats of gender.</span><span class="sxs-lookup"><span data-stu-id="e42d5-149">For example, city or gender.</span></span> <span data-ttu-id="e42d5-150">Standaard is de dimensie *CustomerID* geselecteerd om *metingen op klantniveau* te maken.</span><span class="sxs-lookup"><span data-stu-id="e42d5-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="e42d5-151">U kunt de standaarddimensie verwijderen als u *metingen op bedrijfsniveau*​wilt maken.</span><span class="sxs-lookup"><span data-stu-id="e42d5-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="e42d5-152">Selecteer **Gereed** om de dimensies aan de meting toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="e42d5-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="e42d5-153">Als er meerdere paden zijn tussen de gegevensentiteit die u hebt toegewezen en de entiteit *Klant*, moet u een van de geïdentificeerde [entiteitsrelatiepaden​](relationships.md) kiezen.</span><span class="sxs-lookup"><span data-stu-id="e42d5-153">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="e42d5-154">Meetresultaten kunnen variëren, afhankelijk van het geselecteerde pad.</span><span class="sxs-lookup"><span data-stu-id="e42d5-154">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="e42d5-155">Selecteer **Gegevensvoorkeuren** en kies het entiteitspad dat moet worden gebruikt om uw meting te identificeren.</span><span class="sxs-lookup"><span data-stu-id="e42d5-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="e42d5-156">Als er maar één pad is naar de entiteit *Klant*, wordt dit besturingselement niet weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e42d5-156">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="e42d5-157">Selecteer **Gereed** om uw selectie toe te passen.</span><span class="sxs-lookup"><span data-stu-id="e42d5-157">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Selecteer het entiteitspad voor de meting.":::

1. <span data-ttu-id="e42d5-159">Als u meer berekeningen voor de meting wilt toevoegen, selecteert u **Nieuwe berekening**​.</span><span class="sxs-lookup"><span data-stu-id="e42d5-159">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="e42d5-160">U kunt alleen entiteiten op hetzelfde entiteitspad gebruiken voor nieuwe berekeningen.</span><span class="sxs-lookup"><span data-stu-id="e42d5-160">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="e42d5-161">Meer berekeningen worden weergegeven als nieuwe kolommen in de entiteit voor metingenuitvoer.</span><span class="sxs-lookup"><span data-stu-id="e42d5-161">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="e42d5-162">Selecteer **...** in de berekening om een berekening uit een meting te **Dupliceren** **Naam wijzigen** of te **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="e42d5-162">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="e42d5-163">In het gebied **Voorbeeld** ziet u het gegevensschema van de entiteit voor metingenuitvoer, inclusief filters en dimensies.</span><span class="sxs-lookup"><span data-stu-id="e42d5-163">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="e42d5-164">Het voorbeeld reageert dynamisch op wijzigingen in de configuratie.</span><span class="sxs-lookup"><span data-stu-id="e42d5-164">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="e42d5-165">Selecteer **Uitvoeren** om resultaten voor de geconfigureerde meting te berekenen.</span><span class="sxs-lookup"><span data-stu-id="e42d5-165">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="e42d5-166">Selecteer **Opslaan en sluiten** als u de huidige configuratie wilt behouden en de meting later wilt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="e42d5-166">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="e42d5-167">Ga naar **Metingen** om de nieuw gemaakte meting in de lijst te zien.</span><span class="sxs-lookup"><span data-stu-id="e42d5-167">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="e42d5-168">Uw meetcriteria beheren</span><span class="sxs-lookup"><span data-stu-id="e42d5-168">Manage your measures</span></span>

<span data-ttu-id="e42d5-169">Nadat u [een meting hebt gemaakt](#create-a-measure), ziet u een lijst met metingen op de pagina **Metingen**.</span><span class="sxs-lookup"><span data-stu-id="e42d5-169">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="e42d5-170">U vindt informatie over het type meting, de maker, de datum waarop de meting is gemaakt en de status.</span><span class="sxs-lookup"><span data-stu-id="e42d5-170">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="e42d5-171">Wanneer u een meting uit de lijst selecteert, kunt u een voorbeeld van de uitvoer bekijken en een .CSV-bestand downloaden.</span><span class="sxs-lookup"><span data-stu-id="e42d5-171">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="e42d5-172">Selecteer om al uw meetcriteria tegelijkertijd te vernieuwen de optie **Alles vernieuwen** zonder een specifiek meetcriterium te selecteren.</span><span class="sxs-lookup"><span data-stu-id="e42d5-172">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e42d5-173">![Acties om afzonderlijke meetcriteria te beheren](media/measure-actions.png "Acties om afzonderlijke meetcriteria te beheren")</span><span class="sxs-lookup"><span data-stu-id="e42d5-173">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="e42d5-174">Selecteer een meting in de lijst voor de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="e42d5-174">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="e42d5-175">Selecteer de naam van het meetcriterium om de details te zien.</span><span class="sxs-lookup"><span data-stu-id="e42d5-175">Select the measure name to see its details.</span></span>
- <span data-ttu-id="e42d5-176">**Bewerk** de configuratie van het meetcriterium.</span><span class="sxs-lookup"><span data-stu-id="e42d5-176">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="e42d5-177">**Vernieuw** de meting op basis van de laatste gegevens.</span><span class="sxs-lookup"><span data-stu-id="e42d5-177">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="e42d5-178">**Hernoem** het meetcriterium.</span><span class="sxs-lookup"><span data-stu-id="e42d5-178">**Rename** the measure.</span></span>
- <span data-ttu-id="e42d5-179">**Verwijder** het meetcriterium.</span><span class="sxs-lookup"><span data-stu-id="e42d5-179">**Delete** the measure.</span></span>
- <span data-ttu-id="e42d5-180">**Activeren** of **Deactiveren**.</span><span class="sxs-lookup"><span data-stu-id="e42d5-180">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="e42d5-181">Inactieve metingen worden niet vernieuwd tijdens een [geplande vernieuwing](system.md#schedule-tab)​.</span><span class="sxs-lookup"><span data-stu-id="e42d5-181">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="e42d5-182">Er zijn [zes soorten status](system.md#status-types) voor taken/processen.</span><span class="sxs-lookup"><span data-stu-id="e42d5-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="e42d5-183">Bovendien zijn de meeste processen [afhankelijk van andere stroomafwaartse processen](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="e42d5-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="e42d5-184">U kunt de status van een proces selecteren om voortgangsdetails te zien van de volledige taak.</span><span class="sxs-lookup"><span data-stu-id="e42d5-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="e42d5-185">Na het selecteren van **Details bekijken** voor een van de taken vindt u aanvullende informatie: verwerkingstijd, de laatste verwerkingsdatum en alle fouten en waarschuwingen die bij de taak horen.</span><span class="sxs-lookup"><span data-stu-id="e42d5-185">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="e42d5-186">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="e42d5-186">Next step</span></span>

<span data-ttu-id="e42d5-187">U kunt bestaande metingen gebruiken om [een klantsegment](segments.md)​te maken.</span><span class="sxs-lookup"><span data-stu-id="e42d5-187">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]