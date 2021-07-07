---
title: Verrijking van adresuitbreiding
description: Verrijk en normaliseer adresgegevens van klantprofielen met de modellen van Microsoft.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e0ca731f944da9a7eaae7c2dc2d7568b6386089f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305426"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="fa976-103">Verrijking van klantprofielen met uitgebreide adressen</span><span class="sxs-lookup"><span data-stu-id="fa976-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="fa976-104">Adressen in uw gegevens kunnen ongestructureerd, onvolledig of onjuist zijn.</span><span class="sxs-lookup"><span data-stu-id="fa976-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="fa976-105">Gebruik de modellen van Microsoft om uw adressen te normaliseren en te verrijken met de [Common Data Model-indeling](/common-data-model/schema/core/applicationcommon/address) voor betere nauwkeurigheid en inzichten.</span><span class="sxs-lookup"><span data-stu-id="fa976-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="fa976-106">Adressen uitbreiden</span><span class="sxs-lookup"><span data-stu-id="fa976-106">How we enhance addresses</span></span>

<span data-ttu-id="fa976-107">Ons model doorloopt een proces in twee stappen om een adres uit te breiden.</span><span class="sxs-lookup"><span data-stu-id="fa976-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="fa976-108">Eerst wordt het adres geparseerd om de onderdelen ervan te identificeren en worden deze onderdelen in een gestructureerde indeling geplaatst.</span><span class="sxs-lookup"><span data-stu-id="fa976-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="fa976-109">Vervolgens gebruiken we AI om de waarden in het adres te corrigeren, aan te vullen en te standaardiseren.</span><span class="sxs-lookup"><span data-stu-id="fa976-109">Then, we use AI to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="fa976-110">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="fa976-110">Example</span></span>

<span data-ttu-id="fa976-111">Adresgegevens kunnen een afwijkende notatie hebben en spelfouten bevatten.</span><span class="sxs-lookup"><span data-stu-id="fa976-111">Address information might be in a nonstandard format and contain spelling errors.</span></span> <span data-ttu-id="fa976-112">Met het model kunnen deze problemen worden opgelost en kunnen consistente adressen in uniforme klantprofielen worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="fa976-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="fa976-113">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="fa976-113">Limitations</span></span>

<span data-ttu-id="fa976-114">Uitgebreide adressen werken alleen met de waarden die al bestaan in uw opgenomen adresgegevens.</span><span class="sxs-lookup"><span data-stu-id="fa976-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="fa976-115">Het model doet het volgende niet:</span><span class="sxs-lookup"><span data-stu-id="fa976-115">The model doesn't:</span></span> 

1. <span data-ttu-id="fa976-116">Controleren of het adres een geldig adres is.</span><span class="sxs-lookup"><span data-stu-id="fa976-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="fa976-117">Controleren of de waarden, zoals postcodes of straatnamen, geldig zijn.</span><span class="sxs-lookup"><span data-stu-id="fa976-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="fa976-118">Waarden wijzigen die niet worden herkend.</span><span class="sxs-lookup"><span data-stu-id="fa976-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="fa976-119">Het model maakt gebruik van op machine learning gebaseerde methoden om adressen uit te breiden.</span><span class="sxs-lookup"><span data-stu-id="fa976-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="fa976-120">Hoewel we een hoge betrouwbaarheidsdrempel toepassen voor wanneer het model een invoerwaarde wijzigt, is 100 procent nauwkeurigheid niet gegarandeerd, zoals bij elk model dat is gebaseerd op machine learning.</span><span class="sxs-lookup"><span data-stu-id="fa976-120">While we apply a high confidence threshold for when the model changes an input value, as with any machine learning-based model, 100 percent accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="fa976-121">Ondersteunde landen of regio's</span><span class="sxs-lookup"><span data-stu-id="fa976-121">Supported countries or regions</span></span>

<span data-ttu-id="fa976-122">We ondersteunen momenteel uitgebreide adressen in de volgende landen of regio's:</span><span class="sxs-lookup"><span data-stu-id="fa976-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="fa976-123">Australië</span><span class="sxs-lookup"><span data-stu-id="fa976-123">Australia</span></span>
- <span data-ttu-id="fa976-124">Canada</span><span class="sxs-lookup"><span data-stu-id="fa976-124">Canada</span></span>
- <span data-ttu-id="fa976-125">Verenigd Koninkrijk</span><span class="sxs-lookup"><span data-stu-id="fa976-125">United Kingdom</span></span>
- <span data-ttu-id="fa976-126">Verenigde Staten</span><span class="sxs-lookup"><span data-stu-id="fa976-126">United States</span></span>

<span data-ttu-id="fa976-127">Adressen moeten een waarde voor land/regio bevatten.</span><span class="sxs-lookup"><span data-stu-id="fa976-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="fa976-128">Adressen voor landen of regio's die niet worden ondersteund en adressen waarvoor geen land of regio is opgegeven, worden niet verwerkt.</span><span class="sxs-lookup"><span data-stu-id="fa976-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="fa976-129">De verrijking configureren</span><span class="sxs-lookup"><span data-stu-id="fa976-129">Configure the enrichment</span></span>

1. <span data-ttu-id="fa976-130">Ga naar **Gegevens** > **Verrijking**.</span><span class="sxs-lookup"><span data-stu-id="fa976-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="fa976-131">Selecteer **Mijn gegevens verrijken** op de tegel **Uitgebreide adressen**.</span><span class="sxs-lookup"><span data-stu-id="fa976-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Schermopname van de tegel Uitgebreide adressen.":::

1. <span data-ttu-id="fa976-133">Selecteer de **Klantgegevensset** en kies de entiteit met de adressen die u wilt verrijken.</span><span class="sxs-lookup"><span data-stu-id="fa976-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="fa976-134">U kunt de entiteit *Klant* selecteren om adressen in al uw klantprofielen te verrijken of u kunt een segmententiteit selecteren om adressen alleen in klantprofielen in dat segment te verrijken.</span><span class="sxs-lookup"><span data-stu-id="fa976-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="fa976-135">Selecteer hoe adressen worden opgemaakt in uw gegevensset.</span><span class="sxs-lookup"><span data-stu-id="fa976-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="fa976-136">Kies **Adres met één kenmerk** als adressen in uw gegevens één veld gebruiken.</span><span class="sxs-lookup"><span data-stu-id="fa976-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="fa976-137">Kies **Adres met meerdere kenmerken** als adressen in uw gegevens meerdere gegevensvelden gebruiken.</span><span class="sxs-lookup"><span data-stu-id="fa976-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="fa976-138">Land/regio is verplicht in zowel adressen met enkelvoudige kenmerken als adressen met meervoudige kenmerken.</span><span class="sxs-lookup"><span data-stu-id="fa976-138">Country/Region is mandatory in both single-attribute and multiple-attribute addresses.</span></span> <span data-ttu-id="fa976-139">Adressen die geen geldige of ondersteunde waarden voor land/regio bevatten, worden niet verrijkt.</span><span class="sxs-lookup"><span data-stu-id="fa976-139">Addresses that don't contain valid or supported country/region values won't be enriched.</span></span>

1.  <span data-ttu-id="fa976-140">Wijs de adresvelden vanuit uw uniforme klantentiteit toe.</span><span class="sxs-lookup"><span data-stu-id="fa976-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Veldtoewijzingspagina voor uitgebreide adressen.":::

1. <span data-ttu-id="fa976-142">Selecteer **Volgende** om de veldtoewijzing te voltooien.</span><span class="sxs-lookup"><span data-stu-id="fa976-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="fa976-143">Geef een naam op voor de verrijking en de uitvoerentiteit.</span><span class="sxs-lookup"><span data-stu-id="fa976-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="fa976-144">Selecteer **Verrijking opslaan** na het bekijken van uw keuzes.</span><span class="sxs-lookup"><span data-stu-id="fa976-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="fa976-145">Verrijkingsresultaten</span><span class="sxs-lookup"><span data-stu-id="fa976-145">Enrichment results</span></span>

<span data-ttu-id="fa976-146">Selecteer **Uitvoeren** vanaf de opdrachtbalk om het verrijkingsproces te starten.</span><span class="sxs-lookup"><span data-stu-id="fa976-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="fa976-147">U kunt de verrijking ook automatisch laten uitvoeren als onderdeel van een [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fa976-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="fa976-148">De verwerkingstijd is afhankelijk van de grootte van uw klantgegevens.</span><span class="sxs-lookup"><span data-stu-id="fa976-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="fa976-149">Nadat het verrijkingsproces is voltooid, kunt u de nieuwe verrijkte klantprofielgegevens bekijken onder **Mijn verrijkingen**.</span><span class="sxs-lookup"><span data-stu-id="fa976-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="fa976-150">Ook vindt u daar het tijdstip van de laatste update en het aantal verrijkte profielen.</span><span class="sxs-lookup"><span data-stu-id="fa976-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="fa976-151">U kunt een gedetailleerd overzicht van elk verrijkt profiel openen door **Verrijkte gegevens weergeven** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="fa976-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fa976-152">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="fa976-152">Next steps</span></span>

<span data-ttu-id="fa976-153">Bouw voort op uw verrijkte klantgegevens.</span><span class="sxs-lookup"><span data-stu-id="fa976-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="fa976-154">Maak [segmenten](segments.md) en [metingen](measures.md), en [exporteer de gegevens](export-destinations.md) zelfs om gepersonaliseerde ervaringen aan uw klanten te leveren.</span><span class="sxs-lookup"><span data-stu-id="fa976-154">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
