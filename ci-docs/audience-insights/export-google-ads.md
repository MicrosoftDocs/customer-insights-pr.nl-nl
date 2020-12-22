---
title: Customer Insights-gegevens exporteren naar Google Ads
description: Ontdek hoe u de verbinding met Google Ads configureert.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568424"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="022cb-103">Connector voor Google Ads (preview)</span><span class="sxs-lookup"><span data-stu-id="022cb-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="022cb-104">Exporteer segmenten van geharmoniseerde klantprofielen naar de Google Ads-doelgroeplijst en gebruik ze om te adverteren op Google Zoeken, Gmail, YouTube en Google Display Netwerk.</span><span class="sxs-lookup"><span data-stu-id="022cb-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="022cb-105">Vereisten</span><span class="sxs-lookup"><span data-stu-id="022cb-105">Prerequisites</span></span>

-   <span data-ttu-id="022cb-106">U hebt een [Google Ads-account](https://ads.google.com/) en bijbehorende beheerdersreferenties nodig.</span><span class="sxs-lookup"><span data-stu-id="022cb-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="022cb-107">Er zijn bestaande doelgroepen met bijbehorende id's in Google Ads.</span><span class="sxs-lookup"><span data-stu-id="022cb-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="022cb-108">Zie [Google Ads-doelgroepen](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="022cb-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="022cb-109">U hebt [geconfigureerde segmenten](segments.md)</span><span class="sxs-lookup"><span data-stu-id="022cb-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="022cb-110">Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten velden voor e-mailadres, voornaam en achternaam</span><span class="sxs-lookup"><span data-stu-id="022cb-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="022cb-111">Verbinding maken met Google Ads</span><span class="sxs-lookup"><span data-stu-id="022cb-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="022cb-112">Ga naar **Beheer** > **Exportbestemmingen**.</span><span class="sxs-lookup"><span data-stu-id="022cb-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="022cb-113">Selecteer onder **Google Ads** de optie **Instellen**.</span><span class="sxs-lookup"><span data-stu-id="022cb-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="022cb-114">Geef uw exportbestemming een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="022cb-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="022cb-115">Voer uw **[Google Ads-klant-id](https://support.google.com/google-ads/answer/1704344)** in.</span><span class="sxs-lookup"><span data-stu-id="022cb-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="022cb-116">Voer uw **[Door Google Ads goedgekeurde ontwikkelaarstoken](https://developers.google.com/google-ads/api/docs/first-call/dev-token)** in.</span><span class="sxs-lookup"><span data-stu-id="022cb-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="022cb-117">Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="022cb-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="022cb-118">Voer uw **[Google Ads-doelgroep-id](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** in en selecteer **Verbinden** om de verbinding met Google Ads te initialiseren.</span><span class="sxs-lookup"><span data-stu-id="022cb-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="022cb-119">Selecteer **Verifiëren met Google Ads** en geef uw Google Ads-referenties op.</span><span class="sxs-lookup"><span data-stu-id="022cb-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="022cb-120">Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.</span><span class="sxs-lookup"><span data-stu-id="022cb-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Schermopname voor Google Ads-verbinding exporteren":::

1. <span data-ttu-id="022cb-122">Selecteer **Volgende** om de export te configureren.</span><span class="sxs-lookup"><span data-stu-id="022cb-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="022cb-123">De connector configureren</span><span class="sxs-lookup"><span data-stu-id="022cb-123">Configure the connector</span></span>

1. <span data-ttu-id="022cb-124">Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant.</span><span class="sxs-lookup"><span data-stu-id="022cb-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="022cb-125">Herhaal dezelfde stappen voor de velden **Voornaam** en **Achternaam**.</span><span class="sxs-lookup"><span data-stu-id="022cb-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="022cb-126">Selecteer de segmenten die u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="022cb-126">Select the segments you want to export.</span></span> <span data-ttu-id="022cb-127">U kunt in totaal tot 1 miljoen klantprofielen exporteren naar Google Ads.</span><span class="sxs-lookup"><span data-stu-id="022cb-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="022cb-128">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="022cb-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="022cb-129">De gegevens exporteren</span><span class="sxs-lookup"><span data-stu-id="022cb-129">Export the data</span></span>

<span data-ttu-id="022cb-130">U kunt [gegevens op aanvraag exporteren](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="022cb-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="022cb-131">De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="022cb-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="022cb-132">In Google Ads vindt u nu uw segmenten onder [Google Ads-doelgroepen](https://support.google.com/google-ads/answer/7558048?hl=en/).</span><span class="sxs-lookup"><span data-stu-id="022cb-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="022cb-133">Bekende beperkingen</span><span class="sxs-lookup"><span data-stu-id="022cb-133">Known limitations</span></span>

- <span data-ttu-id="022cb-134">Maximaal 1 miljoen profielen per export naar Google Ads.</span><span class="sxs-lookup"><span data-stu-id="022cb-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="022cb-135">Exporteren naar Google Ads is beperkt tot segmenten.</span><span class="sxs-lookup"><span data-stu-id="022cb-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="022cb-136">Segmenten exporteren met in totaal 1 miljoen profielen kan tot 5 minuten duren vanwege beperkingen aan de providerzijde.</span><span class="sxs-lookup"><span data-stu-id="022cb-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="022cb-137">Het matchen in Google Ads kan tot 48 uur duren.</span><span class="sxs-lookup"><span data-stu-id="022cb-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="022cb-138">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="022cb-138">Data privacy and compliance</span></span>

<span data-ttu-id="022cb-139">Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar Google Ads te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="022cb-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="022cb-140">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat Google Ads voldoet aan uw privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="022cb-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="022cb-141">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="022cb-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="022cb-142">Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="022cb-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
