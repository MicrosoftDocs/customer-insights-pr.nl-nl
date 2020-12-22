---
title: Werken met API's
description: API's gebruiken en beperkingen begrijpen.
ms.date: 12/04/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a03e916676800afdd8692da865a1060952d5c4f
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689124"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="f1dea-103">Werken met Customer Insights-API's</span><span class="sxs-lookup"><span data-stu-id="f1dea-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="f1dea-104">Dynamics 365 Customer Insights biedt API's om uw eigen toepassingen te bouwen op basis van uw gegevens in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f1dea-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f1dea-105">Details van deze API's staan vermeld in de [Referentie voor Customer Insights-API's](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="f1dea-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="f1dea-106">Ze bevatten aanvullende informatie over bewerkingen, parameters en reacties.</span><span class="sxs-lookup"><span data-stu-id="f1dea-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="f1dea-107">In dit artikel leest u hoe u toegang krijgt tot de Customer Insights-API's, een Azure App-registratie maakt en hoe u aan de slag kunt met de beschikbare clientbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="f1dea-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="f1dea-108">De Customer Insights-API's uitproberen</span><span class="sxs-lookup"><span data-stu-id="f1dea-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="f1dea-109">[Meld u aan](https://home.ci.ai.dynamics.com) bij Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f1dea-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="f1dea-110">Als u nog geen abonnement hebt, [meld u dan aan voor een proefversie van Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="f1dea-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="f1dea-111">Ga naar **Beheer** > **Machtigingen** om API's in uw Customer Insights-omgeving in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="f1dea-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="f1dea-112">Hiervoor hebt u beheerdersmachtigingen nodig.</span><span class="sxs-lookup"><span data-stu-id="f1dea-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="f1dea-113">Ga naar het tabblad **API's** en selecteer de knop **Inschakelen**.</span><span class="sxs-lookup"><span data-stu-id="f1dea-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="f1dea-114">Als u de API's inschakelt, wordt een primaire en secundaire abonnementssleutel voor uw exemplaar gemaakt die wordt gebruikt in de API-aanvragen.</span><span class="sxs-lookup"><span data-stu-id="f1dea-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="f1dea-115">U kunt de sleutels opnieuw genereren door **Primaire opnieuw genereren** of **Secundaire opnieuw genereren** te selecteren op **Beheer** > **Machtigingen** > **API's**.</span><span class="sxs-lookup"><span data-stu-id="f1dea-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Customer Insights-API's inschakelen":::

1. <span data-ttu-id="f1dea-117">Selecteer **Onze API's verkennen** om de API's uit te proberen.</span><span class="sxs-lookup"><span data-stu-id="f1dea-117">Select **Explore our APIs** to try out the APIs.</span></span>

1. <span data-ttu-id="f1dea-118">Kies een API-bewerking en selecteer **Probeer het uit**.</span><span class="sxs-lookup"><span data-stu-id="f1dea-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="f1dea-119">Stel in het deelvenster aan de zijkant de waarde in het vervolgkeuzemenu **Autorisatie** in op **impliciet**.</span><span class="sxs-lookup"><span data-stu-id="f1dea-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="f1dea-120">Aan de koptekst `Authorization` wordt een bearer-token toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="f1dea-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="f1dea-121">Uw abonnementssleutel wordt automatisch ingevuld.</span><span class="sxs-lookup"><span data-stu-id="f1dea-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="f1dea-122">Voeg eventueel alle benodigde queryparameters toe.</span><span class="sxs-lookup"><span data-stu-id="f1dea-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="f1dea-123">Scrol naar de onderkant van het deelvenster aan de zijkant en selecteer **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="f1dea-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="f1dea-124">De HTTP-respons wordt snel hieronder weergegeven.</span><span class="sxs-lookup"><span data-stu-id="f1dea-124">The HTTP response will soon appear below.</span></span>

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="f1dea-125">Een nieuwe app-registratie in Azure Portal maken</span><span class="sxs-lookup"><span data-stu-id="f1dea-125">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="f1dea-126">Met deze stappen kunt u aan de slag met de Customer Insights-API's in een Azure-toepassing met gedelegeerde machtigingen.</span><span class="sxs-lookup"><span data-stu-id="f1dea-126">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="f1dea-127">Lees eerst de [sectie Aan de slag](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="f1dea-127">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="f1dea-128">Meld u aan op de [Azure-portal](https://portal.azure.com) met het account dat toegang heeft tot de Customer Insights-gegevens.</span><span class="sxs-lookup"><span data-stu-id="f1dea-128">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="f1dea-129">Selecteer aan de linkerkant **App-registraties**.</span><span class="sxs-lookup"><span data-stu-id="f1dea-129">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="f1dea-130">Selecteer **Nieuwe registratie**, geef een toepassingsnaam op en kies het accounttype.</span><span class="sxs-lookup"><span data-stu-id="f1dea-130">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="f1dea-131">Voeg eventueel een omleidings-URL toe.</span><span class="sxs-lookup"><span data-stu-id="f1dea-131">Optionally, add a redirect URL.</span></span> <span data-ttu-id="f1dea-132">http://localhost is voldoende om een toepassing op uw lokale computer te ontwikkelen.</span><span class="sxs-lookup"><span data-stu-id="f1dea-132">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="f1dea-133">Ga bij uw nieuwe app-registratie naar **API-machtigingen**.</span><span class="sxs-lookup"><span data-stu-id="f1dea-133">On your new App registration, go to **API permissions**.</span></span>

1. <span data-ttu-id="f1dea-134">Selecteer **Een machtiging toevoegen** en selecteer **Customer Insights** in het deelvenster aan de zijkant.</span><span class="sxs-lookup"><span data-stu-id="f1dea-134">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="f1dea-135">Selecteer voor **Machtigingstype** de optie **Gedelegeerde machtigingen** en selecteer de machtiging **gebruikersimitatie**.</span><span class="sxs-lookup"><span data-stu-id="f1dea-135">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="f1dea-136">Selecteer **Machtigingen toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="f1dea-136">Select **Add permissions**.</span></span> <span data-ttu-id="f1dea-137">Als u toegang tot de API nodig hebt zonder dat een gebruiker zich aanmeldt, leest u de sectie [Machtigingen voor server-naar-server-toepassingen](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="f1dea-137">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="f1dea-138">Selecteer **Beheerders toestemming verlenen voor...** om de app-registratie te voltooien.</span><span class="sxs-lookup"><span data-stu-id="f1dea-138">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="f1dea-139">U kunt de toepassings-/client-id voor deze app-registratie gebruiken bij de Microsoft Authentication Library (MSAL) om een bearer-token te verkrijgen om met uw verzoek naar de API te verzenden.</span><span class="sxs-lookup"><span data-stu-id="f1dea-139">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

<span data-ttu-id="f1dea-140">Zie voor meer informatie over MSAL [Overzicht van Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="f1dea-140">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="f1dea-141">Zie voor meer informatie over app-registratie in Azure [De nieuwe registratie-ervaring van de Azure Portal-app](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span><span class="sxs-lookup"><span data-stu-id="f1dea-141">For more information about app registration in Azure, see [The new Azure portal app registration experience](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="f1dea-142">Zie voor informatie over het gebruik van de API's van onze clientbibliotheken [Customer Insights-clientbibliotheken](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="f1dea-142">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="f1dea-143">Machtigingen voor server-naar-server-toepassingen</span><span class="sxs-lookup"><span data-stu-id="f1dea-143">Server-to-server application permissions</span></span>

<span data-ttu-id="f1dea-144">In de [sectie app-registratie](#create-a-new-app-registration-in-the-azure-portal) wordt beschreven hoe u een app registreert waarvoor een gebruiker zich moet aanmelden voor verificatie.</span><span class="sxs-lookup"><span data-stu-id="f1dea-144">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="f1dea-145">Ontdek hoe u een app-registratie maakt die geen gebruikersinteractie vereist en die op een server kan worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="f1dea-145">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="f1dea-146">Ga bij uw app-registratie in de Azure-portal naar **API-machtigingen**.</span><span class="sxs-lookup"><span data-stu-id="f1dea-146">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="f1dea-147">Selecteer **Een machtiging toevoegen** en selecteer **Customer Insights** in het deelvenster aan de zijkant.</span><span class="sxs-lookup"><span data-stu-id="f1dea-147">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="f1dea-148">Selecteer voor **Machtigingstype** de optie **Toepassingsmachtigingen** en selecteer de machtiging **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="f1dea-148">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="f1dea-149">Selecteer **Machtigingen toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="f1dea-149">Select **Add permissions**.</span></span>

1. <span data-ttu-id="f1dea-150">Om beheerderstoestemming te geven voor deze toepassing, moet u een Service Principal toevoegen.</span><span class="sxs-lookup"><span data-stu-id="f1dea-150">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="f1dea-151">Installeer de Azure Active Directory (AD) PowerShell-module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="f1dea-151">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="f1dea-152">Maak verbinding met uw AD-account: `Connect-AzureAD -TenantId <your tenant id>`.</span><span class="sxs-lookup"><span data-stu-id="f1dea-152">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="f1dea-153">U vindt uw tenant-id op **Overzicht** > **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="f1dea-153">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="f1dea-154">Voer de volgende opdracht uit om een Azure AD Service Principal toe te voegen: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` De parameter AppId heeft betrekking op de Customer Insights API-app.</span><span class="sxs-lookup"><span data-stu-id="f1dea-154">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Voorbeeld van Service Principal":::

1. <span data-ttu-id="f1dea-156">Ga terug naar **API-machtigingen** voor uw app-registratie.</span><span class="sxs-lookup"><span data-stu-id="f1dea-156">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="f1dea-157">Selecteer **Beheerders toestemming verlenen voor...** om de app-registratie te voltooien.</span><span class="sxs-lookup"><span data-stu-id="f1dea-157">Select **Grant admin consent for...** to complete the app registration.</span></span>

1. <span data-ttu-id="f1dea-158">Tot slot moeten we de naam van de app-registratie als gebruiker toevoegen in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f1dea-158">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="f1dea-159">Open Customer Insights, ga naar **Beheerder** > **Rechten** en selecteer **Gebruiker toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="f1dea-159">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="f1dea-160">Zoek naar de naam van uw app-registratie, selecteer deze in de zoekresultaten en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f1dea-160">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="f1dea-161">Customer Insights-clientbibliotheken</span><span class="sxs-lookup"><span data-stu-id="f1dea-161">Customer Insights client libraries</span></span>

<span data-ttu-id="f1dea-162">Deze sectie helpt u aan de slag te gaan met het gebruik van de clientbibliotheken die beschikbaar zijn voor de Customer Insights-API's.</span><span class="sxs-lookup"><span data-stu-id="f1dea-162">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span>

### <a name="c-nuget"></a><span data-ttu-id="f1dea-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="f1dea-163">C# NuGet</span></span>

<span data-ttu-id="f1dea-164">Leer hoe u aan de slag gaat met de C#-clientbibliotheken van NuGet.org. Voor meer informatie over het NuGet-pakket, zie [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="f1dea-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="f1dea-165">Momenteel richt dit pakket zich op de frameworks netstandard2.0 en netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="f1dea-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="f1dea-166">De C#-clientbibliotheek toevoegen aan een C#-project</span><span class="sxs-lookup"><span data-stu-id="f1dea-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="f1dea-167">Open in Visual Studio de **NuGet Package Manager** voor uw project.</span><span class="sxs-lookup"><span data-stu-id="f1dea-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="f1dea-168">Zoek **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="f1dea-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="f1dea-169">Selecteer **Installeren** om het pakket aan het project toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="f1dea-169">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="f1dea-170">U kunt deze opdracht ook uitvoeren in de **NuGet Package Manager-console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="f1dea-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Voeg NuGet-pakket toe aan Visual Studio-project":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="f1dea-172">De C#-clientbibliotheek gebruiken</span><span class="sxs-lookup"><span data-stu-id="f1dea-172">Use the C# client library</span></span>

1. <span data-ttu-id="f1dea-173">Gebruik de [Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) om een `AccessToken` op te halen met uw bestaande [Azure app-registratie](#create-a-new-app-registration-in-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="f1dea-173">Use the [Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="f1dea-174">Na het succesvol verifiëren en verkrijgen van een token, bouwt u een nieuwe of gebruikt u een bestaande `HttpClient` met de extra **DefaultRequestHeaders "Autorisatie"** ingesteld op **Bearer <access token>** en **Ocp-Apim-abonnementssleutel** ingesteld op de [**abonnementssleutel** van uw Customer Insights-omgeving](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="f1dea-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="f1dea-175">Reset de **Autorisatie**-koptekst indien van toepassing.</span><span class="sxs-lookup"><span data-stu-id="f1dea-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="f1dea-176">Bijvoorbeeld wanneer het token is verlopen.</span><span class="sxs-lookup"><span data-stu-id="f1dea-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="f1dea-177">Geef deze `HttpClient` door aan de constructie van de `CustomerInsights`-cliënt.</span><span class="sxs-lookup"><span data-stu-id="f1dea-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Voorbeeld van httpclient":::

1. <span data-ttu-id="f1dea-179">Oproepen doen met de client naar de 'extensiemethoden', bijvoorbeeld `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="f1dea-179">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="f1dea-180">Als toegang tot het onderliggende `Microsoft.Rest.HttpOperationResponse` de voorkeur heeft, gebruik dan de "http-berichtmethoden", bijvoorbeeld `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="f1dea-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="f1dea-181">De respons is waarschijnlijk het type `object` omdat de methode meerdere typen kan retourneren (bijvoorbeeld `IList<InstanceInfo>` en `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="f1dea-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="f1dea-182">Om het retourtype te controleren, kunt u de objecten veilig casten in de responstypen die zijn opgegeven op de [API-detailpagina](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) voor die bewerking.</span><span class="sxs-lookup"><span data-stu-id="f1dea-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="f1dea-183">Als er meer informatie over de aanvraag nodig is, gebruik dan de **http-berichtmethoden** om toegang te krijgen tot het onbewerkte responsobject.</span><span class="sxs-lookup"><span data-stu-id="f1dea-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>
