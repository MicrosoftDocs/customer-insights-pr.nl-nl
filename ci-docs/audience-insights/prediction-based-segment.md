---
title: Segmenten op basis van voorspellingsuitvoer
description: Maak segmenten op basis van de uitvoerentiteit van een voorspellingsmodel.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741423"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="03ba3-103">Een segment maken op basis van een voorspellingsmodel (preview)</span><span class="sxs-lookup"><span data-stu-id="03ba3-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="03ba3-104">De resultaten van voorspellingen gelden soms alleen voor een deel van uw klanten.</span><span class="sxs-lookup"><span data-stu-id="03ba3-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="03ba3-105">Verhoog de personalisatie van aanbevelingen door segmenten te maken op basis van resultaten van voorspellingsmodellen.</span><span class="sxs-lookup"><span data-stu-id="03ba3-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="03ba3-106">U wilt bijvoorbeeld specifieke aanbevelingen doen aan klanten die de voorkeur geven aan een bepaald type service.</span><span class="sxs-lookup"><span data-stu-id="03ba3-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="03ba3-107">Vereisten</span><span class="sxs-lookup"><span data-stu-id="03ba3-107">Prerequisites</span></span>

- <span data-ttu-id="03ba3-108">Minimaal [inzendermachtigingen](permissions.md) in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="03ba3-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="03ba3-109">Een model voor productaanbevelingen, transactieverloop, abonnementverloop of de waarde voor de levensduur van klanten geconfigureerd in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="03ba3-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="03ba3-110">Bekijk de vereisten om de verschillende modellen in te stellen:</span><span class="sxs-lookup"><span data-stu-id="03ba3-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="03ba3-111">Productaanbevelingsmodel</span><span class="sxs-lookup"><span data-stu-id="03ba3-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="03ba3-112">Verloopmodel van abonnement</span><span class="sxs-lookup"><span data-stu-id="03ba3-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="03ba3-113">Transactieverloopmodel</span><span class="sxs-lookup"><span data-stu-id="03ba3-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="03ba3-114">Model voor waarde voor levensduur van klant</span><span class="sxs-lookup"><span data-stu-id="03ba3-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="03ba3-115">Een klantsegment maken op basis van een voorspellingen</span><span class="sxs-lookup"><span data-stu-id="03ba3-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="03ba3-116">Ga naar **Intelligence** > **Voorspellingen** en selecteer het tabblad **Mijn voorspellingen**.</span><span class="sxs-lookup"><span data-stu-id="03ba3-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="03ba3-117">Selecteer de verticale ellipsen naast het model dat u wilt bekijken en selecteer **Weergeven**.</span><span class="sxs-lookup"><span data-stu-id="03ba3-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="03ba3-118">Selecteer op de resultatenpagina de optie **Segment maken**.</span><span class="sxs-lookup"><span data-stu-id="03ba3-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="03ba3-119">Bekijk het artikel over het model voor meer informatie over de resultatenpagina.</span><span class="sxs-lookup"><span data-stu-id="03ba3-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Schermopname van de pagina met voorspellingsresultaten met markering op de actie Segment maken.":::

1. <span data-ttu-id="03ba3-121">Maak een nieuw segment op basis van de uitvoerentiteit van het geselecteerde model.</span><span class="sxs-lookup"><span data-stu-id="03ba3-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="03ba3-122">Zie [Segmenten maken en beheren](segments.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="03ba3-122">For more information, see [Create and manage segments](segments.md).</span></span>