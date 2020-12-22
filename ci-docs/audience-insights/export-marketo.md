---
title: Customer Insights-gegevens exporteren naar Marketo
description: Ontdek hoe u de verbinding met Marketo configureert.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34ccee2894f1f2b552d0c6a88a6810e2dfc677a3
ms.sourcegitcommit: 0b1d3ca11b8ba362a959da0eea15c37e9cdba084
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/18/2020
ms.locfileid: "4570397"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="1d69b-103">Connector voor Marketo (preview)</span><span class="sxs-lookup"><span data-stu-id="1d69b-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="1d69b-104">Exporteer segmenten van geharmoniseerde klantprofielen om campagnes te genereren, e-mailmarketing te bieden en specifieke groepen klanten te gebruiken met Marketo.</span><span class="sxs-lookup"><span data-stu-id="1d69b-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1d69b-105">Vereisten</span><span class="sxs-lookup"><span data-stu-id="1d69b-105">Prerequisites</span></span>

-   <span data-ttu-id="1d69b-106">U hebt een [Marketo-account](https://login.marketo.com/) en bijbehorende beheerdersreferenties nodig.</span><span class="sxs-lookup"><span data-stu-id="1d69b-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="1d69b-107">Er zijn bestaande lijsten met bijbehorende id's in Marketo.</span><span class="sxs-lookup"><span data-stu-id="1d69b-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="1d69b-108">Zie [Marketo-lijsten](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1d69b-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="1d69b-109">U hebt [geconfigureerde segmenten](segments.md).</span><span class="sxs-lookup"><span data-stu-id="1d69b-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="1d69b-110">Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="1d69b-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="1d69b-111">Verbinden met Marketo</span><span class="sxs-lookup"><span data-stu-id="1d69b-111">Connect to Marketo</span></span>

1. <span data-ttu-id="1d69b-112">Ga naar **Beheer** > **Exportbestemmingen**.</span><span class="sxs-lookup"><span data-stu-id="1d69b-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="1d69b-113">Selecteer onder **Marketo** de optie **Instellen**.</span><span class="sxs-lookup"><span data-stu-id="1d69b-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="1d69b-114">Geef uw exportbestemming een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="1d69b-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="1d69b-115">Voer uw **[Marketo-client-id, clientgeheim en REST-eindpunt hostnaam](https://developers.marketo.com/rest-api/authentication/)** in.</span><span class="sxs-lookup"><span data-stu-id="1d69b-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="1d69b-116">Voer uw **[Marketo-lijst-id](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** in</span><span class="sxs-lookup"><span data-stu-id="1d69b-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="1d69b-117">Selecteer **Ik ga akkoord** om de **Gegevensprivacy en naleving** te bevestigen en selecteer **Verbinden** om de verbinding met Marketo te initialiseren.</span><span class="sxs-lookup"><span data-stu-id="1d69b-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="1d69b-118">Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.</span><span class="sxs-lookup"><span data-stu-id="1d69b-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Schermopname voor Marketo-verbinding exporteren":::

1. <span data-ttu-id="1d69b-120">Selecteer **Volgende** om de export te configureren.</span><span class="sxs-lookup"><span data-stu-id="1d69b-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="1d69b-121">De connector configureren</span><span class="sxs-lookup"><span data-stu-id="1d69b-121">Configure the connector</span></span>

1. <span data-ttu-id="1d69b-122">Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant.</span><span class="sxs-lookup"><span data-stu-id="1d69b-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="1d69b-123">Optioneel kunt u **Voornaam**, **Achternaam**, **Woonplaats**, **Staat** en **Land/regio** exporteren als extra velden om meer gepersonaliseerde e-mails te maken.</span><span class="sxs-lookup"><span data-stu-id="1d69b-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="1d69b-124">Selecteer **Kenmerk toevoegen** om deze velden toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="1d69b-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="1d69b-125">Selecteer de segmenten die u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="1d69b-125">Select the segments you want to export.</span></span> <span data-ttu-id="1d69b-126">U kunt in totaal tot 1 miljoen klantprofielen exporteren naar Marketo.</span><span class="sxs-lookup"><span data-stu-id="1d69b-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Velden en segmenten selecteren om naar Marketo te exporteren":::

1. <span data-ttu-id="1d69b-128">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1d69b-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="1d69b-129">De gegevens exporteren</span><span class="sxs-lookup"><span data-stu-id="1d69b-129">Export the data</span></span>

<span data-ttu-id="1d69b-130">U kunt [gegevens op aanvraag exporteren](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="1d69b-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="1d69b-131">De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1d69b-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1d69b-132">In Marketo vindt u nu uw segmenten onder [Marketo-lijsten](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="1d69b-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1d69b-133">Bekende beperkingen</span><span class="sxs-lookup"><span data-stu-id="1d69b-133">Known limitations</span></span>

- <span data-ttu-id="1d69b-134">Maximaal 1 miljoen profielen per export naar Marketo.</span><span class="sxs-lookup"><span data-stu-id="1d69b-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="1d69b-135">Exporteren naar Marketo is beperkt tot segmenten.</span><span class="sxs-lookup"><span data-stu-id="1d69b-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="1d69b-136">Segmenten met in totaal 1 miljoen profielen exporteren kan tot 3 uur duren.</span><span class="sxs-lookup"><span data-stu-id="1d69b-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="1d69b-137">Het aantal profielen dat u naar Marketo kunt exporteren, is afhankelijk van uw contract met Marketo.</span><span class="sxs-lookup"><span data-stu-id="1d69b-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1d69b-138">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="1d69b-138">Data privacy and compliance</span></span>

<span data-ttu-id="1d69b-139">Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar Marketo te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="1d69b-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1d69b-140">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat Marketo voldoet aan uw privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="1d69b-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="1d69b-141">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1d69b-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="1d69b-142">Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="1d69b-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
