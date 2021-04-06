---
title: Customer Insights-gegevens naar Adobe Experience Platform exporteren
description: Ontdek hoe u segmenten voor doelgroepinzichten gebruikt in Adobe Experience Platform.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596263"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="9525c-103">Customer Insights-segmenten gebruiken in Adobe Experience Platform (preview)</span><span class="sxs-lookup"><span data-stu-id="9525c-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="9525c-104">Als gebruiker van doelgroepinzichten voor Dynamics 365 Customer Insights hebt u mogelijk segmenten gemaakt om uw marketingcampagnes efficiënter te maken door u op relevante doelgroepen te richten.</span><span class="sxs-lookup"><span data-stu-id="9525c-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="9525c-105">Als u een segment uit doelgroepinzichten in Adobe Experience Platform en toepassingen zoals Adobe Campaign Standard wilt gebruiken, moet u een paar stappen volgen die in dit artikel worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="9525c-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Procesdiagram van de stappen die in dit artikel worden beschreven.":::

## <a name="prerequisites"></a><span data-ttu-id="9525c-107">Vereisten</span><span class="sxs-lookup"><span data-stu-id="9525c-107">Prerequisites</span></span>

-   <span data-ttu-id="9525c-108">Dynamics 365 Customer Insights-licentie</span><span class="sxs-lookup"><span data-stu-id="9525c-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="9525c-109">Adobe Experience Platform-licentie</span><span class="sxs-lookup"><span data-stu-id="9525c-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="9525c-110">Adobe Campaign Standard-licentie</span><span class="sxs-lookup"><span data-stu-id="9525c-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="9525c-111">Azure Blob Storage-account</span><span class="sxs-lookup"><span data-stu-id="9525c-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="9525c-112">Campagne-overzicht</span><span class="sxs-lookup"><span data-stu-id="9525c-112">Campaign Overview</span></span>

<span data-ttu-id="9525c-113">Laten we eens kijken naar een fictieve voorbeeldcampagne om beter te begrijpen hoe u segmenten uit doelgroepinzichten in Adobe Experience Platform kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="9525c-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="9525c-114">Laten we aannemen dat uw bedrijf een maandelijkse, op abonnementen gebaseerde service biedt aan uw klanten in de Verenigde Staten.</span><span class="sxs-lookup"><span data-stu-id="9525c-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="9525c-115">U wilt klanten identificeren waarvan het abonnement binnen acht dagen moet worden verlengd, maar die hun abonnement nog niet hebben verlengd.</span><span class="sxs-lookup"><span data-stu-id="9525c-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="9525c-116">Om deze klanten te behouden, wilt u ze een promotieaanbieding sturen via e-mail, met Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="9525c-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="9525c-117">In dit voorbeeld willen we de promotionele e-mailcampagne één keer uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="9525c-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="9525c-118">In dit artikel wordt niet het gebruiksscenario behandeld waarin de campagne meerdere keer wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="9525c-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="9525c-119">Uw doelgroep identificeren</span><span class="sxs-lookup"><span data-stu-id="9525c-119">Identify your target audience</span></span>

<span data-ttu-id="9525c-120">In ons scenario gaan we ervan uit dat de e-mailadressen van de klanten beschikbaar zijn in doelgroepinzichten en dat hun promotievoorkeuren zijn geanalyseerd om leden van het segment te identificeren.</span><span class="sxs-lookup"><span data-stu-id="9525c-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="9525c-121">Het [segment dat u hebt gedefinieerd in doelgroepinzichten](segments.md) wordt **ChurnProneCustomers** genoemd en u bent van plan deze klanten de e-mailpromotie te sturen.</span><span class="sxs-lookup"><span data-stu-id="9525c-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Schermopname van de pagina Segmenten met het gemaakte segment ChurnProneCustomers.":::

<span data-ttu-id="9525c-123">De aanbiedings-e-mail die u wilt verzenden, bevat de voornaam, achternaam en einddatum van het abonnement van de klant.</span><span class="sxs-lookup"><span data-stu-id="9525c-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="9525c-124">Klanten worden geïnformeerd over de korting die ze krijgen als ze hun abonnement verlengen voordat het afloopt.</span><span class="sxs-lookup"><span data-stu-id="9525c-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="9525c-125">Uw doelgroep exporteren</span><span class="sxs-lookup"><span data-stu-id="9525c-125">Export your target audience</span></span>

<span data-ttu-id="9525c-126">Nu onze doelgroep is geïdentificeerd, kunnen we de export van doelgroepinzichten naar een Azure Blob Storage-account configureren.</span><span class="sxs-lookup"><span data-stu-id="9525c-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="9525c-127">Ga in doelgroepinzichten naar **Beheer** > **Exportbestemmingen**.</span><span class="sxs-lookup"><span data-stu-id="9525c-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="9525c-128">Selecteer **Instellen** in de tegel **Azure Blob Storage**​.</span><span class="sxs-lookup"><span data-stu-id="9525c-128">In the **Azure Blob Storage** tile, select **Set up**.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Configuratietegel voor Azure Blob Storage.":::

1. <span data-ttu-id="9525c-130">Geef een **weergavenaam** voor deze nieuwe exportbestemming op en voer vervolgens de **accountnaam**, **accountsleutel** en **container** in van de Azure Blob Storage-account waarnaar u het segment wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="9525c-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Schermopname van de opslagaccountconfiguratie. "::: 

   - <span data-ttu-id="9525c-132">Zie voor meer informatie over het vinden van de naam en de accountsleutel van uw Azure-blobopslagaccount [Opslagaccountinstellingen beheren in de Azure-portal](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="9525c-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="9525c-133">Zie voor meer informatie over het maken van een container [Een container maken](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="9525c-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="9525c-134">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="9525c-134">Select **Next**.</span></span>

1. <span data-ttu-id="9525c-135">Sluit het segment dat u u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="9525c-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="9525c-136">In dit voorbeeld is het **ChurnProneCustomers**​.</span><span class="sxs-lookup"><span data-stu-id="9525c-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Schermopname van de gebruikersinterface voor segmentselectie met het segment ChurnProneCustomers geselecteerd.":::

1. <span data-ttu-id="9525c-138">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="9525c-138">Select **Save**.</span></span>

<span data-ttu-id="9525c-139">Nadat u de exportbestemming hebt opgeslagen, vindt u deze op **Beheer** > **Exports** > **Mijn exportbestemmingen**.</span><span class="sxs-lookup"><span data-stu-id="9525c-139">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Schermopname met een lijst met exports en gemarkeerd voorbeeldsegment.":::

<span data-ttu-id="9525c-141">U kunt [het segment nu op aanvraag exporteren](export-destinations.md#export-data-on-demand)​.</span><span class="sxs-lookup"><span data-stu-id="9525c-141">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="9525c-142">De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md).</span><span class="sxs-lookup"><span data-stu-id="9525c-142">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9525c-143">Zorg ervoor dat het aantal records in het geëxporteerde segment binnen de toegestane limiet van uw Adobe Campaign Standard-licentie valt.</span><span class="sxs-lookup"><span data-stu-id="9525c-143">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="9525c-144">Geëxporteerde gegevens worden opgeslagen in de Azure Blob-opslagcontainer die u eerder hebt geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="9525c-144">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="9525c-145">Het volgende mappad wordt automatisch gemaakt in uw container:</span><span class="sxs-lookup"><span data-stu-id="9525c-145">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="9525c-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="9525c-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="9525c-147">Voorbeeld: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="9525c-147">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="9525c-148">De *model.json* voor de geëxporteerde entiteiten bevindt zich op het niveau *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="9525c-148">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="9525c-149">Voorbeeld: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="9525c-149">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="9525c-150">XDM (Experience Data Model) definiëren in Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="9525c-150">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="9525c-151">Voordat de geëxporteerde gegevens uit doelgroepinzichten kunnen worden gebruikt in Adobe Experience Platform, moeten we het Experience Data Model-schema definiëren en [de gegevens voor het realtime klantprofiel configureren](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials)​.</span><span class="sxs-lookup"><span data-stu-id="9525c-151">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="9525c-152">Leer [wat XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) en begrijp de [basisprincipes van schemasamenstelling](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="9525c-152">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="9525c-153">Gegevens importeren in Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="9525c-153">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="9525c-154">Nu aan alle voorwaarden is voldaan, moeten we de voorbereide doelgroepgegevens van doelgroepinzichten importeren in Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="9525c-154">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="9525c-155">Maak eerst [een Azure Blob Storage-bronverbinding](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started)​.</span><span class="sxs-lookup"><span data-stu-id="9525c-155">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="9525c-156">Na het definiëren van de bronverbinding [configureert u een gegevensstroom](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) voor een batchverbinding met cloudopslag om de segmentuitvoer uit doelgroepinzichten te importeren in Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="9525c-156">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="9525c-157">Een doelgroep maken in Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="9525c-157">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="9525c-158">We gebruiken Adobe Campaign Standard om de e-mail voor deze campagne te verzenden.</span><span class="sxs-lookup"><span data-stu-id="9525c-158">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="9525c-159">Nadat we de gegevens in Adobe Experience Platform hebben geïmporteerd, moeten we [een doelgroep maken](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard met de gegevens in Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="9525c-159">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="9525c-160">Leer hoe u de [functie voor het maken van segmenten gebruikt](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard om een doelgroep te definiëren op basis van de gegevens in Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="9525c-160">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="9525c-161">De e-mail maken en verzenden met Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="9525c-161">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="9525c-162">Maak de e-mailinhoud en [test en verzend](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) vervolgens uw e-mail.</span><span class="sxs-lookup"><span data-stu-id="9525c-162">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Voorbeeld van e-mail met verlengingsaanbieding van Adobe Campaign Standard.":::