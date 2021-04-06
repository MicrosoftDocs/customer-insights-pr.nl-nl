---
title: Customer Insights-gegevens exporteren naar DotDigital
description: Ontdek hoe u de verbinding met DotDigital configureert.
ms.date: 11/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 51a28bdf0de34f0555d8ad7e3d13b2ef8911d417
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598011"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="9293a-103">Connector voor DotDigital (preview)</span><span class="sxs-lookup"><span data-stu-id="9293a-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="9293a-104">Exporteer segmenten van geharmoniseerde klantprofielen naar DotDigital-adresboeken en gebruik ze voor campagnes, e-mailmarketing en om klantsegmenten op te bouwen met DotDigital.</span><span class="sxs-lookup"><span data-stu-id="9293a-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="9293a-105">Vereisten</span><span class="sxs-lookup"><span data-stu-id="9293a-105">Prerequisites</span></span>

-   <span data-ttu-id="9293a-106">U hebt een [DotDigital-account](https://dotdigital.com/) en bijbehorende beheerdersreferenties nodig.</span><span class="sxs-lookup"><span data-stu-id="9293a-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="9293a-107">Er zijn bestaande adresboeken met bijbehorende id's in DotDigital.</span><span class="sxs-lookup"><span data-stu-id="9293a-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="9293a-108">De id is te vinden in de URL wanneer u een adresboek selecteert en opent.</span><span class="sxs-lookup"><span data-stu-id="9293a-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="9293a-109">Zie [DotDigital-adresboeken](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9293a-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="9293a-110">U hebt [geconfigureerde segmenten](segments.md) in doelgroepinzichten.</span><span class="sxs-lookup"><span data-stu-id="9293a-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="9293a-111">Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="9293a-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="9293a-112">Verbinden met DotDigital</span><span class="sxs-lookup"><span data-stu-id="9293a-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="9293a-113">Ga naar **Beheer** > **Exportbestemmingen**.</span><span class="sxs-lookup"><span data-stu-id="9293a-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="9293a-114">Selecteer onder **DotDigital** de optie **Instellen**.</span><span class="sxs-lookup"><span data-stu-id="9293a-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="9293a-115">Geef uw exportbestemming een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="9293a-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Configuratiedeelvenster voor DotDigital-export.":::

1. <span data-ttu-id="9293a-117">Voer uw **DotDigital-gebruikersnaam en wachtwoord** in.</span><span class="sxs-lookup"><span data-stu-id="9293a-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="9293a-118">Voer uw **[DotDigital adresboek-id](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)** in.</span><span class="sxs-lookup"><span data-stu-id="9293a-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="9293a-119">Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="9293a-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="9293a-120">Selecteer **Verbinden** om de verbinding met DotDigital te initialiseren.</span><span class="sxs-lookup"><span data-stu-id="9293a-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="9293a-121">Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.</span><span class="sxs-lookup"><span data-stu-id="9293a-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="9293a-122">Selecteer **Volgende** om de export te configureren.</span><span class="sxs-lookup"><span data-stu-id="9293a-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="9293a-123">De connector configureren</span><span class="sxs-lookup"><span data-stu-id="9293a-123">Configure the connector</span></span>

1. <span data-ttu-id="9293a-124">Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant.</span><span class="sxs-lookup"><span data-stu-id="9293a-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="9293a-125">Herhaal dezelfde stappen voor andere optionele velden, zoals **Voornaam**, **Achternaam**, **Voor- en achternaam**, **Geslacht** en **Postcode**.</span><span class="sxs-lookup"><span data-stu-id="9293a-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="9293a-126">Selecteer de segmenten die u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="9293a-126">Select the segments you want to export.</span></span> <span data-ttu-id="9293a-127">U kunt in totaal tot 1 miljoen klantprofielen exporteren naar DotDigital.</span><span class="sxs-lookup"><span data-stu-id="9293a-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="9293a-128">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="9293a-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="9293a-129">De gegevens exporteren</span><span class="sxs-lookup"><span data-stu-id="9293a-129">Export the data</span></span>

<span data-ttu-id="9293a-130">U kunt [gegevens op aanvraag exporteren](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="9293a-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="9293a-131">De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9293a-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9293a-132">In DotDigital kunt u nu uw segmenten vinden in [DotDigital-adresboeken](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="9293a-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="9293a-133">Bekende beperkingen</span><span class="sxs-lookup"><span data-stu-id="9293a-133">Known limitations</span></span>

- <span data-ttu-id="9293a-134">Maximaal 1 miljoen profielen per export naar DotDigital.</span><span class="sxs-lookup"><span data-stu-id="9293a-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="9293a-135">Exporteren naar DotDigital is beperkt tot segmenten.</span><span class="sxs-lookup"><span data-stu-id="9293a-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="9293a-136">Segmenten exporteren met in totaal 1 miljoen profielen kan tot 3 uur duren vanwege beperkingen aan de providerzijde.</span><span class="sxs-lookup"><span data-stu-id="9293a-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="9293a-137">Het aantal profielen dat u naar DotDigital kunt exporteren, is afhankelijk van uw contract met DotDigital.</span><span class="sxs-lookup"><span data-stu-id="9293a-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9293a-138">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="9293a-138">Data privacy and compliance</span></span>

<span data-ttu-id="9293a-139">Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar DotDigital te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="9293a-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9293a-140">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat DotDigital voldoet aan uw privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="9293a-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="9293a-141">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9293a-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="9293a-142">Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="9293a-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]