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
ms.openlocfilehash: 1b11c325649b91ebb47cde924227eacedae64b7a
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305150"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="c2566-103">Klantprofielen verrijken met merk- en interesseaffiniteiten (preview)</span><span class="sxs-lookup"><span data-stu-id="c2566-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="c2566-104">Gebruik bedrijfseigen gegevens van Microsoft om uw klantgegevens te verrijken met merk- en interesseaffiniteiten.</span><span class="sxs-lookup"><span data-stu-id="c2566-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="c2566-105">Deze affiniteiten zijn gebaseerd op gegevens van personen in een vergelijkbare demografische groep als uw klanten.</span><span class="sxs-lookup"><span data-stu-id="c2566-105">These affinities are based on data from people with demographics similar to your customers.</span></span> <span data-ttu-id="c2566-106">Deze informatie helpt u om uw klanten beter te begrijpen en te segmenteren op basis van hun affiniteit met specifieke merken en interesses.</span><span class="sxs-lookup"><span data-stu-id="c2566-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="c2566-107">Ga in doelgroepinzichten naar **Gegevens** > **Verrijking** om [verrijkingen te configureren en weer te geven](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="c2566-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="c2566-108">Ga naar het tabblad **Ontdekken** en selecteer **Mijn gegevens verrijken** op de tegel **Merken** om de verrijking van merkaffiniteiten te configureren.</span><span class="sxs-lookup"><span data-stu-id="c2566-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="c2566-109">Ga naar het tabblad **Ontdekken** en selecteer **Mijn gegevens verrijken** op de tegel **Interesses** om de verrijking van interesseaffiniteiten te configureren.</span><span class="sxs-lookup"><span data-stu-id="c2566-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c2566-110">![Tegels Merken en Interesses](media/BrandsInterest-tile-Hub.png "Tegels Merken en Interesses")</span><span class="sxs-lookup"><span data-stu-id="c2566-110">![Brands and Interests tiles](media/BrandsInterest-tile-Hub.png "Brands and Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="c2566-111">Hoe we affiniteiten bepalen</span><span class="sxs-lookup"><span data-stu-id="c2566-111">How we determine affinities</span></span>

<span data-ttu-id="c2566-112">We gebruiken de online zoekgegevens van Microsoft om affiniteiten te vinden voor merken en interesses in verschillende demografische segmenten (gedefinieerd door leeftijd, geslacht of locatie).</span><span class="sxs-lookup"><span data-stu-id="c2566-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="c2566-113">Het online zoekvolume voor een merk of interesse bepaalt hoeveel affiniteit een demografisch segment heeft, vergeleken met andere segmenten, voor dat merk of die interesse.</span><span class="sxs-lookup"><span data-stu-id="c2566-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="c2566-114">Affiniteitsniveau en score</span><span class="sxs-lookup"><span data-stu-id="c2566-114">Affinity level and score</span></span>

<span data-ttu-id="c2566-115">Op elk verrijkt klantprofiel geven we twee gerelateerde waarden: affiniteitsniveau en affiniteitsscore.</span><span class="sxs-lookup"><span data-stu-id="c2566-115">On every enriched customer profile, we provide two related values: affinity level and affinity score.</span></span> <span data-ttu-id="c2566-116">Deze waarden helpen u te bepalen hoe sterk de affiniteit is voor het demografische segment van dat profiel, voor een merk of interesse, in vergelijking met andere demografische segmenten.</span><span class="sxs-lookup"><span data-stu-id="c2566-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="c2566-117">*Affiniteitsniveau* bestaat uit vier niveaus en *Affiniteitsscore* wordt berekend op een schaal van 100 punten die overeenkomt met de affiniteitsniveaus.</span><span class="sxs-lookup"><span data-stu-id="c2566-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="c2566-118">Affiniteitsniveau</span><span class="sxs-lookup"><span data-stu-id="c2566-118">Affinity level</span></span> |<span data-ttu-id="c2566-119">Affiniteitsscore</span><span class="sxs-lookup"><span data-stu-id="c2566-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="c2566-120">Zeer hoog</span><span class="sxs-lookup"><span data-stu-id="c2566-120">Very high</span></span>     | <span data-ttu-id="c2566-121">85-100</span><span class="sxs-lookup"><span data-stu-id="c2566-121">85-100</span></span>       |
|<span data-ttu-id="c2566-122">Hoog</span><span class="sxs-lookup"><span data-stu-id="c2566-122">High</span></span>     | <span data-ttu-id="c2566-123">70-84</span><span class="sxs-lookup"><span data-stu-id="c2566-123">70-84</span></span>        |
|<span data-ttu-id="c2566-124">Gemiddeld</span><span class="sxs-lookup"><span data-stu-id="c2566-124">Medium</span></span>     | <span data-ttu-id="c2566-125">35-69</span><span class="sxs-lookup"><span data-stu-id="c2566-125">35-69</span></span>        |
|<span data-ttu-id="c2566-126">Laag</span><span class="sxs-lookup"><span data-stu-id="c2566-126">Low</span></span>     | <span data-ttu-id="c2566-127">1-34</span><span class="sxs-lookup"><span data-stu-id="c2566-127">1-34</span></span>        |

<span data-ttu-id="c2566-128">Afhankelijk van de granulariteit waarmee u de affiniteit wilt meten, kunt u het affiniteitsniveau of de score gebruiken.</span><span class="sxs-lookup"><span data-stu-id="c2566-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="c2566-129">De affiniteitsscore geeft u een nauwkeurigere controle.</span><span class="sxs-lookup"><span data-stu-id="c2566-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="c2566-130">Ondersteunde landen/regio's</span><span class="sxs-lookup"><span data-stu-id="c2566-130">Supported countries/regions</span></span>

<span data-ttu-id="c2566-131">We ondersteunen momenteel de volgende opties voor landen/regio's: Australië, Canada (Engels), Frankrijk, Duitsland, Verenigd Koninkrijk of Verenigde Staten (Engels).</span><span class="sxs-lookup"><span data-stu-id="c2566-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="c2566-132">Als u een land of regio wilt selecteren, opent u **Verrijking met merken** of **Verrijking met interesses** en selecteert u **Wijzigen** naast **Land/Regio**.</span><span class="sxs-lookup"><span data-stu-id="c2566-132">To select a country or region, open **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="c2566-133">Kies in het deelvenster **Land-/regio-instellingen** een optie en selecteer **Toepassen**.</span><span class="sxs-lookup"><span data-stu-id="c2566-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="c2566-134">Implicaties met betrekking tot landselectie</span><span class="sxs-lookup"><span data-stu-id="c2566-134">Implications related to country selection</span></span>

- <span data-ttu-id="c2566-135">Wanneer u [uw eigen merken kiest](#define-your-brands-or-interests), geeft het systeem suggesties op basis van het geselecteerde land of de geselecteerde regio.</span><span class="sxs-lookup"><span data-stu-id="c2566-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="c2566-136">Wanneer u [een branche kiest](#define-your-brands-or-interests), krijgt u de meest relevante merken of interesses op basis van het geselecteerde land of de geselecteerde regio.</span><span class="sxs-lookup"><span data-stu-id="c2566-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="c2566-137">Bij het [verrijken van profielen](#refresh-enrichment), verrijken we alle klantprofielen waarvoor we gegevens krijgen voor de geselecteerde merken en interesses, inclusief profielen die zich niet in het geselecteerde land of de geselecteerde regio bevinden.</span><span class="sxs-lookup"><span data-stu-id="c2566-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests, including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="c2566-138">Als u bijvoorbeeld Duitsland hebt geselecteerd, verrijken we profielen in de Verenigde Staten als we gegevens beschikbaar hebben voor de geselecteerde merken en interesses in de Verenigde Staten.</span><span class="sxs-lookup"><span data-stu-id="c2566-138">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="c2566-139">Verrijking configureren</span><span class="sxs-lookup"><span data-stu-id="c2566-139">Configure enrichment</span></span>

<span data-ttu-id="c2566-140">Een begeleide ervaring helpt u bij het configureren van de verrijkingen.</span><span class="sxs-lookup"><span data-stu-id="c2566-140">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="c2566-141">Uw merken of interesses definiëren</span><span class="sxs-lookup"><span data-stu-id="c2566-141">Define your brands or interests</span></span>

<span data-ttu-id="c2566-142">Kies maximaal vijf merken of interesses met behulp van een of beide van deze opties:</span><span class="sxs-lookup"><span data-stu-id="c2566-142">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="c2566-143">**Branche**: selecteer uw branche in de vervolgkeuzelijst en kies vervolgens uit de topmerken of interesses voor die branche.</span><span class="sxs-lookup"><span data-stu-id="c2566-143">**Industry**: Select your industry from the dropdown list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="c2566-144">**Uw eigen keuze maken**: voer een merk of interesse in die relevant is voor uw organisatie en kies vervolgens uit de bijpassende suggesties.</span><span class="sxs-lookup"><span data-stu-id="c2566-144">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="c2566-145">Als we geen merk of interesse vermelden waarnaar u op zoek bent, stuur ons dan feedback via de koppeling **Dit voorstellen**.</span><span class="sxs-lookup"><span data-stu-id="c2566-145">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="c2566-146">Verrijkingsvoorkeuren beoordelen</span><span class="sxs-lookup"><span data-stu-id="c2566-146">Review enrichment preferences</span></span>

<span data-ttu-id="c2566-147">Beoordeel uw standaardverrijkingsvoorkeuren en werk deze indien nodig bij.</span><span class="sxs-lookup"><span data-stu-id="c2566-147">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Schermopname van het venster Verrijkingsvoorkeuren.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="c2566-149">Te verrijken entiteit selecteren</span><span class="sxs-lookup"><span data-stu-id="c2566-149">Select entity to enrich</span></span>

<span data-ttu-id="c2566-150">Selecteer **Verrijkte entiteit** en kies de gegevensset die u wilt verrijken met bedrijfsgegevens van Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c2566-150">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="c2566-151">U kunt de entiteit Klant selecteren om al uw klantprofielen te verrijken of een segmententiteit selecteren om alleen klantprofielen in dat segment te verrijken.</span><span class="sxs-lookup"><span data-stu-id="c2566-151">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="c2566-152">Uw velden toewijzen</span><span class="sxs-lookup"><span data-stu-id="c2566-152">Map your fields</span></span>

<span data-ttu-id="c2566-153">Wijs velden van uw geharmoniseerde klantentiteit toe om het demografische segment te definiëren dat u door het systeem wilt laten gebruiken om uw klantgegevens te verrijken.</span><span class="sxs-lookup"><span data-stu-id="c2566-153">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="c2566-154">Wijs land/regio toe en ten minste geboortedatum of genderkenmerken.</span><span class="sxs-lookup"><span data-stu-id="c2566-154">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="c2566-155">Bovendien moet u ten minste een plaats (en staat/provincie) of postcode toewijzen.</span><span class="sxs-lookup"><span data-stu-id="c2566-155">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="c2566-156">Selecteer **Bewerken** om de toewijzing van de velden te definiëren en selecteer **Toepassen** wanneer u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="c2566-156">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="c2566-157">Selecteer **Opslaan** om de veldtoewijzing te voltooien.</span><span class="sxs-lookup"><span data-stu-id="c2566-157">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="c2566-158">De volgende indelingen en waarden worden ondersteund (waarden zijn niet hoofdlettergevoelig):</span><span class="sxs-lookup"><span data-stu-id="c2566-158">The following formats and values are supported (values are not case-sensitive):</span></span>

- <span data-ttu-id="c2566-159">**Geboortedatum**: we raden aan om de geboortedatum te converteren naar het type DateTime tijdens het opnemen van gegevens.</span><span class="sxs-lookup"><span data-stu-id="c2566-159">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="c2566-160">Als alternatief kan het een tekenreeks zijn in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html)-indeling 'jjjj-MM-dd' of 'jjjj-MM-ddTHH:mm:ss'.</span><span class="sxs-lookup"><span data-stu-id="c2566-160">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ss".</span></span>
- <span data-ttu-id="c2566-161">**Geslacht**: Man, Vrouw, Onbekend.</span><span class="sxs-lookup"><span data-stu-id="c2566-161">**Gender**: Male, Female, Unknown.</span></span>
- <span data-ttu-id="c2566-162">**Postcode**: vijfcijferige postcodes voor Verenigde Staten, standaard postcode overal elders.</span><span class="sxs-lookup"><span data-stu-id="c2566-162">**Postal code**: Five-digit ZIP codes for United States, standard postal code everywhere else.</span></span>
- <span data-ttu-id="c2566-163">**Plaats**: plaatsnaam in het Engels.</span><span class="sxs-lookup"><span data-stu-id="c2566-163">**City**: City name in English.</span></span>
- <span data-ttu-id="c2566-164">**Staat/provincie**: afkorting van twee letters voor de VS en Canada.</span><span class="sxs-lookup"><span data-stu-id="c2566-164">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="c2566-165">Afkorting van twee of drie letters voor Australië.</span><span class="sxs-lookup"><span data-stu-id="c2566-165">Two- or three-letter abbreviation for Australia.</span></span> <span data-ttu-id="c2566-166">Niet van toepassing op Frankrijk, Duitsland of het VK.</span><span class="sxs-lookup"><span data-stu-id="c2566-166">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="c2566-167">**Land/regio**:</span><span class="sxs-lookup"><span data-stu-id="c2566-167">**Country/Region**:</span></span>

  - <span data-ttu-id="c2566-168">VS: Verenigde Staten van Amerika, Verenigde Staten, VS, VS, Amerika</span><span class="sxs-lookup"><span data-stu-id="c2566-168">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="c2566-169">CA: Canada, CA</span><span class="sxs-lookup"><span data-stu-id="c2566-169">CA: Canada, CA</span></span>
  - <span data-ttu-id="c2566-170">GB: Verenigd Koninkrijk, VK, Groot-Brittannië, GB, Verenigd Koninkrijk van Groot-Brittannië en Noord-Ierland, Verenigd Koninkrijk van Groot-Brittannië</span><span class="sxs-lookup"><span data-stu-id="c2566-170">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="c2566-171">AU: Australië, AU, Gemenebest van Australië</span><span class="sxs-lookup"><span data-stu-id="c2566-171">AU: Australia, AU, Commonwealth of Australia</span></span>
  - <span data-ttu-id="c2566-172">FR: Frankrijk, FR, Franse Republiek</span><span class="sxs-lookup"><span data-stu-id="c2566-172">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="c2566-173">DE: Duitsland, Duits, Deutschland, Allemagne, DE, Federale Republiek Duitsland, Republiek Duitsland</span><span class="sxs-lookup"><span data-stu-id="c2566-173">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="c2566-174">De verrijking bekijken en een naam geven</span><span class="sxs-lookup"><span data-stu-id="c2566-174">Review and name the enrichment</span></span>

<span data-ttu-id="c2566-175">Tot slot gaat u de informatie bekijken en een naam voor de verrijking opgeven.</span><span class="sxs-lookup"><span data-stu-id="c2566-175">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Pagina voor beoordeling van interesses en naamgeving.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="c2566-177">Verrijking vernieuwen</span><span class="sxs-lookup"><span data-stu-id="c2566-177">Refresh enrichment</span></span>

<span data-ttu-id="c2566-178">Voer de verrijking uit na het configureren van merken, interesses en de veldtoewijzing voor demografische gegevens.</span><span class="sxs-lookup"><span data-stu-id="c2566-178">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="c2566-179">Start het proces door **Uitvoeren** te selecteren op de configuratiepagina voor merken of interesses.</span><span class="sxs-lookup"><span data-stu-id="c2566-179">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="c2566-180">Bovendien kunt u het systeem de verrijking automatisch laten uitvoeren als onderdeel van een geplande vernieuwing.</span><span class="sxs-lookup"><span data-stu-id="c2566-180">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>

<span data-ttu-id="c2566-181">Afhankelijk van de omvang van uw klantgegevens kan het enkele minuten duren voordat een verrijking is voltooid.</span><span class="sxs-lookup"><span data-stu-id="c2566-181">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="c2566-182">Er zijn [zes soorten status](system.md#status-types) voor taken/processen.</span><span class="sxs-lookup"><span data-stu-id="c2566-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="c2566-183">Bovendien zijn de meeste processen [afhankelijk van andere stroomafwaartse processen](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="c2566-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="c2566-184">U kunt de status van een proces selecteren om voortgangsdetails te zien van de volledige taak.</span><span class="sxs-lookup"><span data-stu-id="c2566-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="c2566-185">Na het selecteren van **Zie details** voor een van de taken van de functie vindt u aanvullende informatie: verwerkingstijd, de laatste verwerkingsdatum en alle fouten en waarschuwingen die bij de taak horen.</span><span class="sxs-lookup"><span data-stu-id="c2566-185">After selecting **See details** for one of the job's tasks, you'll find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="c2566-186">Verrijkingsresultaten</span><span class="sxs-lookup"><span data-stu-id="c2566-186">Enrichment results</span></span>

<span data-ttu-id="c2566-187">Na het uitvoeren van het verrijkingsproces gaat u naar **Mijn verrijkingen** om het totale aantal verrijkte klanten en een uitsplitsing van merken of interesses in de verrijkte klantprofielen te bekijken.</span><span class="sxs-lookup"><span data-stu-id="c2566-187">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Voorbeeldweergave van resultaten na het uitvoeren van het verrijkingsproces":::

<span data-ttu-id="c2566-189">Bekijk de verrijkte gegevens door **Verrijkte gegevens weergeven** te selecteren in de grafiek.</span><span class="sxs-lookup"><span data-stu-id="c2566-189">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="c2566-190">Verrijkte gegevens voor merken gaan naar de entiteit **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="c2566-190">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="c2566-191">Gegevens voor interesses bevinden zich in de entiteit **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="c2566-191">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="c2566-192">U vindt deze entiteiten ook in de groep **Verrijking** in **Gegevens** > **Entiteiten**.</span><span class="sxs-lookup"><span data-stu-id="c2566-192">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="c2566-193">Zie verrijkingsgegevens op de klantenkaart</span><span class="sxs-lookup"><span data-stu-id="c2566-193">See enrichment data on the customer card</span></span>

<span data-ttu-id="c2566-194">Merk- en interesse-affiniteiten kunnen ook worden bekeken op individuele klantenkaarten.</span><span class="sxs-lookup"><span data-stu-id="c2566-194">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="c2566-195">Ga naar **Klanten** en selecteer een klantprofiel.</span><span class="sxs-lookup"><span data-stu-id="c2566-195">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="c2566-196">Op de klantkaart vindt u grafieken voor de merken of interesses waarvoor mensen in het demografische profiel van die klant affiniteit hebben.</span><span class="sxs-lookup"><span data-stu-id="c2566-196">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Klantenkaart met verrijkte gegevens":::

## <a name="next-steps"></a><span data-ttu-id="c2566-198">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="c2566-198">Next steps</span></span>

<span data-ttu-id="c2566-199">Bouw voort op uw verrijkte klantgegevens.</span><span class="sxs-lookup"><span data-stu-id="c2566-199">Build on top of your enriched customer data.</span></span> <span data-ttu-id="c2566-200">Maak [segmenten](segments.md) en [metingen](measures.md), en [exporteer de gegevens](export-destinations.md) zelfs om gepersonaliseerde ervaringen aan uw klanten te leveren.</span><span class="sxs-lookup"><span data-stu-id="c2566-200">Create [Segments](segments.md) and [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
