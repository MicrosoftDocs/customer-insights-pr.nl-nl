---
title: Customer Insights-gegevens exporteren naar Autopilot
description: Leer hoe u de verbinding configureert en exporteert naar Autopilot.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760137"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="1196f-103">Segmenten exporteren naar Autopilot (preview)</span><span class="sxs-lookup"><span data-stu-id="1196f-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="1196f-104">Exporteer segmenten van geharmoniseerde klantprofielen naar Autopilot en gebruik ze voor e-mailmarketing in Autopilot.</span><span class="sxs-lookup"><span data-stu-id="1196f-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="1196f-105">Vereisten voor een verbinding</span><span class="sxs-lookup"><span data-stu-id="1196f-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="1196f-106">U hebt een [Autopilot-account](https://www.autopilothq.com/) en bijbehorende beheerdersreferenties nodig.</span><span class="sxs-lookup"><span data-stu-id="1196f-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="1196f-107">U hebt [geconfigureerde segmenten](segments.md) in doelgroepinzichten.</span><span class="sxs-lookup"><span data-stu-id="1196f-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="1196f-108">Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="1196f-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1196f-109">Bekende beperkingen</span><span class="sxs-lookup"><span data-stu-id="1196f-109">Known limitations</span></span>

- <span data-ttu-id="1196f-110">U kunt in totaal tot 100.000 klantprofielen exporteren naar Autopilot.</span><span class="sxs-lookup"><span data-stu-id="1196f-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="1196f-111">Exporteren naar Autopilot is beperkt tot segmenten.</span><span class="sxs-lookup"><span data-stu-id="1196f-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="1196f-112">Het exporteren van maximaal 100.000 profielen naar Autopilot kan enkele uren duren.</span><span class="sxs-lookup"><span data-stu-id="1196f-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="1196f-113">Het aantal profielen dat u naar Autopilot kunt exporteren, is afhankelijk van uw contract met Autopilot.</span><span class="sxs-lookup"><span data-stu-id="1196f-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="1196f-114">Verbinding instellen met Autopilot</span><span class="sxs-lookup"><span data-stu-id="1196f-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="1196f-115">Ga naar **Beheerder** > **Verbindingen**.</span><span class="sxs-lookup"><span data-stu-id="1196f-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1196f-116">Selecteer **Verbinding toevoegen** en kies **Autopilot** om de verbinding te configureren.</span><span class="sxs-lookup"><span data-stu-id="1196f-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="1196f-117">Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="1196f-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1196f-118">De naam en het type verbinding beschrijven deze verbinding.</span><span class="sxs-lookup"><span data-stu-id="1196f-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1196f-119">We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.</span><span class="sxs-lookup"><span data-stu-id="1196f-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1196f-120">Kies wie deze verbinding kan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="1196f-120">Choose who can use this connection.</span></span> <span data-ttu-id="1196f-121">Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling.</span><span class="sxs-lookup"><span data-stu-id="1196f-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="1196f-122">Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1196f-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="1196f-123">Voer uw [API-sleutel voor Autopilot](https://autopilot.docs.apiary.io/#) in.</span><span class="sxs-lookup"><span data-stu-id="1196f-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="1196f-124">Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="1196f-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="1196f-125">Selecteer **Verbinden** om de verbinding met Autopilot te initialiseren.</span><span class="sxs-lookup"><span data-stu-id="1196f-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="1196f-126">Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.</span><span class="sxs-lookup"><span data-stu-id="1196f-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="1196f-127">Selecteer **Opslaan** om de verbinding te voltooien.</span><span class="sxs-lookup"><span data-stu-id="1196f-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="1196f-128">Een export configureren</span><span class="sxs-lookup"><span data-stu-id="1196f-128">Configure an export</span></span>

<span data-ttu-id="1196f-129">U kunt deze export configureren als u toegang hebt tot een verbinding van dit type.</span><span class="sxs-lookup"><span data-stu-id="1196f-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1196f-130">Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1196f-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1196f-131">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="1196f-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1196f-132">Selecteer **Bestemming toevoegen** om een nieuwe export te maken.</span><span class="sxs-lookup"><span data-stu-id="1196f-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="1196f-133">Kies in het veld **Verbinding voor export** een verbinding uit de sectie Autopilot.</span><span class="sxs-lookup"><span data-stu-id="1196f-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="1196f-134">Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="1196f-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="1196f-135">Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant.</span><span class="sxs-lookup"><span data-stu-id="1196f-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="1196f-136">Herhaal dezelfde stappen voor andere optionele velden, zoals **Voornaam**, **Achternaam**.</span><span class="sxs-lookup"><span data-stu-id="1196f-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="1196f-137">Selecteer de segmenten die u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="1196f-137">Select the segments you want to export.</span></span> <span data-ttu-id="1196f-138">Wij **raden u sterk aan niet meer dan 100.000 klantprofielen in totaal te exporteren** naar Autopilot.</span><span class="sxs-lookup"><span data-stu-id="1196f-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="1196f-139">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1196f-139">Select **Save**.</span></span>

<span data-ttu-id="1196f-140">Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="1196f-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1196f-141">De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1196f-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1196f-142">U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1196f-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1196f-143">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="1196f-143">Data privacy and compliance</span></span>

<span data-ttu-id="1196f-144">Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar Autopilot te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="1196f-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1196f-145">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat Autopilot voldoet aan uw privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="1196f-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="1196f-146">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1196f-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="1196f-147">Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="1196f-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
