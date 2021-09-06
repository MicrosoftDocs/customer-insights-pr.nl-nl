---
title: Gegevens exporteren vanuit Customer Insights
description: Beheer exports om gegevens te delen.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: be4d142e0f9f422cac459f603aa5dd8bb490321cfe1b2de58f4a128ae56f4ba3
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034676"
---
# <a name="exports-preview-overview"></a>Overzicht van Exports (preview)

De pagina **Exports** toont u alle geconfigureerde exports. Exports delen specifieke gegevens met verschillende toepassingen. Ze kunnen klantprofielen of entiteiten, schema's en toewijzingsdetails bevatten. Elke export vereist een [verbinding, opgezet door een beheerder, om de verificatie en toegang te beheren](connections.md).

Ga naar **Gegevens** > **Exports** om de pagina met exports te bekijken. Alle gebruikersrollen kunnen geconfigureerde exports bekijken. Gebruik het zoekveld in de opdrachtbalk om exports te zoeken op naam, verbindingsnaam of verbindingstype.

## <a name="set-up-a-new-export"></a>Een nieuwe export instellen

Als u een export wilt instellen of bewerken, moet u over verbindingen beschikken. Verbindingen zijn afhankelijk van uw [gebruikersrol](permissions.md):
- Beheerders hebben toegang tot alle verbindingen. Ze kunnen ook nieuwe verbindingen maken bij het opzetten van een export.
- Inzenders kunnen toegang hebben tot specifieke verbindingen. Zij zijn afhankelijk van beheerders om verbindingen te configureren en te delen. De exportlijst laat zien of inzenders een export kunnen bewerken of alleen bekijken in de kolom **Uw machtigingen**. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.
- Kijkers kunnen alleen bestaande exports bekijken, maar deze niet maken.

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

Exportschema's zijn afhankelijk van de status van uw omgeving. Als er updates worden uitgevoerd op [afhankelijkheden](system.md#refresh-policies), voltooit het systeem bij het starten van een geplande eerst de updates en voert vervolgens de export uit. U kunt zien wanneer een export voor het laatst is vernieuwd in de kolom **Vernieuwd**.

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
