---
title: Customer Insights-gegevens naar Adobe Campaign Standard exporteren
description: Ontdek hoe u segmenten voor doelgroepinzichten gebruikt in Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: b6c010d84119c2fa8b3ef99017c65f9939bf28c4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760275"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="39ff5-103">Customer Insights-segmenten gebruiken in Adobe Campaign Standard (preview)</span><span class="sxs-lookup"><span data-stu-id="39ff5-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="39ff5-104">Als gebruiker van doelgroepinzichten voor Dynamics 365 Customer Insights hebt u mogelijk segmenten gemaakt om uw marketingcampagnes efficiënter te maken door u op relevante doelgroepen te richten.</span><span class="sxs-lookup"><span data-stu-id="39ff5-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="39ff5-105">Als u een segment uit doelgroepinzichten in Adobe Experience Platform en toepassingen zoals Adobe Campaign Standard wilt gebruiken, moet u een paar stappen volgen die in dit artikel worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="39ff5-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Procesdiagram van de stappen die in dit artikel worden beschreven.":::

## <a name="prerequisites"></a><span data-ttu-id="39ff5-107">Vereisten</span><span class="sxs-lookup"><span data-stu-id="39ff5-107">Prerequisites</span></span>

-   <span data-ttu-id="39ff5-108">Dynamics 365 Customer Insights-licentie</span><span class="sxs-lookup"><span data-stu-id="39ff5-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="39ff5-109">Adobe Campaign Standard-licentie</span><span class="sxs-lookup"><span data-stu-id="39ff5-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="39ff5-110">Azure Blob Storage-account</span><span class="sxs-lookup"><span data-stu-id="39ff5-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="39ff5-111">Campagne-overzicht</span><span class="sxs-lookup"><span data-stu-id="39ff5-111">Campaign Overview</span></span>

<span data-ttu-id="39ff5-112">Laten we eens kijken naar een fictieve voorbeeldcampagne om beter te begrijpen hoe u segmenten uit doelgroepinzichten in Adobe Experience Platform kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="39ff5-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="39ff5-113">Laten we aannemen dat uw bedrijf een maandelijkse, op abonnementen gebaseerde service biedt aan uw klanten in de Verenigde Staten.</span><span class="sxs-lookup"><span data-stu-id="39ff5-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="39ff5-114">U wilt klanten identificeren waarvan het abonnement binnen acht dagen moet worden verlengd, maar die hun abonnement nog niet hebben verlengd.</span><span class="sxs-lookup"><span data-stu-id="39ff5-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="39ff5-115">Om deze klanten te behouden, wilt u ze een promotieaanbieding sturen via e-mail, met Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="39ff5-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="39ff5-116">In dit voorbeeld willen we de promotionele e-mailcampagne één keer uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="39ff5-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="39ff5-117">In dit artikel wordt niet het gebruiksscenario behandeld waarin de campagne meerdere keer wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="39ff5-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="39ff5-118">Doelgroepinzichten en Adobe Campaign Standard kunnen echter ook worden geconfigureerd om te werken voor een scenario met terugkerend campagnes.</span><span class="sxs-lookup"><span data-stu-id="39ff5-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="39ff5-119">Uw doelgroep identificeren</span><span class="sxs-lookup"><span data-stu-id="39ff5-119">Identify your target audience</span></span>

<span data-ttu-id="39ff5-120">In ons scenario gaan we ervan uit dat de e-mailadressen van de klanten beschikbaar zijn in doelgroepinzichten en dat hun promotievoorkeuren zijn geanalyseerd om leden van het segment te identificeren.</span><span class="sxs-lookup"><span data-stu-id="39ff5-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="39ff5-121">Het [segment dat u hebt gedefinieerd in doelgroepinzichten](segments.md) wordt **ChurnProneCustomers** genoemd en u bent van plan deze klanten de e-mailpromotie te sturen.</span><span class="sxs-lookup"><span data-stu-id="39ff5-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Schermopname van de pagina Segmenten met het gemaakte segment ChurnProneCustomers.":::

<span data-ttu-id="39ff5-123">De aanbiedings-e-mail die u wilt verzenden, bevat de voornaam, achternaam en einddatum van het abonnement van de klant.</span><span class="sxs-lookup"><span data-stu-id="39ff5-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="39ff5-124">Klanten worden geïnformeerd over de korting die ze krijgen als ze hun abonnement verlengen voordat het afloopt.</span><span class="sxs-lookup"><span data-stu-id="39ff5-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="39ff5-125">Uw doelgroep exporteren</span><span class="sxs-lookup"><span data-stu-id="39ff5-125">Export your target audience</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="39ff5-126">Een verbinding configureren</span><span class="sxs-lookup"><span data-stu-id="39ff5-126">Configure a connection</span></span>

<span data-ttu-id="39ff5-127">Nu onze doelgroep is geïdentificeerd, kunnen we de export van doelgroepinzichten naar een Azure Blob Storage-account configureren.</span><span class="sxs-lookup"><span data-stu-id="39ff5-127">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="39ff5-128">Ga in doelgroepinzichten naar **Beheerder** > **Verbindingen**.</span><span class="sxs-lookup"><span data-stu-id="39ff5-128">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="39ff5-129">Selecteer **Verbinding toevoegen** en kies **Adobe Campaign** om de verbinding te configureren of selecteer **Instellen** op de **Adobe Campaign**-tegel</span><span class="sxs-lookup"><span data-stu-id="39ff5-129">Select **Add connection** and choose **Adobe Campaign** to configure the connection or select **Set up** in the **Adobe Campaign** tile</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Configuratietegel voor Adobe Campaign Standard.":::

1. <span data-ttu-id="39ff5-131">Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="39ff5-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="39ff5-132">De naam en het type verbinding beschrijven deze verbinding.</span><span class="sxs-lookup"><span data-stu-id="39ff5-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="39ff5-133">We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.</span><span class="sxs-lookup"><span data-stu-id="39ff5-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="39ff5-134">Kies wie deze verbinding kan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="39ff5-134">Choose who can use this connection.</span></span> <span data-ttu-id="39ff5-135">Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling.</span><span class="sxs-lookup"><span data-stu-id="39ff5-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="39ff5-136">Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="39ff5-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="39ff5-137">Voer een waarde in de velden **Gebruikersnaam**, **Accountsleutel** en **Container** in van het Azure Blob Storage-account waarnaar u het segment wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="39ff5-137">Enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Schermopname van de opslagaccountconfiguratie. "::: 

   - <span data-ttu-id="39ff5-139">Zie voor meer informatie over het vinden van de naam en de accountsleutel van uw Azure-blobopslagaccount [Opslagaccountinstellingen beheren in de Azure-portal](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="39ff5-139">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="39ff5-140">Zie voor meer informatie over het maken van een container [Een container maken](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="39ff5-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="39ff5-141">Selecteer **Opslaan** om de verbinding te voltooien.</span><span class="sxs-lookup"><span data-stu-id="39ff5-141">Select **Save** to complete the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="39ff5-142">Een export configureren</span><span class="sxs-lookup"><span data-stu-id="39ff5-142">Configure an export</span></span>

<span data-ttu-id="39ff5-143">U kunt deze export configureren als u toegang hebt tot een verbinding van dit type.</span><span class="sxs-lookup"><span data-stu-id="39ff5-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="39ff5-144">Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="39ff5-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="39ff5-145">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="39ff5-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="39ff5-146">Selecteer **Export toevoegen** om een nieuwe export te maken.</span><span class="sxs-lookup"><span data-stu-id="39ff5-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="39ff5-147">Kies in het veld **Verbinding voor export** een verbinding uit de sectie Adobe Campaign.</span><span class="sxs-lookup"><span data-stu-id="39ff5-147">In the **Connection for export** field, choose a connection from the Adobe Campaign section.</span></span> <span data-ttu-id="39ff5-148">Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="39ff5-148">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="39ff5-149">Sluit het segment dat u u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="39ff5-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="39ff5-150">In dit voorbeeld is het **ChurnProneCustomers**​.</span><span class="sxs-lookup"><span data-stu-id="39ff5-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Schermopname van de gebruikersinterface voor segmentselectie met het segment ChurnProneCustomers geselecteerd.":::

1. <span data-ttu-id="39ff5-152">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="39ff5-152">Select **Next**.</span></span>

1. <span data-ttu-id="39ff5-153">Nu wijzen we de velden **Bron** van het segment voor doelgroepinzichten toe aan de veldnamen **Doel** in het Adobe Campaign Standard-profielschema.</span><span class="sxs-lookup"><span data-stu-id="39ff5-153">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Veldtoewijzing voor de Adobe Campaign Standard-connector.":::

   <span data-ttu-id="39ff5-155">Als u meer kenmerken wilt toevoegen, selecteert u **Kenmerk toevoegen**​.</span><span class="sxs-lookup"><span data-stu-id="39ff5-155">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="39ff5-156">De doelnaam kan afwijken van de naam van het bronveld, zodat u nog steeds segmentuitvoer van doelgroepinzichten aan Adobe Campaign Standard kan toewijzen als de velden niet dezelfde naam hebben in de twee systemen.</span><span class="sxs-lookup"><span data-stu-id="39ff5-156">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="39ff5-157">E-mailadres wordt gebruikt als identiteitsveld, maar u kunt elke andere id uit uw klantprofiel voor doelgroepinzichten gebruiken om gegevens toe te wijzen aan Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="39ff5-157">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="39ff5-158">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="39ff5-158">Select **Save**.</span></span>

<span data-ttu-id="39ff5-159">Nadat u de exportbestemming hebt opgeslagen, vindt u deze onder **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="39ff5-159">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="39ff5-160">U kunt [het segment nu op aanvraag exporteren](export-destinations.md#run-exports-on-demand)​.</span><span class="sxs-lookup"><span data-stu-id="39ff5-160">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="39ff5-161">De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md).</span><span class="sxs-lookup"><span data-stu-id="39ff5-161">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="39ff5-162">Zorg ervoor dat het aantal records in het geëxporteerde segment binnen de toegestane limiet van uw Adobe Campaign Standard-licentie valt.</span><span class="sxs-lookup"><span data-stu-id="39ff5-162">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="39ff5-163">Geëxporteerde gegevens worden opgeslagen in de Azure Blob-opslagcontainer die u eerder hebt geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="39ff5-163">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="39ff5-164">Het volgende mappad wordt automatisch gemaakt in uw container:</span><span class="sxs-lookup"><span data-stu-id="39ff5-164">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="39ff5-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="39ff5-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="39ff5-166">Voorbeeld: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="39ff5-166">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="39ff5-167">Adobe Campaign Standard configureren</span><span class="sxs-lookup"><span data-stu-id="39ff5-167">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="39ff5-168">Wanneer een segment uit doelgroepinzichten wordt geëxporteerd, bevat het de kolommen die u hebt geselecteerd tijdens het definiëren van de exportbestemming in de vorige stap.</span><span class="sxs-lookup"><span data-stu-id="39ff5-168">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="39ff5-169">Deze gegevens kunnen worden gebruikt om [profielen te maken in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles)​.</span><span class="sxs-lookup"><span data-stu-id="39ff5-169">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="39ff5-170">Om het segment in Adobe Campaign Standard te gebruiken, moeten we het profielschema in Adobe Campaign Standard uitbreiden met twee extra velden.</span><span class="sxs-lookup"><span data-stu-id="39ff5-170">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="39ff5-171">Lees hoe u de [profielresource uitbreidt](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) met nieuwe velden in Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="39ff5-171">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="39ff5-172">In ons voorbeeld zijn dit de velden *Segmentnaam en Segmentdatum (optioneel)*.</span><span class="sxs-lookup"><span data-stu-id="39ff5-172">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="39ff5-173">We gebruiken deze velden om de profielen in Adobe Campaign Standard te identificeren waarop we ons voor deze campagne willen richten.</span><span class="sxs-lookup"><span data-stu-id="39ff5-173">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="39ff5-174">Als er geen andere records in Adobe Campaign Standard zijn, behalve de records die u gaat importeren, kunt u deze stap overslaan.</span><span class="sxs-lookup"><span data-stu-id="39ff5-174">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="39ff5-175">Gegevens importeren in Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="39ff5-175">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="39ff5-176">Nu aan alle voorwaarden is voldaan, moeten we de voorbereide doelgroepgegevens van doelgroepinzichten importeren in Adobe Campaign Standard om profielen te maken.</span><span class="sxs-lookup"><span data-stu-id="39ff5-176">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="39ff5-177">Lees [hoe u profielen importeert in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) met behulp van een werkstroom.</span><span class="sxs-lookup"><span data-stu-id="39ff5-177">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="39ff5-178">De importwerkstroom in de onderstaande afbeelding is geconfigureerd om elke acht uur te worden uitgevoerd en zoekt naar geëxporteerde segmenten voor doelgroepinzichten (CSV-bestand in Azure Blob Storage).</span><span class="sxs-lookup"><span data-stu-id="39ff5-178">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="39ff5-179">De werkstroom extraheert de inhoud van het CSV-bestand in een opgegeven kolomvolgorde.</span><span class="sxs-lookup"><span data-stu-id="39ff5-179">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="39ff5-180">Deze werkstroom is ontwikkeld om elementaire foutafhandeling uit te voeren en ervoor te zorgen dat elke record een e-mailadres heeft voordat de gegevens in Adobe Campaign Standard worden gehydrateerd.</span><span class="sxs-lookup"><span data-stu-id="39ff5-180">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="39ff5-181">De werkstroom extraheert ook de segmentnaam uit de bestandsnaam voordat deze wordt omgezet in ACS-profielgegevens.</span><span class="sxs-lookup"><span data-stu-id="39ff5-181">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Schermopname van een importwerkstroom in de Adobe Campaign Standard-gebruikersinterface.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="39ff5-183">De doelgroep ophalen in Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="39ff5-183">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="39ff5-184">Zodra de gegevens zijn geïmporteerd in Adobe Campaign Standard, kunt u [een werkstroom maken](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) en [query's](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) op de klanten uitvoeren op basis van de *segmentnaam* en *segmentdatum* om profielen te selecteren die zijn geïdentificeerd voor onze voorbeeldcampagne.</span><span class="sxs-lookup"><span data-stu-id="39ff5-184">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="39ff5-185">De e-mail maken en verzenden met Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="39ff5-185">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="39ff5-186">Maak de e-mailinhoud en [test en verzend](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) vervolgens uw e-mail.</span><span class="sxs-lookup"><span data-stu-id="39ff5-186">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Voorbeeld van e-mail met verlengingsaanbieding van Adobe Campaign Standard.":::
