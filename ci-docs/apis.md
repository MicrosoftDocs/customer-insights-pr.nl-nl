---
title: Werken met Customer Insights-API's
description: API's gebruiken en beperkingen begrijpen.
ms.date: 08/31/2022
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: f499bff4a6ac07a88ff0f773b9cee77dc74989e8
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387334"
---
# <a name="work-with-customer-insights-apis"></a>Werken met Customer Insights-API's

Dynamics 365 Customer Insights biedt API's om uw eigen toepassingen te bouwen op basis van uw gegevens in Customer Insights.

> [!IMPORTANT]
> Details van deze API's staan vermeld in de [Referentie voor Customer Insights-API's](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Ze bevatten aanvullende informatie over bewerkingen, parameters en reacties.

Probeer de Customer Insights-API's, maak een Azure-app-registratie en ga aan de slag met clientbibliotheken.

## <a name="get-started-trying-the-customer-insights-apis"></a>De Customer Insights-API's uitproberen

Schakel Customer Insights API's in en probeer ze uit. Een Customer Insights-beheerder moet API-toegang tot Customer Insights inschakelen. Zodra toegang is ingeschakeld, kan elke gebruiker de API gebruiken met de abonnementssleutel.

1. [Meld u aan](https://home.ci.ai.dynamics.com) bij Customer Insights. Als u nog geen abonnement hebt, [meld u dan aan voor een proefversie van Customer Insights](https://aka.ms/tryci).

1. Ga naar **Beheer** > **Beveiliging** en selecteer het tabblad **API′s**.

1. Als er geen API-toegang tot de omgeving is ingesteld, selecteert u **Inschakelen**.

   Als u de API's inschakelt, wordt een primaire en secundaire abonnementssleutel voor uw exemplaar gemaakt die wordt gebruikt in de API-aanvragen. Selecteer **Primaire opnieuw genereren** of **Secundaire opnieuw genereren** op het tabblad **API′s** om sleutels opnieuw te genereren.

1. Selecteer [**Onze API's verkennen**](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) om de API's uit te proberen.

1. Zoek en selecteer een API-bewerking en selecteer **Uitproberen**.

   :::image type="content" source="media/try-api.png" alt-text="Procedure voor het testen van de API's.":::

1. Stel in het zijvenster de waarde in het vervolgkeuzemenu **Autorisatie** in op **impliciet**. De header `Authorization` wordt toegevoegd met een bearer-token. Uw abonnementssleutel wordt automatisch ingevuld.
  
1. Voeg eventueel alle benodigde queryparameters toe.

1. Scrol naar de onderkant van het deelvenster aan de zijkant en selecteer **Verzenden**.

   De HTTP-respons verschijnt onder aan het deelvenster.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Een nieuwe app-registratie in Azure Portal maken

Maak een nieuwe [app-registratie](/graph/auth-register-app-v2) om de Customer Insights-API's te gebruiken in een Azure-toepassing met gedelegeerde toestemmingen.

1. Voltooi de [sectie Aan de slag](#get-started-trying-the-customer-insights-apis).

1. Meld u aan op de [Azure-portal](https://portal.azure.com) met het account dat toegang heeft tot de Customer Insights-gegevens.

1. Zoek naar en selecteer vervolgens **App-registraties**.

1. Selecteer **Nieuwe registratie**, geef een toepassingsnaam op en kies het accounttype.

   Voeg eventueel een omleidings-URL toe. http://localhost is voldoende om een toepassing op uw lokale computer te ontwikkelen.

1. Selecteer **Registreren**.

1. Ga bij uw nieuwe app-registratie naar **API-machtigingen**.

1. Selecteer **Een machtiging toevoegen** en selecteer **Dynamics 365 AI voor Customer Insights** in het zijpaneel.

1. Selecteer voor **Type machtiging** de optie **Gedelegeerde machtigingen** en selecteer vervolgens de machtiging **user_impersonation**.

1. Selecteer **Machtigingen toevoegen**.

1. Selecteer **Beheerders toestemming verlenen voor...** om de app-registratie te voltooien.

1. Voor toegang tot de API zonder dat een gebruiker zich aanmeldt, gaat u naar [Machtigingen voor server-naar-server-toepassingen](#server-to-server-application-permissions).

U kunt de toepassings-/client-id voor deze app-registratie gebruiken bij de [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) om een bearer-token te verkrijgen om met uw verzoek naar de API te verzenden.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Zie [Customer Insights-clientbibliotheken](#customer-insights-client-libraries) voor informatie over het gebruik van de API's in onze clientbibliotheken.

### <a name="server-to-server-application-permissions"></a>Machtigingen voor server-naar-server-toepassingen

Maak een app-registratie waarvoor geen gebruikersinteractie nodig is en die op een server kan worden uitgevoerd.

1. Ga bij uw app-registratie in de Azure-portal naar **API-machtigingen**.

1. Selecteer **Een machtiging toevoegen**.

1. Selecteer het tabblad **API's die mijn organisatie gebruikt** en kies **Dynamics 365 AI voor Customer Insights** in de lijst.

1. Selecteer voor **Type machtiging** de optie **Toepassingsachtigingen** en selecteer vervolgens de machtiging **CustomerInsights.Api.All**.

1. Selecteer **Machtigingen toevoegen**.

1. Ga terug naar **API-machtigingen** voor uw app-registratie.

1. Selecteer **Beheerders toestemming verlenen voor...** om de app-registratie te voltooien.

   <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Voeg de naam van de app-registratie als gebruiker toe in Customer Insights.

   1. Open Customer Insights, ga naar **Beheerder** > **Beveiliging** en selecteer **Gebruikers toevoegen**.

   1. Zoek naar de naam van uw app-registratie, selecteer deze in de zoekresultaten en selecteer **Opslaan**.

## <a name="sample-queries"></a>Voorbeeldquery's

Een korte lijst met OData-voorbeeldquery's om met de API's te werken, vindt u hier: [Voorbeelden van OData-query's](odata-examples.md).

## <a name="customer-insights-client-libraries"></a>Customer Insights-clientbibliotheken

Aan de slag met het gebruik van de clientbibliotheken die beschikbaar zijn voor de Customer Insights-API's. Alle broncode en voorbeeldtoepassingen van de bibliotheek zijn te vinden op de [GitHub-pagina voor Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries)​.

### <a name="c-nuget"></a>C# NuGet

Gebruik de C#clientbibliotheken van NuGet.org. Momenteel richt het pakket zich op de frameworks netstandard2.0 en netcoreapp2.0. Meer informatie over het NuGet-pakket, vindt u hier: [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).

#### <a name="add-the-c-client-library-to-a-c-project"></a>De C#-clientbibliotheek toevoegen aan een C#-project

1. Open in Visual Studio de **NuGet Package Manager** voor uw project.

1. Zoek **Microsoft.Dynamics.CustomerInsights.Api**.

1. Selecteer **Installeren** om het pakket aan het project toe te voegen.

   U kunt deze opdracht ook uitvoeren in de **NuGet Package Manager-console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>De C#-clientbibliotheek gebruiken

1. Gebruik de [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) om een `AccessToken` op te halen met uw bestaande [Azure app-registratie](#create-a-new-app-registration-in-the-azure-portal).

1. Nadat u een token hebt geverifieerd en verkregen, maakt u een nieuwe of gebruikt u een bestaande `HttpClient` met de **DefaultRequestHeaders "Authorization"** ingesteld op **Bearer "access token"** en **Ocp-Apim-Subscription-Key** ingesteld op de [**abonnementssleutel** uit uw Customer Insights-omgeving](#get-started-trying-the-customer-insights-apis).   

   Reset de **Autorisatie**-koptekst indien van toepassing. Bijvoorbeeld wanneer het token is verlopen.

1. Geef deze `HttpClient` door aan de constructie van de `CustomerInsights`-cliënt.

   <!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Oproepen doen met de client naar de 'extensiemethoden', bijvoorbeeld `GetAllInstancesAsync`. Als toegang tot het onderliggende `Microsoft.Rest.HttpOperationResponse` de voorkeur heeft, gebruik dan de 'http-berichtmethoden', bijvoorbeeld `GetAllInstancesWithHttpMessagesAsync`.

1. De respons is waarschijnlijk het type `object` omdat de methode meerdere typen kan retourneren (bijvoorbeeld `IList<InstanceInfo>` en `ApiErrorResult`). Gebruik om het retourtype te controleren, de objecten in de responstypen die zijn opgegeven op de [API-detailspagina](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) voor die bewerking.

   Als er meer informatie over de aanvraag nodig is, gebruik dan de **http-berichtmethoden** om toegang te krijgen tot het onbewerkte responsobject.

### <a name="nodejs-package"></a>NodeJS-pakket

Gebruik de NodeJS-clientbibliotheken die beschikbaar zijn via NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Python-pakket

Gebruik de Python-clientbibliotheken die beschikbaar zijn via PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
