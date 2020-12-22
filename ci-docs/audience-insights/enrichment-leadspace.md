---
title: Verrijking van bedrijfsprofielen met de verrijking door derden van Leadspace
description: Algemene informatie over de verrijking door derden van Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668717"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="5ec9f-103">Verrijking van bedrijfsprofielen met Leadspace (preview)</span><span class="sxs-lookup"><span data-stu-id="5ec9f-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="5ec9f-104">Leadspace is een data science-bedrijf dat een B2B-platform voor klantgegevens biedt.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="5ec9f-105">Het stelt klanten met geharmoniseerde klantprofielen voor bedrijven in staat hun gegevens te verrijken.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="5ec9f-106">Verrijkingen zijn onder andere aanvullende kenmerken, zoals bedrijfsgrootte, locatie, branche en meer.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5ec9f-107">Vereisten</span><span class="sxs-lookup"><span data-stu-id="5ec9f-107">Prerequisites</span></span>

<span data-ttu-id="5ec9f-108">Als u Leadspace wilt configureren, moet aan de volgende vereisten worden voldaan:</span><span class="sxs-lookup"><span data-stu-id="5ec9f-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="5ec9f-109">U hebt een actieve Leadspace-licentie en de "permanente sleutel" (ook wel **Leadspace-token** genoemd).</span><span class="sxs-lookup"><span data-stu-id="5ec9f-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="5ec9f-110">Neem rechtstreeks contact op met [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) voor details over hun product.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="5ec9f-111">U hebt [Beheerders](permissions.md#administrator)machtigingen.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="5ec9f-112">U hebt [geharmoniseerde klantprofielen](customer-profiles.md) voor bedrijven.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="5ec9f-113">Configuratie</span><span class="sxs-lookup"><span data-stu-id="5ec9f-113">Configuration</span></span>

1. <span data-ttu-id="5ec9f-114">Ga in doelgroepinzichten naar **Gegevens** > **Verrijking**.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="5ec9f-115">Selecteer **Mijn gegevens verrijken** op de Leadspace-tegel.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Schermopname van de Leadspace-tegel.":::

1. <span data-ttu-id="5ec9f-117">Selecteer **Aan de slag** en voer een actief **Leadspace-token** in (permanente sleutel).</span><span class="sxs-lookup"><span data-stu-id="5ec9f-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="5ec9f-118">Bekijk en geef toestemming voor **Gegevensprivacy en naleving** door het selectievakje **Ik ga akkoord** in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="5ec9f-119">Bevestig de invoer door **Verbinden met Leadspace** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="5ec9f-120">Selecteer **Kaartgegevens** en bepaal welke velden van uw geharmoniseerde profielen moeten worden gebruikt om overeenkomende bedrijfsgegevens van Leadspace te zoeken.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-120">Select **Map data** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="5ec9f-121">Het veld **Naam van bedrijf** is verplicht.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-121">The **Name of company** field is required.</span></span> <span data-ttu-id="5ec9f-122">Voor een hogere matchnauwkeurigheid kunt u maximaal twee andere velden, **Bedrijfswebsite** en **Bedrijfslocatie** toevoegen.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-122">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Deelvenster Leadspace-veldtoewijzing.":::
   
1. <span data-ttu-id="5ec9f-124">Selecteer **Toepassen** om de veldtoewijzing te voltooien.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-124">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="5ec9f-125">Selecteer **Uitvoeren** om de bedrijfsprofielen te verrijken.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-125">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="5ec9f-126">Hoe lang een verrijking duurt, hangt af van het aantal geharmoniseerde klantprofielen.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-126">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="5ec9f-127">Verrijkingsresultaten</span><span class="sxs-lookup"><span data-stu-id="5ec9f-127">Enrichment results</span></span>

<span data-ttu-id="5ec9f-128">Nadat u de verrijking hebt vernieuwd, kunt u de nieuw verrijkte bedrijfsgegevens bekijken onder [Mijn verrijkingen](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="5ec9f-128">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="5ec9f-129">U kunt het tijdstip van de laatste update en het aantal verrijkte profielen terugvinden.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-129">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="5ec9f-130">U kunt een gedetailleerd overzicht van elk verrijkt profiel openen door **Verrijkte gegevens weergeven** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-130">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="5ec9f-131">Zie [De API's van Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-131">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="5ec9f-132">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="5ec9f-132">Next steps</span></span>

<span data-ttu-id="5ec9f-133">Bouw voort op uw verrijkte klantgegevens.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-133">Build on top of your enriched customer data.</span></span> <span data-ttu-id="5ec9f-134">Maak [segmenten](segments.md), [metingen](measures.md) en [exporteer de gegevens](export-destinations.md) om uw klanten gepersonaliseerde ervaringen te bieden.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-134">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5ec9f-135">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="5ec9f-135">Data privacy and compliance</span></span>

<span data-ttu-id="5ec9f-136">Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar Leadspace te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-136">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5ec9f-137">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat Leadspace voldoet aan uw privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="5ec9f-138">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="5ec9f-139">Uw Dynamics 365 Customer Insights-beheerder kan deze verrijking op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-139">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>