---
title: Experimenten met Machine Learning Studio (klassiek)
description: Gebruik Machine Learning Studio-modellen (klassiek) in Dynamics 365 Customer Insights.
ms.date: 12/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: ameetj
manager: shellyha
ms.openlocfilehash: 556b6810db0ed2733a3f086291757bd85b77e371
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/03/2020
ms.locfileid: "4669012"
---
# <a name="use-models-based-on-azure-machine-learning-studio-classic"></a>Modellen op basis van Azure Machine Learning Studio (klassiek) gebruiken

De geharmoniseerde gegevens in Dynamics 365 Customer Insights zijn een bron voor het bouwen van Machine Learning-modellen die aanvullende zakelijke inzichten kunnen genereren. Customer Insights kan worden geïntegreerd met Machine Learning Studio (klassiek) om uw eigen aangepaste modellen te gebruiken. Zie [Experimenten met Azure Machine Learning](azure-machine-learning-experiments.md) om te zien hoe modellen die zijn ontwikkeld in Azure Machine Learning, zijn geïntegreerd met Customer Insights.

## <a name="prerequisites"></a>Vereisten

- Toegang tot Customer Insights
- Actief Azure Enterprise-abonnement
- [Geharmoniseerde klantprofielen](data-unification.md)
- [Het exporteren van entiteiten naar Azure Blob-opslag](export-azure-blob-storage.md) instellen

## <a name="set-up-machine-learning-studio-classic"></a>Machine Learning Studio (klassiek) instellen

In een eerste stap moeten we een werkruimte maken voor en Machine Learning Studio (klassiek) openen.

1. Ga naar [https://www.portal.azure.com](https://www.portal.azure.com/) en meld u aan.

1. Selecteer **Een resource maken**.

1. Zoek **Machine Learning Studio-werkruimte** en selecteer **Maken**.

1. Voer de vereiste gegevens in voor het [maken van de werkruimte](https://docs.microsoft.com/azure/machine-learning/studio/create-workspace). Kies het **Prijsniveau voor webservice-abonnement** op basis van de hoeveelheid gegevens die u wilt importeren. Selecteer voor de beste prestaties de **locatie** die geografisch het dichtst in de buurt is.

1. Nadat u de resource hebt gemaakt, wordt het dashboard voor de Machine Learning Studio-werkruimte weergegeven. Selecteer **Machine Learning Studio starten**.

   ![Gebruikersinterface van Azure Machine Learning Studio](media/azure-machine-learning-studio.png)

## <a name="work-with-azure-machine-learning-studio"></a>Werken met Azure Machine Learning Studio

U kunt nu een nieuw experiment maken of een bestaande experimentsjabloon importeren vanuit de voorbeeldgalerie. Er zijn voorbeeldexperimenten voor drie standaardscenario's:

- [Voorspelling voor verloop](#churn-analysis)

- [Levensduurwaarde van klant](#customer-lifetime-value-prediction)

- [Productaanbeveling of op één na beste actie](#productrecommendation-or-next-best-action)

1. Als u een nieuw experiment maakt of een experimentsjabloon uit de galerie gebruikt, moet u de eigenschappen voor **Gegevens importeren** configureren. Gebruik de geleide ervaring of geef rechtstreeks details op om toegang te krijgen tot de Azure Blob Storage die uw gegevens bevat.  

   ![Experiment in Azure Machine Learning Studio](media/azure-machine-learning-studio-experiment.png)

1. Nu kunt u een aangepaste verwerkingspipeline bouwen om de gegevens op te schonen en voor te verwerken, functies te extraheren en een geschikt model te trainen.

1. Test en optimaliseer de modelprestaties.

1. Selecteer, als u tevreden bent met de kwaliteit van een model, de optie **Webservice instellen** > **Voorspellende webservice**. Deze optie importeert het getrainde model en de pipeline voor featurisatie vanuit het trainingsexperiment naar een voorspellende service. De voorspellende service kan een andere set invoergegevens gebruiken met het schema dat in het trainingsexperiment wordt gebruikt om voorspellingen te doen.

   ![Een voorspellende webservice instellen](media/predictive-webservice-control.png)

1. Zodra het experiment met de voorspellende webservice is geslaagd, kunt u het implementeren voor automatische planning. Als u de webservice wilt laten werken met Customer Insights selecteert u **Webservice implementeren** > **Webservice implementeren [Nieuw] Preview**. [Meer informatie over het implementeren van een webservice](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service)

   ![Een voorspellende webservice implementeren](media/predictive-webservice-deploy.png)

## <a name="sample-models-from-the-gallery"></a>Voorbeeldmodellen uit de galerie

We gebruiken een fictief scenario van Contoso Hotel voor de modellen in dit artikel. Contoso Hotel verzamelt de volgende gegevens:

- CRM-gegevens bestaande uit hotelverblijfsactiviteiten. De gegevensset bevat informatie over de verblijfsdatum voor elke geregistreerde klant. Het bevat ook informatie over de boeking, kamertypen, details van uitgaven enzovoort. De gegevens beslaan vier jaar, van januari 2014 tot januari 2018.
- Klantprofielen van hotelgasten. Deze profielen bevatten informatie over elke klant, inclusief hun naam, geboortedatum, postadres, geslacht en telefoonnummer.
- Gebruik van door het hotel aangeboden services, zoals de spa, wasserette, Wi-Fi of koerier. Deze informatie wordt voor elke geregistreerde klant vastgelegd. Het gebruik van services is doorgaans gekoppeld aan het verblijf. In sommige gevallen kunnen services door klanten worden gebruikt zonder dat zij in het hotel verblijven.

## <a name="churn-analysis"></a>Verloopanalyse

Verloopanalyse is van toepassing op verschillende bedrijfsgebieden. In dit voorbeeld gaan we kijken naar het serviceverloop, specifiek in de context van hotelservices, zoals hierboven beschreven. Het biedt een werkend voorbeeld van een end-to-end-modelpijplijn die kan worden gebruikt als startpunt voor elk ander type verloopmodel.

### <a name="definition-of-churn"></a>Definitie van verloop

De definitie van verloop kan per scenario verschillen. In dit voorbeeld moet van verloop worden gesproken als een gast het hotel het afgelopen jaar niet heeft bezocht.  

De experimentsjabloon kan vanuit de galerie worden geïmporteerd. Zorg er eerst voor dat u de gegevens importeert voor **Hotelverblijfsactiviteit**, **Klantgegevens** en **Servicegebruiksgegevens** vanuit Azure Blob-opslag.

   ![Gegevens importeren voor verloopmodel](media/import-data-azure-blob-storage.png)

### <a name="featurization"></a>Featurisatie

Op basis van de definitie van verloop identificeren we eerst de onbewerkte functies die het label zullen beïnvloeden. Vervolgens verwerken we deze onbewerkte functies tot numerieke functies die kunnen worden gebruikt met Machine Learning-modellen. Gegevensintegratie vindt plaats in Customer Insights, zodat we deze tabellen kunnen samenvoegen met behulp van de *Klant-id*.

   ![Geïmporteerde gegevens samenvoegen](media/join-imported-data.png)

Het maken van functies voor het bouwen van het model voor verloopanalyse kan een beetje lastig zijn. De gegevens zijn een functie van de tijd waarbij dagelijks nieuwe hotelactiviteit wordt geregistreerd. Tijdens de featurisatie willen we statische functies genereren vanuit de dynamische gegevens. In dit geval genereren we meerdere functies van hotelactiviteit met een schuivend venster van één jaar. We breiden ook de categorische functies zoals kamertype of boekingstype uit naar afzonderlijke functies met behulp van one-hot-codering.  

Definitieve lijst met functies:

| **Nummer**  | **Original_Column**          | **Afgeleide functies**                                                                                                                      |
|-------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 1           | Kamertype                    | RoomTypeLargeCount, RoomTypeSmallCount                                                                                                    |
| 2           | Type boeking                 | BookingTypeOnlineCount, BookingTypePhoneCallCount                                                                                         |
| 3           | Reiscategorie              | TravelCategoryBusinessCount, TravelCategoryLeisureCount                                                                                   |
| 4           | Uitgegeven dollars                | TotalDollarSpent                                                                                                                          |
| 5           | In- en uitcheckdatum  | StayDayCount, StayDayCount2016, StayDayCount2015, StayDayCount2014, StayCount, StayCount2016. StayCount2015, StayCount2014                |
| 6           | Servicegebruik                | UsageTenure, ConciergeUsage, CourierUsage, DryCleaningUsage, GymUsage, PhoneUsage, RestaurantUsage, SpaUsage, TelevisionUsage, WifiUsage  |

### <a name="model-selection"></a>Modelselectie

Nu moeten we het optimale algoritme kiezen om te gebruiken. In dit geval zijn de meeste functies gebaseerd op categorische functies. Op beslissingsstructuren gebaseerde modellen werken doorgaans goed. Als er alleen numerieke functies zijn, kunnen neurale netwerken een betere keuze zijn. Support Vector Machine (SVM) is eveneens een goede kandidaat in dergelijke situaties. Dit vereist echter nogal wat afstemming om de beste prestaties te verkrijgen. We kiezen **Two-Class Boosted Decision Tree** als het eerste model naar keuze, gevolgd door **Two-Class SVM** als het tweede model. Met Azure Machine Learning Studio kunt u A/B-tests uitvoeren, dus is het gunstig om met twee modellen te beginnen in plaats van één.

De volgende afbeelding toont de pipeline voor training en evaluatie van het model in Azure Machine Learning Studio:

![Verloopmodel in Azure Machine Learning Studio](media/azure-machine-learning-model.png)

We passen ook een techniek toe genaamd **Permutation Feature Importance**, een belangrijk aspect van modeloptimalisatie. Ingebouwde modellen hebben weinig tot geen inzicht in de impact van een specifieke functie op de uiteindelijke voorspelling. De calculator voor functiebelang gebruikt een aangepast algoritme om de invloed van individuele functies op de uitkomst voor een specifiek model te berekenen. Het functiebelang wordt genormaliseerd tussen +1 en -1. Een negatieve invloed betekent dat de overeenkomstige functie een contra-intuïtieve invloed heeft op de uitkomst en uit het model moet worden verwijderd. Een positieve invloed geeft aan dat de functie een grote bijdrage levert aan de voorspelling. Deze waarden zijn geen correlatiecoëfficiënten, aangezien het verschillende metrische gegevens zijn. Zie [Permutation Feature Importance](https://docs.microsoft.com/azure/machine-learning/studio-module-reference/permutation-feature-importance) voor meer informatie.

Het hele [verloopexperiment is beschikbaar in de Azure AI-galerie](https://gallery.azure.ai/Experiment/Hotel-Churn-Predictive-Exp).

## <a name="customer-lifetime-value-prediction"></a>Voorspelling van klantlevensduur

De berekening van de klantlevensduur (CLTV) is een van de belangrijkste meetgegevens die een bedrijf kan gebruiken om zijn klanten te beoordelen en te segmenteren. Voor het hotelwezen is het van cruciaal belang om hun klanten te kennen. Het begrijpen van factoren die gasten tot goede klanten maken, is bijvoorbeeld cruciale informatie. Het helpt het hotelmanagement te beoordelen op welke functies ze zich moeten concentreren en deze moeten verbeteren om hun goedbetaalde klanten tevreden te stellen. Deze beslissingen kunnen een directe impact hebben op omzet en winst.  

### <a name="definition-of-cltv"></a>Definitie van CLTV

Voor dit voorbeeld definiëren we de CLTV van een klant als het totale bedrag in dollars dat de klant naar verwachting in de komende 365 dagen zal uitgeven. We gaan de gegevens van de afgelopen drie jaar gebruiken voor alle klanten om deze waarde te voorspellen.

### <a name="featurization"></a>Featurisatie

In dit geval zal featurisatie veel lijken op het verloopscenario. De labels en voorspelde waarden zijn echter anders dan hierboven gedefinieerd.

### <a name="model-selection"></a>Modelselectie

Het voorspellen van de CLTV is een regressieprobleem, aangezien de voorspelde waarde een continue variabele met een positieve waarde is. Op basis van de functie-eigenschappen selecteren we **Boosted Decision Tree Regression** als één algoritme en **Neural Network Regression** als een ander algoritme voor het trainen van het model.

## <a name="product-recommendation-or-next-best-action"></a>Productaanbeveling of op één na beste actie

Productaanbeveling in een hotelscenario wordt geïnterpreteerd als het aanbevelen van services die door het hotel aan de klanten worden aangeboden. Het doel is om de juiste services voor klanten te kiezen, zodat hun gebruik wordt gemaximaliseerd. Het is vergelijkbaar met filmaanbevelingen voor gebruikers van videostreamingservices.

### <a name="definition-of-product-recommendation-or-next-best-action"></a>Definitie van productaanbeveling of op één na beste actie

We definiëren het doel als het maximaliseren van het bedrag aan servicegebruik in dollars door hotelklanten de best passende services aan te bieden op basis van hun interesse.

### <a name="featurization"></a>Featurisatie

Net als bij het verloopmodel voegen we de ServiceCustomerID voor het hotel toe aan CustomerID om consistente aanbevelingen per CustomerID op te bouwen.

![Featurisatie voor het aanbevelingsmodel](media/azure-machine-learning-model-featurization.png)

De gegevens zijn afkomstig van drie verschillende entiteiten en er worden functies van afgeleid. De featurisatie voor het probleem van aanbeveling is anders in vergelijking met verloop- of CLTV-scenario's. Het aanbevelingsmodel heeft invoergegevens nodig in de vorm van drie reeksen functies.

### <a name="model-selection"></a>Modelselectie

We voorspellen producten of services met behulp van het algoritme genaamd **Train Matchbox Recommender** om het aanbevelingsmodel te trainen.

![Algoritme voor productaanbevelingen](media/azure-machine-learning-model-recommendation-algorithm.png)

De drie invoerpoorten voor het model **Train Matchbox Recommender** neemt de gebruiksgegevens van de trainingsservice, de klantbeschrijving (optioneel) en de servicebeschrijving op. Er zijn drie verschillende manieren om het model te scoren. Een daarvan is voor modelevaluatie waarbij een NDCG-score (Normalized Discounted Cumulative Gain) wordt berekend om de beoordeelde items te rangschikken. In dit experiment hebben we de NDCG-score vastgesteld op 0,97. De andere twee opties zijn het scoren van het model op de gehele aanbevolen servicecatalogus of alleen op items die gebruikers niet eerder hebben gebruikt.

Als we verder kijken naar de verdelingen van de aanbevelingen over de hele servicecatalogus, zien we dat telefoon, wifi en koerier de topservices zijn die moeten worden aanbevolen. Dit komt overeen met wat we hebben gevonden in de distributies van de serviceverbruiksgegevens:

![Uitvoer van aanbevelingsmodel](media/azure-machine-learning-model-output.png)

Het hele [productaanbevelingsexperiment is toegankelijk in Azure AI Gallery.](https://gallery.azure.ai/Experiment/Recommendation-4)

## <a name="integrate-custom-models"></a>Aangepaste modellen integreren

Om deze voorspellingen te gebruiken in Customer Insights, moet u de voorspellingen **exporteren** samen met de klant-id's. [Exporteer ze naar dezelfde Azure Blob-opslaglocatie](https://docs.microsoft.com/azure/storage/common/storage-import-export-data-from-blobs) waarnaar u de brongegevens exporteert. De voorspellende webservice kan zodanig worden gepland dat deze regelmatig wordt uitgevoerd en dat de scores worden bijgewerkt.

Gegevens die door het aangepaste model worden gegenereerd, kunnen worden gebruikt om uw klantgegevens verder te verrijken. Zie [Aangepaste Machine Learning-modellen](custom-models.md) voor meer informatie.
