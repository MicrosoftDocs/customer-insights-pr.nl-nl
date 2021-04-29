---
title: LiveRamp-connector
description: Leer hoe u de verbinding configureert en exporteert naar LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760321"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="a32ef-103">Segmenten exporteren naar LiveRamp&reg; (preview)</span><span class="sxs-lookup"><span data-stu-id="a32ef-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="a32ef-104">Activeer uw gegevens in LiveRamp om verbinding te maken met meer dan 500 platforms op digitaal, sociaal en tv.</span><span class="sxs-lookup"><span data-stu-id="a32ef-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="a32ef-105">Werk met uw gegevens in LiveRamp om advertentiecampagnes te targeten, onderdrukken en personaliseren.</span><span class="sxs-lookup"><span data-stu-id="a32ef-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="a32ef-106">Vereisten voor een verbinding</span><span class="sxs-lookup"><span data-stu-id="a32ef-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="a32ef-107">U hebt een LiveRamp-abonnement nodig om deze connector te kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="a32ef-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="a32ef-108">U kunt een abonnement nemen door rechtstreeks [contact op te nemen met LiveRamp](https://liveramp.com/contact/).</span><span class="sxs-lookup"><span data-stu-id="a32ef-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="a32ef-109">[Meer informatie over LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="a32ef-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="a32ef-110">Verbinding instellen met LiveRamp</span><span class="sxs-lookup"><span data-stu-id="a32ef-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="a32ef-111">Ga naar **Beheerder** > **Verbindingen**.</span><span class="sxs-lookup"><span data-stu-id="a32ef-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a32ef-112">Selecteer **Verbinding toevoegen** en kies **LiveRamp** om de verbinding te configureren.</span><span class="sxs-lookup"><span data-stu-id="a32ef-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="a32ef-113">Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="a32ef-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a32ef-114">De naam en het type verbinding beschrijven deze verbinding.</span><span class="sxs-lookup"><span data-stu-id="a32ef-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a32ef-115">We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.</span><span class="sxs-lookup"><span data-stu-id="a32ef-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a32ef-116">Kies wie deze verbinding kan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="a32ef-116">Choose who can use this connection.</span></span> <span data-ttu-id="a32ef-117">Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling.</span><span class="sxs-lookup"><span data-stu-id="a32ef-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a32ef-118">Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a32ef-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a32ef-119">Verschaf een **gebruikersnaam** en **wachtwoord** voor uw LiveRamp Secure FTP-account (SFTP).</span><span class="sxs-lookup"><span data-stu-id="a32ef-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="a32ef-120">Deze referenties kunnen verschillen van uw LiveRamp Onboarding-referenties.</span><span class="sxs-lookup"><span data-stu-id="a32ef-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="a32ef-121">Selecteer **Verifiëren** om de verbinding met LiveRamp te testen.</span><span class="sxs-lookup"><span data-stu-id="a32ef-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="a32ef-122">Geef na succesvolle verificatie uw toestemming voor **Gegevensprivacy en naleving** door het selectievakje **Ik ga akkoord** in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="a32ef-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="a32ef-123">Selecteer **Opslaan** om de verbinding te voltooien.</span><span class="sxs-lookup"><span data-stu-id="a32ef-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="a32ef-124">Een export configureren</span><span class="sxs-lookup"><span data-stu-id="a32ef-124">Configure an export</span></span>

<span data-ttu-id="a32ef-125">U kunt deze export configureren als u toegang hebt tot een verbinding van dit type.</span><span class="sxs-lookup"><span data-stu-id="a32ef-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a32ef-126">Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a32ef-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a32ef-127">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="a32ef-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a32ef-128">Selecteer **Bestemming toevoegen** om een nieuwe export te maken.</span><span class="sxs-lookup"><span data-stu-id="a32ef-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a32ef-129">Kies in het veld **Verbinding voor export** een verbinding uit de sectie LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="a32ef-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="a32ef-130">Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="a32ef-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a32ef-131">Selecteer in het veld **Uw sleutelidentificatie kiezen** de optie **E-mail**, **Naam en adres** of **Telefoon** om naar LiveRamp te sturen voor identiteitsresolutie.</span><span class="sxs-lookup"><span data-stu-id="a32ef-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a32ef-132">![LiveRamp-connector met kenmerktoewijzing](media/export-liveramp-segments.png "LiveRamp-connector met kenmerktoewijzing")</span><span class="sxs-lookup"><span data-stu-id="a32ef-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="a32ef-133">Wijs de corresponderende kenmerken van uw geharmoniseerde klantentiteit toe aan de geselecteerde sleutel-id.</span><span class="sxs-lookup"><span data-stu-id="a32ef-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="a32ef-134">Selecteer **Kenmerk toevoegen** om meer kenmerken toe te wijzen om naar LiveRamp te verzenden.</span><span class="sxs-lookup"><span data-stu-id="a32ef-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="a32ef-135">Als u meer kenmerken voor sleutel-id's naar LiveRamp verzendt, krijgt u waarschijnlijk een hoger overeenkomstpercentage.</span><span class="sxs-lookup"><span data-stu-id="a32ef-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="a32ef-136">Selecteer de segmenten die u naar LiveRamp wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="a32ef-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="a32ef-137">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="a32ef-137">Select **Save**.</span></span>

<span data-ttu-id="a32ef-138">Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="a32ef-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a32ef-139">De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a32ef-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a32ef-140">U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a32ef-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a32ef-141">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="a32ef-141">Data privacy and compliance</span></span>

<span data-ttu-id="a32ef-142">Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar LiveRamp te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="a32ef-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a32ef-143">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat LiveRamp voldoet aan uw privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="a32ef-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a32ef-144">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a32ef-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a32ef-145">Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="a32ef-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
