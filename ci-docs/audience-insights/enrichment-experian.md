---
title: Verrijking met de verrijking door derden van Experian
description: Algemene informatie over de verrijking door derden van Experian.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4d4723e8f793ee857c4f5204a42be8338c71d4c3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597781"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="38b73-103">Klantprofielen verrijken met demografische gegevens van Experian (preview)</span><span class="sxs-lookup"><span data-stu-id="38b73-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="38b73-104">Experian is een wereldleider in kredietrapportage en marketingdiensten voor consumenten en bedrijven.</span><span class="sxs-lookup"><span data-stu-id="38b73-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="38b73-105">Met de Experian-services voor gegevensverrijking kunt u een dieper inzicht in uw klanten opbouwen door uw klantprofielen te verrijken met demografische gegevens zoals de grootte van het huishouden, het inkomen en meer.</span><span class="sxs-lookup"><span data-stu-id="38b73-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="38b73-106">Vereisten</span><span class="sxs-lookup"><span data-stu-id="38b73-106">Prerequisites</span></span>

<span data-ttu-id="38b73-107">Als u Experian wilt configureren, moet aan de volgende vereisten worden voldaan:</span><span class="sxs-lookup"><span data-stu-id="38b73-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="38b73-108">U hebt een actief Experian-abonnement.</span><span class="sxs-lookup"><span data-stu-id="38b73-108">You have an active Experian subscription.</span></span> <span data-ttu-id="38b73-109">Als u een abonnement wilt nemen, [neemt u rechtstreeks contact op met Experian](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="38b73-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="38b73-110">[Meer informatie over gegevensverrijking met Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="38b73-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="38b73-111">U hebt de gebruikers-id, partij-id en modelnummer voor uw voor SSH geschikte ST-account (Secure Transport) dat Experian voor u heeft gemaakt.</span><span class="sxs-lookup"><span data-stu-id="38b73-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="38b73-112">U hebt [Beheerder](permissions.md#administrator) machtigingen in doelgroepinzichten.</span><span class="sxs-lookup"><span data-stu-id="38b73-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="38b73-113">Configuratie</span><span class="sxs-lookup"><span data-stu-id="38b73-113">Configuration</span></span>

1. <span data-ttu-id="38b73-114">Ga naar **Gegevens** > **Verrijking** en selecteer het tabblad **Detecteren**.</span><span class="sxs-lookup"><span data-stu-id="38b73-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="38b73-115">Selecteer **Mijn gegevens verrijken** op de Experian-tegel.</span><span class="sxs-lookup"><span data-stu-id="38b73-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="38b73-116">![Experian-tegel](media/experian-tile.png "Experian-tegel")</span><span class="sxs-lookup"><span data-stu-id="38b73-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="38b73-117">Selecteer **Aan de slag** en voer de gebruikers-id, partij-id en modelnummer voor uw Experian Secure Transport-account in.</span><span class="sxs-lookup"><span data-stu-id="38b73-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="38b73-118">Bekijk en geef toestemming voor **Gegevensprivacy en naleving** door het selectievakje **Ik ga akkoord** in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="38b73-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="38b73-119">Bevestig alle invoer door **Toepassen** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="38b73-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="38b73-120">Uw velden toewijzen</span><span class="sxs-lookup"><span data-stu-id="38b73-120">Map your fields</span></span>

1.  <span data-ttu-id="38b73-121">Selecteer **Gegevens toevoegen** en kies de **Klantgegevensset** die u wilt verrijken met demografische gegevens van Experian.</span><span class="sxs-lookup"><span data-stu-id="38b73-121">Select **Add data** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="38b73-122">U kunt de entiteit **Klant** selecteren om al uw klantprofielen te verrijken of een segmententiteit selecteren om alleen klantprofielen in dat segment te verrijken.</span><span class="sxs-lookup"><span data-stu-id="38b73-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="38b73-123">Selecteer uw belangrijkste id's uit **Naam en adres**​, **E-mail** of **Telefoon** om naar Experian te sturen voor identiteitsresolutie.</span><span class="sxs-lookup"><span data-stu-id="38b73-123">Select your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="38b73-124">Als u meer belangrijke id-kenmerken naar Experian verzendt, levert dat waarschijnlijk een hogere overeenkomst op.</span><span class="sxs-lookup"><span data-stu-id="38b73-124">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="38b73-125">Selecteer **Volgende** en wijs de overeenkomstige kenmerken van uw uniforme klantentiteit toe voor de geselecteerde id-velden.</span><span class="sxs-lookup"><span data-stu-id="38b73-125">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="38b73-126">Selecteer **Kenmerk toevoegen** om eventuele aanvullende kenmerken die u naar Experian wilt verzenden, toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="38b73-126">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="38b73-127">Selecteer **Opslaan** om de veldtoewijzing te voltooien.</span><span class="sxs-lookup"><span data-stu-id="38b73-127">Select **Save** to complete the field mapping.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="38b73-128">![Experian-veldtoewijzing](media/experian-field-mapping.png "Experian-veldtoewijzing")</span><span class="sxs-lookup"><span data-stu-id="38b73-128">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="38b73-129">Verrijkingsresultaten</span><span class="sxs-lookup"><span data-stu-id="38b73-129">Enrichment results</span></span>

<span data-ttu-id="38b73-130">Selecteer **Uitvoeren** vanaf de opdrachtbalk om het verrijkingsproces te starten.</span><span class="sxs-lookup"><span data-stu-id="38b73-130">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="38b73-131">U kunt de verrijking ook automatisch laten uitvoeren als onderdeel van een [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="38b73-131">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="38b73-132">De verwerkingstijd is afhankelijk van de omvang van uw klantgegevens en de verrijkingsprocessen die Experian voor uw account heeft ingesteld.</span><span class="sxs-lookup"><span data-stu-id="38b73-132">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="38b73-133">Nadat het verrijkingsproces is voltooid, kunt u de nieuwe verrijkte klantprofielgegevens bekijken onder **Mijn verrijkingen**.</span><span class="sxs-lookup"><span data-stu-id="38b73-133">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="38b73-134">Ook vindt u daar het tijdstip van de laatste update en het aantal verrijkte profielen.</span><span class="sxs-lookup"><span data-stu-id="38b73-134">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="38b73-135">U kunt een gedetailleerd overzicht van elk verrijkt profiel openen door **Verrijkte gegevens weergeven** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="38b73-135">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="38b73-136">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="38b73-136">Next steps</span></span>

<span data-ttu-id="38b73-137">Bouw voort op uw verrijkte klantgegevens.</span><span class="sxs-lookup"><span data-stu-id="38b73-137">Build on top of your enriched customer data.</span></span> <span data-ttu-id="38b73-138">Maak [segmenten](segments.md), [metingen](measures.md) en [exporteer de gegevens](export-destinations.md) om uw klanten gepersonaliseerde ervaringen te bieden.</span><span class="sxs-lookup"><span data-stu-id="38b73-138">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="38b73-139">Gegevensprivacy en naleving</span><span class="sxs-lookup"><span data-stu-id="38b73-139">Data privacy and compliance</span></span>

<span data-ttu-id="38b73-140">Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar Experian te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens.</span><span class="sxs-lookup"><span data-stu-id="38b73-140">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="38b73-141">Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat Experian voldoet aan uw privacy- of beveiligingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="38b73-141">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="38b73-142">Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="38b73-142">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="38b73-143">Uw Dynamics 365 Customer Insights-beheerder kan deze verrijking op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.</span><span class="sxs-lookup"><span data-stu-id="38b73-143">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]