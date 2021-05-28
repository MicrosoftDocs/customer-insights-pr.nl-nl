---
title: Customer Insights-gegevens exporteren naar Mailchimp
description: Leer hoe u de verbinding configureert en exporteert naar Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 35848998e738c7ecc1642f2b75912ff78d85f79e
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976149"
---
# <a name="export-segment-lists-to-mailchimp-preview"></a>Segmentlijsten exporteren naar Mailchimp (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar Mailchimp om nieuwsbrieven en e-mailcampagnes te maken.

## <a name="prerequisites-for-connection"></a>Vereisten voor verbinding

-   U hebt een [Mailchimp-account](https://mailchimp.com/) en bijbehorende beheerdersreferenties nodig.
-   Er zijn bestaande doelgroepen met bijbehorende id's in Mailchimp. Zie [Mailchimp-doelgroepen](https://mailchimp.com/help/create-audience/) voor meer informatie.
-   U hebt [geconfigureerde segmenten](segments.md)
-   Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.

## <a name="known-limitations"></a>Bekende beperkingen

- Maximaal 1 miljoen profielen per export naar Mailchimp.
- Exporteren naar Mailchimp is beperkt tot segmenten.
- Het exporteren van segmenten met 1 miljoen profielen kan tot drie uur duren. 
- Het aantal profielen dat u naar Mailchimp kunt exporteren, is afhankelijk van uw contract met Mailchimp.

## <a name="set-up-connection-to-mailchimp"></a>Verbinding instellen met Mailchimp

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Autopilot** om de verbinding te configureren.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.

1. Selecteer **Verbinden** om de verbinding met Mailchimp te initialiseren.

1. Selecteer **Verifiëren met Mailchimp** en geef uw Mailchimp-referenties op.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Opslaan** om de verbinding te voltooien. 

## <a name="configure-the-connector"></a>De connector configureren

U kunt deze export configureren als u toegang hebt tot een verbinding van dit type. Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.

1. Ga naar **Gegevens**> **Exports**.

1. Selecteer **Bestemming toevoegen** om een nieuwe export te maken.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie Mailchimp. Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.

1. Voer uw **[Mailchimp-doelgroep-id](https://mailchimp.com/help/find-audience-id/)** in

3. Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant. 

1. Optioneel kunt u **Voornaam** en **Achternaam** exporteren om meer gepersonaliseerde e-mails te maken. Selecteer **Kenmerk toevoegen** om deze velden toe te wijzen.

1. Selecteer de segmenten die u wilt exporteren. U kunt in totaal tot 1 miljoen klantprofielen exporteren naar Mailchimp.

1. Selecteer **Opslaan**.

Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.

De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab). U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar Mailchimp te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat Mailchimp voldoet aan uw privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.
Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
