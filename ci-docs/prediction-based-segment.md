---
title: Een segment maken op basis van een voorspellingsmodel
description: Maak segmenten op basis van de uitvoerentiteit van een voorspellingsmodel.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: d67594f2467c1a0fde84b1ba0bd1afa4025e7b71
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081055"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>Een segment maken op basis van een voorspellingsmodel (preview)

De resultaten van voorspellingen gelden soms alleen voor een deel van uw klanten. Verhoog de personalisatie van aanbevelingen door segmenten te maken op basis van resultaten van voorspellingsmodellen. U wilt bijvoorbeeld specifieke aanbevelingen doen aan klanten die de voorkeur geven aan een bepaald type service. 

## <a name="prerequisites"></a>Vereisten

- Minimaal [inzendermachtigingen](permissions.md) in Customer Insights.

- Een model voor productaanbevelingen, transactieverloop, abonnementverloop of de waarde voor de levensduur van klanten geconfigureerd in Customer Insights. Bekijk de vereisten om de verschillende modellen in te stellen:

  - [Productaanbevelingsmodel](predict-product-recommendation.md)
  - [Verloopmodel van abonnement](predict-subscription-churn.md)
  - [Transactieverloopmodel](predict-transactional-churn.md)
  - [Model voor waarde voor levensduur van klant](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>Een klantsegment maken op basis van een voorspellingen

1. Ga naar **Intelligence** > **Voorspellingen** en selecteer het tabblad **Mijn voorspellingen**.

1. Selecteer de verticale ellipsen naast het model dat u wilt bekijken en selecteer **Weergeven**.

1. Selecteer op de resultatenpagina de optie **Segment maken**. Bekijk het artikel over het model voor meer informatie over de resultatenpagina.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Schermopname van de pagina met voorspellingsresultaten met markering op de actie Segment maken.":::

1. Maak een nieuw segment op basis van de uitvoerentiteit van het geselecteerde model. Zie [Segmenten maken en beheren](segments.md) voor meer informatie.