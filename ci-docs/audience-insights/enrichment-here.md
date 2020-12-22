---
title: Verrijking van de verrijking door derden van HERE Technologies
description: Algemene informatie over de verrijking door derden van HERE Technologies.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668672"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="771cd-103">Verrijking van klantprofielen met HERE Technologies (preview)</span><span class="sxs-lookup"><span data-stu-id="771cd-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="771cd-104">HERE Technologies is een locatieplatformbedrijf dat locatiegerichte gegevens en services levert.</span><span class="sxs-lookup"><span data-stu-id="771cd-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="771cd-105">Met de gegevensverrijkingsservices van HERE Technologies kunt u een nauwkeuriger locatie-inzicht van uw klanten opbouwen met adresnormalisatie, extractie van breedtegraad en lengtegraad en meer.</span><span class="sxs-lookup"><span data-stu-id="771cd-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="771cd-106">Vereisten</span><span class="sxs-lookup"><span data-stu-id="771cd-106">Prerequisites</span></span>

<span data-ttu-id="771cd-107">Om HERE Technologies-verrijkingen te configureren, moet aan de volgende voorwaarden worden voldaan:</span><span class="sxs-lookup"><span data-stu-id="771cd-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="771cd-108">U moet een actief abonnement hebben voor HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="771cd-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="771cd-109">Om een abonnement te nemen, kunt u [hier registreren](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) of rechtstreeks [contact opnemen met HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="771cd-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="771cd-110">Meer informatie over locatieverrijking door HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="771cd-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="771cd-111">U hebt de HERE Technologies API-sleutel.</span><span class="sxs-lookup"><span data-stu-id="771cd-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="771cd-112">U hebt [Beheerders](permissions.md#administrator)machtigingen.</span><span class="sxs-lookup"><span data-stu-id="771cd-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="771cd-113">Configuratie</span><span class="sxs-lookup"><span data-stu-id="771cd-113">Configuration</span></span>

1. <span data-ttu-id="771cd-114">Ga naar **Gegevens** > **Verrijking**.</span><span class="sxs-lookup"><span data-stu-id="771cd-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="771cd-115">Selecteer **Mijn gegevens verrijken** op de HERE Technologies-tegel.</span><span class="sxs-lookup"><span data-stu-id="771cd-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="771cd-116">![HERE Technologies-tegel](media/HERE-tile.png "HERE Technologies-tegel")</span><span class="sxs-lookup"><span data-stu-id="771cd-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="771cd-117">Voer een actieve **HERE Technologies API-sleutel** in.</span><span class="sxs-lookup"><span data-stu-id="771cd-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="771cd-118">Bekijk en geef toestemming voor **Gegevensprivacy en naleving** door het selectievakje **Ik ga akkoord** in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="771cd-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="771cd-119">Bevestig de invoer door **Verbinden met HERE** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="771cd-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1. <span data-ttu-id="771cd-120">Selecteer **Gegevens toevoegen** en kies of u velden aan het primaire en/of secundaire adres wilt toewijzen.</span><span class="sxs-lookup"><span data-stu-id="771cd-120">Select **Add data** and choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="771cd-121">U kunt voor beide adressen een veldtoewijzing specificeren (bijvoorbeeld een privé- en een werkadres) en de profielen voor beide adressen afzonderlijk verrijken.</span><span class="sxs-lookup"><span data-stu-id="771cd-121">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="771cd-122">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="771cd-122">Select **Next**.</span></span>

1. <span data-ttu-id="771cd-123">Definieer welke velden van uw geharmoniseerde profielen moeten worden gebruikt om te zoeken naar overeenkomende locatiegegevens van HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="771cd-123">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="771cd-124">De velden **Straat 1** en **Postcode** zijn vereist voor het geselecteerde primaire en/of secundaire adres.</span><span class="sxs-lookup"><span data-stu-id="771cd-124">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="771cd-125">Voor een hogere matchnauwkeurigheid kunnen meer velden worden toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="771cd-125">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="771cd-126">![Configuratiepagina voor verrijking van HERE Technologies](media/enrichment-HERE-configuration.png "Configuratiepagina voor verrijking van HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="771cd-126">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="771cd-127">Selecteer **Toepassen** om de veldtoewijzing te voltooien.</span><span class="sxs-lookup"><span data-stu-id="771cd-127">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="771cd-128">Verrijkingsresultaten</span><span class="sxs-lookup"><span data-stu-id="771cd-128">Enrichment results</span></span>

<span data-ttu-id="771cd-129">Selecteer **Uitvoeren** vanaf de opdrachtbalk om het verrijkingsproces te starten.</span><span class="sxs-lookup"><span data-stu-id="771cd-129">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="771cd-130">U kunt de verrijking ook automatisch laten uitvoeren als onderdeel van een [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="771cd-130">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="771cd-131">De verwerkingstijd is afhankelijk van de grootte van uw klantgegevens en de API-responstijden van HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="771cd-131">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="771cd-132">Nadat het verrijkingsproces is voltooid, kunt u de nieuwe verrijkte klantprofielgegevens bekijken onder **Mijn verrijkingen**.</span><span class="sxs-lookup"><span data-stu-id="771cd-132">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="771cd-133">Ook vindt u daar het tijdstip van de laatste update en het aantal verrijkte profielen.</span><span class="sxs-lookup"><span data-stu-id="771cd-133">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="771cd-134">U kunt een gedetailleerd overzicht van elk verrijkt profiel openen door **Verrijkte gegevens weergeven** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="771cd-134">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="771cd-135">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="771cd-135">Next steps</span></span>

<span data-ttu-id="771cd-136">Bouw voort op uw verrijkte klantgegevens.</span><span class="sxs-lookup"><span data-stu-id="771cd-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="771cd-137">Maak [segmenten](segments.md), [metingen](measures.md) en [exporteer de gegevens](export-destinations.md) om uw klanten gepersonaliseerde ervaringen te bieden.</span><span class="sxs-lookup"><span data-stu-id="771cd-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="771cd-138">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="771cd-138">Data privacy and compliance</span></span>

<span data-ttu-id="771cd-139">Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar HERE Technologies te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="771cd-139">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="771cd-140">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat HERE Technologies voldoet aan uw privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="771cd-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="771cd-141">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="771cd-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="771cd-142">Uw Dynamics 365 Customer Insights-beheerder kan deze verrijking op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="771cd-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
