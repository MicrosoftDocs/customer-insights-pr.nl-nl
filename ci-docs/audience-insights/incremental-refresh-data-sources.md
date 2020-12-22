---
title: Incrementeel vernieuwen voor Power Query-gegevensbronnen
description: Vernieuw nieuwe en bijgewerkte gegevens voor grote gegevensbronnen op basis van Power Query.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b7e834f5f2fd1328563139675d7f850008348734
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405500"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="ce7a2-103">Incrementeel vernieuwen voor op Power Query gebaseerde gegevensbronnen</span><span class="sxs-lookup"><span data-stu-id="ce7a2-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="ce7a2-104">Incrementeel vernieuwen voor gegevensbronnen biedt de volgende voordelen:</span><span class="sxs-lookup"><span data-stu-id="ce7a2-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="ce7a2-105">**Sneller vernieuwingen**: alleen gewijzigde gegevens worden vernieuwd.</span><span class="sxs-lookup"><span data-stu-id="ce7a2-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="ce7a2-106">U kunt bijvoorbeeld alleen de gegevens van de afgelopen vijf dagen van een historische gegevensset vernieuwen.</span><span class="sxs-lookup"><span data-stu-id="ce7a2-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="ce7a2-107">**Verhoogde betrouwbaarheid**: met kleinere vernieuwingen hoeft u niet zo lang verbindingen met vluchtige bronsystemen te onderhouden, waardoor het risico op verbindingsproblemen afneemt.</span><span class="sxs-lookup"><span data-stu-id="ce7a2-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="ce7a2-108">**Verminderd verbruik van resources**: door slechts een subset van uw totale gegevens te vernieuwen, worden uw computerresources efficiënter gebruikt en wordt de ecologische voetafdruk kleiner.</span><span class="sxs-lookup"><span data-stu-id="ce7a2-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="ce7a2-109">Incrementele vernieuwing configureren</span><span class="sxs-lookup"><span data-stu-id="ce7a2-109">Configure incremental refresh</span></span>

<span data-ttu-id="ce7a2-110">Doelgroepinzichten maakt incrementele vernieuwing mogelijk voor gegevensbronnen die zijn geïmporteerd via Power Query die incrementele opname ondersteunen.</span><span class="sxs-lookup"><span data-stu-id="ce7a2-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="ce7a2-111">Bijvoorbeeld Azure SQL-databases met datum- en tijdvelden, die aangeven wanneer gegevensrecords voor het laatst zijn bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="ce7a2-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="ce7a2-112">[Een nieuwe gegevensbron maken op basis van Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="ce7a2-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="ce7a2-113">Geef een naam op voor de gegevensbron.</span><span class="sxs-lookup"><span data-stu-id="ce7a2-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="ce7a2-114">Selecteer een gegevensbron die incrementeel vernieuwen ondersteunt, zoals Azure SQL-database.</span><span class="sxs-lookup"><span data-stu-id="ce7a2-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="ce7a2-115">Selecteer de entiteiten of tabellen die u wilt opnemen.</span><span class="sxs-lookup"><span data-stu-id="ce7a2-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="ce7a2-116">Voltooi de transformatiestappen en selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="ce7a2-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="ce7a2-117">In het dialoogvenster **Incrementeel vernieuwen instellen** selecteert u **Instellen** om de **Instellingen voor incrementeel vernieuwen** te openen.</span><span class="sxs-lookup"><span data-stu-id="ce7a2-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="ce7a2-118">Als u selecteert **Overslaan** selecteert, zal de gegevensbron de volledige dataset vernieuwen.</span><span class="sxs-lookup"><span data-stu-id="ce7a2-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="ce7a2-119">U kunt incrementeel vernieuwen ook later toepassen door een bestaande gegevensbron te bewerken.</span><span class="sxs-lookup"><span data-stu-id="ce7a2-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="ce7a2-120">In **Instellingen voor incrementeel vernieuwen** configureert u de incrementele vernieuwing voor alle entiteiten die u hebt geselecteerd bij het maken van de gegevensbron.</span><span class="sxs-lookup"><span data-stu-id="ce7a2-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ce7a2-121">![Entiteiten configureren in een gegevensbron voor incrementeel vernieuwen](media/incremental-refresh-settings.png "Entiteiten configureren in een gegevensbron voor incrementeel vernieuwen")</span><span class="sxs-lookup"><span data-stu-id="ce7a2-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="ce7a2-122">Selecteer een entiteit en geef de volgende details op:</span><span class="sxs-lookup"><span data-stu-id="ce7a2-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="ce7a2-123">**De primaire sleutel definiëren**: selecteer een primaire sleutel voor de entiteit of tabel.</span><span class="sxs-lookup"><span data-stu-id="ce7a2-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="ce7a2-124">**Het veld 'Laatst bijgewerkt' definiëren**: in dit veld worden alleen kenmerken van het type datum of tijd weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ce7a2-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="ce7a2-125">Selecteer een kenmerk dat aangeeft wanneer de records voor het laatst zijn bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="ce7a2-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="ce7a2-126">Het wordt gebruikt om de records te identificeren die binnen het tijdsbestek voor incrementele verversing vallen.</span><span class="sxs-lookup"><span data-stu-id="ce7a2-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="ce7a2-127">**Controleer op updates elke**: geef op hoe lang het tijdsbestek voor de incrementele vernieuwing moet duren.</span><span class="sxs-lookup"><span data-stu-id="ce7a2-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="ce7a2-128">Selecteer **Opslaan** om het maken van de gegevensbron te voltooien.</span><span class="sxs-lookup"><span data-stu-id="ce7a2-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="ce7a2-129">De eerste gegevensvernieuwing is een volledige vernieuwing.</span><span class="sxs-lookup"><span data-stu-id="ce7a2-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="ce7a2-130">Daarna vindt de incrementele gegevensvernieuwing plaats zoals geconfigureerd in de vorige stap.</span><span class="sxs-lookup"><span data-stu-id="ce7a2-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>
