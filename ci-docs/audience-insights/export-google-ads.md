---
title: Customer Insights-gegevens exporteren naar Google Ads
description: Leer hoe u de verbinding configureert en exporteert naar Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f4c094e486577d00d8c0c64e8527829820b335f6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759687"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="cf4f5-103">Segmenten exporteren naar Google Ads (preview)</span><span class="sxs-lookup"><span data-stu-id="cf4f5-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="cf4f5-104">Exporteer segmenten van geharmoniseerde klantprofielen naar de Google Ads-doelgroeplijst en gebruik ze om te adverteren op Google Zoeken, Gmail, YouTube en Google Display Netwerk.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="cf4f5-105">Vereisten voor verbinding</span><span class="sxs-lookup"><span data-stu-id="cf4f5-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="cf4f5-106">U hebt een [Google Ads-account](https://ads.google.com/) en bijbehorende beheerdersreferenties nodig.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="cf4f5-107">U hebt een [goedgekeurd Google Ads-ontwikkelaarstoken](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span><span class="sxs-lookup"><span data-stu-id="cf4f5-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span></span> 
-   <span data-ttu-id="cf4f5-108">U voldoet aan de eisen van het [beleid inzake klantafstemming](https://support.google.com/adspolicy/answer/6299717)</span><span class="sxs-lookup"><span data-stu-id="cf4f5-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717)</span></span>
-   <span data-ttu-id="cf4f5-109">U voldoet aan de eisen van de [hermarketinglijstformaten](https://support.google.com/google-ads/answer/7558048)</span><span class="sxs-lookup"><span data-stu-id="cf4f5-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048)</span></span> 

-   <span data-ttu-id="cf4f5-110">Er zijn bestaande doelgroepen met bijbehorende id's in Google Ads.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="cf4f5-111">Zie [Google Ads-doelgroepen](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="cf4f5-112">U hebt [geconfigureerde segmenten](segments.md)</span><span class="sxs-lookup"><span data-stu-id="cf4f5-112">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="cf4f5-113">Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten velden voor e-mailadres, voornaam en achternaam</span><span class="sxs-lookup"><span data-stu-id="cf4f5-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="known-limitations"></a><span data-ttu-id="cf4f5-114">Bekende beperkingen</span><span class="sxs-lookup"><span data-stu-id="cf4f5-114">Known limitations</span></span>

- <span data-ttu-id="cf4f5-115">Maximaal 1 miljoen profielen per export naar Google Ads.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="cf4f5-116">Exporteren naar Google Ads is beperkt tot segmenten.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="cf4f5-117">Segmenten exporteren met in totaal 1 miljoen profielen kan tot 5 minuten duren vanwege beperkingen aan de providerzijde.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="cf4f5-118">Het matchen in Google Ads kan tot 48 uur duren.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="cf4f5-119">Verbinding met Google Ads instellen</span><span class="sxs-lookup"><span data-stu-id="cf4f5-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="cf4f5-120">Ga naar **Beheerder** > **Verbindingen**.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="cf4f5-121">Selecteer **Verbinding toevoegen** en kies **Google Ads** om de verbinding te configureren.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="cf4f5-122">Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="cf4f5-123">De naam en het type verbinding beschrijven deze verbinding.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="cf4f5-124">We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="cf4f5-125">Kies wie deze verbinding kan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-125">Choose who can use this connection.</span></span> <span data-ttu-id="cf4f5-126">Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="cf4f5-127">Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="cf4f5-128">Voer uw **[Google Ads-klant-id](https://support.google.com/google-ads/answer/1704344)** in.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="cf4f5-129">Voer uw **[Door Google Ads goedgekeurde ontwikkelaarstoken](https://developers.google.com/google-ads/api/docs/first-call/dev-token)** in.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="cf4f5-130">Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="cf4f5-131">Selecteer **Verifiëren met Google Ads** en geef uw Google Ads-referenties op.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="cf4f5-132">Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="cf4f5-133">Selecteer **Opslaan** om de verbinding te voltooien.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="cf4f5-134">Een export configureren</span><span class="sxs-lookup"><span data-stu-id="cf4f5-134">Configure an export</span></span>

<span data-ttu-id="cf4f5-135">U kunt deze export configureren als u toegang hebt tot een verbinding van dit type.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="cf4f5-136">Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="cf4f5-137">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="cf4f5-138">Selecteer **Bestemming toevoegen** om een nieuwe export te maken.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="cf4f5-139">Kies in het veld **Verbinding voor export** een verbinding uit de sectie Google Ads.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="cf4f5-140">Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="cf4f5-141">Voer uw **[Google Ads-doelgroep-id](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** in en selecteer **Verbinden** om de verbinding met Google Ads te initialiseren.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="cf4f5-142">Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="cf4f5-143">Herhaal dezelfde stappen voor de velden **Voornaam** en **Achternaam**.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-143">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="cf4f5-144">Selecteer de segmenten die u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-144">Select the segments you want to export.</span></span> <span data-ttu-id="cf4f5-145">U kunt in totaal tot 1 miljoen klantprofielen exporteren naar Google Ads.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="cf4f5-146">Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="cf4f5-147">De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="cf4f5-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="cf4f5-148">U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="cf4f5-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="cf4f5-149">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="cf4f5-149">Data privacy and compliance</span></span>

<span data-ttu-id="cf4f5-150">Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar Google Ads te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="cf4f5-151">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat Google Ads voldoet aan uw privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="cf4f5-152">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="cf4f5-153">Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="cf4f5-153">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
