---
title: Customer Insights-gegevens exporteren naar Salesforce Marketing Cloud
description: Leer hoe u de verbinding configureert en exporteert naar Salesforce Marketing Cloud.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314597"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="0ee5b-103">Segmenten en andere gegevens exporteren naar Salesforce Marketing Cloud (preview)</span><span class="sxs-lookup"><span data-stu-id="0ee5b-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="0ee5b-104">Gebruik uw klantgegevens in Salesforce Marketing Cloud door ze te exporteren via een SFTP-locatie (Secure File Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="0ee5b-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="0ee5b-105">Vereisten voor verbinding</span><span class="sxs-lookup"><span data-stu-id="0ee5b-105">Prerequisites for connection</span></span>

- <span data-ttu-id="0ee5b-106">Beschikbaarheid van een SFTP-host en bijbehorende beheerdersreferenties.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="0ee5b-107">Procedure voor het instellen van SFTP-locaties voor Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="0ee5b-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="0ee5b-108">Bekende beperkingen</span><span class="sxs-lookup"><span data-stu-id="0ee5b-108">Known limitations</span></span>

- <span data-ttu-id="0ee5b-109">Hoe lang een export duurt, is afhankelijk van uw systeemprestaties.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="0ee5b-110">We raden twee CPU-cores en 1 Gb geheugen aan als minimale configuratie van uw server.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="0ee5b-111">Het exporteren van entiteiten met maximaal 100 miljoen klantprofielen kan 90 minuten duren bij gebruik van de aanbevolen minimale configuratie.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="0ee5b-112">De verbinding met Salesforce Marketing Cloud instellen</span><span class="sxs-lookup"><span data-stu-id="0ee5b-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="0ee5b-113">Ga naar **Beheerder** > **Verbindingen**.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0ee5b-114">Selecteer **Verbinding toevoegen** en kies **Salesforce Marketing Cloud** om de verbinding te configureren.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="0ee5b-115">Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="0ee5b-116">De naam en het type verbinding beschrijven deze verbinding.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="0ee5b-117">We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0ee5b-118">Kies wie deze verbinding kan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-118">Choose who can use this connection.</span></span> <span data-ttu-id="0ee5b-119">Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="0ee5b-120">Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="0ee5b-121">Geef **Gebruikersnaam**, **Wachtwoord**, **Hostnaam** en **Exportmap** voor uw SFTP-account op.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="0ee5b-122">Selecteer **Verifiëren** om de verbinding te testen.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="0ee5b-123">Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="0ee5b-124">Selecteer **Opslaan** om de verbinding te voltooien.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="0ee5b-125">Een export configureren</span><span class="sxs-lookup"><span data-stu-id="0ee5b-125">Configure an export</span></span>

<span data-ttu-id="0ee5b-126">U kunt deze export configureren als u toegang hebt tot een verbinding van dit type.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0ee5b-127">Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0ee5b-128">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0ee5b-129">Selecteer **Bestemming toevoegen** om een nieuwe export te maken.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="0ee5b-130">Kies in het veld **Verbinding voor export** een verbinding uit de sectie SFTP.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="0ee5b-131">Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="0ee5b-132">Kies of u uw gegevens **Gzipped** of **Uitgepakt** wilt exporteren en geef het **veldscheidingsteken** voor de geëxporteerde bestanden op.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="0ee5b-133">Selecteer de entiteiten, bijvoorbeeld segmenten, die u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0ee5b-134">Elke geselecteerde entiteit wordt bij het exporteren opgesplitst in maximaal vijf uitvoerbestanden.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="0ee5b-135">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-135">Select **Save**.</span></span>

<span data-ttu-id="0ee5b-136">Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0ee5b-137">De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0ee5b-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0ee5b-138">U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="0ee5b-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="0ee5b-139">Customer Insights-gegevens importeren vanuit SFTP-locatie naar Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="0ee5b-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="0ee5b-140">Maak [gegevensextensies in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) om het Customer Insights-gegevensbestand te importeren vanuit de SFTP-locatie.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="0ee5b-141">[Importeer de gegevens vanuit de SFTP-locatie](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) in de Salesforce Marketing Cloud-gegevensextensie.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="0ee5b-142">Stel de automatisering in om de gegevens te importeren in de gegevensextensies.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="0ee5b-143">Leer meer over [automatiseringen voor het neerzetten van bestanden en geplande automatiseringen](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="0ee5b-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="0ee5b-144">Definieer een [automatisering van het neerzetten van bestanden](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) of een [geplande automatisering](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="0ee5b-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="0ee5b-145">Hier is een voorbeeld van [een automatisering met SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="0ee5b-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0ee5b-146">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="0ee5b-146">Data privacy and compliance</span></span>

<span data-ttu-id="0ee5b-147">Wanneer u Dynamics 365 Customer Insights instelt om gegevens via SFTP te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0ee5b-148">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat de exportbestemming voldoet aan uw privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0ee5b-149">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0ee5b-150">Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="0ee5b-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
