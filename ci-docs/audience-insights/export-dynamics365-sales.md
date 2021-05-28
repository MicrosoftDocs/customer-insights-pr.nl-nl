---
title: Customer Insights-gegevens exporteren naar Dynamics 365 Sales
description: Leer hoe u de verbinding configureert en exporteert naar Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 328bb2f26ebcea234fb645e5225930ab12f82a8b
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976220"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="a3d3e-103">Segmenten gebruiken in Dynamics 365 Sales (preview)</span><span class="sxs-lookup"><span data-stu-id="a3d3e-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="a3d3e-104">Gebruik uw klantgegevens om marketinglijsten te maken, werkstromen op te volgen en aanbiedingen te verzenden met Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="a3d3e-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="a3d3e-105">Vereiste voor verbinding</span><span class="sxs-lookup"><span data-stu-id="a3d3e-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="a3d3e-106">Contactpersoonrecords moeten aanwezig zijn in Dynamics 365 Sales voordat u een segment van Customer Insights naar Sales kunt exporteren.</span><span class="sxs-lookup"><span data-stu-id="a3d3e-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="a3d3e-107">Lees meer over het opnemen van contactpersonen in [Dynamics 365 Sales met Common Data Services](connect-power-query.md)​.</span><span class="sxs-lookup"><span data-stu-id="a3d3e-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="a3d3e-108">Als u segmenten van doelgroepinzichten naar Sales exporteert, worden er geen nieuwe contactpersoonrecords gemaakt in de Sales-exemplaren.</span><span class="sxs-lookup"><span data-stu-id="a3d3e-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="a3d3e-109">De contactpersoonrecords van Sales moeten worden opgenomen in doelgroepinzichten en worden gebruikt als een gegevensbron.</span><span class="sxs-lookup"><span data-stu-id="a3d3e-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="a3d3e-110">Ze moeten ook worden opgenomen in de geharmoniseerde klantentiteit om klant-id's toe te wijzen aan contactpersoon-id's voordat segmenten kunnen worden geëxporteerd.</span><span class="sxs-lookup"><span data-stu-id="a3d3e-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="a3d3e-111">De verbinding instellen met Sales</span><span class="sxs-lookup"><span data-stu-id="a3d3e-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="a3d3e-112">Ga naar **Beheerder** > **Verbindingen**.</span><span class="sxs-lookup"><span data-stu-id="a3d3e-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a3d3e-113">Selecteer **Verbinding toevoegen** en kies **Dynamics 365 Sales** om de verbinding te configureren.</span><span class="sxs-lookup"><span data-stu-id="a3d3e-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="a3d3e-114">Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="a3d3e-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a3d3e-115">De naam en het type verbinding beschrijven deze verbinding.</span><span class="sxs-lookup"><span data-stu-id="a3d3e-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a3d3e-116">We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.</span><span class="sxs-lookup"><span data-stu-id="a3d3e-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a3d3e-117">Kies wie deze verbinding kan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="a3d3e-117">Choose who can use this connection.</span></span> <span data-ttu-id="a3d3e-118">Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling.</span><span class="sxs-lookup"><span data-stu-id="a3d3e-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a3d3e-119">Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a3d3e-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a3d3e-120">Voer de Sales-URL van uw organisatie in het veld **Serveradres** in.</span><span class="sxs-lookup"><span data-stu-id="a3d3e-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="a3d3e-121">Selecteer in de sectie **Account van serverbeheerder** de optie **Aanmelden** en kies een Dynamics 365 Sales-account.</span><span class="sxs-lookup"><span data-stu-id="a3d3e-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="a3d3e-122">Wijs een klant-id-veld toe aan de Dynamics 365-contactpersoon-id.</span><span class="sxs-lookup"><span data-stu-id="a3d3e-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="a3d3e-123">Selecteer **Opslaan** om de verbinding te voltooien.</span><span class="sxs-lookup"><span data-stu-id="a3d3e-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="a3d3e-124">Een export configureren</span><span class="sxs-lookup"><span data-stu-id="a3d3e-124">Configure an export</span></span>

<span data-ttu-id="a3d3e-125">U kunt deze export configureren als u toegang hebt tot een verbinding van dit type.</span><span class="sxs-lookup"><span data-stu-id="a3d3e-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a3d3e-126">Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a3d3e-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a3d3e-127">Ga naar **Gegevens** > **Exports**.</span><span class="sxs-lookup"><span data-stu-id="a3d3e-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a3d3e-128">Selecteer **Bestemming toevoegen** om een nieuwe export te maken.</span><span class="sxs-lookup"><span data-stu-id="a3d3e-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a3d3e-129">Kies in het veld **Verbinding voor export** een verbinding uit de sectie Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="a3d3e-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="a3d3e-130">Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="a3d3e-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a3d3e-131">Kies een of meer segmenten.</span><span class="sxs-lookup"><span data-stu-id="a3d3e-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="a3d3e-132">Selecteer **Opslaan**</span><span class="sxs-lookup"><span data-stu-id="a3d3e-132">Select **Save**</span></span>

<span data-ttu-id="a3d3e-133">Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="a3d3e-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a3d3e-134">De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a3d3e-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a3d3e-135">U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a3d3e-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
