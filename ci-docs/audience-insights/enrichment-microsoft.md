---
title: Klantprofielen verrijken met gegevens van Microsoft
description: Gebruik bedrijfseigen gegevens van Microsoft om uw klantgegevens te verrijken met merk- en interesseaffiniteiten.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e92360bb886739cfe477ce1d2eb62219228a0292
ms.sourcegitcommit: d4b4053f6ee8f60f1a214982c4726c9de84615ef
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "6245701"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="0ff69-103">Klantprofielen verrijken met merk- en interesseaffiniteiten (preview)</span><span class="sxs-lookup"><span data-stu-id="0ff69-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="0ff69-104">Gebruik bedrijfseigen gegevens van Microsoft om uw klantgegevens te verrijken met merk- en interesseaffiniteiten.</span><span class="sxs-lookup"><span data-stu-id="0ff69-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="0ff69-105">Deze affiniteiten worden bepaald op basis van gegevens van mensen met vergelijkbare demografische gegevens als uw klanten.</span><span class="sxs-lookup"><span data-stu-id="0ff69-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="0ff69-106">Deze informatie helpt u om uw klanten beter te begrijpen en te segmenteren op basis van hun affiniteit met specifieke merken en interesses.</span><span class="sxs-lookup"><span data-stu-id="0ff69-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="0ff69-107">Ga in doelgroepinzichten naar **Gegevens** > **Verrijking** om [verrijkingen te configureren en weer te geven](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="0ff69-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="0ff69-108">Ga naar het tabblad **Ontdekken** en selecteer **Mijn gegevens verrijken** op de tegel **Merken** om de verrijking van merkaffiniteiten te configureren.</span><span class="sxs-lookup"><span data-stu-id="0ff69-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="0ff69-109">Ga naar het tabblad **Ontdekken** en selecteer **Mijn gegevens verrijken** op de tegel **Interesses** om de verrijking van interesseaffiniteiten te configureren.</span><span class="sxs-lookup"><span data-stu-id="0ff69-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0ff69-110">![Tegels voor merken en interesses](media/BrandsInterest-tile-Hub.png "Tegels voor merken en interesses")</span><span class="sxs-lookup"><span data-stu-id="0ff69-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="0ff69-111">Hoe we affiniteiten bepalen</span><span class="sxs-lookup"><span data-stu-id="0ff69-111">How we determine affinities</span></span>

<span data-ttu-id="0ff69-112">We gebruiken de online zoekgegevens van Microsoft om affiniteiten te vinden voor merken en interesses in verschillende demografische segmenten (gedefinieerd door leeftijd, geslacht of locatie).</span><span class="sxs-lookup"><span data-stu-id="0ff69-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="0ff69-113">Het online zoekvolume voor een merk of interesse bepaalt hoeveel affiniteit een demografisch segment heeft, vergeleken met andere segmenten, voor dat merk of die interesse.</span><span class="sxs-lookup"><span data-stu-id="0ff69-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="0ff69-114">Affiniteitsniveau en score</span><span class="sxs-lookup"><span data-stu-id="0ff69-114">Affinity level and score</span></span>

<span data-ttu-id="0ff69-115">Op elk verrijkt klantprofiel geven we twee gerelateerde waarden: affiniteitsniveau en affiniteitsscore.</span><span class="sxs-lookup"><span data-stu-id="0ff69-115">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="0ff69-116">Deze waarden helpen u te bepalen hoe sterk de affiniteit is voor het demografische segment van dat profiel, voor een merk of interesse, in vergelijking met andere demografische segmenten.</span><span class="sxs-lookup"><span data-stu-id="0ff69-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="0ff69-117">*Affiniteitsniveau* bestaat uit vier niveaus en *Affiniteitsscore* wordt berekend op een schaal van 100 punten die overeenkomt met de affiniteitsniveaus.</span><span class="sxs-lookup"><span data-stu-id="0ff69-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="0ff69-118">Affiniteitsniveau</span><span class="sxs-lookup"><span data-stu-id="0ff69-118">Affinity level</span></span> |<span data-ttu-id="0ff69-119">Affiniteitsscore</span><span class="sxs-lookup"><span data-stu-id="0ff69-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="0ff69-120">Zeer hoog</span><span class="sxs-lookup"><span data-stu-id="0ff69-120">Very high</span></span>     | <span data-ttu-id="0ff69-121">85-100</span><span class="sxs-lookup"><span data-stu-id="0ff69-121">85-100</span></span>       |
|<span data-ttu-id="0ff69-122">Hoog</span><span class="sxs-lookup"><span data-stu-id="0ff69-122">High</span></span>     | <span data-ttu-id="0ff69-123">70-84</span><span class="sxs-lookup"><span data-stu-id="0ff69-123">70-84</span></span>        |
|<span data-ttu-id="0ff69-124">Gemiddeld</span><span class="sxs-lookup"><span data-stu-id="0ff69-124">Medium</span></span>     | <span data-ttu-id="0ff69-125">35-69</span><span class="sxs-lookup"><span data-stu-id="0ff69-125">35-69</span></span>        |
|<span data-ttu-id="0ff69-126">Laag</span><span class="sxs-lookup"><span data-stu-id="0ff69-126">Low</span></span>     | <span data-ttu-id="0ff69-127">1-34</span><span class="sxs-lookup"><span data-stu-id="0ff69-127">1-34</span></span>        |

<span data-ttu-id="0ff69-128">Afhankelijk van de granulariteit waarmee u de affiniteit wilt meten, kunt u het affiniteitsniveau of de score gebruiken.</span><span class="sxs-lookup"><span data-stu-id="0ff69-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="0ff69-129">De affiniteitsscore geeft u een nauwkeurigere controle.</span><span class="sxs-lookup"><span data-stu-id="0ff69-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="0ff69-130">Ondersteunde landen/regio's</span><span class="sxs-lookup"><span data-stu-id="0ff69-130">Supported countries/regions</span></span>

<span data-ttu-id="0ff69-131">We ondersteunen momenteel de volgende opties voor landen/regio's: Australië, Canada (Engels), Frankrijk, Duitsland, Verenigd Koninkrijk of Verenigde Staten (Engels).</span><span class="sxs-lookup"><span data-stu-id="0ff69-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="0ff69-132">Als u een land wilt selecteren, opent u **Verrijking van merken** of **Interesseverrijking** en selecteert u **WIjzigen** naast **Land/regio**.</span><span class="sxs-lookup"><span data-stu-id="0ff69-132">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="0ff69-133">Kies in het deelvenster **Land-/regio-instellingen** een optie en selecteer **Toepassen**.</span><span class="sxs-lookup"><span data-stu-id="0ff69-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="0ff69-134">Implicaties met betrekking tot landselectie</span><span class="sxs-lookup"><span data-stu-id="0ff69-134">Implications related to country selection</span></span>

- <span data-ttu-id="0ff69-135">Wanneer u [uw eigen merken kiest](#define-your-brands-or-interests), geeft het systeem suggesties op basis van het geselecteerde land of de geselecteerde regio.</span><span class="sxs-lookup"><span data-stu-id="0ff69-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="0ff69-136">Wanneer u [een branche kiest](#define-your-brands-or-interests), krijgt u de meest relevante merken of interesses op basis van het geselecteerde land of de geselecteerde regio.</span><span class="sxs-lookup"><span data-stu-id="0ff69-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="0ff69-137">Wanneer u [profielen verrijkt](#refresh-enrichment), verrijken we alle klantprofielen waarvoor we gegevens krijgen voor de geselecteerde merken en interesses.</span><span class="sxs-lookup"><span data-stu-id="0ff69-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="0ff69-138">Inclusief profielen die zich niet in het geselecteerde land of de geselecteerde regio bevinden.</span><span class="sxs-lookup"><span data-stu-id="0ff69-138">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="0ff69-139">Als u bijvoorbeeld Duitsland hebt geselecteerd, verrijken we profielen in de Verenigde Staten als we gegevens beschikbaar hebben voor de geselecteerde merken en interesses in de Verenigde Staten.</span><span class="sxs-lookup"><span data-stu-id="0ff69-139">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="0ff69-140">Verrijking configureren</span><span class="sxs-lookup"><span data-stu-id="0ff69-140">Configure Enrichment</span></span>

<span data-ttu-id="0ff69-141">Een begeleide ervaring helpt u bij het configureren van de verrijkingen.</span><span class="sxs-lookup"><span data-stu-id="0ff69-141">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="0ff69-142">Uw merken of interesses definiëren</span><span class="sxs-lookup"><span data-stu-id="0ff69-142">Define your brands or interests</span></span>

<span data-ttu-id="0ff69-143">Kies maximaal vijf merken of interesses met behulp van een of beide van deze opties:</span><span class="sxs-lookup"><span data-stu-id="0ff69-143">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="0ff69-144">**Branche**: selecteer uw branche in de vervolgkeuzelijst en kies vervolgens uit de topmerken of interesses voor die branche.</span><span class="sxs-lookup"><span data-stu-id="0ff69-144">**Industry**: Select your industry from the drop-down list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="0ff69-145">**Uw eigen keuze maken**: voer een merk of interesse in die relevant is voor uw organisatie en kies vervolgens uit de bijpassende suggesties.</span><span class="sxs-lookup"><span data-stu-id="0ff69-145">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="0ff69-146">Als we geen merk of interesse vermelden waarnaar u op zoek bent, stuur ons dan feedback via de koppeling **Dit voorstellen**.</span><span class="sxs-lookup"><span data-stu-id="0ff69-146">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="0ff69-147">Verrijkingsvoorkeuren beoordelen</span><span class="sxs-lookup"><span data-stu-id="0ff69-147">Review enrichment preferences</span></span>

<span data-ttu-id="0ff69-148">Beoordeel uw standaardverrijkingsvoorkeuren en werk deze indien nodig bij.</span><span class="sxs-lookup"><span data-stu-id="0ff69-148">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Schermopname van het venster Verrijkingsvoorkeuren.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="0ff69-150">Te verrijken entiteit selecteren</span><span class="sxs-lookup"><span data-stu-id="0ff69-150">Select entity to enrich</span></span>

<span data-ttu-id="0ff69-151">Selecteer **Verrijkte entiteit** en kies de gegevensset die u wilt verrijken met bedrijfsgegevens van Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0ff69-151">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="0ff69-152">U kunt de entiteit Klant selecteren om al uw klantprofielen te verrijken of een segmententiteit selecteren om alleen klantprofielen in dat segment te verrijken.</span><span class="sxs-lookup"><span data-stu-id="0ff69-152">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="0ff69-153">Uw velden toewijzen</span><span class="sxs-lookup"><span data-stu-id="0ff69-153">Map your fields</span></span>

<span data-ttu-id="0ff69-154">Wijs velden van uw geharmoniseerde klantentiteit toe om het demografische segment te definiëren dat u door het systeem wilt laten gebruiken om uw klantgegevens te verrijken.</span><span class="sxs-lookup"><span data-stu-id="0ff69-154">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="0ff69-155">Wijs land/regio toe en ten minste geboortedatum of genderkenmerken.</span><span class="sxs-lookup"><span data-stu-id="0ff69-155">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="0ff69-156">Bovendien moet u ten minste een plaats (en staat/provincie) of postcode toewijzen.</span><span class="sxs-lookup"><span data-stu-id="0ff69-156">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="0ff69-157">Selecteer **Bewerken** om de toewijzing van de velden te definiëren en selecteer **Toepassen** wanneer u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="0ff69-157">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="0ff69-158">Selecteer **Opslaan** om de veldtoewijzing te voltooien.</span><span class="sxs-lookup"><span data-stu-id="0ff69-158">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="0ff69-159">De volgende indelingen en waarden worden ondersteund. Waarden zijn niet hoofdlettergevoelig:</span><span class="sxs-lookup"><span data-stu-id="0ff69-159">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="0ff69-160">**Geboortedatum**: we raden aan om de geboortedatum te converteren naar het type DateTime tijdens het opnemen van gegevens.</span><span class="sxs-lookup"><span data-stu-id="0ff69-160">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="0ff69-161">Als alternatief kan het een tekenreeks zijn in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html)-indeling 'jjjj-MM-dd' of 'jjjj-MM-dd THH: mm: ssZ'.</span><span class="sxs-lookup"><span data-stu-id="0ff69-161">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="0ff69-162">**Geslacht**: Man, Vrouw, Onbekend</span><span class="sxs-lookup"><span data-stu-id="0ff69-162">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="0ff69-163">**Postcode**: vijfcijferige postcodes voor de VS, standaard postcode overal elders</span><span class="sxs-lookup"><span data-stu-id="0ff69-163">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="0ff69-164">**Plaats**: plaatsnaam in het Engels</span><span class="sxs-lookup"><span data-stu-id="0ff69-164">**City**: City name in English</span></span>
- <span data-ttu-id="0ff69-165">**Staat/provincie**: afkorting van twee letters voor de VS en Canada.</span><span class="sxs-lookup"><span data-stu-id="0ff69-165">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="0ff69-166">Afkorting van twee of drie letters voor Australië.</span><span class="sxs-lookup"><span data-stu-id="0ff69-166">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="0ff69-167">Niet van toepassing op Frankrijk, Duitsland of het VK.</span><span class="sxs-lookup"><span data-stu-id="0ff69-167">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="0ff69-168">**Land/regio**:</span><span class="sxs-lookup"><span data-stu-id="0ff69-168">**Country/Region**:</span></span>

  - <span data-ttu-id="0ff69-169">VS: Verenigde Staten van Amerika, Verenigde Staten, VS, VS, Amerika</span><span class="sxs-lookup"><span data-stu-id="0ff69-169">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="0ff69-170">CA: Canada, CA</span><span class="sxs-lookup"><span data-stu-id="0ff69-170">CA: Canada, CA</span></span>
  - <span data-ttu-id="0ff69-171">GB: Verenigd Koninkrijk, VK, Groot-Brittannië, GB, Verenigd Koninkrijk van Groot-Brittannië en Noord-Ierland, Verenigd Koninkrijk van Groot-Brittannië</span><span class="sxs-lookup"><span data-stu-id="0ff69-171">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="0ff69-172">AU: Australië, AU, Gemenebest van Australië</span><span class="sxs-lookup"><span data-stu-id="0ff69-172">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="0ff69-173">FR: Frankrijk, FR, Franse Republiek</span><span class="sxs-lookup"><span data-stu-id="0ff69-173">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="0ff69-174">DE: Duitsland, Duits, Deutschland, Allemagne, DE, Federale Republiek Duitsland, Republiek Duitsland</span><span class="sxs-lookup"><span data-stu-id="0ff69-174">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="0ff69-175">De verrijking bekijken en een naam geven</span><span class="sxs-lookup"><span data-stu-id="0ff69-175">Review and name the enrichment</span></span>

<span data-ttu-id="0ff69-176">Tot slot gaat u de informatie bekijken en een naam voor de verrijking opgeven.</span><span class="sxs-lookup"><span data-stu-id="0ff69-176">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Pagina voor beoordeling van interesses en naamgeving.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="0ff69-178">Verrijking vernieuwen</span><span class="sxs-lookup"><span data-stu-id="0ff69-178">Refresh enrichment</span></span>

<span data-ttu-id="0ff69-179">Voer de verrijking uit na het configureren van merken, interesses en de veldtoewijzing voor demografische gegevens.</span><span class="sxs-lookup"><span data-stu-id="0ff69-179">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="0ff69-180">Start het proces door **Uitvoeren** te selecteren op de configuratiepagina voor merken of interesses.</span><span class="sxs-lookup"><span data-stu-id="0ff69-180">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="0ff69-181">Bovendien kunt u het systeem de verrijking automatisch laten uitvoeren als onderdeel van een geplande vernieuwing.</span><span class="sxs-lookup"><span data-stu-id="0ff69-181">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="0ff69-182">Afhankelijk van de omvang van uw klantgegevens kan het enkele minuten duren voordat een verrijking is voltooid.</span><span class="sxs-lookup"><span data-stu-id="0ff69-182">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="0ff69-183">Er zijn [zes soorten status](system.md#status-types) voor taken/processen.</span><span class="sxs-lookup"><span data-stu-id="0ff69-183">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="0ff69-184">Bovendien zijn de meeste processen [afhankelijk van andere stroomafwaartse processen](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="0ff69-184">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="0ff69-185">U kunt de status van een proces selecteren om voortgangsdetails te zien van de volledige taak.</span><span class="sxs-lookup"><span data-stu-id="0ff69-185">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="0ff69-186">Na het selecteren van **Details bekijken** voor een van de taken vindt u aanvullende informatie: verwerkingstijd, de laatste verwerkingsdatum en alle fouten en waarschuwingen die bij de taak horen.</span><span class="sxs-lookup"><span data-stu-id="0ff69-186">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="0ff69-187">Verrijkingsresultaten</span><span class="sxs-lookup"><span data-stu-id="0ff69-187">Enrichment results</span></span>

<span data-ttu-id="0ff69-188">Na het uitvoeren van het verrijkingsproces gaat u naar **Mijn verrijkingen** om het totale aantal verrijkte klanten en een uitsplitsing van merken of interesses in de verrijkte klantprofielen te bekijken.</span><span class="sxs-lookup"><span data-stu-id="0ff69-188">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Voorbeeldweergave van resultaten na het uitvoeren van het verrijkingsproces":::

<span data-ttu-id="0ff69-190">Bekijk de verrijkte gegevens door **Verrijkte gegevens weergeven** te selecteren in de grafiek.</span><span class="sxs-lookup"><span data-stu-id="0ff69-190">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="0ff69-191">Verrijkte gegevens voor merken gaan naar de entiteit **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="0ff69-191">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="0ff69-192">Gegevens voor interesses bevinden zich in de entiteit **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="0ff69-192">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="0ff69-193">U vindt deze entiteiten ook in de groep **Verrijking** in **Gegevens** > **Entiteiten**.</span><span class="sxs-lookup"><span data-stu-id="0ff69-193">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="0ff69-194">Zie verrijkingsgegevens op de klantenkaart</span><span class="sxs-lookup"><span data-stu-id="0ff69-194">See enrichment data on the customer card</span></span>

<span data-ttu-id="0ff69-195">Merk- en interesse-affiniteiten kunnen ook worden bekeken op individuele klantenkaarten.</span><span class="sxs-lookup"><span data-stu-id="0ff69-195">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="0ff69-196">Ga naar **Klanten** en selecteer een klantprofiel.</span><span class="sxs-lookup"><span data-stu-id="0ff69-196">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="0ff69-197">Op de klantkaart vindt u grafieken voor de merken of interesses waarvoor mensen in het demografische profiel van die klant affiniteit hebben.</span><span class="sxs-lookup"><span data-stu-id="0ff69-197">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Klantenkaart met verrijkte gegevens":::

## <a name="next-steps"></a><span data-ttu-id="0ff69-199">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="0ff69-199">Next steps</span></span>

<span data-ttu-id="0ff69-200">Bouw voort op uw verrijkte klantgegevens.</span><span class="sxs-lookup"><span data-stu-id="0ff69-200">Build on top of your enriched customer data.</span></span> <span data-ttu-id="0ff69-201">U kunt [Segmenten](segments.md) en [Maatregelen](measures.md) maken en [de gegevens zelfs exporteren](export-destinations.md) om uw klanten gepersonaliseerde ervaringen te bieden.</span><span class="sxs-lookup"><span data-stu-id="0ff69-201">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
