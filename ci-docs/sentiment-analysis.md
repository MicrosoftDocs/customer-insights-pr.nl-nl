---
title: Gevoel voor klantfeedback analyseren (preview)
description: Leer hoe u een gevoelsanalysemodel op klantfeedback kunt gebruiken in Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 61ce9fb18efa6152dddb2e31f4fd0366a31ac2c7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610456"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Gevoel in klantfeedback analyseren (preview)

Met gevoelsanalyse kunt u klantgevoel synthetiseren en bedrijfsaspecten identificeren als kansen voor verbetering. Deze Customer Insights-functie helpt u te begrijpen wat goed werkt en wat verbeterd moet worden. Het kan u helpen om zakelijke acties te stimuleren die ervaringen mogelijk maken, resulterend in een hoge klanttevredenheid en -loyaliteit.

## <a name="overview"></a>Samenzicht

De gevoelsanalysefunctie genereert twee afgeleide inzichten per klant-id. Een gevoelscore (van -5 tot 5) en een lijst van toepasselijke bedrijfsaspecten (bedrijfsgebieden) samen helpen u om de feedback van klanten beter te begrijpen.

Deze analyse helpt u bij het volgende:
- Een overzicht krijgen van klantgevoelens ten opzichte van een merk of organisatie
- Klanten identificeren die een negatief gevoel hebben, om uw campagnes en contacten te focussen en te optimaliseren voor een hoger rendement  
- bedrijfsaspecten identificeren met problemen die door klanten zijn opgemerkt  
- Klanten segmenteren op basis van hun gevoel om gepersonaliseerde campagnes uit te voeren met gerichte verkoop-, marketing- en ondersteuningsinspanningen
- Bedrijfsactiviteiten optimaliseren door aandachtsgebieden of kansen aan te pakken die door klanten zijn genoemd
- bedrijfsaspecten herkennen die het goed doen en tevreden klanten belonen via loyaliteits- en promotieprogramma's

Het model biedt een lijst met woorden die van invloed waren op de beslissing van het model om een bepaalde gevoelsscore of bepaald bedrijfsaspect toe te kennen aan feedbackopmerkingen.  

We gebruiken twee **Modellen voor verwerking van natuurlijke taal (Natural Language Processing, NLP)**: het eerste kent aan elke feedbackopmerking een gevoelsscore toe. Het tweede model legt een relatie met alle toepasselijke bedrijfsaspecten. De modellen zijn getraind op openbare gegevens uit bronnen uit sociale media, de detailhandel, restaurants, consumentenproducten en de auto-industrie.
  
Vooraf gedefinieerde bedrijfsaspecten voor het model om te relateren aan feedbackgegevens zijn onder meer:
- Accountbeheer
- Uitchecken en betaling
- Klantenondersteuning
- In de winkel ophalen
- Verzending en ophalen van verpakking
- Vooraf bestellen
- Prijs
- Privacy en beveiliging
- Promotie en beloningen
- Betalingsbewijs en garantie
- Omruilen en annuleren
- Nauwkeurigheid van afhandeling
- Website-/app-kwaliteit

> [!NOTE]
> Momenteel ondersteunen we alleen gevoelsanalyse op Engelse feedback van klanten. In de toekomst zullen meer talen worden ondersteund. Als feedback in andere talen wordt geüpload, geeft het model nog steeds resultaten. Deze resultaten zullen echter niet nauwkeurig zijn.

## <a name="prerequisites"></a>Vereisten

- Minimaal [Inzendermachtigingen](permissions.md)
- [Geharmoniseerde](data-unification.md) gegevens voor tekstfeedback. We raden u sterk aan om [uw feedbackgegevensentiteiten te configureren als activiteitsentiteiten van het semantische type](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (Feedback-type).
- Unified Customer ID (UCID) van gegevensharmonisatie voor afstemming van gegevensrecords voor tekstfeedback op een individuele klant.
- Feedback-id
- Tijdstempel van feedback
- Feedbacktekst

Customer Insights kan tot 10 miljoen feedbackrecords verwerken voor een enkele modelrun. Het model kan feedbackopmerkingen tot 128 woorden analyseren. Als een feedbackopmerking langer is, houdt de analyse alleen rekening met de eerste 128 woorden.

> [!NOTE]
> Er kan slechts één feedbackentiteit worden geconfigureerd. Als er meerdere feedbackentiteiten zijn, combineert u deze in Power Query vóór de gegevensopname.

## <a name="configure-a-sentiment-analysis"></a>Een gevoelsanalyse configureren

1. Ga naar **Informatie** > **Voorspellingen**.

1. Selecteer op het tabblad **Maken** de optie **Model gebruiken** op de tegel **Analyse van klantgevoel (preview)**.

1. Selecteer **Aan de slag**.

1. Geef de analyse een **naam** ern verstrek de **entiteitsnaam voor uitvoer van bedrijfsaspect** en de **entiteitsnaam voor uitvoer van gevoelsscore**.

1. Selecteer **Volgende**.

1. Selecteer **Gegevens toevoegen** voor **Klantfeedback**.

1. Selecteer het semantische activiteitstype **Feedback** die de feedbackgegevens bevat. Als de activiteit niet is ingesteld, selecteert u **hier** en maakt u deze.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Configuratiestap om feedbackactiviteiten te selecteren voor gevoelsanalyse.":::

1. Selecteer de activiteiten die u voor deze gevoelsanalyse wilt gebruiken en selecteer vervolgens **Volgende**.

1. Wijs de kenmerken in uw gegevens toe aan de modelkenmerken. 

1. Selecteer **Save**.

1. Selecteer **Volgende**. De stap **Controleren en uitvoeren** toont een samenvatting van de configuratie en biedt een kans om wijzigingen aan te brengen voordat u de analyse maakt.

1. Selecteer **Bewerken** in een van de stappen om te controleren en eventuele wijzigingen aan te brengen.

1. Als u tevereden bent over uw selecties, selecteert u **Opslaan en uitvoeren** om te beginnen met het uitvoeren van het model. Selecteer **Gereed**. Het tabblad **Mijn voorspellingen** wordt weergegeven terwijl de voorspelling wordt gemaakt. Het proces kan enkele uren in beslag nemen, afhankelijk van de hoeveelheid gegevens die in de voorspelling is gebruikt.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-analysis-results"></a>Analyseresultaten weergeven

1. Ga naar **Informatie** > **Voorspellingen**.

1. Selecteer op het tabblad **Mijn voorspellingen** de voorspelling die u wilt weergeven.

Er zijn twee tabbladen met resultaten.

### <a name="sumary-tab"></a>Tabblad Overzicht

Er zijn vier primaire secties met gegevens op de resultatenpagina.

- **Gemiddelde gevoelstscore**: gevoelsscores helpen u het algemene gevoel van alle klanten te begrijpen.
  - **Negatief** (-5 > 2)
  - **Neutraal** (-1 > 1)
  - **Positief** (2 > 5)
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Visuele weergave van het algemene klantgevoel.":::

- **Verdeling van klanten op gevoelsscore**: klanten worden ingedeeld in negatieve, neutrale en positieve groepen op basis van hun gevoelsscores. Plaats de muisaanwijzer op de balken in het histogram om het aantal klanten en de gemiddelde gevoelsscore in elke groep te zien. Deze gegevens kunnen u helpen [segmenten van klanten maken](prediction-based-segment.md) op basis van hun gevoelsscores.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Staafdiagram toont het klantgevoel in alle drie de gevoelsgroepen.":::

- **Gemiddelde gevoelsscore in de loop van de tijd**: klantgevoel kan in de loop van de tijd veranderen. We bieden trends in het gevoel van uw klanten voor het tijdsbereik van uw gegevens. Deze weergave helpt u het effect van seizoenspromoties, productlanceringen of andere tijdgebonden interventies op het klantgevoel te meten. Bekijk de grafiek door het gewenste jaar te selecteren in het vervolgkeuzemenu.

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Geschiedenisdiagram met de gevoelsscore in de loop van de tijd weergegeven als een lijn.":::

- **Gevoel in zakelijke aspecten**: een gemiddeld sentiment over zakelijke aspecten helpt u te bepalen over welke aspecten van uw bedrijf klanten al tevreden zijn of wel meer aandacht vereisen. Feedbackrecords die niet overeenkomen met een van de ondersteunde bedrijfsaspecten, worden gecategoriseerd onder **Overige**. Sorteer de gegevens door een kolom te selecteren.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Lijst met bedrijfsaspecten met de bijbehorende gevoelswaarde en het aantal klanten dat dit vermeldt.":::

  Selecteer de naam van een bedrijfsaspect om te zien hoe een bedrijfsaspect door het model wordt geïdentificeerd:

  - **Invloedrijke woorden**: de belangrijkste woorden die van invloed waren op de identificatie van een bedrijfsaspect door het AI-model in klantfeedback.
    **Aanstootgevende woorden tonen**: hiermee kunt u aanstootgevende woorden uit de oorspronkelijke feedbackgegevens van klanten in de lijst opnemen. Gewoonlijk is dit uitgeschakeld.  Maskering van aanstootgevende woorden wordt mogelijk gemaakt met een AI-model en detecteert mogelijk niet alle aanstootgevende woorden. Als u een aanstootgevend woord ontdekt dat niet is gefilterd zoals verwacht, laat het ons dan weten.

    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Lijst met invloedrijke woorden met de schakeloptie om aanstootgevende woorden weer te geven of te verbergen.":::

  - **Feedbackvoorbeelden**: feitelijke feedbackrecords in uw gegevens. Woorden zijn kleurgecodeerd volgens hun invloed op de identificatie van een bedrijfsaspect.

### <a name="influential-words-analysis-tab"></a>Tabblad Analyse van invloedrijke woorden

Er zijn drie secties met aanvullende informatie die uitleggen hoe het gevoelsmodel werkt.
  
- **Topwoorden die bijdragen aan een positief gevoel**: belangrijkste woorden die van invloed zijn geweest op de identificatie van positief gevoel in klantfeedback door het AI-model.  

- **Topwoorden die bijdragen aan een negatief gevoel**: belangrijkste woorden die van invloed zijn geweest op de identificatie van negatief gevoel in klantfeedback door het AI-model.

- **Feedbackvoorbeelden**: actuele feedbackrecords, één met een negatief gevoel en één met een positief gevoel. Woorden in de feedbackrecords worden gemarkeerd op basis van hun bijdrage aan de toegewezen gevoelsscore. Woorden die bijdragen aan een positieve gevoelsscore zijn groen gemarkeerd. Woorden die bijdragen aan een negatieve score zijn rood gemarkeerd.
   Selecteer **Meer bekijken** om meer feedbackvoorbeelden te laden.
  
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Voorbeelden van gevoelsanalyse op klantfeedback.":::

**Aanstootgevende woorden tonen**: hiermee kunt u aanstootgevende woorden uit de oorspronkelijke feedbackgegevens van klanten in de lijst opnemen. Gewoonlijk is dit uitgeschakeld.  Maskering van aanstootgevende woorden wordt mogelijk gemaakt met een AI-model en detecteert mogelijk niet alle aanstootgevende woorden. Als u een aanstootgevend woord ontdekt dat niet is gefilterd zoals verwacht, laat het ons dan weten.

## <a name="act-on-analysis-results"></a>Optreden naar aanleiding van analyseresultaten

Als u nieuwe segmenten met klanten wilt maken vanuit de resultaten van de gevoelsanalyse selecteert u **Segmenten maken** boven aan de pagina met modelresultaten.

## <a name="potential-bias"></a>Potentiële vertekening

Zoals met elke functie die kunstmatige intelligentie voor voorspellingen gebruikt, is er mogelijk sprake van vertekening in de gegevens die u gebruikt om het klantgevoel te voorspellen. Als u feedback bijvoorbeeld alleen digitaal verzamelt, mist u mogelijk feedback van klanten die voornamelijk persoonlijk zaken met u doen, wat van invloed is op de uitvoer van de functie.

Aangezien deze functie geautomatiseerde middelen gebruikt om gegevens te evalueren en voorspellingen te doen op basis van die gegevens, kan het daarom worden gebruikt als een methode voor profilering, zoals die term is gedefinieerd door de Algemene Verordening Gegevensbescherming (AVG). Uw gebruik van deze functie om gegevens te verwerken, kan onderhevig zijn aan de AVG of andere wet- of regelgeving. U bent ervoor verantwoordelijk dat uw gebruik van Dynamics 365 Customer Insights, inclusief gevoelsanalyse, voldoet aan alle toepasselijke wet- en regelgeving, inclusief wetten met betrekking tot privacy, persoonlijke gegevens, biometrische gegevens, gegevensbescherming en vertrouwelijkheid van communicatie.

[!INCLUDE [footer-include](includes/footer-banner.md)]

