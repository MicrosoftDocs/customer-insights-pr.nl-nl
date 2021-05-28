---
title: Customer Insights-gegevens exporteren naar Azure Synapse Analytics
description: Meer informatie over het configureren van de verbinding met Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977371"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="e1f40-103">Gegevens exporteren naar Azure Synapse Analytics (preview)</span><span class="sxs-lookup"><span data-stu-id="e1f40-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="e1f40-104">Azure Synapse is een analyseservice waarmee de tijd tot inzicht in datawarehouses en big data-systemen wordt versneld.</span><span class="sxs-lookup"><span data-stu-id="e1f40-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="e1f40-105">U kunt uw Customer Insights-gegevens opnemen en gebruiken in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span><span class="sxs-lookup"><span data-stu-id="e1f40-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e1f40-106">Vereisten</span><span class="sxs-lookup"><span data-stu-id="e1f40-106">Prerequisites</span></span>

<span data-ttu-id="e1f40-107">Er moet aan de volgende vereisten zijn voldaan om de verbinding van Customer Insights met Azure Synapse te configureren.</span><span class="sxs-lookup"><span data-stu-id="e1f40-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="e1f40-108">Zorg ervoor dat u alle **roltoewijzingen** instelt zoals beschreven.</span><span class="sxs-lookup"><span data-stu-id="e1f40-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="e1f40-109">Vereisten in Customer Insights</span><span class="sxs-lookup"><span data-stu-id="e1f40-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="e1f40-110">U hebt de rol van **Beheerder** in doelgroepinzichten.</span><span class="sxs-lookup"><span data-stu-id="e1f40-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="e1f40-111">Meer informatie over [het instellen van gebruikersmachtigingen in doelgroepinzichten](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="e1f40-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="e1f40-112">In Azure:</span><span class="sxs-lookup"><span data-stu-id="e1f40-112">In Azure:</span></span> 

- <span data-ttu-id="e1f40-113">Een actief Azure-abonnement.</span><span class="sxs-lookup"><span data-stu-id="e1f40-113">An active Azure subscription.</span></span>

- <span data-ttu-id="e1f40-114">Als u een nieuwe Azure Data Lake Storage Gen2-account gebruikt, zijn voor de *service-principal voor doelgroepinzichten* machtigingen van **Bijdrager van opslagblobgegevens** vereist.</span><span class="sxs-lookup"><span data-stu-id="e1f40-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="e1f40-115">Meer informatie over het [maken van verbinding met een Azure Data Lake Storage Gen2-account met de service-principal van Azure voor doelgroepinzichten](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="e1f40-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="e1f40-116">Voor Data Lake Storage Gen2 **moet een** [hiërarchische naamruimte](/azure/storage/blobs/data-lake-storage-namespace) zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="e1f40-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="e1f40-117">In de resourcegroep waar de Azure Synapse-werkruimte zich bevindt, moeten aan de *service-principal* en de *gebruiker voor doelgroepinzichten* minimaal **Lezer**-machtigingen zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="e1f40-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="e1f40-118">Zie voor meer informatie [Azure-rollen toewijzen met behulp van de Azure-portal](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="e1f40-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="e1f40-119">De *gebruiker* heeft machtigingen van **Bijdrager van opslagblobgegevens** in de Azure Data Lake Storage Gen2-account nodig waar de gegevens zich bevinden en zijn gekoppeld aan de Azure Synapse-werkruimte.</span><span class="sxs-lookup"><span data-stu-id="e1f40-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="e1f40-120">Meer informatie over [het gebruik van de Azure-portal om een Azure-rol toe te wijzen voor toegang tot blob- en wachtrijgegevens](/azure/storage/common/storage-auth-aad-rbac-portal) en [machtigingen van Bijdrager van opslagblobgegevens](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="e1f40-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="e1f40-121">Voor de in de *[Azure Synapse-werkruimte beheerde identiteit](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* zijn machtigingen van **Bijdrager van opslagblobgegevens** in de Azure Data Lake Storage Gen2-account vereist waarin de gegevens zich bevinden en zijn gekoppeld aan de Azure Synapse-werkruimte.</span><span class="sxs-lookup"><span data-stu-id="e1f40-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="e1f40-122">Meer informatie over [het gebruik van de Azure-portal om een Azure-rol toe te wijzen voor toegang tot blob- en wachtrijgegevens](/azure/storage/common/storage-auth-aad-rbac-portal) en [machtigingen van Bijdrager van opslagblobgegevens](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="e1f40-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="e1f40-123">In de Azure Synapse-werkruimte moet voor de *service-principal voor doelgroepinzichten* de rol **Synapse-beheerder** zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="e1f40-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="e1f40-124">Zie voor meer informatie [Toegangsbeheer instellen voor uw Synapse-werkruimte](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="e1f40-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="e1f40-125">De verbinding instellen en exporteren naar Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="e1f40-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="e1f40-126">Een verbinding configureren</span><span class="sxs-lookup"><span data-stu-id="e1f40-126">Configure a connection</span></span>

1. <span data-ttu-id="e1f40-127">Ga naar **Beheerder** > **Verbindingen**.</span><span class="sxs-lookup"><span data-stu-id="e1f40-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e1f40-128">Selecteer **Verbinding toevoegen** en kies **Azure Synapse Analytics** of selecteer **Instellen** op de tegel **Azure Synapse Analytics** om de verbinding te configureren.</span><span class="sxs-lookup"><span data-stu-id="e1f40-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="e1f40-129">Geef uw verbinding een herkenbare naam in het veld Weergavenaam.</span><span class="sxs-lookup"><span data-stu-id="e1f40-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="e1f40-130">De naam en het type verbinding beschrijven deze verbinding.</span><span class="sxs-lookup"><span data-stu-id="e1f40-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="e1f40-131">We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.</span><span class="sxs-lookup"><span data-stu-id="e1f40-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e1f40-132">Kies wie deze verbinding kan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e1f40-132">Choose who can use this connection.</span></span> <span data-ttu-id="e1f40-133">Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling.</span><span class="sxs-lookup"><span data-stu-id="e1f40-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e1f40-134">Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e1f40-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e1f40-135">Selecteer of zoek naar het abonnement waarin u de Customer Insights-gegevens wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e1f40-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="e1f40-136">Zodra een abonnement is geselecteerd, kunt u ook **Werkruimte**, **Opslagaccount** en **Container** selecteren.</span><span class="sxs-lookup"><span data-stu-id="e1f40-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="e1f40-137">Selecteer **Opslaan** om de verbinding op te slaan.</span><span class="sxs-lookup"><span data-stu-id="e1f40-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="e1f40-138">Een export configureren</span><span class="sxs-lookup"><span data-stu-id="e1f40-138">Configure an export</span></span>

<span data-ttu-id="e1f40-139">U kunt deze export configureren als u toegang hebt tot een verbinding van dit type.</span><span class="sxs-lookup"><span data-stu-id="e1f40-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e1f40-140">Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e1f40-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e1f40-141">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="e1f40-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e1f40-142">Selecteer **Export toevoegen** om een nieuwe export te maken.</span><span class="sxs-lookup"><span data-stu-id="e1f40-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="e1f40-143">Kies in het veld **Verbinding voor export** een verbinding uit de sectie **Azure Synapse Analytics**.</span><span class="sxs-lookup"><span data-stu-id="e1f40-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="e1f40-144">Als u deze sectienaam niet ziet, zijn er geen [verbindingen](connections.md) van dit type voor u beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="e1f40-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="e1f40-145">Zorg voor een herkenbare **weergavenaam** voor uw export en een **databasenaam**.</span><span class="sxs-lookup"><span data-stu-id="e1f40-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="e1f40-146">Geef aan welke entiteiten u wilt exporteren naar Azure Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="e1f40-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="e1f40-147">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="e1f40-147">Select **Save**.</span></span>

<span data-ttu-id="e1f40-148">Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="e1f40-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e1f40-149">De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e1f40-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e1f40-150">U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e1f40-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="e1f40-151">Een export bijwerken</span><span class="sxs-lookup"><span data-stu-id="e1f40-151">Update an export</span></span>

1. <span data-ttu-id="e1f40-152">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="e1f40-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e1f40-153">Selecteer **Bewerken** in de export die u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="e1f40-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="e1f40-154">Kies **Toevoegen** of **Verwijderen** om entiteiten toe te voegen aan of te verwijderen uit de selectie.</span><span class="sxs-lookup"><span data-stu-id="e1f40-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="e1f40-155">Als entiteiten uit de selectie worden verwijderd, worden ze niet verwijderd uit de Synapse Analytics-database.</span><span class="sxs-lookup"><span data-stu-id="e1f40-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="e1f40-156">Bij toekomstige gegevensvernieuwingen worden de verwijderde entiteiten in die database echter niet bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="e1f40-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="e1f40-157">Met **De databasenaam wijzigen** wordt een nieuwe Synapse Analytics-database gemaakt.</span><span class="sxs-lookup"><span data-stu-id="e1f40-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="e1f40-158">De database met de naam die eerder is geconfigureerd, ontvangt bij toekomstige vernieuwingen geen updates.</span><span class="sxs-lookup"><span data-stu-id="e1f40-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
