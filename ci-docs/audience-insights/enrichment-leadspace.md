---
title: Verrijking van bedrijfsprofielen met de verrijking door derden van Leadspace
description: Algemene informatie over de verrijking door derden van Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0496d10c994cd077a778a6e745e3774e316765ae
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305196"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="d3951-103">Verrijking van bedrijfsprofielen met Leadspace (preview)</span><span class="sxs-lookup"><span data-stu-id="d3951-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="d3951-104">Leadspace is een data science-bedrijf dat een B2B-platform voor klantgegevens biedt.</span><span class="sxs-lookup"><span data-stu-id="d3951-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="d3951-105">Het stelt klanten met geharmoniseerde klantprofielen voor bedrijven in staat hun gegevens te verrijken.</span><span class="sxs-lookup"><span data-stu-id="d3951-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="d3951-106">Verrijkingen voegen meer kenmerken toe zoals bedrijfsgrootte, locatie, branche en meer.</span><span class="sxs-lookup"><span data-stu-id="d3951-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d3951-107">Vereisten</span><span class="sxs-lookup"><span data-stu-id="d3951-107">Prerequisites</span></span>

<span data-ttu-id="d3951-108">Als u Leadspace wilt configureren, moet aan de volgende vereisten worden voldaan:</span><span class="sxs-lookup"><span data-stu-id="d3951-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="d3951-109">U hebt een actieve Leadspace-licentie.</span><span class="sxs-lookup"><span data-stu-id="d3951-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="d3951-110">U hebt [geharmoniseerde klantprofielen](customer-profiles.md) voor bedrijven.</span><span class="sxs-lookup"><span data-stu-id="d3951-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="d3951-111">Een Leadspace-verbinding is al geconfigureerd door een beheerder of u hebt [beheerdersmachtigingen](permissions.md#administrator) en de "eeuwigdurende sleutel" (waarnaar wordt verwezen als **Leadspace-token**).</span><span class="sxs-lookup"><span data-stu-id="d3951-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="d3951-112">Neem rechtstreeks contact op met [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) voor details over hun product.</span><span class="sxs-lookup"><span data-stu-id="d3951-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="d3951-113">De verrijking configureren</span><span class="sxs-lookup"><span data-stu-id="d3951-113">Configure the enrichment</span></span>

1. <span data-ttu-id="d3951-114">Ga in doelgroepinzichten naar **Gegevens** > **Verrijking**.</span><span class="sxs-lookup"><span data-stu-id="d3951-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="d3951-115">Selecteer **Mijn gegevens verrijken** op de tegel van Leadspace en selecteer vervolgens **Aan de slag**.</span><span class="sxs-lookup"><span data-stu-id="d3951-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Schermopname van de Leadspace-tegel.":::

1. <span data-ttu-id="d3951-117">Selecteer een [verbinding](connections.md) in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="d3951-117">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="d3951-118">Neem contact op met een beheerder als er geen verbinding beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="d3951-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="d3951-119">Als u een beheerder bent, kunt u een verbinding maken door **Verbinding toevoegen** te selecteren en **Leadspace** te kiezen.</span><span class="sxs-lookup"><span data-stu-id="d3951-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="d3951-120">Selecteer **Verbinding maken met Leadspace** om de verbinding te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="d3951-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="d3951-121">Selecteer **Volgende** en kies de **klantgegevensset** die u wilt verrijken met bedrijfsgegevens van Leadspace.</span><span class="sxs-lookup"><span data-stu-id="d3951-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="d3951-122">U kunt de entiteit **Klant** selecteren om al uw klantprofielen te verrijken of een segmententiteit selecteren om alleen klantprofielen in dat segment te verrijken.</span><span class="sxs-lookup"><span data-stu-id="d3951-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Schermopname bij het kiezen van de klantgegevensset.":::

1. <span data-ttu-id="d3951-124">Selecteer **Volgende** en bepaal welk type velden uit uw geharmoniseerde profielen worden gebruikt om overeenkomende bedrijfsgegevens van Leadspace te zoeken.</span><span class="sxs-lookup"><span data-stu-id="d3951-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="d3951-125">Het veld **Naam van bedrijf** is verplicht.</span><span class="sxs-lookup"><span data-stu-id="d3951-125">The **Name of company** field is required.</span></span> <span data-ttu-id="d3951-126">Voor een hogere matchnauwkeurigheid kunt u maximaal twee andere velden, **Bedrijfswebsite** en **Bedrijfslocatie** toevoegen.</span><span class="sxs-lookup"><span data-stu-id="d3951-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Deelvenster Leadspace-veldtoewijzing.":::

1. <span data-ttu-id="d3951-128">Selecteer **Volgende** om de veldtoewijzing te voltooien.</span><span class="sxs-lookup"><span data-stu-id="d3951-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="d3951-129">Geef een naam op voor de verrijking en selecteer **Verrijking opslaan** na het bekijken van uw keuzes.</span><span class="sxs-lookup"><span data-stu-id="d3951-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="d3951-130">De verbinding configureren voor Leadspace</span><span class="sxs-lookup"><span data-stu-id="d3951-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="d3951-131">U moet een beheerder zijn om verbindingen te kunnen configureren.</span><span class="sxs-lookup"><span data-stu-id="d3951-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="d3951-132">Selecteer **Verbinding toevoegen** bij het configureren van een verrijking *of* ga naar **Beheerder** > **Verbindingen** en selecteer **Instellen** op de Leadspace-tegel.</span><span class="sxs-lookup"><span data-stu-id="d3951-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="d3951-133">Selecteer **Aan de slag**.</span><span class="sxs-lookup"><span data-stu-id="d3951-133">Select **Get Started**.</span></span> 

1. <span data-ttu-id="d3951-134">Voer een naam in voor de verbinding in het vak **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="d3951-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="d3951-135">Geef een geldig Leadspace-token op.</span><span class="sxs-lookup"><span data-stu-id="d3951-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="d3951-136">Bekijk en geef uw toestemming voor **Gegevensprivacy en naleving** door **Ik ga akkoord** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="d3951-136">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="d3951-137">Selecteer **Verifiëren** om de configuratie te valideren.</span><span class="sxs-lookup"><span data-stu-id="d3951-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="d3951-138">Voltooi de verificatie en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d3951-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Configuratiepagina voor Leadspace-verbinding.":::

## <a name="enrichment-results"></a><span data-ttu-id="d3951-140">Verrijkingsresultaten</span><span class="sxs-lookup"><span data-stu-id="d3951-140">Enrichment results</span></span>

<span data-ttu-id="d3951-141">Nadat u de verrijking hebt vernieuwd, kunt u de nieuw verrijkte bedrijfsgegevens bekijken onder [Mijn verrijkingen](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="d3951-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="d3951-142">U kunt het tijdstip van de laatste update en het aantal verrijkte profielen terugvinden.</span><span class="sxs-lookup"><span data-stu-id="d3951-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="d3951-143">U kunt een gedetailleerd overzicht van elk verrijkt profiel openen door **Verrijkte gegevens weergeven** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="d3951-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="d3951-144">Zie [De API's van Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d3951-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d3951-145">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="d3951-145">Next steps</span></span>

<span data-ttu-id="d3951-146">Bouw voort op uw verrijkte klantgegevens.</span><span class="sxs-lookup"><span data-stu-id="d3951-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="d3951-147">Maak [segmenten](segments.md) en [metingen](measures.md), en [exporteer de gegevens](export-destinations.md) zelfs om gepersonaliseerde ervaringen aan uw klanten te leveren.</span><span class="sxs-lookup"><span data-stu-id="d3951-147">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d3951-148">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="d3951-148">Data privacy and compliance</span></span>

<span data-ttu-id="d3951-149">Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar Leadspace te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="d3951-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d3951-150">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat Leadspace voldoet aan uw privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="d3951-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d3951-151">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d3951-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d3951-152">Uw Dynamics 365 Customer Insights-beheerder kan deze verrijking op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="d3951-152">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
