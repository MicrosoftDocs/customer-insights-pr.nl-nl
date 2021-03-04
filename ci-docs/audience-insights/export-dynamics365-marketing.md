---
title: Customer Insights-gegevens exporteren naar Dynamics 365 Marketing
description: Leer hoe u de verbinding met Dynamics 365 Marketing configureert.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269048"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="66863-103">Connector voor Dynamics 365 Marketing (preview)</span><span class="sxs-lookup"><span data-stu-id="66863-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="66863-104">Gebruik de [segmenten](segments.md) om campagnes te genereren en contact op te nemen met specifieke groepen klanten met Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="66863-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="66863-105">Zie [Segmenten van Dynamics 365 Customer Insights gebruiken met Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="66863-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="66863-106">Vereiste</span><span class="sxs-lookup"><span data-stu-id="66863-106">Prerequisite</span></span>

- <span data-ttu-id="66863-107">Contactpersoonsrecords moeten aanwezig zijn in Dynamics 365 Marketing voordat u een segment van Customer Insights naar Marketing kunt exporteren.</span><span class="sxs-lookup"><span data-stu-id="66863-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="66863-108">Lees meer over het opnemen van contactpersonen in [Dynamics 365 Marketing met Common Data Services](connect-power-query.md)​.</span><span class="sxs-lookup"><span data-stu-id="66863-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="66863-109">Als u segmenten van doelgroepinzichten naar Marketing exporteert, worden er geen nieuwe contactpersoonrecords gemaakt in de Marketing-exemplaren.</span><span class="sxs-lookup"><span data-stu-id="66863-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="66863-110">De contactpersoonrecords van Marketing moeten worden opgenomen in doelgroepinzichten en worden gebruikt als een gegevensbron.</span><span class="sxs-lookup"><span data-stu-id="66863-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="66863-111">Ze moeten ook worden opgenomen in de geharmoniseerde klantentiteit om klant-id's toe te wijzen aan contactpersoon-id's voordat segmenten kunnen worden geëxporteerd.</span><span class="sxs-lookup"><span data-stu-id="66863-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="66863-112">De connector voor Marketing configureren</span><span class="sxs-lookup"><span data-stu-id="66863-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="66863-113">Ga in doelgroepinzichten naar **Beheer** > **Exportbestemmingen**.</span><span class="sxs-lookup"><span data-stu-id="66863-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="66863-114">Ga naar **Dynamics 365 Marketing** en selecteer **Instellen**.</span><span class="sxs-lookup"><span data-stu-id="66863-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="66863-115">Geef uw exportbestemming een herkenbare naam in het veld **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="66863-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="66863-116">Voer de Marketing-URL van uw organisatie in het veld **Serveradres** in.</span><span class="sxs-lookup"><span data-stu-id="66863-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="66863-117">Selecteer in de sectie **Account van serverbeheerder** de optie **Aanmelden** en kies een Dynamics 365 Marketing-account.</span><span class="sxs-lookup"><span data-stu-id="66863-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="66863-118">Wijs een klant-id-veld toe aan de Dynamics 365-contactpersoon-id.</span><span class="sxs-lookup"><span data-stu-id="66863-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="66863-119">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="66863-119">Select **Next**.</span></span>

1. <span data-ttu-id="66863-120">Kies een of meer segmenten.</span><span class="sxs-lookup"><span data-stu-id="66863-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="66863-121">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="66863-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="66863-122">De gegevens exporteren</span><span class="sxs-lookup"><span data-stu-id="66863-122">Export the data</span></span>

<span data-ttu-id="66863-123">U kunt [gegevens op aanvraag exporteren](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="66863-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="66863-124">De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="66863-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]