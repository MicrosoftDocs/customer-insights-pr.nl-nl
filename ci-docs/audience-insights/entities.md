---
title: Entiteiten en gegevenssets
description: Gegevens weergeven op de pagina Entiteiten.
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e3f41c0424b2cd756d72ae6af9d5225ebba92628
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405476"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="f4f80-103">Entiteiten in doelgroepinzichten</span><span class="sxs-lookup"><span data-stu-id="f4f80-103">Entities in audience insights</span></span>

<span data-ttu-id="f4f80-104">Ga, na het [configureren van uw gegevensbronnen](data-sources.md), naar de pagina **Entiteiten** om de kwaliteit van de opgenomen gegevens te evalueren.</span><span class="sxs-lookup"><span data-stu-id="f4f80-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="f4f80-105">Entiteiten worden beschouwd als gegevenssets.</span><span class="sxs-lookup"><span data-stu-id="f4f80-105">Entities are considered datasets.</span></span> <span data-ttu-id="f4f80-106">Meerdere mogelijkheden van Dynamics 365 Customer Insights zijn gebouwd rond deze entiteiten.</span><span class="sxs-lookup"><span data-stu-id="f4f80-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="f4f80-107">Door ze nauwkeurig te bekijken, kunt u de uitvoer van die mogelijkheden valideren.</span><span class="sxs-lookup"><span data-stu-id="f4f80-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="f4f80-108">Op de pagina **Entiteiten** worden entiteiten vermeld. Deze worden weergegeven in verschillende kolommen:</span><span class="sxs-lookup"><span data-stu-id="f4f80-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="f4f80-109">**Naam**: de naam van uw gegevensentiteit.</span><span class="sxs-lookup"><span data-stu-id="f4f80-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="f4f80-110">Als u een waarschuwingssymbool naast een entiteitsnaam ziet, betekent dit dat de gegevens voor die entiteit niet zijn geladen.</span><span class="sxs-lookup"><span data-stu-id="f4f80-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="f4f80-111">**Bron**: het type gegevensbron waarin de entiteit is opgenomen</span><span class="sxs-lookup"><span data-stu-id="f4f80-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="f4f80-112">**Gemaakt door**: naam van de gebruiker die de entiteit heeft gemaakt.</span><span class="sxs-lookup"><span data-stu-id="f4f80-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="f4f80-113">**Gemaakt**: datum en tijdstip waarop de entiteit is gemaakt</span><span class="sxs-lookup"><span data-stu-id="f4f80-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="f4f80-114">**Bijgewerkt door**: naam van de gebruiker die de entiteit heeft bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="f4f80-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="f4f80-115">**Laatst bijgewerkt**: datum en tijd van de laatste update van de entiteit</span><span class="sxs-lookup"><span data-stu-id="f4f80-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="f4f80-116">**Laatste vernieuwing**: datum en tijd van de laatste gegevensvernieuwing</span><span class="sxs-lookup"><span data-stu-id="f4f80-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="f4f80-117">De gegevens van een specifieke entiteit verkennen</span><span class="sxs-lookup"><span data-stu-id="f4f80-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="f4f80-118">Selecteer een entiteit om de verschillende velden en records in die entiteit te verkennen.</span><span class="sxs-lookup"><span data-stu-id="f4f80-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f4f80-119">![Selecteer een entiteit](media/data-manager-entities-data.png "Een entiteit selecteren")</span><span class="sxs-lookup"><span data-stu-id="f4f80-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="f4f80-120">Het tabblad **Gegevens** is standaard geselecteerd en toont een tabel met details over afzonderlijke records van de entiteit.</span><span class="sxs-lookup"><span data-stu-id="f4f80-120">The **Data** tab is selected by default and shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f4f80-121">![Veldentabel](media/data-manager-entities-fields.PNG "Veldentabel")</span><span class="sxs-lookup"><span data-stu-id="f4f80-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="f4f80-122">Op het tabblad **Velden** wordt een tabel weergegeven voor het bekijken van details voor de geselecteerde entiteit, zoals veldnamen, gegevenstypen en typen.</span><span class="sxs-lookup"><span data-stu-id="f4f80-122">The **Fields** tab shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="f4f80-123">In de kolom **Type** worden aan het Common Data Model gekoppelde typen weergegeven, die automatisch worden geïdentificeerd door het systeem of [handmatig worden toegewezen](map-entities.md) door gebruikers.</span><span class="sxs-lookup"><span data-stu-id="f4f80-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="f4f80-124">Dit zijn semantische typen die kunnen verschillen van de gegevenstypen van de kenmerken. Zo heeft bijvoorbeeld het veld *E-mail* een gegevenstype *Tekst*, maar is het (semantische) Common Data Model-type mogelijk *E-mail* of *E-mailadres*.</span><span class="sxs-lookup"><span data-stu-id="f4f80-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="f4f80-125">In beide tabellen wordt slechts een voorbeeld van de gegevens van uw entiteit weergegeven.</span><span class="sxs-lookup"><span data-stu-id="f4f80-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="f4f80-126">Als u de volledige gegevensset wilt bekijken, gaat u naar de pagina **Gegevensbronnen**, selecteert u **Bewerken** en bekijkt u de gegevens van deze entiteit met de Power Query-editor, zoals uitgelegd in [Gegevensbronnen](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="f4f80-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="f4f80-127">Voor meer informatie over de gegevens die zijn opgenomen in de entiteit biedt de kolom **Overzicht** u een aantal belangrijke kenmerken van de gegevens, zoals nullen, ontbrekende waarden, unieke waarden, tellingen en distributies, zoals van toepassing op uw gegevens.</span><span class="sxs-lookup"><span data-stu-id="f4f80-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="f4f80-128">Selecteer het grafiekpictogram om het overzicht van de gegevens weer te geven.</span><span class="sxs-lookup"><span data-stu-id="f4f80-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f4f80-129">![Overzichtssymbool](media/data-manager-entities-summary.png "Aanvraagoverzichtstabel")</span><span class="sxs-lookup"><span data-stu-id="f4f80-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="f4f80-130">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="f4f80-130">Next step</span></span>

<span data-ttu-id="f4f80-131">Bekijk het onderwerp [Harmoniseren](data-unification.md) om meer te weten te komen over het *toewijzen*, *afstemmen* en *samenvoegen* van de opgenomen gegevens.</span><span class="sxs-lookup"><span data-stu-id="f4f80-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>
