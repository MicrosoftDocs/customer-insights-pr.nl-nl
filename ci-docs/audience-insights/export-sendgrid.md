---
title: Customer Insights-gegevens exporteren naar SendGrid
description: Leer hoe u de verbinding configureert en exporteert naar SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a4c64cf77c682e07f3d0759c43355336b5806fc8
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759759"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="8e02e-103">Segmenten exporteren naar SendGrid (preview)</span><span class="sxs-lookup"><span data-stu-id="8e02e-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="8e02e-104">Exporteer segmenten van geharmoniseerde klantprofielen naar SendGrid en gebruik ze voor campagnes en e-mailmarketing in SendGrid.</span><span class="sxs-lookup"><span data-stu-id="8e02e-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="8e02e-105">Vereisten voor een verbinding</span><span class="sxs-lookup"><span data-stu-id="8e02e-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="8e02e-106">U hebt een [SendGrid-account](https://sendgrid.com/) en bijbehorende beheerdersreferenties nodig.</span><span class="sxs-lookup"><span data-stu-id="8e02e-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="8e02e-107">Er zijn bestaande contactpersonenlijsten met bijbehorende id's in SendGrid.</span><span class="sxs-lookup"><span data-stu-id="8e02e-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="8e02e-108">Zie [SendGrid - Contactpersonen beheren](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)​voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8e02e-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="8e02e-109">U hebt [geconfigureerde segmenten](segments.md) in doelgroepinzichten.</span><span class="sxs-lookup"><span data-stu-id="8e02e-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="8e02e-110">Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="8e02e-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8e02e-111">Bekende beperkingen</span><span class="sxs-lookup"><span data-stu-id="8e02e-111">Known limitations</span></span>

- <span data-ttu-id="8e02e-112">Tot 100.000 profielen in totaal naar SendGrid.</span><span class="sxs-lookup"><span data-stu-id="8e02e-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="8e02e-113">Exporteren naar SendGrid is beperkt tot segmenten.</span><span class="sxs-lookup"><span data-stu-id="8e02e-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="8e02e-114">Het exporteren van maximaal 100.000 profielen naar SendGrid kan enkele uren duren.</span><span class="sxs-lookup"><span data-stu-id="8e02e-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="8e02e-115">Het aantal profielen dat u naar SendGrid kunt exporteren, is afhankelijk van uw contract met SendGrid.</span><span class="sxs-lookup"><span data-stu-id="8e02e-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="8e02e-116">Verbinding instellen met SendGrid</span><span class="sxs-lookup"><span data-stu-id="8e02e-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="8e02e-117">Ga naar **Beheerder** > **Verbindingen**.</span><span class="sxs-lookup"><span data-stu-id="8e02e-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="8e02e-118">Selecteer **Verbinding toevoegen** en kies **SendGrid** om de verbinding te configureren.</span><span class="sxs-lookup"><span data-stu-id="8e02e-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="8e02e-119">Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="8e02e-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="8e02e-120">De naam en het type verbinding beschrijven deze verbinding.</span><span class="sxs-lookup"><span data-stu-id="8e02e-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="8e02e-121">We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.</span><span class="sxs-lookup"><span data-stu-id="8e02e-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="8e02e-122">Kies wie deze verbinding kan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="8e02e-122">Choose who can use this connection.</span></span> <span data-ttu-id="8e02e-123">Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling.</span><span class="sxs-lookup"><span data-stu-id="8e02e-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="8e02e-124">Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8e02e-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="8e02e-125">Voer uw **SendGrid API-sleutel** [SendGrid API-sleutel](https://sendgrid.com/docs/ui/account-and-settings/api-keys/) in.</span><span class="sxs-lookup"><span data-stu-id="8e02e-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="8e02e-126">Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="8e02e-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8e02e-127">Selecteer **Verbinden** om de verbinding met SendGrid te initialiseren.</span><span class="sxs-lookup"><span data-stu-id="8e02e-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="8e02e-128">Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.</span><span class="sxs-lookup"><span data-stu-id="8e02e-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="8e02e-129">Selecteer **Opslaan** om de verbinding te voltooien.</span><span class="sxs-lookup"><span data-stu-id="8e02e-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="8e02e-130">Een export configureren</span><span class="sxs-lookup"><span data-stu-id="8e02e-130">Configure an export</span></span>

<span data-ttu-id="8e02e-131">U kunt deze export configureren als u toegang hebt tot een verbinding van dit type.</span><span class="sxs-lookup"><span data-stu-id="8e02e-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="8e02e-132">Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8e02e-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="8e02e-133">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="8e02e-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8e02e-134">Selecteer **Bestemming toevoegen** om een nieuwe export te maken.</span><span class="sxs-lookup"><span data-stu-id="8e02e-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="8e02e-135">Kies in het veld **Verbinding voor export** een verbinding uit de sectie SendGrid.</span><span class="sxs-lookup"><span data-stu-id="8e02e-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="8e02e-136">Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="8e02e-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="8e02e-137">Voer uw **[SendGrid-lijst-id](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)** in.</span><span class="sxs-lookup"><span data-stu-id="8e02e-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="8e02e-138">Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant.</span><span class="sxs-lookup"><span data-stu-id="8e02e-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="8e02e-139">Herhaal dezelfde stappen voor andere optionele velden, zoals **Voornaam**, **Achternaam**, **Land/regio**, **Staat**, **Plaats** en **Postcode**.</span><span class="sxs-lookup"><span data-stu-id="8e02e-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="8e02e-140">Selecteer de segmenten die u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="8e02e-140">Select the segments you want to export.</span></span> <span data-ttu-id="8e02e-141">Wij **raden u sterk aan niet meer dan 100.000 klantprofielen in totaal te exporteren** naar SendGrid.</span><span class="sxs-lookup"><span data-stu-id="8e02e-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="8e02e-142">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="8e02e-142">Select **Save**.</span></span>

<span data-ttu-id="8e02e-143">Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="8e02e-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="8e02e-144">De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8e02e-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8e02e-145">U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="8e02e-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8e02e-146">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="8e02e-146">Data privacy and compliance</span></span>

<span data-ttu-id="8e02e-147">Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar SendGrid te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="8e02e-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8e02e-148">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat SendGrid voldoet aan uw privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="8e02e-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="8e02e-149">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8e02e-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8e02e-150">Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="8e02e-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]