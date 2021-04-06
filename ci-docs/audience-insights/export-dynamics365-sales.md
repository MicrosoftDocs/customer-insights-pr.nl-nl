---
title: Customer Insights-gegevens exporteren naar Dynamics 365 Sales
description: Leer hoe u de verbinding met Dynamics 365 Sales configureert.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598103"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="0129e-103">Connector voor Dynamics 365 Sales (preview)</span><span class="sxs-lookup"><span data-stu-id="0129e-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="0129e-104">Gebruik uw klantgegevens om marketinglijsten te maken, werkstromen op te volgen en aanbiedingen te verzenden met Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="0129e-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="0129e-105">Vereiste</span><span class="sxs-lookup"><span data-stu-id="0129e-105">Prerequisite</span></span>

1. <span data-ttu-id="0129e-106">Contactpersoonrecords moeten aanwezig zijn in Dynamics 365 Sales voordat u een segment van Customer Insights naar Sales kunt exporteren.</span><span class="sxs-lookup"><span data-stu-id="0129e-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="0129e-107">Lees meer over het opnemen van contactpersonen in [Dynamics 365 Sales met Common Data Services](connect-power-query.md)​.</span><span class="sxs-lookup"><span data-stu-id="0129e-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="0129e-108">Als u segmenten van doelgroepinzichten naar Sales exporteert, worden er geen nieuwe contactpersoonrecords gemaakt in de Sales-exemplaren.</span><span class="sxs-lookup"><span data-stu-id="0129e-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="0129e-109">De contactpersoonrecords van Sales moeten worden opgenomen in doelgroepinzichten en worden gebruikt als een gegevensbron.</span><span class="sxs-lookup"><span data-stu-id="0129e-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="0129e-110">Ze moeten ook worden opgenomen in de geharmoniseerde klantentiteit om klant-id's toe te wijzen aan contactpersoon-id's voordat segmenten kunnen worden geëxporteerd.</span><span class="sxs-lookup"><span data-stu-id="0129e-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="0129e-111">De connector voor Sales configureren</span><span class="sxs-lookup"><span data-stu-id="0129e-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="0129e-112">Ga in doelgroepinzichten naar **Beheer** > **Exportbestemmingen**.</span><span class="sxs-lookup"><span data-stu-id="0129e-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="0129e-113">Ga naar **Dynamics 365 Sales** en selecteer **Instellen**.</span><span class="sxs-lookup"><span data-stu-id="0129e-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="0129e-114">Geef uw exportbestemming een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="0129e-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="0129e-115">Voer de Sales-URL van uw organisatie in het veld **Serveradres** in.</span><span class="sxs-lookup"><span data-stu-id="0129e-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="0129e-116">Selecteer in de sectie **Account van serverbeheerder** de optie **Aanmelden** en kies een Dynamics 365 Sales-account.</span><span class="sxs-lookup"><span data-stu-id="0129e-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="0129e-117">Wijs een klant-id-veld toe aan de Dynamics 365-contactpersoon-id.</span><span class="sxs-lookup"><span data-stu-id="0129e-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="0129e-118">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0129e-118">Select **Next**.</span></span>

1. <span data-ttu-id="0129e-119">Kies een of meer segmenten.</span><span class="sxs-lookup"><span data-stu-id="0129e-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="0129e-120">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="0129e-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="0129e-121">De gegevens exporteren</span><span class="sxs-lookup"><span data-stu-id="0129e-121">Export the data</span></span>

<span data-ttu-id="0129e-122">U kunt [gegevens op aanvraag exporteren](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="0129e-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="0129e-123">De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0129e-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]