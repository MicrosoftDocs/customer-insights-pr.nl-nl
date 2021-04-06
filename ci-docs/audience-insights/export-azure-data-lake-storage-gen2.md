---
title: Customer Insights-gegevens exporteren naar Azure Data Lake Storage Gen2
description: Ontdek hoe u de verbinding met Azure Data Lake Storage Gen2 configureert.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596631"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="e1882-103">Connector voor Azure Data Lake Storage Gen2 (preview)</span><span class="sxs-lookup"><span data-stu-id="e1882-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="e1882-104">Sla uw Customer Insights-gegevens op in Azure Data Lake Storage Gen2 of gebruik deze om uw gegevens over te brengen naar andere toepassingen.</span><span class="sxs-lookup"><span data-stu-id="e1882-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="e1882-105">De connector voor Azure Data Lake Storage Gen2 configureren</span><span class="sxs-lookup"><span data-stu-id="e1882-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="e1882-106">Ga in doelgroepinzichten naar **Beheer** > **Exportbestemmingen**.</span><span class="sxs-lookup"><span data-stu-id="e1882-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="e1882-107">Selecteer onder **Azure Data Lake Storage Gen2** de optie **Instellen**.</span><span class="sxs-lookup"><span data-stu-id="e1882-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="e1882-108">Geef uw bestemming een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="e1882-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="e1882-109">Voer **Accountnaam**, **Accountsleutel** **Container** voor uw Azure Data Lake Storage Gen2 in.</span><span class="sxs-lookup"><span data-stu-id="e1882-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="e1882-110">Voor informatie over het maken van een opslagaccount om te gebruiken met Azure Data Lake Storage Gen2, zie [Een opslagaccount maken](/azure/storage/blobs/create-data-lake-storage-account)​.</span><span class="sxs-lookup"><span data-stu-id="e1882-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="e1882-111">Zie [Instellingen voor opslagaccount beheren in de Azure-portal](/azure/storage/common/storage-account-manage)​voor meer informatie over het vinden van de accountnaam en accountsleutel voor Azure Data Lake Gen2.</span><span class="sxs-lookup"><span data-stu-id="e1882-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="e1882-112">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="e1882-112">Select **Next**.</span></span>

1. <span data-ttu-id="e1882-113">Selecteer het vakje naast elk van de entiteiten die u naar deze bestemming wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="e1882-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="e1882-114">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="e1882-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="e1882-115">De gegevens exporteren</span><span class="sxs-lookup"><span data-stu-id="e1882-115">Export the data</span></span>

<span data-ttu-id="e1882-116">U kunt [gegevens op aanvraag exporteren](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e1882-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="e1882-117">De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e1882-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>