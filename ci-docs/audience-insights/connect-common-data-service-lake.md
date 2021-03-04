---
title: Verbinding maken met entiteiten in de Common Data Service beheerde lake
description: Gegevens importeren uit een door Common Data Service beheerd data lake.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 18b6cd3fdaf5b738877a73b520b91dbc6ded40de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267807"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="8b749-103">Verbinding maken met gegevens in een beheerd Common Data Service data lake</span><span class="sxs-lookup"><span data-stu-id="8b749-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="8b749-104">Dit artikel bevat informatie over hoe bestaande Dynamics 365-klanten snel verbinding kunnen maken met hun analytische entiteiten in het door Common Data Service beheerde lake.</span><span class="sxs-lookup"><span data-stu-id="8b749-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="8b749-105">U moet een beheerder zijn in de Common Data Service-organisatie om verder te gaan en de lijst met entiteiten te bekijken die beschikbaar zijn in het beheerde lake.</span><span class="sxs-lookup"><span data-stu-id="8b749-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="8b749-106">Belangrijke aandachtspunten</span><span class="sxs-lookup"><span data-stu-id="8b749-106">Important considerations</span></span>

<span data-ttu-id="8b749-107">Gegevens die worden opgeslagen in online services, zoals Azure Data Lake Storage, kunnen worden opgeslagen op een andere locatie dan waar gegevens worden verwerkt of opgeslagen in Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8b749-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="8b749-108"> Door gegevens te importeren die zijn opgeslagen in online services, gaat u ermee akkoord dat gegevens kunnen worden overgedragen naar en opgeslagen met Dynamics 365 Customer Insights.  [Meer informatie in het Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="8b749-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="8b749-109">Verbinding maken met een door Common Data Service beheerd lake</span><span class="sxs-lookup"><span data-stu-id="8b749-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="8b749-110">Ga in doelgroepinzichten naar **Gegevens** > **Gegevensbronnen**.</span><span class="sxs-lookup"><span data-stu-id="8b749-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="8b749-111">Selecteer **Gegevensbron toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="8b749-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="8b749-112">Selecteer **Verbinden met Common Data Service** en selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="8b749-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="8b749-113">Voer een **naam** in voor de gegevensbron en selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="8b749-113">Enter a **Name** for the data source and select **Next**.</span></span> <span data-ttu-id="8b749-114">Naamrichtlijnen:</span><span class="sxs-lookup"><span data-stu-id="8b749-114">Name guidelines:</span></span> 
   - <span data-ttu-id="8b749-115">Begin met een letter.</span><span class="sxs-lookup"><span data-stu-id="8b749-115">Start with a letter.</span></span>
   - <span data-ttu-id="8b749-116">Gebruik alleen letters en cijfers.</span><span class="sxs-lookup"><span data-stu-id="8b749-116">Use letters and numbers only.</span></span> <span data-ttu-id="8b749-117">Speciale tekens en spaties zijn niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="8b749-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="8b749-118">Gebruik minimaal 3 en maximaal 64 tekens.</span><span class="sxs-lookup"><span data-stu-id="8b749-118">Use between 3 and 64 characters.</span></span>

5. <span data-ttu-id="8b749-119">Geef het **Serveradres** op voor uw Common Data Service-organisatie en selecteer **Aanmelden**.</span><span class="sxs-lookup"><span data-stu-id="8b749-119">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8b749-120">![Dialoogvenster om Common Data Service-serveradres in te voeren](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="8b749-120">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="8b749-121">Selecteer de entiteiten die u wilt opnemen uit de beschikbare lijst.</span><span class="sxs-lookup"><span data-stu-id="8b749-121">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="8b749-122">Als sommige entiteiten al zijn geselecteerd, worden ze mogelijk gebruikt door andere Dynamics 365-toepassingen (zoals Dynamics 365 Sales Insights of Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="8b749-122">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="8b749-123">U kunt de selectie niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="8b749-123">You can't change the selection.</span></span> <span data-ttu-id="8b749-124">Deze entiteiten zijn beschikbaar zodra de gegevensbron is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="8b749-124">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8b749-125">![Dialoogvenster met een lijst van entiteiten in de Common Data Service-organisatie](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="8b749-125">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="8b749-126">Sla uw selectie op om te beginnen met het synchroniseren van de geselecteerde entiteiten met het door Common Data Service beheerde lake.</span><span class="sxs-lookup"><span data-stu-id="8b749-126">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="8b749-127">U vindt de nieuw toegevoegde verbinding op de pagina **Gegevensbronnen**.</span><span class="sxs-lookup"><span data-stu-id="8b749-127">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="8b749-128">Deze wordt in de wachtrij geplaatst voor vernieuwing en het aantal entiteiten wordt weergegeven als 0 totdat alle entiteiten zijn gesynchroniseerd.</span><span class="sxs-lookup"><span data-stu-id="8b749-128">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="8b749-129">Slechts één gegevensbron van een omgeving kan tegelijkertijd dezelfde Common Data Service beheerde lake gebruiken.</span><span class="sxs-lookup"><span data-stu-id="8b749-129">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="8b749-130">Een gegevensbron van een door Common Data Service beheerde lake bewerken</span><span class="sxs-lookup"><span data-stu-id="8b749-130">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="8b749-131">U kunt de entiteitsselectie pas bewerken nadat u de gegevensbron hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="8b749-131">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="8b749-132">Als er bijvoorbeeld extra entiteiten zijn toegevoegd aan Common Data Service en u ze ook wilt importeren.</span><span class="sxs-lookup"><span data-stu-id="8b749-132">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="8b749-133">Als u verbinding wilt maken met een andere Common Data Service, [maakt u een nieuwe gegevensbron](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="8b749-133">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="8b749-134">Ga in doelgroepinzichten naar **Gegevens** > **Gegevensbronnen**.</span><span class="sxs-lookup"><span data-stu-id="8b749-134">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="8b749-135">Selecteer het weglatingsteken naast de gegevensbron die u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="8b749-135">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="8b749-136">Selecteer de optie **Bewerken** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="8b749-136">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="8b749-137">Selecteer extra entiteiten in de beschikbare lijst met entiteiten en selecteer vervolgens **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="8b749-137">Select additional entities from the available list of entities and select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]