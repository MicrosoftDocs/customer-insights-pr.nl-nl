---
title: Metingen begrijpen en beheren
description: Ontdek hoe metingen helpen bij het analyseren en weergeven van de prestaties van uw bedrijf.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: c46fcc3baba1d6c92c2c0fe459a62277343cc0e4
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359767"
---
# <a name="measures-overview"></a>Overzicht van metingen

Meetcriteria helpen u het klantgedrag en de bedrijfsprestaties beter te begrijpen. Ze kijken naar relevante waarden uit [geharmoniseerde profielen](data-unification.md). Een bedrijf wil bijvoorbeeld de *totale uitgaven per klant* bekijken om de aankoopgeschiedenis van een individuele klant te begrijpen of de *totale omzet van het bedrijf* meten om inzicht te krijgen in de omzet op geaggregeerd niveau in het hele bedrijf.  

Metingen worden gemaakt [met behulp van de metingbouwer](measure-builder.md), een gegevensqueryplatform met verschillende operators en eenvoudige toewijzingsopties. Hiermee kunt u de gegevens filteren, resultaten groeperen, [entiteitsrelatiepaden](relationships.md) detecteren en een voorbeeld van de uitvoer bekijken. U kunt [vooraf gedefinieerde sjablonen gebruiken](measure-templates.md) om efficiënt veelgebruikte metingen te configureren.

Gebruik de opbouwfunctie voor meetcriteria om bedrijfsactiviteiten te plannen door klantgegevens op te vragen en inzichten te verkrijgen. Als u bijvoorbeeld een meetcriterium maakt van *totale uitgaven per klant* en *totaal rendement per klant*, helpt dit u een groep klanten met hoge uitgaven en toch een hoog rendement te identificeren. U kunt [een segment maken](segments.md) op basis van deze metingen, om de volgende beste acties aan te sturen. 

## <a name="manage-your-measures"></a>Uw meetcriteria beheren

U vindt de lijst met meetcriteria op de pagina **Meetcriteria**.

U vindt informatie over het type meetcriterium, de maker, de datum waarop het meetcriterium is gemaakt en de status. Wanneer u een meetcriterium uit de lijst selecteert, kunt u een voorbeeld van de uitvoer bekijken en een CSV-bestand downloaden.

Selecteer om al uw meetcriteria tegelijkertijd te vernieuwen de optie **Alles vernieuwen** zonder een specifiek meetcriterium te selecteren.

:::image type="content" source="media/measure-actions.png" alt-text="Acties om afzonderlijke meetcriteria te beheren.":::

Selecteer een meetcriterium in de lijst voor de volgende opties:

- Selecteer de naam van het meetcriterium om de details te zien.
- **Bewerk** de configuratie van het meetcriterium.
- **Vernieuw** het meetcriterium op basis van de laatste gegevens.
- **Hernoem** het meetcriterium.
- **Verwijder** het meetcriterium.
- **Activeren** of **Deactiveren**. Inactieve meetcriteria worden niet vernieuwd tijdens een [geplande vernieuwing](system.md#schedule-tab)​.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="next-step"></a>Volgende stap

U kunt bestaande meetcriteria gebruiken om [een klantsegment](segments.md) te maken.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
