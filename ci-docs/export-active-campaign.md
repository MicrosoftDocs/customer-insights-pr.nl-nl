---
title: Gegevens uit Customer Insights exporteren naar ActiveCampaign
description: Leer hoe u de verbinding configureert en exporteert naar ActiveCampaign.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5d15b9bf7383d06070ac92d7a729fc6e6e00c9d7
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646214"
---
# <a name="export-segments-to-activecampaign-preview"></a>Segmenten exporteren naar ActiveCampaign (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar ActiveCampaign en gebruik ze voor marketingactiviteiten.

## <a name="prerequisites"></a>Vereisten

-   U hebt een [ActiveCampaign-account](https://www.activecampaign.com/) en bijbehorende beheerdersreferenties.
-   U hebt [segmenten geconfigureerd](segments.md) in Customer Insights.
-   Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld met een e-mailadres.

## <a name="known-limitations"></a>Bekende beperkingen

- U kunt per export tot 1 miljoen klantprofielen exporteren naar ActiveCampaign en dit kan tot 90 minuten duren.
- Het exporteren naar ActiveCampaign is beperkt tot segmenten.
- Het aantal klantprofielen dat u kunt exporteren naar ActiveCampaign, is afhankelijk van en wordt beperkt door uw contract met ActiveCampaign.

## <a name="set-up-connection-to-activecampaign"></a>Verbinding instellen met ActiveCampaign

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **ActiveCampaign** om de verbinding te configureren.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Standaard zijn dit alleen beheerders. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Voer uw [ActiveCampaign API-sleutel en hostnaam van REST-eindpunt](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) in. De hostnaam van het REST-eindpunt is alleen de hostnaam zonder https://. 

1. Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.

1. Selecteer **Verbinden** om de verbinding met ActiveCampaign te initialiseren.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

U kunt een export configureren als u toegang hebt tot een verbinding van dit type. Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Bestemming toevoegen** om een nieuwe export te maken.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie ActiveCampaign. Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.

1. Voer uw [**ActiveCampaign-lijst-id**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign) in.    

1. In de sectie **Gegevensvergelijking** selecteert u in het veld **E-mail** het veld dat het e-mailadres van een klant vertegenwoordigt. Dit is vereist voor het exporteren van segmenten naar ActiveCampaign. Optioneel kunt u voornaam, achternaam, en telefoon exporteren om meer gepersonaliseerde e-mails te maken. Selecteer Kenmerk toevoegen om deze velden toe te wijzen.

1. Selecteer **Opslaan**.

Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.

De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab). U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights inschakelt om gegevens te verzenden naar ActiveCampaign, staat u de overdracht van gegevens buiten de nalevingsgrens toe voor Dynamics 365 Customer Insights, inclusief mogelijk gevoelige gegevens zoals persoonsgegevens. Microsoft zal dergelijke gegevens in uw opdracht overdragen, maar u bent er zelf verantwoordelijk voor dat ActiveCampaign voldoet aan alle privacy- of beveiligingsverplichtingen die u hebt. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.

Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.
