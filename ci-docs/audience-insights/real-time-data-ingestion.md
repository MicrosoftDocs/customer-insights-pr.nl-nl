---
title: Realtime gegevensopname en beperkingen
description: Algemene informatie over realtime mogelijkheden in doelgroepinzichten.
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7421ed9d2cb399d546815b2d1b0ea5ec51ca6b6d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270274"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="096fa-103">Realtime gegevensopname (preview)</span><span class="sxs-lookup"><span data-stu-id="096fa-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="096fa-104">Dankzij de bijna-realtime functionaliteit kunt u binnen enkele seconden de meest recente interacties zien die uw klanten hebben gehad met uw producten of services.</span><span class="sxs-lookup"><span data-stu-id="096fa-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="096fa-105">[Geplande vernieuwingen](system.md#schedule-tab) omvatten grote aantallen records en verschillende complexe bewerkingen.</span><span class="sxs-lookup"><span data-stu-id="096fa-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="096fa-106">Eerst worden gegevens opgehaald uit de gegevensbron.</span><span class="sxs-lookup"><span data-stu-id="096fa-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="096fa-107">Vervolgens worden de gegevens geharmoniseerd en vervolgens verrijkt met aanvullende informatie.</span><span class="sxs-lookup"><span data-stu-id="096fa-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="096fa-108">Elke uitvoering van dit proces kan minuten tot uren duren.</span><span class="sxs-lookup"><span data-stu-id="096fa-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="096fa-109">De realtime functionaliteit levert gegevens onmiddellijk op voor verbruik, totdat de volgende geplande vernieuwing deze gegevens uit de gegevensbron haalt.</span><span class="sxs-lookup"><span data-stu-id="096fa-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="096fa-110">Realtime updates hebben een vervaltijd waarna ze de waarde in de gegevensbron niet langer overschrijven:</span><span class="sxs-lookup"><span data-stu-id="096fa-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="096fa-111">Profielupdates worden 4 uur bewaard</span><span class="sxs-lookup"><span data-stu-id="096fa-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="096fa-112">Activiteiten worden 30 dagen bewaard</span><span class="sxs-lookup"><span data-stu-id="096fa-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="096fa-113">Deze waarden zijn API-aanroepparameters die u kunt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="096fa-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="096fa-114">Zij hebben tot doel ervoor te zorgen dat uw brongegevens uw bron van waarheid blijven.</span><span class="sxs-lookup"><span data-stu-id="096fa-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="096fa-115">Als u wilt dat realtime updates langer worden opgenomen, moet u ze toevoegen aan een gegevensbron, zodat ze worden opgehaald tijdens de volgende geplande vernieuwing.</span><span class="sxs-lookup"><span data-stu-id="096fa-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="096fa-116">Realtime update van de geharmoniseerde klantprofielvelden</span><span class="sxs-lookup"><span data-stu-id="096fa-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="096fa-117">Bijgewerkte profielen worden binnen enkele seconden weergegeven in de klantenkaartweergave of in een andere visualisatie.</span><span class="sxs-lookup"><span data-stu-id="096fa-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="096fa-118">Omdat realtime bewerkingen plaatsvinden nadat de gegevensharmonisatie heeft plaatsgevonden, zijn ze alleen van toepassing op de geharmoniseerde klantprofielen.</span><span class="sxs-lookup"><span data-stu-id="096fa-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="096fa-119">Bijgevolg worden met realtime profielwijzigingen geen meetcriteria, het lidmaatschap van segmenten of verrijkingen worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="096fa-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="096fa-120">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="096fa-120">Limitations</span></span>

- <span data-ttu-id="096fa-121">Klantprofielen kunnen worden bijgewerkt, maar niet gemaakt of verwijderd.</span><span class="sxs-lookup"><span data-stu-id="096fa-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="096fa-122">Het exporteren van realtime updates naar externe systemen, zoals Power BI, is momenteel niet mogelijk.</span><span class="sxs-lookup"><span data-stu-id="096fa-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="096fa-123">In realtime activiteiten maken</span><span class="sxs-lookup"><span data-stu-id="096fa-123">Real-time creation of activities</span></span>

<span data-ttu-id="096fa-124">Met de realtime API kunt u een nieuwe activiteit van uw bronsysteem (een individueel bronrecord) naar een geharmoniseerd klantprofiel publiceren.</span><span class="sxs-lookup"><span data-stu-id="096fa-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="096fa-125">De nieuwe activiteit zal binnen enkele seconden beschikbaar zijn als een geharmoniseerde activiteit in de tijdlijn van dat geharmoniseerde klantprofiel.</span><span class="sxs-lookup"><span data-stu-id="096fa-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="096fa-126">U kunt de tijdlijn zien in de klantenkaartweergave of een andere tijdlijnintegratie die u hebt geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="096fa-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="096fa-127">Activiteiten zijn onveranderlijk.</span><span class="sxs-lookup"><span data-stu-id="096fa-127">Activities are immutable.</span></span> <span data-ttu-id="096fa-128">Zij veranderen niet nadat ze zijn gemaakt.</span><span class="sxs-lookup"><span data-stu-id="096fa-128">They don't change once created.</span></span>
> - <span data-ttu-id="096fa-129">Momenteel worden segmenten en meetcriteria niet bijgewerkt op basis van de nieuwe activiteit.</span><span class="sxs-lookup"><span data-stu-id="096fa-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="096fa-130">Activiteiten die alleen zijn toegevoegd via de realtime API, maken geen deel uit van exports en worden niet weergegeven in PowerBI.</span><span class="sxs-lookup"><span data-stu-id="096fa-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="096fa-131">Er zijn twee manieren om verbinding te maken met de realtime API:</span><span class="sxs-lookup"><span data-stu-id="096fa-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="096fa-132">[indirect](#connect-via-the-dynamics-365-customer-insights-connector), door gebruik te maken van de [Dynamics 365 Customer Insights-connector](https://docs.microsoft.com/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="096fa-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/)</span></span>
- <span data-ttu-id="096fa-133">[direct](#connect-directly-to-the-real-time-api), met code</span><span class="sxs-lookup"><span data-stu-id="096fa-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="096fa-134">Voor beide manieren gelden de volgende vereisten:</span><span class="sxs-lookup"><span data-stu-id="096fa-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="096fa-135">Een Customer Insights-omgeving</span><span class="sxs-lookup"><span data-stu-id="096fa-135">A Customer Insights environment</span></span>
- <span data-ttu-id="096fa-136">Geharmoniseerde klantprofielen</span><span class="sxs-lookup"><span data-stu-id="096fa-136">Unified customer profiles</span></span>
- <span data-ttu-id="096fa-137">Activiteiten die zijn geconfigureerd en uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="096fa-137">Activities configured and run</span></span>
- <span data-ttu-id="096fa-138">Inzenders- of beheerdersmachtigingen om uw account te verifiëren</span><span class="sxs-lookup"><span data-stu-id="096fa-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="096fa-139">Verbinding maken via de Dynamics 365 Customer Insights-connector</span><span class="sxs-lookup"><span data-stu-id="096fa-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="096fa-140">De realtime API kan gegevens opnemen van een specifieke Power Platform-connector, de [Dynamics 365 Customer Insights-connector](https://docs.microsoft.com/connectors/customerinsights/), zonder dat u code hoeft te schrijven en te implementeren.</span><span class="sxs-lookup"><span data-stu-id="096fa-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="096fa-141">De connector kan dezelfde realtime acties uitvoeren als de API.</span><span class="sxs-lookup"><span data-stu-id="096fa-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="096fa-142">Voor premium connectors hebt u een geldige licentie nodig.</span><span class="sxs-lookup"><span data-stu-id="096fa-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="096fa-143">Zie [Veelgestelde vragen over Power Apps- en Power Automate-licenties](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="096fa-143">For more information, see [Power Apps and Power Automate licensing FAQs](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="096fa-144">Power Platform [Power Apps en/of Power Automate](https://docs.microsoft.com/connectors/)</span><span class="sxs-lookup"><span data-stu-id="096fa-144">Power Platform [Power Apps and/or Power Automate](https://docs.microsoft.com/connectors/)</span></span>
- <span data-ttu-id="096fa-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="096fa-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span></span>

<span data-ttu-id="096fa-146">Zie de [Power Automate-documentatie](https://docs.microsoft.com/power-automate/) voor meer informatie over het maken van stromen.</span><span class="sxs-lookup"><span data-stu-id="096fa-146">For details about creating flows, see the [Power Automate documentation](https://docs.microsoft.com/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="096fa-147">Rechtstreeks verbinding maken met de realtime API</span><span class="sxs-lookup"><span data-stu-id="096fa-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="096fa-148">U kunt de realtime mogelijkheden gebruiken door uw eigen pijplijn te bouwen en rechtstreeks verbinding te maken met de realtime API.</span><span class="sxs-lookup"><span data-stu-id="096fa-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="096fa-149">U kunt een activiteit plaatsen in de indeling van uw bronsysteem of in de UnifiedActivity-indeling.</span><span class="sxs-lookup"><span data-stu-id="096fa-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="096fa-150">Verkrijg de indeling door een API-aanroep uit te voeren naar /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="096fa-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="096fa-151">Details van deze API, inclusief parameters en reacties, zijn te vinden in de sectie **EntityData** sectie in de [Referentie voor Customer Insights-API's](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="096fa-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="096fa-152">Zie [Werken met Customer Insights-API's](apis.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="096fa-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="096fa-153">Inzicht in uw realtime gebruik krijgen met telemetrie</span><span class="sxs-lookup"><span data-stu-id="096fa-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="096fa-154">Krijg een overzicht van het aantal aanvragen aan bij realtime API en informatie over problemen die het systeem kan tegenkomen.</span><span class="sxs-lookup"><span data-stu-id="096fa-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="096fa-155">U kunt [toegang krijgen tot de realtime telemetrie](system.md#api-usage-tab).</span><span class="sxs-lookup"><span data-stu-id="096fa-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]