---
title: Verrijking met de verrijking van derden van HERE Technologies
description: Algemene informatie over de verrijking door derden van HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b3c1da0f541efb85b2ca9d87a2e3b97bbfb6ca7f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305288"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="f5ea4-103">Verrijking van klantprofielen met HERE Technologies (preview)</span><span class="sxs-lookup"><span data-stu-id="f5ea4-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="f5ea4-104">HERE Technologies is een locatieplatformbedrijf dat locatiegerichte gegevens en services levert.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="f5ea4-105">Met de gegevensverrijkingsservices van HERE Technologies kunt u een nauwkeuriger locatie-inzicht van uw klanten opbouwen met adresnormalisatie, extractie van breedtegraad en lengtegraad en meer.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f5ea4-106">Vereisten</span><span class="sxs-lookup"><span data-stu-id="f5ea4-106">Prerequisites</span></span>

<span data-ttu-id="f5ea4-107">Om HERE Technologies-verrijkingen te configureren, moet aan de volgende voorwaarden worden voldaan:</span><span class="sxs-lookup"><span data-stu-id="f5ea4-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="f5ea4-108">U moet een actief abonnement hebben voor HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="f5ea4-109">U kunt een abonnement nemen door zich [hier te registreren](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) of rechtstreeks [contact op te nemen met HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="f5ea4-109">To get a subscription, you can [sign up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="f5ea4-110">Meer informatie over locatieverrijking door HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="f5ea4-111">Er is een HERE-[verbinding](connections.md) beschikbaar *of* u hebt [beheerdersmachtigingen](permissions.md#administrator) en de HERE Technologies API-sleutel.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-111">A HERE [connection](connections.md) is available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="f5ea4-112">De verrijking configureren</span><span class="sxs-lookup"><span data-stu-id="f5ea4-112">Configure the enrichment</span></span>

1. <span data-ttu-id="f5ea4-113">Ga naar **Gegevens** > **Verrijking**.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="f5ea4-114">Selecteer **Mijn gegevens verrijken** op de tegel van HERE Technologies en selecteer vervolgens **Aan de slag**.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f5ea4-115">![HERE Technologies-tegel](media/HERE-tile.png "HERE Technologies-tegel")</span><span class="sxs-lookup"><span data-stu-id="f5ea4-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="f5ea4-116">Selecteer een [verbinding](connections.md) in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-116">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="f5ea4-117">Neem contact op met een beheerder als er geen verbinding beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="f5ea4-118">Als u een beheerder bent, kunt u een verbinding maken door **Verbinding toevoegen** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="f5ea4-119">Kies **HERE Technologies** uit de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-119">Choose **HERE Technologies** from the dropdown list.</span></span> 

1. <span data-ttu-id="f5ea4-120">Selecteer **Verbinding maken met HERE Technologies** om de selectie te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="f5ea4-121">Selecteer **Volgende** en kies de **klantgegevensset** die u wilt verrijken met locatie gegevens van HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="f5ea4-122">U kunt de entiteit **Klant** selecteren om al uw klantprofielen te verrijken of een segmententiteit selecteren om alleen klantprofielen in dat segment te verrijken.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Schermopname bij het kiezen van de klantgegevensset.":::

1. <span data-ttu-id="f5ea4-124">Kies of u velden aan het primaire en/of secundaire adres wilt toewijzen.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="f5ea4-125">U kunt voor beide adressen een veldtoewijzing specificeren en de profielen voor beide adressen afzonderlijk verrijken.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="f5ea4-126">Als er bijvoorbeeld een huisadres en een zakelijk adres is.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="f5ea4-127">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-127">Select **Next**.</span></span>

1. <span data-ttu-id="f5ea4-128">Definieer welke velden van uw geharmoniseerde profielen moeten worden gebruikt om te zoeken naar overeenkomende locatiegegevens van HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="f5ea4-129">De velden **Straat 1** en **Postcode** zijn vereist voor het geselecteerde primaire en/of secundaire adres.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="f5ea4-130">Voor een hogere matchnauwkeurigheid kunnen meer velden worden toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f5ea4-131">![Configuratiepagina voor verrijking van HERE Technologies](media/enrichment-HERE-configuration.png "Configuratiepagina voor verrijking van HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="f5ea4-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="f5ea4-132">Selecteer **Volgende** om de veldtoewijzing te voltooien.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="f5ea4-133">Geef een naam op voor de verrijking.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-133">Provide a name for the enrichment.</span></span> 

1. <span data-ttu-id="f5ea4-134">Selecteer **Verrijking opslaan** na het bekijken van uw keuzes.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-134">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="f5ea4-135">De verbinding configureren voor HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="f5ea4-135">Configure the connection for HERE Technologies</span></span> 

<span data-ttu-id="f5ea4-136">U moet een beheerder zijn om verbindingen te kunnen configureren.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="f5ea4-137">Selecteer **Verbinding toevoegen** bij het configureren van een verrijking *of* ga naar **Beheerder** > **Verbindingen** en selecteer **Instellen** op de HERE technologies-tegel.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="f5ea4-138">Voer een naam in voor de verbinding in het vak **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="f5ea4-139">Geef een geldige API-sleutel van HERE Technologies op.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="f5ea4-140">Bekijk en geef uw toestemming voor **Gegevensprivacy en naleving** door **Ik ga akkoord** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-140">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="f5ea4-141">Selecteer **Verifiëren** om de configuratie te valideren.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="f5ea4-142">Voltooi de verificatie en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-142">After completing the verification, select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f5ea4-143">![Configuratiepagina voor HERE technologies-verbinding](media/enrichment-HERE-connection.png "Configuratiepagina voor HERE technologies-verbinding")</span><span class="sxs-lookup"><span data-stu-id="f5ea4-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="f5ea4-144">Verrijkingsresultaten</span><span class="sxs-lookup"><span data-stu-id="f5ea4-144">Enrichment results</span></span>

<span data-ttu-id="f5ea4-145">Selecteer **Uitvoeren** vanaf de opdrachtbalk om het verrijkingsproces te starten.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="f5ea4-146">U kunt de verrijking ook automatisch laten uitvoeren als onderdeel van een [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f5ea4-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f5ea4-147">De verwerkingstijd is afhankelijk van de grootte van uw klantgegevens en de API-responstijden van HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="f5ea4-148">Nadat het verrijkingsproces is voltooid, kunt u de nieuwe verrijkte klantprofielgegevens bekijken onder **Mijn verrijkingen**.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="f5ea4-149">Ook vindt u daar het tijdstip van de laatste update en het aantal verrijkte profielen.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="f5ea4-150">U kunt een gedetailleerd overzicht van elk verrijkt profiel openen door **Verrijkte gegevens weergeven** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f5ea4-151">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="f5ea4-151">Next steps</span></span>

<span data-ttu-id="f5ea4-152">Bouw voort op uw verrijkte klantgegevens.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="f5ea4-153">Maak [segmenten](segments.md) en [metingen](measures.md), en [exporteer de gegevens](export-destinations.md) zelfs om gepersonaliseerde ervaringen aan uw klanten te leveren.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-153">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f5ea4-154">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="f5ea4-154">Data privacy and compliance</span></span>

<span data-ttu-id="f5ea4-155">Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar HERE Technologies te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f5ea4-156">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat HERE Technologies voldoet aan uw privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f5ea4-157">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f5ea4-158">Uw Dynamics 365 Customer Insights-beheerder kan deze verrijking op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="f5ea4-158">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
