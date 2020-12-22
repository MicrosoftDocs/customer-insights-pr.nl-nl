---
title: Customer Insights-gegevens exporteren naar SFTP-hosts
description: Meer informatie over het configureren van de verbinding met een SFTP-host.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643497"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="39bcd-103">Connector voor SFTP (preview)</span><span class="sxs-lookup"><span data-stu-id="39bcd-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="39bcd-104">Gebruik uw klantgegevens in toepassingen van derden door deze te exporteren naar een SFTP-host (Secure File Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="39bcd-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="39bcd-105">Vereisten</span><span class="sxs-lookup"><span data-stu-id="39bcd-105">Prerequisites</span></span>

- <span data-ttu-id="39bcd-106">Beschikbaarheid van een SFTP-host en bijbehorende referenties.</span><span class="sxs-lookup"><span data-stu-id="39bcd-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="39bcd-107">Verbinding maken met SFTP</span><span class="sxs-lookup"><span data-stu-id="39bcd-107">Connect to SFTP</span></span>

1. <span data-ttu-id="39bcd-108">Ga naar **Beheer** > **Exportbestemmingen**.</span><span class="sxs-lookup"><span data-stu-id="39bcd-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="39bcd-109">Selecteer onder **SFTP** de optie **Instellen**.</span><span class="sxs-lookup"><span data-stu-id="39bcd-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="39bcd-110">Geef uw bestemming een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="39bcd-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="39bcd-111">Geef **Gebruikersnaam**, **Wachtwoord** en **Hostnaam** voor uw SFTP-account op.</span><span class="sxs-lookup"><span data-stu-id="39bcd-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="39bcd-112">Voorbeeld: als de hoofdmap van uw SFTP-server /hoofdmap/map is en u wilt dat de gegevens worden geëxporteerd naar /hoofdmap/map/ci_export_doelmap, dan moet de host sftp://<server_address>/ci_export_doelmap" zijn.</span><span class="sxs-lookup"><span data-stu-id="39bcd-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="39bcd-113">Selecteer **Verifiëren** om de verbinding te testen.</span><span class="sxs-lookup"><span data-stu-id="39bcd-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="39bcd-114">Kies na succesvolle verificatie of u uw gegevens **Gezipt** of **Niet-gezipt** wilt exporteren en selecteer daarna het **veldscheidingsteken** voor de geëxporteerde bestanden.</span><span class="sxs-lookup"><span data-stu-id="39bcd-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="39bcd-115">Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="39bcd-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="39bcd-116">Selecteer **Volgende** om te beginnen met het configureren van de export.</span><span class="sxs-lookup"><span data-stu-id="39bcd-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="39bcd-117">De verbinding configureren</span><span class="sxs-lookup"><span data-stu-id="39bcd-117">Configure the connection</span></span>

1. <span data-ttu-id="39bcd-118">Selecteer de **klantkenmerken** die u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="39bcd-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="39bcd-119">U kunt een of meer kenmerken exporteren.</span><span class="sxs-lookup"><span data-stu-id="39bcd-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="39bcd-120">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="39bcd-120">Select **Next**.</span></span>

1. <span data-ttu-id="39bcd-121">Selecteer de segmenten die u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="39bcd-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="39bcd-122">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="39bcd-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="39bcd-123">De gegevens exporteren</span><span class="sxs-lookup"><span data-stu-id="39bcd-123">Export the data</span></span>

<span data-ttu-id="39bcd-124">U kunt [gegevens op aanvraag exporteren](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="39bcd-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="39bcd-125">De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="39bcd-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="39bcd-126">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="39bcd-126">Data privacy and compliance</span></span>

<span data-ttu-id="39bcd-127">Wanneer u Dynamics 365 Customer Insights instelt om gegevens via SFTP te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="39bcd-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="39bcd-128">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat de exportbestemming voldoet aan uw privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="39bcd-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="39bcd-129">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="39bcd-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="39bcd-130">Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="39bcd-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
