---
title: Metingen maken en beheren
description: Definieer maatregelen om de prestaties van uw bedrijf te analyseren en weer te geven.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 402e5ef3515bce0e6f56788781b7bd909738aaa6
ms.sourcegitcommit: b833e333745d321edeaf96d3ed14458cbce02ff1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049244"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="fd564-103">Meetcriteria definiëren en beheren</span><span class="sxs-lookup"><span data-stu-id="fd564-103">Define and manage measures</span></span>

<span data-ttu-id="fd564-104">Meetcriteria helpen u het klantgedrag en de bedrijfsprestaties beter te begrijpen.</span><span class="sxs-lookup"><span data-stu-id="fd564-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="fd564-105">Ze kijken naar relevante waarden uit [geharmoniseerde profielen](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="fd564-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="fd564-106">Een bedrijf wil bijvoorbeeld de *totale uitgaven per klant* bekijken om de aankoopgeschiedenis van individuele klanten te begrijpen of de *totale verkoop van het bedrijf* meten om inzicht te krijgen in de totale inkomsten van het hele bedrijf.</span><span class="sxs-lookup"><span data-stu-id="fd564-106">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="fd564-107">Metingen worden gemaakt met behulp van de metingenbouwer, een gegevensqueryplatform met verschillende operators en eenvoudige toewijzingsopties.</span><span class="sxs-lookup"><span data-stu-id="fd564-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="fd564-108">Hiermee kunt u de gegevens filteren, resultaten groeperen, [entiteitsrelatiepaden](relationships.md) detecteren en een voorbeeld van de uitvoer bekijken.</span><span class="sxs-lookup"><span data-stu-id="fd564-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="fd564-109">Gebruik de metingenbouwer om bedrijfsactiviteiten te plannen door klantgegevens op te vragen en inzichten te verkrijgen.</span><span class="sxs-lookup"><span data-stu-id="fd564-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="fd564-110">Als u bijvoorbeeld een meting maakt van *totale uitgaven per klant* en *totaal rendement per klant*, helpt dit u een groep klanten met hoge uitgaven en toch een hoog rendement te identificeren.</span><span class="sxs-lookup"><span data-stu-id="fd564-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="fd564-111">U kunt [een segment maken](segments.md) om de volgende beste acties aan te sturen.</span><span class="sxs-lookup"><span data-stu-id="fd564-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="fd564-112">Uw eigen meetcriterium bouwen</span><span class="sxs-lookup"><span data-stu-id="fd564-112">Build your own measure from scratch</span></span>

<span data-ttu-id="fd564-113">In deze sectie wordt uitgelegd hoe u een geheel nieuwe meting maakt.</span><span class="sxs-lookup"><span data-stu-id="fd564-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="fd564-114">U kunt een meting bouwen met gegevenskenmerken van gegevensentiteiten waarvoor een relatie is ingesteld om verbinding te maken met de entiteit Klant.</span><span class="sxs-lookup"><span data-stu-id="fd564-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="fd564-115">Ga in doelgroepinzichten naar **Metingen**.</span><span class="sxs-lookup"><span data-stu-id="fd564-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="fd564-116">Selecteer **Nieuw** en kies **Bouw uw eigen**.</span><span class="sxs-lookup"><span data-stu-id="fd564-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="fd564-117">Selecteer **Naam bewerken** en geef een **Naam** op voor de meting.</span><span class="sxs-lookup"><span data-stu-id="fd564-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="fd564-118">Als uw nieuwe metingconfiguratie slechts twee velden heeft, bijvoorbeeld CustomerID en één berekening, wordt de uitvoer als een nieuwe kolom toegevoegd aan de door het systeem gegenereerde entiteit Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="fd564-118">If your new measure configuration has only two fields, for example, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="fd564-119">En u kunt de waarde van de meting zien in het geharmoniseerde klantprofiel.</span><span class="sxs-lookup"><span data-stu-id="fd564-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="fd564-120">Andere metingen zullen hun eigen entiteiten genereren.</span><span class="sxs-lookup"><span data-stu-id="fd564-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="fd564-121">Kies in het configuratiegebied de aggregatiefunctie in het vervolgkeuzemenu **Functie selecteren**.</span><span class="sxs-lookup"><span data-stu-id="fd564-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="fd564-122">Aggregatiefuncties omvatten:</span><span class="sxs-lookup"><span data-stu-id="fd564-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="fd564-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="fd564-123">**Sum**</span></span>
   - <span data-ttu-id="fd564-124">**Gemiddeld**</span><span class="sxs-lookup"><span data-stu-id="fd564-124">**Average**</span></span>
   - <span data-ttu-id="fd564-125">**Tellen**</span><span class="sxs-lookup"><span data-stu-id="fd564-125">**Count**</span></span>
   - <span data-ttu-id="fd564-126">**Aantal unieke**</span><span class="sxs-lookup"><span data-stu-id="fd564-126">**Count Unique**</span></span>
   - <span data-ttu-id="fd564-127">**Max.**</span><span class="sxs-lookup"><span data-stu-id="fd564-127">**Max**</span></span>
   - <span data-ttu-id="fd564-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="fd564-128">**Min**</span></span>
   - <span data-ttu-id="fd564-129">**Eerste**: neemt de eerste waarde van de gegevensrecord</span><span class="sxs-lookup"><span data-stu-id="fd564-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="fd564-130">**Laatste**: neemt de laatste waarde die aan de gegevensrecord is toegevoegd</span><span class="sxs-lookup"><span data-stu-id="fd564-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operators voor de berekening van metingen.":::

1. <span data-ttu-id="fd564-132">Selecteer **Kenmerk toevoegen** om de gegevens te selecteren die u nodig hebt om deze meting te maken.</span><span class="sxs-lookup"><span data-stu-id="fd564-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="fd564-133">Selecteer het tabblad **Kenmerken**.</span><span class="sxs-lookup"><span data-stu-id="fd564-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="fd564-134">Gegevensentiteit: kies de entiteit die het kenmerk bevat dat u wilt meten.</span><span class="sxs-lookup"><span data-stu-id="fd564-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="fd564-135">Gegevenskenmerk: kies het kenmerk dat u in de aggregatiefunctie wilt gebruiken om de meting te berekenen.</span><span class="sxs-lookup"><span data-stu-id="fd564-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="fd564-136">U kunt slechts één kenmerk tegelijk selecteren.</span><span class="sxs-lookup"><span data-stu-id="fd564-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="fd564-137">U kunt ook een gegevenskenmerk van een bestaande meting selecteren door het tabblad **Metingen** te selecteren. Of u kunt zoeken naar de naam van een entiteit of meting.</span><span class="sxs-lookup"><span data-stu-id="fd564-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="fd564-138">Selecteer **Toevoegen** om het geselecteerde kenmerk aan de meting toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="fd564-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Selecteer een kenmerk om in berekeningen te gebruiken.":::

1. <span data-ttu-id="fd564-140">Om complexere metingen te bouwen, kunt u meer kenmerken toevoegen of wiskundige operatoren gebruiken voor uw meetfunctie.</span><span class="sxs-lookup"><span data-stu-id="fd564-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Maak een complexe meting met wiskundige operatoren.":::

1. <span data-ttu-id="fd564-142">Om filters toe te voegen, selecteert u het **Filter** in het configuratiegebied.</span><span class="sxs-lookup"><span data-stu-id="fd564-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="fd564-143">Selecteer in de sectie **Kenmerk toevoegen** van het deelvenster **Filters** het kenmerk dat u wilt gebruiken om filters te maken.</span><span class="sxs-lookup"><span data-stu-id="fd564-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="fd564-144">Stel de filteroperatoren in om het filter voor elk geselecteerd kenmerk te definiëren.</span><span class="sxs-lookup"><span data-stu-id="fd564-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="fd564-145">Selecteer **Toepassen** om de filters aan de meting toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="fd564-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="fd564-146">Om dimensies toe te voegen, selecteert u **Dimensie** in het configuratiegebied.</span><span class="sxs-lookup"><span data-stu-id="fd564-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="fd564-147">Dimensies worden weergegeven als kolommen in de entiteit voor metingenuitvoer.</span><span class="sxs-lookup"><span data-stu-id="fd564-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="fd564-148">Selecteer **Dimensies bewerken** om gegevenskenmerken toe te voegen waarop u de meetwaarden wilt groeperen.</span><span class="sxs-lookup"><span data-stu-id="fd564-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="fd564-149">Bijvoorbeeld plaats of gender.</span><span class="sxs-lookup"><span data-stu-id="fd564-149">For example, city or gender.</span></span> <span data-ttu-id="fd564-150">Standaard is de dimensie *CustomerID* geselecteerd om *metingen op klantniveau* te maken.</span><span class="sxs-lookup"><span data-stu-id="fd564-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="fd564-151">U kunt de standaarddimensie verwijderen als u *metingen op bedrijfsniveau*​wilt maken.</span><span class="sxs-lookup"><span data-stu-id="fd564-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="fd564-152">Selecteer **Gereed** om de dimensies aan de meting toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="fd564-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="fd564-153">Als er waarden in uw gegevens staan die u moet vervangen door een geheel getal, vervangt u bijvoorbeeld *null* door *0* en selecteert u **Regels**.</span><span class="sxs-lookup"><span data-stu-id="fd564-153">If there are values in your data that you need to replace with an integer, for example, replace *null* with *0*, select **Rules**.</span></span> <span data-ttu-id="fd564-154">Configureer de regel en zorg ervoor dat u alleen hele getallen kiest als vervanging.</span><span class="sxs-lookup"><span data-stu-id="fd564-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="fd564-155">Als er meerdere paden zijn tussen de gegevensentiteit die u hebt toegewezen en de entiteit *Klant*, moet u een van de geïdentificeerde [entiteitsrelatiepaden​](relationships.md) kiezen.</span><span class="sxs-lookup"><span data-stu-id="fd564-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="fd564-156">Meetresultaten kunnen variëren, afhankelijk van het geselecteerde pad.</span><span class="sxs-lookup"><span data-stu-id="fd564-156">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="fd564-157">Selecteer **Gegevensvoorkeuren** en kies het entiteitspad dat moet worden gebruikt om uw meting te identificeren.</span><span class="sxs-lookup"><span data-stu-id="fd564-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="fd564-158">Als er maar één pad is naar de entiteit *Klant*, wordt dit besturingselement niet weergegeven.</span><span class="sxs-lookup"><span data-stu-id="fd564-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="fd564-159">Selecteer **Gereed** om uw selectie toe te passen.</span><span class="sxs-lookup"><span data-stu-id="fd564-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Selecteer het entiteitspad voor de meting.":::

1. <span data-ttu-id="fd564-161">Als u meer berekeningen voor de meting wilt toevoegen, selecteert u **Nieuwe berekening**​.</span><span class="sxs-lookup"><span data-stu-id="fd564-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="fd564-162">U kunt alleen entiteiten op hetzelfde entiteitspad gebruiken voor nieuwe berekeningen.</span><span class="sxs-lookup"><span data-stu-id="fd564-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="fd564-163">Meer berekeningen worden weergegeven als nieuwe kolommen in de entiteit voor metingenuitvoer.</span><span class="sxs-lookup"><span data-stu-id="fd564-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="fd564-164">Selecteer **...** in de berekening om een berekening uit een meting te **Dupliceren** **Naam wijzigen** of te **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="fd564-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="fd564-165">In het gebied **Voorbeeld** ziet u het gegevensschema van de entiteit voor metingenuitvoer, inclusief filters en dimensies.</span><span class="sxs-lookup"><span data-stu-id="fd564-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="fd564-166">Het voorbeeld reageert dynamisch op wijzigingen in de configuratie.</span><span class="sxs-lookup"><span data-stu-id="fd564-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="fd564-167">Selecteer **Uitvoeren** om resultaten voor de geconfigureerde meting te berekenen.</span><span class="sxs-lookup"><span data-stu-id="fd564-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="fd564-168">Selecteer **Opslaan en sluiten** als u de huidige configuratie wilt behouden en de meting later wilt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="fd564-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="fd564-169">Ga naar **Metingen** om de nieuw gemaakte meting in de lijst te zien.</span><span class="sxs-lookup"><span data-stu-id="fd564-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="fd564-170">Een sjabloon gebruiken om een meetcriterium op te stellen</span><span class="sxs-lookup"><span data-stu-id="fd564-170">Use a template to build a measure</span></span>

<span data-ttu-id="fd564-171">U kunt vooraf gedefinieerde sjablonen van veelgebruikte meetcriteria gebruiken om deze te maken.</span><span class="sxs-lookup"><span data-stu-id="fd564-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="fd564-172">Gedetailleerde beschrijvingen van de sjablonen en een begeleide ervaring helpen u bij het efficiënt maken van meetcriteria.</span><span class="sxs-lookup"><span data-stu-id="fd564-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="fd564-173">Sjablonen bouwen voort op toegewezen gegevens uit de entiteit *Unified Activity*.</span><span class="sxs-lookup"><span data-stu-id="fd564-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="fd564-174">Zorg er dus voor dat u [klantactiviteiten](activities.md) hebt geconfigureerd voordat u een meetcriterium maakt op basis van een sjabloon.</span><span class="sxs-lookup"><span data-stu-id="fd564-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="fd564-175">Beschikbare sjablonen voor meetcriteria:</span><span class="sxs-lookup"><span data-stu-id="fd564-175">Available measure templates:</span></span> 
- <span data-ttu-id="fd564-176">Gemiddelde transactiewaarde (ATV)</span><span class="sxs-lookup"><span data-stu-id="fd564-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="fd564-177">Totale transactiewaarde</span><span class="sxs-lookup"><span data-stu-id="fd564-177">Total transaction value</span></span>
- <span data-ttu-id="fd564-178">Gemiddelde dagelijkse omzet</span><span class="sxs-lookup"><span data-stu-id="fd564-178">Average daily revenue</span></span>
- <span data-ttu-id="fd564-179">Gemiddelde jaaromzet</span><span class="sxs-lookup"><span data-stu-id="fd564-179">Average yearly revenue</span></span>
- <span data-ttu-id="fd564-180">Aantal transacties</span><span class="sxs-lookup"><span data-stu-id="fd564-180">Transaction count</span></span>
- <span data-ttu-id="fd564-181">Verdiende loyaliteitspunten</span><span class="sxs-lookup"><span data-stu-id="fd564-181">Loyalty points earned</span></span>
- <span data-ttu-id="fd564-182">Verzilverde loyaliteitspunten</span><span class="sxs-lookup"><span data-stu-id="fd564-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="fd564-183">Saldo loyaliteitspunten</span><span class="sxs-lookup"><span data-stu-id="fd564-183">Loyalty points balance</span></span>
- <span data-ttu-id="fd564-184">Actieve levensduur van klant</span><span class="sxs-lookup"><span data-stu-id="fd564-184">Active customer lifespan</span></span>
- <span data-ttu-id="fd564-185">Lidmaatschapsduur van loyaliteitsprogramma</span><span class="sxs-lookup"><span data-stu-id="fd564-185">Loyalty membership duration</span></span>
- <span data-ttu-id="fd564-186">Tijd sinds laatste aankoop</span><span class="sxs-lookup"><span data-stu-id="fd564-186">Time since last purchase</span></span>

<span data-ttu-id="fd564-187">De volgende procedure beschrijft de stappen om een nieuw meetcriterium op te stellen met behulp van een sjabloon.</span><span class="sxs-lookup"><span data-stu-id="fd564-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="fd564-188">Ga in doelgroepinzichten naar **Metingen**.</span><span class="sxs-lookup"><span data-stu-id="fd564-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="fd564-189">Selecteer **Nieuw** en selecteer **Een sjabloon kiezen**.</span><span class="sxs-lookup"><span data-stu-id="fd564-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="Schermopname van het vervolgkeuzemenu bij het maken van een nieuw meetcriterium met markering op sjabloon.":::

1. <span data-ttu-id="fd564-191">Zoek de sjabloon die bij uw behoeften past en selecteer **Sjabloon kiezen**.</span><span class="sxs-lookup"><span data-stu-id="fd564-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="fd564-192">Bekijk de vereiste gegevens en selecteer **Aan de slag** als u over alle gegevens beschikt.</span><span class="sxs-lookup"><span data-stu-id="fd564-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="fd564-193">Stel in het deelvenster **Naam bewerken** de naam in voor uw meetcriterium en de uitvoerentiteit.</span><span class="sxs-lookup"><span data-stu-id="fd564-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="fd564-194">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="fd564-194">Select **Done**.</span></span>

1. <span data-ttu-id="fd564-195">Definieer in de sectie **Tijdsperiode instellen** het tijdsbestek van de te gebruiken gegevens.</span><span class="sxs-lookup"><span data-stu-id="fd564-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="fd564-196">Kies of u wilt dat het nieuwe meetcriterium de volledige gegevensset bestrijkt door **Vanaf begin** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="fd564-196">Choose if you want the new measure to cover the entire data set by selecting **All time**.</span></span> <span data-ttu-id="fd564-197">Of als u wilt dat het meetcriterium zich concentreert op een **specifieke tijdsperiode**.</span><span class="sxs-lookup"><span data-stu-id="fd564-197">Or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Schermopname die de tijdsperiode laat zien bij het configureren van een meetcriterium vanuit een sjabloon.":::

1. <span data-ttu-id="fd564-199">Selecteer in de volgende sectie de optie **Gegevens toevoegen** om de activiteiten te kiezen en de bijbehorende gegevens toe te wijzen vanuit uw entiteit *Unified Activity*.</span><span class="sxs-lookup"><span data-stu-id="fd564-199">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="fd564-200">Stap 1 van 2: kies onder **Type activiteit** het type entiteit dat u wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="fd564-200">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="fd564-201">Selecteer voor **Activiteiten** de entiteiten die u wilt toewijzen.</span><span class="sxs-lookup"><span data-stu-id="fd564-201">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="fd564-202">Stap 2 van 2: kies het kenmerk van de entiteit *Unified Activity* voor het onderdeel dat is vereist door de formule.</span><span class="sxs-lookup"><span data-stu-id="fd564-202">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="fd564-203">Voor Gemiddelde transactiewaarde is dit bijvoorbeeld het kenmerk dat de transactiewaarde vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="fd564-203">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="fd564-204">Kies voor **Tijdstempel van activiteit** het kenmerk van de entiteit Unified Activity dat de datum en tijd van de activiteit vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="fd564-204">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="fd564-205">Zodra de gegevenstoewijzing is geslaagd, ziet u de status als **Voltooid** en de naam van de toegewezen activiteiten en kenmerken.</span><span class="sxs-lookup"><span data-stu-id="fd564-205">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="Schermopname van een voltooide configuratie van een meetsjabloon.":::

1. <span data-ttu-id="fd564-207">U kunt nu **Uitvoeren** selecteren om de resultaten van het meetcriterium te berekenen.</span><span class="sxs-lookup"><span data-stu-id="fd564-207">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="fd564-208">Selecteer **Concept opslaan** om het later te verfijnen.</span><span class="sxs-lookup"><span data-stu-id="fd564-208">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="fd564-209">Uw meetcriteria beheren</span><span class="sxs-lookup"><span data-stu-id="fd564-209">Manage your measures</span></span>

<span data-ttu-id="fd564-210">U vindt de lijst met meetcriteria op de pagina **Meetcriteria**.</span><span class="sxs-lookup"><span data-stu-id="fd564-210">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="fd564-211">U vindt informatie over het type meting, de maker, de datum waarop de meting is gemaakt en de status.</span><span class="sxs-lookup"><span data-stu-id="fd564-211">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="fd564-212">Wanneer u een meting uit de lijst selecteert, kunt u een voorbeeld van de uitvoer bekijken en een .CSV-bestand downloaden.</span><span class="sxs-lookup"><span data-stu-id="fd564-212">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="fd564-213">Selecteer om al uw meetcriteria tegelijkertijd te vernieuwen de optie **Alles vernieuwen** zonder een specifiek meetcriterium te selecteren.</span><span class="sxs-lookup"><span data-stu-id="fd564-213">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="fd564-214">![Acties om afzonderlijke meetcriteria te beheren](media/measure-actions.png "Acties om afzonderlijke meetcriteria te beheren")</span><span class="sxs-lookup"><span data-stu-id="fd564-214">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="fd564-215">Selecteer een meting in de lijst voor de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="fd564-215">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="fd564-216">Selecteer de naam van het meetcriterium om de details te zien.</span><span class="sxs-lookup"><span data-stu-id="fd564-216">Select the measure name to see its details.</span></span>
- <span data-ttu-id="fd564-217">**Bewerk** de configuratie van het meetcriterium.</span><span class="sxs-lookup"><span data-stu-id="fd564-217">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="fd564-218">**Vernieuw** de meting op basis van de laatste gegevens.</span><span class="sxs-lookup"><span data-stu-id="fd564-218">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="fd564-219">**Hernoem** het meetcriterium.</span><span class="sxs-lookup"><span data-stu-id="fd564-219">**Rename** the measure.</span></span>
- <span data-ttu-id="fd564-220">**Verwijder** het meetcriterium.</span><span class="sxs-lookup"><span data-stu-id="fd564-220">**Delete** the measure.</span></span>
- <span data-ttu-id="fd564-221">**Activeren** of **Deactiveren**.</span><span class="sxs-lookup"><span data-stu-id="fd564-221">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="fd564-222">Inactieve metingen worden niet vernieuwd tijdens een [geplande vernieuwing](system.md#schedule-tab)​.</span><span class="sxs-lookup"><span data-stu-id="fd564-222">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="fd564-223">Er zijn [zes soorten status](system.md#status-types) voor taken/processen.</span><span class="sxs-lookup"><span data-stu-id="fd564-223">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="fd564-224">Bovendien zijn de meeste processen [afhankelijk van andere stroomafwaartse processen](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="fd564-224">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="fd564-225">U kunt de status van een proces selecteren om voortgangsdetails te zien van de volledige taak.</span><span class="sxs-lookup"><span data-stu-id="fd564-225">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="fd564-226">Na het selecteren van **Details bekijken** voor een van de taken vindt u aanvullende informatie: verwerkingstijd, de laatste verwerkingsdatum en alle fouten en waarschuwingen die bij de taak horen.</span><span class="sxs-lookup"><span data-stu-id="fd564-226">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="fd564-227">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="fd564-227">Next step</span></span>

<span data-ttu-id="fd564-228">U kunt bestaande metingen gebruiken om [een klantsegment](segments.md)​te maken.</span><span class="sxs-lookup"><span data-stu-id="fd564-228">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
