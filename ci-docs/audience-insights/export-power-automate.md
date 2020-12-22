---
title: Power Automate-connector | Microsoft Docs
description: Maak stromen in Microsoft Power Automate vanuit Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405465"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="5c8a6-103">Power Automate-connector (preview)</span><span class="sxs-lookup"><span data-stu-id="5c8a6-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="5c8a6-104">Activeer specifieke gebeurtenissen die automatisch moeten plaatsvinden wanneer uw gegevens veranderen en beheer complexere stromen rechtstreeks in [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="5c8a6-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="5c8a6-105">Triggers voor Power Automate</span><span class="sxs-lookup"><span data-stu-id="5c8a6-105">Power Automate triggers</span></span>

<span data-ttu-id="5c8a6-106">U kunt verschillende triggers gebruiken waarmee u stromen kunt maken om herhaalde taken, zoals meldingen, of meer geavanceerde acties te automatiseren.</span><span class="sxs-lookup"><span data-stu-id="5c8a6-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="5c8a6-107">Trigger wanneer de vernieuwing van een gegevensbron mislukt.</span><span class="sxs-lookup"><span data-stu-id="5c8a6-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="5c8a6-108">Trigger wanneer de vernieuwing van een gegevensbron slaagt.</span><span class="sxs-lookup"><span data-stu-id="5c8a6-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="5c8a6-109">Trigger wanneer een drempel voor een segment wordt overschreden.</span><span class="sxs-lookup"><span data-stu-id="5c8a6-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="5c8a6-110">De trigger is beperkt tot het overschrijden van de drempel.</span><span class="sxs-lookup"><span data-stu-id="5c8a6-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="5c8a6-111">Trigger wanneer een drempel voor een zakelijk meetcriterium wordt overschreden.</span><span class="sxs-lookup"><span data-stu-id="5c8a6-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="5c8a6-112">De trigger is beperkt tot het overschrijden van de drempel.</span><span class="sxs-lookup"><span data-stu-id="5c8a6-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="5c8a6-113">Activeren wanneer een volledige vernieuwing (van gegevensbronnen, segmenten, metingen,...) is voltooid.</span><span class="sxs-lookup"><span data-stu-id="5c8a6-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="5c8a6-114">Trigger wanneer een vernieuwing van het harmoniseringsproces (toewijzen, afstemmen, samenvoegen) is voltooid.</span><span class="sxs-lookup"><span data-stu-id="5c8a6-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="5c8a6-115">[Configureer uw triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="5c8a6-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="5c8a6-116">Acties in Power Automate</span><span class="sxs-lookup"><span data-stu-id="5c8a6-116">Power Automate actions</span></span>
<span data-ttu-id="5c8a6-117">De Power Automate-connector biedt andere acties dan de beschikbare triggers.</span><span class="sxs-lookup"><span data-stu-id="5c8a6-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="5c8a6-118">Zie voor meer informatie de [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="5c8a6-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="5c8a6-119">Een Power Automate-stroom in doelgroepinzichten maken</span><span class="sxs-lookup"><span data-stu-id="5c8a6-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="5c8a6-120">Ga in doelgroepinzichten naar **Beheer** > **Systeem**.</span><span class="sxs-lookup"><span data-stu-id="5c8a6-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="5c8a6-121">Selecteer op de pagina **Systeem** het tabblad **Status**.</span><span class="sxs-lookup"><span data-stu-id="5c8a6-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="5c8a6-122">Selecteer in de sectie **Gegevensbronnen** de optie **Stromen** en selecteer **Een stroom maken** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="5c8a6-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5c8a6-123">![Power Automate-connector met actie Een stroom maken](media/power-automate-connector-create-flow.png "Power Automate-connector met actie Een stroom maken")</span><span class="sxs-lookup"><span data-stu-id="5c8a6-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="5c8a6-124">Selecteer in Power Automate een van de beschikbare triggers om uw favoriete stroom te maken.</span><span class="sxs-lookup"><span data-stu-id="5c8a6-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="5c8a6-125">Als u uw eerste stroom maakt, moet u zich eerst verifiëren met de Power Automate-connector.</span><span class="sxs-lookup"><span data-stu-id="5c8a6-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
