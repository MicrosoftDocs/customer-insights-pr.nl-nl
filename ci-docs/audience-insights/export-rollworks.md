---
title: Customer Insights-gegevens exporteren naar RollWorks
description: Leer hoe u de verbinding configureert en exporteert naar RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4979f0147dea2270f11342c1bb6b0693f3c24aea
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760508"
---
# <a name="export-segment-lists-to-rollworks-preview"></a><span data-ttu-id="61e2e-103">Segmentlijsten exporteren naar RollWorks (preview)</span><span class="sxs-lookup"><span data-stu-id="61e2e-103">Export segment lists to RollWorks (preview)</span></span>

<span data-ttu-id="61e2e-104">Exporteer segmenten van geharmoniseerde klantprofielen naar RollWorks en gebruik deze voor reclame.</span><span class="sxs-lookup"><span data-stu-id="61e2e-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="61e2e-105">Vereisten voor een verbinding</span><span class="sxs-lookup"><span data-stu-id="61e2e-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="61e2e-106">U hebt een [RollWorks-account](https://www.rollworks.com/) en bijbehorende beheerdersreferenties.</span><span class="sxs-lookup"><span data-stu-id="61e2e-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="61e2e-107">U hebt [geconfigureerde segmenten](segments.md) in doelgroepinzichten.</span><span class="sxs-lookup"><span data-stu-id="61e2e-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="61e2e-108">Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="61e2e-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="61e2e-109">Bekende beperkingen</span><span class="sxs-lookup"><span data-stu-id="61e2e-109">Known limitations</span></span>

- <span data-ttu-id="61e2e-110">U kunt maximaal 250.000 profielen per export exporteren naar RollWorks.</span><span class="sxs-lookup"><span data-stu-id="61e2e-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="61e2e-111">U kunt geen segmenten met minder dan 100 profielen exporteren naar RollWorks.</span><span class="sxs-lookup"><span data-stu-id="61e2e-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="61e2e-112">Exporteren naar RollWorks is beperkt tot segmenten.</span><span class="sxs-lookup"><span data-stu-id="61e2e-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="61e2e-113">Het exporteren van maximaal 250.000 profielen naar RollWorks kan tot 10 minuten duren.</span><span class="sxs-lookup"><span data-stu-id="61e2e-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="61e2e-114">Het aantal profielen dat u naar RollWorks kunt exporteren, is afhankelijk van en wordt beperkt door uw contract met RollWorks.</span><span class="sxs-lookup"><span data-stu-id="61e2e-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="61e2e-115">Verbinding instellen met RollWorks</span><span class="sxs-lookup"><span data-stu-id="61e2e-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="61e2e-116">Ga naar **Beheerder** > **Verbindingen**.</span><span class="sxs-lookup"><span data-stu-id="61e2e-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="61e2e-117">Selecteer **Verbinding toevoegen** en kies **RollWorks** om de verbinding te configureren.</span><span class="sxs-lookup"><span data-stu-id="61e2e-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="61e2e-118">Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="61e2e-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="61e2e-119">De naam en het type verbinding beschrijven deze verbinding.</span><span class="sxs-lookup"><span data-stu-id="61e2e-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="61e2e-120">We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.</span><span class="sxs-lookup"><span data-stu-id="61e2e-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="61e2e-121">Kies wie deze verbinding kan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="61e2e-121">Choose who can use this connection.</span></span> <span data-ttu-id="61e2e-122">Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling.</span><span class="sxs-lookup"><span data-stu-id="61e2e-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="61e2e-123">Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="61e2e-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="61e2e-124">Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="61e2e-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="61e2e-125">Selecteer **Verbinden** om de verbinding met RollWorks te initialiseren.</span><span class="sxs-lookup"><span data-stu-id="61e2e-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="61e2e-126">Selecteer **Verifiëren met RollWorks** en geef uw beheerdersreferenties voor RollWorks op.</span><span class="sxs-lookup"><span data-stu-id="61e2e-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="61e2e-127">Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.</span><span class="sxs-lookup"><span data-stu-id="61e2e-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="61e2e-128">Selecteer **Opslaan** om de verbinding te voltooien.</span><span class="sxs-lookup"><span data-stu-id="61e2e-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="61e2e-129">Een export configureren</span><span class="sxs-lookup"><span data-stu-id="61e2e-129">Configure an export</span></span>

<span data-ttu-id="61e2e-130">U kunt deze export configureren als u toegang hebt tot een verbinding van dit type.</span><span class="sxs-lookup"><span data-stu-id="61e2e-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="61e2e-131">Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="61e2e-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="61e2e-132">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="61e2e-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="61e2e-133">Selecteer **Bestemming toevoegen** om een nieuwe export te maken.</span><span class="sxs-lookup"><span data-stu-id="61e2e-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="61e2e-134">Kies in het veld **Verbinding voor export** een verbinding uit de sectie RollWorks.</span><span class="sxs-lookup"><span data-stu-id="61e2e-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="61e2e-135">Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="61e2e-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="61e2e-136">Voer uw **Id van RollWorks-adverteerder** [RollWorks-adverteerder](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles) in.</span><span class="sxs-lookup"><span data-stu-id="61e2e-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="61e2e-137">Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant.</span><span class="sxs-lookup"><span data-stu-id="61e2e-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="61e2e-138">Deze is vereist voor het exporteren van segmenten naar RollWorks.</span><span class="sxs-lookup"><span data-stu-id="61e2e-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="61e2e-139">Selecteer de segmenten die u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="61e2e-139">Select the segments you want to export.</span></span> <span data-ttu-id="61e2e-140">Selecteer een segment met minimaal 100 leden.</span><span class="sxs-lookup"><span data-stu-id="61e2e-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="61e2e-141">U kunt geen kleinere segmenten exporteren.</span><span class="sxs-lookup"><span data-stu-id="61e2e-141">You can't export smaller segments.</span></span> <span data-ttu-id="61e2e-142">Bovendien is de maximale grootte van een te exporteren segment 250.000 leden per export.</span><span class="sxs-lookup"><span data-stu-id="61e2e-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="61e2e-143">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="61e2e-143">Select **Save**.</span></span>

<span data-ttu-id="61e2e-144">Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="61e2e-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="61e2e-145">De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="61e2e-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="61e2e-146">U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="61e2e-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="61e2e-147">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="61e2e-147">Data privacy and compliance</span></span>

<span data-ttu-id="61e2e-148">Wanneer u Dynamics 365 Customer Insights inschakelt om gegevens naar RollWorks te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, inclusief mogelijk gevoelige gegevens zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="61e2e-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="61e2e-149">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent er verantwoordelijk voor dat RollWorks voldoet aan mogelijke privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="61e2e-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="61e2e-150">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="61e2e-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="61e2e-151">Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="61e2e-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
