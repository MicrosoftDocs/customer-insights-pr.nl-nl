---
title: Geharmoniseerde klantprofielen verrijken
description: Gebruik mogelijkheden om uw klantgegevens te verrijken.
ms.date: 03/29/2022
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
ms.openlocfilehash: abc1b6af80e8854ee3bc930453634ef67376c4af
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800599"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Verrijking voor klantprofielen (preview)

Gebruik gegevens vanuit bronnen zoals Microsoft en andere partners om uw klantgegevens te verrijken.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Pagina van verrijkingshub.":::

Ga naar **Gegevens** > **Verrijking** om te werken met verrijkingsopties.  

U hebt de machtigingen Inzender of Beheerder nodig om verrijkingen te kunnen maken of bewerken. Zie [Machtigingen](permissions.md) voor meer informatie.

Op het tabblad **Ontdekken** vindt u alle ondersteunde verrijkingsopties.

# <a name="individual-consumers-b-to-c"></a>[Individuele consumenten (B-to-C)](#tab/b2c)

- [Merken](enrichment-microsoft.md) die worden geleverd door Microsoft
- [Interesses](enrichment-microsoft.md) die worden geleverd door Microsoft
- [Uitgebreide adressen](enrichment-enhanced-addresses.md) geleverd door Microsoft 
- [Demografische gegevens](enrichment-experian.md) geleverd door Experian
- [Aangepaste gegevens](enrichment-SFTP-custom-import.md) via Secure File Transfer Protocol (SFTP) 
- [Azure Maps](enrichment-azure-maps.md) geleverd door Microsoft
- [Locatiegegevens](enrichment-here.md) worden geleverd door HERE Technologies 
- [Identiteit](enrichment-liveramp.md) aangeboden door LiveRamp AbiliTec

# <a name="business-accounts-b-to-b"></a>[Zakelijke accounts (B-to-B)](#tab/b2b)

- [Bedrijfsgegevens](enrichment-leadspace.md) worden verstrekt door Leadspace
- [Uitgebreide adressen](enrichment-enhanced-addresses.md) geleverd door Microsoft 
- [Verbeterde bedrijfsgegevens](enrichment-enhanced-company-data.md) door Microsoft
- [Locatiegegevens](enrichment-here.md) worden geleverd door HERE Technologies 
- [Aangepaste gegevens](enrichment-SFTP-custom-import.md) via Secure File Transfer Protocol (SFTP) 
- [Azure Maps](enrichment-azure-maps.md) geleverd door Microsoft
- [Bedrijfsgegevens](enrichment-dnb.md) geleverd door Dun & Bradstreet
- [Gegevens over accountbetrokkenheid](enrichment-office.md) geleverd door Microsoft

---

Op het tabblad **Mijn verrijkingen** kunt u de verrijkingen zien die u hebt geconfigureerd en hun eigenschappen bewerken.

## <a name="manage-existing-enrichments"></a>Bestaande verrijkingen beheren

Ga naar het tabblad **Mijn verrijkingen** om alle geconfigureerde verrijkingen te zien. Elke verrijking wordt weergegeven als een rij met aanvullende informatie over de verrijking.

Selecteer de verrijking om de beschikbare opties te zien. U kunt ook het verticale weglatingsteken (&vellip;) selecteren op een lijstitem om de opties te zien. Als u verschillende verrijkingen hebt geconfigureerd, kunt u het zoekvak gebruiken om ze snel te vinden.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opties om verrijkingen in de lijst met verrijkingen te beheren.":::

- **Bekijk** verrijkingsdetails met het aantal verrijkte klantprofielen.
- **Bewerk** de verrijkingsconfiguratie.
- **Voer** de verrijking uit om klantprofielen bij te werken met de laatste gegevens.
- **Deactiveer** een bestaande verrijking om te voorkomen dat deze automatisch wordt vernieuwd bij elke geplande vernieuwing. Gegevens van de laatste geslaagde vernieuwing blijven beschikbaar. **Activeer** een inactieve verrijking om automatisch vernieuwen opnieuw te starten bij elke geplande vernieuwing.
- De verrijking **Verwijderen**.

Voer meerdere verrijkingen tegelijk uit of deactiveer ze door ze in de lijst te selecteren. Opties voor weergeven en bewerken zijn niet beschikbaar als bulkactie. Ze werken maar voor één verrijking tegelijk.

## <a name="enrichments-and-connections"></a>Verrijkingen en verbindingen

Verrijkingen van derden worden geconfigureerd met [verbindingen](connections.md), die een beheerder instelt met referenties en die toestemming verlenen voor gegevensoverdracht. Deze verbindingen kunnen worden gebruikt door beheerders en inzenders om verrijkingen te configureren.  

## <a name="multiple-enrichments-of-the-same-type"></a>Meerdere verrijkingen van hetzelfde type

De entiteit die moet worden verrijkt, wordt gespecificeerd tijdens de verrijkingsconfiguratie, waardoor u de mogelijkheid hebt om slechts een subset van uw profielen te verrijken. Verrijk bijvoorbeeld alleen gegevens voor een specifiek segment. U kunt meerdere verrijkingen van hetzelfde type configureren en dezelfde verbinding opnieuw gebruiken. Sommige verrijkingen hebben limieten voor het aantal verrijkingen van hetzelfde type dat kan worden gemaakt. De limieten en het huidige gebruik zijn te zien op de pagina **Verrijking**.

## <a name="enrich-data-sources-before-unification"></a>Gegevensbronnen verrijken vóór harmonisatie

U kunt uw klantgegevens verrijken vóór gegevensharmonisatie om de kwaliteit van een gegevensmatch te helpen verbeteren. Zie [Verrijking voor gegevensbronnen](data-sources-enrichment.md) voor meer informatie.

## <a name="see-the-progress-of-the-enrichment-process"></a>De voortgang van het verrijkingsproces bekijken

U kunt details over de verwerking van een verrijking vinden, inclusief de bijbehorende status en mogelijke problemen, tijdens het vernieuwen of nadat een vernieuwing is voltooid. Krijg inzicht in de processen die betrokken zijn om een verrijking te vernieuwen en hoe lang het duurde om de processen uit te voeren. De verrijkingsstatus wordt ondersteund voor Experian, Leadspace, HERE Technologies, SFTP Import en Azure Maps.

De status van een verrijking weergeven

1. Ga naar **Gegevens** > **Verrijking**. 
1. Selecteer op het tabblad **Mijn verrijkingen** de status van een verrijking om een zijvenster te openen. 
1. Vouw in het deelvenster **Voortgangsdetails** de sectie **Verrijkingen** uit. 
1. Selecteer onder de verrijking waarvan u de voortgang wilt bekijken de optie **Details weergeven**. 
1. Selecteer in het deelvenster **Taakdetails** de optie **Details weergeven** om de processen te bekijken die betrokken zijn bij het bijwerken van de verrijking en hun status. 

## <a name="enrichment-results"></a>Verrijkingsresultaten

Na een voltooide verrijkingsuitvoering kunt u de verrijkingsresultaten bekijken.

1. Ga naar **Gegevens** > **Verrijking**. 
1. Selecteer de verrijking waarover u informatie wilt.

Alle verrijkingen tonen basisinformatie zoals het aantal verrijkte profielen, een voorbeeld van de gegenereerde verrijkingsentiteit en het aantal verrijkte profielen in de loop van de tijd. Indien beschikbaar, biedt **Aantal klanten dat wordt verrijkt per veld** een gedetailleerde beschrijving van de dekking van elk verrijkt veld.

:::image type="content" source="media/enrichments-results.png" alt-text="Pagina met verrijkingsresultaten.":::

Sommige verrijkingen tonen ook informatie die specifiek is voor het type verrijking. Raadpleeg de documentatie bij de desbetreffende verrijking voor meer informatie.


[!INCLUDE [footer-include](includes/footer-banner.md)]
