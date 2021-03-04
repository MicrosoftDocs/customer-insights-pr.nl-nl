---
title: Productaanbevelingen voorspellen
description: Voorspel de producten die een klant waarschijnlijk zal kopen of gebruiken.
ms.date: 02/15/2021
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a2eb2b4697e51a0abb933b654a9b0b150dfa6a3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270483"
---
# <a name="product-recommendation-prediction-preview"></a><span data-ttu-id="c9b1c-103">Productaanbevelingen voorspellen (preview)</span><span class="sxs-lookup"><span data-stu-id="c9b1c-103">Product recommendation prediction (preview)</span></span>

<span data-ttu-id="c9b1c-104">Het productaanbevelingsmodel maakt sets met voorspellende productaanbevelingen.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-104">The product recommendation model creates sets of predictive product recommendations.</span></span> <span data-ttu-id="c9b1c-105">Aanbevelingen zijn gebaseerd op eerder aankoopgedrag en klanten met vergelijkbare aankooppatronen.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-105">Recommendations are based on previous purchase behavior and customers with similar purchase patterns.</span></span> <span data-ttu-id="c9b1c-106">U kunt voorspellingen voor nieuwe productaanbevelingen maken op de pagina **Informatie** > **Voorspellingen**.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-106">You can create new product recommendation predictions on the **Intelligence** > **Predictions** page.</span></span> <span data-ttu-id="c9b1c-107">Selecteer **Mijn voorspellingen** om andere voorspellingen te bekijken die u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-107">Select **My predictions** to see other predictions that you've created.</span></span>

<span data-ttu-id="c9b1c-108">Productaanbevelingen kunnen onderhevig zijn aan lokale wet- en regelgeving en aan de verwachtingen van de klant, waarmee het model niet specifiek rekening houdt.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-108">Product recommendations may be subject to local laws and regulations as well as customer expectations, which the model is not built to specifically take into account.</span></span>  <span data-ttu-id="c9b1c-109">Als gebruiker van deze voorspellende mogelijkheid **moet u de aanbevelingen bekijken voordat u ze aan uw klanten verstrekt** om ervoor te zorgen dat u voldoet aan alle toepasselijke wet- of regelgeving, evenals aan de verwachtingen van de klant voor wat u mogelijk aanbeveelt.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-109">As a user of this predictive capability, **you must review the recommendations prior to delivering them to your customers** to ensure you are complying with any applicable laws or regulations, as well as customer expectations for what you may recommend.</span></span> 

<span data-ttu-id="c9b1c-110">Bovendien geeft de uitvoer van dit model aanbevelingen op basis van het product-id.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-110">Additionally, the output of this model will give you recommendations based on the product ID.</span></span> <span data-ttu-id="c9b1c-111">Uw leveringsmechanisme moet voorspelde product-id's nemen en deze toewijzen aan geschikte inhoud voor uw klanten om rekening te houden met lokalisatie, afbeeldingsinhoud en andere bedrijfsspecifieke inhoud of gedrag.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-111">Your delivery mechanism will need to take predicted product IDs and map them to appropriate content for your customers to account for localization, image content, and other business specific content or behavior.</span></span>

## <a name="sample-guide"></a><span data-ttu-id="c9b1c-112">Voorbeeldgids</span><span class="sxs-lookup"><span data-stu-id="c9b1c-112">Sample Guide</span></span>

<span data-ttu-id="c9b1c-113">Als je deze functie wilt proberen, maar geen gegevens hebt om aan de onderstaande vereisten te voldoen, kunt u [een voorbeeldimplementatie maken](sample-guide-predict-product-recommendation.md)​.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-113">If you're interested in trying this feature but don't have data to complete the requirements below, you can [create a sample implementation](sample-guide-predict-product-recommendation.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c9b1c-114">Vereisten</span><span class="sxs-lookup"><span data-stu-id="c9b1c-114">Prerequisites</span></span>

- <span data-ttu-id="c9b1c-115">Minimaal [inzendermachtigingen](permissions.md) in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-115">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="c9b1c-116">Zakelijke kennis om verschillende soorten producten voor uw bedrijf te begrijpen en te begrijpen hoe uw klanten ermee omgaan.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-116">Business knowledge to understand different types of products for your business and how your customers interact with them.</span></span> <span data-ttu-id="c9b1c-117">We ondersteunen het aanbevelen van producten die eerder door uw klanten zijn gekocht of aanbevelingen voor nieuwe producten.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-117">We support recommending products that have been previously purchased by your customers or recommendations for new products.</span></span>
- <span data-ttu-id="c9b1c-118">Gegevens over uw transacties, aankopen en hun geschiedenis:</span><span class="sxs-lookup"><span data-stu-id="c9b1c-118">Data about transactions, purchases, and their history:</span></span>
    - <span data-ttu-id="c9b1c-119">Transactie-id's om aankopen of transacties te onderscheiden.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-119">Transaction identifiers to distinguish purchases or transactions.</span></span>
    - <span data-ttu-id="c9b1c-120">Klant-id's om transacties toe te wijzen aan uw klanten.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-120">Customer identifiers to map transactions to your customers.</span></span>
    - <span data-ttu-id="c9b1c-121">Transactiegebeurtenisdatums die de datums specificeren waarop de transactie plaatsvond.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-121">Transaction event dates that specify dates the transaction occurred on.</span></span>
    - <span data-ttu-id="c9b1c-122">(Optioneel) Product-id-informatie voor de transactie.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-122">(Optional) Product ID information for the transaction.</span></span>
    - <span data-ttu-id="c9b1c-123">(Optioneel) Of een transactie een retour is of niet.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-123">(Optional) If a transaction is a return or not.</span></span>
    - <span data-ttu-id="c9b1c-124">Het semantische gegevensschema vereist de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="c9b1c-124">The semantic data schema requires the following information:</span></span>
        - <span data-ttu-id="c9b1c-125">**Transactie-id:** een unieke identificatie van een aankoop of transactie.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-125">**Transaction ID:** A unique identifier of a purchase or transaction.</span></span>
        - <span data-ttu-id="c9b1c-126">**Transactiedatum**: de datum van de aankoop of de transactie.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-126">**Transaction date:** The date the of the purchase or transaction.</span></span>
        - <span data-ttu-id="c9b1c-127">**Waarde van de transactie**: de numerieke waarde van de aankoop of de transactie.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-127">**Value of the transaction:** The numerical value of the purchase or transaction.</span></span>
        - <span data-ttu-id="c9b1c-128">**Unieke product-id**: de id van het gekochte product of de gekochte service als uw gegevens zich op regelitemniveau bevinden.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-128">**Unique product ID:** The ID of the product or service purchased if your data is at a line item level.</span></span>
        - <span data-ttu-id="c9b1c-129">(Optioneel) **Aankoop of retour**: een waar/onwaar-veld dat aangeeft of de transactie een retour was of niet.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-129">(Optional) **Purchase or return:** A true/false field that identifies if the transaction was a return or not.</span></span> <span data-ttu-id="c9b1c-130">Als de **Waarde van de transactie** negatief is, gebruiken we deze informatie ook om een retour af te leiden.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-130">If the **Value of the transaction** is negative, we will also use this information to infer a return.</span></span>


## <a name="create-a-product-recommendation-prediction"></a><span data-ttu-id="c9b1c-131">Een voorspelling voor een productaanbeveling maken</span><span class="sxs-lookup"><span data-stu-id="c9b1c-131">Create a product recommendation prediction</span></span>

1. <span data-ttu-id="c9b1c-132">Ga in Customer Insights naar **Informatie** > **Voorspellingen**.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-132">In Customer Insights, go to **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="c9b1c-133">Selecteer de tegel **Model voor productaanbevelingen (preview)** en selecteer **Dit model gebruiken**.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-133">Select the **Product recommendations model (preview)** tile and select **Use this model**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c9b1c-134">![Tegel Productaanbevelingsmodel met knop Dit model gebruiken](media/product-recommendation-usethismodel.PNG "Tegel Productaanbevelingsmodel met knop Dit model gebruiken")</span><span class="sxs-lookup"><span data-stu-id="c9b1c-134">![Product Recommendation model tile with Use this model button](media/product-recommendation-usethismodel.PNG "Product Recommendation model tile with Use this model button")</span></span>

1. <span data-ttu-id="c9b1c-135">Bekijk de informatie over de modelvereisten.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-135">Review the information about the model requirements.</span></span> <span data-ttu-id="c9b1c-136">Als u over de vereiste gegevens beschikt, selecteert u **Aan de slag**.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-136">If you have the required data, select **Get started**.</span></span>

### <a name="name-model"></a><span data-ttu-id="c9b1c-137">Model een naam geven</span><span class="sxs-lookup"><span data-stu-id="c9b1c-137">Name model</span></span>

1. <span data-ttu-id="c9b1c-138">Geef het model een naam om het van andere modellen te onderscheiden.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-138">Provide a name for the model to distinguish it from other models.</span></span>

1. <span data-ttu-id="c9b1c-139">Voer een naam in voor de uitvoerentiteit met alleen letters en cijfers, zonder spaties.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-139">Enter a name for the output entity using letters and numbers only, without any spaces.</span></span> <span data-ttu-id="c9b1c-140">Dat is de naam die de modelentiteit zal gebruiken.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-140">That's the name that the model entity will use.</span></span> <span data-ttu-id="c9b1c-141">Selecteer vervolgens **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-141">Then, select **Next**.</span></span>

### <a name="define-product-recommendation-configuration"></a><span data-ttu-id="c9b1c-142">Definieer de configuratie van productaanbevelingen</span><span class="sxs-lookup"><span data-stu-id="c9b1c-142">Define product recommendation configuration</span></span>

1. <span data-ttu-id="c9b1c-143">Stel het **Aantal producten** in dat u een klant wilt aanbevelen.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-143">Set the **Number of products** you want to recommend to a customer.</span></span> <span data-ttu-id="c9b1c-144">Deze waarde is afhankelijk van de manier waarop uw leveringsmethode de gegevens vult.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-144">This value depends on how your delivery method fills data.</span></span> <span data-ttu-id="c9b1c-145">Als u drie producten kunt aanbevelen, stelt u deze waarde dienovereenkomstig in.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-145">If you can recommend three products, set this value accordingly.</span></span>
   
   >[!TIP]
   > <span data-ttu-id="c9b1c-146">U kunt op elk gewenst moment **Opslaan en sluiten** selecteren om de voorspelling als concept op te slaan.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-146">You can select **Save and close** at any time to save the prediction as a draft.</span></span> <span data-ttu-id="c9b1c-147">U vindt de conceptvoorspelling op het tabblad **Mijn voorspellingen**.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-147">You'll find the draft prediction in the **My predictions** tab.</span></span>

1. <span data-ttu-id="c9b1c-148">U kunt kiezen voor de optie **Producten voorstellen die onlangs door klanten zijn aangeschaft**.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-148">Choose if you want to **Suggest products customers have recently purchased**.</span></span>

1. <span data-ttu-id="c9b1c-149">Als u ervoor hebt gekozen *geen* aanbeveling te doen voor onlangs gekochte producten, stelt u het **Terugkijkvenster** in.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-149">If you've selected to *not* recommend recently purchased products, set the **Look back window**.</span></span> <span data-ttu-id="c9b1c-150">Deze instelling specificeert de tijdsbestek die het model in overweging neemt voordat het product opnieuw aan de gebruiker wordt aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-150">This setting specifies the time frame the model considers before recommending the product to the user again.</span></span> <span data-ttu-id="c9b1c-151">Geef bijvoorbeeld aan dat een klant elke 2 jaar een laptop koopt.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-151">For example, indicate a customer purchases a laptop every 2 years.</span></span> <span data-ttu-id="c9b1c-152">In dit venster wordt de aankoopgeschiedenis van de afgelopen 2 jaar bekeken en als ze een artikel vinden, wordt het uit de aanbevelingen gefilterd.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-152">This window will look at the purchase history for the last 2 years, and if they find an item, the item will be filtered from the recommendations.</span></span>

1. <span data-ttu-id="c9b1c-153">Selecteer **Volgende**</span><span class="sxs-lookup"><span data-stu-id="c9b1c-153">Select **Next**</span></span>

### <a name="add-required-data"></a><span data-ttu-id="c9b1c-154">Vereiste gegevens toevoegen</span><span class="sxs-lookup"><span data-stu-id="c9b1c-154">Add required data</span></span>

1. <span data-ttu-id="c9b1c-155">Selecteer **Gegevens toevoegen** voor **Transactiegeschiedenis van klant** en kies de entiteit die de transactie-/ aankoopgeschiedenisinformatie verstrekt, zoals beschreven in de [vereisten](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="c9b1c-155">Select **Add data** for **Customer transaction history** and choose the entity that provides the transaction/purchase history information as described in the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="c9b1c-156">Wijs de semantische velden toe aan kenmerken binnen uw aankoopgeschiedenis-entiteit en selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-156">Map the semantic fields to attributes within your purchase history entity and select **Next**.</span></span> <span data-ttu-id="c9b1c-157">Zie de [vereisten](#prerequisites) voor beschrijvingen van de velden.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-157">For descriptions of the fields, have a look at the [prerequisites](#prerequisites).</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c9b1c-158">![De entiteitsrelatie definiëren](media/product-recommendation-purchasehistorymapping.PNG "Aankoopgeschiedenispagina met semantische kenmerken die zijn toegewezen aan velden in de geselecteerde aankoopgeschiedenisentiteit")</span><span class="sxs-lookup"><span data-stu-id="c9b1c-158">![Define the entity relationship](media/product-recommendation-purchasehistorymapping.PNG "Purchase history page showing semantic attributes that are mapped to fields in the selected purchase history entity")</span></span>

1. <span data-ttu-id="c9b1c-159">Als de onderstaande velden niet zijn ingevuld, configureert u de relatie tussen de entiteit Aankoopgeschiedenis en de entiteit *Klant*.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-159">If the fields aren't filled in, configure the relationship from your purchase history entity to the *Customer* entity.</span></span>
    1. <span data-ttu-id="c9b1c-160">Selecteer de **entiteit Aankoopgeschiedenis**.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-160">Select the **Purchase history entity**.</span></span>
    1. <span data-ttu-id="c9b1c-161">Selecteer het **Veld** dat de klant identificeert in de entiteit Aankoopgeschiedenis.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-161">Select the **Field** that identifies the customer in the purchase history entity.</span></span> <span data-ttu-id="c9b1c-162">Het moet betrekking hebben op de primaire klant-id van uw entiteit *Klant*.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-162">It needs to relate to the primary customer ID of your *Customer* entity.</span></span>
    1. <span data-ttu-id="c9b1c-163">Selecteer de **entiteit Klant** die overeenkomt met uw primaire klantentiteit.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-163">Select the **Customer entity** that matches your primary customer entity.</span></span>
    1. <span data-ttu-id="c9b1c-164">Voer een naam in waarmee de relatie wordt omschreven.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-164">Enter a name that describes the relationship.</span></span>
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="c9b1c-165">![De pagina Aankoopgeschiedenis waarop het maken van een relatie met klant te zien is](media/model-purchase-join.png "De pagina Aankoopgeschiedenis waarop het maken van een relatie met klant te zien is")</span><span class="sxs-lookup"><span data-stu-id="c9b1c-165">![Purchase history page showing the creation of a relationship to customer](media/model-purchase-join.png "Purchase history page showing the creation of a relationship to customer")</span></span>

1. <span data-ttu-id="c9b1c-166">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-166">Select **Save**.</span></span>

1. <span data-ttu-id="c9b1c-167">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-167">Select **Next**.</span></span>

### <a name="set-schedule-and-review-configuration"></a><span data-ttu-id="c9b1c-168">Schema instellen en configuratie bekijken</span><span class="sxs-lookup"><span data-stu-id="c9b1c-168">Set schedule and review configuration</span></span>

1. <span data-ttu-id="c9b1c-169">Stel een frequentie in voor het opnieuw trainen van uw model.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-169">Set a frequency to retrain your model.</span></span> <span data-ttu-id="c9b1c-170">Deze instelling is belangrijk om de nauwkeurigheid van voorspellingen bij te werken wanneer nieuwe gegevens worden geïmporteerd in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-170">This setting is important to update the accuracy of predictions as new data is imported into Customer Insights.</span></span> <span data-ttu-id="c9b1c-171">De meeste bedrijven kunnen eenmaal per maand opnieuw trainen en krijgen een goede nauwkeurigheid voor hun voorspelling.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-171">Most businesses can retrain once per month and get a good accuracy for their prediction.</span></span>

1. <span data-ttu-id="c9b1c-172">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-172">Select **Next**.</span></span>

1. <span data-ttu-id="c9b1c-173">Bekijk de configuratie.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-173">Review the configuration.</span></span> <span data-ttu-id="c9b1c-174">U kunt teruggaan naar elk willekeurig deel van de voorspellingsconfiguratie door **Bewerken** te selecteren onder de weergegeven waarde.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-174">You can go back to any part of the prediction configuration by selecting **Edit** under the shown value.</span></span> <span data-ttu-id="c9b1c-175">Of u kunt een configuratiestap selecteren vanuit de voortgangsindicator.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-175">Or you can select a configuration step from the progress indicator.</span></span>

1. <span data-ttu-id="c9b1c-176">Selecteer **Opslaan en uitvoeren** om het voorspellingsproces te starten als alle waarden correct zijn geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-176">If all values are configured correctly, select **Save and run** to begin the prediction process.</span></span> <span data-ttu-id="c9b1c-177">Op het tabblad **Mijn voorspellingen** kunt u de status van uw voorspellingen bekijken.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-177">On the **My predictions** tab, you can see the status of your predictions.</span></span> <span data-ttu-id="c9b1c-178">Het proces kan enkele uren in beslag nemen, afhankelijk van de hoeveelheid gegevens die in de voorspelling is gebruikt.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-178">The process may take several hours to complete depending on the amount of data used in the prediction.</span></span>

## <a name="review-a-prediction-status-and-results"></a><span data-ttu-id="c9b1c-179">Een voorspellingsstatus en resultaten bekijken</span><span class="sxs-lookup"><span data-stu-id="c9b1c-179">Review a prediction status and results</span></span>

1. <span data-ttu-id="c9b1c-180">Ga naar het tabblad **Mijn voorspellingen** in **Informatie** > **Voorspellingen**.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-180">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c9b1c-181">![Weergave van de pagina Mijn voorspellingen](media/product-recommendation-mypredictions.PNG "Weergave van de pagina Mijn voorspellingen")</span><span class="sxs-lookup"><span data-stu-id="c9b1c-181">![View of the My Predictions page](media/product-recommendation-mypredictions.PNG "View of the My Predictions page")</span></span>

1. <span data-ttu-id="c9b1c-182">Selecteer de voorspelling die u wilt beoordelen.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-182">Select the prediction you want to review.</span></span>
   - <span data-ttu-id="c9b1c-183">**Voorspellingsnaam:** de naam van de voorspelling die is opgegeven bij het maken ervan.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-183">**Prediction name:** The name of the prediction provided when creating it.</span></span>
   - <span data-ttu-id="c9b1c-184">**Voorspellingstype:** het type model dat voor de voorspelling is gebruikt</span><span class="sxs-lookup"><span data-stu-id="c9b1c-184">**Prediction type:** The type of model used for the prediction</span></span>
   - <span data-ttu-id="c9b1c-185">**Uitvoerentiteit:** naam van de entiteit om de uitvoer van de voorspelling op te slaan.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-185">**Output entity:** Name of the entity to store the output of the prediction.</span></span> <span data-ttu-id="c9b1c-186">U kunt een entiteit met deze naam vinden onder **Gegevens** > **Entiteiten**.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-186">You can find an entity with this name on **Data** > **Entities**.</span></span>
   - <span data-ttu-id="c9b1c-187">**Veld Voorspeld:** dit veld wordt alleen ingevuld voor bepaalde soorten voorspellingen en wordt niet gebruikt bij verloopvoorspelling.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-187">**Predicted field:** This field is populated only for some types of predictions, and isn't used in churn prediction.</span></span>
   - <span data-ttu-id="c9b1c-188">**Status:** de huidige status van de uitvoering van de voorspelling.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-188">**Status:** The current status of the prediction's run.</span></span>
        - <span data-ttu-id="c9b1c-189">**In wachtrij:** de voorspelling wacht momenteel op het uitvoeren van andere processen.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-189">**Queued:** The prediction is currently waiting for other processes to run.</span></span>
        - <span data-ttu-id="c9b1c-190">**Vernieuwen:** de voorspelling is momenteel bezig met het 'scorefase' van de verwerking om resultaten te produceren die naar de uitvoerentiteit zullen worden overgebracht.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-190">**Refreshing:** The prediction is currently running the "score" stage of processing to produce results that will flow into the output entity.</span></span>
        - <span data-ttu-id="c9b1c-191">**Mislukt:** de voorspelling is mislukt.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-191">**Failed:** the prediction has failed.</span></span> <span data-ttu-id="c9b1c-192">Selecteer **Logboeken** voor nadere details.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-192">Select **Logs** for more details.</span></span>
        - <span data-ttu-id="c9b1c-193">**Geslaagd:** de voorspelling is geslaagd.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-193">**Succeeded:** the prediction has succeeded.</span></span> <span data-ttu-id="c9b1c-194">Selecteer **Weergave** onder de verticale puntjes om de voorspelling te beoordelen</span><span class="sxs-lookup"><span data-stu-id="c9b1c-194">Select **View** under the vertical ellipses to review the prediction</span></span>
   - <span data-ttu-id="c9b1c-195">**Bewerkt:** de datum waarop de configuratie voor de voorspelling is gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-195">**Edited:** The date the configuration for the prediction was changed.</span></span>
   - <span data-ttu-id="c9b1c-196">**Laatst vernieuwd:** de datum waarop de voorspelling is vernieuwd resulteert in de uitvoerentiteit.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-196">**Last refreshed:** The date the prediction refreshed results in the output entity.</span></span>

1. <span data-ttu-id="c9b1c-197">Selecteer de verticale puntjes naast de voorspelling waarvoor u de resultaten wilt beoordelen en selecteer **Weergave**.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-197">Select the vertical ellipses next to the prediction you want to review results for and select **View**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c9b1c-198">![Weergave van opties in het menu met verticale puntjes voor een voorspelling, waaronder bewerken, vernieuwen, weergeven, logboeken en verwijderen](media/product-recommendation-verticalellipses.PNG "Weergave van opties in het menu met verticale puntjes voor een voorspelling, waaronder bewerken, vernieuwen, weergeven, logboeken en verwijderen")</span><span class="sxs-lookup"><span data-stu-id="c9b1c-198">![View of options in the vertical ellipses menu for a prediction including edit, refresh, view, logs, and delete](media/product-recommendation-verticalellipses.PNG "View of options in the vertical ellipses menu for a prediction including edit, refresh, view, logs, and delete")</span></span>

1. <span data-ttu-id="c9b1c-199">Er zijn drie primaire gegevenssecties op de resultatenpagina:</span><span class="sxs-lookup"><span data-stu-id="c9b1c-199">There are three primary sections of data within the results page:</span></span>
    1. <span data-ttu-id="c9b1c-200">**Prestaties trainingsmodel:** mogelijke scores zijn A, B of C.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-200">**Training model performance:** A, B, or C are possible scores.</span></span> <span data-ttu-id="c9b1c-201">Deze score geeft de prestatie van de voorspelling aan en kan u helpen de beslissing te nemen om gebruik te maken van de resultaten die in de uitvoerentiteit zijn opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-201">This score indicates the performance of the prediction, and can help you make the decision to use the results stored in the output entity.</span></span>
        - <span data-ttu-id="c9b1c-202">Scores worden bepaald op basis van de volgende regels:</span><span class="sxs-lookup"><span data-stu-id="c9b1c-202">Scores are determined based on the following rules:</span></span>
            - <span data-ttu-id="c9b1c-203">**A** Het model wordt beschouwd als een model van kwaliteit **A** als de metriek "Succes bij K" ten minste 10% meer dan de basislijn is.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-203">**A** The model will be considered **A** quality if the "Success @ K" metric is at least 10% more the baseline.</span></span> 
            - <span data-ttu-id="c9b1c-204">**B** Het model wordt beschouwd als een model van kwaliteit **B** als de metriek "Succes bij K" 0 tot 10% meer dan de basislijn is.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-204">**B** The model will be considered **B** quality if the "Success @ K" metric is 0 to 10% more than the baseline.</span></span>
            - <span data-ttu-id="c9b1c-205">**C** Het model wordt beschouwd als een model van kwaliteit **C** als de metriek "Succes bij K" minder dan de basislijn is.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-205">**C** The model will be considered **C** quality if the "Success @ K" metric is less than than the baseline.</span></span>
               
               > [!div class="mx-imgBorder"]
               > <span data-ttu-id="c9b1c-206">![Weergave van het modelprestatieresultaat](media/product-recommendation-modelperformance.PNG "Weergave van het modelprestatieresultaat")</span><span class="sxs-lookup"><span data-stu-id="c9b1c-206">![View of the model performance result](media/product-recommendation-modelperformance.PNG "View of the model performance result")</span></span>
            - <span data-ttu-id="c9b1c-207">**Basislijn**: het model neemt de beste aanbevolen producten op basis van het aantal aankopen voor alle klanten, en gebruikt geleerde regels die door het model zijn geïdentificeerd om een reeks aanbevelingen voor de klanten te maken.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-207">**Baseline**: The model takes the top most recommended products by purchase count across all customers, and uses learned rules identified by the model to create a set of recommendations for the customers.</span></span> <span data-ttu-id="c9b1c-208">De voorspellingen worden vervolgens vergeleken met de beste producten, zoals berekend door het aantal klanten dat het product heeft gekocht.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-208">The predictions are then compared to the top products, as calculated by the number of customers that had purchased the product.</span></span> <span data-ttu-id="c9b1c-209">Als een klant ten minste één product in zijn aanbevolen producten heeft dat ook te zien was in de best gekochte producten, worden ze beschouwd als een onderdeel van de basislijn.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-209">If a customer has at least one product in their recommended products that was also seen in the top purchased products, they're considered a part of the baseline.</span></span> <span data-ttu-id="c9b1c-210">Als er 10 van deze klanten waren die een aanbevolen product hadden gekocht op een totaal van 100 klanten, zou de basislijn 10% zijn.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-210">If there were 10 of these customers that had a recommended product purchased out of 100 total customers, the baseline would be 10%.</span></span>
            - <span data-ttu-id="c9b1c-211">**Succes bij K**: door gebruik te maken van een validatieset van transacties, worden aanbevelingen gemaakt voor alle klanten en vergeleken met de validatieset van transacties.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-211">**Success @ K**: Using a validation set of time period of transactions, recommendations are created for all customers and compared against the validation set of transactions.</span></span> <span data-ttu-id="c9b1c-212">In een periode van 12 maanden kan bijvoorbeeld maand 12 worden gereserveerd als een validatieset van gegevens.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-212">For example, in a 12 month period, month 12 might be set aside as a validation set of data.</span></span> <span data-ttu-id="c9b1c-213">Als het model ten minste één ding voorspelt dat u in maand 12 zou kopen op basis van wat het van de afgelopen 11 maanden heeft geleerd, zou de klant de metriek "Succesbij K" verhogen.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-213">If the model predicts at least one thing you would purchase in month 12 based on what it learned from the previous 11 months, the customer would increase the "Success @ K" metric.</span></span>
    
    1. <span data-ttu-id="c9b1c-214">**Meest voorgestelde producten (met telling)**: de top 5 producten die zijn voorspeld voor uw klanten.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-214">**Most suggested products (with tally):** The top 5 products that were predicted for your customers.</span></span>
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="c9b1c-215">![Grafiek met de top 5 van meest aanbevolen producten](media/product-recommendation-topproducts.PNG "Grafiek met de top 5 van meest aanbevolen producten")</span><span class="sxs-lookup"><span data-stu-id="c9b1c-215">![Graph showing the top 5 most recommended products](media/product-recommendation-topproducts.PNG "Graph showing the top 5 most recommended products")</span></span>
    
    1. <span data-ttu-id="c9b1c-216">**Zeer betrouwbare productaanbevelingen**: een voorbeeld van aanbevelingen aan uw klanten waarvan het model denkt dat ze waarschijnlijk door de klant zullen worden gekocht.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-216">**High-confidence product recommendations:** A sample of recommendations provided to your customers that the model believes are likely to be purchased by the customer.</span></span>
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="c9b1c-217">![Lijst met zeer betrouwbare suggesties voor een selecte groep individuele klanten](media/product-recommendation-highconfidence.PNG "Lijst met zeer betrouwbare suggesties voor een selecte groep individuele klanten")</span><span class="sxs-lookup"><span data-stu-id="c9b1c-217">![List showing high confidence suggestions for a select set of individual customers](media/product-recommendation-highconfidence.PNG "List showing high confidence suggestions for a select set of individual customers")</span></span>

## <a name="fix-a-failed-prediction"></a><span data-ttu-id="c9b1c-218">Een mislukte voorspelling corrigeren</span><span class="sxs-lookup"><span data-stu-id="c9b1c-218">Fix a failed prediction</span></span>

1. <span data-ttu-id="c9b1c-219">Ga naar het tabblad **Mijn voorspellingen** in **Informatie** > **Voorspellingen**.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-219">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="c9b1c-220">Selecteer de voorspelling waarvoor u foutlogboeken wilt bekijken en selecteer **Logboeken**.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-220">Select the prediction you would like to view error logs for and select **Logs**.</span></span>

1. <span data-ttu-id="c9b1c-221">Bekijk alle fouten.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-221">Review all the errors.</span></span> <span data-ttu-id="c9b1c-222">Er zijn verschillende typen fouten die kunnen optreden en deze beschrijven welke toestand de fout heeft veroorzaakt.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-222">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="c9b1c-223">Een fout waarbij er niet genoeg gegevens beschikbaar zijn om een nauwkeurige voorspelling te maken wordt bijvoorbeeld doorgaans hersteld door extra gegevens in Customer Insights te laden.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-223">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="c9b1c-224">Een voorspelling vernieuwen</span><span class="sxs-lookup"><span data-stu-id="c9b1c-224">Refresh a prediction</span></span>

<span data-ttu-id="c9b1c-225">Voorspellingen worden automatisch volgens dezelfde [planning vernieuwd als uw gegevens](system.md#schedule-tab), zoals geconfigureerd in instellingen.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-225">Predictions automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span>

1. <span data-ttu-id="c9b1c-226">Ga naar het tabblad **Mijn voorspellingen** in **Informatie** > **Voorspellingen**.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-226">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="c9b1c-227">Selecteer de verticale puntjes naast de voorspelling die u wilt vernieuwen.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-227">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="c9b1c-228">Selecteer **Vernieuwen**.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-228">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="c9b1c-229">Een voorspelling verwijderen</span><span class="sxs-lookup"><span data-stu-id="c9b1c-229">Delete a prediction</span></span>

<span data-ttu-id="c9b1c-230">Als u een voorspelling verwijdert, wordt ook de uitvoerentiteit ervan verwijderd.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-230">Deleting a prediction will also remove its output entity.</span></span>

1. <span data-ttu-id="c9b1c-231">Ga naar het tabblad **Mijn voorspellingen** in **Informatie** > **Voorspellingen**.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-231">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="c9b1c-232">Selecteer de verticale puntjes naast de voorspelling die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-232">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="c9b1c-233">Selecteer **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="c9b1c-233">Select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]