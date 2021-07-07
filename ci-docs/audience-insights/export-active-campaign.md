---
title: Gegevens uit Customer Insights exporteren naar ActiveCampaign
description: Leer hoe u de verbinding configureert en exporteert naar ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314599"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="00287-103">Segmenten exporteren naar ActiveCampaign (preview)</span><span class="sxs-lookup"><span data-stu-id="00287-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="00287-104">Exporteer segmenten van geharmoniseerde klantprofielen naar ActiveCampaign en gebruik ze voor marketingactiviteiten.</span><span class="sxs-lookup"><span data-stu-id="00287-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="00287-105">Vereisten</span><span class="sxs-lookup"><span data-stu-id="00287-105">Prerequisites</span></span>

-   <span data-ttu-id="00287-106">U hebt een [ActiveCampaign-account](https://www.activecampaign.com/) en bijbehorende beheerdersreferenties.</span><span class="sxs-lookup"><span data-stu-id="00287-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="00287-107">U hebt [geconfigureerde segmenten](segments.md) in doelgroepinzichten.</span><span class="sxs-lookup"><span data-stu-id="00287-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="00287-108">Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld met een e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="00287-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="00287-109">Bekende beperkingen</span><span class="sxs-lookup"><span data-stu-id="00287-109">Known limitations</span></span>

- <span data-ttu-id="00287-110">U kunt maximaal 1 miljoen profielen per export exporteren naar ActiveCampaign en het kan tot 90 minuten duren voordat de export is voltooid.</span><span class="sxs-lookup"><span data-stu-id="00287-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="00287-111">Het exporteren naar ActiveCampaign is beperkt tot segmenten.</span><span class="sxs-lookup"><span data-stu-id="00287-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="00287-112">Het aantal profielen dat u naar ActiveCampaign kunt exporteren, is afhankelijk van uw contract met ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="00287-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="00287-113">Verbinding instellen met ActiveCampaign</span><span class="sxs-lookup"><span data-stu-id="00287-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="00287-114">Ga naar **Beheerder** > **Verbindingen**.</span><span class="sxs-lookup"><span data-stu-id="00287-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="00287-115">Selecteer **Verbinding toevoegen** en kies **ActiveCampaign** om de verbinding te configureren.</span><span class="sxs-lookup"><span data-stu-id="00287-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="00287-116">Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="00287-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="00287-117">De naam en het type verbinding beschrijven deze verbinding.</span><span class="sxs-lookup"><span data-stu-id="00287-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="00287-118">We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.</span><span class="sxs-lookup"><span data-stu-id="00287-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="00287-119">Kies wie deze verbinding kan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="00287-119">Choose who can use this connection.</span></span> <span data-ttu-id="00287-120">Standaard zijn dit alleen beheerders.</span><span class="sxs-lookup"><span data-stu-id="00287-120">By default, it's only administrators.</span></span> <span data-ttu-id="00287-121">Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="00287-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="00287-122">Voer uw [ActiveCampaign API-sleutel en hostnaam van REST-eindpunt](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) in.</span><span class="sxs-lookup"><span data-stu-id="00287-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="00287-123">De hostnaam van het REST-eindpunt is alleen de hostnaam zonder https://.</span><span class="sxs-lookup"><span data-stu-id="00287-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="00287-124">Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="00287-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="00287-125">Selecteer **Verbinden** om de verbinding met ActiveCampaign te initialiseren.</span><span class="sxs-lookup"><span data-stu-id="00287-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="00287-126">Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.</span><span class="sxs-lookup"><span data-stu-id="00287-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="00287-127">Selecteer **Opslaan** om de verbinding te voltooien.</span><span class="sxs-lookup"><span data-stu-id="00287-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="00287-128">Een export configureren</span><span class="sxs-lookup"><span data-stu-id="00287-128">Configure an export</span></span>

<span data-ttu-id="00287-129">U kunt een export configureren als u toegang hebt tot een verbinding van dit type.</span><span class="sxs-lookup"><span data-stu-id="00287-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="00287-130">Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="00287-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="00287-131">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="00287-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="00287-132">Selecteer **Bestemming toevoegen** om een nieuwe export te maken.</span><span class="sxs-lookup"><span data-stu-id="00287-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="00287-133">Kies in het veld **Verbinding voor export** een verbinding uit de sectie ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="00287-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="00287-134">Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="00287-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="00287-135">Voer uw [**ActiveCampaign-lijst-id**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign) in.</span><span class="sxs-lookup"><span data-stu-id="00287-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="00287-136">Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant.</span><span class="sxs-lookup"><span data-stu-id="00287-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="00287-137">Dit is vereist voor het exporteren van segmenten naar ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="00287-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="00287-138">Optioneel kunt u voornaam, achternaam, en telefoon exporteren om meer gepersonaliseerde e-mails te maken.</span><span class="sxs-lookup"><span data-stu-id="00287-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="00287-139">Selecteer Kenmerk toevoegen om deze velden toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="00287-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="00287-140">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="00287-140">Select **Save**.</span></span>

<span data-ttu-id="00287-141">Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="00287-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="00287-142">De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="00287-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="00287-143">U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="00287-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="00287-144">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="00287-144">Data privacy and compliance</span></span>

<span data-ttu-id="00287-145">Wanneer u Dynamics 365 Customer Insights inschakelt om gegevens te verzenden naar ActiveCampaign, staat u de overdracht van gegevens buiten de nalevingsgrens toe voor Dynamics 365 Customer Insights, inclusief mogelijk gevoelige gegevens zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="00287-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="00287-146">Microsoft zal dergelijke gegevens in uw opdracht overdragen, maar u bent er zelf verantwoordelijk voor dat ActiveCampaign voldoet aan alle privacy- of beveiligingsverplichtingen die u hebt.</span><span class="sxs-lookup"><span data-stu-id="00287-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="00287-147">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="00287-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="00287-148">Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="00287-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
