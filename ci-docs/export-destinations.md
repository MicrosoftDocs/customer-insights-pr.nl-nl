---
title: Overzicht van Exports (preview)
description: Beheer exports om gegevens te delen.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- ci-connections
- customerInsights
ms.openlocfilehash: 44f58d694b9bd35a8d8c04d487d40743291e0566
ms.sourcegitcommit: ef3e17134d44d2731605381ea0385dbc5aef6120
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/09/2022
ms.locfileid: "9460184"
---
# <a name="exports-preview-overview"></a>Overzicht van Exports (preview)

 Met exports kunt u specifieke gegevens met verschillende toepassingen delen. Ze kunnen klantprofielen, entiteiten, schema's en toewijzingsdetails bevatten. Elke export vereist een [verbinding, opgezet door een beheerder, om de verificatie en toegang te beheren](connections.md). De pagina **Exports** toont u alle geconfigureerde exports.

## <a name="export-types"></a>Exporttypen

Er zijn twee hoofdtypen exports:  

- **Gegevens uit-export** hiermee kunt u elk type entiteit exporteren dat beschikbaar is in Customer Insights. De entiteiten die u selecteert voor export, worden geëxporteerd met alle gegevensvelden, metagegevens, schema's en toewijzingsdetails.
- **Segmentexport** hiermee kunt u segmententiteiten exporteren uit Customer Insights. Voor individuele consumenten (B2C) vertegenwoordigen segmenten een lijst met klantprofielen. Voor bedrijven (B2B) [kunnen segmenten een lijst met accounts of contactpersonen vertegenwoordigen](segment-builder.md#create-a-new-segment-with-segment-builder). Bij het configureren van de export selecteert u de opgenomen gegevensvelden, afhankelijk van het doelsysteem waarnaar u gegevens exporteert.

### <a name="export-segments"></a>Segmenten exporteren

**Segmenten exporteren in omgevingen voor zakelijke accounts (B2B) of individuele consumenten (B2C)**  
De meeste exportopties ondersteunen beide typen omgevingen. Het exporteren van segmenten naar verschillende doelsystemen heeft specifieke vereisten. 

**Segmentexport in omgevingen voor individuele consumenten (B2C)**  
- Segmenten in de context van omgevingen voor individuele klanten zijn gebouwd op de entiteit *geharmoniseerd klantprofiel*. Elk segment dat voldoet aan de eisen van de doelsystemen (bijvoorbeeld een e-mailadres), kan worden geëxporteerd.

**Segmentexport in omgevingen voor zakelijke accounts (B2B)**  
- Segmenten in de context van omgevingen voor zakelijke accounts zijn gebouwd op de entiteit *account* of de entiteit *contactpersoon*. Om accountsegmenten ongewijzigd te exporteren, moet het doelsysteem pure accountsegmenten ondersteunen. Dit is het geval voor [LinkedIn](export-linkedin-ads.md) wanneer u kiest voor de optie **bedrijf** bij het definiëren van de export.
- Voor alle andere doelsystemen zijn velden van de contactentiteit vereist
- Met twee segmenttypen (contactpersonen en accounts) identificeert Customer Insights automatisch welk type segmenten in aanmerking komen voor export op basis van het doelsysteem. Voor een op contactpersonen gericht doelsysteem zoals Mailchimp kunt u met Customer Insights bijvoorbeeld alleen contactpersoonsegmenten kiezen om te exporteren.

**Limieten voor segmentexport**  
- Doelsystemen van derden kunnen het aantal klantprofielen dat u kunt exporteren, beperken. 
- Voor individuele klanten ziet u het werkelijke aantal segmentleden wanneer u een segment selecteert om te exporteren. Er verschijnt een waarschuwing als een segment te groot is. 
- Voor zakelijke accounts ziet u het aantal accounts of contactpersonen, afhankelijk van het segment. Er verschijnt een waarschuwing als het segment te groot is. Als de limieten van de doelsystemen worden overschreden, wordt de export overgeslagen.

## <a name="set-up-a-new-export"></a>Een nieuwe export instellen

Als u een export wilt instellen of bewerken, moet u over de juiste verbindingen beschikken. Verbindingen zijn afhankelijk van uw [gebruikersrol](permissions.md):
- **Beheerders** hebben toegang tot alle verbindingen. Ze kunnen ook nieuwe verbindingen maken bij het opzetten van een export.
- **Inzenders** kunnen toegang hebben tot specifieke verbindingen. Zij zijn afhankelijk van beheerders om verbindingen te configureren en te delen. De exportlijst laat zien of inzenders een export kunnen bewerken of alleen bekijken in de kolom **Uw machtigingen**. Ga voor meer informatie naar [Toestaan dat inzenders een verbinding gebruiken voor export](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Kijkers** kunnen alleen bestaande exports bekijken, niet maken.

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen** om een nieuwe export te maken.

1. Selecteer in het deelvenster **Export instellen** welke [verbinding](connections.md) u wilt gebruiken.

1. Geef de vereiste details op en selecteer **Opslaan** om de export te maken. Raadpleeg de Customer Insights-documentatie van de specifieke export voor de vereiste details.

## <a name="manage-existing-exports"></a>Bestaande exports beheren

Ga naar **Gegevens** > **Exports** om de exports en verbindingsnaam, verbindingstype en status ervan te bekijken. Alle gebruikersrollen kunnen geconfigureerde exports bekijken. U kunt de lijst met exports sorteren op elke kolom of het zoekvak gebruiken om de export te vinden die u wilt beheren.

Selecteer een export om beschikbare acties te bekijken.

:::image type="content" source="media/exports_showmore.png" alt-text="Pagina Exports.":::

- **Bekijk** of **bewerk** de export. Gebruikers zonder bewerkingsrechten selecteren **Weergeven** in plaats van **Bewerken** om de exportdetails te zien.
- Selecteer **Export uitvoeren** om de laatste gegevens te exporteren.
- **Maak een duplicaat** van een export.
- **[Plan](#schedule-and-run-exports)** de export.
- Selecteer **Verbinding verbreken** om de verbinding voor deze export te verwijderen. Met Verbinding verbreken wordt de verbinding niet verwijderd, maar wordt de export gedeactiveerd. In de kolom **Gebruikte verbinding** wordt Geen verbinding weergegeven.
- **Verwijder** de export.

## <a name="schedule-and-run-exports"></a>Exports plannen en uitvoeren

Elke export die u configureert, heeft een vernieuwingsschema. Tijdens een vernieuwing zoekt het systeem naar nieuwe of bijgewerkte gegevens om in een export op te nemen. Standaard worden exports uitgevoerd als onderdeel van elke [geplande systeemvernieuwing](schedule-refresh.md). U kunt het vernieuwingsschema aanpassen of uitschakelen om exports handmatig uit te voeren.

> [!TIP]
> Minimaliseer de verwerkingstijd van segmentexporten met de volgende best practices:
> - Verdeel segmententiteiten over meerdere exporten.
> - Voorkom dat u alle exporten tegelijkertijd plant. Laat 30 minuten of een uur tussen de geplande tijd van elke export.

Exportschema's zijn afhankelijk van de status van uw omgeving. Als er updates worden uitgevoerd op [afhankelijkheden](system.md#refresh-processes), voltooit het systeem bij het starten van een geplande eerst de updates en voert vervolgens de export uit. In de kolom **Vernieuwd** wordt aangegeven wanneer een export voor het laatst is vernieuwd.

### <a name="schedule-exports"></a>Exports plannen

Definieer aangepaste vernieuwingsschema's voor afzonderlijke exports of meerdere exports tegelijk. Het momenteel gedefinieerde schema wordt weergegeven in de kolom **Schema** van de exportlijst. De machtiging om de planning te wijzigen is hetzelfde als voor het [bewerken en definiëren van exports](export-destinations.md#set-up-a-new-export).

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer de export die u wilt plannen.

1. Selecteer **Planning**.

1. Stel in het deelvenster **Export plannen** de optie **Uitvoering plannen** in op **Aan** om de export automatisch uit te voeren. Stel de optie in op **Uit** om handmatig te vernieuwen.

1. Kies voor automatisch vernieuwde exports een waarde voor **Terugkeerpatroon** en geef de details hiervoor op. De gedefinieerde tijd is van toepassing op alle exemplaren van een terugkeerpatroon. Het is het tijdstip waarop een export moet worden vernieuwd.

1. Selecteer **Save**.

Bij het bewerken van de planning voor meerdere exports, maakt u een selectie onder **Planningen behouden of overschrijven**:

- **Afzonderlijke planningen behouden**: behoud de eerder gedefinieerde planning voor de geselecteerde exports en schakel ze alleen in of uit.
- **Nieuwe planning voor alle geselecteerde exporten opgeven**: overschrijf de bestaande planningen van de geselecteerde exports.

### <a name="run-exports-on-demand"></a>Exports op aanvraag uitvoeren

Als u gegevens wilt exporteren zonder te wachten op een geplande vernieuwing, gaat u naar **Gegevens** > **Exports**.

- Als u alle exports wilt uitvoeren, selecteert u **Alles uitvoeren** op de opdrachtbalk. Alleen exports met een actieve planning worden uitgevoerd. Als u een export wilt uitvoeren die niet actief is, voert u één export uit.
- U kunt een enkele export uitvoeren door deze te selecteren in de lijst en vervolgens **Uitvoeren** te selecteren op de opdrachtbalk.

## <a name="troubleshooting"></a>Probleemoplossing

### <a name="segment-not-eligible-for-export"></a>Segment komt niet in aanmerking voor export

**Probleem** Binnen een omgeving van zakelijke accounts mislukt uw export met de foutmelding: "Het volgende segment komt niet in aanmerking voor deze exportbestemming: '{naam van segment}'. Kies alleen segmenten van het type ContactProfile en probeer het opnieuw."

**Oplossing** Customer Insights-omgevingen voor zakelijke accounts zijn bijgewerkt om naast accountsegmenten ook contactpersoonsegmenten te ondersteunen. Door die wijziging werken exports waarvoor contactpersoongegevens nodig zijn, alleen met segmenten op basis van contactpersonen.

1. [Maak een segment op basis van contactpersonen](segment-builder.md) dat overeenkomt met uw eerder gebruikte segment.

1. Zodra dat contactpersoonsegment is uitgevoerd, bewerkt u de respectievelijke export en selecteert u het nieuwe segment.

1. Selecteer **Opslaan** om de configuratie op te slaan of **Opslaan en uitvoeren** om deze export meteen te testen.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
