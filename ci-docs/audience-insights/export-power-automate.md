---
title: Power Automate-connector | Microsoft Docs
description: Maak stromen in Microsoft Power Automate vanuit Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: fb1df4e9ab1f78300b8ec1f8dfdfbfbac0e71447
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268818"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="7ff4e-103">Power Automate-connector (preview)</span><span class="sxs-lookup"><span data-stu-id="7ff4e-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="7ff4e-104">Activeer specifieke gebeurtenissen die automatisch moeten plaatsvinden wanneer uw gegevens veranderen en beheer complexere stromen rechtstreeks in [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="7ff4e-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="7ff4e-105">Triggers voor Power Automate</span><span class="sxs-lookup"><span data-stu-id="7ff4e-105">Power Automate triggers</span></span>

<span data-ttu-id="7ff4e-106">Gebruik triggers om cloudstromen te maken en routineuze taken te automatiseren, zoals meldingen of meer geavanceerde acties.</span><span class="sxs-lookup"><span data-stu-id="7ff4e-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="7ff4e-107">Trigger wanneer de vernieuwing van een gegevensbron mislukt.</span><span class="sxs-lookup"><span data-stu-id="7ff4e-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="7ff4e-108">Trigger wanneer de vernieuwing van een gegevensbron slaagt.</span><span class="sxs-lookup"><span data-stu-id="7ff4e-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="7ff4e-109">Trigger wanneer een drempel voor een segment wordt overschreden.</span><span class="sxs-lookup"><span data-stu-id="7ff4e-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="7ff4e-110">De trigger is beperkt tot het overschrijden van de drempel.</span><span class="sxs-lookup"><span data-stu-id="7ff4e-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="7ff4e-111">Trigger wanneer een drempel voor een zakelijk meetcriterium wordt overschreden.</span><span class="sxs-lookup"><span data-stu-id="7ff4e-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="7ff4e-112">De trigger is beperkt tot het overschrijden van de drempel.</span><span class="sxs-lookup"><span data-stu-id="7ff4e-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="7ff4e-113">Activeren wanneer een volledige vernieuwing (van gegevensbronnen, segmenten, metingen,...) is voltooid.</span><span class="sxs-lookup"><span data-stu-id="7ff4e-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="7ff4e-114">Trigger wanneer een vernieuwing van het harmoniseringsproces (toewijzen, afstemmen, samenvoegen) is voltooid.</span><span class="sxs-lookup"><span data-stu-id="7ff4e-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="7ff4e-115">[Configureer uw triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="7ff4e-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="7ff4e-116">Acties in Power Automate</span><span class="sxs-lookup"><span data-stu-id="7ff4e-116">Power Automate actions</span></span>
<span data-ttu-id="7ff4e-117">De Power Automate-connector biedt andere acties dan de beschikbare triggers.</span><span class="sxs-lookup"><span data-stu-id="7ff4e-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="7ff4e-118">Zie voor meer informatie de [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="7ff4e-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="7ff4e-119">Een Power Automate-stroom maken</span><span class="sxs-lookup"><span data-stu-id="7ff4e-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="7ff4e-120">Ga in doelgroepinzichten naar **Beheer** > **Exportbestemmingen**.</span><span class="sxs-lookup"><span data-stu-id="7ff4e-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="7ff4e-121">Selecteer op de tegel **Power Automate** de optie **Instellen**.</span><span class="sxs-lookup"><span data-stu-id="7ff4e-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="7ff4e-122">De Customer Insights-connector (preview) in Power Automate wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="7ff4e-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="7ff4e-123">**Meld u aan** bij Power Automate.</span><span class="sxs-lookup"><span data-stu-id="7ff4e-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="7ff4e-124">Kies een van de beschikbare triggers en voeg meer stappen toe aan uw nieuwe stroom.</span><span class="sxs-lookup"><span data-stu-id="7ff4e-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="7ff4e-125">Zie [Een cloudstroom maken in Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow)​voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="7ff4e-125">For more information, see [Create a cloud flow in Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="7ff4e-126">Voorbeelden van het gebruik van stromen:</span><span class="sxs-lookup"><span data-stu-id="7ff4e-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="7ff4e-127">Plaats een bericht op een Microsoft Teams-kanaal als een gegevensbron niet kan worden vernieuwd.</span><span class="sxs-lookup"><span data-stu-id="7ff4e-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="7ff4e-128">Stuur een e-mail naar de data-eigenaren wanneer een drempel op een segment wordt overschreden.</span><span class="sxs-lookup"><span data-stu-id="7ff4e-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]