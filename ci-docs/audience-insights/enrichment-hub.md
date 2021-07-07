---
title: Geharmoniseerde klantprofielen verrijken
description: Gebruik mogelijkheden om uw klantgegevens te verrijken.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c35e73b366fcd5db2ba5a757295ddda6db30efa0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305242"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="32087-103">Verrijking voor klantprofielen (preview)</span><span class="sxs-lookup"><span data-stu-id="32087-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="32087-104">Gebruik gegevens vanuit bronnen zoals Microsoft en andere partners om uw klantgegevens te verrijken.</span><span class="sxs-lookup"><span data-stu-id="32087-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Pagina van verrijkingshub":::

<span data-ttu-id="32087-106">Ga in doelgroepinzichten naar **Gegevens** > **Verrijking** om te werken met verrijkingsopties.</span><span class="sxs-lookup"><span data-stu-id="32087-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>  

<span data-ttu-id="32087-107">U hebt de machtigingen Inzender of Beheerder nodig om verrijkingen te kunnen maken of bewerken.</span><span class="sxs-lookup"><span data-stu-id="32087-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="32087-108">Zie [Machtigingen](permissions.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="32087-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="32087-109">Op het tabblad **Ontdekken** vindt u de volgende verrijkingen:</span><span class="sxs-lookup"><span data-stu-id="32087-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="32087-110">[Merken](enrichment-microsoft.md) die worden geleverd door Microsoft</span><span class="sxs-lookup"><span data-stu-id="32087-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="32087-111">[Interesses](enrichment-microsoft.md) die worden geleverd door Microsoft</span><span class="sxs-lookup"><span data-stu-id="32087-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="32087-112">[Uitgebreide adressen](enrichment-enhanced-addresses.md) geleverd door Microsoft</span><span class="sxs-lookup"><span data-stu-id="32087-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="32087-113">[Bedrijfsgegevens](enrichment-leadspace.md) worden verstrekt door Leadspace</span><span class="sxs-lookup"><span data-stu-id="32087-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="32087-114">[Demografische gegevens](enrichment-experian.md) geleverd door Experian</span><span class="sxs-lookup"><span data-stu-id="32087-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="32087-115">[Locatiegegevens](enrichment-here.md) worden geleverd door HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="32087-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="32087-116">[Aangepaste gegevens](enrichment-SFTP-custom-import.md) via Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="32087-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="32087-117">Op het tabblad **Mijn verrijkingen** kunt u de verrijkingen zien die u hebt geconfigureerd en hun eigenschappen bewerken.</span><span class="sxs-lookup"><span data-stu-id="32087-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="32087-118">Bestaande verrijkingen beheren</span><span class="sxs-lookup"><span data-stu-id="32087-118">Manage existing enrichments</span></span>

<span data-ttu-id="32087-119">Ga naar het tabblad **Mijn verrijkingen** om alle geconfigureerde verrijkingen te zien.</span><span class="sxs-lookup"><span data-stu-id="32087-119">Go to the **My enrichments** tab to see all configured enrichments.</span></span> <span data-ttu-id="32087-120">Elke verrijking wordt weergegeven als een rij met aanvullende informatie over de verrijking.</span><span class="sxs-lookup"><span data-stu-id="32087-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="32087-121">Selecteer een verrijking om de beschikbare opties te zien.</span><span class="sxs-lookup"><span data-stu-id="32087-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="32087-122">U kunt ook het beletselteken (...) in een lijstitem selecteren om de opties te zien.</span><span class="sxs-lookup"><span data-stu-id="32087-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opties om verrijkingen in de lijst met verrijkingen te beheren":::

- <span data-ttu-id="32087-124">**Bekijk** verrijkingsdetails met het aantal verrijkte klantprofielen.</span><span class="sxs-lookup"><span data-stu-id="32087-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="32087-125">**Bewerk** de verrijkingsconfiguratie.</span><span class="sxs-lookup"><span data-stu-id="32087-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="32087-126">**Voer** de verrijking uit om klantprofielen bij te werken met de laatste gegevens.</span><span class="sxs-lookup"><span data-stu-id="32087-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="32087-127">**Deactiveer** een bestaande verrijking om te voorkomen dat deze automatisch wordt vernieuwd bij elke geplande vernieuwing.</span><span class="sxs-lookup"><span data-stu-id="32087-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="32087-128">Gegevens van de laatste geslaagde vernieuwing blijven beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="32087-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="32087-129">**Activeer** een inactieve verrijking om automatisch vernieuwen opnieuw te starten bij elke geplande vernieuwing.</span><span class="sxs-lookup"><span data-stu-id="32087-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="32087-130">Een verrijking **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="32087-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="32087-131">U kunt meerdere verrijkingen tegelijk uitvoeren of deactiveren door ze in de lijst te selecteren.</span><span class="sxs-lookup"><span data-stu-id="32087-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="32087-132">Opties voor bekijken en bewerken zijn niet beschikbaar als bulkactie en werken slechts voor één verrijking tegelijk.</span><span class="sxs-lookup"><span data-stu-id="32087-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="32087-133">Verrijkingen en verbindingen</span><span class="sxs-lookup"><span data-stu-id="32087-133">Enrichments and connections</span></span>

<span data-ttu-id="32087-134">Verrijkingen van derden worden geconfigureerd met [verbindingen](connections.md), die een beheerder instelt met referenties en die toestemming verlenen voor gegevensoverdracht.</span><span class="sxs-lookup"><span data-stu-id="32087-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="32087-135">De verbinding kan door beheerders en inzenders worden gebruikt voor het configureren van verrijkingen.</span><span class="sxs-lookup"><span data-stu-id="32087-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="32087-136">Meerdere verrijkingen van hetzelfde type</span><span class="sxs-lookup"><span data-stu-id="32087-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="32087-137">De entiteit die moet worden verrijkt, wordt gespecificeerd tijdens de verrijkingsconfiguratie, waardoor u de mogelijkheid hebt om slechts een subset van uw profielen te verrijken.</span><span class="sxs-lookup"><span data-stu-id="32087-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="32087-138">Verrijk bijvoorbeeld alleen gegevens voor een specifiek segment.</span><span class="sxs-lookup"><span data-stu-id="32087-138">For example, enrich data only for a specific segment.</span></span> <span data-ttu-id="32087-139">U kunt meerdere verrijkingen van hetzelfde type configureren en dezelfde verbinding opnieuw gebruiken.</span><span class="sxs-lookup"><span data-stu-id="32087-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="32087-140">Sommige verrijkingen hebben limieten voor het aantal verrijkingen van hetzelfde type dat kan worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="32087-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="32087-141">De limieten en het huidige gebruik zijn te zien op de pagina **Verrijking**.</span><span class="sxs-lookup"><span data-stu-id="32087-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
