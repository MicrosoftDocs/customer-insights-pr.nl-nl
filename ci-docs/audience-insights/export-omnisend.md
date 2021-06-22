---
title: Customer Insights-gegevens exporteren naar Omnisend
description: Leer hoe u de verbinding configureert en exporteert naar Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124475"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="2b941-103">Segmenten exporteren naar Omnisend (preview)</span><span class="sxs-lookup"><span data-stu-id="2b941-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="2b941-104">Exporteer segmenten van geharmoniseerde klantprofielen naar Omnisend en gebruik deze voor marketingactiviteiten.</span><span class="sxs-lookup"><span data-stu-id="2b941-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2b941-105">Vereisten</span><span class="sxs-lookup"><span data-stu-id="2b941-105">Prerequisites</span></span>

-   <span data-ttu-id="2b941-106">U hebt een [Omnisend-account](https://www.omnisend.com/) en bijbehorende beheerdersreferenties.</span><span class="sxs-lookup"><span data-stu-id="2b941-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="2b941-107">U hebt [geconfigureerde segmenten](segments.md) in doelgroepinzichten.</span><span class="sxs-lookup"><span data-stu-id="2b941-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="2b941-108">Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="2b941-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="2b941-109">Bekende beperkingen</span><span class="sxs-lookup"><span data-stu-id="2b941-109">Known limitations</span></span>

- <span data-ttu-id="2b941-110">U kunt maximaal 1 miljoen profielen per export exporteren naar Omnisend en het kan tot 4 uur duren voordat dit is voltooid.</span><span class="sxs-lookup"><span data-stu-id="2b941-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="2b941-111">Exporteren naar Omnisend is beperkt tot segmenten.</span><span class="sxs-lookup"><span data-stu-id="2b941-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="2b941-112">Het aantal profielen dat u naar Omnisend kunt exporteren, is afhankelijk van uw contract met Omnisend.</span><span class="sxs-lookup"><span data-stu-id="2b941-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="2b941-113">Verbinding instellen met Omnisend</span><span class="sxs-lookup"><span data-stu-id="2b941-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="2b941-114">Ga naar **Beheerder** > **Verbindingen**.</span><span class="sxs-lookup"><span data-stu-id="2b941-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="2b941-115">Selecteer **Verbinding toevoegen** en kies **Omnisend** om de verbinding te configureren.</span><span class="sxs-lookup"><span data-stu-id="2b941-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="2b941-116">Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="2b941-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="2b941-117">De naam en het type verbinding beschrijven deze verbinding.</span><span class="sxs-lookup"><span data-stu-id="2b941-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="2b941-118">We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.</span><span class="sxs-lookup"><span data-stu-id="2b941-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="2b941-119">Kies wie deze verbinding kan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="2b941-119">Choose who can use this connection.</span></span> <span data-ttu-id="2b941-120">Standaard zijn dit alleen beheerders.</span><span class="sxs-lookup"><span data-stu-id="2b941-120">By default it's only administrators.</span></span> <span data-ttu-id="2b941-121">Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2b941-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="2b941-122">Voer uw [Omnisend API-sleutel](https://support.omnisend.com/en/articles/1061890-generating-api-key) in.</span><span class="sxs-lookup"><span data-stu-id="2b941-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="2b941-123">Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="2b941-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="2b941-124">Selecteer **Verbinden** om de verbinding met Omnisend te initialiseren.</span><span class="sxs-lookup"><span data-stu-id="2b941-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="2b941-125">Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.</span><span class="sxs-lookup"><span data-stu-id="2b941-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="2b941-126">Selecteer **Opslaan** om de verbinding te voltooien.</span><span class="sxs-lookup"><span data-stu-id="2b941-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="2b941-127">Een export configureren</span><span class="sxs-lookup"><span data-stu-id="2b941-127">Configure an export</span></span>

<span data-ttu-id="2b941-128">U kunt deze export configureren als u toegang hebt tot een verbinding van dit type.</span><span class="sxs-lookup"><span data-stu-id="2b941-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="2b941-129">Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2b941-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="2b941-130">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="2b941-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2b941-131">Selecteer **Bestemming toevoegen** om een nieuwe export te maken.</span><span class="sxs-lookup"><span data-stu-id="2b941-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="2b941-132">Kies in het veld **Verbinding voor export** een verbinding uit de sectie Omnisend.</span><span class="sxs-lookup"><span data-stu-id="2b941-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="2b941-133">Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="2b941-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="2b941-134">Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant.</span><span class="sxs-lookup"><span data-stu-id="2b941-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="2b941-135">Deze is vereist voor het exporteren van segmenten naar Omnisend.</span><span class="sxs-lookup"><span data-stu-id="2b941-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="2b941-136">Optioneel kunt u Voornaam, Achternaam, Adres, Land/regio, Staat, Plaats en Postcode exporteren om meer gepersonaliseerde e-mails te maken.</span><span class="sxs-lookup"><span data-stu-id="2b941-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="2b941-137">Selecteer **Kenmerk toevoegen** om deze velden toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="2b941-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="2b941-138">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="2b941-138">Select **Save**.</span></span>

<span data-ttu-id="2b941-139">Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="2b941-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="2b941-140">De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2b941-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2b941-141">U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="2b941-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2b941-142">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="2b941-142">Data privacy and compliance</span></span>

<span data-ttu-id="2b941-143">Wanneer u Dynamics 365 Customer Insights inschakelt om gegevens naar Ommisend te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, inclusief mogelijk gevoelige gegevens zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="2b941-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2b941-144">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent er verantwoordelijk voor dat Ommisend voldoet aan mogelijke privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="2b941-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="2b941-145">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2b941-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="2b941-146">Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="2b941-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
