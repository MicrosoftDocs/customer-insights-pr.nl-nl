---
title: Voorspelling van de levensduurwaarde van klanten
description: Voorspel het inkomstenpotentieel voor actieve klanten in de toekomst.
ms.date: 02/05/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- ci-custom-models
- customerInsights
ms.openlocfilehash: 3e1b1ce00eeda1cead9ba05beae65b6903d0b9cf
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646401"
---
# <a name="customer-lifetime-value-clv-prediction"></a>Voorspelling van de levensduurwaarde van klanten

Voorspel potentiële waarde (inkomsten) die individuele actieve klanten voor uw bedrijf zullen binnenhalen gedurende een bepaalde toekomstige periode. Deze functie kan u helpen verschillende doelen te bereiken: 
- Klanten met hoge waarde identificeren en dit inzicht verwerken
- Maak strategische klantsegmenten op basis van hun potentiële waarde om gepersonaliseerde campagnes uit te voeren met gerichte verkoop-, marketing- en ondersteuningsinspanningen
- Leid productontwikkeling door te focussen op functies die de klantwaarde verhogen
- Optimaliseer de verkoop- of marketingstrategie en wijs het budget nauwkeuriger toe voor klantenbereik
- Erken en beloon klanten met een hoge waarde via loyaliteits- of beloningsprogramma's 

## <a name="prerequisites"></a>Vereisten

Bedenk voordat u begint wat levensduurwaarde van klanten voor uw bedrijf betekent. Momenteel ondersteunen we op transacties gebaseerde voorspellingen van de levensduurwaarde van klanten. De voorspelde waarde van een klant is gebaseerd op de geschiedenis van zakelijke transacties. Om de voorspelling te maken, hebt u minstens [Inzender](permissions.md)-machtigingen nodig.

Aangezien het configureren en uitvoeren van een model voor levensduurwaarde van klanten niet veel tijd kost, kunt u overwegen om verschillende modellen met verschillende invoervoorkeuren te maken en modelresultaten te vergelijken om te zien welk modelscenario het best bij uw bedrijfsbehoeften past.

###  <a name="data-requirements"></a>Gegevensvereisten

De volgende gegevens zijn vereist en worden, indien gemarkeerd als optioneel, aanbevolen voor betere modelprestaties. Hoe meer gegevens het model kan verwerken, hoe nauwkeuriger de voorspelling zal zijn. Daarom raden we u aan meer gegevens over klantactiviteit op te nemen, indien beschikbaar.

- Klant-id: unieke identificatie om transacties aan een individuele klant te koppelen

- Transactiegeschiedenis: historisch transactielogboek met onderstaand semantisch gegevensschema
    - **Transactie-id**: unieke id van elke transactie
    - **Transactiedatum**: datum, bij voorkeur een tijdstempel van elke transactie
    - **Transactiebedrag**: geldwaarde (bijvoorbeeld omzet of winstmarge) van elke transactie
    - **Label toegewezen aan retouren** (optioneel): Booleaanse waarde die aangeeft of de transactie een retour is 
    - **Product-id** (optioneel): product-id van het product dat bij de transactie is betrokken

- Aanvullende gegevens (optioneel), bijvoorbeeld
    - Webactiviteiten: geschiedenis van websitebezoek, e-mailgeschiedenis
    - Loyaliteitsactiviteiten: opbouw van loyaliteitsbeloningspunten en inwisselgeschiedenis
    - Klantenservicelogboek, serviceoproep, klacht of retourgeschiedenis
- Gegevens over klantactiviteiten (optioneel):
    - Activiteits-id's om activiteiten van hetzelfde type te onderscheiden
    - Klant-id's om activiteiten te koppelen aan uw klanten
    - Activiteitsinformatie met de naam en datum van de activiteit
    - Het semantische gegevensschema voor activiteiten omvat: 
        - **Primaire sleutel:** een unieke id voor een activiteit.
        - **Tijdstempel:** de datum en tijd van de gebeurtenis die wordt geïdentificeerd door de primaire sleutel.
        - **Gebeurtenis (activiteitnaam)**: de naam van de gebeurtenis die u wilt gebruiken
        - **Details (bedrag of waarde)**: details over de klantactiviteit

- Voorgestelde gegevenskenmerken:
    - Voldoende historische gegevens: transactiegegevens van minimaal één jaar. Bij voorkeur twee tot drie jaar transactiegegevens om CLV voor één jaar te voorspellen.
    - Meerdere aankopen per klant: idealiter ten minste twee tot drie transacties per klant-id, bij voorkeur op meerdere datums.
    - Aantal klanten: minimaal 100 unieke klanten, bij voorkeur meer dan 10.000 klanten. Het model mislukt bij minder dan 100 klanten en onvoldoende historische gegevens
    - Compleetheid van gegevens: minder dan 20% ontbrekende waarden in verplichte velden in de invoergegevens   

> [!NOTE]
> - Het model vereist de transactiegeschiedenis van uw klanten. Er kan momenteel slechts één transactiehistorie-entiteit worden geconfigureerd. Als er meerdere aankoop-/transactie-entiteiten zijn, kunt u deze samenvoegen in Power Query vóór de gegevensopname.
> - Voor aanvullende klantactiviteitsgegevens (optioneel) kunt u echter zoveel klantactiviteitsentiteiten toevoegen als u wilt om in aanmerking te komen voor het model.

## <a name="create-a-customer-lifetime-value-prediction"></a>Een voorspelling over de levensduurwaarde van een klant maken

1. Ga naar **Informatie** > **Voorspellingen**.

1. Selecteer de tegel **Levensduurwaarde van klanten** en selecteer **Model gebruiken**. 

1. Selecteer in het deelvenster **Levensduurwaarde van klant** de optie **Aan de slag**.

1. **Geef dit model een naam** en de **Naam van uitvoerentiteit** om ze te onderscheiden van andere modellen of entiteiten.

1. Selecteer **Volgende**.

### <a name="define-model-preferences"></a>Modelvoorkeuren definiëren

1. Stel een **Tijdsperiode voor voorspelling** om te bepalen hoe ver in de toekomst u de levensduurwaarde van de klant wilt voorspellen.    
   Standaard is de eenheid ingesteld op maanden. U kunt het wijzigen in jaren om verder in de toekomst te kijken.

   > [!TIP]
   > Om de levensduurwaarde van een klant nauwkeurig te voorspellen voor de tijdsperiode die u instelt, hebt u een vergelijkbare periode met historische gegevens nodig. Als u bijvoorbeeld CLV wilt voorspellen voor de komende 12 maanden, is het raadzaam ten minste 18-24 maanden aan historische gegevens te hebben.

1. Geef op wat **Actieve klanten** betekenen voor uw bedrijf. Stel het tijdsbestek in waarin een klant ten minste één transactie moet hebben gedaan om als actief te worden beschouwd. Het model voorspelt alleen levensduurwaarde voor actieve klanten. 
   - **Het aankoopinterval laten berekenen door het model (aanbevolen)**: het model analyseert uw gegevens en bepaalt een tijdsperiode op basis van historische aankopen.
   - **Interval handmatig instellen**: als u een specifieke zakelijke definitie van een actieve klant hebt, kiest u deze optie en stelt u de tijdsperiode dienovereenkomstig in.

1. Definieer percentiel van **Hoogwaardige klant** om ervoor te zorgen dat het model resultaten oplevert die passen bij uw bedrijfsdefinitie.
    - **Modelberekening (aanbevolen)**: het model analyseert uw gegevens en bepaalt wat een hoogwaardige klant voor uw bedrijf kan zijn op basis van de transactiegeschiedenis van uw klanten. Het model gebruikt een heuristische regel (geïnspireerd door de 80/20-regel of het pareto-principe) om het aandeel hoogwaardige klanten te vinden. Het percentage klanten dat in de historische periode heeft bijgedragen aan 80% cumulatieve omzet voor uw bedrijf, wordt beschouwd als klanten met een hoge waarde. Doorgaans dragen minder dan 30-40% klanten bij aan 80% cumulatieve omzet. Dit aantal kan echter variëren, afhankelijk van uw bedrijf en branche.    
    - **Percentage actiefste klanten**: definieer hoogwaardige klanten voor uw bedrijf als een percentiel van de actiefste betalende klanten. U kunt deze optie bijvoorbeeld gebruiken om hoogwaardige klanten te definiëren als top 20% van toekomstige betalende klanten.

    Als uw bedrijf hoogwaardige klanten op een andere manier definieert, [laat het ons weten, we horen het graag](https://go.microsoft.com/fwlink/?linkid=2074172)​.

1. Klik op **Volgende** om door te gaan naar de volgende stap.

### <a name="add-required-data"></a>Vereiste gegevens toevoegen

1. Selecteer in de stap **Vereiste gegevens** de optie **Gegevens toevoegen** voor **Transactiegeschiedenis van klant** en kies de entiteit die de transactiegeschiedenisinformatie verstrekt, zoals beschreven in de [vereisten](#prerequisites).

1. Wijs de semantische velden toe aan kenmerken binnen uw aankoopgeschiedenis-entiteit en selecteer **Volgende**.

   :::image type="content" source="media/clv-add-customer-data-mapping.png" alt-text="Afbeelding van de configuratiestap om gegevenskenmerken voor de vereiste gegevens in kaart te brengen.":::
 
1. Als de onderstaande velden niet zijn ingevuld, configureert u de relatie tussen uw aankoopgeschiedenisentiteit en de entiteit *Klant* en selecteert u **Opslaan**.
    1. Selecteer de entiteit Transactiegeschiedenis.
    1. Selecteer het veld dat een klant identificeert in de entiteit Aankoopgeschiedenis. Het moet betrekking hebben op de primaire klant-id van uw entiteit Klant.
    1. Selecteer de entiteit die overeenkomt met uw primaire klantentiteit.
    1. Voer een naam in waarmee de relatie wordt omschreven.

      :::image type="content" source="media/clv-add-customer-data-relationship.png" alt-text="Afbeelding van de configuratiestap om de relatie met de klantentiteit te definiëren.":::

1. Selecteer **Volgende**.

### <a name="add-optional-data"></a>Optionele gegevens toevoegen

Gegevens die belangrijke klantinteracties weerspiegelen (zoals web, klantenservice en gebeurtenislogboeken) voegen context toe aan transactierecords. Meer patronen die in de gegevens van uw klantactiviteit worden gevonden, kunnen de nauwkeurigheid van de voorspellingen verbeteren. 

1. Selecteer in de stap **Aanvullende gegevens (optioneel)** de optie **Gegevens toevoegen**​. Kies de entiteit voor klantactiviteit die de informatie over de klantactiviteit verstrekt, zoals beschreven in de [vereisten](#prerequisites).

1. Wijs de semantische velden toe aan kenmerken binnen de entiteit Klantactiviteiten en selecteer **Volgende**.

   :::image type="content" source="media/clv-additional-data-mapping.png" alt-text="Afbeelding van de configuratiestap om velden voor aanvullende gegevens in kaart te brengen.":::

1. Selecteer een activiteitstype dat overeenkomt met het type klantactiviteit dat u toevoegt. Kies uit bestaande activiteitstypen of voeg een nieuw activiteitstype toe.

1. Configureer de relatie van uw klantactiviteitentiteit met de entiteit *Klant*.
    
    1. Selecteer het veld dat de klant identificeert in de tabel Klantactiviteiten. Het kan rechtstreeks verband houden met de primaire klant-id van de entiteit *Klant*.
    1. Selecteer de entiteit *Klant* die overeenkomt met uw primaire entiteit *Klant*.
    1. Voer een naam in waarmee de relatie wordt omschreven.

   :::image type="content" source="media/clv-additional-data.png" alt-text="Afbeelding van de stap in de configuratiestroom om extra gegevens toe te voegen en de activiteit te configureren met ingevulde voorbeelden.":::

1. Selecteer **Opslaan**.    
    Voeg meer gegevens toe als er andere klantactiviteiten zijn die u wilt opnemen.

1. Selecteer **Volgende**.

### <a name="set-update-schedule"></a>Updateplanning instellen

1. Kies in de stap **Planning voor gegevensupdate** de frequentie om uw model opnieuw te trainen op basis van de nieuwste gegevens. Deze instelling is belangrijk om de nauwkeurigheid van voorspellingen bij te werken wanneer nieuwe gegevens worden opgenomen in Customer Insights. De meeste bedrijven kunnen eenmaal per maand opnieuw trainen en krijgen een goede nauwkeurigheid voor hun voorspelling.

1. Selecteer **Volgende**.

### <a name="review-and-run-the-model-configuration"></a>De modelconfiguratie controleren en uitvoeren

1. In de stap **Uw modelgegevens controleren** valideert u de configuratie van de voorspelling. U kunt teruggaan naar elk willekeurig deel van de voorspellingsconfiguratie door **Bewerken** te selecteren onder de weergegeven waarde. U kunt ook een configuratiestap selecteren via de voortgangsindicator.

1. Als alle waarden correct zijn geconfigureerd, selecteert u **Opslaan en uitvoeren** om het model uit te voeren. Op het tabblad **Mijn voorspellingen** kunt u de status van het voorspellingsproces zien. Het proces kan enkele uren in beslag nemen, afhankelijk van de hoeveelheid gegevens die in de voorspelling is gebruikt.

## <a name="review-prediction-status-and-results"></a>De status en resultaten van de voorspelling controleren

### <a name="review-prediction-status"></a>Status van de voorspelling controleren

1.  Ga naar **Intelligence** > **Voorspellingen** en selecteer het tabblad **Mijn voorspellingen**.
2.  Selecteer de voorspelling die u wilt beoordelen.

- **Naam voorspelling**: naam van de voorspelling die bij het maken is opgegeven.
- **Type voorspelling**: type model dat is gebruikt voor de voorspelling
- **Uitvoerentiteit**: naam van de entiteit om de uitvoer van de voorspelling op te slaan. Ga naar **Gegevens** > **Entiteiten** om de entiteit met deze naam te vinden.
- **Veld Voorspeld**: dit veld wordt alleen ingevuld voor bepaalde soorten voorspellingen en wordt niet gebruikt bij de voorspelling van de levensduurwaarde van klanten.
- **Status**: de status of the voorspellingsuitvoering.
    - **In de wachtrij**: voorspelling wacht tot andere processen voltooid zijn.
    - **Vernieuwen**: de voorspelling wordt momenteel uitgevoerd om resultaten te produceren die naar de uitvoerentiteit zullen stromen.
    - **Mislukt**: voorspellingsuitvoering is mislukt. [Controleer de logbestanden](manage-predictions.md#troubleshoot-a-failed-prediction) voor meer informatie.
    - **Geslaagd**: de voorspelling is geslaagd. Selecteer **Weergeven** onder de verticale ellipsen om de resultaten van de voorspelling te bekijken.
- **Bewerkt**: de datum waarop de configuratie voor de voorspelling is gewijzigd.
- **Laatst vernieuwd**: de datum waarop de voorspelling is vernieuwd resulteert in de uitvoerentiteit.

### <a name="review-prediction-results"></a>Resultaten van de voorspelling controleren

1. Ga naar **Intelligence** > **Voorspellingen** en selecteer het tabblad **Mijn voorspellingen**.

1. Selecteer de voorspelling waarvoor u de resultaten wilt bekijken.

Er zijn drie primaire gegevenssecties op de resultatenpagina.

- **Prestaties van trainingsmodel**: A, B of C zijn mogelijke cijfers. Dit cijfer geeft de prestaties van de voorspelling aan en kan u helpen bij het nemen van de beslissing om de resultaten te gebruiken die zijn opgeslagen in de uitvoerentiteit. Selecteer **Meer informatie over deze score** om de onderliggende prestatiecijfers van het model beter te begrijpen en hoe het uiteindelijke prestatiecijfer van het model is afgeleid.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Afbeelding van het modelscore-informatievenster met het cijfer A.":::

  Aan de hand van de definitie van hoogwaardige klanten die bij het configureren van de voorspelling is verstrekt, beoordeelt het systeem hoe het AI-model presteert bij het voorspellen van de hoogwaardige klanten in vergelijking met een basismodel.    

  Cijfers worden bepaald op basis van de volgende regels:
  - **A** wanneer het model ten minste 5% meer hoogwaardige klanten nauwkeurig voorspelde in vergelijking met het basismodel.
  - **B** wanneer het model 0-5% meer hoogwaardige klanten nauwkeurig voorspelde in vergelijking met het basismodel.
  - **C** wanneer het model minder hoogwaardige klanten nauwkeurig voorspelde in vergelijking met het basismodel.

  In het deelvenster **Modelbeoordeling** worden meer details weergegeven over de prestaties van het AI-model en het basismodel. Het basismodel maakt gebruik van een niet op AI gebaseerde benadering om de levensduurwaarde van de klant te berekenen, voornamelijk op basis van historische aankopen door klanten.     
  De standaardformule die wordt gebruikt om de levensduurwaarden van klanten te berekenen door het basismodel:    

  _**Levensduurwaarde voor elke klant** = gemiddelde maandelijkse aankoop door de klant in het actieve klantenvenster * Aantal maanden in de voorspellingsperiode voor levensduurwaarde van klanten * Algeheel behoudpercentage van alle klanten*_

  Het AI-model wordt vergeleken met het basismodel op basis van twee modelprestatiestatistieken.
  
  - **Succespercentage bij het voorspellen van klanten met een hoge waarde**

    Zie het verschil in het voorspellen van hoogwaardige klanten met behulp van het AI-model in vergelijking met het basismodel. Het slagingspercentage van 84% betekent bijvoorbeeld dat van alle hoogwaardige klanten in de trainingsgegevens het AI-model 84% nauwkeurig kon vastleggen. We vergelijken dit slagingspercentage vervolgens met het slagingspercentage van het basismodel om de relatieve verandering te rapporteren. Deze waarde wordt gebruikt om een cijfer aan het model toe te kennen.

  - **Foutstatistieken**
    
    Met een andere statistiek kunt u de algehele prestaties van het model beoordelen in termen van fouten bij het voorspellen van toekomstige waarden. We gebruiken de algemene statistiek kwadratisch gemiddelde fout om deze fout te beoordelen. Kwadratisch gemiddelde fout is een standaardmanier om de fout van een model te meten bij het voorspellen van kwantitatieve gegevens. De kwadratisch gemiddelde fout van het AI-model wordt vergeleken met de kwadratisch gemiddelde fout van het basismodel en het relatieve verschil wordt gerapporteerd.

  Het AI-model geeft prioriteit aan de nauwkeurige rangschikking van klanten op basis van de waarde die ze voor uw bedrijf opleveren. Dus alleen het slagingspercentage van het voorspellen van hoogwaardige klanten wordt gebruikt om het uiteindelijke modelcijfer af te leiden. De kwadratisch gemiddelde fout-statistiek is gevoelig voor uitschieters. In scenario's waarin u een klein percentage klanten hebt met buitengewoon hoge aankoopwaarden, geeft de algehele kwadratisch gemiddelde fout-statistiek mogelijk niet het volledige beeld van de modelprestaties.   

- **Waarde van klanten per percentiel**: op basis van uw definitie van hoogwaardige klanten, worden klanten gegroepeerd in lage en hoge waarde, op basis van hun voorspellingen voor de levensduurwaarde van klanten en weergegeven in een grafiek. Door over de balken in het histogram te bewegen, kunt u het aantal klanten in elke groep en de gemiddelde levensduurwaarde van klanten van die groep zien. Deze gegevens kunnen helpen als u [segmenten van klanten wilt maken](segments.md) op basis van hun voorspellingen voor de levensduurwaarde van klanten.

- **Meest invloedrijke factoren**: er worden verschillende factoren in overweging genomen bij het maken van uw voorspelling voor de levensduurwaarde van klanten op basis van de invoergegevens die aan het AI-model worden verstrekt. Voor elk van de factoren wordt het belang berekend bij de geaggregeerde voorspellingen die een model opstelt. U kunt deze factoren gebruiken om uw voorspellingsresultaten te valideren. Deze factoren geven ook meer inzicht in de meest invloedrijke factoren die hebben bijgedragen aan het voorspellen van de levensduurwaarde voor al uw klanten.

## <a name="manage-predictions"></a>Voorspellingen beheren

Het is mogelijk om voorspellingen te optimaliseren, problemen op te lossen, voorspellingen te vernieuwen of deze te verwijderen. Bekijk een bruikbaarheidsrapport voor invoergegevens om erachter te komen hoe u een voorspelling sneller en betrouwbaarder kunt maken. Zie [Voorspellingen beheren](manage-predictions.md) voor meer informatie.

[!INCLUDE [footer-include](includes/footer-banner.md)]
