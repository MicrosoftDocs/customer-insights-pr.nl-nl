---
title: Systeemconfiguratie weergeven
description: Meer informatie over systeeminstellingen in Dynamics 365 Customer Insights.
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 6e60bf7c18939a29f660e06989e262deeb59a39b
ms.sourcegitcommit: d7054a900f8c316804b6751e855e0fba4364914b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/02/2022
ms.locfileid: "9395995"
---
# <a name="view-system-configuration"></a>Systeemconfiguratie weergeven

Bekijk systeeminformatie, systeemstatus en API-gebruik.

## <a name="view-api-usage"></a>API-gebruik weergeven

Bekijk details over het realtime API-gebruik en ga na welke gebeurtenissen hebben plaatsgevonden in een bepaald tijdsbestek.

1. Ga naar **Beheer** > **Systeem** en selecteer het tabblad **API-gebruik**.

1. **Selecteer een tijdsbestek** om te bekijken.

   De pagina **API-gebruik** bevat drie secties:

   - **API-aanroepen**: een grafiek die het geaggregeerde aantal aanroepen naar de API in het geselecteerde tijdsbestek visualiseert.
   - **Gegevensoverdracht**: - een grafiek die de hoeveelheid gegevens toont die via de API zijn overgedragen in het geselecteerde tijdsbestek.
   - **Bewerkingen**: een tabel met rijen voor elke beschikbare API-bewerking en details over het gebruik van de bewerkingen. Selecteer een bewerkingsnaam om naar [de API-verwijzing](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) te gaan.

## <a name="view-system-information"></a>Systeemgegevens weergeven

Bekijk weergavenaam, id, regio, type en sessie-id van de omgeving.

1. Ga naar **Beheer** > **Systeem** en selecteer het tabblad **Info**.

1. U kunt de taal en het land/de regio bekijken door het tabblad **Algemeen** te selecteren.

### <a name="update-preferred-language-or-countryregion"></a>Voorkeurstaal of land/regio bijwerken

Customer Insights [ondersteunt vele talen](/dynamics365/get-started/availability). De app gebruikt uw taalvoorkeur om elementen als het menu, labeltekst en systeemberichten in uw voorkeurstaal weer te geven.

Geïmporteerde gegevens en informatie die u handmatig hebt ingevoerd, worden niet vertaald.

1. Ga naar **Beheer** > **Systeem** en selecteer het tabblad **Algemeen**.

1. Kies om uw voorkeurstaal te wijzigen een **taal** uit de dropdown.

1. Gebruik de vervolgkeuzelijst **Indeling voor land/regio** om de gewenste opmaak voor datums, tijd en cijfers te wijzigen. Er wordt een opmaakvoorbeeld weergegeven. Het systeem stelt automatisch een keuze voor wanneer u een nieuwe taal kiest.

1. Selecteer **Save**.

## <a name="view-system-status"></a>Systeemstatus weergeven

Houd de voortgang bij van taken, gegevensopname, gegevensexport en verschillende andere belangrijke productprocessen. Bekijk de informatie om de volledigheid van uw actieve taken en processen te waarborgen.

1. Ga naar **Beheer** > **Systeem** en selecteer het tabblad **Status**.

   Er wordt status- en verwerkingsinformatie voor verschillende processen weergegeven. Bekijk de **naam** van de taak, de **status** van de meest recente uitvoering en het tijdstip in **Laatst bijgewerkt**.

1. U kunt de details van de laatste paar uitvoeringen bekijken door de taak- of procesnaam te selecteren.

1. Als u de voortgangsdetails voor een taak wilt bekijken, selecteert u de status. Het deelvenster **Voortgangsdetails** wordt weergegeven.

   :::image type="content" source="media/system-progress-details.png" alt-text="Deelvenster met details van systeemvoortgang":::

1. U kunt de voortgangsdetails voor alle taken bekijken door **Volledige werkstroom** te selecteren.

### <a name="status-definitions"></a>Statusdefinities

Het systeem gebruikt de volgende statussen voor taken en processen:

|-Status  |Definitie  |
|---------|---------|
|Geannuleerd |Taak of proces is door de gebruiker geannuleerd voordat deze/dit is voltooid.   |
|Mislukt   |Er zijn fouten opgetreden bij taak of proces.         |
|Mislukking  |Taak of proces is mislukt.  |
|Niet gestart   |Gegevensbron heeft nog geen gegevens opgenomen of de taak bevindt zich nog in de conceptmodus.         |
|Verwerking  |De taak of het proces wordt uitgevoerd.  |
|Vernieuwen    |De taak of het proces wordt uitgevoerd. Als u deze bewerking wilt annuleren, selecteert u **Vernieuwen** en **Taak annuleren**. Als u het vernieuwen van een taak of proces stopt, keert het terug naar de laatste vernieuwingsstatus.       |
|Overgeslagen  |De taak of het proces is overgeslagen. Een of meer van de downstreamprocessen waarvan deze taak afhankelijk is, mislukken of worden overgeslagen.|
|Geslaagd  |De taak of het proces is voltooid. Geeft voor gegevensbronnen aan dat de gegevens zijn opgenomen als een tijd wordt vermeld in de kolom **Vernieuwd**.|
|In wachtrij geplaatst | De verwerking wordt in de wachtrij geplaatst en start zodra alle upstreamtaken en -processen zijn voltooid. Zie voor meer informatie [Processen vernieuwen](#refresh-processes).|

### <a name="refresh-processes"></a>Processen vernieuwen

Vernieuwen voor taken en processen wordt uitgevoerd volgens het [geconfigureerde schema](schedule-refresh.md).

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


[!INCLUDE [footer-include](includes/footer-banner.md)]
