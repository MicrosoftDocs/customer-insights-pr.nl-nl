---
title: Gegevens uit Customer Insights exporteren naar Klaviyo
description: Leer hoe u de verbinding configureert en exporteert naar Klaviyo.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 027aee70d9fdab0a92d7fd99209a6ac2ca3cc361
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225446"
---
# <a name="export-segment-lists-to-klaviyo-preview"></a>Segmentlijsten exporteren naar Klaviyo (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar Klaviyo en gebruik ze voor marketingactiviteiten.

## <a name="prerequisites"></a>Vereisten

-   U hebt een [Klaviyo-account](https://www.klaviyo.com/) en bijbehorende beheerdersreferenties.
-   U hebt [geconfigureerde segmenten](segments.md) in doelgroepinzichten.
-   Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.

## <a name="known-limitations"></a>Bekende beperkingen

- U kunt tot 100.000 klantprofielen per export exporteren naar Klaviyo.
- Het exporteren naar Klaviyo is beperkt tot segmenten.
- Het exporteren van tot 1 miljoen klantprofielen naar Klaviyo kan tot 20 minuten duren. 
- Het aantal klantprofielen dat u kunt exporteren naar Klaviyo, is afhankelijk van en wordt beperkt door uw contract met Klaviyo.

## <a name="set-up-connection-to-klaviyo"></a>De verbinding met Klaviyo instellen

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Klaviyo** om de verbinding te configureren.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Geef uw [Klaviyo API-sleutel](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys) op om door te gaan met aanmelden. 

1. Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.

1. Selecteer **Verbinden** om de verbinding met Klaviyo te initialiseren.

1. Selecteer **Verifiëren met Klaviyo** en geef uw beheerdersreferenties op voor Klaviyo.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

U kunt deze export configureren als u toegang hebt tot een verbinding van dit type. Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Bestemming toevoegen** om een nieuwe export te maken.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie Klaviyo. Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.

1. Voer uw [**Klaviyo-lijst-id**](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID) in.     

3. In de sectie **Gegevensvergelijking** selecteert u in het veld **E-mail** het veld dat het e-mailadres van een klant vertegenwoordigt. Dit is vereist voor het exporteren van segmenten naar Klaviyo.

1. Selecteer **Opslaan**.

Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.

De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab). U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights inschakelt om gegevens te verzenden naar Klaviyo, staat u de overdracht van gegevens buiten de nalevingsgrens toe voor Dynamics 365 Customer Insights, inclusief mogelijk gevoelige gegevens zoals persoonsgegevens. Microsoft zal dergelijke gegevens in uw opdracht overdragen, maar u bent er zelf verantwoordelijk voor dat Klaviyo voldoet aan alle privacy- of beveiligingsverplichtingen die u hebt. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.

Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.
