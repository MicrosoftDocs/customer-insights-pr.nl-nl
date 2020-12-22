---
title: Customer Insights-gegevens exporteren naar Dynamics 365 Sales
description: Leer hoe u de verbinding met Dynamics 365 Sales configureert.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643812"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="69f9f-103">Connector voor Dynamics 365 Sales (preview)</span><span class="sxs-lookup"><span data-stu-id="69f9f-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="69f9f-104">Uw klantgegevens gebruiken om marketinglijsten te maken, werkstromen op te volgen en aanbiedingen te verzenden met Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="69f9f-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="69f9f-105">Vereisten</span><span class="sxs-lookup"><span data-stu-id="69f9f-105">Prerequisite</span></span>

<span data-ttu-id="69f9f-106">Contactpersoonrecords [van Dynamics 365 Sales opgenomen met Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="69f9f-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="69f9f-107">De connector voor Sales configureren</span><span class="sxs-lookup"><span data-stu-id="69f9f-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="69f9f-108">Ga in doelgroepinzichten naar **Beheer** > **Exportbestemmingen**.</span><span class="sxs-lookup"><span data-stu-id="69f9f-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="69f9f-109">Ga naar **Dynamics 365 Sales** en selecteer **Instellen**.</span><span class="sxs-lookup"><span data-stu-id="69f9f-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="69f9f-110">Geef uw exportbestemming een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="69f9f-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="69f9f-111">Voer de Sales-URL van uw organisatie in het veld **Serveradres** in.</span><span class="sxs-lookup"><span data-stu-id="69f9f-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="69f9f-112">Selecteer in de sectie **Account van serverbeheerder** de optie **Aanmelden** en kies een Dynamics 365 Sales-account.</span><span class="sxs-lookup"><span data-stu-id="69f9f-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="69f9f-113">Wijs een klant-id-veld toe aan de Dynamics 365-contactpersoon-id.</span><span class="sxs-lookup"><span data-stu-id="69f9f-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="69f9f-114">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="69f9f-114">Select **Next**.</span></span>

1. <span data-ttu-id="69f9f-115">Kies een of meer segmenten.</span><span class="sxs-lookup"><span data-stu-id="69f9f-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="69f9f-116">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="69f9f-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="69f9f-117">De gegevens exporteren</span><span class="sxs-lookup"><span data-stu-id="69f9f-117">Export the data</span></span>

<span data-ttu-id="69f9f-118">U kunt [gegevens op aanvraag exporteren](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="69f9f-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="69f9f-119">De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="69f9f-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
