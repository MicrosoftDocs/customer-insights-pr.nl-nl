---
title: Customer Insights-gegevens exporteren naar SendGrid
description: Ontdek hoe u de verbinding met SendGrid configureert.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597275"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="ed86e-103">Connector voor SendGrid (preview)</span><span class="sxs-lookup"><span data-stu-id="ed86e-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="ed86e-104">Exporteer segmenten van geharmoniseerde klantprofielen naar SendGrid en gebruik ze voor campagnes en e-mailmarketing in SendGrid.</span><span class="sxs-lookup"><span data-stu-id="ed86e-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="ed86e-105">Vereisten</span><span class="sxs-lookup"><span data-stu-id="ed86e-105">Prerequisites</span></span>

-   <span data-ttu-id="ed86e-106">U hebt een [SendGrid-account](https://sendgrid.com/) en bijbehorende beheerdersreferenties nodig.</span><span class="sxs-lookup"><span data-stu-id="ed86e-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ed86e-107">Er zijn bestaande contactpersonenlijsten met bijbehorende id's in SendGrid.</span><span class="sxs-lookup"><span data-stu-id="ed86e-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="ed86e-108">Zie [SendGrid - Contactpersonen beheren](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)​voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ed86e-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="ed86e-109">U hebt [geconfigureerde segmenten](segments.md) in doelgroepinzichten.</span><span class="sxs-lookup"><span data-stu-id="ed86e-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ed86e-110">Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="ed86e-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="ed86e-111">Verbinding maken met SendGrid</span><span class="sxs-lookup"><span data-stu-id="ed86e-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="ed86e-112">Ga naar **Beheer** > **Exportbestemmingen**.</span><span class="sxs-lookup"><span data-stu-id="ed86e-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ed86e-113">Selecteer onder **SendGrid** de optie **Instellen**.</span><span class="sxs-lookup"><span data-stu-id="ed86e-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="ed86e-114">Geef uw exportbestemming een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="ed86e-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="SendGrid-configuratiedeelvenster voor exporteren.":::

1. <span data-ttu-id="ed86e-116">Voer uw **SendGrid API-sleutel** [SendGrid API-sleutel](https://sendgrid.com/docs/ui/account-and-settings/api-keys/) in.</span><span class="sxs-lookup"><span data-stu-id="ed86e-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="ed86e-117">Voer uw **[SendGrid-lijst-id](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)** in.</span><span class="sxs-lookup"><span data-stu-id="ed86e-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="ed86e-118">Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="ed86e-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ed86e-119">Selecteer **Verbinden** om de verbinding met SendGrid te initialiseren.</span><span class="sxs-lookup"><span data-stu-id="ed86e-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="ed86e-120">Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.</span><span class="sxs-lookup"><span data-stu-id="ed86e-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ed86e-121">Selecteer **Volgende** om de export te configureren.</span><span class="sxs-lookup"><span data-stu-id="ed86e-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="ed86e-122">De connector configureren</span><span class="sxs-lookup"><span data-stu-id="ed86e-122">Configure the connector</span></span>

1. <span data-ttu-id="ed86e-123">Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant.</span><span class="sxs-lookup"><span data-stu-id="ed86e-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ed86e-124">Herhaal dezelfde stappen voor andere optionele velden, zoals **Voornaam**, **Achternaam**, **Land/regio**, **Staat**, **Plaats** en **Postcode**.</span><span class="sxs-lookup"><span data-stu-id="ed86e-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="ed86e-125">Selecteer de segmenten die u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="ed86e-125">Select the segments you want to export.</span></span> <span data-ttu-id="ed86e-126">Wij **raden u sterk aan niet meer dan 100.000 klantprofielen in totaal te exporteren** naar SendGrid.</span><span class="sxs-lookup"><span data-stu-id="ed86e-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="ed86e-127">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ed86e-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="ed86e-128">De gegevens exporteren</span><span class="sxs-lookup"><span data-stu-id="ed86e-128">Export the data</span></span>

<span data-ttu-id="ed86e-129">U kunt [gegevens op aanvraag exporteren](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="ed86e-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="ed86e-130">De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ed86e-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ed86e-131">Bekende beperkingen</span><span class="sxs-lookup"><span data-stu-id="ed86e-131">Known limitations</span></span>

- <span data-ttu-id="ed86e-132">Tot 100.000 profielen in totaal naar SendGrid.</span><span class="sxs-lookup"><span data-stu-id="ed86e-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="ed86e-133">Exporteren naar SendGrid is beperkt tot segmenten.</span><span class="sxs-lookup"><span data-stu-id="ed86e-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="ed86e-134">Het exporteren van maximaal 100.000 profielen naar SendGrid kan enkele uren duren.</span><span class="sxs-lookup"><span data-stu-id="ed86e-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="ed86e-135">Het aantal profielen dat u naar SendGrid kunt exporteren, is afhankelijk van uw contract met SendGrid.</span><span class="sxs-lookup"><span data-stu-id="ed86e-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ed86e-136">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="ed86e-136">Data privacy and compliance</span></span>

<span data-ttu-id="ed86e-137">Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar SendGrid te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="ed86e-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ed86e-138">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat SendGrid voldoet aan uw privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="ed86e-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="ed86e-139">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ed86e-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ed86e-140">Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="ed86e-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]