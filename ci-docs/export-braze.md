---
title: Customer Insights-gegevens exporteren naar Braze
description: Ontdek hoe u de verbinding met Braze configureert en exporteert.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bfc9b34506dc3385b5edf12b31e74d05f2d20655
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646067"
---
# <a name="export-segment-lists-to-braze-preview"></a>Segmentlijsten exporteren naar Braze (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar Braze en gebruik deze voor marketingactiviteiten.

## <a name="prerequisites"></a>Vereisten

-   U beschikt over een [Braze-account](https://www.braze.com/) en bijbehorende beheerdersreferenties.
-   U hebt [segmenten geconfigureerd](segments.md) in Customer Insights.
-   Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld dat een e-mailadres en een Braze-klant-id vertegenwoordigt. 

## <a name="known-limitations"></a>Bekende beperkingen

- Exporteren naar Braze is beperkt tot segmenten.
- Het exporteren van tot 1 miljoen klantprofielen naar Braze kan tot 40 minuten duren. 
- Het aantal klantprofielen dat u kunt exporteren naar Braze, is afhankelijk van en wordt beperkt door uw contract met Braze.

## <a name="set-up-connection-to-braze"></a>Verbinding met Braze instellen

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Braze** om de verbinding te configureren.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Geef uw [Braze API-sleutel](https://www.braze.com/docs/api/basics/) op om door te gaan met aanmelden. 

1. Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.

1. Selecteer **Verbinden** om de verbinding met Braze te initialiseren.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

U kunt deze export configureren als u toegang hebt tot een verbinding van dit type. Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Bestemming toevoegen** om een nieuwe export te maken.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie Braze. Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.  

3. Selecteer in de sectie **Gegevensvergelijking**, in het veld **E-mail**, het veld dat het e-mailadres van een klant vertegenwoordigt. Selecteer vervolgens in het veld "Klant-id" het veld dat de Braze-id van de klant vertegenwoordigt. Dit is vereist om segmenten naar Braze te exporteren. De segmenten in Braze worden gemaakt met dezelfde naam voor het segment als in Dynamics 365 Customer Insights. U kunt aanvullende, optionele velden kiezen voor gegevensvergelijking. 

1. Selecteer **Opslaan**.

Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.

De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab). U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar Braze te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens in uw opdracht overdragen, maar het is uw verantwoordelijkheid ervoor te zorgen dat Braze voldoet aan eventuele privacy- of beveiligingsverplichtingen die u hebt. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.

Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.
