---
title: Aan de slag met de functionaliteit voor betrokkenheidsinzichten
description: Een overzicht van hulpbronnen om snel aan de slag te gaan.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 644b125f5d140627d357630ded88dd6838d6edb7
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494588"
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

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>Stap 3: Een werkruimte instellen en code aan uw website toevoegen

In een werkruimte kunt u gebruikersactiviteiten in realtime bekijken en rapporten opslaan en beheren. Voeg code toe aan uw website om te beginnen met het verzamelen van *gebeurtenissen*, de activiteitsgegevens die binnenkomen van gebruikers.

1. [Maak een werkruimte](create-workspace.md) en voeg leden toe.

1. [Voeg code toe aan uw website](instrument-website.md) of [mobiele app](developer-resources.md#capture-events-from-mobile-apps) om gebruikersactiviteit in uw werkruimte te zien aankomen.

1. Bekijk een [realtime rapport](view-reports.md) met actieve gebruikers per browser, apparaat, besturingssysteem, locatie en taal. U kunt ook [aangepaste rapporten](custom-reports.md) maken om uw eigen visualisaties te maken.
    
## <a name="step-4-export-data-to-other-channels"></a>Stap 4: Gegevens exporteren naar andere kanalen

U kunt *verfijnde gebeurtenissen* maken (een virtuele weergave) van uw webanalysegegevens. Filter en exporteer de gegevens vervolgens naar Azure Data Lake Storage. U kunt de geëxporteerde gegevens opnemen als een gegevensbron. Zie [Een koppeling tot stand brengen tussen doelgroepinzichten en betrokkenheidsinzichten](integrate-audience-insights-engagement-insights.md) voor meer informatie.

1. [Maak verfijnde gebeurtenissen](refined-events.md) voor export.

1. [Exporteer de gegevens](export-events.md) naar Data Lake Storage.

1. [Maak een koppeling tussen doelgroepinzichten en betrokkenheidsinzichten](integrate-audience-insights-engagement-insights.md) om gegevens tussen de twee mogelijkheden te delen.

1. Ontdek hoe u [gebeurtenisgegevens met persoonlijke informatie verwijdert en exporteert](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>Stap 5: Verbonden blijven

We stellen uw actieve deelname op prijs en nemen alle relevante feedback in overweging bij het ontwikkelen van toekomstige releases. Deel uw feedback en meld problemen via een van deze kanalen:
- [Community](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Feedback geven](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Ondersteuning aanvragen](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
