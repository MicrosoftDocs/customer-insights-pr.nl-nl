---
title: Customer Insights-gegevens exporteren naar SFTP-hosts
description: Leer hoe u de verbinding configureert en exporteert naar een SFTP-locatie.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 000b44dc8e5cc419132bd17e359fbdd5879caf1b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124313"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a><span data-ttu-id="5567e-103">Segmenten en andere gegevens exporteren naar SFTP (preview)</span><span class="sxs-lookup"><span data-stu-id="5567e-103">Export segments and other data to SFTP (preview)</span></span>

<span data-ttu-id="5567e-104">Gebruik uw klantgegevens in toepassIngen van derden door ze te exporteren naar een SFTP-locatie (Secure File Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="5567e-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="5567e-105">Vereisten voor verbinding</span><span class="sxs-lookup"><span data-stu-id="5567e-105">Prerequisites for connection</span></span>

- <span data-ttu-id="5567e-106">Beschikbaarheid van een SFTP-host en bijbehorende inloggegevens.</span><span class="sxs-lookup"><span data-stu-id="5567e-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="5567e-107">Bekende beperkingen</span><span class="sxs-lookup"><span data-stu-id="5567e-107">Known limitations</span></span>

- <span data-ttu-id="5567e-108">Hoe lang een export duurt, is afhankelijk van uw systeemprestaties.</span><span class="sxs-lookup"><span data-stu-id="5567e-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="5567e-109">We raden twee CPU-cores en 1 Gb geheugen aan als minimale configuratie van uw server.</span><span class="sxs-lookup"><span data-stu-id="5567e-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="5567e-110">Het exporteren van entiteiten met maximaal 100 miljoen klantprofielen kan 90 minuten duren bij gebruik van de aanbevolen minimale configuratie van twee CPU-cores en 1 Gb geheugen.</span><span class="sxs-lookup"><span data-stu-id="5567e-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="5567e-111">Verbinding instellen MET SFTP</span><span class="sxs-lookup"><span data-stu-id="5567e-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="5567e-112">Ga naar **Beheerder** > **Verbindingen**.</span><span class="sxs-lookup"><span data-stu-id="5567e-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="5567e-113">Selecteer **Verbinding toevoegen** en kies **SFTP** om de verbinding te configureren.</span><span class="sxs-lookup"><span data-stu-id="5567e-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="5567e-114">Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="5567e-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="5567e-115">De naam en het type verbinding beschrijven deze verbinding.</span><span class="sxs-lookup"><span data-stu-id="5567e-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="5567e-116">We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.</span><span class="sxs-lookup"><span data-stu-id="5567e-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="5567e-117">Kies wie deze verbinding kan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="5567e-117">Choose who can use this connection.</span></span> <span data-ttu-id="5567e-118">Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling.</span><span class="sxs-lookup"><span data-stu-id="5567e-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="5567e-119">Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="5567e-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="5567e-120">Geef **Gebruikersnaam**, **Wachtwoord**, **Hostnaam** en **Exportmap** voor uw SFTP-account op.</span><span class="sxs-lookup"><span data-stu-id="5567e-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="5567e-121">Selecteer **Verifiëren** om de verbinding te testen.</span><span class="sxs-lookup"><span data-stu-id="5567e-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="5567e-122">Kies of u uw gegevens **Gzipped** of **Uitgepakt** wilt exporteren en geef het **veldscheidingsteken** voor de geëxporteerde bestanden op.</span><span class="sxs-lookup"><span data-stu-id="5567e-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="5567e-123">Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="5567e-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="5567e-124">Selecteer **Opslaan** om de verbinding te voltooien.</span><span class="sxs-lookup"><span data-stu-id="5567e-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="5567e-125">Een export configureren</span><span class="sxs-lookup"><span data-stu-id="5567e-125">Configure an export</span></span>

<span data-ttu-id="5567e-126">U kunt deze export configureren als u toegang hebt tot een verbinding van dit type.</span><span class="sxs-lookup"><span data-stu-id="5567e-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="5567e-127">Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="5567e-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="5567e-128">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="5567e-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5567e-129">Selecteer **Bestemming toevoegen** om een nieuwe export te maken.</span><span class="sxs-lookup"><span data-stu-id="5567e-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="5567e-130">Kies in het veld **Verbinding voor export** een verbinding uit de sectie SFTP.</span><span class="sxs-lookup"><span data-stu-id="5567e-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="5567e-131">Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="5567e-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="5567e-132">Selecteer de entiteiten, bijvoorbeeld segmenten, die u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="5567e-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5567e-133">Elke geselecteerde entiteit wordt bij het exporteren opgesplitst in maximaal vijf uitvoerbestanden.</span><span class="sxs-lookup"><span data-stu-id="5567e-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="5567e-134">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="5567e-134">Select **Save**.</span></span>

<span data-ttu-id="5567e-135">Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="5567e-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="5567e-136">De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="5567e-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="5567e-137">U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="5567e-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5567e-138">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="5567e-138">Data privacy and compliance</span></span>

<span data-ttu-id="5567e-139">Wanneer u Dynamics 365 Customer Insights instelt om gegevens via SFTP te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="5567e-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5567e-140">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat de exportbestemming voldoet aan uw privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="5567e-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="5567e-141">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="5567e-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="5567e-142">Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="5567e-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
