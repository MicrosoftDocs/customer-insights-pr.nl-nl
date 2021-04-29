---
title: Customer Insights-gegevens exporteren naar Dynamics 365 Marketing
description: Leer hoe u de verbinding configureert en exporteert naar Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a13f6f81f5e2570d3302d88c02755f1d86321a01
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759603"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="08827-103">Segmenten gebruiken in Dynamics 365 Marketing (preview)</span><span class="sxs-lookup"><span data-stu-id="08827-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="08827-104">Gebruik de [segmenten](segments.md) om campagnes te genereren en contact op te nemen met specifieke groepen klanten met Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="08827-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="08827-105">Zie [Segmenten van Dynamics 365 Customer Insights gebruiken met Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="08827-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="08827-106">Vereiste voor een verbinding</span><span class="sxs-lookup"><span data-stu-id="08827-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="08827-107">Contactpersoonsrecords moeten aanwezig zijn in Dynamics 365 Marketing voordat u een segment van Customer Insights naar Marketing kunt exporteren.</span><span class="sxs-lookup"><span data-stu-id="08827-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="08827-108">Lees meer over het opnemen van contactpersonen in [Dynamics 365 Marketing met Common Data Services](connect-power-query.md)​.</span><span class="sxs-lookup"><span data-stu-id="08827-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="08827-109">Als u segmenten van doelgroepinzichten naar Marketing exporteert, worden er geen nieuwe contactpersoonrecords gemaakt in de Marketing-exemplaren.</span><span class="sxs-lookup"><span data-stu-id="08827-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="08827-110">De contactpersoonrecords van Marketing moeten worden opgenomen in doelgroepinzichten en worden gebruikt als een gegevensbron.</span><span class="sxs-lookup"><span data-stu-id="08827-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="08827-111">Ze moeten ook worden opgenomen in de geharmoniseerde klantentiteit om klant-id's toe te wijzen aan contactpersoon-id's voordat segmenten kunnen worden geëxporteerd.</span><span class="sxs-lookup"><span data-stu-id="08827-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="08827-112">Verbinding met Marketing instellen</span><span class="sxs-lookup"><span data-stu-id="08827-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="08827-113">Ga naar **Beheerder** > **Verbindingen**.</span><span class="sxs-lookup"><span data-stu-id="08827-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="08827-114">Selecteer **Verbinding toevoegen** en kies **Dynamics 365 Marketing** om de verbinding te configureren.</span><span class="sxs-lookup"><span data-stu-id="08827-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="08827-115">Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="08827-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="08827-116">De naam en het type verbinding beschrijven deze verbinding.</span><span class="sxs-lookup"><span data-stu-id="08827-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="08827-117">We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.</span><span class="sxs-lookup"><span data-stu-id="08827-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="08827-118">Kies wie deze verbinding kan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="08827-118">Choose who can use this connection.</span></span> <span data-ttu-id="08827-119">Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling.</span><span class="sxs-lookup"><span data-stu-id="08827-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="08827-120">Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="08827-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="08827-121">Voer de Marketing-URL van uw organisatie in het veld **Serveradres** in.</span><span class="sxs-lookup"><span data-stu-id="08827-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="08827-122">Selecteer in de sectie **Account van serverbeheerder** de optie **Aanmelden** en kies een Dynamics 365 Marketing-account.</span><span class="sxs-lookup"><span data-stu-id="08827-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="08827-123">Wijs een klant-id-veld toe aan de Dynamics 365-contactpersoon-id.</span><span class="sxs-lookup"><span data-stu-id="08827-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="08827-124">Selecteer **Opslaan** om de verbinding te voltooien.</span><span class="sxs-lookup"><span data-stu-id="08827-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="08827-125">Een export configureren</span><span class="sxs-lookup"><span data-stu-id="08827-125">Configure an export</span></span>

<span data-ttu-id="08827-126">U kunt deze export configureren als u toegang hebt tot een verbinding van dit type.</span><span class="sxs-lookup"><span data-stu-id="08827-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="08827-127">Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="08827-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="08827-128">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="08827-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="08827-129">Selecteer **Bestemming toevoegen** om een nieuwe export te maken.</span><span class="sxs-lookup"><span data-stu-id="08827-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="08827-130">Kies in het veld **Verbinding voor export** een verbinding uit de sectie Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="08827-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="08827-131">Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="08827-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="08827-132">Kies een of meer segmenten.</span><span class="sxs-lookup"><span data-stu-id="08827-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="08827-133">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="08827-133">Select **Save**.</span></span>

<span data-ttu-id="08827-134">Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="08827-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="08827-135">De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="08827-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="08827-136">U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="08827-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
