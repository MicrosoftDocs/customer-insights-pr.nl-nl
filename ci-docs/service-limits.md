---
title: Servicelimieten in Customer Insights
description: Begrijp de beperkingen en limieten in de Customer Insights SaaS-service.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 421e1aa41a54a4b8c34ac27fc7c02e510d2bb588
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387150"
---
# <a name="service-limits-in-customer-insights"></a>Servicelimieten in Customer Insights

 Customer Insights heeft ingebouwde limieten die zijn ontworpen om de betrouwbaarheid en stabiliteit van de service te waarborgen. Verzoeken om wijzigingen kunnen worden gedaan via het [Ideeënforum](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Oppervlakte  | Limieten  | Aantekeningen |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenten, metingen en voorspellingen | 300  | Het totale aantal [segmenten](segments.md), [metingen](measures.md) en [voorspellingen](predictions.md) mag samen niet boven de 300 uitkomen.  |
| Relaties | 20 diepteniveaus bij relaties in entiteitspaden. | Wanneer u [segmenten](segments.md) of [meetcriteria](measures.md) maakt met de Builder-interface, kunnen entiteitspaden maximaal 20 relatiesprongen hebben tussen de beginentiteit en de doelentiteit.  |

## <a name="fair-scheduling-of-jobs"></a>Eerlijke planning van taken

Customer Insights is een SaaS-service die gebruikmaakt van gedeelde Azure-resources. Klanten hebben vaak een werkbelasting van wisselende intensiteit en volgens verschillende planningen. Om eerlijke toegang tot de onderliggende resources te garanderen, zorgen we ervoor dat de systeemprocessen in een eerlijke volgorde worden uitgevoerd. Voorbeelden van systeemprocessen zijn taken die verband houden met gegevensharmonisatie, segmentupdates of het berekenen van metingen. De eerlijke planning beschermt u tegen wachtrijen voor resources als er een piek is in het aantal aangevraagde taken. Tegelijkertijd garandeert Customer Insights niet dat alle taken die u in de wachtrij plaatst, parallel worden verwerkt.

[!INCLUDE [footer-include](includes/footer-banner.md)]
