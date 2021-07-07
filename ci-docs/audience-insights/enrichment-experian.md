---
title: Verrijking met de verrijking van derden Experian
description: Algemene informatie over de verrijking van derden Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309814"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="48577-103">Klantprofielen verrijken met demografische gegevens van Experian (preview)</span><span class="sxs-lookup"><span data-stu-id="48577-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="48577-104">Experian is een wereldleider op het gebied van kredietrapportage en marketingdiensten voor consumenten en bedrijven.</span><span class="sxs-lookup"><span data-stu-id="48577-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="48577-105">Met de dataverrijkingsdiensten van Experian kunt u een dieper inzicht in uw klanten opbouwen door uw klantprofielen te verrijken met demografische gegevens zoals de grootte van het huishouden, inkomen en meer.</span><span class="sxs-lookup"><span data-stu-id="48577-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="48577-106">Vereisten</span><span class="sxs-lookup"><span data-stu-id="48577-106">Prerequisites</span></span>

<span data-ttu-id="48577-107">Als u Experian wilt configureren, moet aan de volgende vereisten worden voldaan:</span><span class="sxs-lookup"><span data-stu-id="48577-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="48577-108">U moet een actief abonnement hebben voor Experian.</span><span class="sxs-lookup"><span data-stu-id="48577-108">You have an active Experian subscription.</span></span> <span data-ttu-id="48577-109">U kunt een abonnement nemen door rechtstreeks [contact op te nemen met Experian](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="48577-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="48577-110">[Kom meer te weten over gegevensverrijking met Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="48577-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="48577-111">Er is al een Experian-verbinding geconfigureerd door een beheerder *of* u hebt [beheerdersmachtigingen](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="48577-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="48577-112">U hebt ook de gebruikers-id, de partij-id en het modelnummer nodig voor uw ST-account (Secure Transport) met SSH-ondersteuning dat Experian voor u heeft gemaakt.</span><span class="sxs-lookup"><span data-stu-id="48577-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="48577-113">Ondersteunde landen/regio's</span><span class="sxs-lookup"><span data-stu-id="48577-113">Supported countries/regions</span></span>

<span data-ttu-id="48577-114">We ondersteunen momenteel alleen het verrijken van klantprofielen in de Verenigde Staten.</span><span class="sxs-lookup"><span data-stu-id="48577-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="48577-115">De verrijking configureren</span><span class="sxs-lookup"><span data-stu-id="48577-115">Configure the enrichment</span></span>

1. <span data-ttu-id="48577-116">Ga naar **Gegevens** > **Verrijking** en selecteer het tabblad **Detecteren**.</span><span class="sxs-lookup"><span data-stu-id="48577-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="48577-117">Selecteer **Mijn gegevens verrijken** op de Experian-tegel.</span><span class="sxs-lookup"><span data-stu-id="48577-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="48577-118">![Experian gaan](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="48577-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="48577-119">Selecteer een [verbinding](connections.md) in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="48577-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="48577-120">Neem contact op met een beheerder als er geen verbinding beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="48577-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="48577-121">Als u een beheerder bent, kunt u een verbinding maken door **Verbinding toevoegen** te selecteren en Experian te kiezen in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="48577-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="48577-122">Selecteer **Verbinden met Experian** om de verbindingsselectie te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="48577-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="48577-123">Selecteer **Volgende** en kies de **klantgegevensset** die u wilt verrijken met demografische gegevens van Experian.</span><span class="sxs-lookup"><span data-stu-id="48577-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="48577-124">U kunt de entiteit **Klant** selecteren om al uw klantprofielen te verrijken of een segmententiteit selecteren om alleen klantprofielen in dat segment te verrijken.</span><span class="sxs-lookup"><span data-stu-id="48577-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Schermopname bij het kiezen van de klantgegevensset.":::

1. <span data-ttu-id="48577-126">Selecteer **Volgende** en definieer welk type velden uit uw geharmoniseerde profielen moeten worden gebruikt om te zoeken naar overeenkomende demografische gegevens van Experian.</span><span class="sxs-lookup"><span data-stu-id="48577-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="48577-127">Ten minste één van de velden **Naam en adres**, **Telefoon** of **E-mail** is vereist.</span><span class="sxs-lookup"><span data-stu-id="48577-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="48577-128">Voor een hogere nauwkeurigheid bij de afstemming kunnen maximaal twee andere velden worden toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="48577-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="48577-129">Deze selectie heeft invloed op de toewijzingsvelden waartoe u in de volgende stap toegang hebt.</span><span class="sxs-lookup"><span data-stu-id="48577-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="48577-130">Als meer sleutel-id-kenmerken naar Experian worden verzonden, levert dit waarschijnlijk een hoger matchpercentage op.</span><span class="sxs-lookup"><span data-stu-id="48577-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="48577-131">Selecteer **Volgende** om de veldtoewijzing te starten.</span><span class="sxs-lookup"><span data-stu-id="48577-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="48577-132">Definieer welke velden uit uw geharmoniseerde profielen moeten worden gebruikt om te zoeken naar overeenkomende demografische gegevens van Experian.</span><span class="sxs-lookup"><span data-stu-id="48577-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="48577-133">Vereiste velden zijn gemarkeerd.</span><span class="sxs-lookup"><span data-stu-id="48577-133">Required fields are marked.</span></span>

1. <span data-ttu-id="48577-134">Geef een naam op voor de verrijking en een naam voor de uitvoerentiteit.</span><span class="sxs-lookup"><span data-stu-id="48577-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="48577-135">Selecteer **Verrijking opslaan** na het bekijken van uw keuzes.</span><span class="sxs-lookup"><span data-stu-id="48577-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="48577-136">De verbinding configureren voor Experian</span><span class="sxs-lookup"><span data-stu-id="48577-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="48577-137">U moet een beheerder zijn om verbindingen te kunnen configureren.</span><span class="sxs-lookup"><span data-stu-id="48577-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="48577-138">Selecteer **Verbinding toevoegen** bij het configureren van een verrijking *of* ga naar **Beheerder** > **Verbindingen** en selecteer **Instellen** op de Experian-tegel.</span><span class="sxs-lookup"><span data-stu-id="48577-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="48577-139">Selecteer **Aan de slag**.</span><span class="sxs-lookup"><span data-stu-id="48577-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="48577-140">Voer een naam in voor de verbinding in het vak **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="48577-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="48577-141">Voer een geldige gebruikers-id, partij-id en modelnummer in voor uw Experian Secure Transport-account.</span><span class="sxs-lookup"><span data-stu-id="48577-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="48577-142">Bekijk en geef uw toestemming voor **Gegevensprivacy en naleving** door **Ik ga akkoord** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="48577-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="48577-143">Selecteer **Verifiëren** om de configuratie te valideren.</span><span class="sxs-lookup"><span data-stu-id="48577-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="48577-144">Voltooi de verificatie en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="48577-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian-verbindingsconfiguratievenster.":::

## <a name="enrichment-results"></a><span data-ttu-id="48577-146">Verrijkingsresultaten</span><span class="sxs-lookup"><span data-stu-id="48577-146">Enrichment results</span></span>

<span data-ttu-id="48577-147">Selecteer **Uitvoeren** vanaf de opdrachtbalk om het verrijkingsproces te starten.</span><span class="sxs-lookup"><span data-stu-id="48577-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="48577-148">U kunt de verrijking ook automatisch laten uitvoeren als onderdeel van een [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="48577-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="48577-149">De verwerkingstijd is afhankelijk van de omvang van uw klantgegevens en de verrijkingsprocessen die voor uw account zijn ingesteld door Experian.</span><span class="sxs-lookup"><span data-stu-id="48577-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="48577-150">Nadat het verrijkingsproces is voltooid, kunt u de nieuwe verrijkte klantprofielgegevens bekijken onder **Mijn verrijkingen**.</span><span class="sxs-lookup"><span data-stu-id="48577-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="48577-151">Ook vindt u daar het tijdstip van de laatste update en het aantal verrijkte profielen.</span><span class="sxs-lookup"><span data-stu-id="48577-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="48577-152">U kunt een gedetailleerd overzicht van elk verrijkt profiel openen door **Verrijkte gegevens weergeven** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="48577-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="48577-153">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="48577-153">Next steps</span></span>

<span data-ttu-id="48577-154">Bouw voort op uw verrijkte klantgegevens.</span><span class="sxs-lookup"><span data-stu-id="48577-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="48577-155">Maak [segmenten](segments.md) en [metingen](measures.md), en [exporteer de gegevens](export-destinations.md) zelfs om gepersonaliseerde ervaringen aan uw klanten te leveren.</span><span class="sxs-lookup"><span data-stu-id="48577-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="48577-156">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="48577-156">Data privacy and compliance</span></span>

<span data-ttu-id="48577-157">Wanneer u Dynamics 365 Customer Insights inschakelt om gegevens te verzenden naar Experian, staat u de overdracht van gegevens buiten de nalevingsgrens toe voor Dynamics 365 Customer Insights, inclusief mogelijk gevoelige gegevens zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="48577-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="48577-158">Microsoft zal dergelijke gegevens in uw opdracht overdragen, maar u bent er zelf verantwoordelijk voor dat Experian voldoet aan alle privacy- of beveiligingsverplichtingen die u hebt.</span><span class="sxs-lookup"><span data-stu-id="48577-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="48577-159">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="48577-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="48577-160">Uw Dynamics 365 Customer Insights-beheerder kan deze verrijking op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="48577-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
