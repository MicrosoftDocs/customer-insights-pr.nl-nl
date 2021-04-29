---
title: Customer Insights-gegevens naar een Azure Blob Storage exporteren
description: Leer hoe u de verbinding configureert en exporteert naar Blob-opslag.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 294feff2f77c3756fbadb36c90aab430454f5967
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760183"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="c358e-103">Segmentlijst en andere gegevens exporteren naar Azure Blob Storage (preview)</span><span class="sxs-lookup"><span data-stu-id="c358e-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="c358e-104">Sla uw Customer Insights-gegevens op in een Blob-opslag of gebruik deze om uw gegevens over te brengen naar andere toepassingen.</span><span class="sxs-lookup"><span data-stu-id="c358e-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="c358e-105">De verbinding instellen met Blob-opslag</span><span class="sxs-lookup"><span data-stu-id="c358e-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="c358e-106">Ga naar **Beheerder** > **Verbindingen**.</span><span class="sxs-lookup"><span data-stu-id="c358e-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="c358e-107">Selecteer **Verbinding toevoegen** en kies **Azure Blob Storage** om de verbinding te configureren.</span><span class="sxs-lookup"><span data-stu-id="c358e-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="c358e-108">Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="c358e-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="c358e-109">De naam en het type verbinding beschrijven deze verbinding.</span><span class="sxs-lookup"><span data-stu-id="c358e-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="c358e-110">We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.</span><span class="sxs-lookup"><span data-stu-id="c358e-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="c358e-111">Kies wie deze verbinding kan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="c358e-111">Choose who can use this connection.</span></span> <span data-ttu-id="c358e-112">Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling.</span><span class="sxs-lookup"><span data-stu-id="c358e-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="c358e-113">Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c358e-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="c358e-114">Voer **Gebruikersnaam**, **Accountsleutel** en **Container** in voor uw Blob-opslagaccount.</span><span class="sxs-lookup"><span data-stu-id="c358e-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="c358e-115">Zie [De instellingen van het opslagaccount in de Azure Portal beheren](/azure/storage/common/storage-account-manage) voor meer informatie over het vinden van de Blob-opslagaccountnaam en -accountsleutel.</span><span class="sxs-lookup"><span data-stu-id="c358e-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="c358e-116">Zie voor meer informatie over het maken van een container [Een container maken](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="c358e-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="c358e-117">Selecteer **Opslaan** om de verbinding te voltooien.</span><span class="sxs-lookup"><span data-stu-id="c358e-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="c358e-118">Een export configureren</span><span class="sxs-lookup"><span data-stu-id="c358e-118">Configure an export</span></span>

<span data-ttu-id="c358e-119">U kunt deze export configureren als u toegang hebt tot een verbinding van dit type.</span><span class="sxs-lookup"><span data-stu-id="c358e-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="c358e-120">Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c358e-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c358e-121">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="c358e-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c358e-122">Selecteer **Bestemming toevoegen** om een nieuwe export te maken.</span><span class="sxs-lookup"><span data-stu-id="c358e-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="c358e-123">Kies in het veld **Verbinding voor export** een verbinding uit de sectie Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="c358e-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="c358e-124">Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="c358e-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="c358e-125">Selecteer het vakje naast elk van de entiteiten die u naar deze bestemming wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="c358e-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="c358e-126">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="c358e-126">Select **Save**.</span></span>

<span data-ttu-id="c358e-127">Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="c358e-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="c358e-128">De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c358e-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="c358e-129">U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="c358e-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="c358e-130">Geëxporteerde gegevens worden opgeslagen in de Blob-opslagcontainer die u hebt geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="c358e-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="c358e-131">De volgende mappaden worden automatisch in uw container gemaakt:</span><span class="sxs-lookup"><span data-stu-id="c358e-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="c358e-132">Voor bronentiteiten en entiteiten die door het systeem zijn gegenereerd: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="c358e-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="c358e-133">Voorbeeld: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="c358e-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="c358e-134">Het model.json voor de geëxporteerde entiteiten bevindt zich op het %ExportDestinationName%-niveau</span><span class="sxs-lookup"><span data-stu-id="c358e-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="c358e-135">Voorbeeld: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="c358e-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
