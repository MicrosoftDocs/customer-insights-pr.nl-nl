---
title: Gegevens uit Customer Insights exporteren naar Sendinblue
description: Leer hoe u de verbinding configureert en exporteert naar Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314598"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="e1be4-103">Segmenten exporteren naar Sendinblue (preview)</span><span class="sxs-lookup"><span data-stu-id="e1be4-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="e1be4-104">Exporteer de segmenten van geharmoniseerde klantprofielen om campagnes te genereren, e-mailmarketing te bieden en specifieke groepen met klanten te gebruiken met Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="e1be4-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="e1be4-105">Vereisten voor verbinding</span><span class="sxs-lookup"><span data-stu-id="e1be4-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="e1be4-106">U hebt een [Sendinblue-account](https://www.sendinblue.com/) en bijbehorende beheerdersreferenties.</span><span class="sxs-lookup"><span data-stu-id="e1be4-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e1be4-107">Er zijn bestaande lijsten in Sendinblue en de bijbehorende id's.</span><span class="sxs-lookup"><span data-stu-id="e1be4-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="e1be4-108">U hebt [geconfigureerde segmenten](segments.md).</span><span class="sxs-lookup"><span data-stu-id="e1be4-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="e1be4-109">Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="e1be4-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e1be4-110">Bekende beperkingen</span><span class="sxs-lookup"><span data-stu-id="e1be4-110">Known limitations</span></span>

- <span data-ttu-id="e1be4-111">Tot 1 miljoen profielen per export naar Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="e1be4-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="e1be4-112">Het exporteren naar Sendinblue is beperkt tot segmenten.</span><span class="sxs-lookup"><span data-stu-id="e1be4-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="e1be4-113">Het exporteren van segmenten met in totaal 1 miljoen profielen kan tot 90 minuten duren.</span><span class="sxs-lookup"><span data-stu-id="e1be4-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="e1be4-114">Het aantal profielen dat u kunt exporteren naar Sendinblue is afhankelijk en beperkt van uw contract met Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="e1be4-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="e1be4-115">Verbinding instellen met Sendinblue</span><span class="sxs-lookup"><span data-stu-id="e1be4-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="e1be4-116">Ga naar **Beheerder** > **Verbindingen**.</span><span class="sxs-lookup"><span data-stu-id="e1be4-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e1be4-117">Selecteer **Verbinding toevoegen** en kies **Sendinblue** om de verbinding te configureren.</span><span class="sxs-lookup"><span data-stu-id="e1be4-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="e1be4-118">Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="e1be4-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e1be4-119">De naam en het type verbinding beschrijven deze verbinding.</span><span class="sxs-lookup"><span data-stu-id="e1be4-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e1be4-120">We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.</span><span class="sxs-lookup"><span data-stu-id="e1be4-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e1be4-121">Kies wie deze verbinding kan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e1be4-121">Choose who can use this connection.</span></span> <span data-ttu-id="e1be4-122">Standaard zijn dit alleen beheerders.</span><span class="sxs-lookup"><span data-stu-id="e1be4-122">By default it's only administrators.</span></span> <span data-ttu-id="e1be4-123">Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e1be4-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e1be4-124">Voer uw **[SendinBlue API-sleutel](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)** in.</span><span class="sxs-lookup"><span data-stu-id="e1be4-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="e1be4-125">Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen en selecteer **Verbinden** om de verbinding met Sendinblue te initialiseren.</span><span class="sxs-lookup"><span data-stu-id="e1be4-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="e1be4-126">Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.</span><span class="sxs-lookup"><span data-stu-id="e1be4-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e1be4-127">Selecteer **Opslaan** om de verbinding te voltooien.</span><span class="sxs-lookup"><span data-stu-id="e1be4-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e1be4-128">Een export configureren</span><span class="sxs-lookup"><span data-stu-id="e1be4-128">Configure an export</span></span>

<span data-ttu-id="e1be4-129">U kunt deze export configureren als u toegang hebt tot een verbinding van dit type.</span><span class="sxs-lookup"><span data-stu-id="e1be4-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e1be4-130">Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e1be4-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e1be4-131">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="e1be4-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e1be4-132">Selecteer **Bestemming toevoegen** om een nieuwe export te maken.</span><span class="sxs-lookup"><span data-stu-id="e1be4-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e1be4-133">Kies in het veld **Verbinding voor export** een verbinding uit de sectie Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="e1be4-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="e1be4-134">Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="e1be4-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e1be4-135">Voer uw **Sendinblue-lijst-id** in</span><span class="sxs-lookup"><span data-stu-id="e1be4-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="e1be4-136">Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant.</span><span class="sxs-lookup"><span data-stu-id="e1be4-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="e1be4-137">Optioneel kunt u **Voornaam**, **Achternaam** en **Telefoon** exporteren om meer gepersonaliseerde e-mails te maken.</span><span class="sxs-lookup"><span data-stu-id="e1be4-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="e1be4-138">Selecteer **Kenmerk toevoegen** om deze velden toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="e1be4-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="e1be4-139">Selecteer de segmenten die u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="e1be4-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="e1be4-140">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="e1be4-140">Select **Save**.</span></span>

<span data-ttu-id="e1be4-141">Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="e1be4-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e1be4-142">De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e1be4-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e1be4-143">U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e1be4-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e1be4-144">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="e1be4-144">Data privacy and compliance</span></span>

<span data-ttu-id="e1be4-145">Wanneer u Dynamics 365 Customer Insights inschakelt om gegevens te verzenden naar Sendinblue, staat u de overdracht van gegevens buiten de nalevingsgrens toe voor Dynamics 365 Customer Insights, inclusief mogelijk gevoelige gegevens zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="e1be4-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e1be4-146">Microsoft zal dergelijke gegevens in uw opdracht overdragen, maar u bent er zelf verantwoordelijk voor dat Sendinblue voldoet aan alle privacy- of beveiligingsverplichtingen die u hebt.</span><span class="sxs-lookup"><span data-stu-id="e1be4-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e1be4-147">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e1be4-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e1be4-148">Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="e1be4-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
