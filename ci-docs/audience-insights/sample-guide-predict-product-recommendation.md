---
title: Voorbeeldgids voor voorspelling van productaanbevelingen
description: Gebruik deze voorbeeldhandleiding om het standaard voorspellingsmodel voor productaanbevelingen uit te proberen.
ms.date: 02/10/2021
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ee873d9b7caa5f891cb2d5b8c665dec90ad0e59
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270482"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="fe577-103">Voorbeeldgids voor voorspelling van productaanbevelingen (preview)</span><span class="sxs-lookup"><span data-stu-id="fe577-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="fe577-104">We laten u een compleet voorbeeld van productaanbevelingsvoorspelling zien aan de hand van de onderstaande voorbeeldgegevens.</span><span class="sxs-lookup"><span data-stu-id="fe577-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="fe577-105">Scenario</span><span class="sxs-lookup"><span data-stu-id="fe577-105">Scenario</span></span>

<span data-ttu-id="fe577-106">Contoso is een bedrijf dat koffie- en koffiemachines van hoge kwaliteit produceert, die ze verkopen via hun Contoso Coffee-website.</span><span class="sxs-lookup"><span data-stu-id="fe577-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="fe577-107">Het doel is om te begrijpen welke producten ze moeten aanbevelen aan hun terugkerende klanten.</span><span class="sxs-lookup"><span data-stu-id="fe577-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="fe577-108">Weten wat klanten **eerder zullen kopen**, kan hen helpen marketinginspanningen te besparen door zich op specifieke artikelen te richten.</span><span class="sxs-lookup"><span data-stu-id="fe577-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fe577-109">Vereisten</span><span class="sxs-lookup"><span data-stu-id="fe577-109">Prerequisites</span></span>

- <span data-ttu-id="fe577-110">Minimaal [inzendermachtigingen](permissions.md) in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="fe577-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="fe577-111">We raden u aan de volgende stappen te implementeren [in een nieuwe omgeving](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="fe577-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="fe577-112">Taak 1 - Gegevens opnemen</span><span class="sxs-lookup"><span data-stu-id="fe577-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="fe577-113">Lees vooral de artikelen [over gegevensopname](data-sources.md) en [gegevensbronnen importeren met Power Query-connectors](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="fe577-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="fe577-114">Bij de volgende informatie wordt ervan uitgegaan dat u bekend bent met opnemen van gegevens in het algemeen.</span><span class="sxs-lookup"><span data-stu-id="fe577-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="fe577-115">Klantgegevens opnemen van het e-commerceplatform</span><span class="sxs-lookup"><span data-stu-id="fe577-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="fe577-116">Maak een gegevensbron met de naam **eCommerce**, kies de importoptie en selecteer de connector **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="fe577-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="fe577-117">Voer de URL in voor eCommerce-contacten in https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="fe577-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="fe577-118">Selecteer tijdens het bewerken van de gegevens **Transformeren** en dan **De eerste rij als kopteksten gebruiken**.</span><span class="sxs-lookup"><span data-stu-id="fe577-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="fe577-119">Werk het gegevenstype voor de onderstaande kolommen bij:</span><span class="sxs-lookup"><span data-stu-id="fe577-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="fe577-120">**DateOfBirth**: datum</span><span class="sxs-lookup"><span data-stu-id="fe577-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="fe577-121">**CreatedOn**: datum/tijd/zone</span><span class="sxs-lookup"><span data-stu-id="fe577-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformeer geboortedatum naar datum.":::

5. <span data-ttu-id="fe577-123">Wijzig in het veld 'Naam' in het rechterdeelvenster uw gegevensbron van **Query** in **eCommerceContacts**.</span><span class="sxs-lookup"><span data-stu-id="fe577-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="fe577-124">De gegevensbron **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="fe577-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="fe577-125">Online aankoopgegevens opnemen</span><span class="sxs-lookup"><span data-stu-id="fe577-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="fe577-126">Voeg nog een gegevensset toe aan dezelfde **eCommerce**-gegevensbron.</span><span class="sxs-lookup"><span data-stu-id="fe577-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="fe577-127">Kies opnieuw de connector **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="fe577-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="fe577-128">Voer de URL in voor de gegevens voor **Online aankopen** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="fe577-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="fe577-129">Selecteer tijdens het bewerken van de gegevens **Transformeren** en dan **De eerste rij als kopteksten gebruiken**.</span><span class="sxs-lookup"><span data-stu-id="fe577-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="fe577-130">Werk het gegevenstype voor de onderstaande kolommen bij:</span><span class="sxs-lookup"><span data-stu-id="fe577-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="fe577-131">**PurchasedOn**: datum/tijd</span><span class="sxs-lookup"><span data-stu-id="fe577-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="fe577-132">**TotalPrice**: valuta</span><span class="sxs-lookup"><span data-stu-id="fe577-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="fe577-133">Wijzig in het veld **Naam** in het deelvenster aan de zijkant uw gegevensbron van **Query** in **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="fe577-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="fe577-134">Sla de gegevensbron op.</span><span class="sxs-lookup"><span data-stu-id="fe577-134">Save the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="fe577-135">Klantgegevens opnemen uit het loyaliteitsschema</span><span class="sxs-lookup"><span data-stu-id="fe577-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="fe577-136">Maak een gegevensbron met de naam **LoyaltyScheme**, kies de importoptie en selecteer de connector **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="fe577-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="fe577-137">Voer de URL in voor eCommerce-contacten in https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="fe577-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="fe577-138">Selecteer tijdens het bewerken van de gegevens **Transformeren** en dan **De eerste rij als kopteksten gebruiken**.</span><span class="sxs-lookup"><span data-stu-id="fe577-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="fe577-139">Werk het gegevenstype voor de onderstaande kolommen bij:</span><span class="sxs-lookup"><span data-stu-id="fe577-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="fe577-140">**DateOfBirth**: datum</span><span class="sxs-lookup"><span data-stu-id="fe577-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="fe577-141">**RewardsPoints**: geheel getal</span><span class="sxs-lookup"><span data-stu-id="fe577-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="fe577-142">**CreatedOn**: datum/tijd</span><span class="sxs-lookup"><span data-stu-id="fe577-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="fe577-143">Wijzig in het veld **Naam** in het rechterdeelvenster uw gegevensbron van **Query** in **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="fe577-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="fe577-144">Sla de gegevensbron op.</span><span class="sxs-lookup"><span data-stu-id="fe577-144">Save the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="fe577-145">Taak 2 - Gegevensharmonisatie</span><span class="sxs-lookup"><span data-stu-id="fe577-145">Task 2 - Data unification</span></span>

<span data-ttu-id="fe577-146">Na het opnemen van de gegevens beginnen we nu met het proces **Toewijzen, Matchen, Samenvoegen** om een geharmoniseerd klantprofiel te maken.</span><span class="sxs-lookup"><span data-stu-id="fe577-146">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="fe577-147">Zie [Gegevensharmonisatie](data-unification.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="fe577-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="fe577-148">Toewijzen</span><span class="sxs-lookup"><span data-stu-id="fe577-148">Map</span></span>

1. <span data-ttu-id="fe577-149">Na het opnemen van de gegevens, wijst u contacten uit eCommerce en Loyaliteitsgegevens toe aan veelgebruikte gegevenstypen.</span><span class="sxs-lookup"><span data-stu-id="fe577-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="fe577-150">Ga naar **Gegevens** > **Unify** > **Toewijzen**.</span><span class="sxs-lookup"><span data-stu-id="fe577-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="fe577-151">Selecteer de entiteiten die het klantprofiel vertegenwoordigen: **eCommerceContacts** en **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="fe577-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![harmoniseer eCommerce- en loyaliteitsgegevensbronnen.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="fe577-153">Selecteer **ContactId** als de primaire sleutel voor **eCommerceContacts** en **LoyaltyID** als de primaire sleutel voor **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="fe577-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Harmoniseer LoyaltyId als primaire sleutel.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="fe577-155">Bij elkaar zoeken</span><span class="sxs-lookup"><span data-stu-id="fe577-155">Match</span></span>

1. <span data-ttu-id="fe577-156">Ga naar het tabblad **Matchen** en selecteer **Volgorde instellen**.</span><span class="sxs-lookup"><span data-stu-id="fe577-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="fe577-157">Kies in de vervolgkeuzelijst **Primair** de optie **eCommerceContacts: eCommerce** als primaire bron en neem alle records op.</span><span class="sxs-lookup"><span data-stu-id="fe577-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="fe577-158">Kies in de vervolgkeuzelijst **Entiteit 2** de optie **loyCustomers: LoyaltyScheme** en neem alle records op.</span><span class="sxs-lookup"><span data-stu-id="fe577-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Harmoniseer match eCommerce en Loyaliteit](media/unify-match-order.png)

4. <span data-ttu-id="fe577-160">Selecteer **Een nieuwe regel maken**</span><span class="sxs-lookup"><span data-stu-id="fe577-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="fe577-161">Voeg uw eerste voorwaarde toe met FullName.</span><span class="sxs-lookup"><span data-stu-id="fe577-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="fe577-162">Selecteer voor eCommerceContacts **FullName** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="fe577-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="fe577-163">Selecteer voor loyCustomers **FullName** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="fe577-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="fe577-164">Selecteer de vervolgkeuzelijst **Normaliseren** en kies **Type (telefoon, naam, adres, ...)**.</span><span class="sxs-lookup"><span data-stu-id="fe577-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="fe577-165">Stel **Precisieniveau**: **Basic** en **Waarde**: **Hoog** in.</span><span class="sxs-lookup"><span data-stu-id="fe577-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="fe577-166">Voer de naam **FullName, Email** in voor de nieuwe regel.</span><span class="sxs-lookup"><span data-stu-id="fe577-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="fe577-167">Voeg een tweede voorwaarde voor het e-mailadres toe door **Voorwaarde toevoegen** te selecteren</span><span class="sxs-lookup"><span data-stu-id="fe577-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="fe577-168">Kies voor entiteit eCommerceContacts **EMail** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="fe577-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="fe577-169">Kies voor entiteit loyCustomers **EMail** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="fe577-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="fe577-170">Laat Normaliseren leeg.</span><span class="sxs-lookup"><span data-stu-id="fe577-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="fe577-171">Stel **Precisieniveau**: **Basic** en **Waarde**: **Hoog** in.</span><span class="sxs-lookup"><span data-stu-id="fe577-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Harmoniseer de matchregel voor naam en e-mailadres.](media/unify-match-rule.png)

7. <span data-ttu-id="fe577-173">Selecteer **Opslaan** en **Uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="fe577-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="fe577-174">Samenvoeging</span><span class="sxs-lookup"><span data-stu-id="fe577-174">Merge</span></span>

1. <span data-ttu-id="fe577-175">Ga naar het tabblad **Samenvoegen**.</span><span class="sxs-lookup"><span data-stu-id="fe577-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="fe577-176">Bij **ContactId** voor de entiteit **loyCustomers** wijzigt u de weergavenaam in **ContactIdLOYALTY** om deze te onderscheiden van de andere opgenomen id's.</span><span class="sxs-lookup"><span data-stu-id="fe577-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![hernoem contactid van loyaliteits-id.](media/unify-merge-contactid.png)

1. <span data-ttu-id="fe577-178">Selecteer **Opslaan** en **Uitvoeren** om het samenvoegingsproces te starten.</span><span class="sxs-lookup"><span data-stu-id="fe577-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="fe577-179">Taak 3 - Voorspelling van productaanbevelingen configureren</span><span class="sxs-lookup"><span data-stu-id="fe577-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="fe577-180">Met de geharmoniseerde klantprofielen op hun plaats, kunnen we nu het abonnementsverloop voorspellen.</span><span class="sxs-lookup"><span data-stu-id="fe577-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="fe577-181">Ga naar **Informatie** > **Voorspelling** en kies **Productaanbeveling**​.</span><span class="sxs-lookup"><span data-stu-id="fe577-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="fe577-182">Selecteer **Aan de slag**.</span><span class="sxs-lookup"><span data-stu-id="fe577-182">Select **Get started**.</span></span>

1. <span data-ttu-id="fe577-183">Geef het model de naam **OOB productaanbevelingsmodel voorspelling** en de uitvoer-entiteit **OOBproductRecommendationModelPrediction**​.</span><span class="sxs-lookup"><span data-stu-id="fe577-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="fe577-184">Definieer drie voorwaarden voor het model:</span><span class="sxs-lookup"><span data-stu-id="fe577-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="fe577-185">**Aantal producten**: stel deze waarde in op **5**​.</span><span class="sxs-lookup"><span data-stu-id="fe577-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="fe577-186">Deze instelling bepaalt hoeveel producten u uw klanten wilt aanbevelen.</span><span class="sxs-lookup"><span data-stu-id="fe577-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="fe577-187">**Producten voorstellen die klanten onlangs hebben gekocht?**: selecteer **Ja** om aan te geven dat u producten wilt opnemen in de aanbeveling die uw klanten eerder hebben gekocht.</span><span class="sxs-lookup"><span data-stu-id="fe577-187">**Suggest products customers have recently purchased?**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="fe577-188">**Terugkijkvenster**: selecteer minimaal **365 dagen**​.</span><span class="sxs-lookup"><span data-stu-id="fe577-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="fe577-189">Deze instelling bepaalt hoe ver het model terugkijkt naar de activiteit van de klant om deze te gebruiken als invoer voor de aanbevelingen.</span><span class="sxs-lookup"><span data-stu-id="fe577-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Modelvoorkeuren voor het aanbevelingsmodel voor producten.":::

1. <span data-ttu-id="fe577-191">Selecteer **Vereiste gegevens** en selecteer **Gegevens toevoegen** voor aankoopgeschiedenis.</span><span class="sxs-lookup"><span data-stu-id="fe577-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="fe577-192">Voeg de entiteit **eCommercePurchases : eCommerce** toe en wijs de velden van eCommerce toe aan de overeenkomstige velden die vereist zijn voor het model.</span><span class="sxs-lookup"><span data-stu-id="fe577-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="fe577-193">Voeg de entiteit **eCommercePurchases : eCommerce** samen met **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="fe577-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![Voeg eCommerce-entiteiten samen.](media/model-purchase-join.png)

1. <span data-ttu-id="fe577-195">Selecteer **Volgende** om de modelplanning in te stellen.</span><span class="sxs-lookup"><span data-stu-id="fe577-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="fe577-196">Het model moet regelmatig worden getraind om nieuwe patronen te leren wanneer er nieuwe gegevens worden opgenomen.</span><span class="sxs-lookup"><span data-stu-id="fe577-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="fe577-197">Selecteer voor dit voorbeeld **Maandelijks**.</span><span class="sxs-lookup"><span data-stu-id="fe577-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="fe577-198">Selecteer nadat u alle details hebt nagekeken **Opslaan en uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="fe577-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="fe577-199">Taak 4 - Bekijk modelresultaten en uitleg</span><span class="sxs-lookup"><span data-stu-id="fe577-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="fe577-200">Laat het model de training en score van de gegevens voltooien.</span><span class="sxs-lookup"><span data-stu-id="fe577-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="fe577-201">U kunt nu de uitleg van het productaanbevelingsmodel bekijken.</span><span class="sxs-lookup"><span data-stu-id="fe577-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="fe577-202">Zie [Een voorspellingsstatus en resultaten beoordelen](predict-subscription-churn.md#review-a-prediction-status-and-results) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="fe577-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="fe577-203">Taak 5 - Maak een segment met veel gekochte producten</span><span class="sxs-lookup"><span data-stu-id="fe577-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="fe577-204">Door het productiemodel uit te voeren, wordt een nieuwe entiteit gemaakt die u kunt zien in **Gegevens** > **Entiteiten**.</span><span class="sxs-lookup"><span data-stu-id="fe577-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="fe577-205">U kunt een nieuw segment maken op basis van de entiteit die door het model is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="fe577-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="fe577-206">Ga naar **Segmenten**.</span><span class="sxs-lookup"><span data-stu-id="fe577-206">Go to **Segments**.</span></span> <span data-ttu-id="fe577-207">Selecteer **Nieuw** en kies **Maken van** > **Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="fe577-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Een segment maken met de modeluitvoer.](media/segment-intelligence.png)

1. <span data-ttu-id="fe577-209">Selecteer het eindpunt **OOBProductRecommendationModelPrediction** en definieer het segment:</span><span class="sxs-lookup"><span data-stu-id="fe577-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="fe577-210">Veld: ProductID</span><span class="sxs-lookup"><span data-stu-id="fe577-210">Field: ProductID</span></span>
   - <span data-ttu-id="fe577-211">Operator: waarde</span><span class="sxs-lookup"><span data-stu-id="fe577-211">Operator: Value</span></span>
   - <span data-ttu-id="fe577-212">Waarde: selecteer de drie beste product-id's</span><span class="sxs-lookup"><span data-stu-id="fe577-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Maak een segment van de modelresultaten.":::

<span data-ttu-id="fe577-214">U hebt nu een segment dat dynamisch wordt bijgewerkt en dat de klanten identificeert die meer bereid zijn de drie meest aanbevolen producten te kopen</span><span class="sxs-lookup"><span data-stu-id="fe577-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="fe577-215">Zie [Segmenten maken en beheren](segments.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="fe577-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]