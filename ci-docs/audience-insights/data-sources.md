---
title: Gegevensbronnen gebruiken om gegevens op te nemen
description: Meer informatie over hoe u gegevens uit verschillende bronnen kunt importeren.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 68aa1b56fb634da80a0c64db72f778d57507104d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269692"
---
# <a name="data-sources-overview"></a><span data-ttu-id="ff69a-103">Overzicht van gegevensbronnen</span><span class="sxs-lookup"><span data-stu-id="ff69a-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="ff69a-104">De doelgroepinzichten-mogelijkheid in Dynamics 365 Customer Insights maakt verbinding met gegevens uit uiteenlopende bronnen.</span><span class="sxs-lookup"><span data-stu-id="ff69a-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="ff69a-105">Verbinden met een gegevensbron wordt vaak *gegevensopname* genoemd.</span><span class="sxs-lookup"><span data-stu-id="ff69a-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="ff69a-106">Na het opnemen van de gegevens kunt u ze [samenvoegen](data-unification.md) en actie ondernemen.</span><span class="sxs-lookup"><span data-stu-id="ff69a-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="ff69a-107">Een gegevensbron toevoegen</span><span class="sxs-lookup"><span data-stu-id="ff69a-107">Add a data source</span></span>

<span data-ttu-id="ff69a-108">Raadpleeg de gedetailleerde artikelen over het toevoegen van een gegevensbron, afhankelijk van de optie die u kiest.</span><span class="sxs-lookup"><span data-stu-id="ff69a-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="ff69a-109">U kunt een gegevensbron op drie manieren toevoegen:</span><span class="sxs-lookup"><span data-stu-id="ff69a-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="ff69a-110">Via tientallen Power Query-connectors</span><span class="sxs-lookup"><span data-stu-id="ff69a-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="ff69a-111">Via een Common Data Model-map</span><span class="sxs-lookup"><span data-stu-id="ff69a-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="ff69a-112">Via uw eigen Common Data Service-lake</span><span class="sxs-lookup"><span data-stu-id="ff69a-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="ff69a-113">U kunt nog geen gegevens toevoegen uit on-premises gegevensbronnen.</span><span class="sxs-lookup"><span data-stu-id="ff69a-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="ff69a-114">Opgenomen gegevens bekijken</span><span class="sxs-lookup"><span data-stu-id="ff69a-114">Review ingested data</span></span>

<span data-ttu-id="ff69a-115">U ziet de naam van elke opgenomen gegevensbron, de status en de laatste keer dat de gegevens voor die bron zijn vernieuwd.</span><span class="sxs-lookup"><span data-stu-id="ff69a-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="ff69a-116">U kunt de lijst met gegevensbronnen op elke kolom sorteren.</span><span class="sxs-lookup"><span data-stu-id="ff69a-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ff69a-117">![Gegevensbron toegevoegd](media/configure-data-datasource-added.png "Gegevensbron toegevoegd")</span><span class="sxs-lookup"><span data-stu-id="ff69a-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="ff69a-118">Status</span><span class="sxs-lookup"><span data-stu-id="ff69a-118">Status</span></span>  |<span data-ttu-id="ff69a-119">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="ff69a-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="ff69a-120">Voltooid</span><span class="sxs-lookup"><span data-stu-id="ff69a-120">Successful</span></span>   |<span data-ttu-id="ff69a-121">Gegevensbron is opgenomen als een tijd wordt vermeld in de kolom **Vernieuwd**.</span><span class="sxs-lookup"><span data-stu-id="ff69a-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="ff69a-122">Niet gestart</span><span class="sxs-lookup"><span data-stu-id="ff69a-122">Not started</span></span>   |<span data-ttu-id="ff69a-123">De gegevensbron heeft nog geen gegevens opgenomen of bevindt zich nog in de conceptmodus.</span><span class="sxs-lookup"><span data-stu-id="ff69a-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="ff69a-124">Vernieuwen</span><span class="sxs-lookup"><span data-stu-id="ff69a-124">Refreshing</span></span>    |<span data-ttu-id="ff69a-125">De opname van gegevens wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="ff69a-125">Data ingestion is in progress.</span></span> <span data-ttu-id="ff69a-126">U kunt deze bewerking annuleren door **Stoppen met vernieuwen** te selecteren in de kolom **Acties**.</span><span class="sxs-lookup"><span data-stu-id="ff69a-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="ff69a-127">Als u het vernieuwen van een gegevensbron stopt, keert het terug naar de laatste vernieuwingsstatus.</span><span class="sxs-lookup"><span data-stu-id="ff69a-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="ff69a-128">Mislukt</span><span class="sxs-lookup"><span data-stu-id="ff69a-128">Failed</span></span>     |<span data-ttu-id="ff69a-129">Er zijn fouten opgetreden bij de gegevensopname.</span><span class="sxs-lookup"><span data-stu-id="ff69a-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="ff69a-130">Selecteer de waarde in de kolom **Status** van een willekeurige gegevensbron voor meer details.</span><span class="sxs-lookup"><span data-stu-id="ff69a-130">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="ff69a-131">Vouw in het deelvenster **Voortgangsgegevens** de optie **Gegevensbronnen** uit.</span><span class="sxs-lookup"><span data-stu-id="ff69a-131">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="ff69a-132">Selecteer **Details weergeven** voor meer informatie over de vernieuwingsstatus, inclusief foutdetails en downstream procesupdates.</span><span class="sxs-lookup"><span data-stu-id="ff69a-132">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="ff69a-133">Het laden van gegevens kan enige tijd in beslag nemen.</span><span class="sxs-lookup"><span data-stu-id="ff69a-133">Loading data can take some time.</span></span> <span data-ttu-id="ff69a-134">Na een succesvolle vernieuwing kunnen de opgenomen gegevens worden bekeken vanaf de pagina **Entiteiten**.</span><span class="sxs-lookup"><span data-stu-id="ff69a-134">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="ff69a-135">Zie [Entiteiten](entities.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ff69a-135">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="ff69a-136">Een gegevensbron vernieuwen</span><span class="sxs-lookup"><span data-stu-id="ff69a-136">Refresh a data source</span></span>

<span data-ttu-id="ff69a-137">Gegevensbronnen kunnen automatisch worden vernieuwd of op aanvraag handmatig worden vernieuwd.</span><span class="sxs-lookup"><span data-stu-id="ff69a-137">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="ff69a-138">Ga naar **Beheer** > **Systeem** > [**Planning**](system.md#schedule-tab) om geplande vernieuwingen van al uw opgenomen gegevensbronnen te configureren.</span><span class="sxs-lookup"><span data-stu-id="ff69a-138">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="ff69a-139">Volg deze stappen om een gegevensbron op aanvraag te vernieuwen:</span><span class="sxs-lookup"><span data-stu-id="ff69a-139">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="ff69a-140">Ga in doelgroepinzichten naar **Gegevens** > **Gegevensbronnen**</span><span class="sxs-lookup"><span data-stu-id="ff69a-140">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="ff69a-141">Selecteer het verticale beletselteken naast de gegevensbron die u wilt vernieuwen en selecteer **Vernieuwen** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="ff69a-141">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="ff69a-142">De gegevensbron wordt nu geactiveerd voor een handmatige vernieuwing.</span><span class="sxs-lookup"><span data-stu-id="ff69a-142">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="ff69a-143">Als u een gegevensbron vernieuwt, worden zowel de entiteitsplanning als de gegevens bijgewerkt voor alle entiteiten die zijn gespecificeerd in de gegevensbron.</span><span class="sxs-lookup"><span data-stu-id="ff69a-143">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="ff69a-144">Selecteer **Vernieuwen stoppen** als u een bestaande vernieuwing wilt annuleren, waarna de gegevensbron terugkeert naar de laatste vernieuwingsstatus.</span><span class="sxs-lookup"><span data-stu-id="ff69a-144">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="ff69a-145">Een gegevensbron verwijderen</span><span class="sxs-lookup"><span data-stu-id="ff69a-145">Delete a data source</span></span>

1. <span data-ttu-id="ff69a-146">Ga in doelgroepinzichten naar **Gegevens** > **Gegevensbronnen**.</span><span class="sxs-lookup"><span data-stu-id="ff69a-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="ff69a-147">Selecteer het verticale weglatingsteken naast de gegevensbron die u wilt verwijderen en selecteer **Verwijderen** uit het vervolgkeuzemenu.</span><span class="sxs-lookup"><span data-stu-id="ff69a-147">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="ff69a-148">Bevestig de verwijdering.</span><span class="sxs-lookup"><span data-stu-id="ff69a-148">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]