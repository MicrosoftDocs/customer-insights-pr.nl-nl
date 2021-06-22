---
title: Customer Insights-gegevens exporteren naar Constant Contact
description: Leer hoe u de verbinding configureert en exporteert naar Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 29f4320c798db62609283e3c48f0b47a4f0b982f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124267"
---
# <a name="export-segments-to-constant-contact-preview"></a><span data-ttu-id="e8d04-103">Segmenten exporteren naar Constant Contact (preview)</span><span class="sxs-lookup"><span data-stu-id="e8d04-103">Export segments to Constant Contact (preview)</span></span>

<span data-ttu-id="e8d04-104">Exporteer segmenten van geharmoniseerde klantprofielen naar Constant Contact en gebruik deze voor marketingactiviteiten.</span><span class="sxs-lookup"><span data-stu-id="e8d04-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="e8d04-105">Vereisten voor een verbinding</span><span class="sxs-lookup"><span data-stu-id="e8d04-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="e8d04-106">U hebt een [Constant Contact-account](https://www.constantcontact.com/account-home) en bijbehorende beheerdersreferenties.</span><span class="sxs-lookup"><span data-stu-id="e8d04-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e8d04-107">U hebt [geconfigureerde segmenten](segments.md) in doelgroepinzichten.</span><span class="sxs-lookup"><span data-stu-id="e8d04-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="e8d04-108">Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="e8d04-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e8d04-109">Bekende beperkingen</span><span class="sxs-lookup"><span data-stu-id="e8d04-109">Known limitations</span></span>

- <span data-ttu-id="e8d04-110">U kunt maximaal 1 miljoen profielen per export exporteren naar Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="e8d04-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="e8d04-111">Exporteren naar Constant Contact is beperkt tot segmenten.</span><span class="sxs-lookup"><span data-stu-id="e8d04-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="e8d04-112">Het exporteren van maximaal 1 miljoen profielen naar Constant Contact kan tot 1 uur duren.</span><span class="sxs-lookup"><span data-stu-id="e8d04-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="e8d04-113">Het aantal profielen dat u naar Constant Contact kunt exporteren, is afhankelijk van en wordt beperkt door uw contract met Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="e8d04-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="e8d04-114">Verbinding instellen met Constant Contact</span><span class="sxs-lookup"><span data-stu-id="e8d04-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="e8d04-115">Ga naar **Beheerder** > **Verbindingen**.</span><span class="sxs-lookup"><span data-stu-id="e8d04-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e8d04-116">Selecteer **Verbinding toevoegen** en kies **Constant Contact** om de verbinding te configureren.</span><span class="sxs-lookup"><span data-stu-id="e8d04-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="e8d04-117">Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="e8d04-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e8d04-118">De naam en het type verbinding beschrijven deze verbinding.</span><span class="sxs-lookup"><span data-stu-id="e8d04-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e8d04-119">We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.</span><span class="sxs-lookup"><span data-stu-id="e8d04-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e8d04-120">Kies wie deze verbinding kan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e8d04-120">Choose who can use this connection.</span></span> <span data-ttu-id="e8d04-121">Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling.</span><span class="sxs-lookup"><span data-stu-id="e8d04-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e8d04-122">Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e8d04-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e8d04-123">Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="e8d04-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e8d04-124">Selecteer **Verbinden** om de verbinding met Constant Contact te initialiseren.</span><span class="sxs-lookup"><span data-stu-id="e8d04-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="e8d04-125">Selecteer **Verifiëren met AdRoll** en geef uw beheerdersreferenties voor Constant Contact op.</span><span class="sxs-lookup"><span data-stu-id="e8d04-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="e8d04-126">Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.</span><span class="sxs-lookup"><span data-stu-id="e8d04-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e8d04-127">Selecteer **Opslaan** om de verbinding te voltooien.</span><span class="sxs-lookup"><span data-stu-id="e8d04-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e8d04-128">Een export configureren</span><span class="sxs-lookup"><span data-stu-id="e8d04-128">Configure an export</span></span>

<span data-ttu-id="e8d04-129">U kunt deze export configureren als u toegang hebt tot een verbinding van dit type.</span><span class="sxs-lookup"><span data-stu-id="e8d04-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e8d04-130">Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e8d04-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e8d04-131">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="e8d04-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e8d04-132">Selecteer **Bestemming toevoegen** om een nieuwe export te maken.</span><span class="sxs-lookup"><span data-stu-id="e8d04-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e8d04-133">Kies in het veld **Verbinding voor export** een verbinding uit de sectie Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="e8d04-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="e8d04-134">Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="e8d04-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e8d04-135">Enter your [**Id van Constant Contact-lijst**](https://app.constantcontact.com/pages/contacts/ui#lists) in.</span><span class="sxs-lookup"><span data-stu-id="e8d04-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="e8d04-136">Open een lijst in Constant Contact om de lijst-id in de URL te vinden.</span><span class="sxs-lookup"><span data-stu-id="e8d04-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="e8d04-137">Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant.</span><span class="sxs-lookup"><span data-stu-id="e8d04-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="e8d04-138">Deze is vereist voor het exporteren van segmenten naar Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="e8d04-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="e8d04-139">Optioneel kunt u Voornaam en Achternaam exporteren als extra velden om meer gepersonaliseerde e-mails te maken.</span><span class="sxs-lookup"><span data-stu-id="e8d04-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="e8d04-140">Selecteer **Kenmerk toevoegen** om deze velden toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="e8d04-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="e8d04-141">Selecteer de segmenten die u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="e8d04-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="e8d04-142">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="e8d04-142">Select **Save**.</span></span>

<span data-ttu-id="e8d04-143">Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="e8d04-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e8d04-144">De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e8d04-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e8d04-145">U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e8d04-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e8d04-146">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="e8d04-146">Data privacy and compliance</span></span>

<span data-ttu-id="e8d04-147">Wanneer u Dynamics 365 Customer Insights inschakelt om gegevens naar Constant Contact te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, inclusief mogelijk gevoelige gegevens zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="e8d04-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e8d04-148">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent er verantwoordelijk voor dat Constant Contact voldoet aan mogelijke privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="e8d04-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e8d04-149">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e8d04-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="e8d04-150">Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="e8d04-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
