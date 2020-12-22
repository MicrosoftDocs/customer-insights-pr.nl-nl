---
title: Customer Insights-gegevens exporteren naar Dynamics 365 Marketing
description: Leer hoe u de verbinding met Dynamics 365 Marketing configureert.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643767"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="8363d-103">Connector voor Dynamics 365 Marketing (preview)</span><span class="sxs-lookup"><span data-stu-id="8363d-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="8363d-104">Gebruik de [segmenten](segments.md) om campagnes te genereren en contact op te nemen met specifieke groepen klanten met Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="8363d-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="8363d-105">Zie [Segmenten van Dynamics 365 Customer Insights gebruiken met Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8363d-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="8363d-106">Vereisten</span><span class="sxs-lookup"><span data-stu-id="8363d-106">Prerequisite</span></span>

<span data-ttu-id="8363d-107">Contactpersoonrecords [van Dynamics 365 Marketing opgenomen door Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="8363d-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="8363d-108">De connector voor Marketing configureren</span><span class="sxs-lookup"><span data-stu-id="8363d-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="8363d-109">Ga in doelgroepinzichten naar **Beheer** > **Exportbestemmingen**.</span><span class="sxs-lookup"><span data-stu-id="8363d-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="8363d-110">Ga naar **Dynamics 365 Marketing** en selecteer **Instellen**.</span><span class="sxs-lookup"><span data-stu-id="8363d-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="8363d-111">Geef uw exportbestemming een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="8363d-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="8363d-112">Voer de Marketing-URL van uw organisatie in het veld **Serveradres** in.</span><span class="sxs-lookup"><span data-stu-id="8363d-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="8363d-113">Selecteer in de sectie **Account van serverbeheerder** de optie **Aanmelden** en kies een Dynamics 365 Marketing-account.</span><span class="sxs-lookup"><span data-stu-id="8363d-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="8363d-114">Wijs een klant-id-veld toe aan de Dynamics 365-contactpersoon-id.</span><span class="sxs-lookup"><span data-stu-id="8363d-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="8363d-115">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="8363d-115">Select **Next**.</span></span>

1. <span data-ttu-id="8363d-116">Kies een of meer segmenten.</span><span class="sxs-lookup"><span data-stu-id="8363d-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="8363d-117">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="8363d-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="8363d-118">De gegevens exporteren</span><span class="sxs-lookup"><span data-stu-id="8363d-118">Export the data</span></span>

<span data-ttu-id="8363d-119">U kunt [gegevens op aanvraag exporteren](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="8363d-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="8363d-120">De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8363d-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
