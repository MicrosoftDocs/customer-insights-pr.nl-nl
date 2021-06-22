---
title: Gegevens exporteren vanuit Customer Insights
description: Beheer exports om gegevens te delen.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e7793fa99f8431d9d420529b39e0b5b5dbf6748
ms.sourcegitcommit: 0689e7ed4265855d1f76745d68af390f8f4af8a0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "6253034"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="ffcbf-103">Overzicht van Exports (preview)</span><span class="sxs-lookup"><span data-stu-id="ffcbf-103">Exports (preview) overview</span></span>

<span data-ttu-id="ffcbf-104">De pagina **Exports** toont u alle geconfigureerde exports.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="ffcbf-105">Exports delen specifieke gegevens met verschillende toepassingen.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="ffcbf-106">Ze kunnen klantprofielen of entiteiten, schema's en toewijzingsdetails bevatten.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="ffcbf-107">Elke export vereist een [verbinding, opgezet door een beheerder, om de verificatie en toegang te beheren](connections.md).</span><span class="sxs-lookup"><span data-stu-id="ffcbf-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="ffcbf-108">Ga naar **Gegevens** > **Exports** om de pagina met exports te bekijken.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="ffcbf-109">Alle gebruikersrollen hebben toegang om geconfigureerde exports te bekijken.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="ffcbf-110">Gebruik van het zoekveld op de opdrachtbalk om exports te zoeken op naam, verbindingsnaam of verbindingstype.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="ffcbf-111">Een nieuwe export instellen</span><span class="sxs-lookup"><span data-stu-id="ffcbf-111">Set up a new export</span></span>

<span data-ttu-id="ffcbf-112">Als u een export wilt instellen of bewerken, moet u over verbindingen beschikken.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="ffcbf-113">Verbindingen zijn afhankelijk van uw [gebruikersrol](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="ffcbf-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="ffcbf-114">Beheerders hebben toegang tot alle verbindingen.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-114">Administrators have access to all connections.</span></span> <span data-ttu-id="ffcbf-115">Ze kunnen ook nieuwe verbindingen maken bij het opzetten van een export.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="ffcbf-116">Inzenders kunnen toegang hebben tot specifieke verbindingen.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="ffcbf-117">Zij zijn afhankelijk van beheerders om verbindingen te configureren en te delen.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="ffcbf-118">De exportlijst laat zien of inzenders een export kunnen bewerken of alleen bekijken in de kolom **Uw machtigingen**.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="ffcbf-119">Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="ffcbf-120">Kijkers kunnen alleen bestaande exports bekijken, maar deze niet maken.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="ffcbf-121">Een nieuwe export definiëren</span><span class="sxs-lookup"><span data-stu-id="ffcbf-121">Define a new export</span></span>

1. <span data-ttu-id="ffcbf-122">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ffcbf-123">Selecteer **Export toevoegen** om een nieuwe export te maken.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="ffcbf-124">Selecteer in het deelvenster **Export instellen** welke verbinding u wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="ffcbf-125">[Verbindingen](connections.md) worden beheerd door beheerders.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="ffcbf-126">Geef de vereiste details op en selecteer **Opslaan** om de export te maken.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="ffcbf-127">Een nieuwe export definiëren op basis van een bestaande export</span><span class="sxs-lookup"><span data-stu-id="ffcbf-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="ffcbf-128">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ffcbf-129">Selecteer in de lijst met exports de export die u wilt dupliceren.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="ffcbf-130">Selecteer **Duplicaat maken** op de opdrachtbalk om het deelvenster **Export instellen** te openen met de details van de geselecteerde export.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="ffcbf-131">Bekijk en pas de export aan en selecteer **Opslaan** om een nieuwe export te maken.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="ffcbf-132">Een export bewerken</span><span class="sxs-lookup"><span data-stu-id="ffcbf-132">Edit an export</span></span>

1. <span data-ttu-id="ffcbf-133">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ffcbf-134">Selecteer in de lijst met exports de export die u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="ffcbf-135">Selecteer **Bewerken** op de opdrachtbalk.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="ffcbf-136">Wijzig de waarden die u wilt bijwerken en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="ffcbf-137">Exports en exportdetails weergeven</span><span class="sxs-lookup"><span data-stu-id="ffcbf-137">View exports and export details</span></span>

<span data-ttu-id="ffcbf-138">Nadat u exportbestemmingen hebt gemaakt, worden deze vermeld bij **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="ffcbf-139">Alle gebruikers kunnen zien welke gegevens worden gedeeld en wat de meest recente status is.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="ffcbf-140">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ffcbf-141">Gebruikers zonder machtigingen voor bewerken selecteren **Weergeven** in plaats van **Bewerken** om de exportdetails te bekijken.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-141">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="ffcbf-142">Het zijvenster toont de configuratie van een export.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="ffcbf-143">Zonder bewerkingsrechten kunt u geen waarden wijzigen.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="ffcbf-144">Selecteer **Sluiten** om terug te keren naar de pagina met exports.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="ffcbf-145">Exports plannen en uitvoeren</span><span class="sxs-lookup"><span data-stu-id="ffcbf-145">Schedule and run exports</span></span>

<span data-ttu-id="ffcbf-146">Elke export die u configureert, heeft een vernieuwingsschema.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="ffcbf-147">Tijdens een vernieuwing zoekt het systeem naar nieuwe of bijgewerkte gegevens om in een export op te nemen.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="ffcbf-148">Standaard worden exports uitgevoerd als onderdeel van elke [geplande systeemvernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ffcbf-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ffcbf-149">U kunt het vernieuwingsschema aanpassen of uitschakelen om exports handmatig uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="ffcbf-150">Exportschema's zijn afhankelijk van de status van uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="ffcbf-151">Als er updates van [afhankelijkheden](system.md#refresh-policies) bezig zijn wanneer een geplande export moet starten, voltooit het systeem eerst de afhankelijkheden en voert het vervolgens de export uit.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-151">If there are updates on [dependencies](system.md#refresh-policies) in progress when a scheduled export should start, the system will first complete the dependencies and then run the export.</span></span> <span data-ttu-id="ffcbf-152">U kunt zien wanneer een export voor het laatst is vernieuwd in de kolom **Vernieuwd**.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="ffcbf-153">Exports plannen</span><span class="sxs-lookup"><span data-stu-id="ffcbf-153">Schedule exports</span></span>

<span data-ttu-id="ffcbf-154">U kunt aangepaste vernieuwingsschema's definiëren voor afzonderlijke exports of meerdere exports tegelijk.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="ffcbf-155">Het momenteel gedefinieerde schema wordt weergegeven in de kolom **Schema** van de exportlijst.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="ffcbf-156">De toestemming om het schema te wijzigen is hetzelfde als voor [het bewerken en definiëren van exports](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ffcbf-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="ffcbf-157">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ffcbf-158">Selecteer de export die u wilt plannen.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="ffcbf-159">Selecteer **Plannen** op de opdrachtbalk.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="ffcbf-160">Stel in het deelvenster **Export plannen** de optie **Uitvoering plannen** in op **Aan** om de export automatisch uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="ffcbf-161">Stel de optie in op **Uit** om handmatig te vernieuwen.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="ffcbf-162">Kies voor automatisch vernieuwde exports een waarde voor **Terugkeerpatroon** en geef de details hiervoor op.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="ffcbf-163">De gedefinieerde tijd is van toepassing op alle exemplaren van een terugkeerpatroon.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="ffcbf-164">Het is het tijdstip waarop een export moet worden vernieuwd.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="ffcbf-165">Pas uw wijzigingen toe en activeer ze door **Opslaan** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="ffcbf-166">Bij het bewerken van de planning voor meerdere exports, dient u een selectie te maken onder **Planningen behouden of overschrijven**:</span><span class="sxs-lookup"><span data-stu-id="ffcbf-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="ffcbf-167">**Afzonderlijke planningen behouden**: houd het eerder gedefinieerde schema voor de geselecteerde exports aan en schakel ze alleen in of uit.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="ffcbf-168">**Nieuwe planning voor alle geselecteerde exporten opgeven**: overschrijf de bestaande planningen van de geselecteerde exports.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="ffcbf-169">Exports op aanvraag uitvoeren</span><span class="sxs-lookup"><span data-stu-id="ffcbf-169">Run exports on demand</span></span>

<span data-ttu-id="ffcbf-170">Als u gegevens wilt exporteren zonder te wachten op een geplande vernieuwing, gaat u naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="ffcbf-171">Als u alle exports wilt uitvoeren, selecteert u **Alles uitvoeren** op de opdrachtbalk.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="ffcbf-172">Met deze actie worden alleen exports uitgevoerd met een actieve planning.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="ffcbf-173">U kunt een enkele export uitvoeren door deze te selecteren in de lijst en vervolgens **Uitvoeren** te selecteren op de opdrachtbalk.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="ffcbf-174">Zo voert exports uit zonder actieve planning.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="ffcbf-175">Een export verwijderen</span><span class="sxs-lookup"><span data-stu-id="ffcbf-175">Remove an Export</span></span>

1. <span data-ttu-id="ffcbf-176">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ffcbf-177">Selecteer de export die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="ffcbf-178">Selecteer **Verwijderen** op de opdrachtbalk.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="ffcbf-179">Bevestig de verwijdering door **Verwijderen** te selecteren op het bevestigingsscherm.</span><span class="sxs-lookup"><span data-stu-id="ffcbf-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
