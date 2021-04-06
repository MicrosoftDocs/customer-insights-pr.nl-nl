---
title: Power Apps-connector
description: Maak verbinding met Power Apps en Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3fa91553fd50a22ab62b5a2b1e3f13b9483776a8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598149"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="3ce59-103">Microsoft Power Apps-connector (preview)</span><span class="sxs-lookup"><span data-stu-id="3ce59-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="3ce59-104">Breng geharmoniseerde klantprofielen naar uw gepersonaliseerde apps met Power Apps.</span><span class="sxs-lookup"><span data-stu-id="3ce59-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="3ce59-105">Verbinden met Power Apps en Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="3ce59-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="3ce59-106">Customer Insights is een van de vele [beschikbare bronnen voor gegevens in Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="3ce59-106">Customer Insights is one of the many [available sources for data in Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="3ce59-107">Raadpleeg de Power Apps-documentatie om te leren hoe [hoe u een gegevensverbinding kunt toevoegen aan een app](/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="3ce59-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="3ce59-108">We raden u aan om ook te bekijken [hoe Power Apps delegeren gebruikt om grote gegevenssets in Canvas-apps te verwerken](/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="3ce59-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="3ce59-109">Beschikbare entiteiten</span><span class="sxs-lookup"><span data-stu-id="3ce59-109">Available entities</span></span>

<span data-ttu-id="3ce59-110">Na het toevoegen van Customer Insights als een gegevensverbinding, kunt u de volgende entiteiten kiezen in Power Apps:</span><span class="sxs-lookup"><span data-stu-id="3ce59-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="3ce59-111">Klant: om gegevens uit het [geharmoniseerde klantprofiel](customer-profiles.md) te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="3ce59-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="3ce59-112">Geharmoniseerde activiteit: om de [activiteitentijdlijn weer te geven](activities.md) in de app.</span><span class="sxs-lookup"><span data-stu-id="3ce59-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="3ce59-113">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="3ce59-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="3ce59-114">Ophaalbare entiteiten</span><span class="sxs-lookup"><span data-stu-id="3ce59-114">Retrievable entities</span></span>

<span data-ttu-id="3ce59-115">U kunt alleen de entiteiten **Klant**, **UnifiedActivity** en **Segmenten** ophalen via de Power Apps-connector.</span><span class="sxs-lookup"><span data-stu-id="3ce59-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="3ce59-116">Andere entiteiten worden weergegeven omdat de onderliggende connector deze ondersteunt via triggers in Power Automate.</span><span class="sxs-lookup"><span data-stu-id="3ce59-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="3ce59-117">Overdracht</span><span class="sxs-lookup"><span data-stu-id="3ce59-117">Delegation</span></span>

<span data-ttu-id="3ce59-118">Delegatie werkt voor de entiteit Klant en de entiteit UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="3ce59-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="3ce59-119">Delegatie voor **Klant**-entiteit: om delegatie voor deze entiteit te gebruiken, moeten de velden worden geïndexeerd in [Zoek- en filterindex](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="3ce59-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="3ce59-120">Delegatie voor **UnifiedActivity**: delegatie voor deze entiteit werkt alleen voor de velden **ActivityId** en **CustomerId**.</span><span class="sxs-lookup"><span data-stu-id="3ce59-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="3ce59-121">Zie [Delegeerbare functies en bewerkingen in Power Apps](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps) voor meer informatie over delegeren .</span><span class="sxs-lookup"><span data-stu-id="3ce59-121">For more information about delegation, see [Power Apps delegable functions and operations](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="3ce59-122">Voorbeeld galeriebesturingselement</span><span class="sxs-lookup"><span data-stu-id="3ce59-122">Example gallery control</span></span>

<span data-ttu-id="3ce59-123">U voegt bijvoorbeeld klantprofielen toe aan een [galeriebesturingselement](/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="3ce59-123">For example, you add customer profiles to a [gallery control](/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="3ce59-124">Voeg een besturingselement **Galerie** toe aan een app die u aan het bouwen bent.</span><span class="sxs-lookup"><span data-stu-id="3ce59-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3ce59-125">![Een galerie-element toevoegen](media/connector-powerapps9.png "Een galerie-element toevoegen")</span><span class="sxs-lookup"><span data-stu-id="3ce59-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="3ce59-126">Selecteer **Klant** als gegevensbron voor items.</span><span class="sxs-lookup"><span data-stu-id="3ce59-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="3ce59-127">![Een gegevensbron selecteren](media/choose-datasource-powerapps.png "Een gegevensbron selecteren")</span><span class="sxs-lookup"><span data-stu-id="3ce59-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="3ce59-128">U kunt het gegevenspaneel aan de rechterkant wijzigen om te selecteren welk veld voor de entiteit Klant moet worden weergegeven in de galerie.</span><span class="sxs-lookup"><span data-stu-id="3ce59-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="3ce59-129">Als u een willekeurig veld van de geselecteerde klant in de galerie wilt weergeven, vult u de eigenschap Tekst van een label in: **{Name_of_the_gallery}.Selected.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="3ce59-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="3ce59-130">Voorbeeld: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="3ce59-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="3ce59-131">Als u de geharmoniseerde tijdlijn voor een klant wilt weergeven, voegt u een galerie-element toe en voegt u de eigenschap Items toe: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="3ce59-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="3ce59-132">Voorbeeld: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="3ce59-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]