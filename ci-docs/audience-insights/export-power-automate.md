---
title: Power Automate-connector | Microsoft Docs
description: Maak stromen in Microsoft Power Automate vanuit Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405465"
---
# <a name="power-automate-connector-preview"></a>Power Automate-connector (preview)

Activeer specifieke gebeurtenissen die automatisch moeten plaatsvinden wanneer uw gegevens veranderen en beheer complexere stromen rechtstreeks in [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Triggers voor Power Automate

U kunt verschillende triggers gebruiken waarmee u stromen kunt maken om herhaalde taken, zoals meldingen, of meer geavanceerde acties te automatiseren. 

- Trigger wanneer de vernieuwing van een gegevensbron mislukt. 
- Trigger wanneer de vernieuwing van een gegevensbron slaagt.
- Trigger wanneer een drempel voor een segment wordt overschreden. De trigger is beperkt tot het overschrijden van de drempel.
- Trigger wanneer een drempel voor een zakelijk meetcriterium wordt overschreden. De trigger is beperkt tot het overschrijden van de drempel.
- Activeren wanneer een volledige vernieuwing (van gegevensbronnen, segmenten, metingen,...) is voltooid.
- Trigger wanneer een vernieuwing van het harmoniseringsproces (toewijzen, afstemmen, samenvoegen) is voltooid.

[Configureer uw triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Acties in Power Automate
De Power Automate-connector biedt andere acties dan de beschikbare triggers. Zie voor meer informatie de [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow-in-audience-insights"></a>Een Power Automate-stroom in doelgroepinzichten maken

1. Ga in doelgroepinzichten naar **Beheer** > **Systeem**.

1. Selecteer op de pagina **Systeem** het tabblad **Status**.

1. Selecteer in de sectie **Gegevensbronnen** de optie **Stromen** en selecteer **Een stroom maken** in de vervolgkeuzelijst.
   > [!div class="mx-imgBorder"]
   > ![Power Automate-connector met actie Een stroom maken](media/power-automate-connector-create-flow.png "Power Automate-connector met actie Een stroom maken")

1. Selecteer in Power Automate een van de beschikbare triggers om uw favoriete stroom te maken. Als u uw eerste stroom maakt, moet u zich eerst verifiëren met de Power Automate-connector.
