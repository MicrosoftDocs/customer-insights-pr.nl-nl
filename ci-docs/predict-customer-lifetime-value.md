---
title: Levensduurwaarde van klant voorspellen
description: Voorspel het inkomstenpotentieel voor actieve klanten in de toekomst.
ms.date: 09/30/2022
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
ms.openlocfilehash: f27462ac327027e50e23387ac9f75a671db9a86d
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610368"
---
# <a name="predict-customer-lifetime-value-clv"></a>Levensduurwaarde van klant voorspellen

Voorspel potentiële waarde (inkomsten) die individuele actieve klanten voor uw bedrijf zullen binnenhalen gedurende een bepaalde toekomstige periode. Deze voorspelling helpt u bij het volgende:

- Klanten met hoge waarde identificeren en dit inzicht verwerken.
- Maak strategische klantsegmenten op basis van hun potentiële waarde om gepersonaliseerde campagnes uit te voeren met gerichte verkoop-, marketing- en ondersteuningsinspanningen.
- Leid productontwikkeling door te focussen op functies die de klantwaarde verhogen.
- De verkoop- of marketingstrategie optimaliseren en het budget nauwkeuriger toewijzen voor klantenbereik.
- Klanten met een hoge waarde erkennen en belonen via loyaliteits- of beloningsprogramma's.

Bepalen wat CLV voor uw bedrijf betekent. Wij ondersteunen op transacties gebaseerde voorspellingen van de levensduurwaarde van klanten. De voorspelde waarde van een klant is gebaseerd op de geschiedenis van zakelijke transacties. Overweeg om verschillende modellen met verschillende invoervoorkeuren te maken en modelresultaten te vergelijken om te zien welk modelscenario het best bij uw bedrijfsbehoeften past.

> [!TIP]
> Probeer de CLV voorspelling uit met voorbeeldgegevens: [Voorbeeldgids voor voorspelling van de levensduurwaarde van klanten (CLV)](sample-guide-predict-clv.md).

## <a name="prerequisites"></a>Vereisten

- Minimaal [Inzendermachtigingen](permissions.md)
- Minimaal 100 unieke klanten, bij voorkeur meer dan 10.000 klanten
- Klant-id. Dit is een unieke id om transacties aan een individuele klant te koppelen
- Minimaal één jaar aan transactiegeschiedenis, bij voorkeur twee tot drie jaar. Idealiter ten minste twee tot drie transacties per klant-id, bij voorkeur op meerdere datums. De transactiegeschiedenis moet het volgende bevatten:
  - **Transactie-id**: unieke id van elke transactie
  - **Transactiedatum**: datum of een tijdstempel van elke transactie
  - **Transactiebedrag**: geldwaarde (bijvoorbeeld omzet of winstmarge) van elke transactie
  - **Label toegewezen aan retouren**: Booleaanse waarde (waar/onwaar) die aangeeft of de transactie een retour is
  - **Product-id**: product-id van product dat bij de transactie is betrokken
- Gegevens over klantactiviteiten:
  - **Primaire sleutel**: unieke id voor een activiteit
  - **Tijdstempel**: datum en tijd van de gebeurtenis die wordt geïdentificeerd door de primaire sleutel
  - **Gebeurtenis (activiteitnaam)**: naam van gebeurtenis die u wilt gebruiken
  - **Details (bedrag of waarde)**: details over de klantactiviteit
- Aanvullende gegevens zoals:
  - Webactiviteiten: geschiedenis van websitebezoek of e-mailgeschiedenis
  - Loyaliteitsactiviteiten: opbouw van loyaliteitsbeloningspunten en inwisselgeschiedenis
  - Klantenservicelogboek: serviceoproep, klacht of retourgeschiedenis
  - Klantprofielgegevens
- Minder dan 20% ontbrekende waarden in vereiste velden

> [!NOTE]
> Er kan slechts één transactiegeschiedenisentiteit worden geconfigureerd. Als er meerdere aankoop- of transactie-entiteiten zijn, combineert u deze in Power Query vóór de gegevensopname.

## <a name="create-a-customer-lifetime-value-prediction"></a>Een voorspelling over de levensduurwaarde van een klant maken

Selecteer **Concept opslaan** op elk gewenst moment om de voorspelling als concept op te slaan. De conceptvoorspelling wordt weergegeven op het tabblad **Mijn voorspellingen**.

1. Ga naar **Informatie** > **Voorspellingen**.

1. Selecteer op het tabblad **Maken** de optie **Model gebruiken** op de tegel **Levensduurwaarde van klant**.

1. Selecteer **Aan de slag**.

1. **Geef dit model een naam** en de **Naam van uitvoerentiteit** om ze te onderscheiden van andere modellen of entiteiten.

1. Selecteer **Volgende**.

### <a name="define-model-preferences"></a>Modelvoorkeuren definiëren

1. Stel een **Tijdsperiode voor voorspelling** om te bepalen hoe ver in de toekomst u de levensduurwaarde van de klant wilt voorspellen. Standaard is de eenheid ingesteld op maanden.

   > [!TIP]
   > Als u de levensduurwaarde van een klant nauwkeurig wilt voorspellen voor de tijdsperiode die u instelt, is een vergelijkbare periode met historische gegevens vereist. Als u bijvoorbeeld CLV wilt voorspellen voor de komende 12 maanden, moet u over ten minste 18-24 maanden aan historische gegevens beschikken.

1. Stel het tijdsbestek in waarin een klant ten minste één transactie moet hebben gedaan om als actief te worden beschouwd. Het model voorspelt alleen de levensduurwaarde voor **actieve klanten**.
   - **Het aankoopinterval laten berekenen door het model (aanbevolen)**: model analyseert uw gegevens en bepaalt een tijdsperiode op basis van historische aankopen.
   - **Interval handmatig instellen**: tijdsperiode voor uw definitie van een actieve klant.

1. Definieer het percentiel van **Klant met hoge waarde**.
    - **Modelberekening (aanbevolen)**: model gebruikt 80/20-regel. Het percentage klanten dat in de historische periode heeft bijgedragen aan 80% cumulatieve omzet voor uw bedrijf, wordt beschouwd als klanten met een hoge waarde. Doorgaans dragen minder dan 30-40% klanten bij aan 80% cumulatieve omzet. Dit aantal kan echter variëren, afhankelijk van uw bedrijf en branche.
    - **Percentage van meest actieve klanten**: specifiek percentiel voor een klant met hoge waarde. Voer bijvoorbeeld **25** in om klanten met hoge waarde te definiëren als top 25% van toekomstige betalende klanten.

    Als uw bedrijf hoogwaardige klanten op een andere manier definieert, [laat het ons weten, we horen het graag](https://go.microsoft.com/fwlink/?linkid=2074172)​.

1. Selecteer **Volgende**.

### <a name="add-required-data"></a>Vereiste gegevens toevoegen

1. Selecteer **Gegevens toevoegen** bij **Transactiegeschiedenis van de klant**.

1. Selecteer het semantische activiteitstype, **SalesOrder** of **SalesOrderLine**, dat de vereiste transactie- of aankoopgeschiedenisgegevens bevat. Als de activiteit niet is ingesteld, selecteert u **hier** en maakt u deze.

1. Kies onder **Activiteiten**, als de activiteitskenmerken semantisch zijn toegewezen bij het maken van de activiteit, de specifieke kenmerken of entiteit waarop u de berekening wilt richten. Als er geen semantische toewijzing heeft plaatsgevonden, selecteert u **Bewerken** en wijst u uw gegevens toe.
  
   :::image type="content" source="media/CLV-add-required.PNG" alt-text="Vereiste gegevens toevoegen voor CLV-model":::

1. Selecteer **Volgende** en bekijk de kenmerken die vereist zijn voor dit model.

1. Selecteer **Save**.

1. Voeg meer activiteiten toe of selecteer **Volgende**.

### <a name="add-optional-activity-data"></a>Optionele activiteitsgegevens toevoegen

Gegevens die belangrijke klantinteracties weerspiegelen (zoals web, klantenservice en gebeurtenislogboeken) voegen context toe aan transactierecords. Meer patronen die in de gegevens van uw klantactiviteit worden gevonden, kunnen de nauwkeurigheid van de voorspellingen verbeteren.

1. Selecteer **Gegevens toevoegen** onder **Modelinzichten verbeteren met aanvullende activiteitsgegevens**.

1. Selecteer een activiteitstype dat overeenkomt met het type klantactiviteit dat u toevoegt. Als de activiteit niet is ingesteld, selecteert u **hier** en maakt u deze.

1. Kies onder **Activiteiten**, als de activiteitskenmerken zijn toegewezen bij het maken van de activiteit, de specifieke kenmerken of entiteit waarop u de berekening wilt richten. Als er geen toewijzing heeft plaatsgevonden, selecteert u **Bewerken** en wijst u uw gegevens toe.

1. Selecteer **Volgende** en bekijk de kenmerken die vereist zijn voor dit model.

1. Selecteer **Save**.

1. Selecteer **Volgende**.

1. [Voeg optionele klantgegevens toe](#add-optional-customer-data) of selecteer **Volgende** en ga naar [Updateplanning instellen](#set-update-schedule).

### <a name="add-optional-customer-data"></a>Optionele klantgegevens toevoegen

Kies uit 18 veelgebruikte klantprofielkenmerken om als invoer voor het model op te nemen. Deze kenmerken kunnen leiden tot meer gepersonaliseerde, relevante en bruikbare modelresultaten voor uw zakelijke gebruiksscenario's.

Bijvoorbeeld: Contoso Coffee wil de levensduurwaarde van de klant voorspellen om klanten met een hoge waarde te benaderen met een gepersonaliseerd aanbod met betrekking tot de lancering van hun nieuwe espressomachine. Contoso gebruikt het CLV-model en voegt alle 18 kenmerken van klantprofielen toe om te zien welke factoren van invloed zijn op hun klanten met de hoogste waarde. Ze vinden dat de locatie van de klant de meest invloedrijke factor is voor deze klanten.
Met deze informatie organiseren ze een lokaal evenement voor de lancering van de espressomachine en werken ze samen met lokale verkopers voor gepersonaliseerde aanbiedingen en een speciale ervaring tijdens het evenement. Zonder deze informatie zou Contoso mogelijk alleen generieke marketing-e-mails hebben verzonden en zo de kans gemist hebben om te personaliseren voor dit lokale segment van hun klanten met een hoge waarde.

1. Selecteer **Gegevens toevoegen** onder **Modelinzichten nog verder verbeteren met aanvullende klantgegevens**.

1. Kies voor **Entiteit** de optie **Klant: CustomerInsights** om het geharmoniseerde klantprofiel te selecteren dat is toegewezen aan kenmerkgegevens voor klanten. Kies voor **Klant-id** **System.Customer.CustomerId**.

1. Wijs meer velden toe als de gegevens beschikbaar zijn in uw geharmoniseerde klantprofielen.

   :::image type="content" source="media/clv-optional-customer-profile-mapping.png" alt-text="Voorbeeld van toegewezen velden voor klantprofielgegevens.":::

1. Selecteer **Save**.

1. Selecteer **Volgende**.

### <a name="set-update-schedule"></a>Updateplanning instellen

1. Kies de frequentie om uw model opnieuw te trainen op basis van de nieuwste gegevens. Deze instelling is belangrijk om de nauwkeurigheid van voorspellingen bij te werken wanneer nieuwe gegevens worden opgenomen in Customer Insights. De meeste bedrijven kunnen eenmaal per maand opnieuw trainen en krijgen een goede nauwkeurigheid voor hun voorspelling.

1. Selecteer **Volgende**.

### <a name="review-and-run-the-model-configuration"></a>De modelconfiguratie controleren en uitvoeren

De stap **Controleren en uitvoeren** toont een samenvatting van de configuratie en biedt een kans om wijzigingen aan te brengen voordat u de voorspelling maakt.

1. Selecteer **Bewerken** in een van de stappen om te controleren en eventuele wijzigingen aan te brengen.

1. Als u tevereden bent over uw selecties, selecteert u **Opslaan en uitvoeren** om te beginnen met het uitvoeren van het model. Selecteer **Gereed**. Het tabblad **Mijn voorspellingen** wordt weergegeven terwijl de voorspelling wordt gemaakt. Het proces kan enkele uren in beslag nemen, afhankelijk van de hoeveelheid gegevens die in de voorspelling is gebruikt.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Resultaten van voorspelling weergeven

1. Ga naar **Informatie** > **Voorspellingen**.

1. Selecteer op het tabblad **Mijn voorspellingen** de voorspelling die u wilt weergeven.

Er zijn drie primaire gegevenssecties op de resultatenpagina.

- **Prestaties trainingsmodel**: beoordelingscijfers A, B of C geven de prestaties van de voorspelling aan en kan u helpen bij het nemen van de beslissing om de resultaten te gebruiken die zijn opgeslagen in de uitvoerentiteit.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Afbeelding van het modelscore-informatievenster met het cijfer A.":::

  Customer Insights beoordeelt hoe het AI-model heeft gepresteerd bij het voorspellen van de klanten met hoge waarde in vergelijking met een basismodel.

  Cijfers worden bepaald op basis van de volgende regels:
  - **A** wanneer het model ten minste 5% meer hoogwaardige klanten nauwkeurig voorspelde in vergelijking met het basismodel.
  - **B** wanneer het model 0-5% meer hoogwaardige klanten nauwkeurig voorspelde in vergelijking met het basismodel.
  - **C** wanneer het model minder hoogwaardige klanten nauwkeurig voorspelde in vergelijking met het basismodel.
  
  Selecteer [**Meer informatie over deze score**](#learn-about-the-score) om het deelvenster **Modelbeoordeling** te openen waarin nadere details worden weergegeven over de prestaties van het AI-model en het basismodel. Dit zal u helpen de onderliggende prestatiecijfers van het model beter te begrijpen en inzicht te krijgen in hoe het uiteindelijke prestatiecijfer van het model is afgeleid. Het basismodel maakt gebruik van een niet op AI gebaseerde benadering om de levensduurwaarde van de klant te berekenen, voornamelijk op basis van historische aankopen door klanten.

- **Waarde van klanten per percentiel**: klanten met een lage en een hoge waarde worden weergegeven in een grafiek. Beweeg over de balken in het histogram om het aantal klanten in elke groep en de gemiddelde levensduurwaarde van klanten van die groep te bekijken. Desgewenst kunt u [segmenten van klanten maken](prediction-based-segment.md) op basis van hun voorspellingen voor hun levensduurwaarde.
  
   :::image type="content" source="media/CLV-value-percent.png" alt-text="Waarde van klanten per percentiel voor model voor levensduurwaarde":::

- **Meest invloedrijke factoren**: er worden verschillende factoren in overweging genomen bij het maken van uw voorspelling voor de levensduurwaarde van klanten op basis van de invoergegevens die aan het AI-model worden verstrekt. Voor elk van de factoren wordt het belang berekend bij de geaggregeerde voorspellingen die een model opstelt. Gebruik deze factoren om uw voorspellingsresultaten te helpen valideren. Deze factoren geven ook meer inzicht in de meest invloedrijke factoren die hebben bijgedragen aan het voorspellen van de levensduurwaarde voor al uw klanten.
  
   :::image type="content" source="media/CLV-influence-factors.png" alt-text="Meest invloedrijke factoren voor model voor levensduurwaarde.":::

### <a name="learn-about-the-score"></a>Meer informatie over de score

De standaardformule die wordt gebruikt om de levensduurwaarden van klanten te berekenen door het basismodel:

 _**Levensduurwaarde voor elke klant** = gemiddelde maandelijkse aankoop door de klant in het actieve klantenvenster * Aantal maanden in de voorspellingsperiode voor levensduurwaarde van klanten * Algeheel behoudpercentage van alle klanten_

Het AI-model wordt vergeleken met het basismodel op basis van twee modelprestatiestatistieken.
  
- **Succespercentage bij het voorspellen van klanten met een hoge waarde**

  Zie het verschil in het voorspellen van hoogwaardige klanten met behulp van het AI-model in vergelijking met het basismodel. Het slagingspercentage van 84% betekent bijvoorbeeld dat van alle hoogwaardige klanten in de trainingsgegevens het AI-model 84% nauwkeurig kon vastleggen. We vergelijken dit slagingspercentage vervolgens met het slagingspercentage van het basismodel om de relatieve verandering te rapporteren. Deze waarde wordt gebruikt om een cijfer aan het model toe te kennen.

- **Foutstatistieken**

  Beoordeel de algehele prestaties van het model in termen van fouten bij het voorspellen van toekomstige waarden. We gebruiken de algemene statistiek kwadratisch gemiddelde fout om deze fout te beoordelen. Kwadratisch gemiddelde fout is een standaardmanier om de fout van een model te meten bij het voorspellen van kwantitatieve gegevens. De kwadratisch gemiddelde fout van het AI-model wordt vergeleken met de kwadratisch gemiddelde fout van het basismodel en het relatieve verschil wordt gerapporteerd.

Het AI-model geeft prioriteit aan de nauwkeurige rangschikking van klanten op basis van de waarde die ze voor uw bedrijf opleveren. Dus alleen het slagingspercentage van het voorspellen van hoogwaardige klanten wordt gebruikt om het uiteindelijke modelcijfer af te leiden. De kwadratisch gemiddelde fout-statistiek is gevoelig voor uitschieters. In scenario's waarin u een klein percentage klanten hebt met buitengewoon hoge aankoopwaarden, geeft de algehele kwadratisch gemiddelde fout-statistiek mogelijk niet het volledige beeld van de modelprestaties.

[!INCLUDE [footer-include](includes/footer-banner.md)]
