---
title: Customer Insights-gegevens exporteren naar Mailchimp
description: Leer hoe u de verbinding configureert en exporteert naar Mailchimp.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f7a33f2eddb6b625ddb8663b97103de75beab44c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226840"
---
# <a name="export-segments-to-mailchimp-preview"></a>Segmenten exporteren naar Mailchimp (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar Mailchimp om nieuwsbrieven en e-mailcampagnes te maken.

## <a name="prerequisites-for-connection"></a>Vereisten voor verbinding

-   U hebt een [Mailchimp-account](https://mailchimp.com/) en bijbehorende beheerdersreferenties nodig.
-   Er zijn bestaande doelgroepen met bijbehorende id's in Mailchimp. Zie [Mailchimp-doelgroepen](https://mailchimp.com/help/create-audience/) voor meer informatie.
-   U hebt [geconfigureerde segmenten](segments.md)
-   Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.

## <a name="known-limitations"></a>Bekende beperkingen

- Tot 1 miljoen klantprofielen per export naar Mailchimp.
- Exporteren naar Mailchimp is beperkt tot segmenten.
- Het exporteren van segmenten met 1 miljoen klantprofielen kan tot drie uur duren. 
- Het aantal klantprofielen dat u kunt exporteren naar Mailchimp, is afhankelijk van en wordt beperkt door uw contract met Mailchimp.

## <a name="set-up-connection-to-mailchimp"></a>Verbinding instellen met Mailchimp

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Mailchimp** om de verbinding te configureren.

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

1. In de sectie **Gegevensvergelijking** selecteert u in het veld **E-mail** het veld dat het e-mailadres van een klant vertegenwoordigt. 

1. Optioneel kunt u **Voornaam** en **Achternaam** exporteren om meer gepersonaliseerde e-mails te maken. Selecteer **Kenmerk toevoegen** om deze velden toe te wijzen.

1. Selecteer de segmenten die u wilt exporteren. U kunt in totaal tot 1 miljoen klantprofielen exporteren naar Mailchimp.

1. Selecteer **Opslaan**.

Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.

De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab). U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar Mailchimp te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat Mailchimp voldoet aan uw privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.
Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
