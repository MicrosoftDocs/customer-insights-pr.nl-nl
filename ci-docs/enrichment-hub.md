---
title: Overzicht van gegevensverrijking (preview)
description: Gebruik mogelijkheden van Microsoft en andere services van derden om uw klantgegevens te verrijken.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 6b6daab480db5e37830ff58b71dcdd3bbdbe46da
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053858"
---
# <a name="data-enrichment-preview-overview"></a>Overzicht van gegevensverrijking (preview)

Gebruik gegevens vanuit bronnen zoals Microsoft en andere partners om uw klantgegevens te verrijken. Verrijkingen van derden worden geconfigureerd met [verbindingen](connections.md), die een beheerder instelt met referenties en die toestemming verlenen voor gegevensoverdracht. Deze verbindingen kunnen worden gebruikt door beheerders en inzenders om verrijkingen te configureren.  

## <a name="multiple-enrichments-of-the-same-type"></a>Meerdere verrijkingen van hetzelfde type

De entiteit die moet worden verrijkt, wordt gespecificeerd tijdens de verrijkingsconfiguratie, waardoor u de mogelijkheid hebt om slechts een subset van uw profielen te verrijken. Verrijk bijvoorbeeld alleen gegevens voor een specifiek segment. U kunt meerdere verrijkingen van hetzelfde type configureren en dezelfde verbinding opnieuw gebruiken. Sommige verrijkingen hebben limieten voor het aantal verrijkingen van hetzelfde type dat kan worden gemaakt. De limieten en het huidige gebruik zijn te zien op elke tegel op het tabblad **Ontdekken** van de pagina **Verrijking**.

## <a name="enrich-data-sources-before-unification"></a>Gegevensbronnen verrijken vóór harmonisatie

U kunt uw klantgegevens verrijken vóór gegevensharmonisatie om de kwaliteit van een gegevensmatch te helpen verbeteren. Zie [Verrijking voor gegevensbronnen](data-sources-enrichment.md) voor meer informatie.

## <a name="create-an-enrichment"></a>Een verrijking maken

U hebt de [machtigingen](permissions.md) Inzender of Beheerder nodig om verrijkingen te kunnen maken of bewerken.

Ga naar **Gegevens** > **Verrijking**. Het tabblad **Ontdekken** toont alle ondersteunde verrijkingsopties.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Pagina van verrijkingshub.":::

# <a name="individual-consumers-b-to-c"></a>[Individuele consumenten (B-to-C)](#tab/b2c)

- [AbiliTec-identiteit](enrichment-liveramp.md) aangeboden door LiveRamp AbiliTec
- [Merken](enrichment-microsoft.md) die worden geleverd door Microsoft
- [Demografische gegevens](enrichment-experian.md) geleverd door Experian
- [Uitgebreide adressen](enrichment-enhanced-addresses.md) geleverd door Microsoft
- [Interesses](enrichment-microsoft.md) die worden geleverd door Microsoft
- [Locatiegegevens](enrichment-azure-maps.md) geleverd door Microsoft Azure Maps
- [Locatiegegevens](enrichment-here.md) worden geleverd door HERE Technologies
- [Aangepaste SFTP-gegevens](enrichment-SFTP-custom-import.md) via Secure File Transfer Protocol (SFTP)

# <a name="business-accounts-b-to-b"></a>[Zakelijke accounts (B-to-B)](#tab/b2b)

- [Gegevens over accountbetrokkenheid](enrichment-office.md) geleverd door Microsoft
- [Bedrijfsgegevens](enrichment-dnb.md) geleverd door Dun & Bradstreet
- [Bedrijfsgegevens](enrichment-leadspace.md) worden verstrekt door Leadspace
- [Uitgebreide adressen](enrichment-enhanced-addresses.md) geleverd door Microsoft
- [Verbeterde bedrijfsgegevens](enrichment-enhanced-company-data.md) door Microsoft
- [Locatiegegevens](enrichment-azure-maps.md) geleverd door Microsoft Azure Maps
- [Locatiegegevens](enrichment-here.md) worden geleverd door HERE Technologies
- [Aangepaste SFTP-gegevens](enrichment-SFTP-custom-import.md) via Secure File Transfer Protocol (SFTP)

---

## <a name="manage-existing-enrichments"></a>Bestaande verrijkingen beheren

Ga naar **Gegevens** > **Verrijking**. Bekijk op het tabblad **Mijn verrijkingen** de geconfigureerde verrijkingen, hun status, het aantal verrijkte klanten en de laatste keer dat de gegevens zijn vernieuwd. U kunt de lijst met verrijkingen sorteren op elke kolom of het zoekvak gebruiken om de verrijking te vinden die u wilt beheren.

Selecteer de verrijking om beschikbare acties te bekijken.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opties om verrijkingen in de lijst met verrijkingen te beheren.":::

- **Bekijk** verrijkingsdetails met het aantal verrijkte klantprofielen.
- **Bewerk** de verrijkingsconfiguratie.
- [**Voer**](#run-or-refresh-enrichments) de verrijking uit om klantprofielen bij te werken met de laatste gegevens. Voer meerdere verrijkingen tegelijk uit door ze in de lijst te selecteren.
- **Activeer** of **Deactiveer** een verrijking. Inactieve verrijkingen worden niet vernieuwd gedurende een [geplande vernieuwing](system.md#schedule-tab).
- De verrijking **Verwijderen**.

U kunt ook [segmenten](segments.md) of [metingen](measures.md) maken van verrijkingen.

## <a name="run-or-refresh-enrichments"></a>Verrijkingen uitvoeren of vernieuwen

Eenmaal uitgevoerd, kunnen verrijkingen worden vernieuwd volgens een automatische planning of handmatig op aanvraag.

1. Om een of meer verrijkingen handmatig te vernieuwen, selecteert u ze en kiest u **Uitvoeren**. Om [een automatische vernieuwing te plannen](system.md#schedule-tab), gaat u naar **Beheerder** > **Systeem** > **Planning**. De verwerkingstijd is afhankelijk van de grootte van uw klantgegevens.

1. Optioneel kunt u [de voortgang van het verrijkingsproces zien](#see-the-progress-of-the-enrichment-process).

1. Nadat het verrijkingsproces is voltooid, gaat u naar **Mijn verrijkingen** om de zojuist verrijkte klantprofielgegevens, het tijdstip van de laatste update en het aantal verrijkte profielen te bekijken.

1. Selecteer de verrijking om [verrijkingsresultaten](#view-enrichment-results) te zien.

### <a name="see-the-progress-of-the-enrichment-process"></a>De voortgang van het verrijkingsproces bekijken

U kunt details over de verwerking van een verrijking vinden, inclusief de bijbehorende status en mogelijke problemen, tijdens het vernieuwen of nadat een vernieuwing is voltooid. Krijg inzicht in de processen die betrokken zijn om een verrijking te vernieuwen en hoe lang het duurde om de processen uit te voeren. De verrijkingsstatus wordt ondersteund voor Experian, Leadspace, HERE Technologies, SFTP Import en Azure Maps.

1. Ga naar **Gegevens** > **Verrijking**.
1. Selecteer op het tabblad **Mijn verrijkingen** de status van de verrijking om een zijvenster te openen.
1. Vouw in het deelvenster **Voortgangsdetails** de sectie **Verrijkingen** uit.
1. Selecteer onder de verrijking waarvan u de voortgang wilt bekijken de optie **Details weergeven**.
1. Selecteer in het deelvenster **Taakdetails** de optie **Details weergeven** om de processen te bekijken die betrokken zijn bij het bijwerken van de verrijking en hun status.

## <a name="view-enrichment-results"></a>Verrijkingsresultaten bekijken

Na een voltooide verrijkingsuitvoering bekijkt u de verrijkingsresultaten.

1. Ga naar **Gegevens** > **Verrijking**.
1. Selecteer op het tabblad **Mijn verrijkingen** de verrijking die u wilt bekijken.

Alle verrijkingen tonen basisinformatie zoals het aantal verrijkte profielen en het aantal verrijkte profielen in de loop van de tijd. Op de tegel **Preview van verrijkte klanten** ziet u een voorbeeld van de gegenereerde verrijkingsentiteit. Als u een gedetailleerde weergave wilt zien, selecteert u **Meer weergeven** en daarna het tabblad **Gegevens**.

:::image type="content" source="media/enrichments-results.png" alt-text="Pagina met verrijkingsresultaten.":::

Indien beschikbaar, biedt **Aantal klanten dat wordt verrijkt per veld** een gedetailleerde beschrijving van de dekking van elk verrijkt veld.

Sommige verrijkingen tonen ook informatie die specifiek is voor het type verrijking. Zie de bijbehorende documentatie voor meer informatie.

[!INCLUDE [footer-include](includes/footer-banner.md)]
