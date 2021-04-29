---
title: Verbindingen met andere services van Customer Insights.
description: Deel gegevens met andere services.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 106dbc26f95b309821d738e1484b1eaa79dd225b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896091"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="ca8b2-103">Overzicht van Verbindingen (preview)</span><span class="sxs-lookup"><span data-stu-id="ca8b2-103">Connections (preview) overview</span></span>

<span data-ttu-id="ca8b2-104">Verbindingen zijn de sleutel om het delen van gegevens van en naar Customer Insights mogelijk te maken.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="ca8b2-105">Elke verbinding brengt het delen van gegevens tot stand met een specifieke service.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="ca8b2-106">Verbindingen vormen de basis voor het [configureren van verrijkingen van derden](enrichment-hub.md) en het [configureren van exports](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="ca8b2-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="ca8b2-107">Dezelfde verbinding kan meerdere keren worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="ca8b2-108">Eén verbinding met Dynamics 365 Marketing werkt bijvoorbeeld voor meerdere exports en één Leadspace-verbinding kan worden gebruikt voor verschillende verrijkingen.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="ca8b2-109">Ga naar **Beheerder** > **Verbindingen** om verbindingen te maken en te bekijken.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="ca8b2-110">Het tabblad **Verbindingen** laat u alle actieve verbindingen zien.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="ca8b2-111">De lijst toont een rij voor elke verbinding.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="ca8b2-112">Krijg een snel overzicht met beschrijving en ontdek wat u kunt doen met elke uitbreidingsoptie op het tabblad **Ontdekken**.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="ca8b2-113">Exports</span><span class="sxs-lookup"><span data-stu-id="ca8b2-113">Exports</span></span>

<span data-ttu-id="ca8b2-114">Alleen beheerders kunnen nieuwe verbindingen configureren, maar ze kunnen inzenders toegang verlenen om bestaande verbindingen te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="ca8b2-115">Beheerders bepalen waar gegevens naartoe kunnen, inzenders bepalen de nettolading en de frequentie die aan hun behoeften voldoen.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="ca8b2-116">Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="ca8b2-117">Verrijkingen</span><span class="sxs-lookup"><span data-stu-id="ca8b2-117">Enrichments</span></span>

<span data-ttu-id="ca8b2-118">Alleen beheerders kunnen nieuwe verbindingen configureren, maar de gemaakte verbindingen zijn altijd beschikbaar voor zowel beheerders als inzenders.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="ca8b2-119">Beheerders beheren referenties en geven toestemming voor gegevensoverdrachten.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="ca8b2-120">De verbindingen kunnen vervolgens door zowel beheerders als inzenders worden gebruikt voor verrijkingen.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="ca8b2-121">Een nieuwe verbinding toevoegen</span><span class="sxs-lookup"><span data-stu-id="ca8b2-121">Add a new connection</span></span>

<span data-ttu-id="ca8b2-122">Als u verbindingen wilt toevoegen, moet u over [beheerdersmachtigingen](permissions.md) beschikken.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="ca8b2-123">Als u verbinding maakt met andere Microsoft-services, gaan we ervan uit dat beide services zich in dezelfde organisatie bevinden.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="ca8b2-124">Ga naar **Beheerder** > **Verbindingen (preview)**.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="ca8b2-125">Ga naar het tabblad **Verbindingen**.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="ca8b2-126">Selecteer **Verbinding toevoegen** om een nieuwe verbinding te maken.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="ca8b2-127">Kies in het vervolgkeuzemenu welk type verbinding u wilt maken.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-127">Choose from the drop-down menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="ca8b2-128">Geef in het deelvenster **Verbindingen instellen** de vereiste details op.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="ca8b2-129">De **weergavenaam** en het type verbinding beschrijven een verbinding.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="ca8b2-130">We raden u aan een naam te kiezen die het doel en het doel van deze verbinding uitlegt.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="ca8b2-131">De exacte velden zijn afhankelijk van de service waarmee u verbinding maakt.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="ca8b2-132">U kunt meer te weten komen over de details van een specifiek verbindingstype in het artikel over de doelservice.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="ca8b2-133">Selecteer **Opslaan** om de verbinding te maken.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="ca8b2-134">U kunt ook **Instellen** selecteren op een tegel op het tabblad **Ontdekken**.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="ca8b2-135">Inzenders toestaan om een verbinding te gebruiken voor exports</span><span class="sxs-lookup"><span data-stu-id="ca8b2-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="ca8b2-136">Bij het opzetten of bewerken van een exportverbinding, kiest u welke gebruikers deze specifieke verbinding mogen gebruiken om [exports](export-destinations.md) te definiëren.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="ca8b2-137">Standaard is er een verbinding beschikbaar voor gebruikers met de beheerdersrol.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="ca8b2-138">U kunt deze instelling wijzigen onder **Kiezen wie deze verbinding kan gebruiken** en laat gebruikers met de rol van inzender deze verbinding gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="ca8b2-139">Inzenders kunnen de verbinding niet bekijken of bewerken.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="ca8b2-140">Ze zullen alleen de weergavenaam en het type zien wanneer ze een export maken.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="ca8b2-141">Door een verbinding te delen, staat u inzenders toe een verbinding te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="ca8b2-142">Inzenders zien gedeelde verbindingen wanneer ze exports instellen.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="ca8b2-143">Zij kunnen elke export beheren die deze specifieke verbinding gebruikt.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="ca8b2-144">U kunt deze instelling wijzigen terwijl u de export behoudt die al door inzenders is gedefinieerd.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="ca8b2-145">Een verbinding bewerken</span><span class="sxs-lookup"><span data-stu-id="ca8b2-145">Edit a connection</span></span>

1. <span data-ttu-id="ca8b2-146">Ga naar **Beheerder** > **Verbindingen (preview)**.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="ca8b2-147">Ga naar het tabblad **Verbindingen**.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="ca8b2-148">Selecteer het verticale weglatingsteken voor de verbinding die u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="ca8b2-149">Selecteer **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-149">Select **Edit**.</span></span>

1. <span data-ttu-id="ca8b2-150">Wijzig de waarden die u wilt bijwerken en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="ca8b2-151">Een verbinding verwijderen</span><span class="sxs-lookup"><span data-stu-id="ca8b2-151">Remove a connection</span></span>

<span data-ttu-id="ca8b2-152">Als de verbinding die u verwijdert, wordt gebruikt door verrijkingen of exports, moet u deze eerst loskoppelen of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="ca8b2-153">Het dialoogvenster voor verwijdering leidt u naar de relevante verrijkingen of exports.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> <span data-ttu-id="ca8b2-154">Losgekoppelde verrijkingen en exports worden inactief.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="ca8b2-155">U activeert deze opnieuw door er een andere verbinding aan toe te voegen op de pagina [Verrijkingen](enrichment-hub.md) of [Exports](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="ca8b2-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="ca8b2-156">Ga naar **Beheerder** > **Verbindingen (preview)**.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="ca8b2-157">Ga naar het tabblad **Verbindingen**.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="ca8b2-158">Selecteer het verticale weglatingsteken voor de verbinding die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="ca8b2-159">Selecteer **Verwijderen** in het vervolgkeuzemenu.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="ca8b2-160">Er wordt een bevestigingsvenster weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="ca8b2-161">Als er verrijkingen of exports zijn die deze verbinding gebruiken, selecteert u de knop om te zien wat de verbinding gebruikt.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="ca8b2-162">**Exports:** u kunt ervoor kiezen om de exports te verwijderen of los te koppelen om de verbinding te kunnen verwijderen.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="ca8b2-163">Voor het loskoppelen van een export kunnen beheerders de actie **Verbinding verbreken** gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="ca8b2-164">Deze actie is beschikbaar voor individuele en meerdere geselecteerde exports.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="ca8b2-165">Door de verbinding te verbreken, behoudt u de exportconfiguratie, maar wordt deze pas uitgevoerd als er een andere verbinding aan is toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="ca8b2-166">**Verrijkingen:** u kunt ervoor kiezen om de verrijkingen te verwijderen of te deactiveren om de verbinding te kunnen verwijderen.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="ca8b2-167">Zodra de verbinding geen afhankelijkheden meer heeft, gaat u terug naar **Beheerder** > **Verbindingen** en probeert u de verbinding opnieuw te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="ca8b2-168">Selecteer **Verwijderen** om het verwijderen te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="ca8b2-168">To confirm the deletion select **Remove**.</span></span>

