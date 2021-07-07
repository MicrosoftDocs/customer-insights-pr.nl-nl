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
ms.openlocfilehash: dccb8dcca8f65f64973e46fed9d83034d58282e2
ms.sourcegitcommit: bcc47d15d4f0eacf008e4dbc09baac7f062b3ca8
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2021
ms.locfileid: "6315872"
---
# <a name="manage-predictions"></a><span data-ttu-id="abb9d-103">Voorspellingen beheren</span><span class="sxs-lookup"><span data-stu-id="abb9d-103">Manage predictions</span></span>

<span data-ttu-id="abb9d-104">In dit artikel worden enkele taken besproken die de meeste voorspellingsscenario's gemeenschappelijk hebben.</span><span class="sxs-lookup"><span data-stu-id="abb9d-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="abb9d-105">Probleem van een mislukte voorspelling oplossen</span><span class="sxs-lookup"><span data-stu-id="abb9d-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="abb9d-106">Ga naar **Intelligence** > **Voorspellingen** en selecteer het tabblad **Mijn voorspellingen**.</span><span class="sxs-lookup"><span data-stu-id="abb9d-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="abb9d-107">Selecteer het verticale beletselteken naast de voorspelling waarvoor u foutenlogbestanden wilt bekijken.</span><span class="sxs-lookup"><span data-stu-id="abb9d-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="abb9d-108">Selecteer **Logbestanden**.</span><span class="sxs-lookup"><span data-stu-id="abb9d-108">Select **Logs**.</span></span>

1. <span data-ttu-id="abb9d-109">Bekijk alle fouten.</span><span class="sxs-lookup"><span data-stu-id="abb9d-109">Review all the errors.</span></span> <span data-ttu-id="abb9d-110">Er zijn verschillende typen fouten die kunnen optreden en deze beschrijven welke toestand de fout heeft veroorzaakt.</span><span class="sxs-lookup"><span data-stu-id="abb9d-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="abb9d-111">Een fout waarbij er niet genoeg gegevens beschikbaar zijn om een nauwkeurige voorspelling te maken wordt bijvoorbeeld doorgaans hersteld door extra gegevens in Customer Insights te laden.</span><span class="sxs-lookup"><span data-stu-id="abb9d-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="abb9d-112">Bruikbaarheidsrapport voor gegevensinvoer</span><span class="sxs-lookup"><span data-stu-id="abb9d-112">Input data usability report</span></span>

<span data-ttu-id="abb9d-113">Het bruikbaarheidsrapport voor invoergegevens biedt een geconsolideerd overzicht van de fouten en waarschuwingen die uw kant-en-klare voorspellingen mogelijk genereren.</span><span class="sxs-lookup"><span data-stu-id="abb9d-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="abb9d-114">Het geeft ook aanbevelingen om de prestaties van het model te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="abb9d-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="abb9d-115">Het rapport is beschikbaar nadat een model zijn trainingsproces heeft voltooid.</span><span class="sxs-lookup"><span data-stu-id="abb9d-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="abb9d-116">Het wordt voor elk model afzonderlijk gemaakt, ongeacht of dit met succes is voltooid of niet.</span><span class="sxs-lookup"><span data-stu-id="abb9d-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="abb9d-117">Het bruikbaarheidsrapport voor gegevensinvoer bekijken</span><span class="sxs-lookup"><span data-stu-id="abb9d-117">View the input data usability report</span></span>

<span data-ttu-id="abb9d-118">Nadat een kant-en-klaar model de trainingsstap heeft voltooid, bekijkt u het rapport:</span><span class="sxs-lookup"><span data-stu-id="abb9d-118">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="abb9d-119">Selecteer de weglatingstekens naast de modelnaam en kies **Bruikbaarheidsrapport voor gegevensinvoer**.</span><span class="sxs-lookup"><span data-stu-id="abb9d-119">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="abb9d-120">Selecteer de status van een model en selecteer **Bruikbaarheidsrapport voor gegevensinvoer bekijken** in het zijpaneel.</span><span class="sxs-lookup"><span data-stu-id="abb9d-120">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="abb9d-121">Selecteer een van de modellen in de lijst en selecteer **Bruikbaarheidsrapport voor gegevensinvoer** op de opdrachtbalk.</span><span class="sxs-lookup"><span data-stu-id="abb9d-121">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="abb9d-122">Open de pagina met modelresultaten en selecteer **Bruikbaarheidsrapport voor gegevensinvoer** op de opdrachtbalk.</span><span class="sxs-lookup"><span data-stu-id="abb9d-122">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="abb9d-123">Informatie in het bruikbaarheidsrapport voor gegevensinvoer</span><span class="sxs-lookup"><span data-stu-id="abb9d-123">Information in the input data usability report</span></span>

<span data-ttu-id="abb9d-124">De volgende kolommen in het rapport bevatten nuttige informatie om de gegevens voor het model te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="abb9d-124">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Voorbeeld van een bruikbaarheidsrapport voor invoergegevens met een tabel met fouten, waarschuwingen en aanbevelingen.":::

- <span data-ttu-id="abb9d-126">Naam: beschrijvende naam van de fout, waarschuwing of aanbeveling.</span><span class="sxs-lookup"><span data-stu-id="abb9d-126">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="abb9d-127">Stap: modelfase, trainen of scoren, waarnaar de informatie verwijst.</span><span class="sxs-lookup"><span data-stu-id="abb9d-127">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="abb9d-128">Status: ernst van de informatie (fout, waarschuwing, aanbeveling).</span><span class="sxs-lookup"><span data-stu-id="abb9d-128">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="abb9d-129">Kolomnaam: kolom in een entiteit die moet worden gewijzigd om de modelprestaties te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="abb9d-129">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="abb9d-130">Entiteitsnaam: naam van de entiteit die moet worden gewijzigd om de modelprestaties te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="abb9d-130">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="abb9d-131">Details: details van de fout, waarschuwing of aanbeveling.</span><span class="sxs-lookup"><span data-stu-id="abb9d-131">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="abb9d-132">Een voorspelling vernieuwen</span><span class="sxs-lookup"><span data-stu-id="abb9d-132">Refresh a prediction</span></span>

<span data-ttu-id="abb9d-133">Voorspellingen worden automatisch vernieuwd volgens hetzelfde [schema van gegevensvernieuwingen](system.md#schedule-tab) zoals geconfigureerd in de instellingen.</span><span class="sxs-lookup"><span data-stu-id="abb9d-133">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="abb9d-134">U kunt ze ook handmatig vernieuwen.</span><span class="sxs-lookup"><span data-stu-id="abb9d-134">You can refresh them manually too.</span></span>

1. <span data-ttu-id="abb9d-135">Ga naar **Intelligence** > **Voorspellingen** en selecteer het tabblad **Mijn voorspellingen**.</span><span class="sxs-lookup"><span data-stu-id="abb9d-135">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="abb9d-136">Selecteer de verticale puntjes naast de voorspelling die u wilt vernieuwen.</span><span class="sxs-lookup"><span data-stu-id="abb9d-136">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="abb9d-137">Selecteer **Vernieuwen**.</span><span class="sxs-lookup"><span data-stu-id="abb9d-137">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="abb9d-138">Een voorspelling verwijderen</span><span class="sxs-lookup"><span data-stu-id="abb9d-138">Delete a prediction</span></span>

<span data-ttu-id="abb9d-139">Als u een voorspelling verwijdert, wordt ook de uitvoerentiteit ervan verwijderd.</span><span class="sxs-lookup"><span data-stu-id="abb9d-139">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="abb9d-140">Ga naar **Intelligence** > **Voorspellingen** en selecteer het tabblad **Mijn voorspellingen**.</span><span class="sxs-lookup"><span data-stu-id="abb9d-140">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="abb9d-141">Selecteer de verticale puntjes naast de voorspelling die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="abb9d-141">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="abb9d-142">Selecteer **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="abb9d-142">Select **Delete**.</span></span>
