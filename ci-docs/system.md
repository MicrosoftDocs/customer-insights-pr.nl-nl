---
title: Systeemconfiguratie
description: Meer informatie over systeeminstellingen in Dynamics 365 Customer Insights.
ms.date: 04/21/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-schedule
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 0ef84d8e286d8135eb8938e72f1319925e948bed
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9050665"
---
# <a name="system-configuration"></a>Systeemconfiguratie

Om toegang te krijgen tot systeemconfiguraties, ga naar **Beheerder** > **Systeem** om een lijst met systeemtaken en -processen te bekijken.

De pagina **Systeem** bevat de volgende tabbladen:
- [-Status](#status-tab)
- [Planning](#schedule-tab)
- [API-gebruik](#api-usage-tab)
- [Info](#about-tab)
- [Algemeen](#general-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Tabblad Instellingen op de systeempagina.":::

## <a name="status-tab"></a>Tabblad Status

Op het tabblad **Status** kunt u de voortgang van taken, gegevensopname, gegevensexport en verschillende andere belangrijke productprocessen volgen. Bekijk de informatie op dit tabblad om de volledigheid van uw actieve taken en processen te waarborgen.

Dit tabblad bevat tabellen met status- en verwerkingsinformatie voor verschillende processen. Elke tabel volgt de **naam** van de taak en de bijbehorende entiteit bij, de **status** van de meest recente uitvoering en het tijdstip in **Laatst bijgewerkt**. U kunt de details van de laatste paar uitvoeringen bekijken door de taak- of procesnaam te selecteren. 

Selecteer de status naast de taak of het proces in de kolom **Status** om het deelvenster **Details van voortgang** te openen.

   :::image type="content" source="media/system-progress-details.png" alt-text="Deelvenster met details van systeemvoortgang":::

### <a name="status-definitions"></a>Statusdefinities

Het systeem gebruikt de volgende statussen voor taken en processen:

|-Status  |Definitie  |
|---------|---------|
|Geannuleerd |De verwerking is door de gebruiker geannuleerd voordat deze is voltooid.   |
|Mislukt   |Er zijn fouten opgetreden bij de gegevensopname.         |
|Mislukking  |De verwerking is mislukt.  |
|Niet gestart   |De gegevensbron heeft nog geen gegevens opgenomen of bevindt zich nog in de conceptmodus.         |
|Verwerking  |De taak of het proces wordt uitgevoerd.  |
|Vernieuwen    |De opname van gegevens wordt uitgevoerd. U kunt deze bewerking annuleren door **Stoppen met vernieuwen** te selecteren in de kolom **Acties**. Als u het vernieuwen van een gegevensbron stopt, keert het terug naar de laatste vernieuwingsstatus.       |
|Overgeslagen  |De taak of het proces is overgeslagen. Een of meer van de downstreamprocessen waarvan deze taak afhankelijk is, mislukken of worden overgeslagen.|
|Geslaagd  |De taak of het proces is voltooid. Geeft voor gegevensbronnen aan dat de gegevens zijn opgenomen als een tijd wordt vermeld in de kolom **Vernieuwd**.|
|In wachtrij geplaatst | De verwerking wordt in de wachtrij geplaatst en start zodra alle upstreamtaken en -processen zijn voltooid. Zie voor meer informatie [Processen vernieuwen](#refresh-processes).|

### <a name="refresh-processes"></a>Processen vernieuwen

Vernieuwen voor taken en processen wordt uitgevoerd volgens het [geconfigureerde schema](#schedule-tab). 

|Proces  |Beschrijving  |
|---------|---------|
|Activiteit  |Wordt handmatig uitgevoerd (eenmalig vernieuwen). Afhankelijk van het samenvoegproces. Inzichten zijn afhankelijk van de verwerking.|
|Analyse koppelen |Wordt handmatig uitgevoerd (eenmalig vernieuwen). Afhankelijk van segmenten.  |
|Voorbereiding van analyse |Wordt handmatig uitgevoerd (eenmalig vernieuwen). Afhankelijk van segmenten.  |
|Gegevensvoorbereiding   |Heeft een entiteit nodig om op te draaien. Gegevensbronentiteiten zijn afhankelijk van opname. Verrijkte entiteiten zijn afhankelijk van verrijkingen. De entiteit Klant is afhankelijk van samenvoeging.  |
|Gegevensbronnen   |Hangt niet af van enig ander proces. Afstemmen is afhankelijk van de succesvolle afronding van dit proces.  |
|Verrijkingen   |Wordt handmatig uitgevoerd (eenmalig vernieuwen). Afhankelijk van het samenvoegproces. |
|Exportbestemmingen |Wordt handmatig uitgevoerd (eenmalig vernieuwen). Afhankelijk van segmenten.  |
|Inzichten |Wordt handmatig uitgevoerd (eenmalig vernieuwen). Afhankelijk van segmenten.  |
|Intelligentie   |Afhankelijk van samenvoeging.   |
|Vergelijken |Hangt af van de verwerking van de gegevensbronnen die worden gebruikt in de afstemmingsdefinitie.      |
|Meetcriteria  |Wordt handmatig uitgevoerd (eenmalig vernieuwen). Afhankelijk van het samenvoegproces.  |
|Samenvoeging   |Afhankelijk van de succesvolle afronding van het afstemmingsproces. Segmenten, meetcriteria, verrijking, zoeken, activiteiten, voorspellingen en gegevensvoorbereiding zijn afhankelijk van de succesvolle afronding van dit proces.   |
|Profielen   |Wordt handmatig uitgevoerd (eenmalig vernieuwen). Afhankelijk van het samenvoegproces. |
|Zoeken   |Wordt handmatig uitgevoerd (eenmalig vernieuwen). Afhankelijk van het samenvoegproces. |
|Segmenten  |Wordt handmatig uitgevoerd (eenmalig vernieuwen). Afhankelijk van het samenvoegproces. Inzichten zijn afhankelijk van de verwerking.|
|System   |Afhankelijk van de succesvolle afronding van het afstemmingsproces. Segmenten, meetcriteria, verrijking, zoeken, activiteiten, voorspellingen en gegevensvoorbereiding zijn afhankelijk van de succesvolle afronding van dit proces.   |
|Gebruiker  |Wordt handmatig uitgevoerd (eenmalig vernieuwen). Is afhankelijk van entiteiten.  |

Selecteer de status van een proces om de voortgangsdetails te zien van de volledige taak waarin het zich bevond. De bovenstaande vernieuwingsprocessen kunnen helpen om te begrijpen wat u kunt doen met een taak of proces met de status **Overgeslagen** of **In wachtrij geplaatst**.

## <a name="schedule-tab"></a>Tabblad Planning

Gebruik het tabblad **Planning** tabblad om automatische vernieuwingen van al uw [opgenomen gegevensbronnen](data-sources.md) te plannen. Automatische vernieuwingen zorgen ervoor dat updates van uw gegevensbronnen worden weerspiegeld in uw geharmoniseerde klantprofielen.

> [!NOTE]
> Door u beheerde gegevensbronnen worden vernieuwd volgens hun eigen schema. Om het vernieuwen van door u beheerde gegevensbronnen te plannen, configureert u de vernieuwingsinstellingen op die specifieke gegevensbron vanuit de pagina **Gegevensbronnen**.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Instellingen voor vernieuwen van gegevensstromen.":::

1. Ga naar **Beheer** > **Systeem** en selecteer het tabblad **Planning**.

2. De standaardstatus voor de geplande vernieuwing is **Uit**. Als u geplande vernieuwingen wilt inschakelen, stelt u de schakelaar boven aan het scherm in op **Aan**.

3. Kies tussen **Wekelijks** (standaard) en **Dagelijks** vernieuwen. Als u wekelijkse vernieuwingen wilt plannen, selecteert u een of meer dagen waarop u de vernieuwing wilt uitvoeren.

4. Stel uw **tijdzone** in en gebruik daarna de vervolgkeuzelijst **Tijd** om uw vernieuwingstijd in te stellen. Als u gereed bent, selecteert u **Instellen**. Als u meerdere vernieuwingen op één dag wilt plannen, selecteert u **Een andere tijd toevoegen**.

5. Selecteer **Opslaan** om uw wijzigingen toe te passen.

## <a name="about-tab"></a>Tabblad Info

Het tabblad **Info** bevat de **weergavenaam** van uw organisatie, de actieve **omgevings-id**, de **regio** en uw **sessie-id**. Als u meer dan één werkomgeving hebt, moet u ze allemaal een gemakkelijk identificeerbare weergavenaam geven.

## <a name="general-tab"></a>Tabblad Algemeen

U kunt de taal en de indeling voor land/regio wijzigen op het tabblad **Algemeen**.

Customer Insights [ondersteunt vele talen](/dynamics365/get-started/availability). De app gebruikt uw taalvoorkeur om elementen als het menu, labeltekst en systeemberichten in uw voorkeurstaal weer te geven.

Geïmporteerde gegevens en informatie die u handmatig hebt ingevoerd, worden niet vertaald.

### <a name="update-the-settings"></a>De instellingen bijwerken

Kies om uw voorkeurstaal te wijzigen een **taal** uit de dropdown.

Gebruik de vervolgkeuzelijst **Indeling voor land/regio** om de gewenste opmaak voor datums, tijd en cijfers te wijzigen. Onder dit veld wordt een opmaakvoorbeeld weergegeven. Het systeem stelt automatisch een keuze voor wanneer u een nieuwe taal kiest.

Selecteer **Opslaan** om uw selecties te bevestigen.

## <a name="api-usage-tab"></a>Tabblad API-gebruik

Vind details over het realtime API-gebruik en kijk welke gebeurtenissen hebben plaatsgevonden in een bepaald tijdsbestek. U kiest de tijdsbestek in het vervolgkeuzemenu **Een tijdsbestek selecteren**. 

**API-gebruik** bevat drie secties: 
- **API-aanroepen**: een grafiek die het geaggregeerde aantal aanroepen naar de API in het geselecteerde tijdsbestek visualiseert.

- **Gegevensoverdracht**: - een grafiek die de hoeveelheid gegevens toont die via de API zijn overgedragen in het geselecteerde tijdsbestek.

-  **Bewerkingen**: een tabel met rijen voor elke beschikbare API-bewerking en details over het gebruik van de bewerkingen. U kunt een bewerkingsnaam selecteren om naar [de API-verwijzing](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances)​te gaan.

   Bewerkingen die gebruikmaken van [realtime gegevensopname](real-time-data-ingestion.md) bevatten een knop met een verrekijkersymbool om het realtime API-gebruik te bekijken. Selecteer de knop om een deelvenster aan de zijkant te openen met gebruiksdetails voor het realtime API-gebruik in de huidige omgeving.   
   Gebruik het vak **Groeperen op** in het deelvenster **Realtime API-gebruik** om te kiezen hoe u uw realtime interacties het best kunt presenteren. U kunt de gegevens groeperen op API-methode, entiteit gekwalificeerde naam (opgenomen entiteit), gemaakt door (bron van de gebeurtenis), resultaat (succes of mislukking) of foutcodes. De gegevens zijn beschikbaar als geschiedenisdiagram en als tabel.


[!INCLUDE [footer-include](includes/footer-banner.md)]
