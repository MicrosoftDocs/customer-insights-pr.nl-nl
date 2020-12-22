---
title: Systeemconfiguratie in doelgroepinzichten
description: Meer informatie over systeeminstellingen in Dynamics 365 Customer Insights-mogelijkheden voor doelgroepinzichten.
ms.date: 06/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: nimagen
manager: shellyha
ms.openlocfilehash: 7dd72e6512cd87ac70235d21667399298408db21
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405509"
---
# <a name="system-configuration"></a>Systeemconfiguratie

De pagina **Systeem** bevat vier tabbladen: **Status**, **Planning**, **Over** en **Algemeen**.

> [!div class="mx-imgBorder"]
> ![Systeempagina](media/system-tabs.png "Systeempagina")

## <a name="status-tab"></a>Tabblad Status

Met het **tabblad Status** kunt u de voortgang volgen van de opname van gegevens, gegevensexports en verschillende belangrijke productprocessen. Bekijk de informatie op dit tabblad om de volledigheid van actieve processen te garanderen.

Dit tabblad bevat statustabellen voor **Gegevensbronnen**, **Systeemprocessen** en **Gegevensvoorbereiding**. Elke tabel volgt de **naam** van de taak en de bijbehorende entiteit bij, de **status** van de meest recente uitvoering en het tijdstip in **Laatst bijgewerkt**.

Bekijk de details van de laatste verschillende uitvoeringen van de taak door de naam te selecteren.

### <a name="status-types"></a>Statustypen

Er zijn zes soorten status voor taken. De volgende statustypen worden ook weergegeven op de pagina's *Afstemming*, *Samenvoeging*, *Gegevensbronnen*, *Segmenten*, *Meetcriteria*, *Verrijking*, *Activiteiten* en *Voorspellingen*:

- **Verwerken:** taak wordt uitgevoerd. De status kan veranderen in Geslaagd of Mislukt.
- **Geslaagd:** taak is met succes afgerond.
- **Overgeslagen:** taak is overgeslagen. Een of meer van de downstreamprocessen waarvan deze taak afhankelijk is, mislukken of worden overgeslagen.
- **Mislukt:** verwerking van de taak is mislukt.
- **Geannuleerd:** de verwerking is geannuleerd door de gebruiker voordat deze is voltooid.
- **In wachtrij geplaatst:** de verwerking staat in de wachtrij en begint zodra alle downstreamtaken zijn voltooid. Zie [Vernieuwingsbeleid](#refresh-policies) voor meer informatie.

### <a name="refresh-policies"></a>Vernieuwingsbeleid

Deze lijst toont het vernieuwingsbeleid voor elk van de hoofdprocessen:

- **Gegevensbronnen:** wordt uitgevoerd volgens het [geconfigureerde schema](#schedule-tab). Hangt niet af van enig ander proces. Afstemmen is afhankelijk van de succesvolle afronding van dit proces.
- **Afstemming:** wordt uitgevoerd volgens het [geconfigureerde schema](#schedule-tab). Hangt af van de verwerking van de gegevensbronnen die worden gebruikt in de afstemmingsdefinitie. Samenvoeging is afhankelijk van de succesvolle afronding van dit proces.
- **Samenvoeging:** wordt uitgevoerd volgens het [geconfigureerde schema](#schedule-tab). Afhankelijk van de succesvolle afronding van het afstemmingsproces. Segmenten, meetcriteria, verrijking, zoeken, activiteiten, voorspellingen en gegevensvoorbereiding zijn afhankelijk van de succesvolle afronding van dit proces.
- **Segmenten**: wordt handmatig uitgevoerd (eenmalige vernieuwing) en volgens het [geconfigureerde schema](#schedule-tab). Afhankelijk van Samenvoeging. Inzichten zijn afhankelijk van de verwerking.
- **Meetcriteria**: wordt handmatig uitgevoerd (eenmalige vernieuwing) en volgens het [geconfigureerde schema](#schedule-tab). Afhankelijk van Samenvoeging.
- **Activiteiten**: wordt handmatig uitgevoerd (eenmalige vernieuwing) en volgens het [geconfigureerde schema](#schedule-tab). Afhankelijk van Samenvoeging.
- **Verrijking**: wordt handmatig uitgevoerd (eenmalige vernieuwing) en volgens het [geconfigureerde schema](#schedule-tab). Afhankelijk van Samenvoeging.
- **Zoeken**: wordt handmatig uitgevoerd (eenmalige vernieuwing) en volgens het [geconfigureerde schema](#schedule-tab). Afhankelijk van Samenvoeging.
- **Gegevensvoorbereiding:** wordt uitgevoerd volgens het [geconfigureerde schema](#schedule-tab). Afhankelijk van Samenvoeging.
- **Inzichten**: wordt handmatig uitgevoerd (eenmalige vernieuwing) en volgens het [geconfigureerde schema](#schedule-tab). Afhankelijk van Segmenten.

Selecteer de status van een taak om de voortgangsdetails te zien van de volledige taak waarin deze zich bevond. Het vernieuwingsbeleid hierboven kan helpen om te begrijpen wat u kunt doen om een taak met de status **Overgeslagen** of **In de wachtrij geplaatst** aan te pakken.

## <a name="schedule-tab"></a>Tabblad Planning

Gebruik het tabblad **Planning** tabblad om automatische vernieuwingen van al uw [opgenomen gegevensbronnen](data-sources.md) te plannen. Automatische vernieuwingen zorgen ervoor dat updates van uw gegevensbronnen worden weerspiegeld in uw geharmoniseerde klantprofielen.

1. Ga in doelgroepinzichten naar **Beheer** > **Systeem** en selecteer het tabblad **Planning**.

2. De standaardstatus voor de geplande vernieuwing is **Uit**. Als u geplande vernieuwingen wilt inschakelen, stelt u de schakelaar boven aan het scherm in op **Aan**.

3. Kies tussen **Wekelijks** (standaard) en **Dagelijks** vernieuwen. Als u wekelijkse vernieuwingen wilt plannen, selecteert u een of meer dagen waarop u de vernieuwing wilt uitvoeren.

4. Stel uw **tijdzone** in en gebruik daarna de vervolgkeuzelijst **Tijd** om uw vernieuwingstijd in te stellen. Als u gereed bent, selecteert u **Instellen**. Als u meerdere vernieuwingen op één dag wilt plannen, selecteert u **Een andere tijd toevoegen**.

5. Selecteer **Opslaan** om uw wijzigingen toe te passen.

## <a name="about-tab"></a>Tabblad Info

Het tabblad **Info** bevat de **weergavenaam** van uw organisatie, de actieve **omgevings-id**, de **regio** en uw **sessie-id**. Als u meer dan één werkomgeving hebt, moet u ze allemaal een gemakkelijk identificeerbare weergavenaam geven.

## <a name="general-tab"></a>Tabblad Algemeen

Er zijn twee opties op het tabblad **Algemeen**, namelijk **Taal** en **Indeling voor land/regio**.

De app [ondersteunt een aantal talen](supported-languages.md). Kies om uw voorkeurstaal te wijzigen een **taal** uit de dropdown.

Gebruik de vervolgkeuzelijst **Indeling voor land/regio** om de gewenste opmaak voor datums, tijd en cijfers te wijzigen. Onder dit veld wordt een opmaakvoorbeeld weergegeven. Het systeem stelt automatisch een keuze voor wanneer u een nieuwe taal kiest.

Selecteer **Opslaan** om uw selecties te bevestigen.

## <a name="api-usage-tab"></a>Tabblad API-gebruik

Vind details over het realtime API-gebruik en bekijk welke gebeurtenissen in een bepaald tijdsbestek hebben plaatsgevonden. Zie [Realtime gegevensopname](real-time-data-ingestion.md) voor meer informatie.
