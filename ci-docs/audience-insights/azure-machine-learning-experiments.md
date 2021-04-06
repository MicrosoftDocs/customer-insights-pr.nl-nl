---
title: Azure Machine Learning-experimenten
description: Azure Machine Learning-modellen gebruiken in Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: edd2cf488b52cef87b09b90336e48fdc7f470a68
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597413"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="e1804-103">Azure Machine Learning-modellen gebruiken</span><span class="sxs-lookup"><span data-stu-id="e1804-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="e1804-104">De geharmoniseerde gegevens in Dynamics 365 Customer Insights zijn een bron voor het bouwen van Machine Learning-modellen die aanvullende zakelijke inzichten kunnen genereren.</span><span class="sxs-lookup"><span data-stu-id="e1804-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="e1804-105">Customer Insights kan worden geïntegreerd met Machine Learning Studio (klassiek) en Azure Machine Learning om uw eigen aangepaste modellen te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e1804-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="e1804-106">Lees [Experimenten met Machine Learning Studio (klassiek)](machine-learning-studio-experiments.md) voor voorbeelden van experimenten die zijn gebouwd op Machine Learning Studio (klassiek).</span><span class="sxs-lookup"><span data-stu-id="e1804-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="e1804-107">Vereisten</span><span class="sxs-lookup"><span data-stu-id="e1804-107">Prerequisites</span></span>

- <span data-ttu-id="e1804-108">Toegang tot Customer Insights</span><span class="sxs-lookup"><span data-stu-id="e1804-108">Access to Customer Insights</span></span>
- <span data-ttu-id="e1804-109">Actief Azure Enterprise-abonnement</span><span class="sxs-lookup"><span data-stu-id="e1804-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="e1804-110">Geharmoniseerde klantprofielen</span><span class="sxs-lookup"><span data-stu-id="e1804-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="e1804-111">[Entiteit exporteren naar Azure Blob Storage](export-azure-blob-storage.md) geconfigureerd</span><span class="sxs-lookup"><span data-stu-id="e1804-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="e1804-112">Azure Machine Learning-werkruimte instellen</span><span class="sxs-lookup"><span data-stu-id="e1804-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="e1804-113">Zie [een Azure Machine Learning-werkruimte maken](/azure/machine-learning/concept-workspace#-create-a-workspace) voor verschillende opties om de werkruimte te maken.</span><span class="sxs-lookup"><span data-stu-id="e1804-113">See [create a Azure Machine Learning workspace](/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="e1804-114">Voor de beste prestaties maakt u de werkruimte in een Azure-regio die geografisch het dichtst bij uw Customer Insights-omgeving ligt.</span><span class="sxs-lookup"><span data-stu-id="e1804-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="e1804-115">Toegang tot uw werkruimte via [Azure Machine Learning Studio](https://ml.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="e1804-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="e1804-116">Er zijn meerdere [manieren om te communiceren](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) met uw werkruimte.</span><span class="sxs-lookup"><span data-stu-id="e1804-116">There are several [ways to interact](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="e1804-117">Werken met Azure Machine Learning designer</span><span class="sxs-lookup"><span data-stu-id="e1804-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="e1804-118">Azure Machine Learning designer biedt een visueel canvas waar u gegevenssets en modules kunt slepen en neerzetten, vergelijkbaar met Machine Learning Studio (klassiek).</span><span class="sxs-lookup"><span data-stu-id="e1804-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="e1804-119">Een batchpijplijn die is gemaakt vanuit de designer, kan worden geïntegreerd in Customer Insights als deze dienovereenkomstig zijn geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="e1804-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="e1804-120">Werken met Azure Machine Learning SDK</span><span class="sxs-lookup"><span data-stu-id="e1804-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="e1804-121">Datawetenschappers en AI-ontwikkelaars gebruiken de [Azure Machine Learning SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) om Machine Learning-workflows te bouwen.</span><span class="sxs-lookup"><span data-stu-id="e1804-121">Data scientists and AI developers use the [Azure Machine Learning SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) to build machine learning workflows.</span></span> <span data-ttu-id="e1804-122">Momenteel kunnen modellen die zijn getraind met de SDK, niet rechtstreeks worden geïntegreerd met Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e1804-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="e1804-123">Een batch-inferentiepijplijn die dat model verbruikt, is vereist voor integratie met Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e1804-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="e1804-124">Batchpijplijnvereisten om te integreren met Customer Insights</span><span class="sxs-lookup"><span data-stu-id="e1804-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="e1804-125">Configuratie van gegevensset</span><span class="sxs-lookup"><span data-stu-id="e1804-125">Dataset Configuration</span></span>

<span data-ttu-id="e1804-126">U moet gegevenssets maken om entiteitsgegevens uit Customer Insights te gebruiken voor uw batch-inferentiepijplijn.</span><span class="sxs-lookup"><span data-stu-id="e1804-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="e1804-127">Deze gegevenssets moeten in de werkruimte worden geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="e1804-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="e1804-128">Momenteel ondersteunen we alleen [gegevenssets in tabelvorm](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv-indeling.</span><span class="sxs-lookup"><span data-stu-id="e1804-128">Currently, we only support [tabular datasets](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="e1804-129">De gegevenssets die overeenkomen met entiteitsgegevens, moeten worden geparametriseerd als een pijplijnparameter.</span><span class="sxs-lookup"><span data-stu-id="e1804-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="e1804-130">Gegevenssetparameters in Designer</span><span class="sxs-lookup"><span data-stu-id="e1804-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="e1804-131">Open in de ontwerper **Kolommen in gegevensset selecteren** en selecteer **Instellen als pijplijnparameter**, waar u een naam opgeeft voor de parameter.</span><span class="sxs-lookup"><span data-stu-id="e1804-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="e1804-132">![Gegevenssetparameters in Designer](media/intelligence-designer-dataset-parameters.png "Gegevenssetparameters in Designer")</span><span class="sxs-lookup"><span data-stu-id="e1804-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="e1804-133">Gegevenssetparameter in SDK (Python)</span><span class="sxs-lookup"><span data-stu-id="e1804-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="e1804-134">Batch-inferentiepijplijn</span><span class="sxs-lookup"><span data-stu-id="e1804-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="e1804-135">In de designer kan een trainingspijplijn worden gebruikt om een inferentiepijplijn te maken of bij te werken.</span><span class="sxs-lookup"><span data-stu-id="e1804-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="e1804-136">Momenteel worden alleen batch-inferentiepijplijnen ondersteund.</span><span class="sxs-lookup"><span data-stu-id="e1804-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="e1804-137">Met de SDK kunt u de pijplijn publiceren naar een eindpunt.</span><span class="sxs-lookup"><span data-stu-id="e1804-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="e1804-138">Momenteel integreert Customer Insights met de standaardpijplijn in een batchpijplijneindpunt in de Machine Learning-werkruimte.</span><span class="sxs-lookup"><span data-stu-id="e1804-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="e1804-139">Pijplijngegevens in Customer Insights importeren</span><span class="sxs-lookup"><span data-stu-id="e1804-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="e1804-140">De designer levert de [module Gegevens exporteren](/azure/machine-learning/algorithm-module-reference/export-data) waarmee de uitvoer van een pijplijn kan worden geëxporteerd naar Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="e1804-140">The designer provides the [Export Data module](/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="e1804-141">Momenteel moet de module het gegevensopslagtype **Azure Blob Storage** gebruiken en de **Gegevensopslag** en het relatieve **Pad** parametriseren.</span><span class="sxs-lookup"><span data-stu-id="e1804-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="e1804-142">Customer Insights overschrijft beide parameters tijdens de uitvoering van een pijplijn met een gegevensopslag en pad dat toegankelijk is voor het product.</span><span class="sxs-lookup"><span data-stu-id="e1804-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e1804-143">![Configuratie van de module Gegevens exporteren](media/intelligence-designer-importdata.png "Configuratie van de module Gegevens exporteren")</span><span class="sxs-lookup"><span data-stu-id="e1804-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="e1804-144">Wanneer u de inferentie-uitvoer schrijft met behulp van code, kunt u de uitvoer uploaden naar een pad binnen een *geregistreerde gegevensopslag* in de werkruimte.</span><span class="sxs-lookup"><span data-stu-id="e1804-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="e1804-145">Als het pad en de gegevensopslag in de pijplijn zijn geparametriseerd, kan Customer Insights de inferentie-uitvoer lezen en importeren.</span><span class="sxs-lookup"><span data-stu-id="e1804-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="e1804-146">Momenteel wordt één uitvoer in tabelvorm in csv-indeling ondersteund.</span><span class="sxs-lookup"><span data-stu-id="e1804-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="e1804-147">Het pad moet de map en de bestandsnaam bevatten.</span><span class="sxs-lookup"><span data-stu-id="e1804-147">The path must include the directory and filename.</span></span>

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```


[!INCLUDE[footer-include](../includes/footer-banner.md)]