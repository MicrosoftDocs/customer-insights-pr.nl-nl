---
title: Voorbeeldhandleiding abonnementsverloop voorspellen
description: Gebruik deze voorbeeldhandleiding om het standaard voorspellingsmodel voor abonnementsverloop uit te proberen.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: fa460fa5c79bc8a356ec5e90050ec85e05c55be8
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306297"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="65fb4-103">Voorbeeldhandleiding abonnementsverloop voorspellen (preview)</span><span class="sxs-lookup"><span data-stu-id="65fb4-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="65fb4-104">We laten u een compleet voorbeeld van abonnementsverloop-voorspelling zien aan de hand van de onderstaande voorbeeldgegevens.</span><span class="sxs-lookup"><span data-stu-id="65fb4-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="65fb4-105">Scenario</span><span class="sxs-lookup"><span data-stu-id="65fb4-105">Scenario</span></span>

<span data-ttu-id="65fb4-106">Contoso is een bedrijf dat koffie en koffiemachines van hoge kwaliteit produceert, die ze verkopen via hun Contoso Coffee-website.</span><span class="sxs-lookup"><span data-stu-id="65fb4-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="65fb4-107">Onlangs zijn ze begonnen met een abonnementsbedrijf voor hun klanten om regelmatig koffie te halen.</span><span class="sxs-lookup"><span data-stu-id="65fb4-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="65fb4-108">Hun doel is om te begrijpen welke geabonneerde klanten hun abonnement in de komende maanden kunnen opzeggen.</span><span class="sxs-lookup"><span data-stu-id="65fb4-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="65fb4-109">Weten welke van hun klanten **waarschijnlijk zal verlopen**, kan hen helpen zich marketinginspanningen te besparen door zich te concentreren op het behouden van hun klanten.</span><span class="sxs-lookup"><span data-stu-id="65fb4-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="65fb4-110">Vereisten</span><span class="sxs-lookup"><span data-stu-id="65fb4-110">Prerequisites</span></span>

- <span data-ttu-id="65fb4-111">Minimaal [inzendermachtigingen](permissions.md) in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="65fb4-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="65fb4-112">We raden u aan de volgende stappen te implementeren [in een nieuwe omgeving](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="65fb4-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="65fb4-113">Taak 1 - Gegevens opnemen</span><span class="sxs-lookup"><span data-stu-id="65fb4-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="65fb4-114">Lees vooral de artikelen [over gegevensopname](data-sources.md) en [gegevensbronnen importeren met Power Query-connectors](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="65fb4-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="65fb4-115">Bij de volgende informatie wordt ervan uitgegaan dat u bekend bent met opnemen van gegevens in het algemeen.</span><span class="sxs-lookup"><span data-stu-id="65fb4-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="65fb4-116">Klantgegevens opnemen van het e-commerceplatform</span><span class="sxs-lookup"><span data-stu-id="65fb4-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="65fb4-117">Maak een gegevensbron met de naam **eCommerce**, kies de importoptie en selecteer de connector **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="65fb4-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="65fb4-118">Voer de URL in voor eCommerce-contacten in https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="65fb4-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="65fb4-119">Selecteer tijdens het bewerken van de gegevens **Transformeren** en dan **De eerste rij als kopteksten gebruiken**.</span><span class="sxs-lookup"><span data-stu-id="65fb4-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="65fb4-120">Werk het gegevenstype voor de onderstaande kolommen bij:</span><span class="sxs-lookup"><span data-stu-id="65fb4-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="65fb4-121">**DateOfBirth**: datum</span><span class="sxs-lookup"><span data-stu-id="65fb4-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="65fb4-122">**CreatedOn**: datum/tijd/zone</span><span class="sxs-lookup"><span data-stu-id="65fb4-122">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformeer geboortedatum naar datum.":::

1. <span data-ttu-id="65fb4-124">Wijzig in het veld **Naam** in het rechterdeelvenster uw gegevensbron van **Query** in **eCommerceContacts**.</span><span class="sxs-lookup"><span data-stu-id="65fb4-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="65fb4-125">Sla de gegevensbron op.</span><span class="sxs-lookup"><span data-stu-id="65fb4-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="65fb4-126">Klantgegevens opnemen uit het loyaliteitsschema</span><span class="sxs-lookup"><span data-stu-id="65fb4-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="65fb4-127">Maak een gegevensbron met de naam **LoyaltyScheme**, kies de importoptie en selecteer de connector **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="65fb4-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="65fb4-128">Voer de URL in voor eCommerce-contacten in https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="65fb4-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="65fb4-129">Selecteer tijdens het bewerken van de gegevens **Transformeren** en dan **De eerste rij als kopteksten gebruiken**.</span><span class="sxs-lookup"><span data-stu-id="65fb4-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="65fb4-130">Werk het gegevenstype voor de onderstaande kolommen bij:</span><span class="sxs-lookup"><span data-stu-id="65fb4-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="65fb4-131">**DateOfBirth**: datum</span><span class="sxs-lookup"><span data-stu-id="65fb4-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="65fb4-132">**RewardsPoints**: geheel getal</span><span class="sxs-lookup"><span data-stu-id="65fb4-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="65fb4-133">**CreatedOn**: datum/tijd</span><span class="sxs-lookup"><span data-stu-id="65fb4-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="65fb4-134">Wijzig in het veld **Naam** in het rechterdeelvenster uw gegevensbron van **Query** in **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="65fb4-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="65fb4-135">Sla de gegevensbron op.</span><span class="sxs-lookup"><span data-stu-id="65fb4-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="65fb4-136">Abonnementsgegevens opnemen</span><span class="sxs-lookup"><span data-stu-id="65fb4-136">Ingest subscription information</span></span>

1. <span data-ttu-id="65fb4-137">Maak een gegevensbron met de naam **Abonnementsgeschiedenis**, kies de importoptie en selecteer de connector **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="65fb4-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="65fb4-138">Voer de URL in voor eCommerce-contacten in https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="65fb4-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="65fb4-139">Selecteer tijdens het bewerken van de gegevens **Transformeren** en dan **De eerste rij als kopteksten gebruiken**.</span><span class="sxs-lookup"><span data-stu-id="65fb4-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="65fb4-140">Werk het gegevenstype voor de onderstaande kolommen bij:</span><span class="sxs-lookup"><span data-stu-id="65fb4-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="65fb4-141">**SubscriptioID**: geheel getal</span><span class="sxs-lookup"><span data-stu-id="65fb4-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="65fb4-142">**SubscriptionAmount**: valuta</span><span class="sxs-lookup"><span data-stu-id="65fb4-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="65fb4-143">**SubscriptionEndDate**: datum/tijd</span><span class="sxs-lookup"><span data-stu-id="65fb4-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="65fb4-144">**SubscriptionStartDate**: datum/tijd</span><span class="sxs-lookup"><span data-stu-id="65fb4-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="65fb4-145">**TransactionDate**: datum/tijd</span><span class="sxs-lookup"><span data-stu-id="65fb4-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="65fb4-146">**IsRecurring**: waar/onwaar</span><span class="sxs-lookup"><span data-stu-id="65fb4-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="65fb4-147">**Is_auto_renew**: waar/onwaar</span><span class="sxs-lookup"><span data-stu-id="65fb4-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="65fb4-148">**RecurringFrequencyInMonths**: geheel getal</span><span class="sxs-lookup"><span data-stu-id="65fb4-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="65fb4-149">Wijzig in het veld **Naam** in het rechterdeelvenster uw gegevensbron van **Query** in **SubscriptionHistory**.</span><span class="sxs-lookup"><span data-stu-id="65fb4-149">In the **Name** field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="65fb4-150">Sla de gegevensbron op.</span><span class="sxs-lookup"><span data-stu-id="65fb4-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="65fb4-151">Klantgegevens van website-reviews opnemen</span><span class="sxs-lookup"><span data-stu-id="65fb4-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="65fb4-152">Maak een gegevensbron met de naam **Website**, kies de importoptie en selecteer de connector **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="65fb4-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="65fb4-153">Voer de URL in voor eCommerce-contacten in https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="65fb4-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="65fb4-154">Selecteer tijdens het bewerken van de gegevens **Transformeren** en dan **De eerste rij als kopteksten gebruiken**.</span><span class="sxs-lookup"><span data-stu-id="65fb4-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="65fb4-155">Werk het gegevenstype voor de onderstaande kolommen bij:</span><span class="sxs-lookup"><span data-stu-id="65fb4-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="65fb4-156">**ReviewRating**: geheel getal</span><span class="sxs-lookup"><span data-stu-id="65fb4-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="65fb4-157">**ReviewDate**: datum</span><span class="sxs-lookup"><span data-stu-id="65fb4-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="65fb4-158">Wijzig in het veld 'Naam' in het rechterdeelvenster uw gegevensbron van **Query** in **Webreviews**.</span><span class="sxs-lookup"><span data-stu-id="65fb4-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="65fb4-159">Taak 2 - Gegevensharmonisatie</span><span class="sxs-lookup"><span data-stu-id="65fb4-159">Task 2 - Data unification</span></span>

<span data-ttu-id="65fb4-160">Na het opnemen van de gegevens beginnen we nu met het proces **Toewijzen, Matchen, Samenvoegen** om een geharmoniseerd klantprofiel te maken.</span><span class="sxs-lookup"><span data-stu-id="65fb4-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="65fb4-161">Zie [Gegevensharmonisatie](data-unification.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="65fb4-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="65fb4-162">Toewijzen</span><span class="sxs-lookup"><span data-stu-id="65fb4-162">Map</span></span>

1. <span data-ttu-id="65fb4-163">Na het opnemen van de gegevens, wijst u contacten uit eCommerce en Loyaliteitsgegevens toe aan veelgebruikte gegevenstypen.</span><span class="sxs-lookup"><span data-stu-id="65fb4-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="65fb4-164">Ga naar **Gegevens** > **Unify** > **Toewijzen**.</span><span class="sxs-lookup"><span data-stu-id="65fb4-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="65fb4-165">Selecteer de entiteiten die het klantprofiel vertegenwoordigen: **eCommerceContacts** en **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="65fb4-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="harmoniseer eCommerce- en loyaliteitsgegevensbronnen.":::

1. <span data-ttu-id="65fb4-167">Selecteer **ContactId** als de primaire sleutel voor **eCommerceContacts** en **LoyaltyID** als de primaire sleutel voor **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="65fb4-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Harmoniseer LoyaltyId als primaire sleutel.":::

### <a name="match"></a><span data-ttu-id="65fb4-169">Bij elkaar zoeken</span><span class="sxs-lookup"><span data-stu-id="65fb4-169">Match</span></span>

1. <span data-ttu-id="65fb4-170">Ga naar het tabblad **Matchen** en selecteer **Volgorde instellen**.</span><span class="sxs-lookup"><span data-stu-id="65fb4-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="65fb4-171">Kies in de vervolgkeuzelijst **Primair** de optie **eCommerceContacts : eCommerce** als primaire bron en neem alle records op.</span><span class="sxs-lookup"><span data-stu-id="65fb4-171">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="65fb4-172">Kies in de vervolgkeuzelijst **Entiteit 2** de optie **loyCustomers: LoyaltyScheme** en neem alle records op.</span><span class="sxs-lookup"><span data-stu-id="65fb4-172">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Harmoniseer match eCommerce en Loyaliteit":::

1. <span data-ttu-id="65fb4-174">Selecteer **Een nieuwe regel maken**</span><span class="sxs-lookup"><span data-stu-id="65fb4-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="65fb4-175">Voeg uw eerste voorwaarde toe met FullName.</span><span class="sxs-lookup"><span data-stu-id="65fb4-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="65fb4-176">Selecteer voor eCommerceContacts de optie **FullName** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="65fb4-176">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="65fb4-177">Selecteer voor loyCustomers de optie **FullName** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="65fb4-177">For loyCustomers select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="65fb4-178">Selecteer de vervolgkeuzelijst **Normaliseren** en kies **Type (telefoon, naam, adres, ...)**.</span><span class="sxs-lookup"><span data-stu-id="65fb4-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="65fb4-179">Stel **Precisieniveau**: **Basic** en **Waarde**: **Hoog** in.</span><span class="sxs-lookup"><span data-stu-id="65fb4-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="65fb4-180">Voer de naam **FullName, Email** in voor de nieuwe regel.</span><span class="sxs-lookup"><span data-stu-id="65fb4-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="65fb4-181">Voeg een tweede voorwaarde voor het e-mailadres toe door **Voorwaarde toevoegen** te selecteren</span><span class="sxs-lookup"><span data-stu-id="65fb4-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="65fb4-182">Kies voor entiteit eCommerceContacts de optie **E-mail** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="65fb4-182">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   * <span data-ttu-id="65fb4-183">Kies voor entiteit loyCustomers de optie **E-mail** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="65fb4-183">For entity loyCustomers, choose **EMail** in the dropdown.</span></span> 
   * <span data-ttu-id="65fb4-184">Laat Normaliseren leeg.</span><span class="sxs-lookup"><span data-stu-id="65fb4-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="65fb4-185">Stel **Precisieniveau**: **Basic** en **Waarde**: **Hoog** in.</span><span class="sxs-lookup"><span data-stu-id="65fb4-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Harmoniseer de matchregel voor naam en e-mailadres.":::

7. <span data-ttu-id="65fb4-187">Selecteer **Opslaan** en **Uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="65fb4-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="65fb4-188">Samenvoeging</span><span class="sxs-lookup"><span data-stu-id="65fb4-188">Merge</span></span>

1. <span data-ttu-id="65fb4-189">Ga naar het tabblad **Samenvoegen**.</span><span class="sxs-lookup"><span data-stu-id="65fb4-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="65fb4-190">Bij **ContactId** voor de entiteit **loyCustomers** wijzigt u de weergavenaam in **ContactIdLOYALTY** om deze te onderscheiden van de andere opgenomen id's.</span><span class="sxs-lookup"><span data-stu-id="65fb4-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="hernoem contactid van loyaliteits-id.":::

1. <span data-ttu-id="65fb4-192">Selecteer **Opslaan** en **Uitvoeren** om het samenvoegingsproces te starten.</span><span class="sxs-lookup"><span data-stu-id="65fb4-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="65fb4-193">Taak 3 - Configureer de voorspelling van het abonnementsverloop</span><span class="sxs-lookup"><span data-stu-id="65fb4-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="65fb4-194">Met de geharmoniseerde klantprofielen op hun plaats, kunnen we nu het abonnementsverloop voorspellen.</span><span class="sxs-lookup"><span data-stu-id="65fb4-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="65fb4-195">Zie het artikel [Abonnementsverloop voorspellen (preview)](predict-subscription-churn.md) voor gedetailleerde stappen.</span><span class="sxs-lookup"><span data-stu-id="65fb4-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="65fb4-196">Ga naar **Intelligence** > **Ontdekken** en selecteer het **Klantverloopmodel**.</span><span class="sxs-lookup"><span data-stu-id="65fb4-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="65fb4-197">Selecteer de optie **Abonnement** en selecteer **Aan de slag**.</span><span class="sxs-lookup"><span data-stu-id="65fb4-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="65fb4-198">Geef het model de naam **OOB voorspelling abonnementsverloop** en de uitvoerentiteit **OOBSubscriptionChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="65fb4-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="65fb4-199">Definieer twee voorwaarden voor het verloopmodel:</span><span class="sxs-lookup"><span data-stu-id="65fb4-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="65fb4-200">**Dagen sinds het einde van het abonnement**: **minstens 60** dagen.</span><span class="sxs-lookup"><span data-stu-id="65fb4-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="65fb4-201">Als een klant zijn abonnement in deze periode niet verlengt nadat het abonnement is afgelopen, wordt de klant beschouwd als verlopen.</span><span class="sxs-lookup"><span data-stu-id="65fb4-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="65fb4-202">**Definitie van verloop**: **minstens 93** dagen.</span><span class="sxs-lookup"><span data-stu-id="65fb4-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="65fb4-203">De duur waarin volgens de voorspelling van het model klanten kunnen verlopen.</span><span class="sxs-lookup"><span data-stu-id="65fb4-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="65fb4-204">Hoe verder u in de toekomst kijkt, hoe minder nauwkeurig de resultaten zijn.</span><span class="sxs-lookup"><span data-stu-id="65fb4-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Selecteer de modelhendels Voorspellingsvenster en Definitie van verloop.":::

1. <span data-ttu-id="65fb4-206">Selecteer **Vereiste gegevens toevoegen** en selecteer **Gegevens toevoegen** voor abonnementsgeschiedenis.</span><span class="sxs-lookup"><span data-stu-id="65fb4-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="65fb4-207">Voeg de entiteit **Subscription : SubscriptionHistory** toe en wijs de velden van eCommerce toe aan de overeenkomstige velden die vereist zijn voor het model.</span><span class="sxs-lookup"><span data-stu-id="65fb4-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="65fb4-208">Voeg de entiteit **Subscription : SubscriptionHistory** samen met **eCommerceContacts : eCommerce** en geef de relatie de naam **eCommerceSubscription**.</span><span class="sxs-lookup"><span data-stu-id="65fb4-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Voeg eCommerce-entiteiten samen.":::

1. <span data-ttu-id="65fb4-210">Voeg onder Klantactiviteiten de entiteitg **webReviews: Website** toe en wijs de velden van webReviews toe aan de overeenkomstige velden die vereist zijn voor het model.</span><span class="sxs-lookup"><span data-stu-id="65fb4-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="65fb4-211">Primaire sleutel: ReviewId</span><span class="sxs-lookup"><span data-stu-id="65fb4-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="65fb4-212">Tijdstempel: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="65fb4-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="65fb4-213">Gebeurtenis: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="65fb4-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="65fb4-214">Configureer een activiteit voor website-reviews.</span><span class="sxs-lookup"><span data-stu-id="65fb4-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="65fb4-215">Selecteer de activiteit **Review** en voeg de entiteit **webReviews: Website** samen met **eCommerceContacts: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="65fb4-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="65fb4-216">Selecteer **Volgende** om de modelplanning in te stellen.</span><span class="sxs-lookup"><span data-stu-id="65fb4-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="65fb4-217">Het model moet regelmatig worden getraind om nieuwe patronen te leren wanneer er nieuwe gegevens worden opgenomen.</span><span class="sxs-lookup"><span data-stu-id="65fb4-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="65fb4-218">Selecteer voor dit voorbeeld **Maandelijks**.</span><span class="sxs-lookup"><span data-stu-id="65fb4-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="65fb4-219">Selecteer nadat u alle details hebt nagekeken **Opslaan en uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="65fb4-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="65fb4-220">Taak 4 - Bekijk modelresultaten en uitleg</span><span class="sxs-lookup"><span data-stu-id="65fb4-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="65fb4-221">Laat het model de training en score van de gegevens voltooien.</span><span class="sxs-lookup"><span data-stu-id="65fb4-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="65fb4-222">U kunt nu de uitleg van het abonnementverloopmodel bekijken.</span><span class="sxs-lookup"><span data-stu-id="65fb4-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="65fb4-223">Zie [Een voorspellingsstatus en resultaten beoordelen](predict-subscription-churn.md#review-a-prediction-status-and-results) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="65fb4-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="65fb4-224">Taak 5 - Maak een segment van klanten met een hoog verlooprisico</span><span class="sxs-lookup"><span data-stu-id="65fb4-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="65fb4-225">Door het productiemodel uit te voeren, wordt een nieuwe entiteit gemaakt die u kunt zien in **Gegevens** > **Entiteiten**.</span><span class="sxs-lookup"><span data-stu-id="65fb4-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="65fb4-226">U kunt een nieuw segment maken op basis van de entiteit die door het model is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="65fb4-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="65fb4-227">Ga naar **Segmenten**.</span><span class="sxs-lookup"><span data-stu-id="65fb4-227">Go to **Segments**.</span></span> <span data-ttu-id="65fb4-228">Selecteer **Nieuw** en kies **Maken van** > **Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="65fb4-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Een segment maken met de modeluitvoer.":::

1. <span data-ttu-id="65fb4-230">Selecteer het eindpunt **OOBSubscriptionChurnPrediction** en definieer het segment:</span><span class="sxs-lookup"><span data-stu-id="65fb4-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="65fb4-231">Veld: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="65fb4-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="65fb4-232">Operator: groter dan</span><span class="sxs-lookup"><span data-stu-id="65fb4-232">Operator: greater than</span></span>
   - <span data-ttu-id="65fb4-233">Waarde: 0,6</span><span class="sxs-lookup"><span data-stu-id="65fb4-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Stel een segment abonnementverloop in.":::

<span data-ttu-id="65fb4-235">U hebt nu een segment dat dynamisch wordt bijgewerkt en dat klanten met een hoog verlooprisico identificeert voor dit abonnementsbedrijf.</span><span class="sxs-lookup"><span data-stu-id="65fb4-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="65fb4-236">Zie [Segmenten maken en beheren](segments.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="65fb4-236">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]