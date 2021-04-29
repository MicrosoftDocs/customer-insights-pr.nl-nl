---
title: Gegevens exporteren vanuit Customer Insights
description: Beheer exports om gegevens te delen.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896137"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="34804-103">Overzicht van Exports (preview)</span><span class="sxs-lookup"><span data-stu-id="34804-103">Exports (preview) overview</span></span>

<span data-ttu-id="34804-104">De pagina **Exports** toont u alle geconfigureerde exports.</span><span class="sxs-lookup"><span data-stu-id="34804-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="34804-105">Exports delen specifieke gegevens met verschillende toepassingen.</span><span class="sxs-lookup"><span data-stu-id="34804-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="34804-106">Ze kunnen klantprofielen of entiteiten, schema's en toewijzingsdetails bevatten.</span><span class="sxs-lookup"><span data-stu-id="34804-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="34804-107">Elke export vereist een [verbinding, opgezet door een beheerder, om de verificatie en toegang te beheren](connections.md).</span><span class="sxs-lookup"><span data-stu-id="34804-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="34804-108">Tot maart 2021 creëerden exports automatisch een verbinding met de bijbehorende service.</span><span class="sxs-lookup"><span data-stu-id="34804-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="34804-109">Exports vereisen nu een [verbinding die is gemaakt en gedeeld door een beheerder](connections.md) voordat u ze kunt maken.</span><span class="sxs-lookup"><span data-stu-id="34804-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="34804-110">Ga naar **Gegevens** > **Exports** om de pagina met exports te bekijken.</span><span class="sxs-lookup"><span data-stu-id="34804-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="34804-111">Alle gebruikersrollen hebben toegang om geconfigureerde exports te bekijken.</span><span class="sxs-lookup"><span data-stu-id="34804-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="34804-112">Gebruik van het zoekveld in de opdrachtbalk om exports te zoeken op naam, verbindingsnaam of verbindingstype.</span><span class="sxs-lookup"><span data-stu-id="34804-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="34804-113">Een nieuwe export instellen</span><span class="sxs-lookup"><span data-stu-id="34804-113">Set up a new export</span></span>

<span data-ttu-id="34804-114">Als u een export wilt instellen of bewerken, moet u over verbindingen beschikken.</span><span class="sxs-lookup"><span data-stu-id="34804-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="34804-115">Verbindingen zijn afhankelijk van uw [gebruikersrol](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="34804-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="34804-116">Beheerders hebben toegang tot alle verbindingen.</span><span class="sxs-lookup"><span data-stu-id="34804-116">Administrators have access to all connections.</span></span> <span data-ttu-id="34804-117">Ze kunnen ook nieuwe verbindingen maken bij het opzetten van een export.</span><span class="sxs-lookup"><span data-stu-id="34804-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="34804-118">Inzenders kunnen toegang hebben tot specifieke verbindingen.</span><span class="sxs-lookup"><span data-stu-id="34804-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="34804-119">Zij zijn afhankelijk van beheerders om verbindingen te configureren en te delen.</span><span class="sxs-lookup"><span data-stu-id="34804-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="34804-120">Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="34804-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="34804-121">Kijkers kunnen alleen bestaande exports bekijken, maar deze niet maken.</span><span class="sxs-lookup"><span data-stu-id="34804-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="34804-122">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="34804-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="34804-123">Selecteer **Export toevoegen** om een nieuwe exportbestemming te maken.</span><span class="sxs-lookup"><span data-stu-id="34804-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="34804-124">Selecteer in het deelvenster **Export instellen** welke verbinding u wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="34804-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="34804-125">[Verbindingen](connections.md) worden beheerd door beheerders.</span><span class="sxs-lookup"><span data-stu-id="34804-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="34804-126">Geef de vereiste details op en selecteer **Opslaan** om de export te maken.</span><span class="sxs-lookup"><span data-stu-id="34804-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="34804-127">Een export bewerken</span><span class="sxs-lookup"><span data-stu-id="34804-127">Edit an export</span></span>

1. <span data-ttu-id="34804-128">Selecteer het verticale weglatingsteken voor de exportbestemming die u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="34804-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="34804-129">Selecteer **Bewerken** in het vervolgkeuzemenu.</span><span class="sxs-lookup"><span data-stu-id="34804-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="34804-130">Wijzig de waarden die u wilt bijwerken en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="34804-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="34804-131">Exports en exportdetails weergeven</span><span class="sxs-lookup"><span data-stu-id="34804-131">View Exports and export details</span></span>

<span data-ttu-id="34804-132">Nadat u exportbestemmingen hebt gemaakt, worden deze vermeld bij **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="34804-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="34804-133">Alle gebruikers kunnen zien welke gegevens worden gedeeld en wat de meest recente status is.</span><span class="sxs-lookup"><span data-stu-id="34804-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="34804-134">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="34804-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="34804-135">Gebruikers zonder machtigingen voor bewerken selecteren **Weergeven** in plaats van **Bewerken** om de exportdetails te bekijken.</span><span class="sxs-lookup"><span data-stu-id="34804-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="34804-136">Dit zijpaneel toont de instellingen van deze export.</span><span class="sxs-lookup"><span data-stu-id="34804-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="34804-137">Zonder bewerkingsrechten kunt u geen waarden wijzigen.</span><span class="sxs-lookup"><span data-stu-id="34804-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="34804-138">Selecteer **Sluiten** om terug te keren naar de pagina met exports.</span><span class="sxs-lookup"><span data-stu-id="34804-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="34804-139">Exports op aanvraag uitvoeren</span><span class="sxs-lookup"><span data-stu-id="34804-139">Run exports on demand</span></span>

<span data-ttu-id="34804-140">Na het configureren van een export, wordt deze uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab) zolang er een werkende verbinding is.</span><span class="sxs-lookup"><span data-stu-id="34804-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="34804-141">Als u gegevens wilt exporteren zonder te wachten op een geplande vernieuwing, gaat u naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="34804-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="34804-142">U hebt twee opties:</span><span class="sxs-lookup"><span data-stu-id="34804-142">You have two options:</span></span>

- <span data-ttu-id="34804-143">Als u alle exports wilt uitvoeren, selecteert u **Alles uitvoeren** op de opdrachtbalk.</span><span class="sxs-lookup"><span data-stu-id="34804-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="34804-144">Als u een enkele export wilt uitvoeren, selecteert u het beletselteken (...) in een lijstitem en kiest u vervolgens **Uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="34804-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="34804-145">Een export verwijderen</span><span class="sxs-lookup"><span data-stu-id="34804-145">Remove an Export</span></span>

1. <span data-ttu-id="34804-146">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="34804-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="34804-147">Selecteer het verticale weglatingsteken voor de export die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="34804-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="34804-148">Selecteer **Verwijderen** in het vervolgkeuzemenu.</span><span class="sxs-lookup"><span data-stu-id="34804-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="34804-149">Bevestig de verwijdering door **Verwijderen** te selecteren op het bevestigingsscherm.</span><span class="sxs-lookup"><span data-stu-id="34804-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
