---
title: Servicelimieten in Customer Insights
description: Begrijp de beperkingen en limieten in de Customer Insights SaaS-service.
ms.date: 05/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6d1b761a5c9f67bfdc7c5b152132c618db3ea36a
ms.sourcegitcommit: 78ef22cd39a1ebd7525f96829cd79d95f34438b9
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/07/2022
ms.locfileid: "8940662"
---
# <a name="service-limits-in-customer-insights"></a>Servicelimieten in Customer Insights

Dit artikel beschrijft de ingebouwde limieten voor de Customer Insights-service, die zijn ontworpen om de betrouwbaarheid en stabiliteit van de service te waarborgen. Verzoeken om wijzigingen kunnen worden gedaan via het [Ideeënforum](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Oppervlakte  | Limieten  | Aantekeningen |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenten, metingen en voorspellingen | 300  | Het totale aantal [segmenten](segments.md), [metingen](measures.md) en [voorspellingen](predictions.md) mag samen niet boven de 300 uitkomen.  |
| Relaties | 20 diepteniveaus bij relaties in entiteitspaden. | Wanneer u [segmenten](segments.md) of [meetcriteria](measures.md) maakt met de Builder-interface, kunnen entiteitspaden maximaal 20 relatiesprongen hebben tussen de beginentiteit en de doelentiteit.  |

## <a name="fair-scheduling-of-jobs"></a>Eerlijke planning van taken

Customer Insights is een SaaS-service die gebruikmaakt van gedeelde Azure-resources. Klanten hebben vaak een werkbelasting van wisselende intensiteit en volgens verschillende planningen. Om eerlijke toegang tot de onderliggende resources te garanderen, zorgen we ervoor dat de systeemprocessen in een eerlijke volgorde worden uitgevoerd. Voorbeelden van systeemprocessen zijn taken die verband houden met gegevensharmonisatie, segmentupdates of het berekenen van metingen. De eerlijke planning beschermt u tegen wachtrijen voor resources als er een piek is in het aantal aangevraagde taken. Tegelijkertijd garandeert Customer Insights niet dat alle taken die u in de wachtrij plaatst, parallel worden verwerkt.

[!INCLUDE [footer-include](includes/footer-banner.md)]
