---
title: Power Automate-connector | Microsoft Docs
description: Maak stromen in Microsoft Power Automate vanuit Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 409792bc3f12fca451ef038e3300758bdf9ecf3b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646338"
---
# <a name="power-automate-connector-preview"></a>Power Automate-connector (preview)

Activeer specifieke gebeurtenissen die automatisch moeten plaatsvinden wanneer uw gegevens veranderen en beheer complexere stromen rechtstreeks in [Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Bekende beperkingen

- U kunt maximaal 100 oproepen per 60 seconden uitvoeren. U kunt het API-eindpunt meerdere keren aanroepen door de parameter $skip te gebruiken. [Meer informatie over de parameter $skip](/connectors/customerinsights/#get-items-from-an-entity).

## <a name="power-automate-triggers"></a>Triggers voor Power Automate

Gebruik triggers om cloudstromen te maken en routineuze taken te automatiseren, zoals meldingen of meer geavanceerde acties. 

- Trigger wanneer de vernieuwing van een gegevensbron mislukt. 
- Trigger wanneer de vernieuwing van een gegevensbron slaagt.
- Trigger wanneer een drempel voor een segment wordt overschreden. De trigger is beperkt tot het overschrijden van de drempel.
- Trigger wanneer een drempel voor een zakelijk meetcriterium wordt overschreden. Alleen zakelijke meetcriteria zonder een dimensie worden ondersteund. De trigger is beperkt tot het overschrijden van de drempel.
- Trigger wanneer een volledige vernieuwing (van gegevensbronnen, segmenten, meetcriteria etc.) is voltooid.
- Trigger wanneer een vernieuwing van het harmoniseringsproces (toewijzen, afstemmen, samenvoegen) is voltooid.

[Configureer uw triggers in Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Acties in Power Automate

De Power Automate-connector biedt andere acties dan de beschikbare triggers. Zie voor meer informatie de [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Een Power Automate-stroom maken

1. Ga naar **Beheer** > **Exportbestemmingen**.

1. Selecteer op de tegel **Power Automate** de optie **Instellen**.

1. De Customer Insights-connector (preview) in Power Automate wordt geopend. **Meld u aan** bij Power Automate.

1. Kies een van de beschikbare triggers en voeg meer stappen toe aan uw nieuwe stroom. Zie [Een cloudstroom maken in Power Automate](/power-automate/get-started-logic-flow)​voor meer informatie.

Voorbeelden van het gebruik van stromen: 
- Plaats een bericht op een Microsoft Teams-kanaal als een gegevensbron niet kan worden vernieuwd. 
- Stuur een e-mail naar de data-eigenaren wanneer een drempel op een segment wordt overschreden.



[!INCLUDE [footer-include](includes/footer-banner.md)]
