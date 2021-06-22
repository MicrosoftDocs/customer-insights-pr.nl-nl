---
title: Customer Insights-gegevens exporteren naar Microsoft Advertising
description: Leer hoe u de verbinding configureert en exporteert naar Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124474"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="b61bc-103">Segmenten exporteren naar Microsoft Advertising (preview)</span><span class="sxs-lookup"><span data-stu-id="b61bc-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="b61bc-104">Exporteer Customer Insights-segmenten naar Microsoft Advertising om doelgroepen met overeenkomende klanten te maken.</span><span class="sxs-lookup"><span data-stu-id="b61bc-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="b61bc-105">Gebruik deze doelgroepen voor uw advertentiecampagnes.</span><span class="sxs-lookup"><span data-stu-id="b61bc-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b61bc-106">Vereisten</span><span class="sxs-lookup"><span data-stu-id="b61bc-106">Prerequisites</span></span>

-   <span data-ttu-id="b61bc-107">Een [Microsoft Advertising-account](https://ads.microsoft.com/) en bijbehorende beheerdersreferenties.</span><span class="sxs-lookup"><span data-stu-id="b61bc-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="b61bc-108">U hebt de gebruiksvoorwaarden voor klantenafstemming geaccepteerd.</span><span class="sxs-lookup"><span data-stu-id="b61bc-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="b61bc-109">[Geconfigureerde segmenten](segments.md) in doelgroepinzichten.</span><span class="sxs-lookup"><span data-stu-id="b61bc-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="b61bc-110">Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld met een e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="b61bc-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b61bc-111">Bekende beperkingen</span><span class="sxs-lookup"><span data-stu-id="b61bc-111">Known limitations</span></span>

- <span data-ttu-id="b61bc-112">U kunt maximaal 500.000 profielen per export exporteren naar Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="b61bc-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="b61bc-113">Exporteren naar Microsoft Advertising is beperkt tot segmenten.</span><span class="sxs-lookup"><span data-stu-id="b61bc-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="b61bc-114">Het exporteren van maximaal 500.000 profielen naar Microsoft Advertising kan tot 10 minuten duren.</span><span class="sxs-lookup"><span data-stu-id="b61bc-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="b61bc-115">De verbinding met Microsoft Advertising instellen</span><span class="sxs-lookup"><span data-stu-id="b61bc-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="b61bc-116">Ga naar **Beheerder** > **Verbindingen**.</span><span class="sxs-lookup"><span data-stu-id="b61bc-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b61bc-117">Selecteer **Verbinding toevoegen** en kies **Microsoft Advertising** om de verbinding te configureren.</span><span class="sxs-lookup"><span data-stu-id="b61bc-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="b61bc-118">Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="b61bc-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b61bc-119">De naam en het type verbinding beschrijven deze verbinding.</span><span class="sxs-lookup"><span data-stu-id="b61bc-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b61bc-120">We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.</span><span class="sxs-lookup"><span data-stu-id="b61bc-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b61bc-121">Kies wie deze verbinding kan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="b61bc-121">Choose who can use this connection.</span></span> <span data-ttu-id="b61bc-122">De standaardoptie is beheerders.</span><span class="sxs-lookup"><span data-stu-id="b61bc-122">The default is administrators.</span></span> <span data-ttu-id="b61bc-123">Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b61bc-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b61bc-124">Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="b61bc-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b61bc-125">Selecteer **Verbinden** om de verbinding met Microsoft Advertising te initialiseren.</span><span class="sxs-lookup"><span data-stu-id="b61bc-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="b61bc-126">Selecteer **Verifiëren met Microsoft Advertising** en geef uw beheerdersreferenties voor Microsoft Advertising op.</span><span class="sxs-lookup"><span data-stu-id="b61bc-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="b61bc-127">Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.</span><span class="sxs-lookup"><span data-stu-id="b61bc-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="b61bc-128">Selecteer **Opslaan** om de verbinding te voltooien.</span><span class="sxs-lookup"><span data-stu-id="b61bc-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="b61bc-129">Een export configureren</span><span class="sxs-lookup"><span data-stu-id="b61bc-129">Configure an export</span></span>

<span data-ttu-id="b61bc-130">U kunt deze export configureren als u toegang hebt tot een verbinding van dit type.</span><span class="sxs-lookup"><span data-stu-id="b61bc-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b61bc-131">Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b61bc-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b61bc-132">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="b61bc-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b61bc-133">Selecteer **Bestemming toevoegen** om een nieuwe export te maken.</span><span class="sxs-lookup"><span data-stu-id="b61bc-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b61bc-134">Kies in het veld **Verbinding voor export** een verbinding uit de sectie Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="b61bc-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="b61bc-135">Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="b61bc-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b61bc-136">Selecteer de segmenten die moeten worden geëxporteerd.</span><span class="sxs-lookup"><span data-stu-id="b61bc-136">Select the segments to export.</span></span> <span data-ttu-id="b61bc-137">De doelgroepen met overeenkomende klanten in Microsoft Advertising worden automatisch gemaakt met de naam van de segmenten die zijn geselecteerd voor export.</span><span class="sxs-lookup"><span data-stu-id="b61bc-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="b61bc-138">Elk segment resulteert in een afzonderlijke doelgroep met overeenkomende klanten.</span><span class="sxs-lookup"><span data-stu-id="b61bc-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="b61bc-139">Voer uw **klant-id en account-id voor Microsoft Advertising** in.</span><span class="sxs-lookup"><span data-stu-id="b61bc-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="b61bc-140">U vindt de klant-id (`cid`) en account-id (`aid`) in de parameters van de URL wanneer u bent aangemeld bij Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="b61bc-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="b61bc-141">Selecteer in het veld **E-mail** van de sectie **Gegevensvergelijking** het veld in uw geharmoniseerde klantprofiel met het e-mailadres van een klant.</span><span class="sxs-lookup"><span data-stu-id="b61bc-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="b61bc-142">Dit is vereist voor het exporteren van segmenten naar Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="b61bc-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="b61bc-143">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b61bc-143">Select **Save**.</span></span>

<span data-ttu-id="b61bc-144">Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="b61bc-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b61bc-145">De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b61bc-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b61bc-146">U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b61bc-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b61bc-147">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="b61bc-147">Data privacy and compliance</span></span>

<span data-ttu-id="b61bc-148">Wanneer u Dynamics 365 Customer Insights inschakelt om gegevens naar Microsoft Advertising te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, inclusief mogelijk gevoelige gegevens zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="b61bc-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b61bc-149">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent er verantwoordelijk voor dat Microsoft Advertising voldoet aan mogelijke privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="b61bc-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b61bc-150">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b61bc-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="b61bc-151">Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="b61bc-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
