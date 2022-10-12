---
title: Aangepaste Machine Learning-modellen | Microsoft Docs
description: Werk met aangepaste modellen van Azure Machine Learning in Dynamics 365 Customer Insights.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 89553b511d249fd586e36a1c4944a977513b0643
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609738"
---
# <a name="custom-machine-learning-models"></a>Aangepaste Machine Learning-modellen

> [!NOTE]
> Ondersteuning voor Machine Learning Studio (klassiek) stopt op 31 augustus 2024. We raden u aan voor die tijd over te stappen naar [Azure Machine Learning](/azure/machine-learning/overview-what-is-azure-machine-learning).
>
> Vanaf 1 december 2021 kunt u geen nieuwe resources maken voor Machine Learning Studio (klassiek). Tot en met 31 augustus 2024 kunt u de bestaande resources van Machine Learning Studio (klassieke) blijven gebruiken. Zie [Migreren naar Azure Machine Learning](/azure/machine-learning/migrate-overview) voor meer informatie.

Met aangepaste modellen kunt u werkstromen beheren op basis van Azure Machine Learning-modellen. Werkstromen helpen u bij het kiezen van de gegevens waaruit u inzichten wilt genereren, en helpen u de resultaten toe te wijzen aan uw geharmoniseerde klantgegevens. Zie voor meer informatie over het bouwen van aangepaste ML-modellen [Azure Machine Learning-modellen gebruiken](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Vereisten

- Webservices die zijn gepubliceerd via [Azure Machine Learning batch-pijplijnen](/azure/machine-learning/concept-ml-pipelines).
- Pijplijn moet worden gepubliceerd onder een [pijplijn-eindpunt](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).
- Een [Azure Data Lake Gen2-opslagaccount](/azure/storage/blobs/data-lake-storage-quickstart-create-account) dat is gekoppeld aan uw Azure Studio-exemplaar.
- Voor Azure Machine Learning-werkruimten met pijplijnen zijn de toegangsrechten van eigenaars of beheerders nodig voor de Azure Machine Learning-werkruimte.

  > [!NOTE]
  > Gegevens worden overgedragen tussen uw Customer Insights-exemplaren en de geselecteerde Azure-webservices of -pijplijnen in de werkstroom. Als u gegevens overboekt naar een Azure-service, moet u ervoor zorgen dat de service is geconfigureerd om gegevens te verwerken op de manier en de locatie die voldoen aan de juridische vereisten of voorschriften voor die gegevens voor uw organisatie.

## <a name="add-a-new-workflow"></a>Een nieuwe werkstroom toevoegen

1. Ga naar **Informatie** > **Aangepaste modellen** en selecteer **Nieuwe werkstroom**.

1. Geef een herkenbare **naam** op.

   :::image type="content" source="media/new-workflowv2.png" alt-text="Schermafbeelding van het deelvenster Nieuwe werkstroom.":::

1. Selecteer de organisatie die de webservice bevat in **Tenant die uw webservice bevat**.

1. Selecteer, als uw Azure Machine Learning-abonnement zich in een andere tenant bevindt dan Customer Insights, **Aanmelden** met uw referenties voor de geselecteerde organisatie.

1. Selecteer de **Werkruimten** die zijn gekoppeld aan uw webservice.

1. Kies de Azure Machine Learning-pijplijn in de vervolgkeuzelijst **Webservice die uw model bevat**. Selecteer vervolgens **Volgende**.
   Meer informatie over [een pijplijn publiceren in Azure Machine Learning met de designer](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) of [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).

1. Voor elke **Invoer voor webservice** selecteert u de overeenkomende **Entiteit** in Customer Insights. Selecteer vervolgens **Volgende**.
   > [!NOTE]
   > De aangepaste modelwerkstroom past heuristiek toe om de invoervelden van de webservice toe te wijzen aan de entiteitskenmerken op basis van de naam en het gegevenstype van het veld. U ziet een foutmelding als een webserviceveld niet kan worden toegewezen aan een entiteit.

   :::image type="content" source="media/intelligence-screen2-updated.png" alt-text="Een werkstroom configureren.":::

1. Stel voor **Modeluitvoerparameters** de volgende eigenschappen in:
   - **Entiteitsnaam** voor de resultaten van de pijplijnuitvoer
   - **Parameternaam voor uitvoergegevensopslag** van uw batch-pijplijn
   - **Parameternaam voor uitvoerpad** van uw batch-pijplijn

   :::image type="content" source="media/intelligence-screen3-outputparameters.png" alt-text="Deelvenster Parameter voor modeluitvoer.":::

1. Selecteer het overeenkomende kenmerk in **Klant-id in resultaten**, waar klanten worden geïdentificeerd en selecteer **Opslaan**.

   :::image type="content" source="media/intelligence-screen4-relatetocustomer.png" alt-text="Resultaten relateren aan het deelvenster Klantgegevens.":::

   Op het scherm **Werkstroom opgeslagen** worden details over de werkstroom weergegeven. Als u een werkstroom hebt geconfigureerd voor een Azure Machine Learning-pipeline, wordt Customer Insights gekoppeld aan de werkruimte die de pipeline bevat. Customer Insights krijgt een **Inzender**-rol in de Azure-werkruimte.

1. Selecteer **Gereed**. De pagina **Aangepaste modellen** wordt weergegeven.

1. Selecteer het verticale weglatingsteken (&vellip;) voor de werkstroom en selecteer **Uitvoeren**. Uw werkstroom wordt ook automatisch uitgevoerd bij elke [geplande vernieuwing](schedule-refresh.md).

## <a name="manage-an-existing-workflow"></a>Een bestaande werkstroom beheren

Ga naar **Intelligentie** > **Aangepaste modellen** om de werkstromen te bekijken die u hebt gemaakt.

Selecteer een werkstroom om beschikbare acties te bekijken.

- Een werkstroom **bewerken**
- Een werkstroom **uitvoeren**
- Een werkstroom [**verwijderen**](#delete-a-workflow)

### <a name="edit-a-workflow"></a>Een werkstroom bewerken

1. Ga naar **Intelligentie** > **Aangepaste modellen**.

1. Selecteer het verticale weglatingsteken (&vellip;) naast de werkstroom die u wilt bijwerken en selecteer **Bewerken**.

1. Wijzig zo nodig de **weergavenaam** en selecteer **Volgende**.

1. Werk indien nodig voor elke **invoer voor webservice** de overeenkomende **entiteit** vanuit Customer Insights bij. Selecteer vervolgens **Volgende**.

1. Wijzig voor **Modeluitvoerparameters** een of meer van de volgende:
   - **Entiteitsnaam** voor de resultaten van de pijplijnuitvoer
   - **Parameternaam voor uitvoergegevensopslag** van uw batch-pijplijn
   - **Parameternaam voor uitvoerpad** van uw batch-pijplijn

1. Wijzig het overeenkomende kenmerk **Klant-id in resultaten** om klanten te identificeren. Kies een kenmerk uit de inferentie-uitvoer met waarden die vergelijkbaar zijn met de kolom Klant-id van de entiteit Klant. Als u deze kolom in uw gegevensset hebt, kiest u een kenmerk dat de rij uniek identificeert.

1. Selecteer **Opslaan**

### <a name="delete-a-workflow"></a>Een werkstroom verwijderen

1. Ga naar **Intelligentie** > **Aangepaste modellen**.

1. Selecteer het verticale weglatingsteken (&vellip;) naast de werkstroom die u wilt verwijderen en selecteer **Verwijderen**.

1. Bevestig de verwijdering.

Uw werkstroom wordt verwijderd. De [entiteit](entities.md) die is gemaakt toen u de werkstroom maakte, blijft bestaan en kan worden bekeken via de pagina **Gegevens** > **Entiteiten**.

## <a name="view-the-results"></a>De resultaten bekijken

Resultaten van een werkstroom worden opgeslagen in de entiteitnaam die is gedefinieerd voor **Modeluitvoerparameters**. U kunt toegang krijgen tot deze gegevens vanaf de pagina [**Gegevens** > **Entiteiten**](entities.md) of via [API-toegang](apis.md).

### <a name="api-access"></a>API-toegang

Gebruik de volgende indeling voor de specifieke OData-query om gegevens op te halen uit een aangepaste modelentiteit:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Vervang `<your instance id>` door de id van uw Customer Insights-omgeving, die in de adresbalk van uw browser wordt weergegeven wanneer u Customer Insights opent.

1. Vervang `<custom model output entity>` door de entiteitsnaam die u hebt opgegeven voor de **Modeluitgangsparameters**.

1. Vervang `<guid value>` door de klant-id van de klant waartoe u toegang probeert te krijgen. Deze id wordt weergegeven op de [pagina met klantprofielen](customer-profiles.md) in het veld Klant-id.

## <a name="frequently-asked-questions"></a>Veelgestelde vragen

- Waarom kan ik mijn pijplijn niet zien wanneer ik een aangepaste modelwerkstroom instel?
  Dit probleem wordt vaak veroorzaakt door een configuratieprobleem in de pijplijn. Zorg ervoor dat de [invoerparameter is geconfigureerd](azure-machine-learning-experiments.md#dataset-configuration) en de [gegevensopslag voor uitvoer en padparameters](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) zijn geconfigureerd.

- Wat betekent de fout Informatiewerkstroom kon niet worden opgeslagen? 
  Gebruikers zien dit foutbericht meestal als ze geen eigenaar- of beheerderstoegang hebben voor de werkruimte. De gebruiker heeft een hoger machtigingsniveau nodig om Customer Insights in staat te stellen de werkstroom als een service te verwerken in plaats van de gebruikersreferenties te gebruiken voor volgende uitvoeringen van de werkstroom.

- Wordt een privé-eindpunt/-koppeling voor mijn aangepaste modelwerkstroom ondersteund?
  Customer Insights biedt momenteel geen ondersteuning voor privé-eindpunten voor aangepaste modellen op maat, maar er is een handmatige oplossing beschikbaar. Neem contact op met de ondersteuning voor details.

## <a name="responsible-ai"></a>Verantwoordelijke AI

Voorspellingen bieden mogelijkheden om betere klantervaringen te creëren, zakelijke mogelijkheden en omzetstromen te verbeteren. We raden u ten zeerste aan de waarde van uw voorspelling af te wegen tegen de impact die deze heeft en vooroordelen die op een ethische manier kunnen worden geïntroduceerd. Lees meer over hoe Microsoft [omgaat met Verantwoordelijke AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). U kunt ook meer informatie vinden over [technieken en processen voor verantwoordelijke Machine Learning](/azure/machine-learning/concept-responsible-ml) specifiek voor Azure Machine Learning.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

[!INCLUDE [footer-include](includes/footer-banner.md)]
