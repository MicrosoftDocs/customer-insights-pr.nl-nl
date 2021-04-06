---
title: Relaties tussen entiteiten en entiteitspaden
description: Maak en beheer relaties tussen entiteiten uit meerdere gegevensbronnen.
ms.date: 04/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c25bfcb8e2a8223498dd1a5e8cfb3712a40ab85e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595206"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="9088e-103">Relaties tussen entiteiten</span><span class="sxs-lookup"><span data-stu-id="9088e-103">Relationships between entities</span></span>

<span data-ttu-id="9088e-104">Relaties helpen u bij het verbinden van entiteiten en het genereren van een grafiek van uw gegevens wanneer entiteiten een gemeenschappelijke identificatie (externe sleutel) delen waarnaar van de ene entiteit naar de andere kan worden verwezen.</span><span class="sxs-lookup"><span data-stu-id="9088e-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="9088e-105">Met verbonden entiteiten kunt u segmenten en meetcriteria definiëren op basis van meerdere gegevensbronnen.</span><span class="sxs-lookup"><span data-stu-id="9088e-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="9088e-106">Er zijn twee typen relaties.</span><span class="sxs-lookup"><span data-stu-id="9088e-106">There are two types of relationships.</span></span> <span data-ttu-id="9088e-107">Niet-bewerkbaar systeemrelaties, die automatisch worden gemaakt, en aangepaste relaties, die worden gemaakt en geconfigureerd door gebruikers.</span><span class="sxs-lookup"><span data-stu-id="9088e-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="9088e-108">Tijdens de afstemmings- en samenvoegingsprocessen worden achter de schermen systeemrelaties gemaakt op basis van intelligente afstemming.</span><span class="sxs-lookup"><span data-stu-id="9088e-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="9088e-109">Deze relaties helpen de klantprofielrecords te relateren aan de records van andere overeenkomstige entiteiten.</span><span class="sxs-lookup"><span data-stu-id="9088e-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="9088e-110">Het volgende diagram illustreert het maken van drie systeemrelaties wanneer de klantentiteit wordt afgestemd met extra entiteiten om de uiteindelijke entiteit Klantprofiel te produceren.</span><span class="sxs-lookup"><span data-stu-id="9088e-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9088e-111">![Het maken van relaties](media/relationships-entities-merge.png "Het maken van relaties")</span><span class="sxs-lookup"><span data-stu-id="9088e-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="9088e-112">**De relatie *CustomerToContact*** is gemaakt tussen de entiteit Klant en de entiteit Contactpersoon.</span><span class="sxs-lookup"><span data-stu-id="9088e-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="9088e-113">De entiteit Klant krijgt het sleutelveld **Contact_contactId** om een relatie tot stand te brengen met het sleutelveld **contactId** van de entiteit Contactpersoon.</span><span class="sxs-lookup"><span data-stu-id="9088e-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="9088e-114">**De relatie *CustomerToAccount*** is gemaakt tussen de entiteit Klant en de entiteit Account.</span><span class="sxs-lookup"><span data-stu-id="9088e-114">***CustomerToAccount* relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="9088e-115">De entiteit Klant krijgt het sleutelveld **Account_accountId** om een relatie tot stand te brengen met het sleutelveld **accountId** van de entiteit Account.</span><span class="sxs-lookup"><span data-stu-id="9088e-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="9088e-116">**De relatie *CustomerToWebAccount*** is gemaakt tussen de entiteit Klant en de entiteit WebAccount.</span><span class="sxs-lookup"><span data-stu-id="9088e-116">***CustomerToWebAccount* relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="9088e-117">De entiteit Klant krijgt het sleutelveld **WebAccount_webaccountId** om een relatie tot stand te brengen met het sleutelveld **webaccountId** van de entiteit WebAccount.</span><span class="sxs-lookup"><span data-stu-id="9088e-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="9088e-118">Een relatie maken</span><span class="sxs-lookup"><span data-stu-id="9088e-118">Create a relationship</span></span>

<span data-ttu-id="9088e-119">Definieer aangepaste relaties op de pagina **Relaties**.</span><span class="sxs-lookup"><span data-stu-id="9088e-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="9088e-120">Elke relatie bestaat uit een bronentiteit (de entiteit die de externe sleutel bevat) en een doelentiteit (de entiteit waarnaar de externe sleutel van de bronentiteit verwijst).</span><span class="sxs-lookup"><span data-stu-id="9088e-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="9088e-121">Ga in doelgroepinzichten naar **Gegevens** > **Relaties**.</span><span class="sxs-lookup"><span data-stu-id="9088e-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="9088e-122">Selecteer **Nieuwe relatie**.</span><span class="sxs-lookup"><span data-stu-id="9088e-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="9088e-123">Geef in het deelvenster **Relatie toevoegen** de volgende informatie op:</span><span class="sxs-lookup"><span data-stu-id="9088e-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9088e-124">![Relatiedetails invoeren](media/relationships-add.png "Relatiedetails invoeren")</span><span class="sxs-lookup"><span data-stu-id="9088e-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="9088e-125">**Relatienaam**: naam die het doel van de relatie weergeeft (bijvoorbeeld **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="9088e-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="9088e-126">**Beschrijving**: de beschrijving van de relatie.</span><span class="sxs-lookup"><span data-stu-id="9088e-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="9088e-127">**Bronentiteit**: selecteer de entiteit die wordt gebruikt als bron in de relatie (bijvoorbeeld WebLog).</span><span class="sxs-lookup"><span data-stu-id="9088e-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="9088e-128">**Kardinaliteit**: selecteer de kardinaliteit van de bronentiteitsrecords.</span><span class="sxs-lookup"><span data-stu-id="9088e-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="9088e-129">"Veel" betekent bijvoorbeeld dat meerdere Weblog-records gerelateerd zijn aan één WebAccount.</span><span class="sxs-lookup"><span data-stu-id="9088e-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="9088e-130">**Bronsleutelveld**: dit vertegenwoordigt het veld met de externe sleutel in de bronentiteit.</span><span class="sxs-lookup"><span data-stu-id="9088e-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="9088e-131">WebLog heeft bijvoorbeeld het veld met de externe sleutel **accountId**.</span><span class="sxs-lookup"><span data-stu-id="9088e-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="9088e-132">**Doelentiteit**: selecteer de entiteit die wordt gebruikt als doel in de relatie (bijvoorbeeld WebAccount).</span><span class="sxs-lookup"><span data-stu-id="9088e-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="9088e-133">**Doelkardinaliteit**: selecteer de kardinaliteit van de doelentiteitsrecords.</span><span class="sxs-lookup"><span data-stu-id="9088e-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="9088e-134">"Een" betekent bijvoorbeeld dat meerdere Weblog-records zijn gerelateerd aan één WebAccount.</span><span class="sxs-lookup"><span data-stu-id="9088e-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="9088e-135">**Doelsleutelveld**: dit veld vertegenwoordigt het sleutelveld van de doelentiteit.</span><span class="sxs-lookup"><span data-stu-id="9088e-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="9088e-136">WebAccount heeft bijvoorbeeld het sleutelveld **accountId**.</span><span class="sxs-lookup"><span data-stu-id="9088e-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="9088e-137">Alleen veel-op-één- en één-op-één-relaties worden ondersteund.</span><span class="sxs-lookup"><span data-stu-id="9088e-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="9088e-138">Veel-op-veel-relaties kunnen worden gemaakt met behulp van twee veel-op-één-relaties en een koppelingsentiteit (een entiteit die wordt gebruikt om de bronentiteit en de doelentiteit met elkaar te verbinden).</span><span class="sxs-lookup"><span data-stu-id="9088e-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="9088e-139">Een relatie verwijderen</span><span class="sxs-lookup"><span data-stu-id="9088e-139">Delete a relationship</span></span>

1. <span data-ttu-id="9088e-140">Ga in doelgroepinzichten naar **Gegevens** > **Relaties**.</span><span class="sxs-lookup"><span data-stu-id="9088e-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="9088e-141">Schakel selectievakjes in voor de relaties die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="9088e-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="9088e-142">Selecteer **Verwijderen** boven aan de tabel **Relaties**.</span><span class="sxs-lookup"><span data-stu-id="9088e-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="9088e-143">Bevestig de verwijdering.</span><span class="sxs-lookup"><span data-stu-id="9088e-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="9088e-144">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="9088e-144">Next step</span></span>

<span data-ttu-id="9088e-145">Systeem- en aangepaste relaties worden gebruikt om segmenten te maken op basis van meerdere gegevensbronnen die niet langer geïsoleerd zijn.</span><span class="sxs-lookup"><span data-stu-id="9088e-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="9088e-146">Zie [Segmenten](segments.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9088e-146">For more information, see [Segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]