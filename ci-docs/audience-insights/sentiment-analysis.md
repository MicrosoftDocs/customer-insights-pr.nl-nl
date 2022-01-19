---
title: Semantische analyse voor feedback van klanten
description: Leer hoe u een gevoelsanalysemodel op klantfeedback kunt gebruiken in Dynamics 365 Customer Insights.
ms.date: 12/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 05e530a1bc96c5fd9c7a3bc0197563d8fe330387
ms.sourcegitcommit: cb71e39de9b891c24bd5cd9c014eb3eeb537ac24
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/10/2022
ms.locfileid: "7951077"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analyseer gevoel in klantfeedback (preview)

Klanten verwachten tegenwoordig producten, diensten en ervaringen van hoge kwaliteit. Vooral klanten die hun feedback delen. Het is voor organisaties een hele uitdaging om een toenemend gegevensvolume te analyseren zonder verminderde nauwkeurigheid en hogere arbeidskosten. Dynamics 365 Customer Insights biedt een gevoelsanalysemodel voor klantfeedback waarmee organisaties hun gegevens nauwkeuriger en tegen lagere kosten kunnen analyseren.

Met gevoelsanalyse kunt u klantgevoel synthetiseren en bedrijfsaspecten identificeren als kansen voor verbetering. Deze Customer Insights-functie helpt u te begrijpen wat goed werkt en wat verbeterd moet worden. Concentreer u op de meest relevante en impactvolle bedrijfsonderdelen om de ervaring voor uw klanten te verbeteren. Uiteindelijk kan het u helpen om zakelijke acties te stimuleren die ervaringen mogelijk maken, resulterend in een hoge klanttevredenheid en -loyaliteit.

## <a name="overview"></a>Samenzicht

De gevoelsanalysefunctie genereert twee afgeleide inzichten per klant-id. Een gevoelscore (van -5 tot 5) en een lijst van toepasselijke bedrijfsaspecten (bedrijfsgebieden) samen helpen u om de feedback van klanten beter te begrijpen. 

Met behulp van deze gegevens is het mogelijk de volgende resultaten te bereiken: 
- Een overzicht krijgen van klantgevoelens ten opzichte van een merk of organisatie
- Klanten identificeren die een negatief gevoel hebben, om uw campagnes en contacten te focussen en te optimaliseren voor een hoger rendement  
- bedrijfsaspecten identificeren met problemen die door klanten zijn opgemerkt  
- Klanten segmenteren op basis van hun gevoel om gepersonaliseerde campagnes uit te voeren met gerichte verkoop-, marketing- en ondersteuningsinspanningen
- Bedrijfsactiviteiten optimaliseren door aandachtsgebieden of kansen aan te pakken die door klanten zijn genoemd
- bedrijfsaspecten herkennen die het goed doen en tevreden klanten belonen via loyaliteits- en promotieprogramma's

Om ervoor te zorgen dat u de resultaten van de modellen kunt vertrouwen, geven we transparante informatie over hoe de modellen beslissingen nemen. U krijgt een lijst met woorden die van invloed waren op de beslissing van de modellen om een bepaalde gevoelsscore of bepaald bedrijfsaspect toe te kennen aan feedbackopmerkingen.  

We gebruiken twee **Modellen voor verwerking van natuurlijke taal (Natural Language Processing, NLP)**: het eerste kent aan elke feedbackopmerking een gevoelsscore toe. Het tweede model legt een relatie met alle toepasselijke bedrijfsaspecten. De modellen zijn getraind op openbare gegevens uit bronnen uit sociale media, de detailhandel, restaurants, consumentenproducten en de auto-industrie.    
  
- Vooraf gedefinieerde bedrijfsaspecten voor het model om te relateren aan feedbackgegevens zijn onder meer:
-   Accountbeheer
-   Uitchecken en betaling
-   Klantenondersteuning
-   In de winkel ophalen
-   Verzending en ophalen van verpakking
-   Vooraf bestellen
-   Prijs
-   Privacy en beveiliging
-   Promotie en beloningen
-   Betalingsbewijs en garantie
-   Omruilen en annuleren
-   Nauwkeurigheid van afhandeling
-   Website-/app-kwaliteit

> [!NOTE]
> Momenteel ondersteunen we alleen gevoelsanalyse op Engelse feedback van klanten. In de toekomst zullen meer talen worden ondersteund. Als feedback in andere talen wordt geüpload, geeft het model nog steeds resultaten. Deze resultaten zullen echter niet nauwkeurig zijn. 

## <a name="prerequisites"></a>Vereisten

Gevoelsanalyse is gebaseerd op tekstfeedbackgegevens die door het [proces voor gegevensharmonisatie](data-unification.md). We raden u sterk aan om vooraf [uw feedbackgegevensentiteiten te configureren als activiteitsentiteiten van het semantische type](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (Feedback-type). 

Om een gevoelsanalysemodel te configureren, hebt u minimaal [Inzender-machtigingen ](permissions.md) nodig.

Customer Insights kan tot 10 miljoen feedbackrecords verwerken voor een enkele modelrun. Het model kan feedbackopmerkingen tot 128 woorden analyseren. Als een feedbackopmerking langer is, houdt de analyse alleen rekening met de eerste 128 woorden.

### <a name="data-requirements"></a>Gegevensvereisten
  
De volgende gegevenskenmerken zijn vereist:
- Unified Customer ID (UCID) om gegevensrecords voor tekstfeedback af te stemmen op een individuele klant. Deze id is het resultaat van het [proces voor gegevensharmonisatie](data-unification.md).
- Feedback-id
- Tijdstempel van feedback
- Feedbacktekst   

> [!TIP]
> Gevoelensanalyse vereist de tekstfeedback van uw klanten. Er kan momenteel slechts één feedbackentiteit worden geconfigureerd. Als er meerdere feedbackentiteiten zijn, kunt u deze samenvoegen in Power Query voordat de gegevensopname begint.

## <a name="configure-a-sentiment-analysis"></a>Een gevoelsanalyse configureren 

1. Ga in Customer Insights naar **Informatie** > **Voorspellingen**.

1. Selecteer op de tegel **Analyse van klantgevoel** de optie **Model gebruiken**.

1. Selecteer in het deelvenster **Analyse van klantgevoel (preview)** de optie **Aan de slag**.

1. Geef in de stap **Modelnaam** een **Naam** op voor uw analyse. 

1. Geef de **Entiteitsnaam voor uitvoer van bedrijfsaspect** en de **Entiteitsnaam voor uitvoer van gevoelsscore** op en selecteer vervolgens **Volgende**.

1. Selecteer in de stap **Vereiste gegevens** de optie **Gegevens toevoegen**.

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Een gegevensstroom toevoegen aan het gevoelsanalysemodel.":::

1. Kies in het deelvenster **Gegevens toevoegen** het semantische type **Feedback** in de lijst.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Configuratiestap om feedbackactiviteiten te selecteren voor gevoelsanalyse.":::

1. Selecteer de activiteiten die u voor deze gevoelsanalyse wilt gebruiken en selecteer vervolgens **Volgende**.
 
1. Wijs de kenmerken in uw gegevens toe aan de modelkenmerken. Selecteer **Opslaan** om uw keuzen toe te passen. 

1. U ziet de status van gegevenstoewijzing. Selecteer **Volgende** om door te gaan. 

1. Valideer in de stap **Uw modelgegevens controleren** de configuratie van uw gevoelsanalyse. U kunt teruggaan naar elk deel van de voorspellingsconfiguratie. Selecteer **Opslaan en uitvoeren** om de analyse te starten. 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Controleer stap voor het gevoelsmodel dat alle geconfigureerde items toont.":::

1. Selecteer **Gereed** om de configuratie-ervaring te verlaten. Het proces kan enkele uren duren, afhankelijk van de hoeveelheid gegevens die wordt gebruikt. 

## <a name="review-analysis-status"></a>Analysestatus controleren

1.  Ga naar **Intelligence** > **Voorspellingen** en selecteer het tabblad **Mijn voorspellingen**.
2.  Selecteer de voorspelling die u wilt beoordelen.
- **Naam voorspelling**: naam van de voorspelling die bij het maken is opgegeven.
- **Type voorspelling**: type model dat is gebruikt voor de voorspelling.
- **Uitvoerentiteit**: naam van de entiteit om de uitvoer van de voorspelling op te slaan. Ga naar **Gegevens** > **Entiteiten** om de entiteit met deze naam te vinden.
- **Veld Voorspeld**: dit veld wordt alleen ingevuld voor bepaalde soorten voorspellingen en wordt niet gebruikt bij de voorspelling van de levensduurwaarde van klanten.
- **Status**: de status of the voorspellingsuitvoering.
  - **In de wachtrij**: voorspelling wacht tot andere processen voltooid zijn.
  - **Vernieuwen**: de voorspelling wordt momenteel uitgevoerd om resultaten te produceren die naar de uitvoerentiteit zullen stromen.
  - **Mislukt**: voorspellingsuitvoering is mislukt. Controleer de logbestanden voor meer informatie.
  - **Geslaagd**: de voorspelling is geslaagd. Selecteer Weergeven onder de verticale ellipsen om de resultaten van de voorspelling te bekijken.
- **Bewerkt**: de datum waarop de configuratie voor de voorspelling is gewijzigd.
- **Laatst vernieuwd**: de datum waarop de voorspelling de resultaten heeft vernieuwd in de uitvoerentiteit.

## <a name="manage-sentiment-analysis"></a>Gevoelsanalyse beheren

U kunt voorspellingen optimaliseren, problemen oplossen met voorspellingen of voorspellingen vernieuwen of verwijderen. Bekijk een bruikbaarheidsrapport voor invoergegevens om erachter te komen hoe u een voorspelling sneller en betrouwbaarder kunt maken. Zie [Voorspellingen beheren](manage-predictions.md) voor meer informatie.

## <a name="review-analysis-results"></a>Analyseresultaten controleren
 
1. Ga naar **Intelligence** > **Voorspellingen** en selecteer het tabblad **Mijn voorspellingen**. 
1. Selecteer de naam van de voorspelling waarvan u de resultaten wilt controleren. Selecteer in dit geval de gevoelsanalyse die u wilt bekijken. 

### <a name="summary-tab"></a>Tabblad Overzicht

Er zijn vier primaire secties met gegevens op de resultatenpagina. 

- **Gemiddelde gevoelstscore**: helpt u het algemene gevoel van alle klanten te begrijpen. Gevoelsscores zijn gegroepeerd in drie categorieën: 
  1.    Negatief (-5 > 2)
  2.    Neutraal (-1 > 1)
  3.    Positief (2 > 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Visuele weergave van het algemene klantgevoel.":::

- **Verdeling van klanten op gevoelsscore**: klanten worden ingedeeld in negatieve, neutrale en positieve groepen op basis van hun gevoelsscores. Plaats de muisaanwijzer op de balken in het histogram om het aantal klanten en de gemiddelde gevoelsscore in elke groep te zien. Deze gegevens kunnen u helpen [segmenten van klanten maken](segments.md) op basis van hun gevoelsscores.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Staafdiagram toont het klantgevoel in alle drie de gevoelsgroepen.":::

- **Gemiddelde gevoelsscore in de loop van de tijd**: klantgevoel kan in de loop van de tijd veranderen. We bieden trends in het gevoel van uw klanten voor het tijdsbereik van uw gegevens. Deze weergave kan u helpen het effect van seizoenspromoties, productlanceringen of andere tijdgebonden interventies op het klantgevoel te meten. Bekijk de grafiek door het gewenste jaar te selecteren in het vervolgkeuzemenu. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Geschiedenisdiagram met de gevoelsscore in de loop van de tijd weergegeven als een lijn.":::
 
- **Gevoel door bedrijfsaspecten heen**: deze tabel geeft een overzicht van het gemiddelde gevoel in alle bedrijfsaspecten. Het kan u helpen te meten welke aspecten van uw bedrijf al klanten tevreden stellen of aspecten die meer aandacht vereisen. Feedbackrecords die niet overeenkomen met een van de ondersteunde bedrijfsaspecten, worden gecategoriseerd onder **Overige**. De tabel is standaard alfabetisch gesorteerd. U kunt de sortering wijzigen door een tabelkop te selecteren.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Lijst met bedrijfsaspecten met de bijbehorende gevoelswaarde en het aantal klanten dat dit vermeldt.":::
 
  Selecteer de naam van een bedrijfsaspect om aanvullende informatie te zien over hoe een bedrijfsaspect door het model wordt geïdentificeerd. Dit deelvenster bestaat uit twee delen: 

  - **Invloedrijke woorden**: toont de belangrijkste woorden die van invloed waren op de identificatie van een bedrijfsaspect door het AI-model in klantfeedback. 
    **Aanstootgevende woorden tonen**: hiermee kunt u aanstootgevende woorden uit de oorspronkelijke feedbackgegevens van klanten in de lijst opnemen. Gewoonlijk is dit uitgeschakeld.  Maskering van aanstootgevende woorden wordt mogelijk gemaakt met een AI-model en detecteert mogelijk niet alle aanstootgevende woorden. We blijven de classificatie herhalen en trainen voor optimale prestaties. Als u een aanstootgevend woord ontdekt dat niet is gefilterd zoals verwacht, laat het ons dan weten. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Lijst met invloedrijke woorden met de schakeloptie om aanstootgevende woorden weer te geven of te verbergen.":::
 
  - **Feedbackvoorbeelden**: toont feitelijke feedbackrecords in uw gegevens. Woorden zijn kleurgecodeerd volgens hun invloed op de identificatie van een bedrijfsaspect. 


### <a name="influential-words-analysis-tab"></a>Tabblad Analyse van invloedrijke woorden

Er zijn drie secties met aanvullende informatie die uitleggen hoe het gevoelsmodel werkt.
  
1. **Topwoorden die bijdragen aan een positief gevoel**: toont de belangrijkste woorden die van invloed zijn geweest op de identificatie van positief gevoel in klantfeedback door het AI-model.  
2. **Topwoorden die bijdragen aan een negatief gevoel**: toont de belangrijkste woorden die van invloed zijn geweest op de identificatie van negatief gevoel in klantfeedback door het AI-model.  
3. **Feedbackvoorbeelden**: toont actuele feedbackrecords, één met een negatief gevoel en één met een positief gevoel. Woorden in de feedbackrecords worden gemarkeerd op basis van hun bijdrage aan de toegewezen gevoelsscore. Woorden die bijdragen aan een positieve gevoelsscore zijn groen gemarkeerd. Woorden die bijdragen aan een negatieve score zijn rood gemarkeerd.
   Selecteer **Meer bekijken** om meer feedbackvoorbeelden te laden die meer informatie en context bieden over hoe het gevoelsmodel werkt.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Voorbeelden van gevoelsanalyse op klantfeedback.":::
 
**Aanstootgevende woorden tonen**: hiermee kunt u aanstootgevende woorden uit de oorspronkelijke feedbackgegevens van klanten in de lijst opnemen. Gewoonlijk is dit uitgeschakeld.  Maskering van aanstootgevende woorden wordt mogelijk gemaakt met een AI-model en detecteert mogelijk niet alle aanstootgevende woorden. We blijven de classificatie herhalen en trainen voor optimale prestaties. Als u een aanstootgevend woord ontdekt dat niet is gefilterd zoals verwacht, laat het ons dan weten. 

## <a name="act-on-analysis-results"></a>Optreden naar aanleiding van analyseresultaten

U kunt eenvoudig beginnen met het maken van nieuwe klantsegmenten vanaf de pagina met resultaten van de gevoelsanalyse door **Segmenten maken** te selecteren boven aan de pagina met modelresultaten.

:::image type="content" source="media/create-segment-model.png" alt-text="Opdrachtbalk met opties op voorspellingsmodellen.":::
 
## <a name="potential-bias"></a>Potentiële vertekening

Zoals met elke functie die kunstmatige intelligentie voor voorspellingen gebruikt, moet u zich bewust zijn van mogelijke vertekening in de gegevens die u gebruikt om het klantgevoel te voorspellen. Als u feedback bijvoorbeeld alleen digitaal verzamelt, kunt u feedback missen van klanten die voornamelijk persoonlijk zaken met u doen, wat van invloed kan zijn op de uitvoer van de functie.

Aangezien deze functie geautomatiseerde middelen gebruikt om gegevens te evalueren en voorspellingen te doen op basis van die gegevens, kan het daarom worden gebruikt als een methode voor profilering, zoals die term is gedefinieerd door de Algemene Verordening Gegevensbescherming (AVG). Uw gebruik van deze functie om gegevens te verwerken, kan onderhevig zijn aan de AVG of andere wet- of regelgeving. U bent ervoor verantwoordelijk dat uw gebruik van Dynamics 365 Customer Insights, inclusief gevoelsanalyse, voldoet aan alle toepasselijke wet- en regelgeving, inclusief wetten met betrekking tot privacy, persoonlijke gegevens, biometrische gegevens, gegevensbescherming en vertrouwelijkheid van communicatie.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

