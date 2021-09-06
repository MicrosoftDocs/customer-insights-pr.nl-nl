---
title: Customer Insights-gegevens exporteren naar Microsoft Advertising
description: Leer hoe u de verbinding configureert en exporteert naar Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8f8a4cbb9590f9c5311789154319283530e0a10343cccbe9c7aec99765b4fbf2
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031453"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Segmenten exporteren naar Microsoft Advertising (preview)

Exporteer Customer Insights-segmenten naar Microsoft Advertising om doelgroepen met overeenkomende klanten te maken. Gebruik deze doelgroepen voor uw advertentiecampagnes.

## <a name="prerequisites"></a>Vereisten

-   Een [Microsoft Advertising-account](https://ads.microsoft.com/) en bijbehorende beheerdersreferenties.
-   U hebt de gebruiksvoorwaarden voor klantenafstemming geaccepteerd. 
-   [Geconfigureerde segmenten](segments.md) in doelgroepinzichten.
-   Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld met een e-mailadres.

## <a name="known-limitations"></a>Bekende beperkingen

- U kunt maximaal 500.000 profielen per export exporteren naar Microsoft Advertising.
- Exporteren naar Microsoft Advertising is beperkt tot segmenten.
- Het exporteren van maximaal 500.000 profielen naar Microsoft Advertising kan tot 10 minuten duren. 


## <a name="set-up-the-connection-to-microsoft-advertising"></a>De verbinding met Microsoft Advertising instellen

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Microsoft Advertising** om de verbinding te configureren.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. De standaardoptie is beheerders. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.

1. Selecteer **Verbinden** om de verbinding met Microsoft Advertising te initialiseren.

1. Selecteer **Verifiëren met Microsoft Advertising** en geef uw beheerdersreferenties voor Microsoft Advertising op.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

U kunt deze export configureren als u toegang hebt tot een verbinding van dit type. Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Bestemming toevoegen** om een nieuwe export te maken.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie Microsoft Advertising. Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.

1. Selecteer de segmenten die moeten worden geëxporteerd. De doelgroepen met overeenkomende klanten in Microsoft Advertising worden automatisch gemaakt met de naam van de segmenten die zijn geselecteerd voor export. Elk segment resulteert in een afzonderlijke doelgroep met overeenkomende klanten. 

1. Voer uw **klant-id en account-id voor Microsoft Advertising** in. U vindt de klant-id (`cid`) en account-id (`aid`) in de parameters van de URL wanneer u bent aangemeld bij Microsoft Advertising.

1. Selecteer in het veld **E-mail** van de sectie **Gegevensvergelijking** het veld in uw geharmoniseerde klantprofiel met het e-mailadres van een klant. Dit is vereist voor het exporteren van segmenten naar Microsoft Advertising.

1. Selecteer **Opslaan**.

Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.

De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab). U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights inschakelt om gegevens naar Microsoft Advertising te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, inclusief mogelijk gevoelige gegevens zoals persoonsgegevens. Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent er verantwoordelijk voor dat Microsoft Advertising voldoet aan mogelijke privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.

Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.
