---
title: Customer Insights-gegevens exporteren naar LinkedIn Ads
description: Procedure voor het configureren van de verbinding en voor het exporteren naar LinkedIn Ads.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124476"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Segmenten exporteren naar LinkedIn Ads (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar LinkedIn Ads om matched audiences te maken. Gebruik de matched audiences voor de targeting van bedrijven en contactpersonen.

## <a name="prerequisites"></a>Vereisten

-   U hebt een [LinkedIn Campaign Manager-account](https://business.linkedin.com/marketing-solutions/ads) en bijbehorende beheerdersreferenties.
-   U hebt [geconfigureerde segmenten](segments.md) in doelgroepinzichten.
-   Klantprofielen in de geëxporteerde segmenten bevatten een veld met een e-mailadres.

## <a name="known-limitations"></a>Bekende beperkingen

- U kunt maximaal 100.000 profielen per export exporteren naar LinkedIn Ads.
- Exporteren naar LinkedIn Ads is beperkt tot segmenten.
- Het exporteren van maximaal 100.000 profielen naar LinkedIn Ads kan tot 10 minuten duren. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>De verbinding instellen met LinkedIn Ads

1. Ga in doelgroepinzichten naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **LinkedIn Ads** om de verbinding te configureren.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Als u geen actie onderneemt, wordt beheerders gebruikt als standaardoptie. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Geef uw [LinkedIn Campaign Manager-account-id](https://www.linkedin.com/help/lms/answer/a424270) op.

1. Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.

1. Selecteer **Verbinden** om de verbinding met Campaign Monitor te initialiseren.

1. Selecteer **Verifiëren met LinkedIn** en geef uw beheerdersreferenties voor LinkedIn Campaign Manager op.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

U kunt een export configureren als u toegang hebt tot een verbinding van dit type. Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Bestemming toevoegen** om een nieuwe export te maken.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie LinkedIn Ads. Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.

1. Kies of u gegevens wilt exporteren om [targeting van contactpersonen](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) of [targeting van bedrijve](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) uit te voeren op LinkedIn. 

1. Selecteer in de sectie **Gegevensvergelijking** het veld in uw geharmoniseerde klantprofiel dat het e-mailadres van een klant vertegenwoordigt. Dit is vereist voor het exporteren van segmenten naar LinkedIn Ads.

1. Selecteer de segmenten die u wilt exporteren. De matched audiences in LinkedIn Campaign Manager worden automatisch gemaakt met de naam van de segmenten die u hebt geselecteerd om te exporteren. Elk segment resulteert in een aparte matched audience. 

1. Selecteer **Opslaan**.

Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.

De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab). U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights inschakelt om gegevens naar LinkedIn Ads te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, inclusief mogelijk gevoelige gegevens zoals persoonsgegevens. Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent er verantwoordelijk voor dat LinkedIn Ads voldoet aan mogelijke privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.

Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.
