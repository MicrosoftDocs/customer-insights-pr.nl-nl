---
title: Power BI-connector
description: De Dynamics 365 Customer Insights-connector leren gebruiken in Power BI.
ms.date: 09/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e43e2f9dbc84ebfbf2154990a752740f973296cb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596033"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="4a200-103">Connector voor Power BI (preview)</span><span class="sxs-lookup"><span data-stu-id="4a200-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="4a200-104">Maak visualisaties voor uw gegevens met de Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="4a200-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="4a200-105">Genereer aanvullende inzichten en stel rapporten op met uw geharmoniseerde klantgegevens.</span><span class="sxs-lookup"><span data-stu-id="4a200-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4a200-106">Vereisten</span><span class="sxs-lookup"><span data-stu-id="4a200-106">Prerequisites</span></span>

- <span data-ttu-id="4a200-107">U hebt geharmoniseerde klantprofielen.</span><span class="sxs-lookup"><span data-stu-id="4a200-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="4a200-108">De nieuwste versie van [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is op uw computer geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="4a200-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="4a200-109">[Meer informatie over Power BI Desktop](/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="4a200-109">[Learn more about Power BI Desktop](/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="4a200-110">De connector voor Power BI configureren</span><span class="sxs-lookup"><span data-stu-id="4a200-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="4a200-111">Selecteer in Power BI Desktop de optie **Bestand** > **Gegevens ophalen**.</span><span class="sxs-lookup"><span data-stu-id="4a200-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="4a200-112">Selecteer **Meer weergeven** en zoek naar **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="4a200-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="4a200-113">Selecteer **Verbinding maken**.</span><span class="sxs-lookup"><span data-stu-id="4a200-113">Select **Connect**.</span></span>

1. <span data-ttu-id="4a200-114">**Meld u aan** met hetzelfde organisatieaccount dat u gebruikt voor Customer Insights en selecteer **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="4a200-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="4a200-115">Het account dat u in deze stap opgeeft, wordt gebruikt om gegevens op te halen uit Customer Insights en hoeft niet hetzelfde account te zijn waarmee u bent ingelogd bij Power BI.</span><span class="sxs-lookup"><span data-stu-id="4a200-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="4a200-116">Om het account dat wordt gebruikt voor het ophalen van gegevens opnieuw in te stellen, opent u Power BI en gaat u naar **Bestand** > **Opties** > **Instellingen** > **Instellingen voor gegevensbron**.</span><span class="sxs-lookup"><span data-stu-id="4a200-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="4a200-117">Selecteer in de lijst met gegevensbronnen **Aanmelden bij Dynamics 365 Customer Insights** en selecteer **Machtigingen wissen**.</span><span class="sxs-lookup"><span data-stu-id="4a200-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="4a200-118">In het dialoogvenster **Navigator**.</span><span class="sxs-lookup"><span data-stu-id="4a200-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="4a200-119">ziet u de lijst met alle omgevingen waartoe u toegang hebt.</span><span class="sxs-lookup"><span data-stu-id="4a200-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="4a200-120">Vouw een omgeving uit en open een van de mappen (entiteiten, metingen, segmenten, verrijkingen).</span><span class="sxs-lookup"><span data-stu-id="4a200-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="4a200-121">Open bijvoorbeeld de map **Entiteiten** om alle entiteiten te bekijken die u kunt importeren.</span><span class="sxs-lookup"><span data-stu-id="4a200-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="4a200-122">![Navigator voor Power BI-connector](media/power-bi-navigator.png "Navigator voor Power BI-connector")</span><span class="sxs-lookup"><span data-stu-id="4a200-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="4a200-123">Schakel de selectievakjes in naast de entiteiten die u wilt opnemen en selecteer **Laden**.</span><span class="sxs-lookup"><span data-stu-id="4a200-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="4a200-124">U kunt meerdere entiteiten selecteren uit meerdere omgevingen.</span><span class="sxs-lookup"><span data-stu-id="4a200-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="4a200-125">U ziet een dialoogvenster voor laden terwijl uw entiteiten worden geladen.</span><span class="sxs-lookup"><span data-stu-id="4a200-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="4a200-126">Zodra al uw geselecteerde entiteiten zijn geladen, kunt u de mogelijkheden van Power BI gebruiken om de gegevens te visualiseren.</span><span class="sxs-lookup"><span data-stu-id="4a200-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="4a200-127">Grote gegevenssets</span><span class="sxs-lookup"><span data-stu-id="4a200-127">Large data sets</span></span>

<span data-ttu-id="4a200-128">De Customer Insights-connector voor Power BI is ontworpen om te werken voor gegevenssets die tot 1 miljoen klantprofielen bevatten.</span><span class="sxs-lookup"><span data-stu-id="4a200-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="4a200-129">Het importeren van grotere gegevenssets kan werken, maar het duurt lang.</span><span class="sxs-lookup"><span data-stu-id="4a200-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="4a200-130">Bovendien kan bij het proces een time-out optreden vanwege Power BI-beperkingen.</span><span class="sxs-lookup"><span data-stu-id="4a200-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="4a200-131">Zie [Power BI: aanbevelingen voor grote gegevenssets](/power-bi/admin/service-premium-what-is#large-datasets) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="4a200-131">For more information, see [Power BI: Recommendations for large data sets](/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="4a200-132">Werken met een subset van gegevens</span><span class="sxs-lookup"><span data-stu-id="4a200-132">Work with a subset of data</span></span>

<span data-ttu-id="4a200-133">Overweeg om met een subset van uw gegevens te werken.</span><span class="sxs-lookup"><span data-stu-id="4a200-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="4a200-134">U kunt bijvoorbeeld [segmenten](segments.md) maken in plaats van alle klantrecords te exporteren naar Power BI.</span><span class="sxs-lookup"><span data-stu-id="4a200-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="4a200-135">Probleemoplossing</span><span class="sxs-lookup"><span data-stu-id="4a200-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="4a200-136">Customer Insights-omgeving wordt niet weergegeven Power BI</span><span class="sxs-lookup"><span data-stu-id="4a200-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="4a200-137">Omgevingen waarvoor meer dan één [relatie](relationships.md) is gedefinieerd tussen twee identieke entiteiten in doelgroepinzichten zijn niet beschikbaar zijn in de Power BI-connector.</span><span class="sxs-lookup"><span data-stu-id="4a200-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="4a200-138">U kunt de gedupliceerde relaties identificeren en verwijderen.</span><span class="sxs-lookup"><span data-stu-id="4a200-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="4a200-139">Ga in doelgroepinzichten naar **Gegevens** > **Relaties** in de omgeving die ontbreekt in Power BI​.</span><span class="sxs-lookup"><span data-stu-id="4a200-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="4a200-140">Identificeer gedupliceerde relaties:</span><span class="sxs-lookup"><span data-stu-id="4a200-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="4a200-141">Controleer of er meer dan één relatie is gedefinieerd tussen dezelfde twee entiteiten.</span><span class="sxs-lookup"><span data-stu-id="4a200-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="4a200-142">Controleer of er een relatie tot stand is gebracht tussen twee entiteiten die beide zijn opgenomen in het harmonisatieproces.</span><span class="sxs-lookup"><span data-stu-id="4a200-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="4a200-143">Er is een impliciete relatie gedefinieerd tussen alle entiteiten die in het harmonisatieproces zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="4a200-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="4a200-144">Verwijder eventuele dubbele relaties die u hebt gevonden.</span><span class="sxs-lookup"><span data-stu-id="4a200-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="4a200-145">Na verwijdering van de gedupliceerde relaties, probeert u de Power BI-connector opnieuw te configureren.</span><span class="sxs-lookup"><span data-stu-id="4a200-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="4a200-146">De omgeving zou nu beschikbaar moeten zijn.</span><span class="sxs-lookup"><span data-stu-id="4a200-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]