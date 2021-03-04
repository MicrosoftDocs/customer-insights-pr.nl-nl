---
title: Customer Insights-gegevens exporteren naar Azure Data Lake Storage Gen2
description: Ontdek hoe u de verbinding met Azure Data Lake Storage Gen2 configureert.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477173"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="ed719-103">Connector voor Azure Data Lake Storage Gen2 (preview)</span><span class="sxs-lookup"><span data-stu-id="ed719-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="ed719-104">Sla uw Customer Insights-gegevens op in Azure Data Lake Storage Gen2 of gebruik deze om uw gegevens over te brengen naar andere toepassingen.</span><span class="sxs-lookup"><span data-stu-id="ed719-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="ed719-105">De connector voor Azure Data Lake Storage Gen2 configureren</span><span class="sxs-lookup"><span data-stu-id="ed719-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="ed719-106">Ga in doelgroepinzichten naar **Beheer** > **Exportbestemmingen**.</span><span class="sxs-lookup"><span data-stu-id="ed719-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ed719-107">Selecteer onder **Azure Data Lake Storage Gen2** de optie **Instellen**.</span><span class="sxs-lookup"><span data-stu-id="ed719-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="ed719-108">Geef uw bestemming een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="ed719-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="ed719-109">Voer **Accountnaam**, **Accountsleutel** **Container** voor uw Azure Data Lake Storage Gen2 in.</span><span class="sxs-lookup"><span data-stu-id="ed719-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="ed719-110">Voor informatie over het maken van een opslagaccount om te gebruiken met Azure Data Lake Storage Gen2, zie [Een opslagaccount maken](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account)​.</span><span class="sxs-lookup"><span data-stu-id="ed719-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="ed719-111">Zie [Instellingen voor opslagaccount beheren in de Azure-portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage)​voor meer informatie over het vinden van de accountnaam en accountsleutel voor Azure Data Lake Gen2.</span><span class="sxs-lookup"><span data-stu-id="ed719-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="ed719-112">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="ed719-112">Select **Next**.</span></span>

1. <span data-ttu-id="ed719-113">Selecteer het vakje naast elk van de entiteiten die u naar deze bestemming wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="ed719-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="ed719-114">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ed719-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="ed719-115">De gegevens exporteren</span><span class="sxs-lookup"><span data-stu-id="ed719-115">Export the data</span></span>

<span data-ttu-id="ed719-116">U kunt [gegevens op aanvraag exporteren](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ed719-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="ed719-117">De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ed719-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
