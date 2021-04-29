---
title: Customer Insights-gegevens exporteren naar Campaign Monitor
description: Leer hoe u de verbinding configureert en exporteert naar Campaign Monitor.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7fd6af37b40e21d030a1ace0cd5f8fcc7861c3fa
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760507"
---
# <a name="export-segment-lists-to-campaign-monitor-preview"></a><span data-ttu-id="a00dd-103">Segmentlijsten exporteren naar Campaign Monitor (preview)</span><span class="sxs-lookup"><span data-stu-id="a00dd-103">Export segment lists to Campaign Monitor (preview)</span></span>

<span data-ttu-id="a00dd-104">Exporteer segmenten van geharmoniseerde klantprofielen naar Campaign Monitor en gebruik deze voor marketingactiviteiten.</span><span class="sxs-lookup"><span data-stu-id="a00dd-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a00dd-105">Vereisten</span><span class="sxs-lookup"><span data-stu-id="a00dd-105">Prerequisites</span></span>

-   <span data-ttu-id="a00dd-106">U hebt een [Campaign Monitor-account](https://www.campaignmonitor.com/) en bijbehorende beheerdersreferenties.</span><span class="sxs-lookup"><span data-stu-id="a00dd-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a00dd-107">U hebt [geconfigureerde segmenten](segments.md) in doelgroepinzichten.</span><span class="sxs-lookup"><span data-stu-id="a00dd-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="a00dd-108">Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="a00dd-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a00dd-109">Bekende beperkingen</span><span class="sxs-lookup"><span data-stu-id="a00dd-109">Known limitations</span></span>

- <span data-ttu-id="a00dd-110">U kunt maximaal 1 miljoen profielen per export exporteren naar Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="a00dd-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="a00dd-111">Exporteren naar Campaign Monitor is beperkt tot segmenten.</span><span class="sxs-lookup"><span data-stu-id="a00dd-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="a00dd-112">Het exporteren van maximaal 1 miljoen profielen naar Campaign Monitor kan tot 20 minuten duren.</span><span class="sxs-lookup"><span data-stu-id="a00dd-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="a00dd-113">Het aantal profielen dat u naar Campaign Monitor kunt exporteren, is afhankelijk van en wordt beperkt door uw contract met Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="a00dd-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="a00dd-114">Verbinding instellen met Campaign Monitor</span><span class="sxs-lookup"><span data-stu-id="a00dd-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="a00dd-115">Ga naar **Beheerder** > **Verbindingen**.</span><span class="sxs-lookup"><span data-stu-id="a00dd-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a00dd-116">Selecteer **Verbinding toevoegen** en kies **Campaign Monitor** om de verbinding te configureren.</span><span class="sxs-lookup"><span data-stu-id="a00dd-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="a00dd-117">Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="a00dd-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a00dd-118">De naam en het type verbinding beschrijven deze verbinding.</span><span class="sxs-lookup"><span data-stu-id="a00dd-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a00dd-119">We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.</span><span class="sxs-lookup"><span data-stu-id="a00dd-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a00dd-120">Kies wie deze verbinding kan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="a00dd-120">Choose who can use this connection.</span></span> <span data-ttu-id="a00dd-121">Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling.</span><span class="sxs-lookup"><span data-stu-id="a00dd-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a00dd-122">Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a00dd-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a00dd-123">Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="a00dd-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a00dd-124">Selecteer **Verbinden** om de verbinding met Campaign Monitor te initialiseren.</span><span class="sxs-lookup"><span data-stu-id="a00dd-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="a00dd-125">Selecteer **Verifiëren met Campaign Monitor** en geef uw beheerdersreferenties voor Campaign Monitor op.</span><span class="sxs-lookup"><span data-stu-id="a00dd-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="a00dd-126">Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.</span><span class="sxs-lookup"><span data-stu-id="a00dd-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a00dd-127">Selecteer **Opslaan** om de verbinding te voltooien.</span><span class="sxs-lookup"><span data-stu-id="a00dd-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="a00dd-128">Een export configureren</span><span class="sxs-lookup"><span data-stu-id="a00dd-128">Configure an export</span></span>

<span data-ttu-id="a00dd-129">U kunt deze export configureren als u toegang hebt tot een verbinding van dit type.</span><span class="sxs-lookup"><span data-stu-id="a00dd-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a00dd-130">Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a00dd-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a00dd-131">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="a00dd-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a00dd-132">Selecteer **Bestemming toevoegen** om een nieuwe export te maken.</span><span class="sxs-lookup"><span data-stu-id="a00dd-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a00dd-133">Kies in het veld **Verbinding voor export** een verbinding uit de sectie Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="a00dd-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="a00dd-134">Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="a00dd-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a00dd-135">Voer uw [**lijst-id van Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id) in.</span><span class="sxs-lookup"><span data-stu-id="a00dd-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="a00dd-136">[Genereer de API-sleutel](https://www.campaignmonitor.com/api/getting-started/) van **Accountinstellingen** in Campaign Monitor om de API-lijst-id te bekijken.</span><span class="sxs-lookup"><span data-stu-id="a00dd-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="a00dd-137">Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant.</span><span class="sxs-lookup"><span data-stu-id="a00dd-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="a00dd-138">Deze is vereist voor het exporteren van segmenten naar Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="a00dd-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="a00dd-139">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="a00dd-139">Select **Save**.</span></span>

<span data-ttu-id="a00dd-140">Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="a00dd-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a00dd-141">De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a00dd-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a00dd-142">U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a00dd-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a00dd-143">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="a00dd-143">Data privacy and compliance</span></span>

<span data-ttu-id="a00dd-144">Wanneer u Dynamics 365 Customer Insights inschakelt om gegevens naar Campaign Monitor te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, inclusief mogelijk gevoelige gegevens zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="a00dd-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a00dd-145">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent er verantwoordelijk voor dat Campaign Monitor voldoet aan mogelijke privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="a00dd-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a00dd-146">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a00dd-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="a00dd-147">Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="a00dd-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
