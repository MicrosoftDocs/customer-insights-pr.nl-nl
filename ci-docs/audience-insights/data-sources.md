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
ms.openlocfilehash: 3c0b4690e18285aa37eef481b3cfac951884ead6
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085524"
---
# <a name="data-sources-overview"></a><span data-ttu-id="b2ba2-103">Overzicht van gegevensbronnen</span><span class="sxs-lookup"><span data-stu-id="b2ba2-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="b2ba2-104">De doelgroepinzichten-mogelijkheid in Dynamics 365 Customer Insights maakt verbinding met gegevens uit uiteenlopende bronnen.</span><span class="sxs-lookup"><span data-stu-id="b2ba2-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="b2ba2-105">Verbinden met een gegevensbron wordt vaak *gegevensopname* genoemd.</span><span class="sxs-lookup"><span data-stu-id="b2ba2-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="b2ba2-106">Na het opnemen van de gegevens kunt u ze [samenvoegen](data-unification.md) en actie ondernemen.</span><span class="sxs-lookup"><span data-stu-id="b2ba2-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="b2ba2-107">Een gegevensbron toevoegen</span><span class="sxs-lookup"><span data-stu-id="b2ba2-107">Add a data source</span></span>

<span data-ttu-id="b2ba2-108">Raadpleeg de gedetailleerde artikelen over het toevoegen van een gegevensbron, afhankelijk van de optie die u kiest.</span><span class="sxs-lookup"><span data-stu-id="b2ba2-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="b2ba2-109">U kunt een gegevensbron op drie manieren toevoegen:</span><span class="sxs-lookup"><span data-stu-id="b2ba2-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="b2ba2-110">Via tientallen Power Query-connectors</span><span class="sxs-lookup"><span data-stu-id="b2ba2-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="b2ba2-111">Via een Common Data Model-map</span><span class="sxs-lookup"><span data-stu-id="b2ba2-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="b2ba2-112">Via uw eigen Common Data Service-lake</span><span class="sxs-lookup"><span data-stu-id="b2ba2-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="b2ba2-113">Gegevens toevoegen vanuit on-premises gegevensbronnen</span><span class="sxs-lookup"><span data-stu-id="b2ba2-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="b2ba2-114">Het opnemen van gegevens uit on-premises gegevensbronnen in Doelgroepinzichten wordt ondersteund op basis van Power Platform-gegevensstromen.</span><span class="sxs-lookup"><span data-stu-id="b2ba2-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="b2ba2-115">Gegevensstromen kunnen worden ingeschakeld in Customer Insights door [het verstrekken van de URL van de Microsoft Dataverse-omgeving](manage-environments.md#create-an-environment-in-an-existing-organization) bij het opzetten van de omgeving.</span><span class="sxs-lookup"><span data-stu-id="b2ba2-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="b2ba2-116">Gegevensbronnen die worden gemaakt na het koppelen van een Dataverse-omgeving met Customer Insights maken standaard gebruik van [Power Platform-gegevensstromen](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365).</span><span class="sxs-lookup"><span data-stu-id="b2ba2-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="b2ba2-117">Gegevensstromen ondersteunen on-premises connectiviteit met behulp van de gegevensgateway.</span><span class="sxs-lookup"><span data-stu-id="b2ba2-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="b2ba2-118">Verwijder gegevensbronnen die al bestonden vóór een Dataverse-omgeving werd gekoppeld en maak deze opnieuw om [de on-premises gegevensgateways te gebruiken](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span><span class="sxs-lookup"><span data-stu-id="b2ba2-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span></span>

<span data-ttu-id="b2ba2-119">Gegevensgateways van een bestaande Power BI- of Power Apps-omgeving worden zichtbaar en u kunt deze opnieuw gebruiken in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b2ba2-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="b2ba2-120">De pagina met gegevensbronnen toont koppelingen om naar de Power Platform-omgeving te gaan waar u on-premises gegevensgateways kunt bekijken en configureren.</span><span class="sxs-lookup"><span data-stu-id="b2ba2-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="b2ba2-121">Opgenomen gegevens bekijken</span><span class="sxs-lookup"><span data-stu-id="b2ba2-121">Review ingested data</span></span>

<span data-ttu-id="b2ba2-122">U ziet de naam van elke opgenomen gegevensbron, de status en de laatste keer dat de gegevens voor die bron zijn vernieuwd.</span><span class="sxs-lookup"><span data-stu-id="b2ba2-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="b2ba2-123">U kunt de lijst met gegevensbronnen op elke kolom sorteren.</span><span class="sxs-lookup"><span data-stu-id="b2ba2-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b2ba2-124">![Gegevensbron toegevoegd](media/configure-data-datasource-added.png "Gegevensbron toegevoegd")</span><span class="sxs-lookup"><span data-stu-id="b2ba2-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="b2ba2-125">Status</span><span class="sxs-lookup"><span data-stu-id="b2ba2-125">Status</span></span>  |<span data-ttu-id="b2ba2-126">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="b2ba2-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="b2ba2-127">Voltooid</span><span class="sxs-lookup"><span data-stu-id="b2ba2-127">Successful</span></span>   |<span data-ttu-id="b2ba2-128">Gegevensbron is opgenomen als een tijd wordt vermeld in de kolom **Vernieuwd**.</span><span class="sxs-lookup"><span data-stu-id="b2ba2-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="b2ba2-129">Niet gestart</span><span class="sxs-lookup"><span data-stu-id="b2ba2-129">Not started</span></span>   |<span data-ttu-id="b2ba2-130">De gegevensbron heeft nog geen gegevens opgenomen of bevindt zich nog in de conceptmodus.</span><span class="sxs-lookup"><span data-stu-id="b2ba2-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="b2ba2-131">Vernieuwen</span><span class="sxs-lookup"><span data-stu-id="b2ba2-131">Refreshing</span></span>    |<span data-ttu-id="b2ba2-132">De opname van gegevens wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="b2ba2-132">Data ingestion is in progress.</span></span> <span data-ttu-id="b2ba2-133">U kunt deze bewerking annuleren door **Stoppen met vernieuwen** te selecteren in de kolom **Acties**.</span><span class="sxs-lookup"><span data-stu-id="b2ba2-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="b2ba2-134">Als u het vernieuwen van een gegevensbron stopt, keert het terug naar de laatste vernieuwingsstatus.</span><span class="sxs-lookup"><span data-stu-id="b2ba2-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="b2ba2-135">Mislukt</span><span class="sxs-lookup"><span data-stu-id="b2ba2-135">Failed</span></span>     |<span data-ttu-id="b2ba2-136">Er zijn fouten opgetreden bij de gegevensopname.</span><span class="sxs-lookup"><span data-stu-id="b2ba2-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="b2ba2-137">Selecteer de waarde in de kolom **Status** van een willekeurige gegevensbron voor meer details.</span><span class="sxs-lookup"><span data-stu-id="b2ba2-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="b2ba2-138">Vouw in het deelvenster **Voortgangsgegevens** de optie **Gegevensbronnen** uit.</span><span class="sxs-lookup"><span data-stu-id="b2ba2-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="b2ba2-139">Selecteer **Details weergeven** voor meer informatie over de vernieuwingsstatus, inclusief foutdetails en downstream procesupdates.</span><span class="sxs-lookup"><span data-stu-id="b2ba2-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="b2ba2-140">Het laden van gegevens kan enige tijd in beslag nemen.</span><span class="sxs-lookup"><span data-stu-id="b2ba2-140">Loading data can take some time.</span></span> <span data-ttu-id="b2ba2-141">Na een succesvolle vernieuwing kunnen de opgenomen gegevens worden bekeken vanaf de pagina **Entiteiten**.</span><span class="sxs-lookup"><span data-stu-id="b2ba2-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="b2ba2-142">Zie [Entiteiten](entities.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b2ba2-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="b2ba2-143">Een gegevensbron vernieuwen</span><span class="sxs-lookup"><span data-stu-id="b2ba2-143">Refresh a data source</span></span>

<span data-ttu-id="b2ba2-144">Gegevensbronnen kunnen automatisch worden vernieuwd of op aanvraag handmatig worden vernieuwd.</span><span class="sxs-lookup"><span data-stu-id="b2ba2-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="b2ba2-145">Ga naar **Beheer** > **Systeem** > [**Planning**](system.md#schedule-tab) om geplande vernieuwingen van al uw opgenomen gegevensbronnen te configureren.</span><span class="sxs-lookup"><span data-stu-id="b2ba2-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="b2ba2-146">Volg deze stappen om een gegevensbron op aanvraag te vernieuwen:</span><span class="sxs-lookup"><span data-stu-id="b2ba2-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="b2ba2-147">Ga in doelgroepinzichten naar **Gegevens** > **Gegevensbronnen**</span><span class="sxs-lookup"><span data-stu-id="b2ba2-147">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="b2ba2-148">Selecteer het verticale beletselteken naast de gegevensbron die u wilt vernieuwen en selecteer **Vernieuwen** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="b2ba2-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="b2ba2-149">De gegevensbron wordt nu geactiveerd voor een handmatige vernieuwing.</span><span class="sxs-lookup"><span data-stu-id="b2ba2-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="b2ba2-150">Als u een gegevensbron vernieuwt, worden zowel het entiteitsschema als de gegevens bijgewerkt voor alle entiteiten die zijn opgegeven in de gegevensbron.</span><span class="sxs-lookup"><span data-stu-id="b2ba2-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="b2ba2-151">Selecteer **Vernieuwen stoppen** als u een bestaande vernieuwing wilt annuleren, waarna de gegevensbron terugkeert naar de laatste vernieuwingsstatus.</span><span class="sxs-lookup"><span data-stu-id="b2ba2-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="b2ba2-152">Een gegevensbron verwijderen</span><span class="sxs-lookup"><span data-stu-id="b2ba2-152">Delete a data source</span></span>

1. <span data-ttu-id="b2ba2-153">Ga in doelgroepinzichten naar **Gegevens** > **Gegevensbronnen**.</span><span class="sxs-lookup"><span data-stu-id="b2ba2-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="b2ba2-154">Selecteer het verticale weglatingsteken naast de gegevensbron die u wilt verwijderen en selecteer **Verwijderen** uit het vervolgkeuzemenu.</span><span class="sxs-lookup"><span data-stu-id="b2ba2-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="b2ba2-155">Bevestig de verwijdering.</span><span class="sxs-lookup"><span data-stu-id="b2ba2-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
