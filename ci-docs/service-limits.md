---
title: Servicelimieten in Dynamics 365 Customer Insights
description: Begrijp limieten en beperkingen.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eba7871faf304d5945191b5b9bc215243b4f8a05
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483657"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Servicelimieten in Customer Insights-mogelijkheden

Dit artikel beschrijft de ingebouwde limieten voor de Customer Insights-service, die zijn ontworpen om de betrouwbaarheid en stabiliteit van de service te waarborgen. Verzoeken om wijzigingen kunnen worden gedaan via het [Ideeënforum](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Doelgroepinzichten

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Servicelimieten in Dynamics 365 Customer Insights-mogelijkheden voor doelgroepinzichten

| Gebied  | Limieten  | Aantekeningen |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenten en meetcriteria | 100 segmenten of metingen. | Het totale aantal actieve [segmenten](audience-insights/segments.md) en [metingen](audience-insights/measures.md) mag bij elkaar niet meer zijn dan 100.  |
| Relaties | 20 diepteniveaus bij relaties in entiteitspaden. | Wanneer u [segmenten](audience-insights/segments.md) of [meetcriteria](audience-insights/measures.md) maakt met de Builder-interface, kunnen entiteitspaden maximaal 20 relatiesprongen hebben tussen de beginentiteit en de doelentiteit.  |


## <a name="engagement-insights"></a>Betrokkenheidsinzichten

### <a name="workspace-and-event-quotas"></a>Werkruimte en gebeurtenisquota

Betrokkenheidsinzichten is een zeer schaalbare toepassing die miljoenen gebeurtenissen per seconde kan ondersteunen. Tijdens openbare preview hebben gebeurtenissen een volumedrempel. Er is ook een limiet aan het aantal werkruimten in een organisatie.

### <a name="engagement-insights-limits"></a>Limieten van betrokkenheidsinzichten

- Maximaal gebeurtenisvolume per werkruimte = 100 gebeurtenissen per seconde

- Maximaal aantal werkruimten per organisatie = 100

Wanneer gebeurtenissen de drempel overschrijden, kan dit leiden tot verlies van gegevens in rapporten op basis van die gebeurtenissen. U kunt [contact opnemen met de ondersteuning](https://go.microsoft.com/fwlink/?linkid=2145734) om een volumeverhoging aan te vragen voordat u de limieten overschrijdt. We zullen samen met u uw behoefte aan een volumeverhoging bepalen en uw verzoek ondersteunen.


[!INCLUDE[footer-include](includes/footer-banner.md)]