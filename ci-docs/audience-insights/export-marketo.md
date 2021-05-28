---
title: Customer Insights-gegevens exporteren naar Marketo
description: Leer hoe u de verbinding configureert en exporteert naar Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b5a644e286bd44d4ebf7d1837255326c005b48d6
ms.sourcegitcommit: 74cd4fa9cbb784d9dff174c0eec7b4dcb408d66b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059310"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="1acc2-103">Segmenten exporteren naar Marketo (preview)</span><span class="sxs-lookup"><span data-stu-id="1acc2-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="1acc2-104">Exporteer segmenten van geharmoniseerde klantprofielen om campagnes te genereren, e-mailmarketing te bieden en specifieke groepen klanten te gebruiken met Marketo.</span><span class="sxs-lookup"><span data-stu-id="1acc2-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="1acc2-105">Vereisten voor verbinding</span><span class="sxs-lookup"><span data-stu-id="1acc2-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="1acc2-106">U hebt een [Marketo-account](https://login.marketo.com/) en bijbehorende beheerdersreferenties nodig.</span><span class="sxs-lookup"><span data-stu-id="1acc2-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="1acc2-107">Er zijn bestaande lijsten met bijbehorende id's in Marketo.</span><span class="sxs-lookup"><span data-stu-id="1acc2-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="1acc2-108">Zie [Marketo-lijsten](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1acc2-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="1acc2-109">U hebt [geconfigureerde segmenten](segments.md).</span><span class="sxs-lookup"><span data-stu-id="1acc2-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="1acc2-110">Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="1acc2-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1acc2-111">Bekende beperkingen</span><span class="sxs-lookup"><span data-stu-id="1acc2-111">Known limitations</span></span>

- <span data-ttu-id="1acc2-112">Maximaal 1 miljoen profielen per export naar Marketo.</span><span class="sxs-lookup"><span data-stu-id="1acc2-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="1acc2-113">Exporteren naar Marketo is beperkt tot segmenten.</span><span class="sxs-lookup"><span data-stu-id="1acc2-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="1acc2-114">Segmenten met in totaal 1 miljoen profielen exporteren kan tot 3 uur duren.</span><span class="sxs-lookup"><span data-stu-id="1acc2-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="1acc2-115">Het aantal profielen dat u naar Marketo kunt exporteren, is afhankelijk van uw contract met Marketo.</span><span class="sxs-lookup"><span data-stu-id="1acc2-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="1acc2-116">Verbinding met Marketo instellen</span><span class="sxs-lookup"><span data-stu-id="1acc2-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="1acc2-117">Ga naar **Beheerder** > **Verbindingen**.</span><span class="sxs-lookup"><span data-stu-id="1acc2-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1acc2-118">Selecteer **Verbinding toevoegen** en kies **Marketo** om de verbinding te configureren.</span><span class="sxs-lookup"><span data-stu-id="1acc2-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="1acc2-119">Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="1acc2-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1acc2-120">De naam en het type verbinding beschrijven deze verbinding.</span><span class="sxs-lookup"><span data-stu-id="1acc2-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1acc2-121">We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.</span><span class="sxs-lookup"><span data-stu-id="1acc2-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1acc2-122">Kies wie deze verbinding kan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="1acc2-122">Choose who can use this connection.</span></span> <span data-ttu-id="1acc2-123">Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling.</span><span class="sxs-lookup"><span data-stu-id="1acc2-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="1acc2-124">Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1acc2-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1acc2-125">Voer uw **[Marketo-client-id, clientgeheim en REST-eindpunt hostnaam](https://developers.marketo.com/rest-api/authentication/)** in.</span><span class="sxs-lookup"><span data-stu-id="1acc2-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span> <span data-ttu-id="1acc2-126">De hostnaam van het REST-eindpunt is alleen de hostnaam zonder `https://`.</span><span class="sxs-lookup"><span data-stu-id="1acc2-126">The REST Endpoint Hostname is the hostname only, without `https://`.</span></span> <span data-ttu-id="1acc2-127">Voorbeeld: `xyz-abc-123.mktorest.com`.</span><span class="sxs-lookup"><span data-stu-id="1acc2-127">Example: `xyz-abc-123.mktorest.com`.</span></span> 

1. <span data-ttu-id="1acc2-128">Selecteer **Ik ga akkoord** om de **Gegevensprivacy en naleving** te bevestigen en selecteer **Verbinden** om de verbinding met Marketo te initialiseren.</span><span class="sxs-lookup"><span data-stu-id="1acc2-128">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="1acc2-129">Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.</span><span class="sxs-lookup"><span data-stu-id="1acc2-129">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="1acc2-130">Selecteer **Opslaan** om de verbinding te voltooien.</span><span class="sxs-lookup"><span data-stu-id="1acc2-130">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="1acc2-131">Een export configureren</span><span class="sxs-lookup"><span data-stu-id="1acc2-131">Configure an export</span></span>

<span data-ttu-id="1acc2-132">U kunt deze export configureren als u toegang hebt tot een verbinding van dit type.</span><span class="sxs-lookup"><span data-stu-id="1acc2-132">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1acc2-133">Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1acc2-133">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1acc2-134">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="1acc2-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1acc2-135">Selecteer **Bestemming toevoegen** om een nieuwe export te maken.</span><span class="sxs-lookup"><span data-stu-id="1acc2-135">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="1acc2-136">Kies in het veld **Verbinding voor export** een verbinding uit de sectie Marketo.</span><span class="sxs-lookup"><span data-stu-id="1acc2-136">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="1acc2-137">Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="1acc2-137">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1acc2-138">Voer uw **[Lijst-id van Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** in.</span><span class="sxs-lookup"><span data-stu-id="1acc2-138">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span></span> <span data-ttu-id="1acc2-139">De lijst-ID is een puur numerieke waarde.</span><span class="sxs-lookup"><span data-stu-id="1acc2-139">The list ID is a purely numerical value.</span></span> <span data-ttu-id="1acc2-140">Als uw lijst-id van Marketo bijvoorbeeld ST12345A7 is, verwijdert u het teken voor en na de cijfers en voert u `12345` in.</span><span class="sxs-lookup"><span data-stu-id="1acc2-140">For example, if your Marketo list ID is ST12345A7, remove the character before and after the numerals and enter `12345`.</span></span> 

1. <span data-ttu-id="1acc2-141">Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant.</span><span class="sxs-lookup"><span data-stu-id="1acc2-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="1acc2-142">Optioneel kunt u **Voornaam**, **Achternaam**, **Plaats**, **Staat** en **Land/regio** exporteren om meer gepersonaliseerde e-mails te maken.</span><span class="sxs-lookup"><span data-stu-id="1acc2-142">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="1acc2-143">Selecteer **Kenmerk toevoegen** om deze velden toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="1acc2-143">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="1acc2-144">Selecteer de segmenten die u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="1acc2-144">Select the segments you want to export.</span></span> <span data-ttu-id="1acc2-145">U kunt in totaal tot 1 miljoen klantprofielen exporteren naar Marketo.</span><span class="sxs-lookup"><span data-stu-id="1acc2-145">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="1acc2-146">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1acc2-146">Select **Save**.</span></span>

<span data-ttu-id="1acc2-147">Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="1acc2-147">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1acc2-148">De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1acc2-148">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1acc2-149">U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1acc2-149">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="1acc2-150">In Marketo vindt u nu uw segmenten onder [Marketo-lijsten](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="1acc2-150">In Marketo, you can now find your segments under [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1acc2-151">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="1acc2-151">Data privacy and compliance</span></span>

<span data-ttu-id="1acc2-152">Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar Marketo te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="1acc2-152">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1acc2-153">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat Marketo voldoet aan uw privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="1acc2-153">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="1acc2-154">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1acc2-154">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="1acc2-155">Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="1acc2-155">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
