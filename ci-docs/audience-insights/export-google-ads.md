---
title: Customer Insights-gegevens exporteren naar Google Ads
description: Ontdek hoe u de verbinding met Google Ads configureert.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568424"
---
# <a name="connector-for-google-ads-preview"></a>Connector voor Google Ads (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar de Google Ads-doelgroeplijst en gebruik ze om te adverteren op Google Zoeken, Gmail, YouTube en Google Display Netwerk. 

## <a name="prerequisites"></a>Vereisten

-   U hebt een [Google Ads-account](https://ads.google.com/) en bijbehorende beheerdersreferenties nodig.
-   Er zijn bestaande doelgroepen met bijbehorende id's in Google Ads. Zie [Google Ads-doelgroepen](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.) voor meer informatie.
-   U hebt [geconfigureerde segmenten](segments.md)
-   Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten velden voor e-mailadres, voornaam en achternaam

## <a name="connect-to-google-ads"></a>Verbinding maken met Google Ads

1. Ga naar **Beheer** > **Exportbestemmingen**.

1. Selecteer onder **Google Ads** de optie **Instellen**.

1. Geef uw exportbestemming een herkenbare naam in het veld **Weergavenaam**.

1. Voer uw **[Google Ads-klant-id](https://support.google.com/google-ads/answer/1704344)** in.

1. Voer uw **[Door Google Ads goedgekeurde ontwikkelaarstoken](https://developers.google.com/google-ads/api/docs/first-call/dev-token)** in.

1. Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.

1. Voer uw **[Google Ads-doelgroep-id](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** in en selecteer **Verbinden** om de verbinding met Google Ads te initialiseren.

1. Selecteer **Verifiëren met Google Ads** en geef uw Google Ads-referenties op.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Schermopname voor Google Ads-verbinding exporteren":::

1. Selecteer **Volgende** om de export te configureren.

## <a name="configure-the-connector"></a>De connector configureren

1. Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant. Herhaal dezelfde stappen voor de velden **Voornaam** en **Achternaam**.

1. Selecteer de segmenten die u wilt exporteren. U kunt in totaal tot 1 miljoen klantprofielen exporteren naar Google Ads.

1. Selecteer **Opslaan**.

## <a name="export-the-data"></a>De gegevens exporteren

U kunt [gegevens op aanvraag exporteren](export-destinations.md). De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab). In Google Ads vindt u nu uw segmenten onder [Google Ads-doelgroepen](https://support.google.com/google-ads/answer/7558048?hl=en/).

## <a name="known-limitations"></a>Bekende beperkingen

- Maximaal 1 miljoen profielen per export naar Google Ads.
- Exporteren naar Google Ads is beperkt tot segmenten.
- Segmenten exporteren met in totaal 1 miljoen profielen kan tot 5 minuten duren vanwege beperkingen aan de providerzijde. 
- Het matchen in Google Ads kan tot 48 uur duren.

## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar Google Ads te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat Google Ads voldoet aan uw privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.
Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.
