---
title: Segmenten maken en beheren
description: Maak segmenten van klanten om deze te groeperen op basis van verschillende kenmerken.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064931"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="9f8ac-103">Segmenten maken en beheren</span><span class="sxs-lookup"><span data-stu-id="9f8ac-103">Create and manage segments</span></span>

<span data-ttu-id="9f8ac-104">Definieer complexe filters rond de uniforme klantentiteit en de bijhorende gerelateerde entiteiten.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="9f8ac-105">Elk segment maakt na verwerking een set klantrecords die u kunt exporteren en waarop u actie kunt ondernemen.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="9f8ac-106">Segmenten worden beheerd op de pagina **Segmenten**.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="9f8ac-107">Het volgende voorbeeld illustreert de segmentatiemogelijkheid.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="9f8ac-108">We hebben een segment gedefinieerd voor klanten die in de afgelopen 90 dagen voor ten minste $ 500 aan goederen hebben besteld *en* die betrokken waren bij een klantenserviceoproep die werd geëscaleerd.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Schermopname van de gebruikersinterface van de segmentbouwer met twee groepen waarmee een klantsegment wordt opgegeven.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="9f8ac-110">Een nieuw segment maken</span><span class="sxs-lookup"><span data-stu-id="9f8ac-110">Create a new segment</span></span>

<span data-ttu-id="9f8ac-111">Er zijn meerdere manieren om een nieuw segment te maken.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="9f8ac-112">In dit gedeelte wordt beschreven hoe u een geheel *leeg segment* maakt.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="9f8ac-113">U kunt ook een *snel segment* maken op basis van bestaande entiteiten of gebruikmaken van Machine Learning-modellen om *voorgestelde segmenten* te krijgen.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="9f8ac-114">Meer informatie: [Overzicht segmenten](segments.md)</span><span class="sxs-lookup"><span data-stu-id="9f8ac-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="9f8ac-115">Terwijl u een segment maakt, kunt u een concept opslaan.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="9f8ac-116">Het wordt opgeslagen als een inactief segment en kan niet worden geactiveerd als het is voltooid met een geldige configuratie.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="9f8ac-117">Ga naar de pagina **Segmenten**.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="9f8ac-118">Selecteer **Nieuw** > **Leeg segment**.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="9f8ac-119">Kies een segmenttype in het deelvenster **Nieuw segment**:</span><span class="sxs-lookup"><span data-stu-id="9f8ac-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="9f8ac-120">**Dynamische segmenten** [vernieuwen](segments.md#refresh-segments) in een terugkerende planning.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="9f8ac-121">**Statische segmenten** eenmaal uitvoeren wanneer u ze maakt.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="9f8ac-122">Geef een **Naam van uitvoerentiteit** voor het segment op.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="9f8ac-123">Geef optioneel een weergavenaam op en een beschrijving die helpt bij het identificeren van het segment.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="9f8ac-124">Selecteer **Volgende** om naar de pagina **Segmentbouwer** te gaan waar u een groep definieert.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="9f8ac-125">Een groep is een set klanten.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="9f8ac-126">Kies de entiteit die het kenmerk bevat waarop u wilt segmenteren.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="9f8ac-127">Kies het kenmerk waarop u wilt segmenteren.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="9f8ac-128">Dit kenmerk kan een van de volgende vier waardetypen hebben: numeriek, tekenreeks, datum of booleaans.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="9f8ac-129">Kies een operator en een waarde voor het geselecteerde kenmerk.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9f8ac-130">![Aangepast groepsfilter](media/customer-group-numbers.png "Klantgroepsfilter")</span><span class="sxs-lookup"><span data-stu-id="9f8ac-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="9f8ac-131">Aantal</span><span class="sxs-lookup"><span data-stu-id="9f8ac-131">Number</span></span> |<span data-ttu-id="9f8ac-132">Definitie</span><span class="sxs-lookup"><span data-stu-id="9f8ac-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="9f8ac-133">0</span><span class="sxs-lookup"><span data-stu-id="9f8ac-133">1</span></span>     |<span data-ttu-id="9f8ac-134">Entity</span><span class="sxs-lookup"><span data-stu-id="9f8ac-134">Entity</span></span>          |
   |<span data-ttu-id="9f8ac-135">2</span><span class="sxs-lookup"><span data-stu-id="9f8ac-135">2</span></span>     |<span data-ttu-id="9f8ac-136">Kenmerk</span><span class="sxs-lookup"><span data-stu-id="9f8ac-136">Attribute</span></span>          |
   |<span data-ttu-id="9f8ac-137">3</span><span class="sxs-lookup"><span data-stu-id="9f8ac-137">3</span></span>    |<span data-ttu-id="9f8ac-138">Operator</span><span class="sxs-lookup"><span data-stu-id="9f8ac-138">Operator</span></span>         |
   |<span data-ttu-id="9f8ac-139">4</span><span class="sxs-lookup"><span data-stu-id="9f8ac-139">4</span></span>    |<span data-ttu-id="9f8ac-140">Weergegeven als</span><span class="sxs-lookup"><span data-stu-id="9f8ac-140">Value</span></span>         |

   1. <span data-ttu-id="9f8ac-141">Als u meer voorwaarden aan een groep wilt toevoegen, kunt u twee logische operators gebruiken:</span><span class="sxs-lookup"><span data-stu-id="9f8ac-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="9f8ac-142">**EN**-operator: er moet aan beide voorwaarden worden voldaan als onderdeel van het segmentatieproces.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="9f8ac-143">Deze optie is vooral handig wanneer u voorwaarden definieert voor verschillende entiteiten.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="9f8ac-144">**OF**-operator: er moet aan een van beide voorwaarden worden voldaan als onderdeel van het segmentatieproces.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="9f8ac-145">Deze optie is vooral handig wanneer u meerdere voorwaarden definieert voor dezelfde entiteit.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="9f8ac-146">![OF-operator waarbij aan een van beide voorwaarden moet worden voldaan](media/segmentation-either-condition.png "OF-operator waarbij aan een van beide voorwaarden moet worden voldaan")</span><span class="sxs-lookup"><span data-stu-id="9f8ac-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="9f8ac-147">Het is momenteel mogelijk om een **OF**-operator te nesten onder een **EN**-operator, maar niet andersom.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="9f8ac-148">Elke groep komt overeen met een reeks klanten.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-148">Each group matches set of customers.</span></span> <span data-ttu-id="9f8ac-149">U kunt groepen combineren om de klanten op te nemen die nodig zijn voor uw businesscase.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="9f8ac-150">Selecteer **Groep toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="9f8ac-151">![Klantengroep - Groep toevoegen](media/customer-group-add-group.png "Klantengroep - Groep toevoegen")</span><span class="sxs-lookup"><span data-stu-id="9f8ac-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="9f8ac-152">Selecteer een van de set-operators: **Samenvoegen**, **Doorsnede** of **Uitsluiten**.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9f8ac-153">![Klantengroep - Verbinding toevoegen](media/customer-group-union.png "Klantengroep - Verbinding toevoegen")</span><span class="sxs-lookup"><span data-stu-id="9f8ac-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="9f8ac-154">**Verbinding** verbindt de twee groepen.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="9f8ac-155">**Overlappen** overlapt de twee groepen.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="9f8ac-156">Alleen gegevens die *gemeenschappelijk* zijn voor beide groepen, worden behouden in de geharmoniseerde groep.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="9f8ac-157">**Behalve** combineert de twee groepen.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-157">**Except** combines the two groups.</span></span> <span data-ttu-id="9f8ac-158">Alleen gegevens in groep A die *niet gemeenschappelijk* zijn voor gegevens in groep B, worden behouden.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="9f8ac-159">Als de entiteit via [relaties](relationships.md) met de geharmoniseerde klantentiteit is verbonden, moet u het relatiepad definiëren om een geldig segment te maken.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="9f8ac-160">Voeg de entiteiten uit het relatiepad toe totdat u de entiteit **Klant : CustomerInsights** in de vervolgkeuzelijst kunt selecteren.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="9f8ac-161">Kies dan **Alle records** voor elke stap.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9f8ac-162">![Relatiepad tijdens het maken van segmenten](media/segments-multiple-relationships.png "Relatiepad tijdens het maken van segmenten")</span><span class="sxs-lookup"><span data-stu-id="9f8ac-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="9f8ac-163">Segmenten genereren standaard een uitvoerentiteit die alle kenmerken van klantprofielen bevat die overeenkomen met de gedefinieerde filters.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="9f8ac-164">Als een segment is gebaseerd op andere entiteiten dan de entiteit *Klant*, kunt u meer attributen van deze entiteiten aan de uitvoerentiteit toevoegen.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="9f8ac-165">Selecteer **Projectkernmerken** om de kenmerken te kiezen die aan de uitvoerentiteit worden toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="9f8ac-166">Voorbeeld: een segment is gebaseerd op een entiteit die gegevens over klantactiviteit bevat die gerelateerd zijn aan de entiteit *Klant*.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="9f8ac-167">Het segment zoekt naar alle klanten die de helpdesk de afgelopen 60 dagen hebben gebeld.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="9f8ac-168">U kunt ervoor kiezen om de gespreksduur en het aantal gesprekken toe te voegen aan alle overeenkomende klantrecords in de uitvoerentiteit.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="9f8ac-169">Deze gegevens kunnen handig zijn om een e-mail met handige koppelingen naar Help-artikelen en FAQ's te sturen naar klanten die vaak hebben gebeld.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="9f8ac-170">Geprojecteerde kenmerken werken alleen voor entiteiten die een een-op-veel-relatie hebben met de klantentiteit.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="9f8ac-171">Eén klant kan bijvoorbeeld meerdere abonnementen hebben.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="9f8ac-172">U kunt alleen kenmerken projecteren van een entiteit die wordt gebruikt in elke groep segmentquery's die u aan het bouwen bent.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="9f8ac-173">Bij het gebruik van set-operators wordt rekening gehouden met geprojecteerde kenmerken.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="9f8ac-174">Selecteer **Opslaan** om uw segment op te slaan.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="9f8ac-175">Uw segment wordt opgeslagen en verwerkt als alle vereisten zijn gevalideerd.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="9f8ac-176">Anders wordt het opgeslagen als concept.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="9f8ac-177">Selecteer **Terug naar segmenten** om terug te gaan naar de pagina **Segmenten**.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="9f8ac-178">Snelle segmenten</span><span class="sxs-lookup"><span data-stu-id="9f8ac-178">Quick segments</span></span>

<span data-ttu-id="9f8ac-179">Met snelle segmenten kunt u snel eenvoudige segmenten bouwen met één operator voor snellere inzichten.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="9f8ac-180">Selecteer op de pagina **Segmenten** de optie **Nieuw** > **Maken van**.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="9f8ac-181">Selecteer de optie **Profielen** om een segment te bouwen dat is gebaseerd op de entiteit *geharmoniseerde klant*.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="9f8ac-182">Selecteer de optie **Meetcriteria** om een segment te bouwen rond meetcriteria die u eerder hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="9f8ac-183">Selecteer de optie **Intelligentie** om een segment op te bouwen rond een van de uitvoerentiteiten die u hebt gegenereerd met behulp van de mogelijkheden **Voorspellingen** of **Aangepaste modellen**.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="9f8ac-184">Selecteer in het dialoogvenster **Nieuw snel segment** een kenmerk uit de vervolgkeuzelijst **Veld**.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="9f8ac-185">Het systeem biedt enkele aanvullende inzichten waarmee u betere segmenten van uw klanten kunt maken.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="9f8ac-186">Voor categorievelden geven we tien topposities van klanten weer.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="9f8ac-187">Kies een **Waarde** en selecteer **Evalueren**.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="9f8ac-188">Voor een numeriek kenmerk laat het systeem zien welke kenmerkwaarde onder het percentiel van elke klant valt.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="9f8ac-189">Kies een **Operator** en een **Waarde** en selecteer vervolgens **Evalueren**.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="9f8ac-190">Het systeem zal u van een **Geschatte segmentgrootte** voorzien.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="9f8ac-191">U kunt kiezen of u het door u gedefinieerde segment wilt genereren of het eerst opnieuw wilt bezoeken om een andere segmentgrootte te krijgen.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="9f8ac-192">![Naam en schatting voor een snel segment](media/quick-segment-name.png "Naam en schatting voor een snel segment")</span><span class="sxs-lookup"><span data-stu-id="9f8ac-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="9f8ac-193">Geef een **Naam** op voor uw segment.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="9f8ac-194">Voer desgewenst een **Weergavenaam** in.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="9f8ac-195">Selecteer **Opslaan** om uw segment te maken.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="9f8ac-196">Nadat de verwerking van segment is voltooid, kunt u het bekijken zoals elk ander segment dat u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9f8ac-197">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="9f8ac-197">Next steps</span></span>

<span data-ttu-id="9f8ac-198">[Exporteer een segment](export-destinations.md) en verken de [klantenkaart](customer-card-add-in.md) en [connectors](export-power-bi.md) om inzichten op klantniveau te verkrijgen.</span><span class="sxs-lookup"><span data-stu-id="9f8ac-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
