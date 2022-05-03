---
title: Azure Machine Learning-experimenten
description: Azure Machine Learning-modellen gebruiken in Dynamics 365 Customer Insights.
ms.date: 12/02/2021
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: cefd037a021b669e827f0593d63b938d452963f7
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646127"
---
# <a name="use-azure-machine-learning-based-models"></a>Azure Machine Learning-modellen gebruiken

De geharmoniseerde gegevens in Dynamics 365 Customer Insights zijn een bron voor het bouwen van Machine Learning-modellen die aanvullende zakelijke inzichten kunnen genereren. Customer Insights kan worden geïntegreerd met Azure Machine Learning om uw eigen aangepaste modellen te gebruiken.

## <a name="prerequisites"></a>Vereisten

- Toegang tot Customer Insights
- Actief Azure Enterprise-abonnement
- [Geharmoniseerde klantprofielen](data-unification.md)
- [Entiteit exporteren naar Azure Blob Storage](export-azure-blob-storage.md) geconfigureerd

## <a name="set-up-azure-machine-learning-workspace"></a>Azure Machine Learning-werkruimte instellen

1. Zie [een Azure Machine Learning-werkruimte maken](/azure/machine-learning/concept-workspace#-create-a-workspace) voor verschillende opties om de werkruimte te maken. Voor de beste prestaties maakt u de werkruimte in een Azure-regio die geografisch het dichtst bij uw Customer Insights-omgeving ligt.

1. Toegang tot uw werkruimte via [Azure Machine Learning Studio](https://ml.azure.com/). Er zijn meerdere [manieren om te communiceren](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) met uw werkruimte.

## <a name="work-with-azure-machine-learning-designer"></a>Werken met Azure Machine Learning designer

Azure Machine Learning-ontwerper biedt een visueel canvas waar u gegevenssets en modules kunt slepen en neerzetten. Een batchpijplijn die is gemaakt vanuit de designer, kan worden geïntegreerd in Customer Insights als deze dienovereenkomstig zijn geconfigureerd. 
   
## <a name="working-with-azure-machine-learning-sdk"></a>Werken met Azure Machine Learning SDK

Datawetenschappers en AI-ontwikkelaars gebruiken de [Azure Machine Learning SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) om Machine Learning-workflows te bouwen. Momenteel kunnen modellen die zijn getraind met de SDK, niet rechtstreeks worden geïntegreerd met Customer Insights. Een batch-inferentiepijplijn die dat model verbruikt, is vereist voor integratie met Customer Insights.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Batchpijplijnvereisten om te integreren met Customer Insights

### <a name="dataset-configuration"></a>Configuratie van gegevensset

U moet gegevenssets maken om entiteitsgegevens uit Customer Insights te gebruiken voor uw batch-inferentiepijplijn. Deze gegevenssets moeten in de werkruimte worden geregistreerd. Momenteel ondersteunen we alleen [gegevenssets in tabelvorm](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv-indeling. De gegevenssets die overeenkomen met entiteitsgegevens, moeten worden geparametriseerd als een pijplijnparameter.
   
* Gegevenssetparameters in Designer
   
     Open in de ontwerper **Kolommen in gegevensset selecteren** en selecteer **Instellen als pijplijnparameter**, waar u een naam opgeeft voor de parameter.

     > [!div class="mx-imgBorder"]
     > ![Gegevenssetparameters in Designer.](media/intelligence-designer-dataset-parameters.png "Gegevenssetparameters in Designer")
   
* Gegevenssetparameter in SDK (Python)
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Batch-inferentiepijplijn
  
* In de designer kan een trainingspijplijn worden gebruikt om een inferentiepijplijn te maken of bij te werken. Momenteel worden alleen batch-inferentiepijplijnen ondersteund.

* Met de SDK kunt u de pijplijn publiceren naar een eindpunt. Momenteel integreert Customer Insights met de standaardpijplijn in een batchpijplijneindpunt in de Machine Learning-werkruimte.
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Pijplijngegevens in Customer Insights importeren

* De designer levert de [module Gegevens exporteren](/azure/machine-learning/algorithm-module-reference/export-data) waarmee de uitvoer van een pijplijn kan worden geëxporteerd naar Azure Storage. Momenteel moet de module het gegevensopslagtype **Azure Blob Storage** gebruiken en de **Gegevensopslag** en het relatieve **Pad** parametriseren. Customer Insights overschrijft beide parameters tijdens de uitvoering van een pijplijn met een gegevensopslag en pad dat toegankelijk is voor het product.
   > [!div class="mx-imgBorder"]
   > ![Configuratie van de module Gegevens exporteren.](media/intelligence-designer-importdata.png "Configuratie van de module Gegevens exporteren")
   
* Wanneer u de inferentie-uitvoer schrijft met behulp van code, kunt u de uitvoer uploaden naar een pad binnen een *geregistreerde gegevensopslag* in de werkruimte. Als het pad en de gegevensopslag in de pijplijn zijn geparametriseerd, kan Customer Insights de inferentie-uitvoer lezen en importeren. Momenteel wordt één uitvoer in tabelvorm in csv-indeling ondersteund. Het pad moet de map en de bestandsnaam bevatten.

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


[!INCLUDE [footer-include](includes/footer-banner.md)]