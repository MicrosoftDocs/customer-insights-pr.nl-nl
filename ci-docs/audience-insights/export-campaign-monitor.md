---
title: Customer Insights-gegevens exporteren naar Campaign Monitor
description: Leer hoe u de verbinding configureert en exporteert naar Campaign Monitor.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: be9c92a087ab4664077d18fe8585bf96715c1535
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228147"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Segmenten exporteren naar Campaign Monitor (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar Campaign Monitor en gebruik deze voor marketingactiviteiten.

## <a name="prerequisites"></a>Vereisten

-   U hebt een [Campaign Monitor-account](https://www.campaignmonitor.com/) en bijbehorende beheerdersreferenties.
-   U hebt [geconfigureerde segmenten](segments.md) in doelgroepinzichten.
-   Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.

## <a name="known-limitations"></a>Bekende beperkingen

- U kunt tot 1 miljoen klantprofielen per export exporteren naar Campaign Monitor.
- Exporteren naar Campaign Monitor is beperkt tot segmenten.
- Het exporteren van tot 1 miljoen klantprofielen naar Campaign Monitor kan tot 20 minuten duren. 
- Het aantal klantprofielen dat u kunt exporteren naar Campaign Monitor, is afhankelijk van en wordt beperkt door uw contract met Campaign Monitor.

## <a name="set-up-connection-to-campaign-monitor"></a>Verbinding instellen met Campaign Monitor

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Campaign Monitor** om de verbinding te configureren.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.

1. Selecteer **Verbinden** om de verbinding met Campaign Monitor te initialiseren.

1. Selecteer **Verifiëren met Campaign Monitor** en geef uw beheerdersreferenties voor Campaign Monitor op.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

U kunt deze export configureren als u toegang hebt tot een verbinding van dit type. Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Bestemming toevoegen** om een nieuwe export te maken.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie Campaign Monitor. Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.

1. Voer uw [**lijst-id van Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id) in.    
   [Genereer de API-sleutel](https://www.campaignmonitor.com/api/getting-started/) van **Accountinstellingen** in Campaign Monitor om de API-lijst-id te bekijken.  

1. In de sectie **Gegevensvergelijking** selecteert u in het veld **E-mail** het veld dat het e-mailadres van een klant vertegenwoordigt. Deze is vereist voor het exporteren van segmenten naar Campaign Monitor.

1. Selecteer **Opslaan**.

Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.

De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab). U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights inschakelt om gegevens naar Campaign Monitor te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, inclusief mogelijk gevoelige gegevens zoals persoonsgegevens. Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent er verantwoordelijk voor dat Campaign Monitor voldoet aan mogelijke privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.

Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.
