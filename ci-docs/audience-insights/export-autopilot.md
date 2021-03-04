---
title: Customer Insights-gegevens exporteren naar Autopilot
description: Ontdek hoe u de verbinding met Autopilot configureert.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269232"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="6350e-103">Connector voor Autopilot (preview)</span><span class="sxs-lookup"><span data-stu-id="6350e-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="6350e-104">Exporteer segmenten van geharmoniseerde klantprofielen naar Autopilot en gebruik ze voor e-mailmarketing in Autopilot.</span><span class="sxs-lookup"><span data-stu-id="6350e-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="6350e-105">Vereisten</span><span class="sxs-lookup"><span data-stu-id="6350e-105">Prerequisites</span></span>

-   <span data-ttu-id="6350e-106">U hebt een [Autopilot-account](https://www.autopilothq.com/) en bijbehorende beheerdersreferenties nodig.</span><span class="sxs-lookup"><span data-stu-id="6350e-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="6350e-107">U hebt [geconfigureerde segmenten](segments.md) in doelgroepinzichten.</span><span class="sxs-lookup"><span data-stu-id="6350e-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="6350e-108">Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="6350e-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="6350e-109">Verbinding maken met Autopilot</span><span class="sxs-lookup"><span data-stu-id="6350e-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="6350e-110">Ga naar **Beheer** > **Exportbestemmingen**.</span><span class="sxs-lookup"><span data-stu-id="6350e-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="6350e-111">Selecteer onder **Autopilot** de optie **Instellen**.</span><span class="sxs-lookup"><span data-stu-id="6350e-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="6350e-112">Geef uw exportbestemming een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="6350e-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Configuratiedeelvenster voor Autopilot-verbinding.":::

1. <span data-ttu-id="6350e-114">Voer uw **Autopilot API-sleutel** [Autopilot API-sleutel](https://autopilot.docs.apiary.io/#)​in.</span><span class="sxs-lookup"><span data-stu-id="6350e-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="6350e-115">Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="6350e-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="6350e-116">Selecteer **Verbinden** om de verbinding met Autopilot te initialiseren.</span><span class="sxs-lookup"><span data-stu-id="6350e-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="6350e-117">Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.</span><span class="sxs-lookup"><span data-stu-id="6350e-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="6350e-118">Selecteer **Volgende** om de export te configureren.</span><span class="sxs-lookup"><span data-stu-id="6350e-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="6350e-119">De connector configureren</span><span class="sxs-lookup"><span data-stu-id="6350e-119">Configure the connector</span></span>

1. <span data-ttu-id="6350e-120">Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant.</span><span class="sxs-lookup"><span data-stu-id="6350e-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="6350e-121">Herhaal dezelfde stappen voor andere optionele velden, zoals **Voornaam**, **Achternaam**.</span><span class="sxs-lookup"><span data-stu-id="6350e-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="6350e-122">Selecteer de segmenten die u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="6350e-122">Select the segments you want to export.</span></span> <span data-ttu-id="6350e-123">Wij **raden u sterk aan niet meer dan 100.000 klantprofielen in totaal te exporteren** naar Autopilot.</span><span class="sxs-lookup"><span data-stu-id="6350e-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="6350e-124">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6350e-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="6350e-125">De gegevens exporteren</span><span class="sxs-lookup"><span data-stu-id="6350e-125">Export the data</span></span>

<span data-ttu-id="6350e-126">U kunt [gegevens op aanvraag exporteren](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="6350e-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="6350e-127">De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6350e-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="6350e-128">Bekende beperkingen</span><span class="sxs-lookup"><span data-stu-id="6350e-128">Known limitations</span></span>

- <span data-ttu-id="6350e-129">U kunt in totaal tot 100.000 klantprofielen exporteren naar Autopilot.</span><span class="sxs-lookup"><span data-stu-id="6350e-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="6350e-130">Exporteren naar Autopilot is beperkt tot segmenten.</span><span class="sxs-lookup"><span data-stu-id="6350e-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="6350e-131">Het exporteren van maximaal 100.000 profielen naar Autopilot kan enkele uren duren.</span><span class="sxs-lookup"><span data-stu-id="6350e-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="6350e-132">Het aantal profielen dat u naar Autopilot kunt exporteren, is afhankelijk van uw contract met Autopilot.</span><span class="sxs-lookup"><span data-stu-id="6350e-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6350e-133">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="6350e-133">Data privacy and compliance</span></span>

<span data-ttu-id="6350e-134">Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar Autopilot te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="6350e-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6350e-135">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat Autopilot voldoet aan uw privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="6350e-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="6350e-136">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="6350e-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="6350e-137">Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="6350e-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]