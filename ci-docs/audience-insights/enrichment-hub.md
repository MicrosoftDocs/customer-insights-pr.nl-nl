---
title: Geharmoniseerde klantprofielen verrijken
description: Gebruik mogelijkheden om uw klantgegevens te verrijken.
ms.date: 11/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 36e6f7f8fcd64fc2591e913910918b83bf27567b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597689"
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


[!INCLUDE[footer-include](../includes/footer-banner.md)]