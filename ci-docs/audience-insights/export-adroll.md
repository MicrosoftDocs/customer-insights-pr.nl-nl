---
title: Customer Insights-gegevens exporteren naar AdRoll
description: Leer hoe u de verbinding configureert en exporteert naar AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dbebc3ee3978ca6ee9d1ad1c15c226479876709f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124359"
---
# <a name="export-segments-to-adroll-preview"></a>Segmenten exporteren naar AdRoll (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar AdRoll en gebruik ze voor advertenties. 

## <a name="prerequisites-for-a-connection"></a>Vereisten voor een verbinding

-   U hebt een [AdRoll-account](https://www.adroll.com/) en bijbehorende beheerdersreferenties nodig.
-   U hebt [geconfigureerde segmenten](segments.md) in doelgroepinzichten.
-   Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.

## <a name="known-limitations"></a>Bekende beperkingen

- U kunt in totaal tot 250.000 profielen per export exporteren naar AdRoll.
- U kunt geen segmenten met minder dan 100 profielen naar AdRoll exporteren. 
- Exporteren naar AdRoll is beperkt tot segmenten.
- Het exporteren van maximaal 250.000 profielen naar AdRoll kan tot 10 minuten duren. 
- Het aantal profielen dat u naar AdRoll kunt exporteren, is afhankelijk van uw contract met AdRoll.

## <a name="set-up-connection-to-adroll"></a>Verbinding met AdRoll instellen

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **AdRoll** om de verbinding te configureren.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.

1. Selecteer **Verbinden** om de verbinding met AdRoll te initialiseren.

1. Selecteer **Verifiëren met AdRoll** en geef uw beheerdersreferenties voor AdRoll op. 

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

U kunt deze export configureren als u toegang hebt tot een verbinding van dit type. Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Bestemming toevoegen** om een nieuwe export te maken.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie AdRoll. Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.

1. Voer uw **AdRoll-adverteerder-id** in. Zie [AdRoll-adverteerdersprofielen](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles) voor meer informatie.

3. Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant. Het is vereist om segmenten naar AdRoll te exporteren.

1. Selecteer de segmenten die u wilt exporteren. Selecteer een segment met minimaal 100 leden. U kunt geen kleinere segmenten exporteren. Bovendien is de maximale grootte van een te exporteren segment 250.000 leden per export. 

1. Selecteer **Opslaan**.

Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.

De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab). U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar AdRoll te verzenden, staat u de overdracht toe van gegevens buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat AdRoll voldoet aan uw privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.

Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.
