---
title: Aan de slag met de functionaliteit voor betrokkenheidsinzichten
description: Een overzicht van hulpbronnen om snel aan de slag te gaan.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 12/21/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5ee1567cea834670a16aaa3253912b7957ce26b3
ms.sourcegitcommit: 86739a3f238162fc96837270b5d184e648fab15c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2021
ms.locfileid: "7405352"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Aan de slag met de Dynamics 365 Customer Insights functionaliteit voor betrokkenheidsinzichten (openbare preview)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Met de functionaliteit voor betrokkenheidsinzichten kunt u klantgedrag op uw website verzamelen en meten. Het kan worden geïntegreerd met de functionaliteit voor doelgroepinzichten, zodat u naast klantprofielrapporten ook uitgebreide realtime gedragsanalyses kunt zien. De koppelingen in dit artikel helpen u snel uw omgeving te configureren en in te stellen.

## <a name="step-1-review-prerequisites"></a>Stap 1: De vereisten bekijken

Eerst moet u een actieve Microsoft Azure Active Directory-gebruikersaccount hebben. Daarna leest u de volgende artikelen voordat u een werkruimte voor betrokkenheidsinzichten instelt.

- Controleer en ga akkoord met de [Servicevoorwaarden](terms-of-service.md) met Microsoft.  
- Lees het artikel [Cookies en toestemming van de gebruiker beheren](user-consent-storage.md). Evalueer na het lezen van dit artikel of u uw melding over toestemming van gebruikers moet bijwerken. Als u voorheen geen 'niet-essentiële' cookies had, moet u waarschijnlijk uw sitebeleid bijwerken.
- Bekijk de [verklarende woordenlijst](glossary.md) voor een snelle kennismaking met de belangrijkste termen en concepten.

## <a name="step-2-explore-engagement-insights"></a>Stap 2: Betrokkenheidinzichten verkennen

De eerste keer dat u betrokkenheidsinzichten bezoekt, kunt u instellingen configureren, beleid controleren en het product verkennen.

1. Meld u aan op de [Portal voor de betrokkenheidsinzichten-functionaliteit](https://pi.dynamics.com) met uw Microsoft Azure Active Directory-gebruikersaccount. (Het kan uw school- of werkaccount zijn.)

1. Selecteer uw regio en gebruik het selectievakje om aan te geven of u zich wilt aanmelden voor het ontvangen van updates en aanbiedingen via e-mail.

1. Lees de **Gebruiksvoorwaarden voor betrokkenheidsinzichten (preview)** en de **Privacyverklaring** door en selecteer **Bekijk de demo** om ze te accepteren.

1. Verken het product met behulp van een set voorbeeldgegevens.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>Stap 3: Een werkruimte instellen en code aan uw website toevoegen

In de werkruimte kunt u de gebruikersactiviteit in realtime bekijken en rapporten opslaan en beheren. Voeg code toe aan uw website om te beginnen met het verzamelen van *gebeurtenissen*, de activiteitsgegevens die binnenkomen van gebruikers.

1. [Maak een werkruimte](create-workspace.md) en voeg leden toe.

1. [Voeg code toe aan uw website](instrument-website.md) of [mobiele app](developer-resources.md#capture-events-from-mobile-apps) om gebruikersactiviteit in uw werkruimte te zien aankomen.

1. Bekijk een [realtime rapport](view-reports.md) dat actieve gebruikers toont per browser, apparaat, besturingssysteem, locatie en taal. U kunt ook [aangepaste rapporten](custom-reports.md) maken om uw eigen visualisaties te maken.
    
## <a name="step-4-export-data-to-other-channels"></a>Stap 4: Gegevens exporteren naar andere kanalen

U kunt *verfijnde gebeurtenissen* maken (een virtuele weergave) van uw webanalysegegevens. Filter en exporteer de gegevens vervolgens naar Azure Data Lake Storage. U kunt de geëxporteerde gegevens opnemen als een gegevensbron. Zie [Een koppeling tot stand brengen tussen doelgroepinzichten en betrokkenheidsinzichten](integrate-audience-insights-engagement-insights.md) voor meer informatie.

1. [Maak verfijnde gebeurtenissen](refined-events.md) voor export.

1. [Exporteer de gegevens](export-events.md) naar Data Lake Storage.

1. Ontdek hoe u [gebeurtenisgegevens met persoonlijke informatie verwijdert en exporteert](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>Stap 5: Verbonden blijven

We stellen uw actieve deelname op prijs en zijn van plan alle relevante feedback in overweging te nemen bij het ontwikkelen van toekomstige releases. Deel uw feedback en meld problemen via een van deze kanalen:
- [Community](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Feedback geven](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Ondersteuning aanvragen](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
