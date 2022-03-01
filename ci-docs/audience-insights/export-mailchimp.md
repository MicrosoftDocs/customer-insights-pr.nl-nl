---
title: Customer Insights-gegevens exporteren naar Mailchimp
description: Ontdek hoe u de verbinding met Mailchimp configureert.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: edff494f6edf26a8b641cb1d788a715389ddb346
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405471"
---
# <a name="connector-for-mailchimp-preview"></a>Connector voor Mailchimp (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar Mailchimp om nieuwsbrieven en e-mailcampagnes te maken.

## <a name="prerequisites"></a>Vereisten

-   U hebt een [Mailchimp-account](https://mailchimp.com/) en bijbehorende beheerdersreferenties nodig.
-   Er zijn bestaande doelgroepen met bijbehorende id's in Mailchimp. Zie [Mailchimp-doelgroepen](https://mailchimp.com/help/create-audience/) voor meer informatie.
-   U hebt [geconfigureerde segmenten](segments.md)
-   Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.

## <a name="connect-to-mailchimp"></a>Verbinding maken met MailChimp

1. Ga naar **Beheer** > **Exportbestemmingen**.

1. Selecteer onder **Mailchimp** de optie **Instellen**.

1. Geef uw exportbestemming een herkenbare naam in het veld **Weergavenaam**.

1. Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.

1. Voer uw **[Mailchimp-doelgroep-id](https://mailchimp.com/help/find-audience-id/)** in en selecteer **Verbinden** om de verbinding met Mailchimp te initialiseren.

1. Selecteer **Verifiëren met Mailchimp** en geef uw Mailchimp-referenties op.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Schermopname voor Mailchimp-verbinding exporteren":::

1. Selecteer **Volgende** om de export te configureren.

## <a name="configure-the-connector"></a>De connector configureren

1. Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant. 

1. Optioneel kunt u **Voornaam** en **Achternaam** exporteren als extra velden om meer gepersonaliseerde e-mails te maken. Selecteer **Kenmerk toevoegen** om deze velden toe te wijzen.

1. Selecteer de segmenten die u wilt exporteren. U kunt in totaal tot 1 miljoen klantprofielen exporteren naar Mailchimp.

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Velden en segmenten selecteren om naar Mailchimp te exporteren":::

1. Selecteer **Opslaan**.

## <a name="export-the-data"></a>De gegevens exporteren

U kunt [gegevens op aanvraag exporteren](export-destinations.md). De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab). In Mailchimp vindt u nu uw segmenten onder [Mailchimp-doelgroepen](https://mailchimp.com/help/create-audience/).

## <a name="known-limitations"></a>Bekende beperkingen

- Maximaal 1 miljoen profielen per export naar Mailchimp.
- Exporteren naar Mailchimp is beperkt tot segmenten.
- Segmenten exporteren met in totaal 1 miljoen profielen kan tot drie uur duren vanwege beperkingen aan de providerzijde. 
- Het aantal profielen dat u naar Mailchimp kunt exporteren, is afhankelijk van uw contract met Mailchimp.

## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar Mailchimp te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat Mailchimp voldoet aan uw privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.
Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.
