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
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350401"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Servicelimieten in Customer Insights-mogelijkheden

Dit artikel beschrijft de ingebouwde limieten voor de Customer Insights-service, die zijn ontworpen om de betrouwbaarheid en stabiliteit van de service te waarborgen. Verzoeken om wijzigingen kunnen worden gedaan via het [Ideeënforum](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Doelgroepinzichten

| Oppervlakte  | Limieten  | Aantekeningen |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenten, metingen en voorspellingen | 300  | Het totale aantal [segmenten](audience-insights/segments.md), [metingen](audience-insights/measures.md) en [voorspellingen](audience-insights/predictions.md) mag samen niet boven de 300 uitkomen.  |
| Relaties | 20 diepteniveaus bij relaties in entiteitspaden. | Wanneer u [segmenten](audience-insights/segments.md) of [meetcriteria](audience-insights/measures.md) maakt met de Builder-interface, kunnen entiteitspaden maximaal 20 relatiesprongen hebben tussen de beginentiteit en de doelentiteit.  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
