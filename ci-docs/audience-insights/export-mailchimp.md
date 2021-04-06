---
title: Customer Insights-gegevens exporteren naar Mailchimp
description: Ontdek hoe u de verbinding met Mailchimp configureert.
ms.date: 10/26/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f86616731c3cc3d26370727103ea9c5d4288c8d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598195"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="46363-103">Connector voor Mailchimp (preview)</span><span class="sxs-lookup"><span data-stu-id="46363-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="46363-104">Exporteer segmenten van geharmoniseerde klantprofielen naar Mailchimp om nieuwsbrieven en e-mailcampagnes te maken.</span><span class="sxs-lookup"><span data-stu-id="46363-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="46363-105">Vereisten</span><span class="sxs-lookup"><span data-stu-id="46363-105">Prerequisites</span></span>

-   <span data-ttu-id="46363-106">U hebt een [Mailchimp-account](https://mailchimp.com/) en bijbehorende beheerdersreferenties nodig.</span><span class="sxs-lookup"><span data-stu-id="46363-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="46363-107">Er zijn bestaande doelgroepen met bijbehorende id's in Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="46363-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="46363-108">Zie [Mailchimp-doelgroepen](https://mailchimp.com/help/create-audience/) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="46363-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="46363-109">U hebt [geconfigureerde segmenten](segments.md)</span><span class="sxs-lookup"><span data-stu-id="46363-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="46363-110">Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="46363-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="46363-111">Verbinding maken met MailChimp</span><span class="sxs-lookup"><span data-stu-id="46363-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="46363-112">Ga naar **Beheer** > **Exportbestemmingen**.</span><span class="sxs-lookup"><span data-stu-id="46363-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="46363-113">Selecteer onder **Mailchimp** de optie **Instellen**.</span><span class="sxs-lookup"><span data-stu-id="46363-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="46363-114">Geef uw exportbestemming een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="46363-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="46363-115">Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="46363-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="46363-116">Voer uw **[Mailchimp-doelgroep-id](https://mailchimp.com/help/find-audience-id/)** in en selecteer **Verbinden** om de verbinding met Mailchimp te initialiseren.</span><span class="sxs-lookup"><span data-stu-id="46363-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="46363-117">Selecteer **Verifiëren met Mailchimp** en geef uw Mailchimp-referenties op.</span><span class="sxs-lookup"><span data-stu-id="46363-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="46363-118">Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.</span><span class="sxs-lookup"><span data-stu-id="46363-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Schermopname voor Mailchimp-verbinding exporteren":::

1. <span data-ttu-id="46363-120">Selecteer **Volgende** om de export te configureren.</span><span class="sxs-lookup"><span data-stu-id="46363-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="46363-121">De connector configureren</span><span class="sxs-lookup"><span data-stu-id="46363-121">Configure the connector</span></span>

1. <span data-ttu-id="46363-122">Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant.</span><span class="sxs-lookup"><span data-stu-id="46363-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="46363-123">Optioneel kunt u **Voornaam** en **Achternaam** exporteren als extra velden om meer gepersonaliseerde e-mails te maken.</span><span class="sxs-lookup"><span data-stu-id="46363-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="46363-124">Selecteer **Kenmerk toevoegen** om deze velden toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="46363-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="46363-125">Selecteer de segmenten die u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="46363-125">Select the segments you want to export.</span></span> <span data-ttu-id="46363-126">U kunt in totaal tot 1 miljoen klantprofielen exporteren naar Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="46363-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Velden en segmenten selecteren om naar Mailchimp te exporteren":::

1. <span data-ttu-id="46363-128">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="46363-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="46363-129">De gegevens exporteren</span><span class="sxs-lookup"><span data-stu-id="46363-129">Export the data</span></span>

<span data-ttu-id="46363-130">U kunt [gegevens op aanvraag exporteren](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="46363-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="46363-131">De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="46363-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="46363-132">In Mailchimp vindt u nu uw segmenten onder [Mailchimp-doelgroepen](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="46363-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="46363-133">Bekende beperkingen</span><span class="sxs-lookup"><span data-stu-id="46363-133">Known limitations</span></span>

- <span data-ttu-id="46363-134">Maximaal 1 miljoen profielen per export naar Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="46363-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="46363-135">Exporteren naar Mailchimp is beperkt tot segmenten.</span><span class="sxs-lookup"><span data-stu-id="46363-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="46363-136">Segmenten exporteren met in totaal 1 miljoen profielen kan tot drie uur duren vanwege beperkingen aan de providerzijde.</span><span class="sxs-lookup"><span data-stu-id="46363-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="46363-137">Het aantal profielen dat u naar Mailchimp kunt exporteren, is afhankelijk van uw contract met Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="46363-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="46363-138">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="46363-138">Data privacy and compliance</span></span>

<span data-ttu-id="46363-139">Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar Mailchimp te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="46363-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="46363-140">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat Mailchimp voldoet aan uw privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="46363-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="46363-141">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="46363-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="46363-142">Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="46363-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]