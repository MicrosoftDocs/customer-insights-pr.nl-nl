---
title: Voorbeeldhandleiding transactieverloop voorspellen
description: Gebruik deze voorbeeldhandleiding om het standaard voorspellingsmodel voor transactieverloop uit te proberen.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 49dad45c951f3c00d77ddd99faec48bfccada8b0
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306114"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="72948-103">Voorbeeldhandleiding transactieverloop voorspellen (preview)</span><span class="sxs-lookup"><span data-stu-id="72948-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="72948-104">We laten u een compleet voorbeeld van transactieverloop-voorspelling in Customer Insights zien aan de hand van de onderstaande voorbeeldgegevens.</span><span class="sxs-lookup"><span data-stu-id="72948-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="72948-105">Alle gegevens die in deze handleiding worden gebruikt, zijn geen echte klantgegevens en maken deel uit van de Contoso-gegevensset die te vinden is in de omgeving *Demo* binnen uw Customer Insights-abonnement.</span><span class="sxs-lookup"><span data-stu-id="72948-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="72948-106">Scenario</span><span class="sxs-lookup"><span data-stu-id="72948-106">Scenario</span></span>

<span data-ttu-id="72948-107">Contoso is een bedrijf dat koffie en koffiemachines van hoge kwaliteit produceert, die ze verkopen via hun Contoso Coffee-website.</span><span class="sxs-lookup"><span data-stu-id="72948-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="72948-108">Hun doel is te weten te komen welke klanten die hun producten normaal gesproken regelmatig kopen, in de komende 60 dagen geen actieve klant meer zijn.</span><span class="sxs-lookup"><span data-stu-id="72948-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="72948-109">Weten welke van hun klanten **waarschijnlijk zal verlopen**, kan hen helpen zich marketinginspanningen te besparen door zich te concentreren op het behouden van hun klanten.</span><span class="sxs-lookup"><span data-stu-id="72948-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="72948-110">Vereisten</span><span class="sxs-lookup"><span data-stu-id="72948-110">Prerequisites</span></span>

- <span data-ttu-id="72948-111">Minimaal [inzendermachtigingen](permissions.md) in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="72948-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="72948-112">We raden u aan de volgende stappen te implementeren [in een nieuwe omgeving](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="72948-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="72948-113">Taak 1 - Gegevens opnemen</span><span class="sxs-lookup"><span data-stu-id="72948-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="72948-114">Lees vooral de artikelen [over gegevensopname](data-sources.md) en [gegevensbronnen importeren met Power Query-connectors](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="72948-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="72948-115">Bij de volgende informatie wordt ervan uitgegaan dat u bekend bent met opnemen van gegevens in het algemeen.</span><span class="sxs-lookup"><span data-stu-id="72948-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="72948-116">Klantgegevens opnemen van het e-commerceplatform</span><span class="sxs-lookup"><span data-stu-id="72948-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="72948-117">Maak een gegevensbron met de naam **eCommerce**, kies de importoptie en selecteer de connector **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="72948-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="72948-118">Voer de URL in voor eCommerce-contacten in https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="72948-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="72948-119">Selecteer tijdens het bewerken van de gegevens **Transformeren** en dan **De eerste rij als kopteksten gebruiken**.</span><span class="sxs-lookup"><span data-stu-id="72948-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="72948-120">Werk het gegevenstype voor de onderstaande kolommen bij:</span><span class="sxs-lookup"><span data-stu-id="72948-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="72948-121">**DateOfBirth**: datum</span><span class="sxs-lookup"><span data-stu-id="72948-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="72948-122">**CreatedOn**: datum/tijd/zone</span><span class="sxs-lookup"><span data-stu-id="72948-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="72948-123">![DoB transformeren naar datum](media/ecommerce-dob-date.PNG "geboortedatum naar datum transformeren")</span><span class="sxs-lookup"><span data-stu-id="72948-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="72948-124">Wijzig in het veld **Naam** in het rechterdeelvenster uw gegevensbron van **Query** in **eCommerceContacts**.</span><span class="sxs-lookup"><span data-stu-id="72948-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="72948-125">Sla de gegevensbron op.</span><span class="sxs-lookup"><span data-stu-id="72948-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="72948-126">Online aankoopgegevens opnemen</span><span class="sxs-lookup"><span data-stu-id="72948-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="72948-127">Voeg nog een gegevensset toe aan dezelfde **eCommerce**-gegevensbron.</span><span class="sxs-lookup"><span data-stu-id="72948-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="72948-128">Kies opnieuw de connector **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="72948-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="72948-129">Voer de URL in voor de gegevens voor **Online aankopen** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="72948-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="72948-130">Selecteer tijdens het bewerken van de gegevens **Transformeren** en dan **De eerste rij als kopteksten gebruiken**.</span><span class="sxs-lookup"><span data-stu-id="72948-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="72948-131">Werk het gegevenstype voor de onderstaande kolommen bij:</span><span class="sxs-lookup"><span data-stu-id="72948-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="72948-132">**PurchasedOn**: datum/tijd</span><span class="sxs-lookup"><span data-stu-id="72948-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="72948-133">**TotalPrice**: valuta</span><span class="sxs-lookup"><span data-stu-id="72948-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="72948-134">Wijzig in het veld **Naam** in het rechterdeelvenster uw gegevensbron van **Query** in **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="72948-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="72948-135">Sla de gegevensbron op.</span><span class="sxs-lookup"><span data-stu-id="72948-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="72948-136">Klantgegevens opnemen uit het loyaliteitsschema</span><span class="sxs-lookup"><span data-stu-id="72948-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="72948-137">Maak een gegevensbron met de naam **LoyaltyScheme**, kies de importoptie en selecteer de connector **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="72948-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="72948-138">Voer de URL in voor eCommerce-contacten in https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="72948-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="72948-139">Selecteer tijdens het bewerken van de gegevens **Transformeren** en dan **De eerste rij als kopteksten gebruiken**.</span><span class="sxs-lookup"><span data-stu-id="72948-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="72948-140">Werk het gegevenstype voor de onderstaande kolommen bij:</span><span class="sxs-lookup"><span data-stu-id="72948-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="72948-141">**DateOfBirth**: datum</span><span class="sxs-lookup"><span data-stu-id="72948-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="72948-142">**RewardsPoints**: geheel getal</span><span class="sxs-lookup"><span data-stu-id="72948-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="72948-143">**CreatedOn**: datum/tijd</span><span class="sxs-lookup"><span data-stu-id="72948-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="72948-144">Wijzig in het veld **Naam** in het rechterdeelvenster uw gegevensbron van **Query** in **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="72948-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="72948-145">Sla de gegevensbron op.</span><span class="sxs-lookup"><span data-stu-id="72948-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="72948-146">Taak 2 - Gegevensharmonisatie</span><span class="sxs-lookup"><span data-stu-id="72948-146">Task 2 - Data unification</span></span>

<span data-ttu-id="72948-147">Na het opnemen van de gegevens beginnen we nu met het proces **Toewijzen, Matchen, Samenvoegen** om een geharmoniseerd klantprofiel te maken.</span><span class="sxs-lookup"><span data-stu-id="72948-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="72948-148">Zie [Gegevensharmonisatie](data-unification.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="72948-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="72948-149">Toewijzen</span><span class="sxs-lookup"><span data-stu-id="72948-149">Map</span></span>

1. <span data-ttu-id="72948-150">Na het opnemen van de gegevens, wijst u contacten uit eCommerce en Loyaliteitsgegevens toe aan veelgebruikte gegevenstypen.</span><span class="sxs-lookup"><span data-stu-id="72948-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="72948-151">Ga naar **Gegevens** > **Unify** > **Toewijzen**.</span><span class="sxs-lookup"><span data-stu-id="72948-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="72948-152">Selecteer de entiteiten die het klantprofiel vertegenwoordigen: **eCommerceContacts** en **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="72948-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="harmoniseer eCommerce- en loyaliteitsgegevensbronnen.":::

1. <span data-ttu-id="72948-154">Selecteer **ContactId** als de primaire sleutel voor **eCommerceContacts** en **LoyaltyID** als de primaire sleutel voor **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="72948-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Harmoniseer LoyaltyId als primaire sleutel.":::

### <a name="match"></a><span data-ttu-id="72948-156">Bij elkaar zoeken</span><span class="sxs-lookup"><span data-stu-id="72948-156">Match</span></span>

1. <span data-ttu-id="72948-157">Ga naar het tabblad **Matchen** en selecteer **Volgorde instellen**.</span><span class="sxs-lookup"><span data-stu-id="72948-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="72948-158">Kies in de vervolgkeuzelijst **Primair** de optie **eCommerceContacts : eCommerce** als primaire bron en neem alle records op.</span><span class="sxs-lookup"><span data-stu-id="72948-158">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="72948-159">Kies in de vervolgkeuzelijst **Entiteit 2** de optie **loyCustomers: LoyaltyScheme** en neem alle records op.</span><span class="sxs-lookup"><span data-stu-id="72948-159">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Harmoniseer match eCommerce en Loyaliteit":::

1. <span data-ttu-id="72948-161">Selecteer **Een nieuwe regel maken**</span><span class="sxs-lookup"><span data-stu-id="72948-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="72948-162">Voeg uw eerste voorwaarde toe met FullName.</span><span class="sxs-lookup"><span data-stu-id="72948-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="72948-163">Selecteer voor eCommerceContacts de optie **FullName** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="72948-163">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="72948-164">Selecteer voor loyCustomers de optie **FullName** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="72948-164">For loyCustomers select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="72948-165">Selecteer de vervolgkeuzelijst **Normaliseren** en kies **Type (telefoon, naam, adres, ...)**.</span><span class="sxs-lookup"><span data-stu-id="72948-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="72948-166">Stel **Precisieniveau**: **Basic** en **Waarde**: **Hoog** in.</span><span class="sxs-lookup"><span data-stu-id="72948-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="72948-167">Voer de naam **FullName, Email** in voor de nieuwe regel.</span><span class="sxs-lookup"><span data-stu-id="72948-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="72948-168">Voeg een tweede voorwaarde voor het e-mailadres toe door **Voorwaarde toevoegen** te selecteren</span><span class="sxs-lookup"><span data-stu-id="72948-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="72948-169">Kies voor entiteit eCommerceContacts de optie **E-mail** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="72948-169">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   * <span data-ttu-id="72948-170">Kies voor entiteit loyCustomers de optie **E-mail** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="72948-170">For entity loyCustomers, choose **EMail** in the dropdown.</span></span> 
   * <span data-ttu-id="72948-171">Laat Normaliseren leeg.</span><span class="sxs-lookup"><span data-stu-id="72948-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="72948-172">Stel **Precisieniveau**: **Basic** en **Waarde**: **Hoog** in.</span><span class="sxs-lookup"><span data-stu-id="72948-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Harmoniseer de matchregel voor naam en e-mailadres.":::

7. <span data-ttu-id="72948-174">Selecteer **Opslaan** en **Uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="72948-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="72948-175">Samenvoeging</span><span class="sxs-lookup"><span data-stu-id="72948-175">Merge</span></span>

1. <span data-ttu-id="72948-176">Ga naar het tabblad **Samenvoegen**.</span><span class="sxs-lookup"><span data-stu-id="72948-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="72948-177">Bij **ContactId** voor de entiteit **loyCustomers** wijzigt u de weergavenaam in **ContactIdLOYALTY** om deze te onderscheiden van de andere opgenomen id's.</span><span class="sxs-lookup"><span data-stu-id="72948-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="hernoem contactid van loyaliteits-id.":::

1. <span data-ttu-id="72948-179">Selecteer **Opslaan** en **Uitvoeren** om het samenvoegingsproces te starten.</span><span class="sxs-lookup"><span data-stu-id="72948-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="72948-180">Taak 3 - Configureer de voorspelling van het transactieverloop</span><span class="sxs-lookup"><span data-stu-id="72948-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="72948-181">Met de geharmoniseerde klantprofielen op hun plaats, kunnen we nu het abonnementsverloop voorspellen.</span><span class="sxs-lookup"><span data-stu-id="72948-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="72948-182">Zie het artikel [Abonnementsverloop voorspellen (preview)](predict-subscription-churn.md) voor gedetailleerde stappen.</span><span class="sxs-lookup"><span data-stu-id="72948-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="72948-183">Ga naar **Intelligence** > **Ontdekken** en selecteer het **Klantverloopmodel**.</span><span class="sxs-lookup"><span data-stu-id="72948-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="72948-184">Selecteer de optie **Transactie** en selecteer **Aan de slag**.</span><span class="sxs-lookup"><span data-stu-id="72948-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="72948-185">Geef het model de naam **OOB voorspelling eCommerce transactieverloop** en de uitvoerentiteit **OOBeCommerceChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="72948-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="72948-186">Definieer twee voorwaarden voor het verloopmodel:</span><span class="sxs-lookup"><span data-stu-id="72948-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="72948-187">**Voorspellingsvenster**: **minstens 60** dagen.</span><span class="sxs-lookup"><span data-stu-id="72948-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="72948-188">Deze instelling bepaalt hoe ver in de toekomst we het klantverloop willen voorspellen.</span><span class="sxs-lookup"><span data-stu-id="72948-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="72948-189">**Definitie van verloop**: **minstens 60** dagen.</span><span class="sxs-lookup"><span data-stu-id="72948-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="72948-190">De duur zonder aankoop waarna een klant als verlopen wordt beschouwd.</span><span class="sxs-lookup"><span data-stu-id="72948-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="Selecteer de modelhendels Voorspellingsvenster en Definitie van verloop.":::

1. <span data-ttu-id="72948-192">Selecteer **Aankoopgeschiedenis (vereist)** en selecteer **Gegevens toevoegen** voor aankoopgeschiedenis.</span><span class="sxs-lookup"><span data-stu-id="72948-192">Select **Purchase History (required)** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="72948-193">Voeg de entiteit **eCommercePurchases : eCommerce** toe en wijs de velden van eCommerce toe aan de overeenkomstige velden die vereist zijn voor het model.</span><span class="sxs-lookup"><span data-stu-id="72948-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="72948-194">Voeg de entiteit **eCommercePurchases : eCommerce** samen met **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="72948-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Voeg eCommerce-entiteiten samen.":::

1. <span data-ttu-id="72948-196">Selecteer **Volgende** om de modelplanning in te stellen.</span><span class="sxs-lookup"><span data-stu-id="72948-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="72948-197">Het model moet regelmatig worden getraind om nieuwe patronen te leren wanneer er nieuwe gegevens worden opgenomen.</span><span class="sxs-lookup"><span data-stu-id="72948-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="72948-198">Selecteer voor dit voorbeeld **Maandelijks**.</span><span class="sxs-lookup"><span data-stu-id="72948-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="72948-199">Selecteer nadat u alle details hebt nagekeken **Opslaan en uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="72948-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="72948-200">Taak 4 - Bekijk modelresultaten en uitleg</span><span class="sxs-lookup"><span data-stu-id="72948-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="72948-201">Laat het model de training en score van de gegevens voltooien.</span><span class="sxs-lookup"><span data-stu-id="72948-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="72948-202">U kunt nu de uitleg van het abonnementverloopmodel bekijken.</span><span class="sxs-lookup"><span data-stu-id="72948-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="72948-203">Zie [Een voorspellingsstatus en resultaten beoordelen](predict-subscription-churn.md#review-a-prediction-status-and-results) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="72948-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="72948-204">Taak 5 - Maak een segment van klanten met een hoog verlooprisico</span><span class="sxs-lookup"><span data-stu-id="72948-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="72948-205">Door het productiemodel uit te voeren, wordt een nieuwe entiteit gemaakt die u kunt zien in **Gegevens** > **Entiteiten**.</span><span class="sxs-lookup"><span data-stu-id="72948-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="72948-206">U kunt een nieuw segment maken op basis van de entiteit die door het model is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="72948-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="72948-207">Ga naar **Segmenten**.</span><span class="sxs-lookup"><span data-stu-id="72948-207">Go to **Segments**.</span></span> <span data-ttu-id="72948-208">Selecteer **Nieuw** en kies **Maken van** > **Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="72948-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Een segment maken met de modeluitvoer.":::

1. <span data-ttu-id="72948-210">Selecteer het eindpunt **OOBSubscriptionChurnPrediction** en definieer het segment:</span><span class="sxs-lookup"><span data-stu-id="72948-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="72948-211">Veld: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="72948-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="72948-212">Operator: groter dan</span><span class="sxs-lookup"><span data-stu-id="72948-212">Operator: greater than</span></span>
   - <span data-ttu-id="72948-213">Waarde: 0,6</span><span class="sxs-lookup"><span data-stu-id="72948-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Stel een segment abonnementverloop in.":::

<span data-ttu-id="72948-215">U hebt nu een segment dat dynamisch wordt bijgewerkt en dat klanten met een hoog verlooprisico identificeert voor dit abonnementsbedrijf.</span><span class="sxs-lookup"><span data-stu-id="72948-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="72948-216">Zie [Segmenten maken en beheren](segments.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="72948-216">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]