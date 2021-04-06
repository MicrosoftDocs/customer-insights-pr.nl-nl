---
title: Customer Insights-gegevens exporteren naar AdRoll
description: Ontdek hoe u de verbinding met AdRoll configureert.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697068"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="b710d-103">Connector voor AdRoll (preview)</span><span class="sxs-lookup"><span data-stu-id="b710d-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="b710d-104">Exporteer segmenten van geharmoniseerde klantprofielen naar AdRoll en gebruik ze voor advertenties.</span><span class="sxs-lookup"><span data-stu-id="b710d-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="b710d-105">Vereisten</span><span class="sxs-lookup"><span data-stu-id="b710d-105">Prerequisites</span></span>

-   <span data-ttu-id="b710d-106">U hebt een [AdRoll-account](https://www.adroll.com/) en bijbehorende beheerdersreferenties nodig.</span><span class="sxs-lookup"><span data-stu-id="b710d-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="b710d-107">U hebt [geconfigureerde segmenten](segments.md) in doelgroepinzichten.</span><span class="sxs-lookup"><span data-stu-id="b710d-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="b710d-108">Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="b710d-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="b710d-109">Verbinding maken met AdRoll</span><span class="sxs-lookup"><span data-stu-id="b710d-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="b710d-110">Ga naar **Beheer** > **Exportbestemmingen**.</span><span class="sxs-lookup"><span data-stu-id="b710d-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="b710d-111">Selecteer onder **AdRoll** de optie **Instellen**.</span><span class="sxs-lookup"><span data-stu-id="b710d-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="b710d-112">Geef uw exportbestemming een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="b710d-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Configuratiedeelvenster voor AdRoll-verbinding.":::

1. <span data-ttu-id="b710d-114">Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="b710d-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b710d-115">Selecteer **Verbinden** om de verbinding met AdRoll te initialiseren.</span><span class="sxs-lookup"><span data-stu-id="b710d-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="b710d-116">Selecteer **Verifiëren met AdRoll** en geef uw beheerdersreferenties voor AdRoll op.</span><span class="sxs-lookup"><span data-stu-id="b710d-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="b710d-117">Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.</span><span class="sxs-lookup"><span data-stu-id="b710d-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="b710d-118">Voer uw **AdRoll-adverteerders-id** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles)​ in.</span><span class="sxs-lookup"><span data-stu-id="b710d-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="b710d-119">Selecteer **Volgende** om de export te configureren.</span><span class="sxs-lookup"><span data-stu-id="b710d-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="b710d-120">De connector configureren</span><span class="sxs-lookup"><span data-stu-id="b710d-120">Configure the connector</span></span>

1. <span data-ttu-id="b710d-121">Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant.</span><span class="sxs-lookup"><span data-stu-id="b710d-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="b710d-122">Het is vereist om segmenten naar AdRoll te exporteren.</span><span class="sxs-lookup"><span data-stu-id="b710d-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="b710d-123">Selecteer de segmenten die u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="b710d-123">Select the segments you want to export.</span></span> <span data-ttu-id="b710d-124">Selecteer een segment met minimaal 100 leden.</span><span class="sxs-lookup"><span data-stu-id="b710d-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="b710d-125">U kunt geen kleinere segmenten exporteren.</span><span class="sxs-lookup"><span data-stu-id="b710d-125">You can't export smaller segments.</span></span> <span data-ttu-id="b710d-126">Bovendien is de maximale grootte van een te exporteren segment 250.000 leden per export.</span><span class="sxs-lookup"><span data-stu-id="b710d-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="b710d-127">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b710d-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="b710d-128">De gegevens exporteren</span><span class="sxs-lookup"><span data-stu-id="b710d-128">Export the data</span></span>

<span data-ttu-id="b710d-129">U kunt [gegevens op aanvraag exporteren](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="b710d-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="b710d-130">De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b710d-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b710d-131">Bekende beperkingen</span><span class="sxs-lookup"><span data-stu-id="b710d-131">Known limitations</span></span>

- <span data-ttu-id="b710d-132">U kunt in totaal tot 250.000 profielen per export exporteren naar AdRoll.</span><span class="sxs-lookup"><span data-stu-id="b710d-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="b710d-133">U kunt geen segmenten met minder dan 100 profielen naar AdRoll exporteren.</span><span class="sxs-lookup"><span data-stu-id="b710d-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="b710d-134">Exporteren naar AdRoll is beperkt tot segmenten.</span><span class="sxs-lookup"><span data-stu-id="b710d-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="b710d-135">Het exporteren van maximaal 250.000 profielen naar AdRoll kan tot 10 minuten duren.</span><span class="sxs-lookup"><span data-stu-id="b710d-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="b710d-136">Het aantal profielen dat u naar AdRoll kunt exporteren, is afhankelijk van uw contract met AdRoll.</span><span class="sxs-lookup"><span data-stu-id="b710d-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b710d-137">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="b710d-137">Data privacy and compliance</span></span>

<span data-ttu-id="b710d-138">Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar AdRoll te verzenden, staat u de overdracht toe van gegevens buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="b710d-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b710d-139">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat AdRoll voldoet aan uw privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="b710d-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b710d-140">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b710d-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="b710d-141">Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="b710d-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
