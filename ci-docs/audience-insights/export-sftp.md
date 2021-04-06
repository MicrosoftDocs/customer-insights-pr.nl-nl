---
title: Customer Insights-gegevens exporteren naar SFTP-hosts
description: Meer informatie over het configureren van de verbinding met een SFTP-host.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598379"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="3c5c9-103">Connector voor SFTP (preview)</span><span class="sxs-lookup"><span data-stu-id="3c5c9-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="3c5c9-104">Gebruik uw klantgegevens in toepassingen van derden door deze te exporteren naar een SFTP-host (Secure File Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="3c5c9-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3c5c9-105">Vereisten</span><span class="sxs-lookup"><span data-stu-id="3c5c9-105">Prerequisites</span></span>

- <span data-ttu-id="3c5c9-106">Beschikbaarheid van een SFTP-host en bijbehorende inloggegevens.</span><span class="sxs-lookup"><span data-stu-id="3c5c9-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="3c5c9-107">Verbinding maken met SFTP</span><span class="sxs-lookup"><span data-stu-id="3c5c9-107">Connect to SFTP</span></span>

1. <span data-ttu-id="3c5c9-108">Ga naar **Beheer** > **Exportbestemmingen**.</span><span class="sxs-lookup"><span data-stu-id="3c5c9-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="3c5c9-109">Selecteer onder **SFTP** de optie **Instellen**.</span><span class="sxs-lookup"><span data-stu-id="3c5c9-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="3c5c9-110">Geef uw bestemming een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="3c5c9-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="3c5c9-111">Geef **Gebruikersnaam**, **Wachtwoord**, **Hostnaam** en **Exportmap** voor uw SFTP-account op.</span><span class="sxs-lookup"><span data-stu-id="3c5c9-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="3c5c9-112">Selecteer **Verifiëren** om de verbinding te testen.</span><span class="sxs-lookup"><span data-stu-id="3c5c9-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="3c5c9-113">Kies na succesvolle verificatie of u uw gegevens **Gzipped** of **Uitgepakt** wilt exporteren en selecteer het **veldscheidingsteken** voor de geëxporteerde bestanden.</span><span class="sxs-lookup"><span data-stu-id="3c5c9-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="3c5c9-114">Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="3c5c9-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="3c5c9-115">Selecteer **Volgende** om te beginnen met het configureren van de export.</span><span class="sxs-lookup"><span data-stu-id="3c5c9-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="3c5c9-116">De export configureren</span><span class="sxs-lookup"><span data-stu-id="3c5c9-116">Configure the export</span></span>

1. <span data-ttu-id="3c5c9-117">Selecteer de entiteiten, bijvoorbeeld segmenten, die u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="3c5c9-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3c5c9-118">Elke geselecteerde entiteit bevat bij het exporteren maximaal vijf uitvoerbestanden.</span><span class="sxs-lookup"><span data-stu-id="3c5c9-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="3c5c9-119">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="3c5c9-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="3c5c9-120">De gegevens exporteren</span><span class="sxs-lookup"><span data-stu-id="3c5c9-120">Export the data</span></span>

<span data-ttu-id="3c5c9-121">U kunt [gegevens op aanvraag exporteren](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="3c5c9-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="3c5c9-122">De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3c5c9-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="3c5c9-123">Bekende beperkingen</span><span class="sxs-lookup"><span data-stu-id="3c5c9-123">Known limitations</span></span>

- <span data-ttu-id="3c5c9-124">Hoe lang een export duurt, is afhankelijk van uw systeemprestaties.</span><span class="sxs-lookup"><span data-stu-id="3c5c9-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="3c5c9-125">We raden twee CPU-cores en 1 Gb geheugen aan als minimale configuratie van uw server.</span><span class="sxs-lookup"><span data-stu-id="3c5c9-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="3c5c9-126">Het exporteren van entiteiten met maximaal 100 miljoen klantprofielen kan 90 minuten duren bij gebruik van de aanbevolen minimale configuratie van twee CPU-cores en 1 Gb geheugen.</span><span class="sxs-lookup"><span data-stu-id="3c5c9-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3c5c9-127">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="3c5c9-127">Data privacy and compliance</span></span>

<span data-ttu-id="3c5c9-128">Wanneer u Dynamics 365 Customer Insights instelt om gegevens via SFTP te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="3c5c9-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3c5c9-129">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat de exportbestemming voldoet aan uw privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="3c5c9-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="3c5c9-130">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3c5c9-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="3c5c9-131">Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="3c5c9-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]