---
title: Customer Insights-gegevens exporteren naar LinkedIn Ads
description: Procedure voor het configureren van de verbinding en voor het exporteren naar LinkedIn Ads.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124476"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="68bea-103">Segmenten exporteren naar LinkedIn Ads (preview)</span><span class="sxs-lookup"><span data-stu-id="68bea-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="68bea-104">Exporteer segmenten van geharmoniseerde klantprofielen naar LinkedIn Ads om matched audiences te maken.</span><span class="sxs-lookup"><span data-stu-id="68bea-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="68bea-105">Gebruik de matched audiences voor de targeting van bedrijven en contactpersonen.</span><span class="sxs-lookup"><span data-stu-id="68bea-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="68bea-106">Vereisten</span><span class="sxs-lookup"><span data-stu-id="68bea-106">Prerequisites</span></span>

-   <span data-ttu-id="68bea-107">U hebt een [LinkedIn Campaign Manager-account](https://business.linkedin.com/marketing-solutions/ads) en bijbehorende beheerdersreferenties.</span><span class="sxs-lookup"><span data-stu-id="68bea-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="68bea-108">U hebt [geconfigureerde segmenten](segments.md) in doelgroepinzichten.</span><span class="sxs-lookup"><span data-stu-id="68bea-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="68bea-109">Klantprofielen in de geëxporteerde segmenten bevatten een veld met een e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="68bea-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="68bea-110">Bekende beperkingen</span><span class="sxs-lookup"><span data-stu-id="68bea-110">Known limitations</span></span>

- <span data-ttu-id="68bea-111">U kunt maximaal 100.000 profielen per export exporteren naar LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="68bea-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="68bea-112">Exporteren naar LinkedIn Ads is beperkt tot segmenten.</span><span class="sxs-lookup"><span data-stu-id="68bea-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="68bea-113">Het exporteren van maximaal 100.000 profielen naar LinkedIn Ads kan tot 10 minuten duren.</span><span class="sxs-lookup"><span data-stu-id="68bea-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="68bea-114">De verbinding instellen met LinkedIn Ads</span><span class="sxs-lookup"><span data-stu-id="68bea-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="68bea-115">Ga in doelgroepinzichten naar **Beheerder** > **Verbindingen**.</span><span class="sxs-lookup"><span data-stu-id="68bea-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="68bea-116">Selecteer **Verbinding toevoegen** en kies **LinkedIn Ads** om de verbinding te configureren.</span><span class="sxs-lookup"><span data-stu-id="68bea-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="68bea-117">Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="68bea-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="68bea-118">De naam en het type verbinding beschrijven deze verbinding.</span><span class="sxs-lookup"><span data-stu-id="68bea-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="68bea-119">We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.</span><span class="sxs-lookup"><span data-stu-id="68bea-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="68bea-120">Kies wie deze verbinding kan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="68bea-120">Choose who can use this connection.</span></span> <span data-ttu-id="68bea-121">Als u geen actie onderneemt, wordt beheerders gebruikt als standaardoptie.</span><span class="sxs-lookup"><span data-stu-id="68bea-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="68bea-122">Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="68bea-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="68bea-123">Geef uw [LinkedIn Campaign Manager-account-id](https://www.linkedin.com/help/lms/answer/a424270) op.</span><span class="sxs-lookup"><span data-stu-id="68bea-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="68bea-124">Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="68bea-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="68bea-125">Selecteer **Verbinden** om de verbinding met Campaign Monitor te initialiseren.</span><span class="sxs-lookup"><span data-stu-id="68bea-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="68bea-126">Selecteer **Verifiëren met LinkedIn** en geef uw beheerdersreferenties voor LinkedIn Campaign Manager op.</span><span class="sxs-lookup"><span data-stu-id="68bea-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="68bea-127">Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.</span><span class="sxs-lookup"><span data-stu-id="68bea-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="68bea-128">Selecteer **Opslaan** om de verbinding te voltooien.</span><span class="sxs-lookup"><span data-stu-id="68bea-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="68bea-129">Een export configureren</span><span class="sxs-lookup"><span data-stu-id="68bea-129">Configure an export</span></span>

<span data-ttu-id="68bea-130">U kunt een export configureren als u toegang hebt tot een verbinding van dit type.</span><span class="sxs-lookup"><span data-stu-id="68bea-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="68bea-131">Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="68bea-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="68bea-132">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="68bea-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="68bea-133">Selecteer **Bestemming toevoegen** om een nieuwe export te maken.</span><span class="sxs-lookup"><span data-stu-id="68bea-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="68bea-134">Kies in het veld **Verbinding voor export** een verbinding uit de sectie LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="68bea-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="68bea-135">Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="68bea-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="68bea-136">Kies of u gegevens wilt exporteren om [targeting van contactpersonen](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) of [targeting van bedrijve](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) uit te voeren op LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="68bea-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="68bea-137">Selecteer in de sectie **Gegevensvergelijking** het veld in uw geharmoniseerde klantprofiel dat het e-mailadres van een klant vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="68bea-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="68bea-138">Dit is vereist voor het exporteren van segmenten naar LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="68bea-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="68bea-139">Selecteer de segmenten die u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="68bea-139">Select the segments you want to export.</span></span> <span data-ttu-id="68bea-140">De matched audiences in LinkedIn Campaign Manager worden automatisch gemaakt met de naam van de segmenten die u hebt geselecteerd om te exporteren.</span><span class="sxs-lookup"><span data-stu-id="68bea-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="68bea-141">Elk segment resulteert in een aparte matched audience.</span><span class="sxs-lookup"><span data-stu-id="68bea-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="68bea-142">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="68bea-142">Select **Save**.</span></span>

<span data-ttu-id="68bea-143">Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="68bea-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="68bea-144">De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="68bea-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="68bea-145">U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="68bea-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="68bea-146">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="68bea-146">Data privacy and compliance</span></span>

<span data-ttu-id="68bea-147">Wanneer u Dynamics 365 Customer Insights inschakelt om gegevens naar LinkedIn Ads te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, inclusief mogelijk gevoelige gegevens zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="68bea-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="68bea-148">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent er verantwoordelijk voor dat LinkedIn Ads voldoet aan mogelijke privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="68bea-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="68bea-149">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="68bea-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="68bea-150">Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="68bea-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
