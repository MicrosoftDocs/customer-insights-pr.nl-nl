---
title: Gegevens exporteren vanuit Customer Insights
description: Beheer exports om gegevens te delen.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 05485fc7def3d699d5179bcaa005ceb57024f840
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977961"
---
# <a name="exports-preview-overview"></a>Overzicht van Exports (preview)

De pagina **Exports** toont u alle geconfigureerde exports. Exports delen specifieke gegevens met verschillende toepassingen. Ze kunnen klantprofielen, entiteiten, schema's en toewijzingsdetails bevatten. Elke export vereist een [verbinding, opgezet door een beheerder, om de verificatie en toegang te beheren](connections.md).

Ga naar **Gegevens** > **Exports** om de pagina met exports te bekijken. Alle gebruikersrollen kunnen geconfigureerde exports bekijken. Gebruik het zoekveld in de opdrachtbalk om exports te zoeken op naam, verbindingsnaam of verbindingstype.

## <a name="export-types"></a>Exporttypen

Er zijn twee hoofdtypen exports:  

- **Gegevens uit-export** hiermee kunt u elk type entiteit exporteren dat beschikbaar is in doelgroepinzichten. De entiteiten die u selecteert voor export, worden geëxporteerd met alle gegevensvelden, metagegevens, schema's en toewijzingsdetails. 
- **Segmentexport** hiermee kunt u segmententiteiten exporteren uit doelgroepinzichten. Segmenten vertegenwoordigen een lijst met klantprofielen. Bij het configureren van de export selecteert u de inbegrepen gegevensvelden, afhankelijk van het doelsysteem waarnaar u gegevens exporteert. 

### <a name="export-segments"></a>Segmenten exporteren

**Segmenten exporteren in omgevingen voor zakelijke accounts (B2B) of individuele consumenten (B2C)**  
De meeste exportopties ondersteunen beide typen omgevingen. Het exporteren van segmenten naar verschillende doelsystemen heeft specifieke eisen. Over het algemeen bevat een segmentlid, het klantprofiel, contactgegevens. Hoewel dit meestal het geval is voor segmenten die zijn gebaseerd op individuele consumenten (B2C), hoeft dit niet het geval te zijn voor segmenten die zijn gebaseerd op zakelijke accounts (B2B). 

**Segmentexport in omgevingen voor zakelijke accounts (B2B)**  
- Segmenten in de context van omgevingen voor zakelijke accounts zijn gebouwd op de entiteit *account*. Om accountsegmenten ongewijzigd te exporteren, moet het doelsysteem pure accountsegmenten ondersteunen. Dit is het geval voor [LinkedIn](export-linkedin-ads.md) wanneer u kiest voor de optie **bedrijf** bij het definiëren van de export.
- Voor alle andere doelsystemen zijn velden van de contactentiteit vereist Om ervoor te zorgen dat accountsegmenten gegevens kunnen ophalen van gerelateerde contactpersonen, moet uw segmentdefinitie kenmerken van de contactentiteit projecteren. Meer informatie over het [configureren van segmenten en projectkenmerken](segment-builder.md).

**Segmentexport in omgevingen voor individuele consumenten (B2C)**  
- Segmenten in de context van omgevingen voor individuele klanten zijn gebouwd op de entiteit *geharmoniseerd klantprofiel*. Elk segment dat voldoet aan de eisen van de doelsystemen (bijvoorbeeld een e-mailadres), kan worden geëxporteerd.

**Limieten voor segmentexport**  
- Doelsystemen van derden kunnen het aantal klantprofielen dat u kunt exporteren, beperken. 
- Voor individuele klanten ziet u het werkelijke aantal segmentleden wanneer u een segment selecteert om te exporteren. Er verschijnt een waarschuwing als een segment te groot is. 
- Voor zakelijke accounts ziet u het aantal accounts in een segment; het aantal contacten dat mogelijk wordt geprojecteerd, wordt echter niet weergegeven. In sommige gevallen kan dit ertoe leiden dat het geëxporteerde segment daadwerkelijk meer klantprofielen bevat dan het doelsysteem accepteert. Als de limieten van de doelsystemen worden overschreden, wordt de export overgeslagen. 

## <a name="set-up-a-new-export"></a>Een nieuwe export instellen  
Als u een export wilt instellen of bewerken, moet u over verbindingen beschikken. Verbindingen zijn afhankelijk van uw [gebruikersrol](permissions.md):
- **Beheerders** hebben toegang tot alle verbindingen. Ze kunnen ook nieuwe verbindingen maken bij het opzetten van een export.
- **Inzenders** kunnen toegang hebben tot specifieke verbindingen. Zij zijn afhankelijk van beheerders om verbindingen te configureren en te delen. De exportlijst laat zien of inzenders een export kunnen bewerken of alleen bekijken in de kolom **Uw machtigingen**. Ga voor meer informatie naar [Toestaan dat inzenders een verbinding gebruiken voor export](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Kijkers** kunnen alleen bestaande exports bekijken, niet maken.

### <a name="define-a-new-export"></a>Een nieuwe export definiëren

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen** om een nieuwe export te maken.

1. Selecteer in het deelvenster **Export instellen** welke verbinding u wilt gebruiken. [Verbindingen](connections.md) worden beheerd door beheerders. 

1. Geef de vereiste details op en selecteer **Opslaan** om de export te maken.

### <a name="define-a-new-export-based-on-an-existing-export"></a>Een nieuwe export definiëren op basis van een bestaande export

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer in de lijst met exports de export die u wilt dupliceren.

1. Selecteer **Duplicaat maken** op de opdrachtbalk om het deelvenster **Export instellen** te openen met de details van de geselecteerde export.

1. Bekijk en pas de export aan en selecteer **Opslaan** om een nieuwe export te maken.

### <a name="edit-an-export"></a>Een export bewerken

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer in de lijst met exports de export die u wilt bewerken.

1. Selecteer **Bewerken** op de opdrachtbalk.

1. Wijzig de waarden die u wilt bijwerken en selecteer **Opslaan**.

## <a name="view-exports-and-export-details"></a>Exports en exportdetails weergeven

Nadat u exportbestemmingen hebt gemaakt, worden deze vermeld bij **Gegevens** > **Exports**. Alle gebruikers kunnen zien welke gegevens worden gedeeld en wat de meest recente status is.

1. Ga naar **Gegevens** > **Exports**.

1. Gebruikers zonder bewerkingsrechten selecteren **Weergeven** in plaats van **Bewerken** om de exportdetails te zien.

1. Het zijvenster toont de configuratie van een export. Zonder bewerkingsrechten kunt u geen waarden wijzigen. Selecteer **Sluiten** om terug te keren naar de pagina met exports.

## <a name="schedule-and-run-exports"></a>Exports plannen en uitvoeren

Elke export die u configureert, heeft een vernieuwingsschema. Tijdens een vernieuwing zoekt het systeem naar nieuwe of bijgewerkte gegevens om in een export op te nemen. Standaard worden exports uitgevoerd als onderdeel van elke [geplande systeemvernieuwing](system.md#schedule-tab). U kunt het vernieuwingsschema aanpassen of uitschakelen om exports handmatig uit te voeren.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

Exportschema's zijn afhankelijk van de status van uw omgeving. Als er updates worden uitgevoerd op [afhankelijkheden](system.md#refresh-processes), voltooit het systeem bij het starten van een geplande eerst de updates en voert vervolgens de export uit. U kunt zien wanneer een export voor het laatst is vernieuwd in de kolom **Vernieuwd**.

### <a name="schedule-exports"></a>Exports plannen

U kunt aangepaste vernieuwingsschema's definiëren voor afzonderlijke exports of meerdere exports tegelijk. Het momenteel gedefinieerde schema wordt weergegeven in de kolom **Schema** van de exportlijst. De toestemming om het schema te wijzigen is hetzelfde als voor [het bewerken en definiëren van exports](export-destinations.md#set-up-a-new-export). 

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer de export die u wilt plannen.

1. Selecteer **Plannen** op de opdrachtbalk.

1. Stel in het deelvenster **Export plannen** de optie **Uitvoering plannen** in op **Aan** om de export automatisch uit te voeren. Stel de optie in op **Uit** om handmatig te vernieuwen.

1. Kies voor automatisch vernieuwde exports een waarde voor **Terugkeerpatroon** en geef de details hiervoor op. De gedefinieerde tijd is van toepassing op alle exemplaren van een terugkeerpatroon. Het is het tijdstip waarop een export moet worden vernieuwd.

1. Pas uw wijzigingen toe en activeer ze door **Opslaan** te selecteren.

Bij het bewerken van de planning voor meerdere exports, dient u een selectie te maken onder **Planningen behouden of overschrijven**:
- **Afzonderlijke planningen behouden**: houd het eerder gedefinieerde schema voor de geselecteerde exports aan en schakel ze alleen in of uit.
- **Nieuwe planning voor alle geselecteerde exporten opgeven**: overschrijf de bestaande planningen van de geselecteerde exports.

### <a name="run-exports-on-demand"></a>Exports op aanvraag uitvoeren

Als u gegevens wilt exporteren zonder te wachten op een geplande vernieuwing, gaat u naar **Gegevens** > **Exports**.

- Als u alle exports wilt uitvoeren, selecteert u **Alles uitvoeren** op de opdrachtbalk. Met deze actie worden alleen exports uitgevoerd met een actieve planning.
- U kunt een enkele export uitvoeren door deze te selecteren in de lijst en vervolgens **Uitvoeren** te selecteren op de opdrachtbalk. Zo voert exports uit zonder actieve planning. 

## <a name="remove-an-export"></a>Een export verwijderen

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer de export die u wilt verwijderen.

1. Selecteer **Verwijderen** op de opdrachtbalk.

1. Bevestig de verwijdering door **Verwijderen** te selecteren op het bevestigingsscherm.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
