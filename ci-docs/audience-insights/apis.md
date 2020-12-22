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
# <a name="work-with-customer-insights-apis"></a>Werken met Customer Insights-API's

Dynamics 365 Customer Insights biedt API's om uw eigen toepassingen te bouwen op basis van uw gegevens in Customer Insights.

> [!IMPORTANT]
> Details van deze API's staan vermeld in de [Referentie voor Customer Insights-API's](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Ze bevatten aanvullende informatie over bewerkingen, parameters en reacties.

In dit artikel leest u hoe u toegang krijgt tot de Customer Insights-API's, een Azure App-registratie maakt en hoe u aan de slag kunt met de beschikbare clientbibliotheken.

## <a name="get-started-trying-the-customer-insights-apis"></a>De Customer Insights-API's uitproberen

1. [Meld u aan](https://home.ci.ai.dynamics.com) bij Customer Insights. Als u nog geen abonnement hebt, [meld u dan aan voor een proefversie van Customer Insights](https://aka.ms/tryci).

1. Ga naar **Beheer** > **Machtigingen** om API's in uw Customer Insights-omgeving in te schakelen. Hiervoor hebt u beheerdersmachtigingen nodig.

1. Ga naar het tabblad **API's** en selecteer de knop **Inschakelen**.    
   Als u de API's inschakelt, wordt een primaire en secundaire abonnementssleutel voor uw exemplaar gemaakt die wordt gebruikt in de API-aanvragen. U kunt de sleutels opnieuw genereren door **Primaire opnieuw genereren** of **Secundaire opnieuw genereren** te selecteren op **Beheer** > **Machtigingen** > **API's**.

   :::image type="content" source="media/enable-apis.gif" alt-text="Customer Insights-API's inschakelen":::

1. Selecteer **Onze API's verkennen** om de API's uit te proberen.

1. Kies een API-bewerking en selecteer **Probeer het uit**.

1. Stel in het deelvenster aan de zijkant de waarde in het vervolgkeuzemenu **Autorisatie** in op **impliciet**. Aan de koptekst `Authorization` wordt een bearer-token toegevoegd. Uw abonnementssleutel wordt automatisch ingevuld.
  
1. Voeg eventueel alle benodigde queryparameters toe.

1. Scrol naar de onderkant van het deelvenster aan de zijkant en selecteer **Verzenden**.

De HTTP-respons wordt snel hieronder weergegeven.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Een nieuwe app-registratie in Azure Portal maken

Met deze stappen kunt u aan de slag met de Customer Insights-API's in een Azure-toepassing met gedelegeerde machtigingen. Lees eerst de [sectie Aan de slag](#get-started-trying-the-customer-insights-apis).

1. Meld u aan op de [Azure-portal](https://portal.azure.com) met het account dat toegang heeft tot de Customer Insights-gegevens.

1. Selecteer aan de linkerkant **App-registraties**.

1. Selecteer **Nieuwe registratie**, geef een toepassingsnaam op en kies het accounttype.
   Voeg eventueel een omleidings-URL toe. http://localhost is voldoende om een toepassing op uw lokale computer te ontwikkelen.

1. Ga bij uw nieuwe app-registratie naar **API-machtigingen**.

1. Selecteer **Een machtiging toevoegen** en selecteer **Customer Insights** in het deelvenster aan de zijkant.

1. Selecteer voor **Machtigingstype** de optie **Gedelegeerde machtigingen** en selecteer de machtiging **gebruikersimitatie**.

1. Selecteer **Machtigingen toevoegen**. Als u toegang tot de API nodig hebt zonder dat een gebruiker zich aanmeldt, leest u de sectie [Machtigingen voor server-naar-server-toepassingen](#server-to-server-application-permissions).

1. Selecteer **Beheerders toestemming verlenen voor...** om de app-registratie te voltooien.

U kunt de toepassings-/client-id voor deze app-registratie gebruiken bij de Microsoft Authentication Library (MSAL) om een bearer-token te verkrijgen om met uw verzoek naar de API te verzenden.

Zie voor meer informatie over MSAL [Overzicht van Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).

Zie voor meer informatie over app-registratie in Azure [De nieuwe registratie-ervaring van de Azure Portal-app](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).

Zie voor informatie over het gebruik van de API's van onze clientbibliotheken [Customer Insights-clientbibliotheken](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Machtigingen voor server-naar-server-toepassingen

In de [sectie app-registratie](#create-a-new-app-registration-in-the-azure-portal) wordt beschreven hoe u een app registreert waarvoor een gebruiker zich moet aanmelden voor verificatie. Ontdek hoe u een app-registratie maakt die geen gebruikersinteractie vereist en die op een server kan worden uitgevoerd.

1. Ga bij uw app-registratie in de Azure-portal naar **API-machtigingen**.

1. Selecteer **Een machtiging toevoegen** en selecteer **Customer Insights** in het deelvenster aan de zijkant.

1. Selecteer voor **Machtigingstype** de optie **Toepassingsmachtigingen** en selecteer de machtiging **CustomerInsights.Api.All**.

1. Selecteer **Machtigingen toevoegen**.

1. Om beheerderstoestemming te geven voor deze toepassing, moet u een Service Principal toevoegen.

   1. Installeer de Azure Active Directory (AD) PowerShell-module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`
   1. Maak verbinding met uw AD-account: `Connect-AzureAD -TenantId <your tenant id>`. U vindt uw tenant-id op **Overzicht** > **Azure Active Directory**.
   1. Voer de volgende opdracht uit om een Azure AD Service Principal toe te voegen: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` De parameter AppId heeft betrekking op de Customer Insights API-app.

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Voorbeeld van Service Principal":::

1. Ga terug naar **API-machtigingen** voor uw app-registratie.

1. Selecteer **Beheerders toestemming verlenen voor...** om de app-registratie te voltooien.

1. Tot slot moeten we de naam van de app-registratie als gebruiker toevoegen in Customer Insights.    
   Open Customer Insights, ga naar **Beheerder** > **Rechten** en selecteer **Gebruiker toevoegen**.

1. Zoek naar de naam van uw app-registratie, selecteer deze in de zoekresultaten en selecteer **Opslaan**.

## <a name="customer-insights-client-libraries"></a>Customer Insights-clientbibliotheken

Deze sectie helpt u aan de slag te gaan met het gebruik van de clientbibliotheken die beschikbaar zijn voor de Customer Insights-API's.

### <a name="c-nuget"></a>C# NuGet

Leer hoe u aan de slag gaat met de C#-clientbibliotheken van NuGet.org. Voor meer informatie over het NuGet-pakket, zie [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Momenteel richt dit pakket zich op de frameworks netstandard2.0 en netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>De C#-clientbibliotheek toevoegen aan een C#-project

1. Open in Visual Studio de **NuGet Package Manager** voor uw project.

1. Zoek **Microsoft.Dynamics.CustomerInsights.Api**.

1. Selecteer **Installeren** om het pakket aan het project toe te voegen.
   U kunt deze opdracht ook uitvoeren in de **NuGet Package Manager-console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Voeg NuGet-pakket toe aan Visual Studio-project":::

#### <a name="use-the-c-client-library"></a>De C#-clientbibliotheek gebruiken

1. Gebruik de [Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) om een `AccessToken` op te halen met uw bestaande [Azure app-registratie](#create-a-new-app-registration-in-the-azure-portal).

1. Na het succesvol verifiëren en verkrijgen van een token, bouwt u een nieuwe of gebruikt u een bestaande `HttpClient` met de extra **DefaultRequestHeaders "Autorisatie"** ingesteld op **Bearer <access token>** en **Ocp-Apim-abonnementssleutel** ingesteld op de [**abonnementssleutel** van uw Customer Insights-omgeving](#get-started-trying-the-customer-insights-apis).    
   Reset de **Autorisatie**-koptekst indien van toepassing. Bijvoorbeeld wanneer het token is verlopen.

1. Geef deze `HttpClient` door aan de constructie van de `CustomerInsights`-cliënt.

   :::image type="content" source="media/httpclient-sample.png" alt-text="Voorbeeld van httpclient":::

1. Oproepen doen met de client naar de 'extensiemethoden', bijvoorbeeld `GetAllInstancesAsync`. Als toegang tot het onderliggende `Microsoft.Rest.HttpOperationResponse` de voorkeur heeft, gebruik dan de "http-berichtmethoden", bijvoorbeeld `GetAllInstancesWithHttpMessagesAsync`.

1. De respons is waarschijnlijk het type `object` omdat de methode meerdere typen kan retourneren (bijvoorbeeld `IList<InstanceInfo>` en `ApiErrorResult`). Om het retourtype te controleren, kunt u de objecten veilig casten in de responstypen die zijn opgegeven op de [API-detailpagina](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) voor die bewerking.    
   Als er meer informatie over de aanvraag nodig is, gebruik dan de **http-berichtmethoden** om toegang te krijgen tot het onbewerkte responsobject.