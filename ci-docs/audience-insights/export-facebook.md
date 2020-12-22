---
title: Customer Insights-gegevens exporteren naar Facebook Ads Manager
description: Meer informatie over het configureren van de verbinding met Facebook Ads Manager.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8260e3b5e529f3d54678d9d6e11aebb2795e27fd
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643677"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="ca42b-103">Connector voor Facebook Ads Manager (preview)</span><span class="sxs-lookup"><span data-stu-id="ca42b-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="ca42b-104">Exporteer segmenten van geharmoniseerde klantprofielen naar Facebook Ads Manager om campagnes te maken op Facebook en Instagram.</span><span class="sxs-lookup"><span data-stu-id="ca42b-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ca42b-105">Vereisten</span><span class="sxs-lookup"><span data-stu-id="ca42b-105">Prerequisites</span></span>

- <span data-ttu-id="ca42b-106">U moet een [**Facebook Ad-account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) hebben met een [**Facebook Business-account**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="ca42b-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="ca42b-107">U moet een beheerder zijn van het [**Facebook Ad-account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="ca42b-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="ca42b-108">Verbinden met Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="ca42b-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="ca42b-109">Ga naar **Beheer** > **Exportbestemmingen**.</span><span class="sxs-lookup"><span data-stu-id="ca42b-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ca42b-110">Selecteer onder **Facebook Ads Manager** de optie **Instellen**.</span><span class="sxs-lookup"><span data-stu-id="ca42b-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="ca42b-111">Geef uw exportbestemming een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="ca42b-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="ca42b-112">Selecteer **Doorgaan met Facebook** om zich aan te melden bij uw Facebook Ad-account.</span><span class="sxs-lookup"><span data-stu-id="ca42b-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="ca42b-113">Geef **ads_management** een machtiging na verificatie met Facebook.</span><span class="sxs-lookup"><span data-stu-id="ca42b-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="ca42b-114">Selecteer het **Facebook Ads-account** waarmee u wilt werken.</span><span class="sxs-lookup"><span data-stu-id="ca42b-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="ca42b-115">Selecteer een **Bestaande aangepaste doelgroep** in de vervolgkeuzelijst of maak een **Nieuwe aangepaste doelgroep**.</span><span class="sxs-lookup"><span data-stu-id="ca42b-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="ca42b-116">Zie [**Doelgroepen in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ca42b-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="ca42b-117">Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="ca42b-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ca42b-118">Selecteer **Volgende** om de export te configureren.</span><span class="sxs-lookup"><span data-stu-id="ca42b-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="ca42b-119">De connector configureren</span><span class="sxs-lookup"><span data-stu-id="ca42b-119">Configure the connector</span></span>

1. <span data-ttu-id="ca42b-120">Selecteer in het veld **Uw sleutel-id kiezen** de optie **E-mail**, **Naam en adres** of **Telefoon** om naar Facebook Ads Manager te verzenden.</span><span class="sxs-lookup"><span data-stu-id="ca42b-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="ca42b-121">Wijs de corresponderende kenmerken van uw geharmoniseerde klantentiteit toe aan de geselecteerde sleutel-id.</span><span class="sxs-lookup"><span data-stu-id="ca42b-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="ca42b-122">[TIP] U hebt de beste kans op een overeenkomst als u **E-mail** als sleutel-id selecteert.</span><span class="sxs-lookup"><span data-stu-id="ca42b-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="ca42b-123">De matching kan verbeteren door toevoeging van extra id's.</span><span class="sxs-lookup"><span data-stu-id="ca42b-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="ca42b-124">Selecteer **Kenmerk toevoegen** om extra kenmerken toe te wijzen voor verzending naar Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="ca42b-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="ca42b-125">Kenmerken van Facebook Ads Manager komen overeen met de volgende gebruikersvriendelijke namen: **FN** = **Voornaam**, **LN** = **Achternaam**, **FI** = **Eerste initiaal**, **PHONE** = **Telefoon**, **GEN** = **Geslacht**, **DOB** = **Geboortedatum**, **ST** = **Staat**, **CT** = **Plaats**, **ZIP** = **Postcode**, **COUNTRY** = **Land/regio**</span><span class="sxs-lookup"><span data-stu-id="ca42b-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="ca42b-126">Selecteer de segmenten die u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="ca42b-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="ca42b-127">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ca42b-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="ca42b-128">De gegevens exporteren</span><span class="sxs-lookup"><span data-stu-id="ca42b-128">Export the data</span></span>

<span data-ttu-id="ca42b-129">U kunt [gegevens op aanvraag exporteren](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="ca42b-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="ca42b-130">De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ca42b-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ca42b-131">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="ca42b-131">Data privacy and compliance</span></span>

<span data-ttu-id="ca42b-132">Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar Facebook Ads Manager te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="ca42b-132">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ca42b-133">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat Facebook Ads voldoet aan uw privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="ca42b-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="ca42b-134">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ca42b-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ca42b-135">Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="ca42b-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
