---
title: Systeemconfiguratie in doelgroepinzichten
description: Meer informatie over systeeminstellingen in Dynamics 365 Customer Insights-mogelijkheden voor doelgroepinzichten.
ms.date: 02/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 87bf8d7b9c23633ebdc929e15ac645c55cc21e4a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595374"
---
# <a name="system-configuration"></a>Systeemconfiguratie

De pagina **Systeem** bevat de volgende tabbladen:
- [Status](#status-tab)
- [Planning](#schedule-tab)
- [API-gebruik](#api-usage-tab)
- [Info](#about-tab)
- [Algemeen](#general-tab)

> [!div class="mx-imgBorder"]
> ![Systeempagina](media/system-tabs.png "Systeempagina")

## <a name="status-tab"></a>Tabblad Status

Op het tabblad **Status** kunt u de voortgang van gegevensopname, gegevensexport en verschillende andere belangrijke productprocessen volgen. Bekijk de informatie op dit tabblad om de volledigheid van actieve processen te garanderen.

Dit tabblad bevat tabellen met status- en verwerkingsinformatie voor verschillende processen. Elke tabel volgt de **naam** van de taak en de bijbehorende entiteit bij, de **status** van de meest recente uitvoering en het tijdstip in **Laatst bijgewerkt**.

Bekijk de details van de laatste verschillende uitvoeringen van de taak door de naam te selecteren.

### <a name="status-types"></a>Statustypen

Er zijn zes soorten status voor taken. De volgende statustypen worden ook weergegeven op de pagina's *Afstemming*, *Samenvoeging*, *Gegevensbronnen*, *Segmenten*, *Meetcriteria*, *Verrijking*, *Activiteiten* en *Voorspellingen*:

- **Verwerken:** taak wordt uitgevoerd. De status kan veranderen in Geslaagd of Mislukt.
- **Geslaagd:** taak is met succes afgerond.
- **Overgeslagen:** taak is overgeslagen. Een of meer van de downstreamprocessen waarvan deze taak afhankelijk is, mislukken of worden overgeslagen.
- **Mislukt:** verwerking van de taak is mislukt.
- **Geannuleerd:** de verwerking is geannuleerd door de gebruiker voordat deze is voltooid.
- **In de wachtrij**: de verwerking wordt in de wachtrij geplaatst en begint zodra alle upstream-taken zijn voltooid. Zie [Vernieuwingsbeleid](#refresh-policies) voor meer informatie.

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

Vind details over het realtime API-gebruik en kijk welke gebeurtenissen hebben plaatsgevonden in een bepaald tijdsbestek. U kiest het tijdsbestek in het vervolgkeuzemenu **Een tijdsbestek selecteren**. 

**API-gebruik** bevat drie secties: 
- **API-aanroepen**: een grafiek die het geaggregeerde aantal aanroepen naar de API in het geselecteerde tijdsbestek visualiseert.

- **Gegevensoverdracht**: - een grafiek die de hoeveelheid gegevens toont die via de API zijn overgedragen in het geselecteerde tijdsbestek.

-  **Bewerkingen**: een tabel met rijen voor elke beschikbare API-bewerking en details over het gebruik van de bewerkingen. U kunt een bewerkingsnaam selecteren om naar [de API-verwijzing](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances)​te gaan.

   Bewerkingen die gebruikmaken van [realtime gegevensopname](real-time-data-ingestion.md) bevatten een knop met een verrekijkersymbool om realtime API-gebruik te bekijken. Selecteer de knop om een deelvenster aan de zijkant te openen met gebruiksdetails voor het realtime API-gebruik in de huidige omgeving.   
   Gebruik het vak **Groeperen op** in het deelvenster **Realtime API-gebruik** om te kiezen hoe u uw realtime interacties het best kunt presenteren. U kunt de gegevens groeperen op API-methode, entiteit gekwalificeerde naam (opgenomen entiteit), gemaakt door (bron van de gebeurtenis), resultaat (succes of mislukking) of foutcodes. De gegevens zijn beschikbaar als geschiedenisdiagram en als tabel.


[!INCLUDE[footer-include](../includes/footer-banner.md)]