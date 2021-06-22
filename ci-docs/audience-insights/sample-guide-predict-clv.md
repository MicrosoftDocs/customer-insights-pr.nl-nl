---
title: Voorbeeldgids voor voorspelling van de levensduurwaarde van klanten
description: Gebruik deze voorbeeldgids om het voorspellingsmodel voor de levensduurwaarden van klanten uit te proberen.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 73d294a285b4ad706bec7fe925c1daa0b839ddd6
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129939"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="98c84-103">Voorbeeldgids voor voorspelling van de levensduurwaarde van klanten (CLV)</span><span class="sxs-lookup"><span data-stu-id="98c84-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="98c84-104">In deze gids wordt een end-to-end voorbeeld van de voorspelling van de levensduurwaarde van klanten (CLV) in Customer Insights uitgelegd aan de hand van voorbeeldgegevens.</span><span class="sxs-lookup"><span data-stu-id="98c84-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="98c84-105">Scenario</span><span class="sxs-lookup"><span data-stu-id="98c84-105">Scenario</span></span>

<span data-ttu-id="98c84-106">Contoso is een bedrijf dat koffie en koffiemachines van hoge kwaliteit produceert.</span><span class="sxs-lookup"><span data-stu-id="98c84-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="98c84-107">Ze verkopen de producten via hun Contoso Coffee-website.</span><span class="sxs-lookup"><span data-stu-id="98c84-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="98c84-108">Het bedrijf inzicht krijgen in de waarde (omzet) die hun klanten in de komende 12 maanden kunnen genereren.</span><span class="sxs-lookup"><span data-stu-id="98c84-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="98c84-109">Als ze de verwachte waarde van hun klanten in de komende 12 maanden kennen, kunnen ze hun marketinginspanningen op hoogwaardige klanten concentreren.</span><span class="sxs-lookup"><span data-stu-id="98c84-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="98c84-110">Vereisten</span><span class="sxs-lookup"><span data-stu-id="98c84-110">Prerequisites</span></span>

- <span data-ttu-id="98c84-111">Minimaal [inzendermachtigingen](permissions.md) in doelgroepinzichten.</span><span class="sxs-lookup"><span data-stu-id="98c84-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="98c84-112">We raden u aan de volgende stappen te implementeren [in een nieuwe omgeving](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="98c84-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="98c84-113">Taak 1 - Gegevens opnemen</span><span class="sxs-lookup"><span data-stu-id="98c84-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="98c84-114">Bekijk de artikelen [over gegevensopname](data-sources.md) en [het importeren van gegevensbronnen met Power Query-connectors](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="98c84-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="98c84-115">Bij de volgende informatie wordt ervan uitgegaan dat u bekend bent met opnemen van gegevens in het algemeen.</span><span class="sxs-lookup"><span data-stu-id="98c84-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="98c84-116">Klantgegevens opnemen van het e-commerceplatform</span><span class="sxs-lookup"><span data-stu-id="98c84-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="98c84-117">Maak een gegevensbron met de naam **eCommerce**, kies de importoptie en selecteer de connector **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="98c84-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="98c84-118">Voer de URL voor eCommerce-contactpersonen [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts) in.</span><span class="sxs-lookup"><span data-stu-id="98c84-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="98c84-119">Selecteer tijdens het bewerken van de gegevens **Transformeren** en dan **De eerste rij als kopteksten gebruiken**.</span><span class="sxs-lookup"><span data-stu-id="98c84-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="98c84-120">Werk het gegevenstype voor de onderstaande kolommen bij:</span><span class="sxs-lookup"><span data-stu-id="98c84-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="98c84-121">**DateOfBirth**: datum</span><span class="sxs-lookup"><span data-stu-id="98c84-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="98c84-122">**CreatedOn**: datum/tijd/zone</span><span class="sxs-lookup"><span data-stu-id="98c84-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformeer geboortedatum naar datum.":::

1. <span data-ttu-id="98c84-124">Wijzig in het veld 'Naam' in het rechterdeelvenster uw gegevensbron van **Query** in **eCommerceContacts**.</span><span class="sxs-lookup"><span data-stu-id="98c84-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="98c84-125">De gegevensbron **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="98c84-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="98c84-126">Online aankoopgegevens opnemen</span><span class="sxs-lookup"><span data-stu-id="98c84-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="98c84-127">Voeg nog een gegevensset toe aan dezelfde **eCommerce**-gegevensbron.</span><span class="sxs-lookup"><span data-stu-id="98c84-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="98c84-128">Kies opnieuw de connector **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="98c84-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="98c84-129">Voer de URL in voor de gegevens voor **Online aankopen** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="98c84-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="98c84-130">Selecteer tijdens het bewerken van de gegevens **Transformeren** en dan **De eerste rij als kopteksten gebruiken**.</span><span class="sxs-lookup"><span data-stu-id="98c84-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="98c84-131">Werk het gegevenstype voor de onderstaande kolommen bij:</span><span class="sxs-lookup"><span data-stu-id="98c84-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="98c84-132">**PurchasedOn**: datum/tijd</span><span class="sxs-lookup"><span data-stu-id="98c84-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="98c84-133">**TotalPrice**: valuta</span><span class="sxs-lookup"><span data-stu-id="98c84-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="98c84-134">Wijzig in het veld **Naam** in het deelvenster aan de zijkant uw gegevensbron van **Query** in **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="98c84-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="98c84-135">De gegevensbron **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="98c84-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="98c84-136">Klantgegevens opnemen uit het loyaliteitsschema</span><span class="sxs-lookup"><span data-stu-id="98c84-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="98c84-137">Maak een gegevensbron met de naam **LoyaltyScheme**, kies de importoptie en selecteer de connector **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="98c84-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="98c84-138">Voer de URL in voor eCommerce-contacten in https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="98c84-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="98c84-139">Selecteer tijdens het bewerken van de gegevens **Transformeren** en dan **De eerste rij als kopteksten gebruiken**.</span><span class="sxs-lookup"><span data-stu-id="98c84-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="98c84-140">Werk het gegevenstype voor de onderstaande kolommen bij:</span><span class="sxs-lookup"><span data-stu-id="98c84-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="98c84-141">**DateOfBirth**: datum</span><span class="sxs-lookup"><span data-stu-id="98c84-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="98c84-142">**RewardsPoints**: geheel getal</span><span class="sxs-lookup"><span data-stu-id="98c84-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="98c84-143">**CreatedOn**: datum/tijd</span><span class="sxs-lookup"><span data-stu-id="98c84-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="98c84-144">Wijzig in het veld **Naam** in het rechterdeelvenster uw gegevensbron van **Query** in **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="98c84-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="98c84-145">De gegevensbron **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="98c84-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="98c84-146">Klantgegevens van website-reviews opnemen</span><span class="sxs-lookup"><span data-stu-id="98c84-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="98c84-147">Maak een gegevensbron met de naam **Website**, kies de importoptie en selecteer de connector **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="98c84-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="98c84-148">Voer de URL in voor eCommerce-contacten in https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="98c84-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="98c84-149">Selecteer tijdens het bewerken van de gegevens **Transformeren** en dan **De eerste rij als kopteksten gebruiken**.</span><span class="sxs-lookup"><span data-stu-id="98c84-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="98c84-150">Werk het gegevenstype voor de onderstaande kolommen bij:</span><span class="sxs-lookup"><span data-stu-id="98c84-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="98c84-151">**ReviewRating**: decimaal getal</span><span class="sxs-lookup"><span data-stu-id="98c84-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="98c84-152">**ReviewDate**: datum</span><span class="sxs-lookup"><span data-stu-id="98c84-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="98c84-153">Wijzig in het veld 'Naam' in het rechterdeelvenster uw gegevensbron van **Query** in **Beoordelingen**.</span><span class="sxs-lookup"><span data-stu-id="98c84-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="98c84-154">De gegevensbron **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="98c84-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="98c84-155">Taak 2 - Gegevensharmonisatie</span><span class="sxs-lookup"><span data-stu-id="98c84-155">Task 2 - Data unification</span></span>

<span data-ttu-id="98c84-156">Nadat we de gegevens hebben opgenomen, beginnen we nu met het proces voor gegevensharmonisatie om een geharmoniseerd klantprofiel te maken.</span><span class="sxs-lookup"><span data-stu-id="98c84-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="98c84-157">Zie [Gegevensharmonisatie](data-unification.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="98c84-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="98c84-158">Toewijzen</span><span class="sxs-lookup"><span data-stu-id="98c84-158">Map</span></span>

1. <span data-ttu-id="98c84-159">Na het opnemen van de gegevens, wijst u contacten uit eCommerce en Loyaliteitsgegevens toe aan veelgebruikte gegevenstypen.</span><span class="sxs-lookup"><span data-stu-id="98c84-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="98c84-160">Ga naar **Gegevens** > **Unify** > **Toewijzen**.</span><span class="sxs-lookup"><span data-stu-id="98c84-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="98c84-161">Selecteer de entiteiten die het klantprofiel vertegenwoordigen: **eCommerceContacts** en **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="98c84-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="98c84-162">Selecteer vervolgens **Toepassen**.</span><span class="sxs-lookup"><span data-stu-id="98c84-162">Then, select **Apply**.</span></span>

   ![harmoniseer eCommerce- en loyaliteitsgegevensbronnen.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="98c84-164">Selecteer **ContactId** als de primaire sleutel voor **eCommerceContacts** en **LoyaltyID** als de primaire sleutel voor **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="98c84-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Harmoniseer LoyaltyId als primaire sleutel.](media/unify-loyaltyid.png)

1. <span data-ttu-id="98c84-166">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="98c84-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="98c84-167">Bij elkaar zoeken</span><span class="sxs-lookup"><span data-stu-id="98c84-167">Match</span></span>

1. <span data-ttu-id="98c84-168">Ga naar het tabblad **Matchen** en selecteer **Volgorde instellen**.</span><span class="sxs-lookup"><span data-stu-id="98c84-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="98c84-169">Kies in de vervolgkeuzelijst **Primair** de optie **eCommerceContacts: eCommerce** als primaire bron en neem alle records op.</span><span class="sxs-lookup"><span data-stu-id="98c84-169">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="98c84-170">Kies in de vervolgkeuzelijst **Entiteit 2** de optie **loyCustomers: LoyaltyScheme** en neem alle records op.</span><span class="sxs-lookup"><span data-stu-id="98c84-170">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Harmoniseer match eCommerce en Loyaliteit](media/unify-match-order.png)

1. <span data-ttu-id="98c84-172">Selecteer **Regel toevoegen**</span><span class="sxs-lookup"><span data-stu-id="98c84-172">Select **Add rule**</span></span>

1. <span data-ttu-id="98c84-173">Voeg uw eerste voorwaarde toe met FullName.</span><span class="sxs-lookup"><span data-stu-id="98c84-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="98c84-174">Selecteer voor eCommerceContacts **FullName** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="98c84-174">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="98c84-175">Selecteer voor loyCustomers **FullName** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="98c84-175">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="98c84-176">Selecteer de vervolgkeuzelijst **Normaliseren** en kies **Type (telefoon, naam, adres, ...)**.</span><span class="sxs-lookup"><span data-stu-id="98c84-176">Select the **Normalize** drop-down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="98c84-177">Stel **Precisieniveau**: **Basic** en **Waarde**: **Hoog** in.</span><span class="sxs-lookup"><span data-stu-id="98c84-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="98c84-178">Voer de naam **FullName, Email** in voor de nieuwe regel.</span><span class="sxs-lookup"><span data-stu-id="98c84-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="98c84-179">Voeg een tweede voorwaarde voor het e-mailadres toe door **Voorwaarde toevoegen** te selecteren</span><span class="sxs-lookup"><span data-stu-id="98c84-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="98c84-180">Kies voor entiteit eCommerceContacts **EMail** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="98c84-180">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="98c84-181">Kies voor entiteit loyCustomers **EMail** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="98c84-181">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="98c84-182">Laat Normaliseren leeg.</span><span class="sxs-lookup"><span data-stu-id="98c84-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="98c84-183">Stel **Precisieniveau**: **Basic** en **Waarde**: **Hoog** in.</span><span class="sxs-lookup"><span data-stu-id="98c84-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Harmoniseer de matchregel voor naam en e-mailadres.](media/unify-match-rule.png)

1. <span data-ttu-id="98c84-185">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="98c84-185">Select **Done**.</span></span>

1. <span data-ttu-id="98c84-186">Selecteer **Opslaan** en **Uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="98c84-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="98c84-187">Samenvoeging</span><span class="sxs-lookup"><span data-stu-id="98c84-187">Merge</span></span>

1. <span data-ttu-id="98c84-188">Ga naar het tabblad **Samenvoegen**.</span><span class="sxs-lookup"><span data-stu-id="98c84-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="98c84-189">Bij **ContactId** voor de entiteit **loyCustomers** wijzigt u de weergavenaam in **ContactIdLOYALTY** om deze te onderscheiden van de andere opgenomen id's.</span><span class="sxs-lookup"><span data-stu-id="98c84-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![hernoem contactid van loyaliteits-id.](media/unify-merge-contactid.png)

1. <span data-ttu-id="98c84-191">Selecteer **Opslaan** en **Samenvoegen en downstreamprocessen uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="98c84-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="98c84-192">Taak 3 - De voorspelling van de levensduurwaarde van klanten configureren</span><span class="sxs-lookup"><span data-stu-id="98c84-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="98c84-193">Met de geharmoniseerde klantprofielen kunnen we nu de voorspelling voor de levensduurwaarde van klanten uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="98c84-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="98c84-194">Zie [Voorspelling van levensduurwaarde van klant (preview)](predict-customer-lifetime-value.md) voor gedetailleerde stappen.</span><span class="sxs-lookup"><span data-stu-id="98c84-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="98c84-195">Ga naar **Informatie**  > **Voorspellingen** en selecteer **Model voor waarde voor levensduur van klant**.</span><span class="sxs-lookup"><span data-stu-id="98c84-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="98c84-196">Neem de informatie in het zijvenster door en selecteer **Aan de slag**.</span><span class="sxs-lookup"><span data-stu-id="98c84-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="98c84-197">Geef het model **OOB eCommerce CLV-voorspelling** en de uitvoerentiteit **OOBeCommerceCLVPrediction** een naam.</span><span class="sxs-lookup"><span data-stu-id="98c84-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="98c84-198">Definieer modelvoorkeuren voor het CLV-model:</span><span class="sxs-lookup"><span data-stu-id="98c84-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="98c84-199">**Periode van voorspellingstijd**: **12 maanden of 1 jaar**.</span><span class="sxs-lookup"><span data-stu-id="98c84-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="98c84-200">Deze instelling definieert hoe ver in de toekomst de levensduurwaarde van de klant moet worden voorspeld.</span><span class="sxs-lookup"><span data-stu-id="98c84-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="98c84-201">**Actieve klanten**: specificeer wat actieve klanten voor uw bedrijf betekenen.</span><span class="sxs-lookup"><span data-stu-id="98c84-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="98c84-202">Stel de historische tijdsbestek in waarin een klant ten minste één transactie moet hebben gehad om als actief te worden beschouwd.</span><span class="sxs-lookup"><span data-stu-id="98c84-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="98c84-203">Het model voorspelt alleen levensduurwaarde voor actieve klanten.</span><span class="sxs-lookup"><span data-stu-id="98c84-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="98c84-204">Kies ervoor om het model de tijdsperiode te laten berekenen op basis van historische transactiegegevens of een specifiek tijdsbestek op te geven.</span><span class="sxs-lookup"><span data-stu-id="98c84-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="98c84-205">In deze voorbeeldgids kiezen we voor **Model het aankoopinterval laten berekenen**, wat de standaardoptie is.</span><span class="sxs-lookup"><span data-stu-id="98c84-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="98c84-206">**Klanten met hoge waarde**: definieer klanten met hoge waarde als een percentiel van best betalende klanten.</span><span class="sxs-lookup"><span data-stu-id="98c84-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="98c84-207">Het model gebruikt deze invoer om resultaten te leveren die passen bij uw bedrijfsdefinitie van klanten met hoge waarde.</span><span class="sxs-lookup"><span data-stu-id="98c84-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="98c84-208">U kunt ervoor kiezen om het model klanten met hoge waarde te laten definiëren.</span><span class="sxs-lookup"><span data-stu-id="98c84-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="98c84-209">Het gebruikt een heuristische regel waarmee het percentiel wordt afgeleid.</span><span class="sxs-lookup"><span data-stu-id="98c84-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="98c84-210">U kunt ook klanten met hoge waarde definiëren als een percentiel van best betalende klanten in de toekomst.</span><span class="sxs-lookup"><span data-stu-id="98c84-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="98c84-211">In deze voorbeeldgids definiëren we klanten met hoge waarde handmatig als **top 30% van actieve betalende klanten** en selecteren **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="98c84-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Voorkeurenstap in de begeleide ervaring voor het CLV-model.":::

1. <span data-ttu-id="98c84-213">Selecteer in de stap **Vereiste gegevens** de optie **Gegevens toevoegen** om de transactiegeschiedenisgegevens te verstrekken.</span><span class="sxs-lookup"><span data-stu-id="98c84-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="98c84-214">Voeg de entiteit **eCommercePurchaces : eCommerce** toe en wijs de kenmerken toe die vereist zijn door het model:</span><span class="sxs-lookup"><span data-stu-id="98c84-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="98c84-215">Transactie-id: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="98c84-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="98c84-216">Transactiedatum: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="98c84-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="98c84-217">Transactiebedrag: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="98c84-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="98c84-218">Product-id: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="98c84-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="98c84-219">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="98c84-219">Select **Next**.</span></span>

1. <span data-ttu-id="98c84-220">Stel de relatie in tussen de entiteit **eCommercePurchases : eCommerce** en **eCommerceContacten : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="98c84-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="98c84-221">Via de stap **Aanvullende gegevens (optioneel)** kunt u meer klantactiviteitsgegevens toevoegen.</span><span class="sxs-lookup"><span data-stu-id="98c84-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="98c84-222">Deze gegevens kunnen helpen om meer inzicht te krijgen in klantinteracties met uw bedrijf, wat kan bijdragen aan CLV.</span><span class="sxs-lookup"><span data-stu-id="98c84-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="98c84-223">Door toevoeging van belangrijke klantinteracties zoals weblogs, klantenservicelogboeken of geschiedenis van beloningsprogramma's kan de nauwkeurigheid van voorspellingen worden verbeterd.</span><span class="sxs-lookup"><span data-stu-id="98c84-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="98c84-224">Selecteer **Gegevens toevoegen** om meer klantactiviteitsgegevens op te nemen.</span><span class="sxs-lookup"><span data-stu-id="98c84-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="98c84-225">Voeg de entiteit Klantactiviteit toe en wijs de bijbehorende veldnamen toe aan de overeenkomstige velden die door het model worden vereist:</span><span class="sxs-lookup"><span data-stu-id="98c84-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="98c84-226">Entiteit Klantactiviteit: Reviews:Website</span><span class="sxs-lookup"><span data-stu-id="98c84-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="98c84-227">Primaire sleutel: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="98c84-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="98c84-228">Timestamp Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="98c84-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="98c84-229">Gebeurtenis (naam activiteit): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="98c84-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="98c84-230">Details (bedrag of waarde): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="98c84-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="98c84-231">Selecteer **Volgende** en configureer de activiteit en de relatie tussen de transactiegegevens en de klantgegevens:</span><span class="sxs-lookup"><span data-stu-id="98c84-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="98c84-232">Type activiteit: kies bestaande</span><span class="sxs-lookup"><span data-stu-id="98c84-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="98c84-233">Activiteitslabel: Review</span><span class="sxs-lookup"><span data-stu-id="98c84-233">Activity label: Review</span></span>
   - <span data-ttu-id="98c84-234">Overeenkomstig label: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="98c84-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="98c84-235">Klantentiteit: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="98c84-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="98c84-236">Relatie: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="98c84-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="98c84-237">Selecteer **Volgende** om de modelplanning in te stellen.</span><span class="sxs-lookup"><span data-stu-id="98c84-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="98c84-238">Het model moet regelmatig trainen om nieuwe patronen te leren wanneer er nieuwe gegevens worden opgenomen.</span><span class="sxs-lookup"><span data-stu-id="98c84-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="98c84-239">Kies voor dit voorbeeld de optie **Maandelijks**.</span><span class="sxs-lookup"><span data-stu-id="98c84-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="98c84-240">Selecteer nadat u alle details hebt nagekeken **Opslaan en uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="98c84-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="98c84-241">Taak 4 - Bekijk modelresultaten en uitleg</span><span class="sxs-lookup"><span data-stu-id="98c84-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="98c84-242">Laat het model de training en score van de gegevens voltooien.</span><span class="sxs-lookup"><span data-stu-id="98c84-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="98c84-243">Vervolgens kunt u de resultaten en uitleg van het CLV-model bekijken.</span><span class="sxs-lookup"><span data-stu-id="98c84-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="98c84-244">Zie [Een voorspellingsstatus en resultaten beoordelen](predict-customer-lifetime-value.md#review-prediction-status-and-results) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="98c84-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="98c84-245">Taak 5 - Een segment van klanten met hoge waarde maken</span><span class="sxs-lookup"><span data-stu-id="98c84-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="98c84-246">Door het model uit te voeren, wordt een nieuwe entiteit gemaakt, die wordt vermeld in **Gegevens** > **Entiteiten**.</span><span class="sxs-lookup"><span data-stu-id="98c84-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="98c84-247">U kunt een nieuw klantsegment maken op basis van de entiteit die door het model is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="98c84-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="98c84-248">Ga naar **Segmenten**.</span><span class="sxs-lookup"><span data-stu-id="98c84-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="98c84-249">Selecteer **Nieuw** en kies **Maken van** > **Informatie**.</span><span class="sxs-lookup"><span data-stu-id="98c84-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Een segment maken met de modeluitvoer.](media/segment-intelligence.png)

1. <span data-ttu-id="98c84-251">Selecteer de entiteit **OOBeCommerceCLVPrediction** en definieer het segment:</span><span class="sxs-lookup"><span data-stu-id="98c84-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="98c84-252">Veld: CLVScore</span><span class="sxs-lookup"><span data-stu-id="98c84-252">Field: CLVScore</span></span>
  - <span data-ttu-id="98c84-253">Operator: groter dan</span><span class="sxs-lookup"><span data-stu-id="98c84-253">Operator: greater than</span></span>
  - <span data-ttu-id="98c84-254">Waarde: 1500</span><span class="sxs-lookup"><span data-stu-id="98c84-254">Value: 1500</span></span>

1. <span data-ttu-id="98c84-255">Selecteer **Beoordeling** en **Opslaan** voor het segment.</span><span class="sxs-lookup"><span data-stu-id="98c84-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="98c84-256">U hebt nu een segment dat klanten identificeert waarvan wordt voorspeld dat ze in de komende 12 maanden meer dan $ 1500 aan inkomsten zullen genereren.</span><span class="sxs-lookup"><span data-stu-id="98c84-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="98c84-257">Dit segment wordt dynamisch bijgewerkt als er meer gegevens worden opgenomen.</span><span class="sxs-lookup"><span data-stu-id="98c84-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="98c84-258">Zie [Segmenten maken en beheren](segments.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="98c84-258">For more information, see [Create and manage segments](segments.md).</span></span>
