---
title: Customer Insights-gegevens naar Adobe Campaign Standard exporteren
description: Ontdek hoe u segmenten voor doelgroepinzichten gebruikt in Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596309"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="1c5b2-103">Customer Insights-segmenten gebruiken in Adobe Campaign Standard (preview)</span><span class="sxs-lookup"><span data-stu-id="1c5b2-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="1c5b2-104">Als gebruiker van doelgroepinzichten voor Dynamics 365 Customer Insights hebt u mogelijk segmenten gemaakt om uw marketingcampagnes efficiënter te maken door u op relevante doelgroepen te richten.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="1c5b2-105">Als u een segment uit doelgroepinzichten in Adobe Experience Platform en toepassingen zoals Adobe Campaign Standard wilt gebruiken, moet u een paar stappen volgen die in dit artikel worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Procesdiagram van de stappen die in dit artikel worden beschreven.":::

## <a name="prerequisites"></a><span data-ttu-id="1c5b2-107">Vereisten</span><span class="sxs-lookup"><span data-stu-id="1c5b2-107">Prerequisites</span></span>

-   <span data-ttu-id="1c5b2-108">Dynamics 365 Customer Insights-licentie</span><span class="sxs-lookup"><span data-stu-id="1c5b2-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="1c5b2-109">Adobe Campaign Standard-licentie</span><span class="sxs-lookup"><span data-stu-id="1c5b2-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="1c5b2-110">Azure Blob Storage-account</span><span class="sxs-lookup"><span data-stu-id="1c5b2-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="1c5b2-111">Campagne-overzicht</span><span class="sxs-lookup"><span data-stu-id="1c5b2-111">Campaign Overview</span></span>

<span data-ttu-id="1c5b2-112">Laten we eens kijken naar een fictieve voorbeeldcampagne om beter te begrijpen hoe u segmenten uit doelgroepinzichten in Adobe Experience Platform kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="1c5b2-113">Laten we aannemen dat uw bedrijf een maandelijkse, op abonnementen gebaseerde service biedt aan uw klanten in de Verenigde Staten.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="1c5b2-114">U wilt klanten identificeren waarvan het abonnement binnen acht dagen moet worden verlengd, maar die hun abonnement nog niet hebben verlengd.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="1c5b2-115">Om deze klanten te behouden, wilt u ze een promotieaanbieding sturen via e-mail, met Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="1c5b2-116">In dit voorbeeld willen we de promotionele e-mailcampagne één keer uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="1c5b2-117">In dit artikel wordt niet het gebruiksscenario behandeld waarin de campagne meerdere keer wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="1c5b2-118">Doelgroepinzichten en Adobe Campaign Standard kunnen echter ook worden geconfigureerd om te werken voor een scenario met terugkerend campagnes.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="1c5b2-119">Uw doelgroep identificeren</span><span class="sxs-lookup"><span data-stu-id="1c5b2-119">Identify your target audience</span></span>

<span data-ttu-id="1c5b2-120">In ons scenario gaan we ervan uit dat de e-mailadressen van de klanten beschikbaar zijn in doelgroepinzichten en dat hun promotievoorkeuren zijn geanalyseerd om leden van het segment te identificeren.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="1c5b2-121">Het [segment dat u hebt gedefinieerd in doelgroepinzichten](segments.md) wordt **ChurnProneCustomers** genoemd en u bent van plan deze klanten de e-mailpromotie te sturen.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Schermopname van de pagina Segmenten met het gemaakte segment ChurnProneCustomers.":::

<span data-ttu-id="1c5b2-123">De aanbiedings-e-mail die u wilt verzenden, bevat de voornaam, achternaam en einddatum van het abonnement van de klant.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="1c5b2-124">Klanten worden geïnformeerd over de korting die ze krijgen als ze hun abonnement verlengen voordat het afloopt.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="1c5b2-125">Uw doelgroep exporteren</span><span class="sxs-lookup"><span data-stu-id="1c5b2-125">Export your target audience</span></span>

<span data-ttu-id="1c5b2-126">Nu onze doelgroep is geïdentificeerd, kunnen we de export van doelgroepinzichten naar een Azure Blob Storage-account configureren.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="1c5b2-127">Ga in doelgroepinzichten naar **Beheer** > **Exportbestemmingen**.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="1c5b2-128">Selecteer **Instellen** in de tegel **Adobe Campaign**​.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-128">In the **Adobe Campaign** tile, select **Set up**.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Configuratietegel voor Adobe Campaign Standard.":::

1. <span data-ttu-id="1c5b2-130">Geef een **weergavenaam** voor deze nieuwe exportbestemming op en voer vervolgens de **accountnaam**, **accountsleutel** en **container** in van de Azure Blob Storage-account waarnaar u het segment wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Schermopname van de opslagaccountconfiguratie. "::: 

   - <span data-ttu-id="1c5b2-132">Zie voor meer informatie over het vinden van de naam en de accountsleutel van uw Azure-blobopslagaccount [Opslagaccountinstellingen beheren in de Azure-portal](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="1c5b2-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="1c5b2-133">Zie voor meer informatie over het maken van een container [Een container maken](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="1c5b2-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="1c5b2-134">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-134">Select **Next**.</span></span>

1. <span data-ttu-id="1c5b2-135">Sluit het segment dat u u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="1c5b2-136">In dit voorbeeld is het **ChurnProneCustomers**​.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Schermopname van de gebruikersinterface voor segmentselectie met het segment ChurnProneCustomers geselecteerd.":::

1. <span data-ttu-id="1c5b2-138">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-138">Select **Next**.</span></span>

1. <span data-ttu-id="1c5b2-139">Nu wijzen we de velden **Bron** van het segment voor doelgroepinzichten toe aan de veldnamen **Doel** in het Adobe Campaign Standard-profielschema.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-139">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Veldtoewijzing voor de Adobe Campaign Standard-connector.":::

   <span data-ttu-id="1c5b2-141">Als u meer kenmerken wilt toevoegen, selecteert u **Kenmerk toevoegen**​.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-141">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="1c5b2-142">De doelnaam kan afwijken van de naam van het bronveld, zodat u nog steeds segmentuitvoer van doelgroepinzichten aan Adobe Campaign Standard kan toewijzen als de velden niet dezelfde naam hebben in de twee systemen.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-142">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1c5b2-143">E-mailadres wordt gebruikt als identiteitsveld, maar u kunt elke andere id uit uw klantprofiel voor doelgroepinzichten gebruiken om gegevens toe te wijzen aan Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-143">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="1c5b2-144">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-144">Select **Save**.</span></span>

<span data-ttu-id="1c5b2-145">Nadat u de exportbestemming hebt opgeslagen, vindt u deze op **Beheer** > **Exports** > **Mijn exportbestemmingen**.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-145">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Schermopname met een lijst met exports en gemarkeerd voorbeeldsegment.":::

<span data-ttu-id="1c5b2-147">U kunt [het segment nu op aanvraag exporteren](export-destinations.md#export-data-on-demand)​.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-147">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="1c5b2-148">De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md).</span><span class="sxs-lookup"><span data-stu-id="1c5b2-148">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1c5b2-149">Zorg ervoor dat het aantal records in het geëxporteerde segment binnen de toegestane limiet van uw Adobe Campaign Standard-licentie valt.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-149">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="1c5b2-150">Geëxporteerde gegevens worden opgeslagen in de Azure Blob-opslagcontainer die u eerder hebt geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-150">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="1c5b2-151">Het volgende mappad wordt automatisch gemaakt in uw container:</span><span class="sxs-lookup"><span data-stu-id="1c5b2-151">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="1c5b2-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="1c5b2-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="1c5b2-153">Voorbeeld: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="1c5b2-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="1c5b2-154">Adobe Campaign Standard configureren</span><span class="sxs-lookup"><span data-stu-id="1c5b2-154">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="1c5b2-155">Wanneer een segment uit doelgroepinzichten wordt geëxporteerd, bevat het de kolommen die u hebt geselecteerd tijdens het definiëren van de exportbestemming in de vorige stap.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-155">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="1c5b2-156">Deze gegevens kunnen worden gebruikt om [profielen te maken in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles)​.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-156">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="1c5b2-157">Om het segment in Adobe Campaign Standard te gebruiken, moeten we het profielschema in Adobe Campaign Standard uitbreiden met twee extra velden.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-157">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="1c5b2-158">Lees hoe u de [profielresource uitbreidt](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) met nieuwe velden in Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-158">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="1c5b2-159">In ons voorbeeld zijn dit de velden *Segmentnaam en Segmentdatum (optioneel)*.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-159">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="1c5b2-160">We gebruiken deze velden om de profielen in Adobe Campaign Standard te identificeren waarop we ons voor deze campagne willen richten.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-160">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="1c5b2-161">Als er geen andere records in Adobe Campaign Standard zijn, behalve de records die u gaat importeren, kunt u deze stap overslaan.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-161">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="1c5b2-162">Gegevens importeren in Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="1c5b2-162">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="1c5b2-163">Nu aan alle voorwaarden is voldaan, moeten we de voorbereide doelgroepgegevens van doelgroepinzichten importeren in Adobe Campaign Standard om profielen te maken.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-163">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="1c5b2-164">Lees [hoe u profielen importeert in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) met behulp van een werkstroom.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-164">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="1c5b2-165">De importwerkstroom in de onderstaande afbeelding is geconfigureerd om elke acht uur te worden uitgevoerd en zoekt naar geëxporteerde segmenten voor doelgroepinzichten (CSV-bestand in Azure Blob Storage).</span><span class="sxs-lookup"><span data-stu-id="1c5b2-165">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="1c5b2-166">De werkstroom extraheert de inhoud van het CSV-bestand in een opgegeven kolomvolgorde.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-166">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="1c5b2-167">Deze werkstroom is ontwikkeld om elementaire foutafhandeling uit te voeren en ervoor te zorgen dat elke record een e-mailadres heeft voordat de gegevens in Adobe Campaign Standard worden gehydrateerd.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-167">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="1c5b2-168">De werkstroom extraheert ook de segmentnaam uit de bestandsnaam voordat deze wordt omgezet in ACS-profielgegevens.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-168">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Schermopname van een importwerkstroom in de Adobe Campaign Standard-gebruikersinterface.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="1c5b2-170">De doelgroep ophalen in Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="1c5b2-170">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="1c5b2-171">Zodra de gegevens zijn geïmporteerd in Adobe Campaign Standard, kunt u [een werkstroom maken](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) en [query's](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) op de klanten uitvoeren op basis van de *segmentnaam* en *segmentdatum* om profielen te selecteren die zijn geïdentificeerd voor onze voorbeeldcampagne.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-171">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="1c5b2-172">De e-mail maken en verzenden met Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="1c5b2-172">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="1c5b2-173">Maak de e-mailinhoud en [test en verzend](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) vervolgens uw e-mail.</span><span class="sxs-lookup"><span data-stu-id="1c5b2-173">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Voorbeeld van e-mail met verlengingsaanbieding van Adobe Campaign Standard.":::