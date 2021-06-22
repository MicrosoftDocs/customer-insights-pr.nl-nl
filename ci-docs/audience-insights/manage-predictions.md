---
title: Gedeelde taken voor voorspellingsscenario's
description: Leer hoe u voorspellingen beheert, problemen oplost en verfijnt.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b935be08199f20e83bceb3317985b0e1dc120016
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095700"
---
# <a name="manage-predictions"></a><span data-ttu-id="77101-103">Voorspellingen beheren</span><span class="sxs-lookup"><span data-stu-id="77101-103">Manage predictions</span></span>

<span data-ttu-id="77101-104">In dit artikel worden enkele taken besproken die de meeste voorspellingsscenario's gemeenschappelijk hebben.</span><span class="sxs-lookup"><span data-stu-id="77101-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="77101-105">Probleem van een mislukte voorspelling oplossen</span><span class="sxs-lookup"><span data-stu-id="77101-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="77101-106">Ga naar **Intelligence** > **Voorspellingen** en selecteer het tabblad **Mijn voorspellingen**.</span><span class="sxs-lookup"><span data-stu-id="77101-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="77101-107">Selecteer het verticale beletselteken naast de voorspelling waarvoor u foutenlogbestanden wilt bekijken.</span><span class="sxs-lookup"><span data-stu-id="77101-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="77101-108">Selecteer **Logbestanden**.</span><span class="sxs-lookup"><span data-stu-id="77101-108">Select **Logs**.</span></span>

1. <span data-ttu-id="77101-109">Bekijk alle fouten.</span><span class="sxs-lookup"><span data-stu-id="77101-109">Review all the errors.</span></span> <span data-ttu-id="77101-110">Er zijn verschillende typen fouten die kunnen optreden en deze beschrijven welke toestand de fout heeft veroorzaakt.</span><span class="sxs-lookup"><span data-stu-id="77101-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="77101-111">Een fout waarbij er niet genoeg gegevens beschikbaar zijn om een nauwkeurige voorspelling te maken wordt bijvoorbeeld doorgaans hersteld door extra gegevens in Customer Insights te laden.</span><span class="sxs-lookup"><span data-stu-id="77101-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="77101-112">Bruikbaarheidsrapport voor gegevensinvoer</span><span class="sxs-lookup"><span data-stu-id="77101-112">Input data usability report</span></span>

<span data-ttu-id="77101-113">Het bruikbaarheidsrapport voor invoergegevens biedt een geconsolideerd overzicht van de fouten en waarschuwingen die uw kant-en-klare voorspellingen mogelijk genereren.</span><span class="sxs-lookup"><span data-stu-id="77101-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="77101-114">Het geeft ook aanbevelingen om de prestaties van het model te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="77101-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="77101-115">Het rapport is beschikbaar nadat een model zijn trainingsproces heeft voltooid.</span><span class="sxs-lookup"><span data-stu-id="77101-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="77101-116">Het wordt voor elk model afzonderlijk gemaakt, ongeacht of dit met succes is voltooid of niet.</span><span class="sxs-lookup"><span data-stu-id="77101-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

> [!NOTE]
> <span data-ttu-id="77101-117">Momenteel werkt deze functie alleen voor het model voor transactieverloop.</span><span class="sxs-lookup"><span data-stu-id="77101-117">Currently, this feature only works for the Transaction Churn model.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="77101-118">Het bruikbaarheidsrapport voor gegevensinvoer bekijken</span><span class="sxs-lookup"><span data-stu-id="77101-118">View the input data usability report</span></span>

<span data-ttu-id="77101-119">Nadat een kant-en-klaar model de trainingsstap heeft voltooid, bekijkt u het rapport:</span><span class="sxs-lookup"><span data-stu-id="77101-119">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="77101-120">Selecteer de weglatingstekens naast de modelnaam en kies **Bruikbaarheidsrapport voor gegevensinvoer**.</span><span class="sxs-lookup"><span data-stu-id="77101-120">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="77101-121">Selecteer de status van een model en selecteer **Bruikbaarheidsrapport voor gegevensinvoer bekijken** in het zijpaneel.</span><span class="sxs-lookup"><span data-stu-id="77101-121">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="77101-122">Selecteer een van de modellen in de lijst en selecteer **Bruikbaarheidsrapport voor gegevensinvoer** op de opdrachtbalk.</span><span class="sxs-lookup"><span data-stu-id="77101-122">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="77101-123">Open de pagina met modelresultaten en selecteer **Bruikbaarheidsrapport voor gegevensinvoer** op de opdrachtbalk.</span><span class="sxs-lookup"><span data-stu-id="77101-123">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="77101-124">Informatie in het bruikbaarheidsrapport voor gegevensinvoer</span><span class="sxs-lookup"><span data-stu-id="77101-124">Information in the input data usability report</span></span>

<span data-ttu-id="77101-125">De volgende kolommen in het rapport bevatten nuttige informatie om de gegevens voor het model te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="77101-125">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Voorbeeld van een bruikbaarheidsrapport voor invoergegevens met een tabel met fouten, waarschuwingen en aanbevelingen.":::

- <span data-ttu-id="77101-127">Naam: beschrijvende naam van de fout, waarschuwing of aanbeveling.</span><span class="sxs-lookup"><span data-stu-id="77101-127">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="77101-128">Stap: modelfase, trainen of scoren, waarnaar de informatie verwijst.</span><span class="sxs-lookup"><span data-stu-id="77101-128">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="77101-129">Status: ernst van de informatie (fout, waarschuwing, aanbeveling).</span><span class="sxs-lookup"><span data-stu-id="77101-129">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="77101-130">Kolomnaam: kolom in een entiteit die moet worden gewijzigd om de modelprestaties te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="77101-130">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="77101-131">Entiteitsnaam: naam van de entiteit die moet worden gewijzigd om de modelprestaties te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="77101-131">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="77101-132">Details: details van de fout, waarschuwing of aanbeveling.</span><span class="sxs-lookup"><span data-stu-id="77101-132">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="77101-133">Een voorspelling vernieuwen</span><span class="sxs-lookup"><span data-stu-id="77101-133">Refresh a prediction</span></span>

<span data-ttu-id="77101-134">Voorspellingen worden automatisch vernieuwd volgens hetzelfde [schema van gegevensvernieuwingen](system.md#schedule-tab) zoals geconfigureerd in de instellingen.</span><span class="sxs-lookup"><span data-stu-id="77101-134">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="77101-135">U kunt ze ook handmatig vernieuwen.</span><span class="sxs-lookup"><span data-stu-id="77101-135">You can refresh them manually too.</span></span>

1. <span data-ttu-id="77101-136">Ga naar **Intelligence** > **Voorspellingen** en selecteer het tabblad **Mijn voorspellingen**.</span><span class="sxs-lookup"><span data-stu-id="77101-136">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="77101-137">Selecteer de verticale puntjes naast de voorspelling die u wilt vernieuwen.</span><span class="sxs-lookup"><span data-stu-id="77101-137">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="77101-138">Selecteer **Vernieuwen**.</span><span class="sxs-lookup"><span data-stu-id="77101-138">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="77101-139">Een voorspelling verwijderen</span><span class="sxs-lookup"><span data-stu-id="77101-139">Delete a prediction</span></span>

<span data-ttu-id="77101-140">Als u een voorspelling verwijdert, wordt ook de uitvoerentiteit ervan verwijderd.</span><span class="sxs-lookup"><span data-stu-id="77101-140">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="77101-141">Ga naar **Intelligence** > **Voorspellingen** en selecteer het tabblad **Mijn voorspellingen**.</span><span class="sxs-lookup"><span data-stu-id="77101-141">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="77101-142">Selecteer de verticale puntjes naast de voorspelling die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="77101-142">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="77101-143">Selecteer **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="77101-143">Select **Delete**.</span></span>
