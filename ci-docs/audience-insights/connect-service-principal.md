---
title: Verbinding maken met een Azure Data Lake Storage Gen2-account met een Service Principal
description: Gebruik een Azure Service-principal voor doelgroepinzichten om verbinding te maken met uw eigen data lake wanneer u deze koppelt aan doelgroepinzichten.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eebbac1370a847869d98beaf70db49b809d762e7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267716"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="1e720-103">Verbinding maken met een Azure Data Lake Storage Gen2-account met een Azure Service Principal voor doelgroepinzichten</span><span class="sxs-lookup"><span data-stu-id="1e720-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="1e720-104">Geautomatiseerde hulpmiddelen die Azure-services gebruiken, moeten altijd beperkte machtigingen hebben.</span><span class="sxs-lookup"><span data-stu-id="1e720-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="1e720-105">In plaats van toepassingen zich te laten aanmelden als een gebruiker met volledige rechten, biedt Azure Service Principals.</span><span class="sxs-lookup"><span data-stu-id="1e720-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="1e720-106">Lees verder om te zien hoe u doelgroepinzichten kunt verbinden met een Azure Data Lake Storage Gen2-account met behulp van een Azure Service Principal in plaats van opslagaccountsleutels.</span><span class="sxs-lookup"><span data-stu-id="1e720-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="1e720-107">U kunt de Service Principal gebruiken om veilig [een Common Data Model-map toe te voegen of te bewerken als een gegevensbron](connect-common-data-model.md) of [een nieuwe omgeving te maken of een bestaande te bewerken](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="1e720-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="1e720-108">Voor het Azure Data Lake Gen2-opslagaccount dat de service-principal wil gebruiken, moet [Hierarchical Name Space (HNS) ingeschakeld zijn](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace)​.</span><span class="sxs-lookup"><span data-stu-id="1e720-108">The Azure Data Lake Gen2 storage account that intends to use the service principal must have [Hierarchical Name Space (HNS) enabled](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).</span></span>
> - <span data-ttu-id="1e720-109">U hebt beheerdersmachtigingen nodig om uw Azure-abonnement de Service Principal te laten maken.</span><span class="sxs-lookup"><span data-stu-id="1e720-109">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="1e720-110">Een Azure Service Principal voor doelgroepinzichten maken</span><span class="sxs-lookup"><span data-stu-id="1e720-110">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="1e720-111">Voordat u een nieuwe Service Principal voor doelgroepinzichten maakt, controleert u of deze al bestaat in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="1e720-111">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="1e720-112">Een bestaande Service Principal zoeken</span><span class="sxs-lookup"><span data-stu-id="1e720-112">Look for an existing service principal</span></span>

1. <span data-ttu-id="1e720-113">Ga naar de [Azure-beheerportal](https://portal.azure.com) en meld u aan bij uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="1e720-113">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="1e720-114">Selecteer **Azure Active Directory** bij de Azure-services.</span><span class="sxs-lookup"><span data-stu-id="1e720-114">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="1e720-115">Selecteer onder **Beheer** de optie **Ondernemingstoepassingen**.</span><span class="sxs-lookup"><span data-stu-id="1e720-115">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="1e720-116">Zoek de toepassings-id van doelgroepinzichten `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` of de naam `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="1e720-116">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="1e720-117">Als u een overeenkomend record vindt, betekent dit dat de service principal voor doelgroepinzichten bestaat.</span><span class="sxs-lookup"><span data-stu-id="1e720-117">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="1e720-118">U hoeft deze niet opnieuw te maken.</span><span class="sxs-lookup"><span data-stu-id="1e720-118">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Schermafbeelding met de bestaande service principal.":::
   
6. <span data-ttu-id="1e720-120">Als er geen resultaten worden geretourneerd, maakt u een nieuwe service principal.</span><span class="sxs-lookup"><span data-stu-id="1e720-120">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="1e720-121">Een nieuwe service principal maken</span><span class="sxs-lookup"><span data-stu-id="1e720-121">Create a new service principal</span></span>

1. <span data-ttu-id="1e720-122">Installeer de nieuwste versie van **Azure Active Directory PowerShell voor Graph**.</span><span class="sxs-lookup"><span data-stu-id="1e720-122">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="1e720-123">Zie [Microsoft Azure Active Directory PowerShell voor Graph installeren](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1e720-123">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="1e720-124">Selecteer op uw pc de Windows-toets op het toetsenbord en zoek **Windows PowerShell** en **Uitvoeren als beheerder**.</span><span class="sxs-lookup"><span data-stu-id="1e720-124">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="1e720-125">Voer `Install-Module AzureAD` in het PowerShell-venster dat wordt geopend in.</span><span class="sxs-lookup"><span data-stu-id="1e720-125">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="1e720-126">Maak de service principal voor doelgroepinzichten met de Azure AD PowerShell-module.</span><span class="sxs-lookup"><span data-stu-id="1e720-126">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="1e720-127">Voer `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure` in het PowerShell-venster in.</span><span class="sxs-lookup"><span data-stu-id="1e720-127">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="1e720-128">Vervang 'uw tenant-id' door de werkelijke id van uw tenant waar u de service principal wilt maken.</span><span class="sxs-lookup"><span data-stu-id="1e720-128">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="1e720-129">De omgevingsnaamparameter `AzureEnvironmentName` is optioneel.</span><span class="sxs-lookup"><span data-stu-id="1e720-129">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="1e720-130">Voer `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"` in.</span><span class="sxs-lookup"><span data-stu-id="1e720-130">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="1e720-131">Met deze opdracht wordt de service principal gemaakt voor doelgroepinzichten voor de geselecteerde tenant.</span><span class="sxs-lookup"><span data-stu-id="1e720-131">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="1e720-132">Machtigingen verlenen aan de service principal om toegang te krijgen tot het opslagaccount</span><span class="sxs-lookup"><span data-stu-id="1e720-132">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="1e720-133">Ga naar de Azure Portal om machtigingen te verlenen aan de service principal voor het opslagaccount dat u wilt gebruiken in doelgroepinzichten.</span><span class="sxs-lookup"><span data-stu-id="1e720-133">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="1e720-134">Ga naar de [Azure-beheerportal](https://portal.azure.com) en meld u aan bij uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="1e720-134">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="1e720-135">Open het opslagaccount waartoe u de service principal voor doelgroepinzichten toegang wilt geven.</span><span class="sxs-lookup"><span data-stu-id="1e720-135">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="1e720-136">Selecteer **Toegangscontrole (IAM)** in het navigatiedeelvenster en selecteer **Toevoegen** > **Roltoewijzing toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="1e720-136">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Schermafbeelding met Azure Portal tijdens het toevoegen van een roltoewijzing.":::
   
1. <span data-ttu-id="1e720-138">Stel in het deelvenster **Roltoewijzing toevoegen** de volgende eigenschappen in:</span><span class="sxs-lookup"><span data-stu-id="1e720-138">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="1e720-139">Rol: *Inzender van opslagblob-gegevens*</span><span class="sxs-lookup"><span data-stu-id="1e720-139">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="1e720-140">Wijs toegang toe aan: *Gebruiker, groep of service principal*</span><span class="sxs-lookup"><span data-stu-id="1e720-140">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="1e720-141">Selecteer: *Dynamics 365 AI voor Customer Insights* (de [service principal die u hebt gemaakt](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="1e720-141">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="1e720-142">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1e720-142">Select **Save**.</span></span>

<span data-ttu-id="1e720-143">Het kan tot 15 minuten duren om de wijzigingen door te geven.</span><span class="sxs-lookup"><span data-stu-id="1e720-143">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="1e720-144">Voer de Azure-resource-id of de Azure-abonnementsgegevens in de opslagaccountbijlage bij doelgroepinzichten in.</span><span class="sxs-lookup"><span data-stu-id="1e720-144">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="1e720-145">Koppel een Azure Data Lake-opslagaccount in doelgroepinzichten aan [opslaguitvoergegevens](manage-environments.md) of [gebruik het als een gegevensbron](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="1e720-145">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="1e720-146">Als u de optie Azure Data Lake kiest, kunt u kiezen tussen de resource- of de abonnementenbenadering.</span><span class="sxs-lookup"><span data-stu-id="1e720-146">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="1e720-147">Volg de onderstaande stappen om de vereiste informatie over de geselecteerde benadering te verstrekken.</span><span class="sxs-lookup"><span data-stu-id="1e720-147">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resource-based-storage-account-connection"></a><span data-ttu-id="1e720-148">Verbinding voor resource-opslagaccount</span><span class="sxs-lookup"><span data-stu-id="1e720-148">Resource-based storage account connection</span></span>

1. <span data-ttu-id="1e720-149">Ga naar de [Azure-beheerportal](https://portal.azure.com), meld u aan bij uw abonnement en open het opslagaccount.</span><span class="sxs-lookup"><span data-stu-id="1e720-149">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="1e720-150">Ga naar **Instellingen** > **Eigenschappen** in het navigatiedeelvenster.</span><span class="sxs-lookup"><span data-stu-id="1e720-150">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="1e720-151">Kopieer de waarde voor de resource-id van het opslagaccount.</span><span class="sxs-lookup"><span data-stu-id="1e720-151">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopieer de resource-id van het opslagaccount.":::

1. <span data-ttu-id="1e720-153">Voeg in doelgroepinzichten de resource-id in het resourceveld in dat wordt weergegeven in het opslagaccountverbindingsscherm.</span><span class="sxs-lookup"><span data-stu-id="1e720-153">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Voer de informatie voor de resource-id van het opslagaccount in.":::   
   
1. <span data-ttu-id="1e720-155">Ga door met de resterende stappen in doelgroepinzichten om het opslagaccount te koppelen.</span><span class="sxs-lookup"><span data-stu-id="1e720-155">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="1e720-156">Verbinding voor abonnement-opslagaccount</span><span class="sxs-lookup"><span data-stu-id="1e720-156">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="1e720-157">Ga naar de [Azure-beheerportal](https://portal.azure.com), meld u aan bij uw abonnement en open het opslagaccount.</span><span class="sxs-lookup"><span data-stu-id="1e720-157">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="1e720-158">Ga naar **Instellingen** > **Eigenschappen** in het navigatiedeelvenster.</span><span class="sxs-lookup"><span data-stu-id="1e720-158">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="1e720-159">Controleer of bij **Abonnement**, **Resourcegroep** en **Naam** van het opslagaccount de juiste waarden zijn geselecteerd in doelgroepinzichten.</span><span class="sxs-lookup"><span data-stu-id="1e720-159">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="1e720-160">Kies in doelgroepinzichten de waarden of de overeenkomstige velden wanneer u het opslagaccount koppelt.</span><span class="sxs-lookup"><span data-stu-id="1e720-160">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>
   
1. <span data-ttu-id="1e720-161">Ga door met de resterende stappen in doelgroepinzichten om het opslagaccount te koppelen.</span><span class="sxs-lookup"><span data-stu-id="1e720-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]