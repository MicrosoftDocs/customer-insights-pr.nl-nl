---
title: Verbinding maken met een Azure Data Lake Storage Gen2-account met een Service Principal
description: Gebruik een Azure Service Principal voor doelgroepinzichten om verbinding te maken met uw eigen data lake wanneer u deze koppelt aan doelgroepinzichten.
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644082"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="575e9-103">Verbinding maken met een Azure Data Lake Storage Gen2-account met een Azure Service Principal voor doelgroepinzichten</span><span class="sxs-lookup"><span data-stu-id="575e9-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="575e9-104">Geautomatiseerde hulpmiddelen die Azure-services gebruiken, moeten altijd beperkte machtigingen hebben.</span><span class="sxs-lookup"><span data-stu-id="575e9-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="575e9-105">In plaats van toepassingen zich te laten aanmelden als een gebruiker met volledige rechten, biedt Azure Service Principals.</span><span class="sxs-lookup"><span data-stu-id="575e9-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="575e9-106">Lees verder om te zien hoe u doelgroepinzichten kunt verbinden met een Azure Data Lake Storage Gen2-account met behulp van een Azure Service Principal in plaats van opslagaccountsleutels.</span><span class="sxs-lookup"><span data-stu-id="575e9-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="575e9-107">U kunt de Service Principal gebruiken om veilig [een Common Data Model-map toe te voegen of te bewerken als een gegevensbron](connect-common-data-model.md) of [een nieuwe omgeving te maken of een bestaande te bewerken](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="575e9-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

<span data-ttu-id="575e9-108">U hebt beheerdersmachtigingen nodig om uw Azure-abonnement de Service Principal te laten maken.</span><span class="sxs-lookup"><span data-stu-id="575e9-108">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="575e9-109">Een Azure Service Principal voor doelgroepinzichten maken</span><span class="sxs-lookup"><span data-stu-id="575e9-109">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="575e9-110">Voordat u een nieuwe Service Principal voor doelgroepinzichten maakt, controleert u of deze al bestaat in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="575e9-110">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="575e9-111">Een bestaande Service Principal zoeken</span><span class="sxs-lookup"><span data-stu-id="575e9-111">Look for an existing service principal</span></span>

1. <span data-ttu-id="575e9-112">Ga naar de [Azure-beheerportal](https://portal.azure.com) en meld u aan bij uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="575e9-112">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="575e9-113">Selecteer **Azure Active Directory** bij de Azure-services.</span><span class="sxs-lookup"><span data-stu-id="575e9-113">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="575e9-114">Selecteer onder **Beheer** de optie **Ondernemingstoepassingen**.</span><span class="sxs-lookup"><span data-stu-id="575e9-114">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="575e9-115">Zoek de toepassings-id van doelgroepinzichten `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` of de naam `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="575e9-115">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="575e9-116">Als u een overeenkomend record vindt, betekent dit dat de service principal voor doelgroepinzichten bestaat.</span><span class="sxs-lookup"><span data-stu-id="575e9-116">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="575e9-117">U hoeft deze niet opnieuw te maken.</span><span class="sxs-lookup"><span data-stu-id="575e9-117">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Schermafbeelding met de bestaande service principal.":::
   
6. <span data-ttu-id="575e9-119">Als er geen resultaten worden geretourneerd, maakt u een nieuwe service principal.</span><span class="sxs-lookup"><span data-stu-id="575e9-119">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="575e9-120">Een nieuwe service principal maken</span><span class="sxs-lookup"><span data-stu-id="575e9-120">Create a new service principal</span></span>

1. <span data-ttu-id="575e9-121">Installeer de nieuwste versie van **Azure Active Directory PowerShell voor Graph**.</span><span class="sxs-lookup"><span data-stu-id="575e9-121">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="575e9-122">Zie [Microsoft Azure Active Directory PowerShell voor Graph installeren](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="575e9-122">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="575e9-123">Selecteer op uw pc de Windows-toets op het toetsenbord en zoek **Windows PowerShell** en **Uitvoeren als beheerder**.</span><span class="sxs-lookup"><span data-stu-id="575e9-123">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="575e9-124">Voer `Install-Module AzureAD` in het PowerShell-venster dat wordt geopend in.</span><span class="sxs-lookup"><span data-stu-id="575e9-124">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="575e9-125">Maak de service principal voor doelgroepinzichten met de Azure AD PowerShell-module.</span><span class="sxs-lookup"><span data-stu-id="575e9-125">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="575e9-126">Voer `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure` in het PowerShell-venster in.</span><span class="sxs-lookup"><span data-stu-id="575e9-126">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="575e9-127">Vervang 'uw tenant-id' door de werkelijke id van uw tenant waar u de service principal wilt maken.</span><span class="sxs-lookup"><span data-stu-id="575e9-127">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="575e9-128">De omgevingsnaamparameter `AzureEnvironmentName` is optioneel.</span><span class="sxs-lookup"><span data-stu-id="575e9-128">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="575e9-129">Voer `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"` in.</span><span class="sxs-lookup"><span data-stu-id="575e9-129">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="575e9-130">Met deze opdracht wordt de service principal gemaakt voor doelgroepinzichten voor de geselecteerde tenant.</span><span class="sxs-lookup"><span data-stu-id="575e9-130">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="575e9-131">Machtigingen verlenen aan de service principal om toegang te krijgen tot het opslagaccount</span><span class="sxs-lookup"><span data-stu-id="575e9-131">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="575e9-132">Ga naar de Azure Portal om machtigingen te verlenen aan de service principal voor het opslagaccount dat u wilt gebruiken in doelgroepinzichten.</span><span class="sxs-lookup"><span data-stu-id="575e9-132">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="575e9-133">Ga naar de [Azure-beheerportal](https://portal.azure.com) en meld u aan bij uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="575e9-133">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="575e9-134">Open het opslagaccount waartoe u de service principal voor doelgroepinzichten toegang wilt geven.</span><span class="sxs-lookup"><span data-stu-id="575e9-134">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="575e9-135">Selecteer **Toegangscontrole (IAM)** in het navigatiedeelvenster en selecteer **Toevoegen** > **Roltoewijzing toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="575e9-135">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Schermafbeelding met Azure Portal tijdens het toevoegen van een roltoewijzing.":::
   
1. <span data-ttu-id="575e9-137">Stel in het deelvenster **Roltoewijzing toevoegen** de volgende eigenschappen in:</span><span class="sxs-lookup"><span data-stu-id="575e9-137">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="575e9-138">Rol: *Inzender van opslagblob-gegevens*</span><span class="sxs-lookup"><span data-stu-id="575e9-138">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="575e9-139">Wijs toegang toe aan: *Gebruiker, groep of service principal*</span><span class="sxs-lookup"><span data-stu-id="575e9-139">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="575e9-140">Selecteer: *Dynamics 365 AI voor Customer Insights* (de [service principal die u hebt gemaakt](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="575e9-140">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="575e9-141">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="575e9-141">Select **Save**.</span></span>

<span data-ttu-id="575e9-142">Het kan tot 15 minuten duren om de wijzigingen door te geven.</span><span class="sxs-lookup"><span data-stu-id="575e9-142">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="575e9-143">Voer de Azure-resource-id of de Azure-abonnementsgegevens in de opslagaccountbijlage bij doelgroepinzichten in.</span><span class="sxs-lookup"><span data-stu-id="575e9-143">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="575e9-144">Koppel een Azure Data Lake-opslagaccount in doelgroepinzichten aan [opslaguitvoergegevens](manage-environments.md) of [gebruik het als een gegevensbron](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="575e9-144">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="575e9-145">Als u de optie Azure Data Lake kiest, kunt u kiezen tussen de resource- of de abonnementenbenadering.</span><span class="sxs-lookup"><span data-stu-id="575e9-145">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="575e9-146">Volg de onderstaande stappen om de vereiste informatie over de geselecteerde benadering te verstrekken.</span><span class="sxs-lookup"><span data-stu-id="575e9-146">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resounce-based-storage-account-connection"></a><span data-ttu-id="575e9-147">Verbinding voor resource-opslagaccount</span><span class="sxs-lookup"><span data-stu-id="575e9-147">Resounce-based storage account connection</span></span>

1. <span data-ttu-id="575e9-148">Ga naar de [Azure-beheerportal](https://portal.azure.com), meld u aan bij uw abonnement en open het opslagaccount.</span><span class="sxs-lookup"><span data-stu-id="575e9-148">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="575e9-149">Ga naar **Instellingen** > **Eigenschappen** in het navigatiedeelvenster.</span><span class="sxs-lookup"><span data-stu-id="575e9-149">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="575e9-150">Kopieer de waarde voor de resource-id van het opslagaccount.</span><span class="sxs-lookup"><span data-stu-id="575e9-150">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopieer de resource-id van het opslagaccount.":::

1. <span data-ttu-id="575e9-152">Voeg in doelgroepinzichten de resource-id in het resourceveld in dat wordt weergegeven in het opslagaccountverbindingsscherm.</span><span class="sxs-lookup"><span data-stu-id="575e9-152">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Voer de informatie voor de resource-id van het opslagaccount in.":::   
   
1. <span data-ttu-id="575e9-154">Ga door met de resterende stappen in doelgroepinzichten om het opslagaccount te koppelen.</span><span class="sxs-lookup"><span data-stu-id="575e9-154">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="575e9-155">Verbinding voor abonnement-opslagaccount</span><span class="sxs-lookup"><span data-stu-id="575e9-155">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="575e9-156">Ga naar de [Azure-beheerportal](https://portal.azure.com), meld u aan bij uw abonnement en open het opslagaccount.</span><span class="sxs-lookup"><span data-stu-id="575e9-156">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="575e9-157">Ga naar **Instellingen** > **Eigenschappen** in het navigatiedeelvenster.</span><span class="sxs-lookup"><span data-stu-id="575e9-157">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="575e9-158">Controleer of bij **Abonnement**, **Resourcegroep** en **Naam** van het opslagaccount de juiste waarden zijn geselecteerd in doelgroepinzichten.</span><span class="sxs-lookup"><span data-stu-id="575e9-158">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="575e9-159">Kies in doelgroepinzichten de waarden of de overeenkomstige velden wanneer u het opslagaccount koppelt.</span><span class="sxs-lookup"><span data-stu-id="575e9-159">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="Voer de informatie voor de resource-id van het opslagaccount in.":::
   
1. <span data-ttu-id="575e9-161">Ga door met de resterende stappen in doelgroepinzichten om het opslagaccount te koppelen.</span><span class="sxs-lookup"><span data-stu-id="575e9-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>
