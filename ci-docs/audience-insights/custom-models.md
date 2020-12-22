---
title: Aangepaste Machine Learning-modellen | Microsoft Docs
description: Werk met aangepaste modellen van Azure Machine Learning in Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668897"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="151a5-103">Aangepaste Machine Learning-modellen</span><span class="sxs-lookup"><span data-stu-id="151a5-103">Custom machine learning models</span></span>

<span data-ttu-id="151a5-104">Met **Informatie** > **Aangepaste modellen** kunt u werkstromen beheren op basis van Azure Machine Learning-modellen.</span><span class="sxs-lookup"><span data-stu-id="151a5-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="151a5-105">Werkstromen helpen u bij het kiezen van de gegevens waaruit u inzichten wilt genereren, en helpen u de resultaten toe te wijzen aan uw geharmoniseerde klantgegevens.</span><span class="sxs-lookup"><span data-stu-id="151a5-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="151a5-106">Zie voor meer informatie over het bouwen van aangepaste ML-modellen [Azure Machine Learning-modellen gebruiken](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="151a5-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="151a5-107">Verantwoordelijke AI</span><span class="sxs-lookup"><span data-stu-id="151a5-107">Responsible AI</span></span>

<span data-ttu-id="151a5-108">Voorspellingen bieden mogelijkheden om betere klantervaringen te creëren, zakelijke mogelijkheden en omzetstromen te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="151a5-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="151a5-109">We raden u ten zeerste aan de waarde van uw voorspelling af te wegen tegen de impact die deze heeft en vooroordelen die op een ethische manier kunnen worden geïntroduceerd.</span><span class="sxs-lookup"><span data-stu-id="151a5-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="151a5-110">Lees meer over hoe Microsoft [omgaat met Verantwoordelijke AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="151a5-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="151a5-111">U kunt ook meer informatie vinden over [technieken en processen voor verantwoordelijke Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specifiek voor Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="151a5-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="151a5-112">Vereisten</span><span class="sxs-lookup"><span data-stu-id="151a5-112">Prerequisites</span></span>

- <span data-ttu-id="151a5-113">Momenteel ondersteunt deze functie webservices die zijn gepubliceerd via [Machine Learning Studio (klassiek)](https://studio.azureml.net) en [Azure Machine Learning batch-pijplijnen](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="151a5-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="151a5-114">U hebt een Azure Data Lake Gen2-opslagaccount nodig dat is gekoppeld aan uw Azure Studio-exemplaar om deze functie te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="151a5-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="151a5-115">Zie voor meer informatie [Een Azure Data Lake Storage Gen2-opslagaccount maken](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="151a5-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="151a5-116">Een nieuwe werkstroom toevoegen</span><span class="sxs-lookup"><span data-stu-id="151a5-116">Add a new workflow</span></span>

1. <span data-ttu-id="151a5-117">Ga naar **Informatie** > **Aangepaste modellen** en selecteer **Nieuwe werkstroom**.</span><span class="sxs-lookup"><span data-stu-id="151a5-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="151a5-118">Geef uw aangepaste model een herkenbare naam in het veld **Naam**.</span><span class="sxs-lookup"><span data-stu-id="151a5-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="151a5-119">![Schermafbeelding van het deelvenster Nieuwe werkstroom](media/new-workflowv2.png "Schermafbeelding van het deelvenster Nieuwe werkstroom")</span><span class="sxs-lookup"><span data-stu-id="151a5-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="151a5-120">Selecteer de organisatie die de webservice bevat in **Tenant die uw webservice bevat**.</span><span class="sxs-lookup"><span data-stu-id="151a5-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="151a5-121">Selecteer, als uw Azure Machine Learning-abonnement zich in een andere tenant bevindt dan Customer Insights, **Aanmelden** met uw referenties voor de geselecteerde organisatie.</span><span class="sxs-lookup"><span data-stu-id="151a5-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="151a5-122">Selecteer de **Werkruimten** die zijn gekoppeld aan uw webservice.</span><span class="sxs-lookup"><span data-stu-id="151a5-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="151a5-123">Er worden twee secties vermeld, een voor Azure Machine Learning v1 (Machine Learning Studio (klassiek)) en Azure Machine Learning v2 (Azure Machine Learning).</span><span class="sxs-lookup"><span data-stu-id="151a5-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="151a5-124">Als u niet zeker weet welke werkruimte de juiste is voor uw Machine Learning Studio-webservice (klassiek), selecteert u **Willekeurig**.</span><span class="sxs-lookup"><span data-stu-id="151a5-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="151a5-125">Kies de Machine Learning Studio-webservice (klassiek) of Azure Machine Learning-pijplijn in de vervolgkeuzelijst **Webservice met uw model**.</span><span class="sxs-lookup"><span data-stu-id="151a5-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="151a5-126">Selecteer vervolgens **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="151a5-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="151a5-127">Meer informatie over [een webservice publiceren in Machine Learning Studio (klassiek)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="151a5-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="151a5-128">Meer informatie over [een pijplijn publiceren in Azure Machine Learning met de designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) of [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="151a5-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> 
     > [!NOTE]
     > <span data-ttu-id="151a5-129">Uw pijplijn moet worden gepubliceerd onder een [pijplijn-eindpunt](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="151a5-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="151a5-130">Voor elke **Invoer voor webservice** selecteert u de overeenkomende **Entiteit** in doelgroepinzichten en tot slot selecteert u **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="151a5-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="151a5-131">![Een werkstroom configureren](media/intelligence-screen2-updated.png "Een werkstroom configureren")</span><span class="sxs-lookup"><span data-stu-id="151a5-131">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="151a5-132">Stel in de stap **Modeluitvoerparameters** de volgende eigenschappen in:</span><span class="sxs-lookup"><span data-stu-id="151a5-132">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="151a5-133">Machine Learning Studio (klassiek)</span><span class="sxs-lookup"><span data-stu-id="151a5-133">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="151a5-134">Voer de **Entiteitsnaam** van de uitvoer in waarnaar u de uitvoerresultaten van de webservice wilt laten stromen.</span><span class="sxs-lookup"><span data-stu-id="151a5-134">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="151a5-135">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="151a5-135">Azure Machine Learning</span></span>
      1. <span data-ttu-id="151a5-136">Voer de **Entiteitsnaam** van de uitvoer in waarnaar u de uitvoerresultaten van de pijplijn wilt laten stromen.</span><span class="sxs-lookup"><span data-stu-id="151a5-136">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="151a5-137">Selecteer in de vervolgkeuzelijst de **Parameternaam van de uitvoergegevensopslag** van uw batchpijplijn.</span><span class="sxs-lookup"><span data-stu-id="151a5-137">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="151a5-138">Selecteer in de vervolgkeuzelijst de **Parameternaam van het uitvoerpad** van uw batchpijplijn.</span><span class="sxs-lookup"><span data-stu-id="151a5-138">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="151a5-139">![Deelvenster Parameter voor modeluitvoer](media/intelligence-screen3-outputparameters.png "Deelvenster Parameter voor modeluitvoer")</span><span class="sxs-lookup"><span data-stu-id="151a5-139">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="151a5-140">Selecteer het overeenkomende kenmerk in de vervolgkeuzelijst **Klant-id in resultaten** die klanten identificeert en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="151a5-140">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="151a5-141">![Resultaten relateren aan het deelvenster Klantgegevens](media/intelligence-screen4-relatetocustomer.png "Resultaten relateren aan het deelvenster Klantgegevens")</span><span class="sxs-lookup"><span data-stu-id="151a5-141">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="151a5-142">U krijgt het scherm **Werkstroom opgeslagen** te zien met details over de werkstroom.</span><span class="sxs-lookup"><span data-stu-id="151a5-142">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="151a5-143">Als u een werkstroom hebt geconfigureerd voor een Azure Machine Learning-pijplijn, worden doelgroepinzichten gekoppeld aan de werkruimte die de pijplijn bevat.</span><span class="sxs-lookup"><span data-stu-id="151a5-143">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="151a5-144">Doelgroepinzichten krijgen een rol als **inzender** in de Azure-werkruimte.</span><span class="sxs-lookup"><span data-stu-id="151a5-144">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="151a5-145">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="151a5-145">Select **Done**.</span></span>

1. <span data-ttu-id="151a5-146">U kunt de workflow nu uitvoeren vanuit de pagina **Aangepaste modellen**.</span><span class="sxs-lookup"><span data-stu-id="151a5-146">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="151a5-147">Een werkstroom bewerken</span><span class="sxs-lookup"><span data-stu-id="151a5-147">Edit a workflow</span></span>

1. <span data-ttu-id="151a5-148">Selecteer op de pagina **Aangepaste modellen** de verticale ellips in de kolom **Acties** naast een werkstroom die u eerder hebt gemaakt en selecteer vervolgens **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="151a5-148">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="151a5-149">U kunt de herkenbare naam van uw werkstroom bijwerken in het veld **Weergavenaam**, maar u kunt de geconfigureerde webservice of pijplijn niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="151a5-149">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="151a5-150">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="151a5-150">Select **Next**.</span></span>

1. <span data-ttu-id="151a5-151">Voor elke **Invoer voor webservice** kunt u de overeenkomende **Entiteit** in doelgroepinzichten bijwerken.</span><span class="sxs-lookup"><span data-stu-id="151a5-151">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="151a5-152">Selecteer vervolgens **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="151a5-152">Then, select **Next**.</span></span>

1. <span data-ttu-id="151a5-153">Stel in de stap **Modeluitvoerparameters** de volgende eigenschappen in:</span><span class="sxs-lookup"><span data-stu-id="151a5-153">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="151a5-154">Machine Learning Studio (klassiek)</span><span class="sxs-lookup"><span data-stu-id="151a5-154">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="151a5-155">Voer de **Entiteitsnaam** van de uitvoer in waarnaar u de uitvoerresultaten van de webservice wilt laten stromen.</span><span class="sxs-lookup"><span data-stu-id="151a5-155">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="151a5-156">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="151a5-156">Azure Machine Learning</span></span>
      1. <span data-ttu-id="151a5-157">Voer de **Entiteitsnaam** van de uitvoer in waarnaar u de uitvoerresultaten van de pijplijn wilt laten stromen.</span><span class="sxs-lookup"><span data-stu-id="151a5-157">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="151a5-158">Selecteer de **Parameternaam voor uitvoergegevensopslag** voor uw testpijplijn.</span><span class="sxs-lookup"><span data-stu-id="151a5-158">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="151a5-159">Selecteer de **Parameternaam voor uitvoerpad** voor uw testpijplijn.</span><span class="sxs-lookup"><span data-stu-id="151a5-159">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="151a5-160">Selecteer het overeenkomende kenmerk in de vervolgkeuzelijst **Klant-id in resultaten** die klanten identificeert en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="151a5-160">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="151a5-161">U moet een kenmerk kiezen uit de inferentie-uitvoer met waarden die vergelijkbaar zijn met de kolom Klant-id van de entiteit Klant.</span><span class="sxs-lookup"><span data-stu-id="151a5-161">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="151a5-162">Als u deze kolom in uw gegevensset hebt, kiest u een kenmerk dat de rij uniek identificeert.</span><span class="sxs-lookup"><span data-stu-id="151a5-162">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="151a5-163">Een werkstroom uitvoeren</span><span class="sxs-lookup"><span data-stu-id="151a5-163">Run a workflow</span></span>

1. <span data-ttu-id="151a5-164">Selecteer op de pagina **Aangepaste modellen** de verticale ellips in de kolom **Acties** naast een werkstroom die u eerder hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="151a5-164">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="151a5-165">Selecteer **Uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="151a5-165">Select **Run**.</span></span>

<span data-ttu-id="151a5-166">Uw werkstroom wordt ook automatisch uitgevoerd bij elke geplande vernieuwing.</span><span class="sxs-lookup"><span data-stu-id="151a5-166">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="151a5-167">Lees meer over [Geplande vernieuwingen instellen](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="151a5-167">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="151a5-168">Een werkstroom verwijderen</span><span class="sxs-lookup"><span data-stu-id="151a5-168">Delete a workflow</span></span>

1. <span data-ttu-id="151a5-169">Selecteer op de pagina **Aangepaste modellen** de verticale ellips in de kolom **Acties** naast een werkstroom die u eerder hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="151a5-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="151a5-170">Selecteer **Verwijderen** en bevestig de verwijdering.</span><span class="sxs-lookup"><span data-stu-id="151a5-170">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="151a5-171">Uw werkstroom wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="151a5-171">Your workflow will be deleted.</span></span> <span data-ttu-id="151a5-172">De [entiteit](entities.md) die is gemaakt toen u de werkstroom maakte, blijft bestaan en kan worden bekeken via de pagina **Entiteiten**.</span><span class="sxs-lookup"><span data-stu-id="151a5-172">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>
