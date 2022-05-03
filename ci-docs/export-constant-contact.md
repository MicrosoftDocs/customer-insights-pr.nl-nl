---
title: Customer Insights-gegevens exporteren naar Constant Contact
description: Leer hoe u de verbinding configureert en exporteert naar Constant Contact.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 310de0355f71829346f0e35508487e5962d6e912
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646384"
---
# <a name="export-segments-to-constant-contact-preview"></a>Segmenten exporteren naar Constant Contact (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar Constant Contact en gebruik deze voor marketingactiviteiten. 

## <a name="prerequisites-for-a-connection"></a>Vereisten voor een verbinding

-   U hebt een [Constant Contact-account](https://www.constantcontact.com/account-home) en bijbehorende beheerdersreferenties.
-   U hebt [segmenten geconfigureerd](segments.md) in Customer Insights.
-   Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.

## <a name="known-limitations"></a>Bekende beperkingen

- U kunt tot 1 miljoen klantprofielen per export exporteren naar Constant Contact.
- Exporteren naar Constant Contact is beperkt tot segmenten.
- Het exporteren van tot 1 miljoen klantprofielen naar Constant Contact kan tot 1 uur duren. 
- Het aantal klantprofielen dat u kunt exporteren naar Constant Contact, is afhankelijk van en wordt beperkt door uw contract met Constant Contact.

## <a name="set-up-connection-to-constant-contact"></a>Verbinding instellen met Constant Contact

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Constant Contact** om de verbinding te configureren.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.

1. Selecteer **Verbinden** om de verbinding met Constant Contact te initialiseren.

1. Selecteer **Verifiëren met Constant Contact** en geef uw beheerdersreferenties op voor Constant Contact. 

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

U kunt deze export configureren als u toegang hebt tot een verbinding van dit type. Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Bestemming toevoegen** om een nieuwe export te maken.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie Constant Contact. Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.

1. Enter your [**Id van Constant Contact-lijst**](https://app.constantcontact.com/pages/contacts/ui#lists) in. Open een lijst in Constant Contact om de lijst-id in de URL te vinden.

1. In de sectie **Gegevensvergelijking** selecteert u in het veld **E-mail** het veld dat het e-mailadres van een klant vertegenwoordigt. Deze is vereist voor het exporteren van segmenten naar Constant Contact.

1. Optioneel kunt u Voornaam en Achternaam exporteren als extra velden om meer gepersonaliseerde e-mails te maken. Selecteer **Kenmerk toevoegen** om deze velden toe te wijzen.

1. Selecteer de segmenten die u wilt exporteren.

1. Selecteer **Opslaan**.

Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.

De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab). U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights inschakelt om gegevens naar Constant Contact te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, inclusief mogelijk gevoelige gegevens zoals persoonsgegevens. Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent er verantwoordelijk voor dat Constant Contact voldoet aan mogelijke privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.

Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.