---
title: Geharmoniseerde klantprofielen verrijken
description: Gebruik mogelijkheden om uw klantgegevens te verrijken.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c35e73b366fcd5db2ba5a757295ddda6db30efa0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305242"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Verrijking voor klantprofielen (preview)

Gebruik gegevens vanuit bronnen zoals Microsoft en andere partners om uw klantgegevens te verrijken.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Pagina van verrijkingshub":::

Ga in doelgroepinzichten naar **Gegevens** > **Verrijking** om te werken met verrijkingsopties.  

U hebt de machtigingen Inzender of Beheerder nodig om verrijkingen te kunnen maken of bewerken. Zie [Machtigingen](permissions.md) voor meer informatie.

Op het tabblad **Ontdekken** vindt u de volgende verrijkingen:

- [Merken](enrichment-microsoft.md) die worden geleverd door Microsoft
- [Interesses](enrichment-microsoft.md) die worden geleverd door Microsoft
- [Uitgebreide adressen](enrichment-enhanced-addresses.md) geleverd door Microsoft
- [Bedrijfsgegevens](enrichment-leadspace.md) worden verstrekt door Leadspace
- [Demografische gegevens](enrichment-experian.md) geleverd door Experian
- [Locatiegegevens](enrichment-here.md) worden geleverd door HERE Technologies
- [Aangepaste gegevens](enrichment-SFTP-custom-import.md) via Secure File Transfer Protocol (SFTP)

Op het tabblad **Mijn verrijkingen** kunt u de verrijkingen zien die u hebt geconfigureerd en hun eigenschappen bewerken.

## <a name="manage-existing-enrichments"></a>Bestaande verrijkingen beheren

Ga naar het tabblad **Mijn verrijkingen** om alle geconfigureerde verrijkingen te zien. Elke verrijking wordt weergegeven als een rij met aanvullende informatie over de verrijking.

Selecteer een verrijking om de beschikbare opties te zien. U kunt ook het beletselteken (...) in een lijstitem selecteren om de opties te zien.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opties om verrijkingen in de lijst met verrijkingen te beheren":::

- **Bekijk** verrijkingsdetails met het aantal verrijkte klantprofielen.
- **Bewerk** de verrijkingsconfiguratie.
- **Voer** de verrijking uit om klantprofielen bij te werken met de laatste gegevens.
- **Deactiveer** een bestaande verrijking om te voorkomen dat deze automatisch wordt vernieuwd bij elke geplande vernieuwing. Gegevens van de laatste geslaagde vernieuwing blijven beschikbaar. **Activeer** een inactieve verrijking om automatisch vernieuwen opnieuw te starten bij elke geplande vernieuwing.
- Een verrijking **Verwijderen**.

U kunt meerdere verrijkingen tegelijk uitvoeren of deactiveren door ze in de lijst te selecteren. Opties voor bekijken en bewerken zijn niet beschikbaar als bulkactie en werken slechts voor één verrijking tegelijk.

## <a name="enrichments-and-connections"></a>Verrijkingen en verbindingen

Verrijkingen van derden worden geconfigureerd met [verbindingen](connections.md), die een beheerder instelt met referenties en die toestemming verlenen voor gegevensoverdracht. De verbinding kan door beheerders en inzenders worden gebruikt voor het configureren van verrijkingen.  

## <a name="multiple-enrichments-of-the-same-type"></a>Meerdere verrijkingen van hetzelfde type

De entiteit die moet worden verrijkt, wordt gespecificeerd tijdens de verrijkingsconfiguratie, waardoor u de mogelijkheid hebt om slechts een subset van uw profielen te verrijken. Verrijk bijvoorbeeld alleen gegevens voor een specifiek segment. U kunt meerdere verrijkingen van hetzelfde type configureren en dezelfde verbinding opnieuw gebruiken. Sommige verrijkingen hebben limieten voor het aantal verrijkingen van hetzelfde type dat kan worden gemaakt. De limieten en het huidige gebruik zijn te zien op de pagina **Verrijking**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
