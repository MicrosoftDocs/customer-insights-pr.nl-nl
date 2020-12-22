---
title: Bot voor Microsoft Teams
description: Zoek geharmoniseerde klantprofielen op in Microsoft Teams met behulp van een bot.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 45ea23fbefe5f1d44c3961183b76d2cc5c45355e
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405498"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="5ad52-103">Teams-bot voor Dynamics 365 Customer Insights (preview)</span><span class="sxs-lookup"><span data-stu-id="5ad52-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="5ad52-104">Maak verbinding met Microsoft Teams om een bot geharmoniseerde klantprofielen in Teams-kanalen te laten opzoeken.</span><span class="sxs-lookup"><span data-stu-id="5ad52-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5ad52-105">![Teams-bot die een klantrecord weergeeft](media/teams-bot.png "Teams-bot die een klantrecord weergeeft")</span><span class="sxs-lookup"><span data-stu-id="5ad52-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5ad52-106">Vereisten</span><span class="sxs-lookup"><span data-stu-id="5ad52-106">Prerequisites</span></span>

<span data-ttu-id="5ad52-107">Als u de bot wilt instellen en configureren, moet aan de volgende voorwaarden worden voldaan:</span><span class="sxs-lookup"><span data-stu-id="5ad52-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="5ad52-108">Er is minimaal één [gegevensbron toegevoegd](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="5ad52-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="5ad52-109">Het [harmoniseringsproces](data-unification.md) is voltooid.</span><span class="sxs-lookup"><span data-stu-id="5ad52-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="5ad52-110">Er zijn velden toegevoegd aan de [zoek- en filterindex](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="5ad52-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="5ad52-111">Customer Insights en Teams bevinden zich in dezelfde organisatie.</span><span class="sxs-lookup"><span data-stu-id="5ad52-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="5ad52-112">De bot configureren</span><span class="sxs-lookup"><span data-stu-id="5ad52-112">Configure the bot</span></span>

1. <span data-ttu-id="5ad52-113">Ga in doelgroepinzichten naar **Beheer** > **Exportbestemmingen**.</span><span class="sxs-lookup"><span data-stu-id="5ad52-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="5ad52-114">Selecteer op de tegel Microsoft Teams de optie **Instellen**.</span><span class="sxs-lookup"><span data-stu-id="5ad52-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="5ad52-115">U wordt doorgestuurd naar het gebied **Apps** in Teams.</span><span class="sxs-lookup"><span data-stu-id="5ad52-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="5ad52-116">U kunt Teams ook openen en **Apps** selecteren in de linkerbenedenhoek of dit rechtstreeks [ophalen vanuit AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).</span><span class="sxs-lookup"><span data-stu-id="5ad52-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="5ad52-117">Zoek naar **Customer Insights** en selecteer de app.</span><span class="sxs-lookup"><span data-stu-id="5ad52-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="5ad52-118">Selecteer **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="5ad52-118">Select **Add**.</span></span>
1. <span data-ttu-id="5ad52-119">Nadat u zich hebt aangemeld bij Customer Insights in Teams, ziet u een welkomstbericht en kunt u aan de slag.</span><span class="sxs-lookup"><span data-stu-id="5ad52-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="5ad52-120">Dingen die u kunt doen met de bot</span><span class="sxs-lookup"><span data-stu-id="5ad52-120">Things you can do with the bot</span></span>

<span data-ttu-id="5ad52-121">De bot biedt zoekmogelijkheden voor geharmoniseerde klantprofielen.</span><span class="sxs-lookup"><span data-stu-id="5ad52-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="5ad52-122">Voer **zoeken** in gevolgd door een naam, e-mailadres of ander veld in het geharmoniseerde klantprofiel dat is toegevoegd aan de zoek- en filterindex.</span><span class="sxs-lookup"><span data-stu-id="5ad52-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="5ad52-123">U krijgt een kaart met maximaal 15 velden uit het resulterende klantprofiel.</span><span class="sxs-lookup"><span data-stu-id="5ad52-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="5ad52-124">Meerdere overeenkomsten retourneren een lijst met resultaten waarin u een profiel kunt selecteren.</span><span class="sxs-lookup"><span data-stu-id="5ad52-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="5ad52-125">U kunt de zoekterm tussen dubbele aanhalingstekens plaatsen om een exacte overeenkomst op te zoeken.</span><span class="sxs-lookup"><span data-stu-id="5ad52-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="5ad52-126">Als uw organisatie meerdere Customer Insights-omgevingen in dezelfde organisatie heeft, kunt u **switchinstance** invoeren om te kiezen met welke omgeving u de bot wilt verbinden.</span><span class="sxs-lookup"><span data-stu-id="5ad52-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="5ad52-127">VOer **help** in om een lijst met beschikbare opdrachten voor de bot te bekijken.</span><span class="sxs-lookup"><span data-stu-id="5ad52-127">Enter **help** to see a list of available commands for the bot.</span></span>  
