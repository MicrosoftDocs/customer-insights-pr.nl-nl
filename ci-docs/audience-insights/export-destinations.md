---
title: Gegevens exporteren vanuit Customer Insights
description: Beheer exports om gegevens te delen.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016608"
---
# <a name="exports-preview-overview"></a>Overzicht van Exports (preview)

De pagina **Exports** toont u alle geconfigureerde exports. Exports delen specifieke gegevens met verschillende toepassingen. Ze kunnen klantprofielen of entiteiten, schema's en toewijzingsdetails bevatten. Elke export vereist een [verbinding, opgezet door een beheerder, om de verificatie en toegang te beheren](connections.md).

Ga naar **Gegevens** > **Exports** om de pagina met exports te bekijken. Alle gebruikersrollen hebben toegang om geconfigureerde exports te bekijken. Gebruik van het zoekveld in de opdrachtbalk om exports te zoeken op naam, verbindingsnaam of verbindingstype.

## <a name="set-up-a-new-export"></a>Een nieuwe export instellen

Als u een export wilt instellen of bewerken, moet u over verbindingen beschikken. Verbindingen zijn afhankelijk van uw [gebruikersrol](permissions.md):
- Beheerders hebben toegang tot alle verbindingen. Ze kunnen ook nieuwe verbindingen maken bij het opzetten van een export.
- Inzenders kunnen toegang hebben tot specifieke verbindingen. Zij zijn afhankelijk van beheerders om verbindingen te configureren en te delen. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.
- Kijkers kunnen alleen bestaande exports bekijken, maar deze niet maken.

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen** om een nieuwe exportbestemming te maken.

1. Selecteer in het deelvenster **Export instellen** welke verbinding u wilt gebruiken. [Verbindingen](connections.md) worden beheerd door beheerders. 

1. Geef de vereiste details op en selecteer **Opslaan** om de export te maken.

### <a name="edit-an-export"></a>Een export bewerken

1. Selecteer het verticale weglatingsteken voor de exportbestemming die u wilt bewerken.

1. Selecteer **Bewerken** in het vervolgkeuzemenu.

1. Wijzig de waarden die u wilt bijwerken en selecteer **Opslaan**.

## <a name="view-exports-and-export-details"></a>Exports en exportdetails weergeven

Nadat u exportbestemmingen hebt gemaakt, worden deze vermeld bij **Gegevens** > **Exports**. Alle gebruikers kunnen zien welke gegevens worden gedeeld en wat de meest recente status is.

1. Ga naar **Gegevens** > **Exports**.

1. Gebruikers zonder machtigingen voor bewerken selecteren **Weergeven** in plaats van **Bewerken** om de exportdetails te bekijken.

1. Dit zijpaneel toont de instellingen van deze export. Zonder bewerkingsrechten kunt u geen waarden wijzigen. Selecteer **Sluiten** om terug te keren naar de pagina met exports.

## <a name="run-exports-on-demand"></a>Exports op aanvraag uitvoeren

Na het configureren van een export, wordt deze uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab) zolang er een werkende verbinding is.

Als u gegevens wilt exporteren zonder te wachten op een geplande vernieuwing, gaat u naar **Gegevens** > **Exports**. U hebt twee opties:

- Als u alle exports wilt uitvoeren, selecteert u **Alles uitvoeren** op de opdrachtbalk. 
- Als u een enkele export wilt uitvoeren, selecteert u het beletselteken (...) in een lijstitem en kiest u vervolgens **Uitvoeren**.

## <a name="remove-an-export"></a>Een export verwijderen

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer het verticale weglatingsteken voor de export die u wilt verwijderen.

1. Selecteer **Verwijderen** in het vervolgkeuzemenu.

1. Bevestig de verwijdering door **Verwijderen** te selecteren op het bevestigingsscherm.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
