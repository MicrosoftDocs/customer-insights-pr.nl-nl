---
title: Realtime gegevensopname en beperkingen
description: Algemene informatie over realtime mogelijkheden in doelgroepinzichten.
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00a72e6a67e33c8e70ccc6139c5e62020f9d3e1
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689169"
---
# <a name="real-time-data-ingestion-preview"></a>Realtime gegevensopname (preview)

Dankzij de bijna-realtime functionaliteit kunt u binnen enkele seconden de meest recente interacties zien die uw klanten hebben gehad met uw producten of services.

[Geplande vernieuwingen](system.md#schedule-tab) omvatten grote aantallen records en verschillende complexe bewerkingen. Eerst worden gegevens opgehaald uit de gegevensbron. Vervolgens worden de gegevens geharmoniseerd en vervolgens verrijkt met aanvullende informatie. Elke uitvoering van dit proces kan minuten tot uren duren.

De realtime functionaliteit levert gegevens onmiddellijk op voor verbruik, totdat de volgende geplande vernieuwing deze gegevens uit de gegevensbron haalt.

Realtime updates hebben een vervaltijd waarna ze de waarde in de gegevensbron niet langer overschrijven:

- Profielupdates worden 4 uur bewaard
- Activiteiten worden 30 dagen bewaard

Deze waarden zijn API-aanroepparameters die u kunt wijzigen. Zij hebben tot doel ervoor te zorgen dat uw brongegevens uw bron van waarheid blijven. Als u wilt dat realtime updates langer worden opgenomen, moet u ze toevoegen aan een gegevensbron, zodat ze worden opgehaald tijdens de volgende geplande vernieuwing.

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a>Realtime update van de geharmoniseerde klantprofielvelden

Bijgewerkte profielen worden binnen enkele seconden weergegeven in de klantenkaartweergave of in een andere visualisatie.

Omdat realtime bewerkingen plaatsvinden nadat de gegevensharmonisatie heeft plaatsgevonden, zijn ze alleen van toepassing op de geharmoniseerde klantprofielen. Bijgevolg worden met realtime profielwijzigingen geen meetcriteria, het lidmaatschap van segmenten of verrijkingen worden bijgewerkt.

### <a name="limitations"></a>Beperkingen

- Klantprofielen kunnen worden bijgewerkt, maar niet gemaakt of verwijderd.
- Het exporteren van realtime updates naar externe systemen, zoals Power BI, is momenteel niet mogelijk.

## <a name="real-time-creation-of-activities"></a>In realtime activiteiten maken

Met de realtime API kunt u een nieuwe activiteit van uw bronsysteem (een individueel bronrecord) naar een geharmoniseerd klantprofiel publiceren. De nieuwe activiteit zal binnen enkele seconden beschikbaar zijn als een geharmoniseerde activiteit in de tijdlijn van dat geharmoniseerde klantprofiel. U kunt de tijdlijn zien in de klantenkaartweergave of een andere tijdlijnintegratie die u hebt geconfigureerd.

> [!NOTE]
>
> - Activiteiten zijn onveranderlijk. Zij veranderen niet nadat ze zijn gemaakt.
> - Momenteel worden segmenten en meetcriteria niet bijgewerkt op basis van de nieuwe activiteit.
> - Activiteiten die alleen zijn toegevoegd via de realtime API, maken geen deel uit van exports en worden niet weergegeven in PowerBI.

Er zijn twee manieren om verbinding te maken met de realtime API:

- [indirect](#connect-via-the-dynamics-365-customer-insights-connector), door gebruik te maken van de [Dynamics 365 Customer Insights-connector](https://docs.microsoft.com/connectors/customerinsights/)
- [direct](#connect-directly-to-the-real-time-api), met code

Voor beide manieren gelden de volgende vereisten:

- Een Customer Insights-omgeving
- Geharmoniseerde klantprofielen
- Activiteiten die zijn geconfigureerd en uitgevoerd
- Inzenders- of beheerdersmachtigingen om uw account te verifiëren

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>Verbinding maken via de Dynamics 365 Customer Insights-connector

De realtime API kan gegevens opnemen van een specifieke Power Platform-connector, de [Dynamics 365 Customer Insights-connector](https://docs.microsoft.com/connectors/customerinsights/), zonder dat u code hoeft te schrijven en te implementeren.    
De connector kan dezelfde realtime acties uitvoeren als de API. Voor premium connectors hebt u een geldige licentie nodig. Zie [Veelgestelde vragen over Power Apps- en Power Automate-licenties](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq) voor meer informatie.

- Power Platform [Power Apps en/of Power Automate](https://docs.microsoft.com/connectors/)
- Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)

Zie de [Power Automate-documentatie](https://docs.microsoft.com/power-automate/) voor meer informatie over het maken van stromen.

## <a name="connect-directly-to-the-real-time-api"></a>Rechtstreeks verbinding maken met de realtime API

U kunt de realtime mogelijkheden gebruiken door uw eigen pijplijn te bouwen en rechtstreeks verbinding te maken met de realtime API.    
U kunt een activiteit plaatsen in de indeling van uw bronsysteem of in de UnifiedActivity-indeling. Verkrijg de indeling door een API-aanroep uit te voeren naar /api/instances/{instanceId}/manage/entities/UnifiedActivity.

Details van deze API, inclusief parameters en reacties, zijn te vinden in de sectie **EntityData** sectie in de [Referentie voor Customer Insights-API's](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Zie [Werken met Customer Insights-API's](apis.md) voor meer informatie.

## <a name="understand-your-real-time-usage-with-telemetry"></a>Inzicht in uw realtime gebruik krijgen met telemetrie

Krijg een overzicht van het aantal aanvragen aan bij realtime API en informatie over problemen die het systeem kan tegenkomen. U kunt [toegang krijgen tot de realtime telemetrie](system.md#api-usage-tab) door naar **Beheerder** > **Systeem** > **API-gebruik** te gaan. In de tabel **Activiteiten** bevatten rijen voor API-bewerkingen die de realtime methoden gebruiken, een knop om realtime API-gebruik te bekijken. De knop wordt weergegeven met een verrekijkersymbool. Selecteer de knop om een deelvenster aan de zijkant te openen met gebruiksdetails voor het realtime API-gebruik in de huidige omgeving.

Gebruik de selectie **Groeperen op** om te kiezen hoe u uw realtime interacties het beste kunt presenteren op een tijdlijn die varieert van de afgelopen 24 uur tot de afgelopen 30 dagen. U kunt de gegevens groeperen op API-methode, entiteit gekwalificeerde naam (opgenomen entiteit), gemaakt door (bron van de gebeurtenis), resultaat (succes of mislukking) of foutcodes. De gegevens zijn beschikbaar als geschiedenisdiagram en als tabel.