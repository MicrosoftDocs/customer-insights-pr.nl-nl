---
title: Relaties tussen entiteiten en entiteitspaden
description: Maak en beheer relaties tussen entiteiten uit meerdere gegevensbronnen.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171158"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="26824-103">Relaties tussen entiteiten</span><span class="sxs-lookup"><span data-stu-id="26824-103">Relationships between entities</span></span>

<span data-ttu-id="26824-104">Relaties verbinden entiteiten en definiëren een grafiek van uw gegevens wanneer entiteiten een gemeenschappelijke id, een refererende sleutel, delen.</span><span class="sxs-lookup"><span data-stu-id="26824-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="26824-105">Er kan vanuit de ene entiteit naar de andere worden verwezen met deze refererende sleutel.</span><span class="sxs-lookup"><span data-stu-id="26824-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="26824-106">Verbonden entiteiten maken het definiëren van segmenten en meetcriteria mogelijk op basis van meerdere gegevensbronnen.</span><span class="sxs-lookup"><span data-stu-id="26824-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="26824-107">Er zijn drie typen relaties:</span><span class="sxs-lookup"><span data-stu-id="26824-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="26824-108">Niet-bewerkbaar systeemrelaties, die door het systeem worden gemaakt als onderdeel van het gegevensharmonisatieproces</span><span class="sxs-lookup"><span data-stu-id="26824-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="26824-109">Niet-bewerkbare overgenomen relaties, die automatisch worden gemaakt op basis van het opnemen van gegevensbronnen</span><span class="sxs-lookup"><span data-stu-id="26824-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="26824-110">Bewerkbare aangepaste relaties, die worden gemaakt en geconfigureerd door gebruikers</span><span class="sxs-lookup"><span data-stu-id="26824-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="26824-111">Niet-bewerkbare systeemrelaties</span><span class="sxs-lookup"><span data-stu-id="26824-111">Non-editable system relationships</span></span>

<span data-ttu-id="26824-112">Tijdens de gegevensharmonisatie worden systeemrelaties automatisch gemaakt op basis van intelligente afstemming.</span><span class="sxs-lookup"><span data-stu-id="26824-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="26824-113">Deze relaties helpen de klantprofielrecords te relateren aan overeenkomstige records.</span><span class="sxs-lookup"><span data-stu-id="26824-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="26824-114">In het volgende diagram wordt het maken van drie systeemgebaseerde relaties geïllustreerd.</span><span class="sxs-lookup"><span data-stu-id="26824-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="26824-115">De klantentiteit wordt gematcht met andere entiteiten om de geharmoniseerde entiteit *Klant* te maken.</span><span class="sxs-lookup"><span data-stu-id="26824-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagram met relatiepaden voor de klantentiteit met drie 1-n-relaties.":::

- <span data-ttu-id="26824-117">De **relatie *CustomerToContact*** is gemaakt tussen de entiteit *Klant* en de entiteit *Contactpersoon*.</span><span class="sxs-lookup"><span data-stu-id="26824-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="26824-118">De entiteit *Klant* krijgt het sleutelveld **Contact_contactID** om een relatie tot stand te brengen met het sleutelveld **contactID** van de entiteit *Contactpersoon*.</span><span class="sxs-lookup"><span data-stu-id="26824-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="26824-119">De **relatie *CustomerToAccount*** is gemaakt tussen de entiteit *Klant* en de entiteit *Account*.</span><span class="sxs-lookup"><span data-stu-id="26824-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="26824-120">De entiteit *Klant* krijgt het sleutelveld **Account_accountID** om een relatie tot stand te brengen met het sleutelveld **accountID** van de entiteit *Account*.</span><span class="sxs-lookup"><span data-stu-id="26824-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="26824-121">De **relatie *CustomerToWebAccount*** is gemaakt tussen de entiteit *Klant* en de entiteit *WebAccount*.</span><span class="sxs-lookup"><span data-stu-id="26824-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="26824-122">De entiteit *Klant* krijgt het sleutelveld **WebAccount_webaccountID** om een relatie tot stand te brengen met het sleutelveld **webaccountID** van de entiteit *WebAccount*.</span><span class="sxs-lookup"><span data-stu-id="26824-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="26824-123">Niet-bewerkbare overgenomen relaties</span><span class="sxs-lookup"><span data-stu-id="26824-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="26824-124">Tijdens het gegevensopnameproces controleert het systeem gegevensbronnen op bestaande relaties.</span><span class="sxs-lookup"><span data-stu-id="26824-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="26824-125">Als er geen relatie bestaat, maakt het systeem deze automatisch aan.</span><span class="sxs-lookup"><span data-stu-id="26824-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="26824-126">Deze relaties worden ook gebruikt in downstreamprocessen.</span><span class="sxs-lookup"><span data-stu-id="26824-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="26824-127">Een aangepaste relatie maken</span><span class="sxs-lookup"><span data-stu-id="26824-127">Create a custom relationship</span></span>

<span data-ttu-id="26824-128">Relatie bestaat uit een *bronentiteit* met de refererende sleutel en een *doelentiteit* waarnaar de refererende sleutel van de bronentiteit verwijst.</span><span class="sxs-lookup"><span data-stu-id="26824-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="26824-129">Ga in doelgroepinzichten naar **Gegevens** > **Relaties**.</span><span class="sxs-lookup"><span data-stu-id="26824-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="26824-130">Selecteer **Nieuwe relatie**.</span><span class="sxs-lookup"><span data-stu-id="26824-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="26824-131">Geef in het deelvenster **Nieuwe relatie** de volgende informatie op:</span><span class="sxs-lookup"><span data-stu-id="26824-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="Zijvenster Nieuwe relatie met lege invoervelden.":::

   - <span data-ttu-id="26824-133">**Relatienaam**: naam die het doel van de relatie weergeeft.</span><span class="sxs-lookup"><span data-stu-id="26824-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="26824-134">Voorbeeld: CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="26824-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="26824-135">**Beschrijving**: de beschrijving van de relatie.</span><span class="sxs-lookup"><span data-stu-id="26824-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="26824-136">**Bronentiteit**: entiteit die wordt gebruikt als bron in de relatie.</span><span class="sxs-lookup"><span data-stu-id="26824-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="26824-137">Voorbeeld: SupportCase.</span><span class="sxs-lookup"><span data-stu-id="26824-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="26824-138">**Doelentiteit**: entiteit die wordt gebruikt als doel in de relatie.</span><span class="sxs-lookup"><span data-stu-id="26824-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="26824-139">Voorbeeld: Customer.</span><span class="sxs-lookup"><span data-stu-id="26824-139">Example: Customer.</span></span>
   - <span data-ttu-id="26824-140">**Bronkardinaliteit**: geef de kardinaliteit van de bronentiteit op.</span><span class="sxs-lookup"><span data-stu-id="26824-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="26824-141">Kardinaliteit beschrijft het aantal mogelijke elementen in een set.</span><span class="sxs-lookup"><span data-stu-id="26824-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="26824-142">Het heeft altijd betrekking op de doelkardinaliteit.</span><span class="sxs-lookup"><span data-stu-id="26824-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="26824-143">U kunt kiezen tussen **Een** en **Veel**.</span><span class="sxs-lookup"><span data-stu-id="26824-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="26824-144">Alleen veel-op-één- en één-op-één-relaties worden ondersteund.</span><span class="sxs-lookup"><span data-stu-id="26824-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="26824-145">Veel-op-één: meerdere bronrecords kunnen betrekking hebben op één doelrecord.</span><span class="sxs-lookup"><span data-stu-id="26824-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="26824-146">Voorbeeld: meerdere ondersteuningsaanvragen van een enkele klant.</span><span class="sxs-lookup"><span data-stu-id="26824-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="26824-147">Eén-op-één: een enkele bronrecord heeft betrekking op één doelrecord.</span><span class="sxs-lookup"><span data-stu-id="26824-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="26824-148">Voorbeeld: één loyaliteits-id voor een enkele klant.</span><span class="sxs-lookup"><span data-stu-id="26824-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="26824-149">Veel-op-veel-relaties kunnen worden gemaakt met behulp van twee veel-op-één-relaties en een koppelingsentiteit, die de bronentiteit en de doelentiteit verbindt.</span><span class="sxs-lookup"><span data-stu-id="26824-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="26824-150">**Doelkardinaliteit**: selecteer de kardinaliteit van de doelentiteitsrecords.</span><span class="sxs-lookup"><span data-stu-id="26824-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="26824-151">**Bronsleutelveld**: het veld voor de refererende sleutel in de bronentiteit.</span><span class="sxs-lookup"><span data-stu-id="26824-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="26824-152">Voorbeeld: SupportCase kan CaseID gebruiken als veld voor refererende sleutel.</span><span class="sxs-lookup"><span data-stu-id="26824-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="26824-153">**Doelsleutelveld**: het sleutelveld van de doelentiteit.</span><span class="sxs-lookup"><span data-stu-id="26824-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="26824-154">Voorbeeld: Customer zou het sleutelveld **CustomerID** kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="26824-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="26824-155">Selecteer **Opslaan** om de aangepaste relatie te maken.</span><span class="sxs-lookup"><span data-stu-id="26824-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="26824-156">Relaties weergeven</span><span class="sxs-lookup"><span data-stu-id="26824-156">View relationships</span></span>

<span data-ttu-id="26824-157">Op de pagina Relaties worden alle relaties vermeld die zijn gemaakt.</span><span class="sxs-lookup"><span data-stu-id="26824-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="26824-158">Elke rij vertegenwoordigt een relatie, die ook details bevat over de bronentiteit, de doelentiteit en de kardinaliteit.</span><span class="sxs-lookup"><span data-stu-id="26824-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="Lijst met relaties en opties in de actiebalk van de pagina Relaties.":::

<span data-ttu-id="26824-160">Deze pagina biedt een reeks opties voor bestaande en nieuwe relaties:</span><span class="sxs-lookup"><span data-stu-id="26824-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="26824-161">**Nieuwe relatie:** [maak een aangepaste relatie](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="26824-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="26824-162">**Visualizer**: [verken de relatievisualizer](#explore-the-relationship-visualizer) om een netwerkdiagram te zien van de bestaande relaties en hun kardinaliteit.</span><span class="sxs-lookup"><span data-stu-id="26824-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="26824-163">**Filteren op**: kies het type relaties om in de lijst weer te geven.</span><span class="sxs-lookup"><span data-stu-id="26824-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="26824-164">**Relaties zoeken**: gebruik een op tekst gebaseerde zoekopdracht op eigenschappen van de relaties.</span><span class="sxs-lookup"><span data-stu-id="26824-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="26824-165">De relatievisualizer verkennen</span><span class="sxs-lookup"><span data-stu-id="26824-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="26824-166">De relatievisualizer geeft een netwerkdiagram van de bestaande relaties tussen verbonden entiteiten en hun kardinaliteit weer.</span><span class="sxs-lookup"><span data-stu-id="26824-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="26824-167">Om de weergave aan te passen, kunt u de positie van de vakken wijzigen door ze op het canvas te slepen.</span><span class="sxs-lookup"><span data-stu-id="26824-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="Schermopname van het netwerkdiagram van de relatievisualizer met verbindingen tussen gerelateerde entiteiten.":::

<span data-ttu-id="26824-169">Beschikbare opties:</span><span class="sxs-lookup"><span data-stu-id="26824-169">Available options:</span></span> 
- <span data-ttu-id="26824-170">**Exporteren als afbeelding**: sla de huidige weergave op als een afbeeldingsbestand.</span><span class="sxs-lookup"><span data-stu-id="26824-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="26824-171">**Wijzigen naar horizontale/verticale indeling**: wijzig de uitlijning van de entiteiten en relaties.</span><span class="sxs-lookup"><span data-stu-id="26824-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="26824-172">**Bewerken**: werk eigenschappen van aangepaste relaties bij in het bewerkingsvenster en sla de wijzigingen op.</span><span class="sxs-lookup"><span data-stu-id="26824-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="26824-173">Bestaande relaties beheren</span><span class="sxs-lookup"><span data-stu-id="26824-173">Manage existing relationships</span></span> 

<span data-ttu-id="26824-174">Op de pagina Relaties wordt elke relatie weergegeven door een rij.</span><span class="sxs-lookup"><span data-stu-id="26824-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="26824-175">Selecteer een relatie en kies een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="26824-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="26824-176">**Bewerken**: werk eigenschappen van aangepaste relaties bij in het bewerkingsvenster en sla de wijzigingen op.</span><span class="sxs-lookup"><span data-stu-id="26824-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="26824-177">**Verwijderen**: aangepaste relaties verwijderen.</span><span class="sxs-lookup"><span data-stu-id="26824-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="26824-178">**Weergeven**: door het systeem gemaakte en overgenomen relaties bekijken.</span><span class="sxs-lookup"><span data-stu-id="26824-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="26824-179">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="26824-179">Next step</span></span>

<span data-ttu-id="26824-180">Systeem- en aangepaste relaties worden gebruikt om [segmenten te maken](segments.md) op basis van meerdere gegevensbronnen die niet langer geïsoleerd zijn.</span><span class="sxs-lookup"><span data-stu-id="26824-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
