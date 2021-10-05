---
title: Customer Insights-gegevens exporteren naar Google Ads
description: Leer hoe u de verbinding configureert en exporteert naar Google Ads.
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c958f58c927b76364f305dad8f524dde29b2a638
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558949"
---
# <a name="export-segments-to-google-ads-preview"></a>Segmenten exporteren naar Google Ads (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar een Google Ads-doelgroepenlijst en gebruik ze om te adverteren op Google Search, Gmail, YouTube en Google Display Network. 

> [!IMPORTANT]
> Momenteel kunt u alleen een nieuwe verbinding maken en gegevens exporteren naar Google Ads als u al een goedgekeurde Google Ads Developer-token heeft. Vanwege beleidswijzigingen gaan we de Google Ads-export binnenkort bijwerken en een exportoptie bieden waarvoor geen ontwikkelaarstoken nodig is om de continuïteit van uw ervaring te garanderen en de export naar Google Ads te vereenvoudigen. We raden aan om niet meer verbindingen met Google Ads in te stellen om een gemakkelijkere overstap naar de nieuwe exportoptie te faciliteren.

## <a name="prerequisites-for-connection"></a>Vereisten voor verbinding

-   U hebt een [Google Ads-account](https://ads.google.com/) en bijbehorende beheerdersreferenties nodig.
-   U hebt een [goedgekeurd Google Ads-ontwikkelaarstoken](https://developers.google.com/google-ads/api/docs/first-call/dev-token). 
-   U voldoet aan de eisen van het [beleid inzake klantafstemming](https://support.google.com/adspolicy/answer/6299717).
-   U voldoet aan de eisen van de [hermarketinglijstformaten](https://support.google.com/google-ads/answer/7558048).
-   Er zijn bestaande doelgroepen met bijbehorende id's in Google Ads. Zie [Google Ads-doelgroepen](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.) voor meer informatie.
-   U hebt [geconfigureerde segmenten](segments.md).
-   Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten velden voor e-mailadres, voornaam en achternaam.

## <a name="known-limitations"></a>Bekende beperkingen

- Maximaal 1 miljoen profielen per export naar Google Ads.
- Exporteren naar Google Ads is beperkt tot segmenten.
- Segmenten exporteren met in totaal 1 miljoen profielen kan tot 5 minuten duren vanwege beperkingen aan de providerzijde. 
- Het matchen in Google Ads kan tot 48 uur duren.

## <a name="set-up-connection-to-google-ads"></a>Verbinding met Google Ads instellen

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Google Ads** om de verbinding te configureren.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Voer uw **[Google Ads-klant-id](https://support.google.com/google-ads/answer/1704344)** in.

1. Voer uw **[Door Google Ads goedgekeurde ontwikkelaarstoken](https://developers.google.com/google-ads/api/docs/first-call/dev-token)** in.

1. Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.

1. Selecteer **Verifiëren met Google Ads** en geef uw Google Ads-referenties op.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Opslaan** om de verbinding te voltooien. 

## <a name="configure-an-export"></a>Een export configureren

U kunt deze export configureren als u toegang hebt tot een verbinding van dit type. Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Bestemming toevoegen** om een nieuwe export te maken.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie Google Ads. Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.

1. Voer uw **[Google Ads-doelgroep-id](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** in en selecteer **Verbinden** om de verbinding met Google Ads te initialiseren.

1. Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant.

1. Selecteer de segmenten die u wilt exporteren. U kunt in totaal tot 1 miljoen klantprofielen exporteren naar Google Ads.

Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.

De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab). 

U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar Google Ads te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat Google Ads voldoet aan uw privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.
Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
