---
title: Customer Insights-gegevens exporteren naar Azure Data Lake Storage Gen2
description: Ontdek hoe u de verbinding met Azure Data Lake Storage Gen2 configureert.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760045"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="dc927-103">De verbinding instellen met Azure Data Lake Storage Gen2 (preview)</span><span class="sxs-lookup"><span data-stu-id="dc927-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="dc927-104">Ga naar **Beheerder** > **Verbindingen**.</span><span class="sxs-lookup"><span data-stu-id="dc927-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="dc927-105">Selecteer **Verbinding toevoegen** en kies **Azure Data Lake Gen 2** om de verbinding te configureren.</span><span class="sxs-lookup"><span data-stu-id="dc927-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="dc927-106">Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="dc927-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="dc927-107">De naam en het type verbinding beschrijven deze verbinding.</span><span class="sxs-lookup"><span data-stu-id="dc927-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="dc927-108">We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.</span><span class="sxs-lookup"><span data-stu-id="dc927-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="dc927-109">Kies wie deze verbinding kan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="dc927-109">Choose who can use this connection.</span></span> <span data-ttu-id="dc927-110">Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling.</span><span class="sxs-lookup"><span data-stu-id="dc927-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="dc927-111">Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="dc927-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="dc927-112">Voer **Accountnaam**, **Accountsleutel** **Container** voor uw Azure Data Lake Storage Gen2 in.</span><span class="sxs-lookup"><span data-stu-id="dc927-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="dc927-113">Voor informatie over het maken van een opslagaccount om te gebruiken met Azure Data Lake Storage Gen2, zie [Een opslagaccount maken](/azure/storage/blobs/create-data-lake-storage-account)​.</span><span class="sxs-lookup"><span data-stu-id="dc927-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="dc927-114">Zie [De instellingen van het opslagaccount in de Azure-portal beheren](/azure/storage/common/storage-account-manage) voor meer informatie over het vinden van de Azure Data Lake Gen 2-opslagaccountnaam en -accountsleutel.</span><span class="sxs-lookup"><span data-stu-id="dc927-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="dc927-115">Selecteer **Opslaan** om de verbinding te voltooien.</span><span class="sxs-lookup"><span data-stu-id="dc927-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="dc927-116">Een export configureren</span><span class="sxs-lookup"><span data-stu-id="dc927-116">Configure an export</span></span>

<span data-ttu-id="dc927-117">U kunt deze export configureren als u toegang hebt tot een verbinding van dit type.</span><span class="sxs-lookup"><span data-stu-id="dc927-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="dc927-118">Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="dc927-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="dc927-119">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="dc927-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="dc927-120">Selecteer **Export toevoegen** om een nieuwe export te maken.</span><span class="sxs-lookup"><span data-stu-id="dc927-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="dc927-121">Kies in het veld **Verbinding voor export** een verbinding uit de sectie **Azure Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="dc927-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="dc927-122">Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="dc927-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="dc927-123">Selecteer het vakje naast elk van de entiteiten die u naar deze bestemming wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="dc927-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="dc927-124">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="dc927-124">Select **Save**.</span></span>

<span data-ttu-id="dc927-125">Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="dc927-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="dc927-126">De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="dc927-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="dc927-127">U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="dc927-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="dc927-128">Geëxporteerde gegevens worden opgeslagen in de Azure Data Lake Gen 2-opslagcontainer die u hebt geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="dc927-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
