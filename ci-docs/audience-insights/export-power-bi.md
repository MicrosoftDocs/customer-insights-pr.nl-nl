---
title: Power BI-connector
description: De Dynamics 365 Customer Insights-connector leren gebruiken in Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405470"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="038c0-103">Connector voor Power BI (preview)</span><span class="sxs-lookup"><span data-stu-id="038c0-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="038c0-104">Maak visualisaties voor uw gegevens met de Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="038c0-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="038c0-105">Genereer aanvullende inzichten en stel rapporten op met uw geharmoniseerde klantgegevens.</span><span class="sxs-lookup"><span data-stu-id="038c0-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="038c0-106">Vereisten</span><span class="sxs-lookup"><span data-stu-id="038c0-106">Prerequisites</span></span>

- <span data-ttu-id="038c0-107">U hebt geharmoniseerde klantprofielen.</span><span class="sxs-lookup"><span data-stu-id="038c0-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="038c0-108">De meest recente versie van [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is op uw computer geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="038c0-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="038c0-109">[Meer informatie over Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="038c0-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="038c0-110">De connector voor Power BI configureren</span><span class="sxs-lookup"><span data-stu-id="038c0-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="038c0-111">Selecteer in Power BI Desktop de optie **Bestand** > **Gegevens ophalen**.</span><span class="sxs-lookup"><span data-stu-id="038c0-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="038c0-112">Selecteer **Meer weergeven** en zoek naar **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="038c0-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="038c0-113">Selecteer het resultaat en selecteer **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="038c0-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="038c0-114">**Meld u aan** met hetzelfde organisatieaccount dat u gebruikt voor Customer Insights en selecteer **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="038c0-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="038c0-115">Het account dat u in deze stap opgeeft, wordt gebruikt om gegevens op te halen uit Customer Insights en hoeft niet hetzelfde account te zijn waarmee u bent ingelogd bij Power BI.</span><span class="sxs-lookup"><span data-stu-id="038c0-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="038c0-116">Om het account dat wordt gebruikt voor het ophalen van gegevens opnieuw in te stellen, opent u Power BI en gaat u naar **Bestand** > **Opties** > **Instellingen** > **Instellingen voor gegevensbron**.</span><span class="sxs-lookup"><span data-stu-id="038c0-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="038c0-117">Selecteer in de lijst met gegevensbronnen **Aanmelden bij Dynamics 365 Customer Insights** en selecteer **Machtigingen wissen**.</span><span class="sxs-lookup"><span data-stu-id="038c0-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="038c0-118">In het dialoogvenster **Navigator**.</span><span class="sxs-lookup"><span data-stu-id="038c0-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="038c0-119">ziet u de lijst met alle omgevingen waartoe u toegang hebt.</span><span class="sxs-lookup"><span data-stu-id="038c0-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="038c0-120">Vouw een omgeving uit en open een van de mappen (entiteiten, metingen, segmenten, verrijkingen).</span><span class="sxs-lookup"><span data-stu-id="038c0-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="038c0-121">Open bijvoorbeeld de map **Entiteiten** om alle entiteiten te bekijken die u kunt importeren.</span><span class="sxs-lookup"><span data-stu-id="038c0-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="038c0-122">![Navigator voor Power BI-connector](media/power-bi-navigator.png "Navigator voor Power BI-connector")</span><span class="sxs-lookup"><span data-stu-id="038c0-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="038c0-123">Schakel de selectievakjes in naast de entiteiten die u wilt opnemen en selecteer **Laden**.</span><span class="sxs-lookup"><span data-stu-id="038c0-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="038c0-124">U kunt meerdere entiteiten selecteren uit meerdere omgevingen.</span><span class="sxs-lookup"><span data-stu-id="038c0-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="038c0-125">U ziet een dialoogvenster voor laden terwijl uw entiteiten worden geladen.</span><span class="sxs-lookup"><span data-stu-id="038c0-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="038c0-126">Zodra al uw geselecteerde entiteiten zijn geladen, kunt u de mogelijkheden van Power BI gebruiken om de gegevens te visualiseren.</span><span class="sxs-lookup"><span data-stu-id="038c0-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="038c0-127">Grote gegevenssets</span><span class="sxs-lookup"><span data-stu-id="038c0-127">Large data sets</span></span>

<span data-ttu-id="038c0-128">De Customer Insights-connector voor Power BI is ontworpen om te werken voor gegevenssets die tot 1 miljoen klantprofielen bevatten.</span><span class="sxs-lookup"><span data-stu-id="038c0-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="038c0-129">Het importeren van grotere gegevenssets kan werken, maar het duurt lang.</span><span class="sxs-lookup"><span data-stu-id="038c0-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="038c0-130">Bovendien kan bij het proces een time-out optreden vanwege Power BI-beperkingen.</span><span class="sxs-lookup"><span data-stu-id="038c0-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="038c0-131">Zie [Power BI: aanbevelingen voor grote gegevenssets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="038c0-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="038c0-132">Werken met een subset van gegevens</span><span class="sxs-lookup"><span data-stu-id="038c0-132">Work with a subset of data</span></span>

<span data-ttu-id="038c0-133">Overweeg om met een subset van uw gegevens te werken.</span><span class="sxs-lookup"><span data-stu-id="038c0-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="038c0-134">U kunt bijvoorbeeld [segmenten](segments.md) maken in plaats van alle klantrecords te exporteren naar Power BI.</span><span class="sxs-lookup"><span data-stu-id="038c0-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>
