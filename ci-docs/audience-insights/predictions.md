---
title: Gedeeltelijke gegevens voltooien met behulp van voorspellingen
description: Gebruik voorspellingen om onvolledige klantgegevens in te vullen.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: zacook
manager: shellyha
ms.openlocfilehash: 577232c7e901dfd54a195c3e9cfac5d1f0f866e6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268266"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="10297-103">Uw gedeeltelijke gegevens aanvullen met voorspellingen</span><span class="sxs-lookup"><span data-stu-id="10297-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="10297-104">Met Voorspellingen kunt u eenvoudig voorspelde waarden maken die uw begrip van een klant kunnen verbeteren.</span><span class="sxs-lookup"><span data-stu-id="10297-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="10297-105">Op de pagina **Intelligence** > **Voorspellingen** kunt u **Mijn voorspellingen** selecteren om voorspellingen te zien die u hebt geconfigureerd in andere delen van doelgroepinzichten en om deze verder aan te passen.</span><span class="sxs-lookup"><span data-stu-id="10297-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="10297-106">U kunt deze functie niet gebruiken als uw omgeving Azure Data Lake Gen 2-opslag gebruikt.</span><span class="sxs-lookup"><span data-stu-id="10297-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="10297-107">De voorspellingsfunctie maakt gebruik van geautomatiseerde middelen om gegevens te evalueren en voorspellingen te doen op basis van die gegevens, en heeft daarom de mogelijkheid om te worden gebruikt als methode voor profilering, zoals die term wordt gedefinieerd door de Algemene verordening gegevensbescherming ("AVG").</span><span class="sxs-lookup"><span data-stu-id="10297-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="10297-108">Op het gebruik door de klant van deze functie om gegevens te verwerken, zijn mogelijk de AVG of andere wetten of voorschriften van toepassing.</span><span class="sxs-lookup"><span data-stu-id="10297-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="10297-109">U bent ervoor verantwoordelijk dat uw gebruik van Dynamics 365 Customer Insights, inclusief voorspellingen, voldoet aan alle toepasselijke wet- en regelgeving, inclusief wetten met betrekking tot privacy, persoonsgegevens, biometrische gegevens, gegevensbescherming en vertrouwelijkheid van communicatie.</span><span class="sxs-lookup"><span data-stu-id="10297-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="10297-110">Vereisten</span><span class="sxs-lookup"><span data-stu-id="10297-110">Prerequisites</span></span>

<span data-ttu-id="10297-111">Voordat uw organisatie de voorspellingsfunctie kan gebruiken, moet u ervoor zorgen dat aan de volgende voorwaarden is voldaan:</span><span class="sxs-lookup"><span data-stu-id="10297-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="10297-112">Uw organisatie heeft een exemplaar [ingesteld in de Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) en deze zit in dezelfde organisatie als Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="10297-112">Your organization has an instance [set up in the Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="10297-113">Uw omgeving is gekoppeld aan uw Common Data Service-exemplaar.</span><span class="sxs-lookup"><span data-stu-id="10297-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="10297-114">Als u [een nieuwe omgeving maakt](manage-environments.md), configureert u deze in het dialoogvenster **Een omgeving maken** en selecteert u **Geavanceerd**.</span><span class="sxs-lookup"><span data-stu-id="10297-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="10297-115">Als u al een omgeving hebt gemaakt, gaat u naar de instellingen en selecteert u **Geavanceerd**.</span><span class="sxs-lookup"><span data-stu-id="10297-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="10297-116">Hoe dan ook, in de sectie **Voorspellingen gebruiken** voert u de URL van het Common Data Service-exemplaar in waaraan u uw omgeving wilt koppelen.</span><span class="sxs-lookup"><span data-stu-id="10297-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="10297-117">Een voorspelling maken in de entiteit Klant</span><span class="sxs-lookup"><span data-stu-id="10297-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="10297-118">Ga in doelgroepinzichten naar **Gegevens** > **Entiteiten**.</span><span class="sxs-lookup"><span data-stu-id="10297-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="10297-119">Selecteer de entiteit **Klant**.</span><span class="sxs-lookup"><span data-stu-id="10297-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="10297-120">Selecteer in de entiteit **Klant: CustomerInsights** op het tabblad **Velden**.</span><span class="sxs-lookup"><span data-stu-id="10297-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="10297-121">Zoek de kenmerknaam waarvoor u waarden wilt voorspellen en selecteer vervolgens het pictogram **Overzicht** in de kolom **Samenvatting**.</span><span class="sxs-lookup"><span data-stu-id="10297-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="10297-122">![Overzichtspictogram](media/intelligence-overviewicon.png "Overzichtspictogram")</span><span class="sxs-lookup"><span data-stu-id="10297-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="10297-123">Als er veel waarden ontbreken voor uw kenmerk, selecteert u **Ontbrekende waarden voorspellen** om door te gaan met uw voorspelling.</span><span class="sxs-lookup"><span data-stu-id="10297-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="10297-124">![Overzichtsstatus met knop Ontbrekende waarden voorspellen weergegeven](media/intelligence-overviewpredictmissingvalues.png "Overzichtsstatus met knop Ontbrekende waarden voorspellen weergegeven")</span><span class="sxs-lookup"><span data-stu-id="10297-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="10297-125">Geef een **weergavenaam** en een **naam van de uitvoerentiteit** op voor de resultaten van de voorspelling.</span><span class="sxs-lookup"><span data-stu-id="10297-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="10297-126">Een vooraf ingevulde lijst met opties laat zien waar u de waarden kunt toewijzen aan een voorspelde categorie.</span><span class="sxs-lookup"><span data-stu-id="10297-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="10297-127">In dit geval zullen uw enige categorieopties 0 of 1 zijn, omdat deze verwijzen naar de waar/onwaar of binaire aard van de voorspelling.</span><span class="sxs-lookup"><span data-stu-id="10297-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="10297-128">Wijs in de kolom Categorie de veldwaarden die u als '0' wilt classificeren in de uiteindelijke voorspelling toe aan "0" in de kolom Categorie en de items die u als "1" wilt classificeren in de uiteindelijke voorspelling aan "1".</span><span class="sxs-lookup"><span data-stu-id="10297-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="10297-129">![Voorbeeld van toegewezen veldwaarden aan categorieën](media/intelligence-categorymapping.png "Voorbeeld van toegewezen veldwaarden aan categorieën")</span><span class="sxs-lookup"><span data-stu-id="10297-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="10297-130">Selecteer **Gereed**. De voorspelling wordt nu verwerkt.</span><span class="sxs-lookup"><span data-stu-id="10297-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="10297-131">De verwerking duurt enige tijd, afhankelijk van de grootte en complexiteit van gegevens.</span><span class="sxs-lookup"><span data-stu-id="10297-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="10297-132">De resultaten zijn beschikbaar in een nieuwe entiteit op basis van de **naam van de uitvoerentiteit** van de voorspelling die u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="10297-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="10297-133">Een voorspelling maken terwijl u een segment maakt</span><span class="sxs-lookup"><span data-stu-id="10297-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="10297-134">Het voorspellen van ontbrekende waarden voor een specifiek kenmerk naar keuze is ook mogelijk bij het maken van een segment.</span><span class="sxs-lookup"><span data-stu-id="10297-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="10297-135">In het bijzonder wanneer u snel een segment maakt op basis van uw geharmoniseerde entiteit Klant en entiteit Meetcriterium voor klant.</span><span class="sxs-lookup"><span data-stu-id="10297-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="10297-136">Als onderdeel van deze stroom kiest u een specifiek kenmerk om uw segment op te baseren, zoals Klanttevredenheid, Aankoopbedrag of een ander kenmerk van uw keuze.</span><span class="sxs-lookup"><span data-stu-id="10297-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="10297-137">Bij het maken van segmenten zal het systeem een methode voorstellen voor het voorspellen van ontbrekende waarden voor dit kenmerk.</span><span class="sxs-lookup"><span data-stu-id="10297-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="10297-138">Ga in doelgroepinzichten naar **Segmenten** en selecteer de tegel **Profielen**.</span><span class="sxs-lookup"><span data-stu-id="10297-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="10297-139">Kies een **veld** om een segment te maken en selecteer een **operator** en selecteer vervolgens **Evalueren**.</span><span class="sxs-lookup"><span data-stu-id="10297-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="10297-140">Geef een **naam** en een **weergavenaam** op voor het segment.</span><span class="sxs-lookup"><span data-stu-id="10297-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="10297-141">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="10297-141">Select **Save**.</span></span>

5. <span data-ttu-id="10297-142">Als het gemaakte segment onvolledige gegevens in het bronveld bevat, kunt u ervoor kiezen om de ontbrekende waarden te voorspellen.</span><span class="sxs-lookup"><span data-stu-id="10297-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="10297-143">![Voorspellingsknop](media/segments-predictoption.png "Voorspellingsknop")</span><span class="sxs-lookup"><span data-stu-id="10297-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="10297-144">Geef een **weergavenaam** en een **naam van de uitvoerentiteit** op voor de resultaten van de voorspelling.</span><span class="sxs-lookup"><span data-stu-id="10297-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="10297-145">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="10297-145">Select **Done**.</span></span> <span data-ttu-id="10297-146">Uw voorspelling wordt binnenkort gegenereerd in een nieuwe entiteit met de naam die u hebt opgegeven bij **Naam van uitvoerentiteit**.</span><span class="sxs-lookup"><span data-stu-id="10297-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="10297-147">Een voorspelling weergeven</span><span class="sxs-lookup"><span data-stu-id="10297-147">View a prediction</span></span>

1. <span data-ttu-id="10297-148">Ga in doelgroepinzichten naar **Intelligence** > **Voorspellingen** > **Mijn voorspellingen**.</span><span class="sxs-lookup"><span data-stu-id="10297-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="10297-149">Selecteer de voorspelling die u wilt beoordelen.</span><span class="sxs-lookup"><span data-stu-id="10297-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="10297-150">Selecteer de drie puntjes in de kolom **Acties** en kies **Weergeven**.</span><span class="sxs-lookup"><span data-stu-id="10297-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="10297-151">U ziet een aantal gegevenspunten in de weergave van uw voorspelling.</span><span class="sxs-lookup"><span data-stu-id="10297-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="10297-152">![Voorspellingspagina](media/intelligence-predictionsviewpage.png "Voorspellingspagina")</span><span class="sxs-lookup"><span data-stu-id="10297-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="10297-153">**Voorspelde waarden** toont de toewijzing die u tijdens de fase Toewijzing van veldwaarde aan categorie hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="10297-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="10297-154">Dit zijn de waarden in uw gegevensset weergegeven die zijn toegewezen aan een specifieke categorie.</span><span class="sxs-lookup"><span data-stu-id="10297-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="10297-155">-**Meest populaire beïnvloeders** zijn de factoren in uw gegevensset die waarschijnlijk van invloed zijn op het vertrouwen van de voorspelling van uw veldwaarde die wordt toegewezen aan een specifieke categorie.</span><span class="sxs-lookup"><span data-stu-id="10297-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="10297-156">**Prestatie** geeft aan hoe de voorspellingen het doen.</span><span class="sxs-lookup"><span data-stu-id="10297-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="10297-157">Selecteer de koppeling voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="10297-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="10297-158">**Voorbeeld** toont voorbeelden van de uitgevoerde gegevensset voor uw voorspelling en de waarschijnlijkheid van, of ons vertrouwen in, de voorspelde waarde, waarbij 0 onzeker is en 1 zeker is.</span><span class="sxs-lookup"><span data-stu-id="10297-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="10297-159">Een voorspelling bijwerken</span><span class="sxs-lookup"><span data-stu-id="10297-159">Update a prediction</span></span>

1. <span data-ttu-id="10297-160">Ga in doelgroepinzichten naar **Intelligence** > **Voorspellingen** > **Mijn voorspellingen**.</span><span class="sxs-lookup"><span data-stu-id="10297-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="10297-161">Selecteer de voorspelling die u wilt bijwerken en selecteer het pictogram **Bijwerken**.</span><span class="sxs-lookup"><span data-stu-id="10297-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="10297-162">De voorspelling wordt gepland voor verwerking.</span><span class="sxs-lookup"><span data-stu-id="10297-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="10297-163">U kunt de tijd zien waarop deze voor het laatst is bijgewerkt in de kolom **Bijgewerkt** van de pagina **Voorspellingen**.</span><span class="sxs-lookup"><span data-stu-id="10297-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="10297-164">Een voorspelling bewerken</span><span class="sxs-lookup"><span data-stu-id="10297-164">Edit a prediction</span></span>

<span data-ttu-id="10297-165">Nadat u een voorspelling hebt gemaakt, kunt u het model aanpassen in de AI Builder om de effectiviteit van uw model te vergroten.</span><span class="sxs-lookup"><span data-stu-id="10297-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="10297-166">Ga in doelgroepinzichten naar **Intelligence** > **Voorspellingen** > **Mijn voorspellingen**.</span><span class="sxs-lookup"><span data-stu-id="10297-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="10297-167">Selecteer de voorspelling die u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="10297-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="10297-168">Selecteer de drie puntjes in de kolom **Acties** en kies **Weergeven**.</span><span class="sxs-lookup"><span data-stu-id="10297-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="10297-169">Selecteer **Aanpassen in AI Builder**.</span><span class="sxs-lookup"><span data-stu-id="10297-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="10297-170">Werk uw model bij in de AI Builder.</span><span class="sxs-lookup"><span data-stu-id="10297-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="10297-171">[Meer informatie over het beheren van modellen in de AI Builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="10297-171">[Learn more about managing models in the AI builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="10297-172">Bij de volgende uitvoering van uw voorspelling wordt het bijgewerkte model gebruikt dat u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="10297-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="10297-173">Nieuwe modellen die zijn gemaakt in AI Builder, worden niet weergegeven in doelgroepinzichten, tenzij het model is gemaakt op basis van de hierboven genoemde ervaringen.</span><span class="sxs-lookup"><span data-stu-id="10297-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="10297-174">Een voorspelling verwijderen</span><span class="sxs-lookup"><span data-stu-id="10297-174">Remove a prediction</span></span>

1. <span data-ttu-id="10297-175">Ga in doelgroepinzichten naar **Intelligence** > **Voorspellingen** > **Mijn voorspellingen**.</span><span class="sxs-lookup"><span data-stu-id="10297-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="10297-176">Selecteer de voorspelling die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="10297-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="10297-177">Selecteer de drie puntjes in de kolom **Acties** en kies **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="10297-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="10297-178">Bevestig de verwijdering.</span><span class="sxs-lookup"><span data-stu-id="10297-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="10297-179">Problemen oplossen</span><span class="sxs-lookup"><span data-stu-id="10297-179">Troubleshooting</span></span>

<span data-ttu-id="10297-180">Als u het proces voor het bijvoegen van Common Data Service niet kunt voltooien als gevolg van een fout, kunt u proberen het proces handmatig te voltooien.</span><span class="sxs-lookup"><span data-stu-id="10297-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="10297-181">Er zijn twee bekende problemen die kunnen optreden tijdens het bijvoegen:</span><span class="sxs-lookup"><span data-stu-id="10297-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="10297-182">De invoegtoepassingoplossing Klantenkaart is niet geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="10297-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="10297-183">Voer de instructies uit voor [het installeren en configureren van de oplossing](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="10297-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="10297-184">App-machtigingen worden niet verleend.</span><span class="sxs-lookup"><span data-stu-id="10297-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="10297-185">Ga naar [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="10297-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="10297-186">Selecteer **Omgevingen**.</span><span class="sxs-lookup"><span data-stu-id="10297-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="10297-187">Selecteer het beletselteken naast de omgeving waaraan u de toestemming wilt toevoegen en selecteer **Instellingen**.</span><span class="sxs-lookup"><span data-stu-id="10297-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="10297-188">Vouw **Gebruikers + machtigingen** uit en selecteer **Gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="10297-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="10297-189">Selecteer **+ Nieuw** en selecteer **Gebruiker**.</span><span class="sxs-lookup"><span data-stu-id="10297-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="10297-190">Selecteer **Toepassingsgebruiker** als dit nog niet is geselecteerd en voer de volgende informatie in:</span><span class="sxs-lookup"><span data-stu-id="10297-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="10297-191">**Gebruikersnaam:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="10297-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="10297-192">**Toepassings-id:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="10297-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="10297-193">**Voornaam:** Customer</span><span class="sxs-lookup"><span data-stu-id="10297-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="10297-194">**Achternaam:** Insights</span><span class="sxs-lookup"><span data-stu-id="10297-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="10297-195">**Primair e-mailadres:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="10297-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="10297-196">Kies **Opslaan en sluiten**.</span><span class="sxs-lookup"><span data-stu-id="10297-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="10297-197">Selecteer de gebruiker die u zojuist hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="10297-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="10297-198">Selecteer **Rollen beheren** in de bovenste menubalk.</span><span class="sxs-lookup"><span data-stu-id="10297-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="10297-199">Selecteer **Systeembeheerder** en selecteer vervolgens **OK**.</span><span class="sxs-lookup"><span data-stu-id="10297-199">Select **System Administrator**, then select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]