---
title: Overzicht over ondersteunde voorspellingsscenario's
description: Voorspellingsscenario's en opties die worden gedekt door de Dynamics 365 Customer Insights-toepassing.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: b73046844f6009a2b163b5eaadf5f63f75cda1d8
ms.sourcegitcommit: b78c9680b213204e6b0ed47f0147205083f6a98f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "6539155"
---
# <a name="predictions-overview"></a>Overzicht van voorspellingen

Dynamics 365 Customer Insights wordt geleverd met een verscheidenheid aan opties die gebruikmaken van AI en Machine Learning om gegevens te voorspellen. 

## <a name="out-of-box-models"></a>Kant-en-klare modellen

De eenvoudigste manier om te beginnen met het voorspellen van gegevens zijn vooraf gedefinieerde modellen, vaak kant-en-klare modellen genoemd. Deze hebben alleen bepaalde gegevens en structuur nodig om snel inzichten te genereren. Momenteel zijn de volgende modellen beschikbaar: 
- [Levensduurwaarde van klant](predict-customer-lifetime-value.md): voorspelt de potentiële omzet van een klant gedurende de gehele interactie met een bedrijf. 
- [Productaanbeveling](predict-product-recommendation.md): stelt sets met voorspellende productaanbevelingen voor op basis van aankoopgedrag en klanten met vergelijkbare aankooppatronen.
- [Verloop van abonnement](predict-subscription-churn.md): voorspelt of het risico bestaat dat een klant niet langer gebruik zal maken van de abonnementsproducten of -services van uw bedrijf.
- [Transactioneel verloop](predict-transactional-churn.md) : voorspelt of een klant niet langer uw producten of services zal kopen in een bepaald tijdsbestek.

## <a name="azure-machine-learning-integration"></a>Azure Machine Learning-integratie

Als een organisatie al gebruikmaakt van Machine Learning-scenario's op basis van Azure Machine Learning-experimenten, helpt de functie voor aangepaste modellen in Customer Insights om de stippen met elkaar te verbinden. Maak werkstromen die u helpen bij het kiezen van de gegevens waaruit u inzichten wilt genereren en koppel de resultaten aan uw geharmoniseerde klantprofielen. Zie [Aangepaste Machine Learning-modellen](custom-models.md) voor meer informatie.

## <a name="ai-builder-prediction"></a>Voorspelling voor AI Builder

Soms zijn gegevenssets onvolledig en ontbreken er enkele waarden. Customer Insights kan helpen om ontbrekende waarden voor de klantentiteit en -segmenten te voorspellen. Zie [Uw gedeeltelijke gegevens aanvullen met voorspellingen](predictions.md) voor meer informatie.
