---
title: LiveRamp-connector
description: Ontdek hoe u gegevens kunt exporteren naar LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 64d781f52e8124fc3e83a7b84f468830c5249cfd
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270152"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="79a0a-103">LiveRamp&reg;-connector (preview)</span><span class="sxs-lookup"><span data-stu-id="79a0a-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="79a0a-104">Activeer uw gegevens in LiveRamp om verbinding te maken met meer dan 500 platforms in digitale, sociale en tv-ecosystemen.</span><span class="sxs-lookup"><span data-stu-id="79a0a-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="79a0a-105">Werk met uw gegevens in LiveRamp om advertentiecampagnes te targeten, onderdrukken en personaliseren.</span><span class="sxs-lookup"><span data-stu-id="79a0a-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="79a0a-106">Vereisten</span><span class="sxs-lookup"><span data-stu-id="79a0a-106">Prerequisites</span></span>

- <span data-ttu-id="79a0a-107">U hebt een LiveRamp-abonnement nodig om deze connector te kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="79a0a-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="79a0a-108">U kunt een abonnement nemen door rechtstreeks [contact op te nemen met LiveRamp](https://liveramp.com/contact/).</span><span class="sxs-lookup"><span data-stu-id="79a0a-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="79a0a-109">[Meer informatie over LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="79a0a-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="79a0a-110">Verbinding maken met LiveRamp</span><span class="sxs-lookup"><span data-stu-id="79a0a-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="79a0a-111">Ga in doelgroepinzichten naar **Beheer** > **Exportbestemmingen**.</span><span class="sxs-lookup"><span data-stu-id="79a0a-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="79a0a-112">Selecteer op de tegel **LiveRamp** de optie **Instellen**.</span><span class="sxs-lookup"><span data-stu-id="79a0a-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="79a0a-113">Geef uw bestemming een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="79a0a-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="79a0a-114">Verschaf een **gebruikersnaam** en **wachtwoord** voor uw LiveRamp Secure FTP-account (SFTP).</span><span class="sxs-lookup"><span data-stu-id="79a0a-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="79a0a-115">Deze referenties kunnen verschillen van uw LiveRamp Onboarding-referenties.</span><span class="sxs-lookup"><span data-stu-id="79a0a-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="79a0a-116">Selecteer **Verifiëren** om de verbinding met LiveRamp te testen.</span><span class="sxs-lookup"><span data-stu-id="79a0a-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="79a0a-117">Geef na succesvolle verificatie uw toestemming voor **Gegevensprivacy en naleving** door het selectievakje **Ik ga akkoord** in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="79a0a-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="79a0a-118">Selecteer **Volgende** om de LiveRamp-connector in te stellen.</span><span class="sxs-lookup"><span data-stu-id="79a0a-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="79a0a-119">De connector configureren</span><span class="sxs-lookup"><span data-stu-id="79a0a-119">Configure the connector</span></span>

1. <span data-ttu-id="79a0a-120">Selecteer in het veld **Uw sleutelidentificatie kiezen** de optie **E-mail**, **Naam en adres** of **Telefoon** om naar LiveRamp te sturen voor identiteitsresolutie.</span><span class="sxs-lookup"><span data-stu-id="79a0a-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="79a0a-121">Wijs de corresponderende kenmerken van uw geharmoniseerde klantentiteit toe aan de geselecteerde sleutel-id.</span><span class="sxs-lookup"><span data-stu-id="79a0a-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="79a0a-122">Selecteer **Kenmerk toevoegen** om extra kenmerken toe te wijzen voor verzending naar LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="79a0a-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="79a0a-123">Als u meer kenmerken voor sleutel-id's naar LiveRamp verzendt, krijgt u waarschijnlijk een hoger overeenkomstpercentage.</span><span class="sxs-lookup"><span data-stu-id="79a0a-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="79a0a-124">Selecteer de segmenten die u naar LiveRamp wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="79a0a-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="79a0a-125">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="79a0a-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="79a0a-126">![LiveRamp-connector met kenmerktoewijzing](media/export-liveramp-segments.png "LiveRamp-connector met kenmerktoewijzing")</span><span class="sxs-lookup"><span data-stu-id="79a0a-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="79a0a-127">De gegevens exporteren</span><span class="sxs-lookup"><span data-stu-id="79a0a-127">Export the data</span></span>

<span data-ttu-id="79a0a-128">De export begint spoedig als aan alle voorwaarden voor export is voldaan.</span><span class="sxs-lookup"><span data-stu-id="79a0a-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="79a0a-129">De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="79a0a-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="79a0a-130">Zodra de export is voltooid, kunt u zich aanmelden bij LiveRamp Onboarding om uw gegevens te activeren en te distribueren.</span><span class="sxs-lookup"><span data-stu-id="79a0a-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="79a0a-131">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="79a0a-131">Data privacy and compliance</span></span>

<span data-ttu-id="79a0a-132">Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar LiveRamp te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="79a0a-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="79a0a-133">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat LiveRamp voldoet aan uw privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="79a0a-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="79a0a-134">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="79a0a-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="79a0a-135">Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="79a0a-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]