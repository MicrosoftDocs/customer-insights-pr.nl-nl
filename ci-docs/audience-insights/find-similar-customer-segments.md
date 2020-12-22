---
title: Vergelijkbare klanten zoeken met AI
description: Vergelijkbare klantsegmenten zoeken met kunstmatige intelligentie.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 8cdec4edd599b0249fcf144b5e5c0124504e1e14
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405497"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="65eb6-103">Vergelijkbare klanten (preview)</span><span class="sxs-lookup"><span data-stu-id="65eb6-103">Similar Customers (preview)</span></span>

<span data-ttu-id="65eb6-104">Met deze functie kunt u vergelijkbare klanten in uw klantenbestand zoeken met behulp van kunstmatige intelligentie.</span><span class="sxs-lookup"><span data-stu-id="65eb6-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="65eb6-105">U moet ten minste één segment hebben gemaakt om deze functie te kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="65eb6-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="65eb6-106">Door de criteria van een bestaand segment uit te breiden, kunt u klanten vinden die vergelijkbaar zijn met dat segment.</span><span class="sxs-lookup"><span data-stu-id="65eb6-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="65eb6-107">*Vergelijkbare klanten zoeken* gebruikt geautomatiseerde middelen om gegevens te evalueren en voorspellingen te doen op basis van die gegevens, en heeft daarom de mogelijkheid om te worden gebruikt als profileringsmethode, zoals die term wordt gedefinieerd door de Algemene verordening gegevensbescherming ("AVG").</span><span class="sxs-lookup"><span data-stu-id="65eb6-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="65eb6-108">Op het gebruik door de klant van deze functie om gegevens te verwerken, zijn mogelijk de AVG of andere wetten of voorschriften van toepassing.</span><span class="sxs-lookup"><span data-stu-id="65eb6-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="65eb6-109">U bent ervoor verantwoordelijk dat uw gebruik van Dynamics 365 Customer Insights, inclusief voorspellingen, voldoet aan alle toepasselijke wet- en regelgeving, inclusief wetten met betrekking tot privacy, persoonsgegevens, biometrische gegevens, gegevensbescherming en vertrouwelijkheid van communicatie.</span><span class="sxs-lookup"><span data-stu-id="65eb6-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="65eb6-110">Vergelijkbare klanten zoeken</span><span class="sxs-lookup"><span data-stu-id="65eb6-110">Finding similar customers</span></span>

1. <span data-ttu-id="65eb6-111">Ga in doelgroepinzichten naar **Segmenten** en selecteer het segment waarop u uw nieuwe segment wilt baseren.</span><span class="sxs-lookup"><span data-stu-id="65eb6-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="65eb6-112">Dat is uw *bronsegment*.</span><span class="sxs-lookup"><span data-stu-id="65eb6-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="65eb6-113">Selecteer in de actiebalk **Vergelijkbare klanten zoeken**.</span><span class="sxs-lookup"><span data-stu-id="65eb6-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="65eb6-114">Bekijk de voorgestelde naam voor uw nieuwe segment en wijzig deze indien nodig.</span><span class="sxs-lookup"><span data-stu-id="65eb6-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="65eb6-115">Bekijk de velden die uw nieuwe segment definiëren.</span><span class="sxs-lookup"><span data-stu-id="65eb6-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="65eb6-116">Deze velden definiëren de basis waarop het systeem zal proberen vergelijkbare klanten te vinden voor uw bronsegment.</span><span class="sxs-lookup"><span data-stu-id="65eb6-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="65eb6-117">Het systeem selecteert standaard aanbevolen velden.</span><span class="sxs-lookup"><span data-stu-id="65eb6-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="65eb6-118">Velden die de modelprestaties aanzienlijk kunnen verminderen, worden automatisch uitgesloten:</span><span class="sxs-lookup"><span data-stu-id="65eb6-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="65eb6-119">Velden met de volgende gegevenstypen: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="65eb6-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="65eb6-120">Velden met een kardinaliteit (het aantal elementen in een veld) van minder dan 2 of meer dan 30</span><span class="sxs-lookup"><span data-stu-id="65eb6-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="65eb6-121">Kies of u **Alle klanten** wilt opnemen of alleen klanten in een **Specifiek bestaand segment** in uw nieuwe segment.</span><span class="sxs-lookup"><span data-stu-id="65eb6-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="65eb6-122">Sluit klanten in uw bronsegment uit door het selectievakje **Iedereen uitsluiten in bronsegment** in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="65eb6-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="65eb6-123">Standaard stelt het systeem voor om slechts 20% van de doelgroep op te nemen in uw uitvoer.</span><span class="sxs-lookup"><span data-stu-id="65eb6-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="65eb6-124">Bewerk deze drempelwaarde indien nodig.</span><span class="sxs-lookup"><span data-stu-id="65eb6-124">Edit this threshold as needed.</span></span> <span data-ttu-id="65eb6-125">Als de drempelwaarde wordt verhoogd, neemt de precisie af.</span><span class="sxs-lookup"><span data-stu-id="65eb6-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="65eb6-126">Selecteer **Uitvoeren** onder aan de pagina om een binaire classificatietaak te starten (een methode van Machine Learning) die de gegevensset analyseert.</span><span class="sxs-lookup"><span data-stu-id="65eb6-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="65eb6-127">Het vergelijkbare segment bekijken</span><span class="sxs-lookup"><span data-stu-id="65eb6-127">View the similar segment</span></span>

<span data-ttu-id="65eb6-128">Na het verwerken van het vergelijkbare segment, vindt u het nieuwe segment vermeld op de pagina **Segmenten**.</span><span class="sxs-lookup"><span data-stu-id="65eb6-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="65eb6-129">![Segment van vergelijkbare klanten](media/expanded-segment.png "Segment van vergelijkbare klanten")</span><span class="sxs-lookup"><span data-stu-id="65eb6-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="65eb6-130">Selecteer **Weergeven** op de actiebalk om het segmentdetail te openen.</span><span class="sxs-lookup"><span data-stu-id="65eb6-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="65eb6-131">Deze weergave bevat informatie over de resultaatverdeling tussen [overeenkomstscores](#about-similarity-scores).</span><span class="sxs-lookup"><span data-stu-id="65eb6-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="65eb6-132">U vindt de waarden voor de overeenkomstscore ook in **Voorbeeld van segmentleden**.</span><span class="sxs-lookup"><span data-stu-id="65eb6-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="65eb6-133">De uitvoer van een vergelijkbaar segment gebruiken</span><span class="sxs-lookup"><span data-stu-id="65eb6-133">Use the output of a similar segment</span></span>

<span data-ttu-id="65eb6-134">U kunt [werken met de uitvoer van een vergelijkbaar segment](segments.md) zoals u doet met andere segmenten.</span><span class="sxs-lookup"><span data-stu-id="65eb6-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="65eb6-135">U kunt bijvoorbeeld het segment exporteren of een meting bouwen.</span><span class="sxs-lookup"><span data-stu-id="65eb6-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="65eb6-136">Een vergelijkbaar segment vernieuwen en bewerken</span><span class="sxs-lookup"><span data-stu-id="65eb6-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="65eb6-137">Als u een vergelijkbaar segment wilt vernieuwen, selecteert u het op de pagina **Segmenten** en selecteert u **Vernieuwen** op de actiebalk.</span><span class="sxs-lookup"><span data-stu-id="65eb6-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="65eb6-138">Als u een vergelijkbaar segment bewerkt, worden uw gegevens opnieuw verwerkt.</span><span class="sxs-lookup"><span data-stu-id="65eb6-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="65eb6-139">Het eerder gemaakte segment wordt bijgewerkt met vernieuwde gegevens.</span><span class="sxs-lookup"><span data-stu-id="65eb6-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="65eb6-140">Als u een vergelijkbaar segment wilt bewerken, selecteert u het op de pagina **Segmenten** en selecteert u **Bewerken** op de actiebalk.</span><span class="sxs-lookup"><span data-stu-id="65eb6-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="65eb6-141">Pas uw wijzigingen toe en selecteer **Uitvoeren** om de verwerking te starten.</span><span class="sxs-lookup"><span data-stu-id="65eb6-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="65eb6-142">Een vergelijkbaar segment verwijderen</span><span class="sxs-lookup"><span data-stu-id="65eb6-142">Delete a similar segment</span></span>

<span data-ttu-id="65eb6-143">Selecteer het segment op de pagina **Segmenten** en selecteer vervolgens **Verwijderen** op de actiebalk.</span><span class="sxs-lookup"><span data-stu-id="65eb6-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="65eb6-144">Bevestig vervolgens uw verwijdering.</span><span class="sxs-lookup"><span data-stu-id="65eb6-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="65eb6-145">Info over overeenkomstscores</span><span class="sxs-lookup"><span data-stu-id="65eb6-145">About similarity scores</span></span>

<span data-ttu-id="65eb6-146">Het Machine Learning-model voor binaire classificatie kent een score toe aan klanten in het vergelijkbare segment.</span><span class="sxs-lookup"><span data-stu-id="65eb6-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="65eb6-147">De score is gebaseerd op de overeenkomst met klanten in het bronsegment.</span><span class="sxs-lookup"><span data-stu-id="65eb6-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="65eb6-148">Klanten met vergelijkbaarheidsscores onder 0,55 zijn klanten die door het systeem worden geclassificeerd *niet vergelijkbaar* met klanten in het bronsegment</span><span class="sxs-lookup"><span data-stu-id="65eb6-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="65eb6-149">Klanten met overeenkomstscores tussen 0,55 en 0,7 worden geclassificeerd als *enigszins vergelijkbaar*</span><span class="sxs-lookup"><span data-stu-id="65eb6-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="65eb6-150">Klanten met overeenkomstscores tussen 0,7 en 0,85 worden geclassificeerd als *vergelijkbaar*</span><span class="sxs-lookup"><span data-stu-id="65eb6-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="65eb6-151">Klanten met overeenkomstscores tussen 0,85 en 1 zijn klanten die door het systeem als *zeer vergelijkbaar* worden geclassificeerd</span><span class="sxs-lookup"><span data-stu-id="65eb6-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="65eb6-152">Klanten met een overeenkomstscore onder de 0,4 worden niet opgenomen in de modeluitvoer.</span><span class="sxs-lookup"><span data-stu-id="65eb6-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="65eb6-153">Het systeem beschouwt ze niet als vergelijkbaar genoeg met het bronsegment.</span><span class="sxs-lookup"><span data-stu-id="65eb6-153">The system doesn't consider them similar enough to the source segment.</span></span>
