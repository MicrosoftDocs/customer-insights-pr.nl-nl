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
# <a name="custom-machine-learning-models"></a>Aangepaste Machine Learning-modellen

Met **Informatie** > **Aangepaste modellen** kunt u werkstromen beheren op basis van Azure Machine Learning-modellen. Werkstromen helpen u bij het kiezen van de gegevens waaruit u inzichten wilt genereren, en helpen u de resultaten toe te wijzen aan uw geharmoniseerde klantgegevens. Zie voor meer informatie over het bouwen van aangepaste ML-modellen [Azure Machine Learning-modellen gebruiken](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>Verantwoordelijke AI

Voorspellingen bieden mogelijkheden om betere klantervaringen te creëren, zakelijke mogelijkheden en omzetstromen te verbeteren. We raden u ten zeerste aan de waarde van uw voorspelling af te wegen tegen de impact die deze heeft en vooroordelen die op een ethische manier kunnen worden geïntroduceerd. Lees meer over hoe Microsoft [omgaat met Verantwoordelijke AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). U kunt ook meer informatie vinden over [technieken en processen voor verantwoordelijke Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specifiek voor Azure Machine Learning.

## <a name="prerequisites"></a>Vereisten

- Momenteel ondersteunt deze functie webservices die zijn gepubliceerd via [Machine Learning Studio (klassiek)](https://studio.azureml.net) en [Azure Machine Learning batch-pijplijnen](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).

- U hebt een Azure Data Lake Gen2-opslagaccount nodig dat is gekoppeld aan uw Azure Studio-exemplaar om deze functie te gebruiken. Zie voor meer informatie [Een Azure Data Lake Storage Gen2-opslagaccount maken](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)

## <a name="add-a-new-workflow"></a>Een nieuwe werkstroom toevoegen

1. Ga naar **Informatie** > **Aangepaste modellen** en selecteer **Nieuwe werkstroom**.

1. Geef uw aangepaste model een herkenbare naam in het veld **Naam**.

   > [!div class="mx-imgBorder"]
   > ![Schermafbeelding van het deelvenster Nieuwe werkstroom](media/new-workflowv2.png "Schermafbeelding van het deelvenster Nieuwe werkstroom")

1. Selecteer de organisatie die de webservice bevat in **Tenant die uw webservice bevat**.

1. Selecteer, als uw Azure Machine Learning-abonnement zich in een andere tenant bevindt dan Customer Insights, **Aanmelden** met uw referenties voor de geselecteerde organisatie.

1. Selecteer de **Werkruimten** die zijn gekoppeld aan uw webservice. Er worden twee secties vermeld, een voor Azure Machine Learning v1 (Machine Learning Studio (klassiek)) en Azure Machine Learning v2 (Azure Machine Learning). Als u niet zeker weet welke werkruimte de juiste is voor uw Machine Learning Studio-webservice (klassiek), selecteert u **Willekeurig**.

1. Kies de Machine Learning Studio-webservice (klassiek) of Azure Machine Learning-pijplijn in de vervolgkeuzelijst **Webservice met uw model**. Selecteer vervolgens **Volgende**.
   - Meer informatie over [een webservice publiceren in Machine Learning Studio (klassiek)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - Meer informatie over [een pijplijn publiceren in Azure Machine Learning met de designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) of [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). 
     > [!NOTE]
     > Uw pijplijn moet worden gepubliceerd onder een [pijplijn-eindpunt](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Voor elke **Invoer voor webservice** selecteert u de overeenkomende **Entiteit** in doelgroepinzichten en tot slot selecteert u **Volgende**.

   > [!div class="mx-imgBorder"]
   > ![Een werkstroom configureren](media/intelligence-screen2-updated.png "Een werkstroom configureren")

1. Stel in de stap **Modeluitvoerparameters** de volgende eigenschappen in:
   - Machine Learning Studio (klassiek)
      1. Voer de **Entiteitsnaam** van de uitvoer in waarnaar u de uitvoerresultaten van de webservice wilt laten stromen.
   - Azure Machine Learning
      1. Voer de **Entiteitsnaam** van de uitvoer in waarnaar u de uitvoerresultaten van de pijplijn wilt laten stromen.
      1. Selecteer in de vervolgkeuzelijst de **Parameternaam van de uitvoergegevensopslag** van uw batchpijplijn.
      1. Selecteer in de vervolgkeuzelijst de **Parameternaam van het uitvoerpad** van uw batchpijplijn.
      
      > [!div class="mx-imgBorder"]
      > ![Deelvenster Parameter voor modeluitvoer](media/intelligence-screen3-outputparameters.png "Deelvenster Parameter voor modeluitvoer")

1. Selecteer het overeenkomende kenmerk in de vervolgkeuzelijst **Klant-id in resultaten** die klanten identificeert en selecteer **Opslaan**.
   
   > [!div class="mx-imgBorder"]
   > ![Resultaten relateren aan het deelvenster Klantgegevens](media/intelligence-screen4-relatetocustomer.png "Resultaten relateren aan het deelvenster Klantgegevens")

1. U krijgt het scherm **Werkstroom opgeslagen** te zien met details over de werkstroom.    
   Als u een werkstroom hebt geconfigureerd voor een Azure Machine Learning-pijplijn, worden doelgroepinzichten gekoppeld aan de werkruimte die de pijplijn bevat. Doelgroepinzichten krijgen een rol als **inzender** in de Azure-werkruimte.

1. Selecteer **Gereed**.

1. U kunt de workflow nu uitvoeren vanuit de pagina **Aangepaste modellen**.

## <a name="edit-a-workflow"></a>Een werkstroom bewerken

1. Selecteer op de pagina **Aangepaste modellen** de verticale ellips in de kolom **Acties** naast een werkstroom die u eerder hebt gemaakt en selecteer vervolgens **Bewerken**.

1. U kunt de herkenbare naam van uw werkstroom bijwerken in het veld **Weergavenaam**, maar u kunt de geconfigureerde webservice of pijplijn niet wijzigen. Selecteer **Volgende**.

1. Voor elke **Invoer voor webservice** kunt u de overeenkomende **Entiteit** in doelgroepinzichten bijwerken. Selecteer vervolgens **Volgende**.

1. Stel in de stap **Modeluitvoerparameters** de volgende eigenschappen in:
   - Machine Learning Studio (klassiek)
      1. Voer de **Entiteitsnaam** van de uitvoer in waarnaar u de uitvoerresultaten van de webservice wilt laten stromen.
   - Azure Machine Learning
      1. Voer de **Entiteitsnaam** van de uitvoer in waarnaar u de uitvoerresultaten van de pijplijn wilt laten stromen.
      1. Selecteer de **Parameternaam voor uitvoergegevensopslag** voor uw testpijplijn.
      1. Selecteer de **Parameternaam voor uitvoerpad** voor uw testpijplijn.

1. Selecteer het overeenkomende kenmerk in de vervolgkeuzelijst **Klant-id in resultaten** die klanten identificeert en selecteer **Opslaan**.
   U moet een kenmerk kiezen uit de inferentie-uitvoer met waarden die vergelijkbaar zijn met de kolom Klant-id van de entiteit Klant. Als u deze kolom in uw gegevensset hebt, kiest u een kenmerk dat de rij uniek identificeert.

## <a name="run-a-workflow"></a>Een werkstroom uitvoeren

1. Selecteer op de pagina **Aangepaste modellen** de verticale ellips in de kolom **Acties** naast een werkstroom die u eerder hebt gemaakt.

1. Selecteer **Uitvoeren**.

Uw werkstroom wordt ook automatisch uitgevoerd bij elke geplande vernieuwing. Lees meer over [Geplande vernieuwingen instellen](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Een werkstroom verwijderen

1. Selecteer op de pagina **Aangepaste modellen** de verticale ellips in de kolom **Acties** naast een werkstroom die u eerder hebt gemaakt.

1. Selecteer **Verwijderen** en bevestig de verwijdering.

Uw werkstroom wordt verwijderd. De [entiteit](entities.md) die is gemaakt toen u de werkstroom maakte, blijft bestaan en kan worden bekeken via de pagina **Entiteiten**.
