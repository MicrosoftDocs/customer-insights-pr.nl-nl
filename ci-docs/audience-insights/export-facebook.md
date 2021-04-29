---
title: Customer Insights-gegevens exporteren naar Facebook Ads Manager
description: Leer hoe u de verbinding configureert en exporteert naar Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ca32906a98bc734639fb369d6f5a92e8888fd850
ms.sourcegitcommit: 6d5dd572f75ba4c0303ec77c3b74e4318d52705c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906804"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="ce248-103">Segmentenlijst exporteren naar Facebook Ads Manager (preview)</span><span class="sxs-lookup"><span data-stu-id="ce248-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="ce248-104">Exporteer segmenten van geharmoniseerde klantprofielen naar Facebook Ads Manager om campagnes te maken op Facebook en Instagram.</span><span class="sxs-lookup"><span data-stu-id="ce248-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="ce248-105">Vereisten voor verbinding</span><span class="sxs-lookup"><span data-stu-id="ce248-105">Prerequisites for connection</span></span>

- <span data-ttu-id="ce248-106">U hebt een [**Facebook Ad-account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) nodig dat een [**zakelijk Facebook-account**](https://business.facebook.com/) bevat.</span><span class="sxs-lookup"><span data-stu-id="ce248-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="ce248-107">U moet een beheerder zijn van het [**Facebook Ad-account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="ce248-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ce248-108">Bekende beperkingen</span><span class="sxs-lookup"><span data-stu-id="ce248-108">Known limitations</span></span>

- <span data-ttu-id="ce248-109">Maximaal 10 miljoen klantprofielen per export naar Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="ce248-109">Up to 10 million customer profile per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="ce248-110">Exporteren naar Facebook Ads Manager is beperkt tot segmenten.</span><span class="sxs-lookup"><span data-stu-id="ce248-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="ce248-111">Maak of update in Facebook alleen aangepaste doelgroepen van het type *klantenlijst*.</span><span class="sxs-lookup"><span data-stu-id="ce248-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="ce248-112">Segmenten met in totaal 10 miljoen profielen exporteren kan tot 90 minuten duren.</span><span class="sxs-lookup"><span data-stu-id="ce248-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="ce248-113">Verbinding instellen met Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="ce248-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="ce248-114">Voordat gebruikers een export kunnen maken, moet een beheerder de verbinding met de service configureren en inzenders toestaan de verbinding te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ce248-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="ce248-115">Ga naar **Beheerder** > **Verbindingen**.</span><span class="sxs-lookup"><span data-stu-id="ce248-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ce248-116">Selecteer **Verbinding toevoegen** en kies **Facebook Ads Manager** om de verbinding te configureren.</span><span class="sxs-lookup"><span data-stu-id="ce248-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="ce248-117">Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="ce248-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ce248-118">De naam en het type verbinding beschrijven deze verbinding.</span><span class="sxs-lookup"><span data-stu-id="ce248-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ce248-119">We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.</span><span class="sxs-lookup"><span data-stu-id="ce248-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ce248-120">Kies wie deze verbinding kan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ce248-120">Choose who can use this connection.</span></span> <span data-ttu-id="ce248-121">Als u geen actie onderneemt, wordt **Beheerders** gebruikt als standaardinstelling.</span><span class="sxs-lookup"><span data-stu-id="ce248-121">If you take no action, the default will be **Administrators**.</span></span> <span data-ttu-id="ce248-122">Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ce248-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ce248-123">Verifiëren met Facebook Ads:</span><span class="sxs-lookup"><span data-stu-id="ce248-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="ce248-124">Selecteer **Doorgaan met Facebook** om zich aan te melden bij uw Facebook Ad-account.</span><span class="sxs-lookup"><span data-stu-id="ce248-124">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

   1. <span data-ttu-id="ce248-125">Geef **ads_management** een machtiging na verificatie met Facebook.</span><span class="sxs-lookup"><span data-stu-id="ce248-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="ce248-126">Selecteer het **Facebook Ads-account** waarmee u wilt werken.</span><span class="sxs-lookup"><span data-stu-id="ce248-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="ce248-127">Selecteer een **Bestaande aangepaste doelgroep** in de vervolgkeuzelijst of maak een **Nieuwe aangepaste doelgroep**.</span><span class="sxs-lookup"><span data-stu-id="ce248-127">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="ce248-128">Zie [**Doelgroepen in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ce248-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="ce248-129">U kunt op Facebook alleen aangepaste doelgroepen maken of bijwerken van het type *klantenlijst* met deze export.</span><span class="sxs-lookup"><span data-stu-id="ce248-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="ce248-130">In sommige gevallen ziet u aangepaste doelgroepen van verschillende typen in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="ce248-130">In some cases, you see custom audiences of different types in the drop-down list.</span></span> <span data-ttu-id="ce248-131">Als een ander type dan *klantenlijst* wordt geselecteerd, resulteert dit in een mislukte export.</span><span class="sxs-lookup"><span data-stu-id="ce248-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="ce248-132">Bekijk **Gegevensprivacy en naleving** en selecteer **Ik ga akkoord**.</span><span class="sxs-lookup"><span data-stu-id="ce248-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="ce248-133">Selecteer **Opslaan** om de verbinding te voltooien.</span><span class="sxs-lookup"><span data-stu-id="ce248-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ce248-134">Een export configureren</span><span class="sxs-lookup"><span data-stu-id="ce248-134">Configure an export</span></span>

<span data-ttu-id="ce248-135">U kunt deze export configureren als u toegang hebt tot een verbinding van dit type.</span><span class="sxs-lookup"><span data-stu-id="ce248-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ce248-136">Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ce248-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ce248-137">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="ce248-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ce248-138">Selecteer **Bestemming toevoegen** om een nieuwe export te maken.</span><span class="sxs-lookup"><span data-stu-id="ce248-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="ce248-139">Kies in **Verbinding voor export** een verbinding uit de sectie **Facebook Ads Manager**.</span><span class="sxs-lookup"><span data-stu-id="ce248-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="ce248-140">Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="ce248-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ce248-141">Selecteer in het veld **Uw sleutel-id kiezen** de optie **E-mail**, **Naam en adres** of **Telefoon** om naar Facebook Ads Manager te verzenden.</span><span class="sxs-lookup"><span data-stu-id="ce248-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="ce248-142">Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="ce248-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="ce248-143">Wijs de corresponderende kenmerken van uw geharmoniseerde klantentiteit toe aan de geselecteerde sleutel-id.</span><span class="sxs-lookup"><span data-stu-id="ce248-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="ce248-144">[TIP] U hebt de beste kans op een overeenkomst als u **E-mail** als sleutel-id selecteert.</span><span class="sxs-lookup"><span data-stu-id="ce248-144">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="ce248-145">De matching kan verbeteren door toevoeging van extra id's.</span><span class="sxs-lookup"><span data-stu-id="ce248-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="ce248-146">Selecteer **Kenmerk toevoegen** om meer kenmerken toe te wijzen om naar Facebook Ads Manager te verzenden.</span><span class="sxs-lookup"><span data-stu-id="ce248-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="ce248-147">Kenmerken van Facebook Ads Manager komen overeen met de volgende gebruikersvriendelijke namen: **FN** = **Voornaam**, **LN** = **Achternaam**, **FI** = **Eerste initiaal**, **PHONE** = **Telefoon**, **GEN** = **Geslacht**, **DOB** = **Geboortedatum**, **ST** = **Staat**, **CT** = **Plaats**, **ZIP** = **Postcode**, **COUNTRY** = **Land/regio**</span><span class="sxs-lookup"><span data-stu-id="ce248-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="ce248-148">Selecteer de segmenten die u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="ce248-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="ce248-149">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ce248-149">Select **Save**.</span></span>

<span data-ttu-id="ce248-150">Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="ce248-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ce248-151">De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ce248-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ce248-152">U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ce248-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ce248-153">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="ce248-153">Data privacy and compliance</span></span>

<span data-ttu-id="ce248-154">Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar Facebook Ads Manager te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="ce248-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ce248-155">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat Facebook Ads voldoet aan uw privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="ce248-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="ce248-156">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ce248-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ce248-157">Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="ce248-157">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
