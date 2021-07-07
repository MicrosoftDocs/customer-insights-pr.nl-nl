---
title: Aangepaste Machine Learning-modellen | Microsoft Docs
description: Werk met aangepaste modellen van Azure Machine Learning in Dynamics 365 Customer Insights.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 82f6f363497f8f1b45fa84acd49bcaed332e60e8
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305620"
---
# <a name="custom-machine-learning-models"></a>Aangepaste Machine Learning-modellen

Met **Informatie** > **Aangepaste modellen** kunt u werkstromen beheren op basis van Azure Machine Learning-modellen. Werkstromen helpen u bij het kiezen van de gegevens waaruit u inzichten wilt genereren, en helpen u de resultaten toe te wijzen aan uw geharmoniseerde klantgegevens. Zie voor meer informatie over het bouwen van aangepaste ML-modellen [Azure Machine Learning-modellen gebruiken](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>Verantwoordelijke AI

Voorspellingen bieden mogelijkheden om betere klantervaringen te creëren, zakelijke mogelijkheden en omzetstromen te verbeteren. We raden u ten zeerste aan de waarde van uw voorspelling af te wegen tegen de impact die deze heeft en vooroordelen die op een ethische manier kunnen worden geïntroduceerd. Lees meer over hoe Microsoft [omgaat met Verantwoordelijke AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). U kunt ook meer informatie vinden over [technieken en processen voor verantwoordelijke Machine Learning](/azure/machine-learning/concept-responsible-ml) specifiek voor Azure Machine Learning.

## <a name="prerequisites"></a>Vereisten

- Momenteel ondersteunt deze functie webservices die zijn gepubliceerd via [Machine Learning Studio (klassiek)](https://studio.azureml.net) en [Azure Machine Learning batch-pijplijnen](/azure/machine-learning/concept-ml-pipelines).

- U hebt een Azure Data Lake Gen2-opslagaccount nodig dat is gekoppeld aan uw Azure Studio-exemplaar om deze functie te gebruiken. Zie voor meer informatie [Een Azure Data Lake Storage Gen2-opslagaccount maken](/azure/storage/blobs/data-lake-storage-quickstart-create-account).

- Voor Azure Machine Learning-werkruimten met pijplijnen hebt u de toegangsrechten van eigenaars of beheerders nodig voor de Azure Machine Learning-werkruimte.

   > [!NOTE]
   > Gegevens worden overgedragen tussen uw Customer Insights-exemplaren en de geselecteerde Azure-webservices of -pijplijnen in de werkstroom. Als u gegevens overboekt naar een Azure-service, moet u ervoor zorgen dat de service is geconfigureerd om gegevens te verwerken op de manier en de locatie die voldoen aan de juridische vereisten of voorschriften voor die gegevens voor uw organisatie.

## <a name="add-a-new-workflow"></a>Een nieuwe werkstroom toevoegen

1. Ga naar **Informatie** > **Aangepaste modellen** en selecteer **Nieuwe werkstroom**.

1. Geef uw aangepaste model een herkenbare naam in het veld **Naam**.

   > [!div class="mx-imgBorder"]
   > ![Schermafbeelding van het deelvenster Nieuwe werkstroom](media/new-workflowv2.png "Schermafbeelding van het deelvenster Nieuwe werkstroom")

1. Selecteer de organisatie die de webservice bevat in **Tenant die uw webservice bevat**.

1. Selecteer, als uw Azure Machine Learning-abonnement zich in een andere tenant bevindt dan Customer Insights, **Aanmelden** met uw referenties voor de geselecteerde organisatie.

1. Selecteer de **Werkruimten** die zijn gekoppeld aan uw webservice. Er worden twee secties vermeld, een voor Azure Machine Learning v1 (Machine Learning Studio (klassiek)) en Azure Machine Learning v2 (Azure Machine Learning). Als u niet zeker weet welke werkruimte de juiste is voor uw Machine Learning Studio-webservice (klassiek), selecteert u **Willekeurig**.

1. Kies de Machine Learning Studio-webservice (klassiek) of Azure Machine Learning-pijplijn in de vervolgkeuzelijst **Webservice met uw model**. Selecteer vervolgens **Volgende**.
   - Meer informatie over [een webservice publiceren in Machine Learning Studio (klassiek)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - Meer informatie over [een pijplijn publiceren in Azure Machine Learning met de designer](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) of [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). Uw pijplijn moet worden gepubliceerd onder een [pijplijn-eindpunt](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Voor elke **Invoer voor webservice** selecteert u de overeenkomende **Entiteit** in doelgroepinzichten en tot slot selecteert u **Volgende**.
   > [!NOTE]
   > De aangepaste modelwerkstroom past heuristiek toe om de invoervelden van de webservice toe te wijzen aan de entiteitskenmerken op basis van de naam en het gegevenstype van het veld. U ziet een foutmelding als een webserviceveld niet kan worden toegewezen aan een entiteit.

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

1. Selecteer het overeenkomende kenmerk uit de vervolgkeuzelijst **Klant-id in resultaten** die klanten identificeert en selecteer **Opslaan**.

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

1. Selecteer het overeenkomende kenmerk uit de vervolgkeuzelijst **Klant-id in resultaten** die klanten identificeert en selecteer **Opslaan**.
   Kies een kenmerk uit de inferentie-uitvoer met waarden die vergelijkbaar zijn met de kolom Klant-id van de entiteit Klant. Als u deze kolom in uw gegevensset hebt, kiest u een kenmerk dat de rij uniek identificeert.

## <a name="run-a-workflow"></a>Een werkstroom uitvoeren

1. Selecteer op de pagina **Aangepaste modellen** de verticale ellips in de kolom **Acties** naast een werkstroom die u eerder hebt gemaakt.

1. Selecteer **Uitvoeren**.

Uw werkstroom wordt ook automatisch uitgevoerd bij elke geplande vernieuwing. Lees meer over [Geplande vernieuwingen instellen](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Een werkstroom verwijderen

1. Selecteer op de pagina **Aangepaste modellen** de verticale ellips in de kolom **Acties** naast een werkstroom die u eerder hebt gemaakt.

1. Selecteer **Verwijderen** en bevestig de verwijdering.

Uw werkstroom wordt verwijderd. De [entiteit](entities.md) die is gemaakt toen u de werkstroom maakte, blijft bestaan en kan worden bekeken via de pagina **Entiteiten**.

## <a name="results"></a>Resultaten

Resultaten van een werkstroom worden opgeslagen in de entiteit die is geconfigureerd tijdens de fase Modeluitvoerparameters. U kunt deze gegevens openen via de [pagina Entiteiten](entities.md) of met [API-toegang](apis.md)​.

### <a name="api-access"></a>API-toegang

Gebruik de volgende indeling voor de specifieke OData-query om gegevens op te halen uit een aangepaste modelentiteit:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Vervang `<your instance id>` door de id van uw Customer Insights-omgeving, die u in de adresbalk van uw browser vindt wanneer u Customer Insights opent.

1. Vervang `<custom model output entity>` door de entiteitsnaam die u hebt opgegeven tijdens de stap Modeluitvoerparameters van de aangepaste modelconfiguratie.

1. Vervang `<guid value>` door de klant-id van de klant waarvoor u de record wilt openen. U kunt deze id meestal vinden op de [pagina Klantprofielen](customer-profiles.md) in het veld Klant-id.

## <a name="frequently-asked-questions"></a>Veelgestelde vragen

- Waarom kan ik mijn pijplijn niet zien wanneer ik een aangepaste modelwerkstroom instel?    
  Dit probleem wordt vaak veroorzaakt door een configuratieprobleem in de pijplijn. Zorg ervoor dat de [invoerparameter is geconfigureerd](azure-machine-learning-experiments.md#dataset-configuration) en de [gegevensopslag voor uitvoer en padparameters](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) zijn geconfigureerd.

- Wat betekent de fout Informatiewerkstroom kon niet worden opgeslagen?    
  Gebruikers zien dit foutbericht meestal als ze geen eigenaar- of beheerderstoegang hebben voor de werkruimte. De gebruiker heeft een hoger machtigingsniveau nodig om Customer Insights in staat te stellen de werkstroom als een service te verwerken in plaats van de gebruikersreferenties te gebruiken voor volgende uitvoeringen van de werkstroom.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
