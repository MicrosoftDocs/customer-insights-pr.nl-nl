---
title: Customer Insights-gegevens exporteren naar AdRoll
description: Leer hoe u de verbinding configureert en exporteert naar AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e8f4d4ee6b2c6cdec513b700641db568fa16076d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895953"
---
# <a name="export-segment-lists-to-adroll-preview"></a><span data-ttu-id="bdb6e-103">Segmentlijsten exporteren naar AdRoll (preview)</span><span class="sxs-lookup"><span data-stu-id="bdb6e-103">Export segment lists to AdRoll (preview)</span></span>

<span data-ttu-id="bdb6e-104">Exporteer segmenten van geharmoniseerde klantprofielen naar AdRoll en gebruik ze voor advertenties.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="bdb6e-105">Vereisten voor een verbinding</span><span class="sxs-lookup"><span data-stu-id="bdb6e-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="bdb6e-106">U hebt een [AdRoll-account](https://www.adroll.com/) en bijbehorende beheerdersreferenties nodig.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="bdb6e-107">U hebt [geconfigureerde segmenten](segments.md) in doelgroepinzichten.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="bdb6e-108">Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="bdb6e-109">Bekende beperkingen</span><span class="sxs-lookup"><span data-stu-id="bdb6e-109">Known limitations</span></span>

- <span data-ttu-id="bdb6e-110">U kunt in totaal tot 250.000 profielen per export exporteren naar AdRoll.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-110">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="bdb6e-111">U kunt geen segmenten met minder dan 100 profielen naar AdRoll exporteren.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="bdb6e-112">Exporteren naar AdRoll is beperkt tot segmenten.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="bdb6e-113">Het exporteren van maximaal 250.000 profielen naar AdRoll kan tot 10 minuten duren.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-113">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="bdb6e-114">Het aantal profielen dat u naar AdRoll kunt exporteren, is afhankelijk van uw contract met AdRoll.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-114">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="bdb6e-115">Verbinding met AdRoll instellen</span><span class="sxs-lookup"><span data-stu-id="bdb6e-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="bdb6e-116">Ga naar **Beheerder** > **Verbindingen**.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="bdb6e-117">Selecteer **Verbinding toevoegen** en kies **AdRoll** om de verbinding te configureren.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="bdb6e-118">Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="bdb6e-119">De naam en het type verbinding beschrijven deze verbinding.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="bdb6e-120">We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="bdb6e-121">Kies wie deze verbinding kan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-121">Choose who can use this connection.</span></span> <span data-ttu-id="bdb6e-122">Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="bdb6e-123">Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="bdb6e-124">Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="bdb6e-125">Selecteer **Verbinden** om de verbinding met AdRoll te initialiseren.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="bdb6e-126">Selecteer **Verifiëren met AdRoll** en geef uw beheerdersreferenties voor AdRoll op.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="bdb6e-127">Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="bdb6e-128">Selecteer **Opslaan** om de verbinding te voltooien.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="bdb6e-129">Een export configureren</span><span class="sxs-lookup"><span data-stu-id="bdb6e-129">Configure an export</span></span>

<span data-ttu-id="bdb6e-130">U kunt deze export configureren als u toegang hebt tot een verbinding van dit type.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="bdb6e-131">Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="bdb6e-132">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="bdb6e-133">Selecteer **Bestemming toevoegen** om een nieuwe export te maken.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="bdb6e-134">Kies in het veld **Verbinding voor export** een verbinding uit de sectie AdRoll.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="bdb6e-135">Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="bdb6e-136">Voer uw **AdRoll-adverteerder-id** in. Zie [AdRoll-adverteerdersprofielen](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-136">Enter your **AdRoll Advertiser ID** For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="bdb6e-137">Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="bdb6e-138">Het is vereist om segmenten naar AdRoll te exporteren.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-138">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="bdb6e-139">Selecteer de segmenten die u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-139">Select the segments you want to export.</span></span> <span data-ttu-id="bdb6e-140">Selecteer een segment met minimaal 100 leden.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="bdb6e-141">U kunt geen kleinere segmenten exporteren.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-141">You can't export smaller segments.</span></span> <span data-ttu-id="bdb6e-142">Bovendien is de maximale grootte van een te exporteren segment 250.000 leden per export.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="bdb6e-143">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-143">Select **Save**.</span></span>

<span data-ttu-id="bdb6e-144">Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="bdb6e-145">De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bdb6e-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bdb6e-146">U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="bdb6e-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bdb6e-147">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="bdb6e-147">Data privacy and compliance</span></span>

<span data-ttu-id="bdb6e-148">Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar AdRoll te verzenden, staat u de overdracht toe van gegevens buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-148">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bdb6e-149">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat AdRoll voldoet aan uw privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="bdb6e-150">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="bdb6e-151">Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="bdb6e-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
