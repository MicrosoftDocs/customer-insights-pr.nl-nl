---
title: Power Automate-connector (preview) | Microsoft Docs
description: Maak stromen in Microsoft Power Automate vanuit Dynamics 365 Customer Insights.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196112"
---
# <a name="power-automate-connector-preview"></a>Power Automate-connector (preview)

Activeer specifieke gebeurtenissen die automatisch moeten plaatsvinden wanneer uw gegevens veranderen en beheer complexere stromen rechtstreeks in [Microsoft Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Bekende beperkingen

- maximaal 100 oproepen per 60 seconden. Gebruik de [parameter $skip](/connectors/customerinsights/#get-items-from-an-entity) om het API-eindpunt meerdere keren aan te roepen.

## <a name="power-automate-triggers"></a>Triggers voor Power Automate

Gebruik triggers om cloudstromen te maken en routineuze taken te automatiseren, zoals meldingen of meer geavanceerde acties. Gebruik triggers in de volgende gevallen:

- Als de vernieuwing van een gegevensbron mislukt.
- Als de vernieuwing van een gegevensbron lukt.
- Als een drempel voor een segment wordt overschreden. De trigger is beperkt tot het overschrijden van de drempel.
- Als een drempel voor een zakelijke meting wordt overschreden. Alleen zakelijke meetcriteria zonder een dimensie worden ondersteund. De trigger is beperkt tot het overschrijden van de drempel.
- Als een volledige geplande vernieuwing wordt voltooid. Deze trigger werkt niet voor handmatig gestarte vernieuwingen.
- Als een vernieuwing van het harmonisatieproces wordt voltooid.

[Configureer uw triggers in Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Acties in Power Automate

De Power Automate-connector biedt andere acties dan de beschikbare triggers. Zie voor meer informatie de [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Een Power Automate-stroom maken

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer op de tegel **Power Automate** de optie **Instellen**.

1. De Customer Insights-connector (preview) in Power Automate wordt geopend. **Meld u aan** bij Power Automate.

1. Kies een van de beschikbare triggers en voeg meer stappen toe aan uw nieuwe stroom. Zie [Een cloudstroom maken in Power Automate](/power-automate/get-started-logic-flow)​voor meer informatie.

Voorbeelden van het gebruik van stromen: 
- Plaats een bericht op een Microsoft Teams-kanaal als een gegevensbron niet kan worden vernieuwd. 
- Stuur een e-mail naar de data-eigenaren wanneer een drempel op een segment wordt overschreden.

[!INCLUDE [footer-include](includes/footer-banner.md)]
