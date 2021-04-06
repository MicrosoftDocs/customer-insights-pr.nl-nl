---
title: Power Automate-connector | Microsoft Docs
description: Maak stromen in Microsoft Power Automate vanuit Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e973bb11b31c9e70b695ebec8aa2700fdaa5e44f
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597919"
---
# <a name="power-automate-connector-preview"></a>Power Automate-connector (preview)

Activeer specifieke gebeurtenissen die automatisch moeten plaatsvinden wanneer uw gegevens veranderen en beheer complexere stromen rechtstreeks in [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Triggers voor Power Automate

Gebruik triggers om cloudstromen te maken en routineuze taken te automatiseren, zoals meldingen of meer geavanceerde acties. 

- Trigger wanneer de vernieuwing van een gegevensbron mislukt. 
- Trigger wanneer de vernieuwing van een gegevensbron slaagt.
- Trigger wanneer een drempel voor een segment wordt overschreden. De trigger is beperkt tot het overschrijden van de drempel.
- Trigger wanneer een drempel voor een zakelijk meetcriterium wordt overschreden. De trigger is beperkt tot het overschrijden van de drempel.
- Activeren wanneer een volledige vernieuwing (van gegevensbronnen, segmenten, metingen,...) is voltooid.
- Trigger wanneer een vernieuwing van het harmoniseringsproces (toewijzen, afstemmen, samenvoegen) is voltooid.

[Configureer uw triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Acties in Power Automate
De Power Automate-connector biedt andere acties dan de beschikbare triggers. Zie voor meer informatie de [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Een Power Automate-stroom maken

1. Ga in doelgroepinzichten naar **Beheer** > **Exportbestemmingen**.

1. Selecteer op de tegel **Power Automate** de optie **Instellen**.

1. De Customer Insights-connector (preview) in Power Automate wordt geopend. **Meld u aan** bij Power Automate.

1. Kies een van de beschikbare triggers en voeg meer stappen toe aan uw nieuwe stroom. Zie [Een cloudstroom maken in Power Automate](/power-automate/get-started-logic-flow)​voor meer informatie.

Voorbeelden van het gebruik van stromen: 
- Plaats een bericht op een Microsoft Teams-kanaal als een gegevensbron niet kan worden vernieuwd. 
- Stuur een e-mail naar de data-eigenaren wanneer een drempel op een segment wordt overschreden.



[!INCLUDE[footer-include](../includes/footer-banner.md)]