---
title: Servicelimieten in Dynamics 365 Customer Insights
description: Begrijp limieten en beperkingen.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e2e7fc3033c25646693831d4c4c800d84ae6d6da
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641756"
---
# <a name="service-limits-in-customer-insights"></a>Servicelimieten in Customer Insights

Dit artikel beschrijft de ingebouwde limieten voor de Customer Insights-service, die zijn ontworpen om de betrouwbaarheid en stabiliteit van de service te waarborgen. Verzoeken om wijzigingen kunnen worden gedaan via het [Ideeënforum](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="customer-insights"></a>Customer Insights

| Oppervlakte  | Limieten  | Aantekeningen |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenten, metingen en voorspellingen | 300  | Het totale aantal [segmenten](segments.md), [metingen](measures.md) en [voorspellingen](predictions.md) mag samen niet boven de 300 uitkomen.  |
| Relaties | 20 diepteniveaus bij relaties in entiteitspaden. | Wanneer u [segmenten](segments.md) of [meetcriteria](measures.md) maakt met de Builder-interface, kunnen entiteitspaden maximaal 20 relatiesprongen hebben tussen de beginentiteit en de doelentiteit.  |


[!INCLUDE [footer-include](includes/footer-banner.md)]
