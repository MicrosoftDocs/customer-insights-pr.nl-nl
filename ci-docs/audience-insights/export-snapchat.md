---
title: Customer Insights-gegevens exporteren naar Snapchat
description: Leer hoe u de verbinding configureert en exporteert naar Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6565ab81599abcc0f94465e1153f08e0bc119839
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124037"
---
# <a name="export-segments-to-snapchat-preview"></a><span data-ttu-id="d73ad-103">Segmenten exporteren naar Snapchat (preview)</span><span class="sxs-lookup"><span data-stu-id="d73ad-103">Export segments to Snapchat (preview)</span></span>

<span data-ttu-id="d73ad-104">Exporteer segmenten van geharmoniseerde klantprofielen naar Snapchat en gebruik deze voor reclame.</span><span class="sxs-lookup"><span data-stu-id="d73ad-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="d73ad-105">Vereisten voor een verbinding</span><span class="sxs-lookup"><span data-stu-id="d73ad-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="d73ad-106">Je hebt een [zakelijk Snapchat-account](https://business.snapchat.com/), een [Snapchat Ads-account](https://ads.snapchat.com/) en de bijbehorende beheerdersreferenties.</span><span class="sxs-lookup"><span data-stu-id="d73ad-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d73ad-107">U hebt [geconfigureerde segmenten](segments.md) in doelgroepinzichten.</span><span class="sxs-lookup"><span data-stu-id="d73ad-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="d73ad-108">Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="d73ad-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d73ad-109">Bekende beperkingen</span><span class="sxs-lookup"><span data-stu-id="d73ad-109">Known limitations</span></span>

- <span data-ttu-id="d73ad-110">Exporteren naar Snapchat is beperkt tot segmenten.</span><span class="sxs-lookup"><span data-stu-id="d73ad-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="d73ad-111">Het exporteren van maximaal 1 miljoen profielen naar Snapchat kan tot 15 minuten duren.</span><span class="sxs-lookup"><span data-stu-id="d73ad-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="d73ad-112">Verbinding instellen met Snapchat</span><span class="sxs-lookup"><span data-stu-id="d73ad-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="d73ad-113">Ga naar **Beheerder** > **Verbindingen**.</span><span class="sxs-lookup"><span data-stu-id="d73ad-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d73ad-114">Selecteer **Verbinding toevoegen** en kies **Snapchat** om de verbinding te configureren.</span><span class="sxs-lookup"><span data-stu-id="d73ad-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="d73ad-115">Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="d73ad-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d73ad-116">De naam en het type verbinding beschrijven deze verbinding.</span><span class="sxs-lookup"><span data-stu-id="d73ad-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d73ad-117">We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.</span><span class="sxs-lookup"><span data-stu-id="d73ad-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d73ad-118">Kies wie deze verbinding kan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="d73ad-118">Choose who can use this connection.</span></span> <span data-ttu-id="d73ad-119">Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling.</span><span class="sxs-lookup"><span data-stu-id="d73ad-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="d73ad-120">Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d73ad-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d73ad-121">Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="d73ad-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d73ad-122">Selecteer **Verbinden** om de verbinding met Snapchat te initialiseren.</span><span class="sxs-lookup"><span data-stu-id="d73ad-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="d73ad-123">Selecteer **Verifiëren met Snapchat** en geef uw beheerdersreferenties voor Snapchat op.</span><span class="sxs-lookup"><span data-stu-id="d73ad-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="d73ad-124">Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.</span><span class="sxs-lookup"><span data-stu-id="d73ad-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d73ad-125">Selecteer **Opslaan** om de verbinding te voltooien.</span><span class="sxs-lookup"><span data-stu-id="d73ad-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d73ad-126">Een export configureren</span><span class="sxs-lookup"><span data-stu-id="d73ad-126">Configure an export</span></span>

<span data-ttu-id="d73ad-127">U kunt deze export configureren als u toegang hebt tot een verbinding van dit type.</span><span class="sxs-lookup"><span data-stu-id="d73ad-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d73ad-128">Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d73ad-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d73ad-129">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="d73ad-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d73ad-130">Selecteer **Bestemming toevoegen** om een nieuwe export te maken.</span><span class="sxs-lookup"><span data-stu-id="d73ad-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d73ad-131">Kies in het veld **Verbinding voor export** een verbinding uit de sectie Snapchat.</span><span class="sxs-lookup"><span data-stu-id="d73ad-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="d73ad-132">Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="d73ad-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d73ad-133">Voer de [**Snapchat-doelgroep-id**](https://businesshelp.snapchat.com/s/article/custom-audiences) in.</span><span class="sxs-lookup"><span data-stu-id="d73ad-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="d73ad-134">Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant.</span><span class="sxs-lookup"><span data-stu-id="d73ad-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="d73ad-135">Deze is vereist voor het exporteren van segmenten naar Snapchat.</span><span class="sxs-lookup"><span data-stu-id="d73ad-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="d73ad-136">Selecteer de segmenten die u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="d73ad-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="d73ad-137">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d73ad-137">Select **Save**.</span></span>

<span data-ttu-id="d73ad-138">Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="d73ad-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d73ad-139">De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d73ad-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d73ad-140">U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d73ad-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d73ad-141">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="d73ad-141">Data privacy and compliance</span></span>

<span data-ttu-id="d73ad-142">Wanneer u Dynamics 365 Customer Insights inschakelt om gegevens naar Snapchat te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, inclusief mogelijk gevoelige gegevens zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="d73ad-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d73ad-143">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent er verantwoordelijk voor dat Snapchat voldoet aan mogelijke privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="d73ad-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d73ad-144">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d73ad-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="d73ad-145">Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="d73ad-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
