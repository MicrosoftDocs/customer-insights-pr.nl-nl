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
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895999"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="94019-103">Verrijking voor klantprofielen (preview)</span><span class="sxs-lookup"><span data-stu-id="94019-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="94019-104">Gebruik gegevens vanuit bronnen zoals Microsoft en andere partners om uw klantgegevens te verrijken.</span><span class="sxs-lookup"><span data-stu-id="94019-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Pagina van verrijkingshub":::

<span data-ttu-id="94019-106">Ga in doelgroepinzichten naar **Gegevens** > **Verrijking** om te werken met verrijkingsopties.</span><span class="sxs-lookup"><span data-stu-id="94019-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="94019-107">U hebt de machtigingen Inzender of Beheerder nodig om verrijkingen te kunnen maken of bewerken.</span><span class="sxs-lookup"><span data-stu-id="94019-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="94019-108">Zie [Machtigingen](permissions.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="94019-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="94019-109">Op het tabblad **Ontdekken** vindt u de volgende verrijkingen:</span><span class="sxs-lookup"><span data-stu-id="94019-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="94019-110">[Merken](enrichment-microsoft.md) die worden geleverd door Microsoft</span><span class="sxs-lookup"><span data-stu-id="94019-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="94019-111">[Interesses](enrichment-microsoft.md) die worden geleverd door Microsoft</span><span class="sxs-lookup"><span data-stu-id="94019-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="94019-112">[Bedrijfsgegevens](enrichment-leadspace.md) worden verstrekt door Leadspace</span><span class="sxs-lookup"><span data-stu-id="94019-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="94019-113">[Demografische gegevens](enrichment-experian.md) die worden geleverd door Experian</span><span class="sxs-lookup"><span data-stu-id="94019-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="94019-114">[Locatiegegevens](enrichment-here.md) worden geleverd door HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="94019-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="94019-115">[Aangepaste gegevens](enrichment-SFTP-custom-import.md) via Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="94019-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="94019-116">Op het tabblad **Mijn verrijkingen** kunt u de verrijkingen zien die u hebt geconfigureerd en hun eigenschappen bewerken.</span><span class="sxs-lookup"><span data-stu-id="94019-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="94019-117">Bestaande verrijkingen beheren</span><span class="sxs-lookup"><span data-stu-id="94019-117">Manage existing enrichments</span></span>

<span data-ttu-id="94019-118">Ga naar **Mijn verrijkingen** om alle geconfigureerde verrijkingen te zien.</span><span class="sxs-lookup"><span data-stu-id="94019-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="94019-119">Elke verrijking wordt weergegeven als een rij met aanvullende informatie over de verrijking.</span><span class="sxs-lookup"><span data-stu-id="94019-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="94019-120">Selecteer een verrijking om de beschikbare opties te zien.</span><span class="sxs-lookup"><span data-stu-id="94019-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="94019-121">U kunt ook het beletselteken (...) in een lijstitem selecteren om de opties te zien.</span><span class="sxs-lookup"><span data-stu-id="94019-121">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opties om verrijkingen in de lijst met verrijkingen te beheren":::

- <span data-ttu-id="94019-123">**Bekijk** verrijkingsdetails met het aantal verrijkte klantprofielen.</span><span class="sxs-lookup"><span data-stu-id="94019-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="94019-124">**Bewerk** de verrijkingsconfiguratie.</span><span class="sxs-lookup"><span data-stu-id="94019-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="94019-125">**Voer** de verrijking uit om klantprofielen bij te werken met de laatste gegevens.</span><span class="sxs-lookup"><span data-stu-id="94019-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="94019-126">**Deactiveer** een bestaande verrijking om te voorkomen dat deze automatisch wordt vernieuwd bij elke geplande vernieuwing.</span><span class="sxs-lookup"><span data-stu-id="94019-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="94019-127">Gegevens van de laatste geslaagde vernieuwing blijven beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="94019-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="94019-128">**Activeer** een inactieve verrijking om automatisch vernieuwen opnieuw te starten bij elke geplande vernieuwing.</span><span class="sxs-lookup"><span data-stu-id="94019-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="94019-129">Een verrijking **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="94019-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="94019-130">U kunt meerdere verrijkingen tegelijk uitvoeren of deactiveren door ze in de lijst te selecteren.</span><span class="sxs-lookup"><span data-stu-id="94019-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="94019-131">Opties voor bekijken en bewerken zijn niet beschikbaar als bulkactie en werken slechts voor één verrijking tegelijk.</span><span class="sxs-lookup"><span data-stu-id="94019-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="94019-132">Verrijkingen en verbindingen</span><span class="sxs-lookup"><span data-stu-id="94019-132">Enrichments and connections</span></span>

<span data-ttu-id="94019-133">Verrijkingen van derden worden geconfigureerd met [verbindingen](connections.md), die een beheerder instelt met referenties en die toestemming verlenen voor gegevensoverdracht.</span><span class="sxs-lookup"><span data-stu-id="94019-133">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="94019-134">De verbinding kan door beheerders en inzenders worden gebruikt voor het configureren van verrijkingen.</span><span class="sxs-lookup"><span data-stu-id="94019-134">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="94019-135">Meerdere verrijkingen van hetzelfde type</span><span class="sxs-lookup"><span data-stu-id="94019-135">Multiple enrichments of the same type</span></span>

<span data-ttu-id="94019-136">De entiteit die moet worden verrijkt, wordt gespecificeerd tijdens de verrijkingsconfiguratie, waardoor u de mogelijkheid hebt om slechts een subset van uw profielen te verrijken.</span><span class="sxs-lookup"><span data-stu-id="94019-136">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="94019-137">Verrijk bijvoorbeeld alleen gegevens voor een specifiek segment.</span><span class="sxs-lookup"><span data-stu-id="94019-137">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="94019-138">U kunt meerdere verrijkingen van hetzelfde type configureren en dezelfde verbinding opnieuw gebruiken.</span><span class="sxs-lookup"><span data-stu-id="94019-138">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="94019-139">Sommige verrijkingen hebben limieten voor het aantal verrijkingen van hetzelfde type dat kan worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="94019-139">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="94019-140">De limieten en het huidige gebruik zijn te zien op de pagina **Verrijking**.</span><span class="sxs-lookup"><span data-stu-id="94019-140">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
