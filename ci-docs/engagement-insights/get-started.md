---
title: Aan de slag met de functionaliteit voor betrokkenheidsinzichten
description: Een overzicht van hulpbronnen om snel aan de slag te gaan.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: c435810e712bbbf69f8f1cfb582fc0a971566de6
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225592"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Aan de slag met de Dynamics 365 Customer Insights functionaliteit voor betrokkenheidsinzichten (openbare preview)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Met de functionaliteit voor betrokkenheidsinzichten kunt u klantgedrag op uw website verzamelen en meten. Het kan worden geïntegreerd met de functionaliteit voor doelgroepinzichten, zodat u naast klantprofielrapporten ook uitgebreide realtime gedragsanalyses kunt zien. De koppelingen in dit artikel helpen u snel uw omgeving te configureren en in te stellen.

## <a name="step-1-review-prerequisites"></a>Stap 1: De vereisten bekijken

U moet over een actief gebruikersaccount voor Microsoft Azure Active Directory (AAD) beschikken. Daarna leest u de volgende artikelen voordat u een werkruimte voor betrokkenheidsinzichten instelt.

- Lees en ga akkoord met de [Servicevoorwaarden](terms-of-service.md) van Microsoft.  
- Lees het artikel [Cookies en toestemming van de gebruiker beheren](user-consent-storage.md). Evalueer daarna of u uw melding van gebruikerstoestemming moet bijwerken. Als u voorheen geen 'niet-essentiële' cookies had, moet u waarschijnlijk uw sitebeleid bijwerken.
- Bekijk de [verklarende woordenlijst](glossary.md) voor een snelle kennismaking met de belangrijkste termen en concepten.

## <a name="step-2-explore-engagement-insights"></a>Stap 2: Betrokkenheidinzichten verkennen

Als u zich voor de eerste keer aanmeldt bij doelgroepinzichten, kunt u instellingen configureren en de mogelijkheden verkennen.

1. Meld u aan bij de [portal voor betrokkenheidsinzichten](https://home.ci.ai.dynamics.com/app/engagement-insights) met uw Microsoft AAD-gebruikersaccount (school of werk).

1. Selecteer uw regio en schakel het vakje in als u zich wilt aanmelden om e-mailupdates en aanbiedingen te ontvangen.

1. Bekijk de **Gebruiksvoorwaarden voor betrokkenheidsinzichten** en de **Privacyverklaring** en selecteer vervolgens **De demo verkennen** om deze instellingen te accepteren.

1. Verken het product met behulp van een set voorbeeldgegevens.

##  <a name="step-3-set-up-a-workspace-and-create-reports"></a>Stap 3: Een werkruimte instellen en rapporten maken

In een werkruimte kunt u gebruikersactiviteiten in realtime bekijken en rapporten opslaan en beheren. Voeg code toe aan uw website om te beginnen met het verzamelen van *gebeurtenissen*, de activiteitsgegevens die binnenkomen van gebruikers.

1. [Maak een werkruimte](create-workspace.md) en voeg leden toe.

1. [Voeg code toe aan uw website](instrument-website.md) of [mobiele app](developer-resources.md#capture-events-from-mobile-apps) om gebruikersactiviteit in uw werkruimte te zien aankomen.

1. Bekijk een [realtime rapport](view-reports.md) met actieve gebruikers per browser, apparaat, besturingssysteem, locatie en taal. U kunt ook [aangepaste rapporten](custom-reports.md) maken om uw eigen visualisaties te maken.

1. Maak [dimensies](dimensions.md) om bezoekers te sorteren op nieuwe en terugkerende gebruikers, [metrische gegevens](metrics.md) om gebruikersgedrag beter te begrijpen, en [segmenten](segments.md) om subsets van bezoekers te identificeren op basis van kenmerken of interacties op de website.
    
## <a name="step-4-export-data-to-other-channels"></a>Stap 4: Gegevens exporteren naar andere kanalen

U kunt *verfijnde gebeurtenissen* maken (een virtuele weergave) van uw webanalysegegevens. Filter en exporteer de gegevens vervolgens naar Azure Data Lake Storage. U kunt de geëxporteerde gegevens opnemen als een gegevensbron.

1. [Maak verfijnde gebeurtenissen](refined-events.md) voor export.

1. [Exporteer de gegevens](export-events.md) naar Azure Data Lake Storage.

1. [Maak een koppeling tussen doelgroepinzichten en betrokkenheidsinzichten](integrate-audience-insights-engagement-insights.md) om gegevens tussen de twee mogelijkheden te delen.

1. [Herken webgebeurtenissen van eerder geverifieerde gebruikers](unknown-to-known.md) met de functie **onbekend tot bekend**.

1. Ontdek hoe u [gebeurtenisgegevens met persoonlijke informatie verwijdert en exporteert](delete-export-personal-data.md).

## <a name="step-5-create-and-manage-funnel-reports"></a>Stap 5: Trechterrapporten maken en beheren

Een trechterrapport verzamelt informatie over de stappen die plaatsvinden tijdens een klantreis via uw website of mobiele app. Naast het maken van kant-en-klare profielrapporten en aangepaste rapporten kunt u een trechterrapport maken om de paden te identificeren die uw klanten volgen voordat ze een aankoop doen. 

1. [Een trechterrapport maken](funnel-reports.md) om geïnformeerde beslissingen te nemen en om gebieden voor optimalisatie en procesverbeteringen te identificeren.

1. Maak trechterrapporten voor meerdere kanalen, zodra u uw mobiele app heeft voorzien van de [Android SDK](get-started-android.md) of [iOS-SDK](get-started-ios.md) voor inzichten in betrokkenheid.

1. Gebruik [trechterinzichten](funnel-reports.md#funnel-insights) om meer inzicht te krijgen in het gedrag van klanten over de stappen in uw trechterrapport.
 
## <a name="step-6-stay-connected"></a>Stap 6: Verbonden blijven

We stellen uw actieve deelname op prijs en nemen alle relevante feedback in overweging bij het ontwikkelen van toekomstige releases. Deel uw feedback en meld problemen via een van deze kanalen:
- [Community](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Feedback geven](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Ondersteuning aanvragen](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
