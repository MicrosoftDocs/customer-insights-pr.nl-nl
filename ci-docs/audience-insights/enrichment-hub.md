---
title: Geharmoniseerde klantprofielen verrijken
description: Gebruik mogelijkheden om uw klantgegevens te verrijken.
ms.date: 11/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 36e6f7f8fcd64fc2591e913910918b83bf27567b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597689"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="ab090-103">Verrijking voor klantprofielen (preview)</span><span class="sxs-lookup"><span data-stu-id="ab090-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="ab090-104">Gebruik gegevens vanuit bronnen zoals Microsoft en andere partners om uw klantgegevens te verrijken.</span><span class="sxs-lookup"><span data-stu-id="ab090-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Pagina van verrijkingshub":::

<span data-ttu-id="ab090-106">Ga in doelgroepinzichten naar **Gegevens** > **Verrijking** om te werken met verrijkingsopties.</span><span class="sxs-lookup"><span data-stu-id="ab090-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="ab090-107">U hebt de machtigingen Inzender of Beheerder nodig om verrijkingen te kunnen maken of bewerken.</span><span class="sxs-lookup"><span data-stu-id="ab090-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="ab090-108">Zie [Machtigingen](permissions.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ab090-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="ab090-109">Op het tabblad **Ontdekken** vindt u de volgende verrijkingen:</span><span class="sxs-lookup"><span data-stu-id="ab090-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="ab090-110">[Merken](enrichment-microsoft-graph.md) die worden verstrekt door Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="ab090-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="ab090-111">[Interesses](enrichment-microsoft-graph.md) die worden verstrekt door Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="ab090-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="ab090-112">[Bedrijfsgegevens](enrichment-leadspace.md) worden verstrekt door Leadspace</span><span class="sxs-lookup"><span data-stu-id="ab090-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="ab090-113">[Demografische gegevens](enrichment-experian.md) die worden geleverd door Experian</span><span class="sxs-lookup"><span data-stu-id="ab090-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="ab090-114">[Locatiegegevens](enrichment-here.md) worden geleverd door HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="ab090-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="ab090-115">[Aangepaste gegevens](enrichment-SFTP-custom-import.md) via Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="ab090-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="ab090-116">Op het tabblad **Mijn verrijkingen** kunt u de verrijkingen zien die u hebt geconfigureerd en hun eigenschappen bewerken.</span><span class="sxs-lookup"><span data-stu-id="ab090-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="ab090-117">Bestaande verrijkingen beheren</span><span class="sxs-lookup"><span data-stu-id="ab090-117">Manage existing enrichments</span></span>

<span data-ttu-id="ab090-118">Ga naar **Mijn verrijkingen** om alle geconfigureerde verrijkingen te zien.</span><span class="sxs-lookup"><span data-stu-id="ab090-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="ab090-119">Elke verrijking wordt weergegeven als een rij met aanvullende informatie over de verrijking.</span><span class="sxs-lookup"><span data-stu-id="ab090-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="ab090-120">Selecteer een verrijking om de beschikbare opties te zien.</span><span class="sxs-lookup"><span data-stu-id="ab090-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="ab090-121">U kunt ook het beletselteken (...) op een lijstitem selecteren om de opties te zien.</span><span class="sxs-lookup"><span data-stu-id="ab090-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opties om verrijkingen in de lijst met verrijkingen te beheren":::

- <span data-ttu-id="ab090-123">**Bekijk** verrijkingsdetails met het aantal verrijkte klantprofielen.</span><span class="sxs-lookup"><span data-stu-id="ab090-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="ab090-124">**Bewerk** de verrijkingsconfiguratie.</span><span class="sxs-lookup"><span data-stu-id="ab090-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="ab090-125">**Voer** de verrijking uit om klantprofielen bij te werken met de laatste gegevens.</span><span class="sxs-lookup"><span data-stu-id="ab090-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="ab090-126">**Deactiveer** een bestaande verrijking om te voorkomen dat deze automatisch wordt vernieuwd bij elke geplande vernieuwing.</span><span class="sxs-lookup"><span data-stu-id="ab090-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="ab090-127">Gegevens van de laatste geslaagde vernieuwing blijven beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="ab090-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="ab090-128">**Activeer** een inactieve verrijking om automatisch vernieuwen opnieuw te starten bij elke geplande vernieuwing.</span><span class="sxs-lookup"><span data-stu-id="ab090-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="ab090-129">Een verrijking **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="ab090-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="ab090-130">U kunt meerdere verrijkingen tegelijk uitvoeren of deactiveren door ze in de lijst te selecteren.</span><span class="sxs-lookup"><span data-stu-id="ab090-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="ab090-131">Opties voor bekijken en bewerken zijn niet beschikbaar als bulkactie en werken slechts voor één verrijking tegelijk.</span><span class="sxs-lookup"><span data-stu-id="ab090-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]