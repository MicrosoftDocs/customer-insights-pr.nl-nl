---
title: Customer Insights-gegevens exporteren naar DotDigital
description: Leer hoe u de verbinding configureert en exporteert naar DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d08504856e1c673ef32433b83bf491d7f4e8cee4
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976840"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a><span data-ttu-id="f7575-103">Segmentlijsten exporteren naar DotDigital (preview)</span><span class="sxs-lookup"><span data-stu-id="f7575-103">Export segment lists to DotDigital (preview)</span></span>

<span data-ttu-id="f7575-104">Exporteer segmenten van geharmoniseerde klantprofielen naar DotDigital-adresboeken en gebruik ze voor campagnes, e-mailmarketing en om klantsegmenten op te bouwen met DotDigital.</span><span class="sxs-lookup"><span data-stu-id="f7575-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="f7575-105">Vereisten voor een verbinding</span><span class="sxs-lookup"><span data-stu-id="f7575-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="f7575-106">U hebt een [DotDigital-account](https://dotdigital.com/) en bijbehorende beheerdersreferenties nodig.</span><span class="sxs-lookup"><span data-stu-id="f7575-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f7575-107">Er zijn bestaande adresboeken met bijbehorende id's in DotDigital.</span><span class="sxs-lookup"><span data-stu-id="f7575-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="f7575-108">De id is te vinden in de URL wanneer u een adresboek selecteert en opent.</span><span class="sxs-lookup"><span data-stu-id="f7575-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="f7575-109">Zie [DotDigital-adresboeken](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f7575-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="f7575-110">U hebt [geconfigureerde segmenten](segments.md) in doelgroepinzichten.</span><span class="sxs-lookup"><span data-stu-id="f7575-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="f7575-111">Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="f7575-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f7575-112">Bekende beperkingen</span><span class="sxs-lookup"><span data-stu-id="f7575-112">Known limitations</span></span>

- <span data-ttu-id="f7575-113">Maximaal 1 miljoen profielen per export naar DotDigital.</span><span class="sxs-lookup"><span data-stu-id="f7575-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="f7575-114">Exporteren naar DotDigital is beperkt tot segmenten.</span><span class="sxs-lookup"><span data-stu-id="f7575-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="f7575-115">Segmenten exporteren met in totaal 1 miljoen profielen kan tot 3 uur duren vanwege beperkingen aan de providerzijde.</span><span class="sxs-lookup"><span data-stu-id="f7575-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="f7575-116">Het aantal profielen dat u naar DotDigital kunt exporteren, is afhankelijk van uw contract met DotDigital.</span><span class="sxs-lookup"><span data-stu-id="f7575-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="f7575-117">Verbinding met DotDigital instellen</span><span class="sxs-lookup"><span data-stu-id="f7575-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="f7575-118">Ga naar **Beheerder** > **Verbindingen**.</span><span class="sxs-lookup"><span data-stu-id="f7575-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f7575-119">Selecteer **Verbinding toevoegen** en kies **DotDigital** om de verbinding te configureren.</span><span class="sxs-lookup"><span data-stu-id="f7575-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="f7575-120">Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="f7575-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f7575-121">De naam en het type verbinding beschrijven deze verbinding.</span><span class="sxs-lookup"><span data-stu-id="f7575-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f7575-122">We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.</span><span class="sxs-lookup"><span data-stu-id="f7575-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f7575-123">Kies wie deze verbinding kan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="f7575-123">Choose who can use this connection.</span></span> <span data-ttu-id="f7575-124">Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling.</span><span class="sxs-lookup"><span data-stu-id="f7575-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f7575-125">Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f7575-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f7575-126">Voer uw **DotDigital-gebruikersnaam en wachtwoord** in.</span><span class="sxs-lookup"><span data-stu-id="f7575-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="f7575-127">Voer uw **[DotDigital adresboek-id](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)** in.</span><span class="sxs-lookup"><span data-stu-id="f7575-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="f7575-128">Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="f7575-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f7575-129">Selecteer **Verbinden** om de verbinding met DotDigital te initialiseren.</span><span class="sxs-lookup"><span data-stu-id="f7575-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="f7575-130">Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.</span><span class="sxs-lookup"><span data-stu-id="f7575-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="f7575-131">Selecteer **Opslaan** om de verbinding te voltooien.</span><span class="sxs-lookup"><span data-stu-id="f7575-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="f7575-132">Een export configureren</span><span class="sxs-lookup"><span data-stu-id="f7575-132">Configure an export</span></span>

<span data-ttu-id="f7575-133">U kunt deze export configureren als u toegang hebt tot een verbinding van dit type.</span><span class="sxs-lookup"><span data-stu-id="f7575-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f7575-134">Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f7575-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f7575-135">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="f7575-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f7575-136">Selecteer **Bestemming toevoegen** om een nieuwe export te maken.</span><span class="sxs-lookup"><span data-stu-id="f7575-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f7575-137">Kies in het veld **Verbinding voor export** een verbinding uit de sectie DotDigital.</span><span class="sxs-lookup"><span data-stu-id="f7575-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="f7575-138">Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="f7575-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="f7575-139">Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant.</span><span class="sxs-lookup"><span data-stu-id="f7575-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="f7575-140">Herhaal dezelfde stappen voor andere optionele velden, zoals **Voornaam**, **Achternaam**, **Voor- en achternaam**, **Geslacht** en **Postcode**.</span><span class="sxs-lookup"><span data-stu-id="f7575-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="f7575-141">Selecteer de segmenten die u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="f7575-141">Select the segments you want to export.</span></span> <span data-ttu-id="f7575-142">U kunt in totaal tot 1 miljoen klantprofielen exporteren naar DotDigital.</span><span class="sxs-lookup"><span data-stu-id="f7575-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="f7575-143">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f7575-143">Select **Save**.</span></span>

<span data-ttu-id="f7575-144">Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="f7575-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f7575-145">De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f7575-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f7575-146">U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f7575-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="f7575-147">In DotDigital kunt u nu uw segmenten vinden in [DotDigital-adresboeken](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="f7575-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f7575-148">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="f7575-148">Data privacy and compliance</span></span>

<span data-ttu-id="f7575-149">Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar DotDigital te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="f7575-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f7575-150">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat DotDigital voldoet aan uw privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="f7575-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="f7575-151">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f7575-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f7575-152">Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="f7575-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
