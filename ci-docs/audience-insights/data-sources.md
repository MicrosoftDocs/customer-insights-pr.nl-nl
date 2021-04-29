---
title: Gegevensbronnen gebruiken om gegevens op te nemen
description: Meer informatie over hoe u gegevens uit verschillende bronnen kunt importeren.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 0fc13d3ac0a5176637b6fe481dabe0b2aec11649
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887888"
---
# <a name="data-sources-overview"></a><span data-ttu-id="ed6ff-103">Overzicht van gegevensbronnen</span><span class="sxs-lookup"><span data-stu-id="ed6ff-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="ed6ff-104">De doelgroepinzichten-mogelijkheid in Dynamics 365 Customer Insights maakt verbinding met gegevens uit uiteenlopende bronnen.</span><span class="sxs-lookup"><span data-stu-id="ed6ff-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="ed6ff-105">Verbinden met een gegevensbron wordt vaak *gegevensopname* genoemd.</span><span class="sxs-lookup"><span data-stu-id="ed6ff-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="ed6ff-106">Na het opnemen van de gegevens kunt u ze [samenvoegen](data-unification.md) en actie ondernemen.</span><span class="sxs-lookup"><span data-stu-id="ed6ff-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="ed6ff-107">Een gegevensbron toevoegen</span><span class="sxs-lookup"><span data-stu-id="ed6ff-107">Add a data source</span></span>

<span data-ttu-id="ed6ff-108">Raadpleeg de gedetailleerde artikelen over het toevoegen van een gegevensbron, afhankelijk van de optie die u kiest.</span><span class="sxs-lookup"><span data-stu-id="ed6ff-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="ed6ff-109">U kunt een gegevensbron op drie manieren toevoegen:</span><span class="sxs-lookup"><span data-stu-id="ed6ff-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="ed6ff-110">Via tientallen Power Query-connectors</span><span class="sxs-lookup"><span data-stu-id="ed6ff-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="ed6ff-111">Via een Common Data Model-map</span><span class="sxs-lookup"><span data-stu-id="ed6ff-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="ed6ff-112">Via uw eigen Common Data Service-lake</span><span class="sxs-lookup"><span data-stu-id="ed6ff-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="ed6ff-113">Gegevens toevoegen vanuit on-premises gegevensbronnen</span><span class="sxs-lookup"><span data-stu-id="ed6ff-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="ed6ff-114">Het opnemen van gegevens uit on-premises gegevensbronnen in Doelgroepinzichten wordt ondersteund op basis van Power Platform-gegevensstromen.</span><span class="sxs-lookup"><span data-stu-id="ed6ff-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="ed6ff-115">Gegevensstromen kunnen worden ingeschakeld in Customer Insights door [het verstrekken van de URL van de Microsoft Dataverse-omgeving](manage-environments.md#create-an-environment-in-an-existing-organization) bij het opzetten van de omgeving.</span><span class="sxs-lookup"><span data-stu-id="ed6ff-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="ed6ff-116">Gegevensbronnen die worden gemaakt na het koppelen van een Dataverse-omgeving met Customer Insights maken standaard gebruik van [Power Platform-gegevensstromen](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365).</span><span class="sxs-lookup"><span data-stu-id="ed6ff-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="ed6ff-117">Gegevensstromen ondersteunen on-premises connectiviteit met behulp van de gegevensgateways.</span><span class="sxs-lookup"><span data-stu-id="ed6ff-117">Dataflows support on-prem connectivity using the data gateways.</span></span> <span data-ttu-id="ed6ff-118">Verwijder gegevensbronnen die al bestonden vóór een Dataverse-omgeving werd gekoppeld en maak deze opnieuw om de on-premises gegevensgateways te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ed6ff-118">Remove and recreate data sources that existed before a Dataverse environment was associated to use the on-premises data gateways.</span></span>

<span data-ttu-id="ed6ff-119">Gegevensgateways van een bestaande Power BI- of Power Apps-omgeving worden zichtbaar en u kunt deze opnieuw gebruiken in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ed6ff-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="ed6ff-120">De pagina met gegevensbronnen toont koppelingen om naar de Power Platform-omgeving te gaan waar u on-premises gegevensgateways kunt bekijken en configureren.</span><span class="sxs-lookup"><span data-stu-id="ed6ff-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

:::image type="content" source="media/data-sources-onpremises-gateways.png" alt-text="Schermopname van de pagina met gegevensbronnen die koppelingen bevat die naar de Power Platform-omgeving wijzen.":::

## <a name="review-ingested-data"></a><span data-ttu-id="ed6ff-122">Opgenomen gegevens bekijken</span><span class="sxs-lookup"><span data-stu-id="ed6ff-122">Review ingested data</span></span>

<span data-ttu-id="ed6ff-123">U ziet de naam van elke opgenomen gegevensbron, de status en de laatste keer dat de gegevens voor die bron zijn vernieuwd.</span><span class="sxs-lookup"><span data-stu-id="ed6ff-123">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="ed6ff-124">U kunt de lijst met gegevensbronnen op elke kolom sorteren.</span><span class="sxs-lookup"><span data-stu-id="ed6ff-124">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ed6ff-125">![Gegevensbron toegevoegd](media/configure-data-datasource-added.png "Gegevensbron toegevoegd")</span><span class="sxs-lookup"><span data-stu-id="ed6ff-125">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="ed6ff-126">Status</span><span class="sxs-lookup"><span data-stu-id="ed6ff-126">Status</span></span>  |<span data-ttu-id="ed6ff-127">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="ed6ff-127">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="ed6ff-128">Voltooid</span><span class="sxs-lookup"><span data-stu-id="ed6ff-128">Successful</span></span>   |<span data-ttu-id="ed6ff-129">Gegevensbron is opgenomen als een tijd wordt vermeld in de kolom **Vernieuwd**.</span><span class="sxs-lookup"><span data-stu-id="ed6ff-129">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="ed6ff-130">Niet gestart</span><span class="sxs-lookup"><span data-stu-id="ed6ff-130">Not started</span></span>   |<span data-ttu-id="ed6ff-131">De gegevensbron heeft nog geen gegevens opgenomen of bevindt zich nog in de conceptmodus.</span><span class="sxs-lookup"><span data-stu-id="ed6ff-131">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="ed6ff-132">Vernieuwen</span><span class="sxs-lookup"><span data-stu-id="ed6ff-132">Refreshing</span></span>    |<span data-ttu-id="ed6ff-133">De opname van gegevens wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="ed6ff-133">Data ingestion is in progress.</span></span> <span data-ttu-id="ed6ff-134">U kunt deze bewerking annuleren door **Stoppen met vernieuwen** te selecteren in de kolom **Acties**.</span><span class="sxs-lookup"><span data-stu-id="ed6ff-134">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="ed6ff-135">Als u het vernieuwen van een gegevensbron stopt, keert het terug naar de laatste vernieuwingsstatus.</span><span class="sxs-lookup"><span data-stu-id="ed6ff-135">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="ed6ff-136">Mislukt</span><span class="sxs-lookup"><span data-stu-id="ed6ff-136">Failed</span></span>     |<span data-ttu-id="ed6ff-137">Er zijn fouten opgetreden bij de gegevensopname.</span><span class="sxs-lookup"><span data-stu-id="ed6ff-137">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="ed6ff-138">Selecteer de waarde in de kolom **Status** van een willekeurige gegevensbron voor meer details.</span><span class="sxs-lookup"><span data-stu-id="ed6ff-138">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="ed6ff-139">Vouw in het deelvenster **Voortgangsgegevens** de optie **Gegevensbronnen** uit.</span><span class="sxs-lookup"><span data-stu-id="ed6ff-139">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="ed6ff-140">Selecteer **Details weergeven** voor meer informatie over de vernieuwingsstatus, inclusief foutdetails en downstream procesupdates.</span><span class="sxs-lookup"><span data-stu-id="ed6ff-140">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="ed6ff-141">Het laden van gegevens kan enige tijd in beslag nemen.</span><span class="sxs-lookup"><span data-stu-id="ed6ff-141">Loading data can take some time.</span></span> <span data-ttu-id="ed6ff-142">Na een succesvolle vernieuwing kunnen de opgenomen gegevens worden bekeken vanaf de pagina **Entiteiten**.</span><span class="sxs-lookup"><span data-stu-id="ed6ff-142">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="ed6ff-143">Zie [Entiteiten](entities.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ed6ff-143">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="ed6ff-144">Een gegevensbron vernieuwen</span><span class="sxs-lookup"><span data-stu-id="ed6ff-144">Refresh a data source</span></span>

<span data-ttu-id="ed6ff-145">Gegevensbronnen kunnen automatisch worden vernieuwd of op aanvraag handmatig worden vernieuwd.</span><span class="sxs-lookup"><span data-stu-id="ed6ff-145">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="ed6ff-146">Ga naar **Beheer** > **Systeem** > [**Planning**](system.md#schedule-tab) om geplande vernieuwingen van al uw opgenomen gegevensbronnen te configureren.</span><span class="sxs-lookup"><span data-stu-id="ed6ff-146">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="ed6ff-147">Volg deze stappen om een gegevensbron op aanvraag te vernieuwen:</span><span class="sxs-lookup"><span data-stu-id="ed6ff-147">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="ed6ff-148">Ga in doelgroepinzichten naar **Gegevens** > **Gegevensbronnen**</span><span class="sxs-lookup"><span data-stu-id="ed6ff-148">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="ed6ff-149">Selecteer het verticale beletselteken naast de gegevensbron die u wilt vernieuwen en selecteer **Vernieuwen** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="ed6ff-149">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="ed6ff-150">De gegevensbron wordt nu geactiveerd voor een handmatige vernieuwing.</span><span class="sxs-lookup"><span data-stu-id="ed6ff-150">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="ed6ff-151">Als u een gegevensbron vernieuwt, worden zowel het entiteitsschema als de gegevens bijgewerkt voor alle entiteiten die zijn opgegeven in de gegevensbron.</span><span class="sxs-lookup"><span data-stu-id="ed6ff-151">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="ed6ff-152">Selecteer **Vernieuwen stoppen** als u een bestaande vernieuwing wilt annuleren, waarna de gegevensbron terugkeert naar de laatste vernieuwingsstatus.</span><span class="sxs-lookup"><span data-stu-id="ed6ff-152">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="ed6ff-153">Een gegevensbron verwijderen</span><span class="sxs-lookup"><span data-stu-id="ed6ff-153">Delete a data source</span></span>

1. <span data-ttu-id="ed6ff-154">Ga in doelgroepinzichten naar **Gegevens** > **Gegevensbronnen**.</span><span class="sxs-lookup"><span data-stu-id="ed6ff-154">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="ed6ff-155">Selecteer het verticale weglatingsteken naast de gegevensbron die u wilt verwijderen en selecteer **Verwijderen** uit het vervolgkeuzemenu.</span><span class="sxs-lookup"><span data-stu-id="ed6ff-155">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="ed6ff-156">Bevestig de verwijdering.</span><span class="sxs-lookup"><span data-stu-id="ed6ff-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
