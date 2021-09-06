---
title: Customer Insights-gegevens exporteren naar Snapchat
description: Leer hoe u de verbinding configureert en exporteert naar Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 421dcd5ba5421597cf9dea71a9f9f25c7972a4f26fb49d4b042f8667a317ab5d
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033395"
---
# <a name="export-segments-to-snapchat-preview"></a>Segmenten exporteren naar Snapchat (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar Snapchat en gebruik deze voor reclame. 

## <a name="prerequisites-for-a-connection"></a>Vereisten voor een verbinding

-   Je hebt een [zakelijk Snapchat-account](https://business.snapchat.com/), een [Snapchat Ads-account](https://ads.snapchat.com/) en de bijbehorende beheerdersreferenties.
-   U hebt [geconfigureerde segmenten](segments.md) in doelgroepinzichten.
-   Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.

## <a name="known-limitations"></a>Bekende beperkingen

- Exporteren naar Snapchat is beperkt tot segmenten.
- Het exporteren van maximaal 1 miljoen profielen naar Snapchat kan tot 15 minuten duren. 

## <a name="set-up-connection-to-snapchat"></a>Verbinding instellen met Snapchat

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Snapchat** om de verbinding te configureren.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.

1. Selecteer **Verbinden** om de verbinding met Snapchat te initialiseren.

1. Selecteer **Verifiëren met Snapchat** en geef uw beheerdersreferenties voor Snapchat op. 

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

U kunt deze export configureren als u toegang hebt tot een verbinding van dit type. Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Bestemming toevoegen** om een nieuwe export te maken.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie Snapchat. Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.

1. Voer de [**Snapchat-doelgroep-id**](https://businesshelp.snapchat.com/s/article/custom-audiences) in.

1. Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant. Deze is vereist voor het exporteren van segmenten naar Snapchat.

1. Selecteer de segmenten die u wilt exporteren. 

1. Selecteer **Opslaan**.

Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.

De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab). U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights inschakelt om gegevens naar Snapchat te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, inclusief mogelijk gevoelige gegevens zoals persoonsgegevens. Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent er verantwoordelijk voor dat Snapchat voldoet aan mogelijke privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.

Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.
