---
title: Customer Insights-gegevens exporteren naar Mailchimp
description: Leer hoe u de verbinding configureert en exporteert naar Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7922a6a69f863caae5401549ed6f88a61aa77d39
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124221"
---
# <a name="export-segments-to-mailchimp-preview"></a><span data-ttu-id="d235e-103">Segmenten exporteren naar Mailchimp (preview)</span><span class="sxs-lookup"><span data-stu-id="d235e-103">Export segments to Mailchimp (preview)</span></span>

<span data-ttu-id="d235e-104">Exporteer segmenten van geharmoniseerde klantprofielen naar Mailchimp om nieuwsbrieven en e-mailcampagnes te maken.</span><span class="sxs-lookup"><span data-stu-id="d235e-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="d235e-105">Vereisten voor verbinding</span><span class="sxs-lookup"><span data-stu-id="d235e-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="d235e-106">U hebt een [Mailchimp-account](https://mailchimp.com/) en bijbehorende beheerdersreferenties nodig.</span><span class="sxs-lookup"><span data-stu-id="d235e-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d235e-107">Er zijn bestaande doelgroepen met bijbehorende id's in Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="d235e-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="d235e-108">Zie [Mailchimp-doelgroepen](https://mailchimp.com/help/create-audience/) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d235e-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="d235e-109">U hebt [geconfigureerde segmenten](segments.md)</span><span class="sxs-lookup"><span data-stu-id="d235e-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="d235e-110">Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="d235e-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d235e-111">Bekende beperkingen</span><span class="sxs-lookup"><span data-stu-id="d235e-111">Known limitations</span></span>

- <span data-ttu-id="d235e-112">Maximaal 1 miljoen profielen per export naar Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="d235e-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="d235e-113">Exporteren naar Mailchimp is beperkt tot segmenten.</span><span class="sxs-lookup"><span data-stu-id="d235e-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="d235e-114">Het exporteren van segmenten met 1 miljoen profielen kan tot drie uur duren.</span><span class="sxs-lookup"><span data-stu-id="d235e-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="d235e-115">Het aantal profielen dat u naar Mailchimp kunt exporteren, is afhankelijk van uw contract met Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="d235e-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="d235e-116">Verbinding instellen met Mailchimp</span><span class="sxs-lookup"><span data-stu-id="d235e-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="d235e-117">Ga naar **Beheerder** > **Verbindingen**.</span><span class="sxs-lookup"><span data-stu-id="d235e-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d235e-118">Selecteer **Verbinding toevoegen** en kies **Autopilot** om de verbinding te configureren.</span><span class="sxs-lookup"><span data-stu-id="d235e-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="d235e-119">Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="d235e-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d235e-120">De naam en het type verbinding beschrijven deze verbinding.</span><span class="sxs-lookup"><span data-stu-id="d235e-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d235e-121">We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.</span><span class="sxs-lookup"><span data-stu-id="d235e-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d235e-122">Kies wie deze verbinding kan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="d235e-122">Choose who can use this connection.</span></span> <span data-ttu-id="d235e-123">Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling.</span><span class="sxs-lookup"><span data-stu-id="d235e-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="d235e-124">Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d235e-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d235e-125">Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="d235e-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d235e-126">Selecteer **Verbinden** om de verbinding met Mailchimp te initialiseren.</span><span class="sxs-lookup"><span data-stu-id="d235e-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="d235e-127">Selecteer **Verifiëren met Mailchimp** en geef uw Mailchimp-referenties op.</span><span class="sxs-lookup"><span data-stu-id="d235e-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="d235e-128">Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.</span><span class="sxs-lookup"><span data-stu-id="d235e-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d235e-129">Selecteer **Opslaan** om de verbinding te voltooien.</span><span class="sxs-lookup"><span data-stu-id="d235e-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="d235e-130">De connector configureren</span><span class="sxs-lookup"><span data-stu-id="d235e-130">Configure the connector</span></span>

<span data-ttu-id="d235e-131">U kunt deze export configureren als u toegang hebt tot een verbinding van dit type.</span><span class="sxs-lookup"><span data-stu-id="d235e-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d235e-132">Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d235e-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d235e-133">Ga naar **Gegevens**> **Exports**.</span><span class="sxs-lookup"><span data-stu-id="d235e-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="d235e-134">Selecteer **Bestemming toevoegen** om een nieuwe export te maken.</span><span class="sxs-lookup"><span data-stu-id="d235e-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d235e-135">Kies in het veld **Verbinding voor export** een verbinding uit de sectie Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="d235e-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="d235e-136">Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="d235e-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d235e-137">Voer uw **[Mailchimp-doelgroep-id](https://mailchimp.com/help/find-audience-id/)** in</span><span class="sxs-lookup"><span data-stu-id="d235e-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="d235e-138">Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant.</span><span class="sxs-lookup"><span data-stu-id="d235e-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="d235e-139">Optioneel kunt u **Voornaam** en **Achternaam** exporteren om meer gepersonaliseerde e-mails te maken.</span><span class="sxs-lookup"><span data-stu-id="d235e-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="d235e-140">Selecteer **Kenmerk toevoegen** om deze velden toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="d235e-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="d235e-141">Selecteer de segmenten die u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="d235e-141">Select the segments you want to export.</span></span> <span data-ttu-id="d235e-142">U kunt in totaal tot 1 miljoen klantprofielen exporteren naar Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="d235e-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="d235e-143">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d235e-143">Select **Save**.</span></span>

<span data-ttu-id="d235e-144">Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="d235e-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d235e-145">De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d235e-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d235e-146">U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d235e-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d235e-147">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="d235e-147">Data privacy and compliance</span></span>

<span data-ttu-id="d235e-148">Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar Mailchimp te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="d235e-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d235e-149">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat Mailchimp voldoet aan uw privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="d235e-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d235e-150">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d235e-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d235e-151">Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="d235e-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
