---
title: Klantactiviteiten
description: Definieer klantactiviteiten en bekijk ze op de tijdlijn van de klant.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: fbfa9d7e00859cc80c24b98bd2dc806f1fda7803
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596723"
---
# <a name="customer-activities"></a><span data-ttu-id="b51eb-103">Klantactiviteiten</span><span class="sxs-lookup"><span data-stu-id="b51eb-103">Customer activities</span></span>

<span data-ttu-id="b51eb-104">Combineer klantactiviteiten van [verschillende gegevensbronnen](data-sources.md) in Dynamics 365 Customer Insights om een klanttijdlijn te maken met de activiteiten in chronologische volgorde.</span><span class="sxs-lookup"><span data-stu-id="b51eb-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="b51eb-105">U kunt de tijdlijn opnemen in apps voor klantbetrokkenheid in Dynamics 365 via de [invoegtoepassing Klantenkaart](customer-card-add-in.md) of in een Power BI-dashboard.</span><span class="sxs-lookup"><span data-stu-id="b51eb-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="b51eb-106">Een activiteit definiëren</span><span class="sxs-lookup"><span data-stu-id="b51eb-106">Define an activity</span></span>

<span data-ttu-id="b51eb-107">Uw gegevensbronnen omvatten entiteiten met transactie- en activiteitsgegevens uit meerdere gegevensbronnen.</span><span class="sxs-lookup"><span data-stu-id="b51eb-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="b51eb-108">Identificeer deze entiteiten en selecteer de activiteiten die u op de tijdlijn van de klant wilt bekijken.</span><span class="sxs-lookup"><span data-stu-id="b51eb-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="b51eb-109">Kies de entiteit die uw doelactiviteit of -activiteiten omvat.</span><span class="sxs-lookup"><span data-stu-id="b51eb-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="b51eb-110">Ga in doelgroepinzichten naar **Gegevens** > **Activiteiten**.</span><span class="sxs-lookup"><span data-stu-id="b51eb-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="b51eb-111">Selecteer **Activiteit toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="b51eb-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b51eb-112">Een entiteit moet ten minste één kenmerk van het type **Datum** hebben om te worden opgenomen in de tijdlijn van een klant en u kunt geen entiteiten toevoegen zonder velden **Datum**.</span><span class="sxs-lookup"><span data-stu-id="b51eb-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="b51eb-113">Het besturingselement **Activiteit toevoegen** is uitgeschakeld als een dergelijke entiteit niet wordt gevonden.</span><span class="sxs-lookup"><span data-stu-id="b51eb-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="b51eb-114">Stel in het deelvenster **Activiteit toevoegen** de waarden in voor de volgende velden:</span><span class="sxs-lookup"><span data-stu-id="b51eb-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="b51eb-115">**Entiteit**: selecteer een entiteit die transactie- of activiteitsgegevens bevat.</span><span class="sxs-lookup"><span data-stu-id="b51eb-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="b51eb-116">**Primaire sleutel**: selecteer het veld waarmee een record eenduidig wordt geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="b51eb-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="b51eb-117">Het mag geen dubbele waarden, lege waarden of ontbrekende waarden bevatten.</span><span class="sxs-lookup"><span data-stu-id="b51eb-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="b51eb-118">**Tijdstempel**: selecteer het veld dat de starttijd van uw activiteit vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="b51eb-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="b51eb-119">**Gebeurtenis**: selecteer het veld dat de gebeurtenis voor de activiteit aangeeft.</span><span class="sxs-lookup"><span data-stu-id="b51eb-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="b51eb-120">**webadres**: selecteer het veld dat een URL vertegenwoordigt met aanvullende informatie over deze activiteit.</span><span class="sxs-lookup"><span data-stu-id="b51eb-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="b51eb-121">Bijvoorbeeld het transactiesysteem dat de bron van deze activiteit vormt.</span><span class="sxs-lookup"><span data-stu-id="b51eb-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="b51eb-122">Deze URL kan elk veld zijn uit de gegevensbron, of het kan worden geconstrueerd als een nieuw veld via een Power Query-transformatie.</span><span class="sxs-lookup"><span data-stu-id="b51eb-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="b51eb-123">Deze URL-gegevens worden opgeslagen in de entiteit Geharmoniseerde activiteit, die stroomafwaarts kan worden gebruikt met behulp van API's.</span><span class="sxs-lookup"><span data-stu-id="b51eb-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="b51eb-124">**Details**: selecteer optioneel het veld dat wordt toegevoegd voor extra details.</span><span class="sxs-lookup"><span data-stu-id="b51eb-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="b51eb-125">**Pictogram**: selecteer optioneel het pictogram dat deze activiteit aangeeft.</span><span class="sxs-lookup"><span data-stu-id="b51eb-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="b51eb-126">**Type activiteit**: definieer de verwijzing naar het activiteitstype naar Common Data Model dat het beste de semantische definitie van de activiteit beschrijft.</span><span class="sxs-lookup"><span data-stu-id="b51eb-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="b51eb-127">Configureer in de sectie **Relatie instellen** de details om uw activiteitsgegevens te koppelen aan de corresponderende klant.</span><span class="sxs-lookup"><span data-stu-id="b51eb-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

    - <span data-ttu-id="b51eb-128">**Activiteitsentiteitsveld**: selecteer het veld in uw activiteitsentiteit dat zal worden gebruikt om een relatie met een andere entiteit tot stand te brengen.</span><span class="sxs-lookup"><span data-stu-id="b51eb-128">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="b51eb-129">**Klantentiteit**: selecteer de corresponderende bronklantentiteit waarmee uw activiteitsentiteit een relatie zal hebben.</span><span class="sxs-lookup"><span data-stu-id="b51eb-129">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="b51eb-130">U kunt alleen relaties tot stand brengen met bronklantenentiteiten die worden gebruikt in het proces van gegevensharmonisering.</span><span class="sxs-lookup"><span data-stu-id="b51eb-130">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="b51eb-131">**Veld Klantentiteit**: dit veld toont de primaire sleutel van de bronklantentiteit zoals geselecteerd in het kaartproces.</span><span class="sxs-lookup"><span data-stu-id="b51eb-131">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="b51eb-132">Dit primaire sleutelveld in de bronklantentiteit wordt gebruikt om een relatie tot stand te brengen met de activiteitsentiteit.</span><span class="sxs-lookup"><span data-stu-id="b51eb-132">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="b51eb-133">**Naam**: als er al een relatie bestaat tussen deze activiteitsentiteit en de geselecteerde bronklantentiteit, staat de relatienaam in de alleen-lezenmodus.</span><span class="sxs-lookup"><span data-stu-id="b51eb-133">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="b51eb-134">Als een dergelijke relatie niet bestaat, wordt er een nieuwe relatie gemaakt met de hier opgegeven naam.</span><span class="sxs-lookup"><span data-stu-id="b51eb-134">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b51eb-135">![De entiteitsrelatie definiëren](media/activities-entities-define.png "De entiteitsrelatie definiëren")</span><span class="sxs-lookup"><span data-stu-id="b51eb-135">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

1. <span data-ttu-id="b51eb-136">Selecteer **Opslaan** om uw wijzigingen toe te passen.</span><span class="sxs-lookup"><span data-stu-id="b51eb-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="b51eb-137">Selecteer **Uitvoeren** op de pagina **Activiteiten**.</span><span class="sxs-lookup"><span data-stu-id="b51eb-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="b51eb-138">Er zijn [zes soorten status](system.md#status-types) voor taken/processen.</span><span class="sxs-lookup"><span data-stu-id="b51eb-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="b51eb-139">Bovendien zijn de meeste processen [afhankelijk van andere stroomafwaartse processen](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="b51eb-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="b51eb-140">U kunt de status van een proces selecteren om voortgangsdetails te zien van de volledige taak.</span><span class="sxs-lookup"><span data-stu-id="b51eb-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="b51eb-141">Na het selecteren van **Details bekijken** voor een van de taken vindt u aanvullende informatie: verwerkingstijd, de laatste verwerkingsdatum en alle fouten en waarschuwingen die bij de taak horen.</span><span class="sxs-lookup"><span data-stu-id="b51eb-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="b51eb-142">Een activiteit bewerken</span><span class="sxs-lookup"><span data-stu-id="b51eb-142">Edit an activity</span></span>

1. <span data-ttu-id="b51eb-143">Ga in doelgroepinzichten naar **Gegevens** > **Activiteiten**.</span><span class="sxs-lookup"><span data-stu-id="b51eb-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="b51eb-144">Selecteer de activiteitsentiteit die u wilt bewerken en selecteer **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="b51eb-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="b51eb-145">Of u kunt de muisaanwijzer op de rij van de entiteit plaatsen en het pictogram **Bewerken** selecteren.</span><span class="sxs-lookup"><span data-stu-id="b51eb-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="b51eb-146">Klik op het pictogram **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="b51eb-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="b51eb-147">Werk in het deelvenster **Activiteit bewerken** de waarden bij en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b51eb-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="b51eb-148">Selecteer **Uitvoeren** op de pagina **Activiteiten**.</span><span class="sxs-lookup"><span data-stu-id="b51eb-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="b51eb-149">Een activiteit verwijderen</span><span class="sxs-lookup"><span data-stu-id="b51eb-149">Delete an activity</span></span>

1. <span data-ttu-id="b51eb-150">Ga in doelgroepinzichten naar **Gegevens** > **Activiteiten**.</span><span class="sxs-lookup"><span data-stu-id="b51eb-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="b51eb-151">Selecteer de activiteitsentiteit die u wilt verwijderen en selecteer **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="b51eb-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="b51eb-152">Of u kunt de muisaanwijzer op de rij van de entiteit plaatsen en het pictogram **Verwijderen** selecteren.</span><span class="sxs-lookup"><span data-stu-id="b51eb-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="b51eb-153">Bovendien kunt u meerdere activiteitsentiteiten selecteren om tegelijkertijd te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="b51eb-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b51eb-154">![De entiteitsrelaties bewerken of verwijderen](media/activities-entities-edit-delete.png "De entiteitsrelaties bewerken of verwijderen")</span><span class="sxs-lookup"><span data-stu-id="b51eb-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="b51eb-155">Selecteer het pictogram **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="b51eb-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="b51eb-156">Bevestig de verwijdering.</span><span class="sxs-lookup"><span data-stu-id="b51eb-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]