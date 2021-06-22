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
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095699"
---
# <a name="predictions-overview"></a><span data-ttu-id="3d5f5-103">Overzicht van voorspellingen</span><span class="sxs-lookup"><span data-stu-id="3d5f5-103">Predictions overview</span></span>

<span data-ttu-id="3d5f5-104">Dynamics 365 Customer Insights wordt geleverd met een verscheidenheid aan opties die gebruikmaken van AI en Machine Learning om gegevens te voorspellen.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="3d5f5-105">Kant-en-klare modellen</span><span class="sxs-lookup"><span data-stu-id="3d5f5-105">Out-of-box models</span></span>

<span data-ttu-id="3d5f5-106">De eenvoudigste manier om te beginnen met het voorspellen van gegevens zijn vooraf gedefinieerde modellen, vaak kant-en-klare modellen genoemd.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="3d5f5-107">Deze hebben alleen bepaalde gegevens en structuur nodig om snel inzichten te genereren.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="3d5f5-108">Momenteel zijn de volgende modellen beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="3d5f5-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="3d5f5-109">[Levensduurwaarde van klant](predict-customer-lifetime-value.md): voorspelt de potentiële omzet van een klant gedurende de gehele interactie met een bedrijf.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="3d5f5-110">[Productaanbeveling](predict-product-recommendation.md): stelt sets met voorspellende productaanbevelingen voor op basis van aankoopgedrag en klanten met vergelijkbare aankooppatronen.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="3d5f5-111">[Verloop van abonnement](predict-subscription-churn.md): voorspelt of het risico bestaat dat een klant niet langer gebruik zal maken van de abonnementsproducten of -services van uw bedrijf.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="3d5f5-112">[Transactioneel verloop](predict-transactional-churn.md) : voorspelt of een klant niet langer uw producten of services zal kopen in een bepaald tijdsbestek.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="3d5f5-113">Azure Machine Learning-integratie</span><span class="sxs-lookup"><span data-stu-id="3d5f5-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="3d5f5-114">Als een organisatie al gebruikmaakt van Machine Learning-scenario's op basis van Azure Machine Learning-experimenten, helpt de functie voor aangepaste modellen in Customer Insights om de stippen met elkaar te verbinden.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="3d5f5-115">Maak werkstromen die u helpen bij het kiezen van de gegevens waaruit u inzichten wilt genereren en koppel de resultaten aan uw geharmoniseerde klantprofielen.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="3d5f5-116">Zie [Aangepaste Machine Learning-modellen](custom-models.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="3d5f5-117">Voorspelling voor AI Builder</span><span class="sxs-lookup"><span data-stu-id="3d5f5-117">AI Builder prediction</span></span>

<span data-ttu-id="3d5f5-118">Soms zijn gegevenssets onvolledig en ontbreken er enkele waarden.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="3d5f5-119">Customer Insights kan helpen om ontbrekende waarden voor de klantentiteit en -segmenten te voorspellen.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="3d5f5-120">Zie [Uw gedeeltelijke gegevens aanvullen met voorspellingen](predictions.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3d5f5-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
