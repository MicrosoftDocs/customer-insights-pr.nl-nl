---
title: Werken met API's
description: API's gebruiken en beperkingen begrijpen.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9326f821f9970ba2254ab804814e369abb677eb0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304736"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="4a190-103">Werken met Customer Insights-API's</span><span class="sxs-lookup"><span data-stu-id="4a190-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="4a190-104">Dynamics 365 Customer Insights biedt API's om uw eigen toepassingen te bouwen op basis van uw gegevens in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4a190-104">Dynamics 365 Customer Insights provides APIs to build your own applications based on your data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4a190-105">Details van deze API's staan vermeld in de [Referentie voor Customer Insights-API's](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="4a190-105">Details of these APIs are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="4a190-106">Ze bevatten aanvullende informatie over bewerkingen, parameters en reacties.</span><span class="sxs-lookup"><span data-stu-id="4a190-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="4a190-107">In dit artikel wordt beschreven hoe u toegang krijgt tot de Customer Insights-API's, een registratie van Azure-apps maakt en aan de slag gaat met de beschikbare clientbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="4a190-107">This article describes how to access the Customer Insights APIs, create an Azure App Registration, and get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="4a190-108">De Customer Insights-API's uitproberen</span><span class="sxs-lookup"><span data-stu-id="4a190-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="4a190-109">[Meld u aan](https://home.ci.ai.dynamics.com) bij Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4a190-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="4a190-110">Als u nog geen abonnement hebt, [meld u dan aan voor een proefversie van Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="4a190-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="4a190-111">Ga naar **Beheer** > **Machtigingen** om API's in uw Customer Insights-omgeving in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="4a190-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="4a190-112">Hiervoor hebt u beheerdersmachtigingen nodig.</span><span class="sxs-lookup"><span data-stu-id="4a190-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="4a190-113">Ga naar het tabblad **API's** en selecteer de knop **Inschakelen**.</span><span class="sxs-lookup"><span data-stu-id="4a190-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
 
   <span data-ttu-id="4a190-114">Als u de API's inschakelt, wordt een primaire en secundaire abonnementssleutel voor uw exemplaar gemaakt die wordt gebruikt in de API-aanvragen.</span><span class="sxs-lookup"><span data-stu-id="4a190-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="4a190-115">U kunt de sleutels opnieuw genereren door **Primaire opnieuw genereren** of **Secundaire opnieuw genereren** te selecteren op **Beheer** > **Machtigingen** > **API's**.</span><span class="sxs-lookup"><span data-stu-id="4a190-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Customer Insights-API's inschakelen":::

1. <span data-ttu-id="4a190-117">Selecteer **Onze API's verkennen** om de [API's uit te proberen](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span><span class="sxs-lookup"><span data-stu-id="4a190-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="4a190-118">Kies een API-bewerking en selecteer **Probeer het uit**.</span><span class="sxs-lookup"><span data-stu-id="4a190-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="4a190-119">Stel in het zijvenster de waarde in het vervolgkeuzemenu **Autorisatie** in op **impliciet**.</span><span class="sxs-lookup"><span data-stu-id="4a190-119">In the side pane, set the value in the **Authorization** dropdown menu to **implicit**.</span></span> <span data-ttu-id="4a190-120">De header `Authorization` wordt toegevoegd met een bearer-token.</span><span class="sxs-lookup"><span data-stu-id="4a190-120">The `Authorization` header gets added with a bearer token.</span></span> <span data-ttu-id="4a190-121">Uw abonnementssleutel wordt automatisch ingevuld.</span><span class="sxs-lookup"><span data-stu-id="4a190-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="4a190-122">Voeg eventueel alle benodigde queryparameters toe.</span><span class="sxs-lookup"><span data-stu-id="4a190-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="4a190-123">Scrol naar de onderkant van het deelvenster aan de zijkant en selecteer **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="4a190-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="4a190-124">De HTTP-respons wordt snel hieronder weergegeven.</span><span class="sxs-lookup"><span data-stu-id="4a190-124">The HTTP response will soon appear below.</span></span>

   :::image type="content" source="media/try-apis.gif" alt-text="Procedure voor het testen van de API's.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="4a190-126">Een nieuwe app-registratie in Azure Portal maken</span><span class="sxs-lookup"><span data-stu-id="4a190-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="4a190-127">Met deze stappen kunt u aan de slag gaan met het gebruik van de Customer Insights-API's in een Azure-toepassing met gedelegeerde machtigingen.</span><span class="sxs-lookup"><span data-stu-id="4a190-127">These steps help you get started with using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="4a190-128">Zorg ervoor dat u eerst de [sectie Aan de slag](#get-started-trying-the-customer-insights-apis) voltooit.</span><span class="sxs-lookup"><span data-stu-id="4a190-128">Make sure to complete the [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="4a190-129">Meld u aan op de [Azure-portal](https://portal.azure.com) met het account dat toegang heeft tot de Customer Insights-gegevens.</span><span class="sxs-lookup"><span data-stu-id="4a190-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="4a190-130">Selecteer aan de linkerkant **App-registraties**.</span><span class="sxs-lookup"><span data-stu-id="4a190-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="4a190-131">Selecteer **Nieuwe registratie**, geef een toepassingsnaam op en kies het accounttype.</span><span class="sxs-lookup"><span data-stu-id="4a190-131">Select **New registration**, provide an application name and choose the account type.</span></span>
 
   <span data-ttu-id="4a190-132">Voeg eventueel een omleidings-URL toe.</span><span class="sxs-lookup"><span data-stu-id="4a190-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="4a190-133">http://localhost is voldoende om een toepassing op uw lokale computer te ontwikkelen.</span><span class="sxs-lookup"><span data-stu-id="4a190-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="4a190-134">Ga bij uw nieuwe app-registratie naar **API-machtigingen**.</span><span class="sxs-lookup"><span data-stu-id="4a190-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="Procedure voor het instellen van API-machtigingen in app-registratie.":::

1. <span data-ttu-id="4a190-136">Selecteer **Een machtiging toevoegen** en selecteer **Customer Insights** in het deelvenster aan de zijkant.</span><span class="sxs-lookup"><span data-stu-id="4a190-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="4a190-137">Selecteer voor **Type machtiging** de optie **Gedelegeerde machtigingen** en selecteer vervolgens de machtiging **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="4a190-137">For **Permission type**, select **Delegated permissions** and then select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="4a190-138">Selecteer **Machtigingen toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="4a190-138">Select **Add permissions**.</span></span> <span data-ttu-id="4a190-139">Als u toegang tot de API nodig hebt zonder dat een gebruiker zich aanmeldt, leest u de sectie [Machtigingen voor server-naar-server-toepassingen](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="4a190-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="4a190-140">Selecteer **Beheerders toestemming verlenen voor...** om de app-registratie te voltooien.</span><span class="sxs-lookup"><span data-stu-id="4a190-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="4a190-141">U kunt de toepassings-/client-id voor deze app-registratie gebruiken bij de Microsoft Authentication Library (MSAL) om een bearer-token te verkrijgen om met uw verzoek naar de API te verzenden.</span><span class="sxs-lookup"><span data-stu-id="4a190-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Procedure voor het verlenen van toestemming door de beheerder.":::

<span data-ttu-id="4a190-143">Zie voor meer informatie over MSAL [Overzicht van Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="4a190-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="4a190-144">Zie [Een toepassing registreren](/azure/active-directory/develop/quickstart-register-app.md#register-an-application) voor meer informatie over app-registratie in Azure.</span><span class="sxs-lookup"><span data-stu-id="4a190-144">For more information about app registration in Azure, see [Register an application](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span></span>

<span data-ttu-id="4a190-145">Zie [Customer Insights-clientbibliotheken](#customer-insights-client-libraries) voor informatie over het gebruik van de API's in onze clientbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="4a190-145">For information on using the APIs in our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="4a190-146">Machtigingen voor server-naar-server-toepassingen</span><span class="sxs-lookup"><span data-stu-id="4a190-146">Server-to-server application permissions</span></span>

<span data-ttu-id="4a190-147">In de [sectie app-registratie](#create-a-new-app-registration-in-the-azure-portal) wordt beschreven hoe u een app registreert waarvoor een gebruiker zich moet aanmelden voor verificatie.</span><span class="sxs-lookup"><span data-stu-id="4a190-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="4a190-148">Ontdek hoe u een app-registratie maakt die geen gebruikersinteractie vereist en die op een server kan worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="4a190-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="4a190-149">Ga bij uw app-registratie in de Azure-portal naar **API-machtigingen**.</span><span class="sxs-lookup"><span data-stu-id="4a190-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="4a190-150">Selecteer **Een machtiging toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="4a190-150">Select **Add a permission**.</span></span> 

1. <span data-ttu-id="4a190-151">Selecteer het tabblad **API's die mijn organisatie gebruikt** en kies **Dynamics 365 AI voor Customer Insights** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="4a190-151">Select the **APIs my organization uses** tab and choose **Dynamics 365 AI for Customer Insights** from the list.</span></span> 

1. <span data-ttu-id="4a190-152">Selecteer voor **Type machtiging** de optie **Toepassingsachtigingen** en selecteer vervolgens de machtiging **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="4a190-152">For **Permission type**, select **Application permissions** and then select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="4a190-153">Selecteer **Machtigingen toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="4a190-153">Select **Add permissions**.</span></span>

1. <span data-ttu-id="4a190-154">Ga terug naar **API-machtigingen** voor uw app-registratie.</span><span class="sxs-lookup"><span data-stu-id="4a190-154">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="4a190-155">Selecteer **Beheerders toestemming verlenen voor...** om de app-registratie te voltooien.</span><span class="sxs-lookup"><span data-stu-id="4a190-155">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Procedure voor het verlenen van toestemming door de beheerder.":::

1. <span data-ttu-id="4a190-157">Tot slot moeten we de naam van de app-registratie als gebruiker toevoegen in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4a190-157">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>  
   
   <span data-ttu-id="4a190-158">Open Customer Insights, ga naar **Beheerder** > **Rechten** en selecteer **Gebruiker toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="4a190-158">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="4a190-159">Zoek naar de naam van uw app-registratie, selecteer deze in de zoekresultaten en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="4a190-159">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="4a190-160">Customer Insights-clientbibliotheken</span><span class="sxs-lookup"><span data-stu-id="4a190-160">Customer Insights client libraries</span></span>

<span data-ttu-id="4a190-161">Deze sectie helpt u aan de slag te gaan met het gebruik van de clientbibliotheken die beschikbaar zijn voor de Customer Insights-API's.</span><span class="sxs-lookup"><span data-stu-id="4a190-161">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="4a190-162">Alle broncode en voorbeeldtoepassingen van de bibliotheek zijn te vinden op de [GitHub-pagina voor Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries)​.</span><span class="sxs-lookup"><span data-stu-id="4a190-162">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="4a190-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="4a190-163">C# NuGet</span></span>

<span data-ttu-id="4a190-164">Leer hoe u aan de slag gaat met de C#-clientbibliotheken van NuGet.org. Voor meer informatie over het NuGet-pakket, zie [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="4a190-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="4a190-165">Momenteel richt dit pakket zich op de frameworks netstandard2.0 en netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="4a190-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="4a190-166">De C#-clientbibliotheek toevoegen aan een C#-project</span><span class="sxs-lookup"><span data-stu-id="4a190-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="4a190-167">Open in Visual Studio de **NuGet Package Manager** voor uw project.</span><span class="sxs-lookup"><span data-stu-id="4a190-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="4a190-168">Zoek **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="4a190-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="4a190-169">Selecteer **Installeren** om het pakket aan het project toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="4a190-169">Select **Install** to add the package to the project.</span></span>
 
   <span data-ttu-id="4a190-170">U kunt deze opdracht ook uitvoeren in de **NuGet Package Manager-console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="4a190-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Voeg NuGet-pakket toe aan Visual Studio-project":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="4a190-172">De C#-clientbibliotheek gebruiken</span><span class="sxs-lookup"><span data-stu-id="4a190-172">Use the C# client library</span></span>

1. <span data-ttu-id="4a190-173">Gebruik de [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) om een `AccessToken` op te halen met uw bestaande [Azure app-registratie](#create-a-new-app-registration-in-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="4a190-173">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="4a190-174">Na het succesvol verifiëren en verkrijgen van een token, bouwt u een nieuwe of gebruikt u een bestaande `HttpClient` met de extra **DefaultRequestHeaders "Autorisatie"** ingesteld op **Bearer <access token>** en **Ocp-Apim-abonnementssleutel** ingesteld op de [**abonnementssleutel** van uw Customer Insights-omgeving](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="4a190-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>   
 
   <span data-ttu-id="4a190-175">Reset de **Autorisatie**-koptekst indien van toepassing.</span><span class="sxs-lookup"><span data-stu-id="4a190-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="4a190-176">Bijvoorbeeld wanneer het token is verlopen.</span><span class="sxs-lookup"><span data-stu-id="4a190-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="4a190-177">Geef deze `HttpClient` door aan de constructie van de `CustomerInsights`-cliënt.</span><span class="sxs-lookup"><span data-stu-id="4a190-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Voorbeeld van httpclient":::

1. <span data-ttu-id="4a190-179">Doe oproepen met de client naar de 'extensiemethoden', bijvoorbeeld `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="4a190-179">Make calls with the client to the "extension methods"—for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="4a190-180">Als toegang tot het onderliggende `Microsoft.Rest.HttpOperationResponse` de voorkeur heeft, gebruik dan de 'http-berichtmethoden', bijvoorbeeld `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="4a190-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods"—for example, `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="4a190-181">De respons is waarschijnlijk het type `object` omdat de methode meerdere typen kan retourneren (bijvoorbeeld `IList<InstanceInfo>` en `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="4a190-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="4a190-182">Om het retourtype te controleren, kunt u de objecten veilig casten in de responstypen die zijn opgegeven op de [API-detailpagina](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) voor die bewerking.</span><span class="sxs-lookup"><span data-stu-id="4a190-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   
   <span data-ttu-id="4a190-183">Als er meer informatie over de aanvraag nodig is, gebruik dan de **http-berichtmethoden** om toegang te krijgen tot het onbewerkte responsobject.</span><span class="sxs-lookup"><span data-stu-id="4a190-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="4a190-184">NodeJS-pakket</span><span class="sxs-lookup"><span data-stu-id="4a190-184">NodeJS package</span></span>

<span data-ttu-id="4a190-185">Gebruik de NodeJS-clientbibliotheken die beschikbaar zijn via NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="4a190-185">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="4a190-186">Python-pakket</span><span class="sxs-lookup"><span data-stu-id="4a190-186">Python package</span></span>

<span data-ttu-id="4a190-187">Gebruik de Python-clientbibliotheken die beschikbaar zijn via PyPi: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="4a190-187">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
