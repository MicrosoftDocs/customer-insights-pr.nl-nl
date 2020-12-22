---
title: Geharmoniseerde klantprofielen verrijken
description: Gebruik mogelijkheden om uw klantgegevens te verrijken.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c25cfbf3808fc1534b54d2d834f1c63ff4c9fe0a
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667088"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Verrijking voor klantprofielen (preview)

Gebruik gegevens vanuit bronnen zoals Microsoft en andere partners om uw klantgegevens te verrijken.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Pagina van verrijkingshub":::

Ga in doelgroepinzichten naar **Gegevens** > **Verrijking** om te werken met verrijkingsopties.    
U hebt de machtigingen Inzender of Beheerder nodig om verrijkingen te kunnen maken of bewerken. Zie [Machtigingen](permissions.md) voor meer informatie.

Op het tabblad **Ontdekken** vindt u de volgende verrijkingen:

- [Merken](enrichment-microsoft-graph.md) die worden verstrekt door Microsoft Graph
- [Interesses](enrichment-microsoft-graph.md) die worden verstrekt door Microsoft Graph
- [Bedrijfsgegevens](enrichment-leadspace.md) worden verstrekt door Leadspace
- [Demografische gegevens](enrichment-experian.md) die worden geleverd door Experian
- [Locatiegegevens](enrichment-here.md) worden geleverd door HERE Technologies
- [Aangepaste gegevens](enrichment-SFTP-custom-import.md) via Secure File Transfer Protocol (SFTP)

Op het tabblad **Mijn verrijkingen** kunt u de verrijkingen zien die u hebt geconfigureerd en hun eigenschappen bewerken.

## <a name="manage-existing-enrichments"></a>Bestaande verrijkingen beheren

Ga naar **Mijn verrijkingen** om alle geconfigureerde verrijkingen te zien. Elke verrijking wordt weergegeven als een rij met aanvullende informatie over de verrijking.

Selecteer een verrijking om de beschikbare opties te zien. U kunt ook het beletselteken (...) op een lijstitem selecteren om de opties te zien.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opties om verrijkingen in de lijst met verrijkingen te beheren":::

- **Bekijk** verrijkingsdetails met het aantal verrijkte klantprofielen.
- **Bewerk** de verrijkingsconfiguratie.
- **Voer** de verrijking uit om klantprofielen bij te werken met de laatste gegevens.
- **Deactiveer** een bestaande verrijking om te voorkomen dat deze automatisch wordt vernieuwd bij elke geplande vernieuwing. Gegevens van de laatste geslaagde vernieuwing blijven beschikbaar. **Activeer** een inactieve verrijking om automatisch vernieuwen opnieuw te starten bij elke geplande vernieuwing.
- Een verrijking **Verwijderen**.

U kunt meerdere verrijkingen tegelijk uitvoeren of deactiveren door ze in de lijst te selecteren. Opties voor bekijken en bewerken zijn niet beschikbaar als bulkactie en werken slechts voor één verrijking tegelijk.
