---
title: Productaanbevelingen voorspellen
description: Voorspel de producten die een klant waarschijnlijk zal kopen of gebruiken.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 0057d6796bb60db44d08b58d9e0daaf6e7c90fde
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610276"
---
# <a name="predict-product-recommendations"></a>Productaanbevelingen voorspellen

Het productaanbevelingsmodel maakt sets met voorspellende productaanbevelingen. Aanbevelingen zijn gebaseerd op eerder aankoopgedrag en klanten met vergelijkbare aankooppatronen. Dit model is voor individuele consumenten (B-to-C).

U moet over zakelijke kennis beschikken om verschillende typen producten voor uw bedrijf te begrijpen en te begrijpen hoe uw klanten ermee omgaan. We ondersteunen het aanbevelen van producten die eerder door uw klanten zijn gekocht of aanbevelingen voor nieuwe producten.

Productaanbevelingen kunnen onderhevig zijn aan lokale wet- en regelgeving en verwachtingen van de klant, waarmee het model niet specifiek rekening houdt. Daarom **moet u de aanbevelingen beoordelen voordat u ze aan uw klanten doorgeeft** om ervoor te zorgen dat u voldoet aan alle toepasselijke wet- of regelgeving en de verwachtingen van de klant voor wat u mogelijk aanbeveelt.

De uitvoer van dit model biedt aanbevelingen op basis van het product-id. Uw leveringsmechanisme moet de voorspelde product-id's toewijzen aan de juiste inhoud voor uw klanten om rekening te houden met lokalisatie, afbeeldingsinhoud en andere bedrijfsspecifieke inhoud of gedragingen.

> [!TIP]
> Probeer het voorspellen van productaanbevelingen uit aan de hand van voorbeeldgegevens: [Voorbeeldhandleiding voor voorspellen van productaanbevelingen](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Vereisten

- Minimaal [Inzendermachtigingen](permissions.md)
- Minimaal 100 klanten, bij voorkeur meer dan 10.000 klanten.
- Klant-id. Dit is een unieke id om transacties aan een individuele klant te koppelen
- Minimaal één jaar aan transactiegegevens, bij voorkeur twee tot drie jaar om enige seizoensinvloeden op te nemen. Idealiter minimaal drie of meer transacties per klant-id. De transactiegeschiedenis moet het volgende bevatten:
  - **Transactie-id**: unieke identificatie van een aankoop of transactie.
  - **Transactiedatum**: datum van de aankoop of de transactie.
  - **Waarde van de transactie**: numerieke waarde van de aankoop of de transactie.
  - **Unieke product-id**: id van het gekochte product of de gekochte service als uw gegevens zich op regelitemniveau bevinden.
  - **Aankoop of retour**: een Booleaans veld (waar/onwaar) waarin de waarde *waar* aangeeft dat een transactie een retour was. Als de gegevens voor aankoop of retour niet zijn opgegeven in het model en de **waarde van de transactie** negatief is, gaan we uit van een retour.
- Een gegevensentiteit voor een productcatalogus voor gebruik als een productfilter.

> [!NOTE]
> - Het model vereist de transactiegeschiedenis van uw klanten, waarbij de transactie alle gegevens zijn die een interactie tussen gebruiker en product beschrijven. Bijvoorbeeld het aanschaffen van een product, het volgen van een les of het bijwonen van een gebeurtenis.
> - Er kan slechts één transactiegeschiedenisentiteit worden geconfigureerd. Als er meerdere aankoop-entiteiten zijn, combineert u deze in Power Query vóór de gegevensopname.
> - Als order- en ordergegevens verschillende entiteiten zijn, voegt u deze samen voordat u ze in het model gebruikt. Het model werkt niet alleen met een bestellings-id of ontvangst-id in een entiteit.

## <a name="create-a-product-recommendation-prediction"></a>Een voorspelling voor een productaanbeveling maken

Selecteer **Concept opslaan** op elk gewenst moment om de voorspelling als concept op te slaan. De conceptvoorspelling wordt weergegeven op het tabblad **Mijn voorspellingen**.

1. Ga naar **Informatie** > **Voorspellingen**.

1. Selecteer op het tabblad **Maken** de optie **Model gebruiken** op de tegel **Productaanbevelingen (preview)**.

1. Selecteer **Aan de slag**.

1. **Geef dit model een naam** en de **Naam van uitvoerentiteit** om ze te onderscheiden van andere modellen of entiteiten.

1. Selecteer **Volgende**.

### <a name="define-product-recommendation-preferences"></a>Voorkeuren voor productaanbevelingen definiëren

1. Stel het **aantal producten** in voor aanbeveling aan een klant. Deze waarde is afhankelijk van de manier waarop uw leveringsmethode de gegevens vult.

1. Kies of u producten wilt opnemen die klanten voorheen hebben gekocht in het veld **Verwachte herhaalde aankopen**.

1. Stel het **Terugkijkvenster** in met de tijdsbestek dat het model in overweging neemt voordat het product opnieuw aan de gebruiker wordt aanbevolen. Geef bijvoorbeeld aan dat een klant om de twee jaar een laptop koopt. Het model bekijkt de aankoopgeschiedenis van de afgelopen twee jaar en filtert, als er een item wordt gevonden, het iitem uit de aanbevelingen.

1. Selecteer **Volgende**

### <a name="add-purchase-history"></a>Aankoopgeschiedenis toevoegen

1. Selecteer **Gegevens toevoegen** bij **Transactiegeschiedenis van de klant**.

1. Selecteer het semantische activiteitstype **SalesOrderLine** dat de vereiste transactie- of aankoopgeschiedenisgegevens bevat. Als de activiteit niet is ingesteld, selecteert u **hier** en maakt u deze.

1. Kies onder **Activiteiten**, als de activiteitskenmerken semantisch zijn toegewezen bij het maken van de activiteit, de specifieke kenmerken of entiteit waarop u de berekening wilt richten. Als er geen semantische toewijzing heeft plaatsgevonden, selecteert u **Bewerken** en wijst u uw gegevens toe.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Zijvenster met het kiezen van specifieke activiteiten onder het semantische type.":::

1. Selecteer **Volgende** en bekijk de kenmerken die vereist zijn voor dit model.

1. Selecteer **Save**.

1. Selecteer **Volgende**.

### <a name="add-product-information-and-filters"></a>Productgegevens en filters toevoegen

Soms zijn alleen bepaalde producten gunstig of geschikt voor het type voorspelling dat u opstelt. Gebruik productfilters om een subset van producten met specifieke kenmerken te identificeren die u aan uw klanten kunt aanbevelen. Het model gebruikt alle beschikbare producten om patronen te leren, maar gebruikt alleen de producten die overeenkomen met het productfilter in de uitvoer.

1. Voeg uw productcatalogusentiteit toe die gegevens voor elk product bevat. Wijs de vereiste gegevens toe en selecteer **Opslaan**.

1. Selecteer **Volgende**.

1. Selecteer **Productfilters**:

   - **Geen filters**: gebruik alle producten in Productaanbevelingen voorspellen.

   - **Specifieke productfilters definiëren**: gebruik specifieke producten in Productaanbevelingen voorspellen. Selecteer in het deelvenster **Kenmerken van productcatalogus** de kenmerken van uw productcatalogusentiteit die u in het filter wilt opnemen.

     :::image type="content" source="media/product-filters-sidepane.png" alt-text="Zijpaneel met kenmerken in de Productcatalogus-entiteit om te selecteren voor productfilters.":::

1. Kies of u het productfilter **en** of **of** wilt laten gebruiken om uw selectie van kenmerken uit de productcatalogus logisch te combineren.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Voorbeeldconfiguratie van productfilters gecombineerd met logische EN-connectors.":::

1. Selecteer **Volgende**.

### <a name="set-update-schedule"></a>Updateplanning instellen

1. Kies een frequentie voor het opnieuw trainen van uw model. Deze instelling is belangrijk om de nauwkeurigheid van voorspellingen bij te werken wanneer nieuwe gegevens worden opgenomen in Customer Insights. De meeste bedrijven kunnen eenmaal per maand opnieuw trainen en krijgen een goede nauwkeurigheid voor hun voorspelling.

1. Selecteer **Volgende**.

### <a name="review-and-run-the-model-configuration"></a>De modelconfiguratie controleren en uitvoeren

De stap **Controleren en uitvoeren** toont een samenvatting van de configuratie en biedt een kans om wijzigingen aan te brengen voordat u de voorspelling maakt.

1. Selecteer **Bewerken** in een van de stappen om te controleren en eventuele wijzigingen aan te brengen.

1. Als u tevereden bent over uw selecties, selecteert u **Opslaan en uitvoeren** om te beginnen met het uitvoeren van het model. Selecteer **Gereed**. Het tabblad **Mijn voorspellingen** wordt weergegeven terwijl de voorspelling wordt gemaakt. Het proces kan enkele uren in beslag nemen, afhankelijk van de hoeveelheid gegevens die in de voorspelling is gebruikt.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Resultaten van voorspelling weergeven

1. Ga naar **Informatie** > **Voorspellingen**.

1. Selecteer op het tabblad **Mijn voorspellingen** de voorspelling die u wilt weergeven.

Er zijn vijf primaire gegevenssecties op de resultatenpagina.

- **Modelprestaties:** beoordelingscijfers A, B of C geven de prestaties van de voorspelling aan en kan u helpen bij het nemen van de beslissing om de resultaten te gebruiken die zijn opgeslagen in de uitvoerentiteit.
  
  :::image type="content" source="media/product-recommendation-modelperformance.PNG" alt-text="Afbeelding van het modelprestatieresultaat met het beoordelingscijfer A.":::

  Cijfers worden bepaald op basis van de volgende regels:
  - **A** wanneer het metrische gegeven "Succes bij K" ten minste 10% hoger is dan de basislijn.
  - **B** wanneer het metrische gegeven "Succes bij K" 0% tot 10% hoger is dan de basislijn.
  - **C** wanneer het metrische gegeven "Succes bij K" lager is dan de basislijn.
  - **Basislijn**: de beste aanbevolen producten op basis van het aantal aankopen voor alle klanten + geleerde regels die door het model zijn geïdentificeerd = een reeks aanbevelingen voor de klanten. De voorspellingen worden vervolgens vergeleken met de beste producten, zoals berekend door het aantal klanten dat het product heeft gekocht. Als een klant ten minste één product in zijn aanbevolen producten heeft dat ook te zien was in de best gekochte producten, worden ze beschouwd als een onderdeel van de basislijn. Als er bijvoorbeeld 10 van deze klanten zijn die een aanbevolen product hebben gekocht op een totaal van 100 klanten, bedraagt de basislijn 10%.
  - **Succes bij K**: er worden aanbevelingen gemaakt voor alle klanten en vergeleken met de validatieset voor de tijdsperiode van transacties. In een periode van 12 maanden kan bijvoorbeeld maand 12 worden gereserveerd als een validatieset van gegevens. Als het model ten minste één ding voorspelt dat u in maand 12 zou kopen op basis van wat het van de afgelopen 11 maanden heeft geleerd, zou de klant de metriek "Succesbij K" verhogen.

- **Meest voorgestelde producten (met aantal):** de top vijf producten die zijn voorspeld voor uw klanten.
  
  :::image type="content" source="media/product-recommendation-topproducts.PNG" alt-text="Grafiek met de top 5 van meest aanbevolen producten.":::

- **Belangrijkste aanbevelingsfactoren:** het model gebruikt de transactiegeschiedenis van de klant om productaanbevelingen te doen. Het leert patronen op basis van eerdere aankopen en vindt overeenkomsten tussen klanten en producten. Deze overeenkomsten worden vervolgens gebruikt om productaanbevelingen te genereren.
  De volgende factoren kunnen van invloed zijn op een productaanbeveling die door het model wordt gegenereerd.
  - **Eerdere transacties**: een aanbevolen product was gebaseerd op eerdere aankooppatronen. Het model kan bijvoorbeeld een *Surface Arc Mouse* adviseren als iemand onlangs een *Surface Book 3* en een *Surface-pen* heeft aangeschaft. Het model heeft geleerd dat historisch gezien veel klanten een *Surface Arc Mouse* kochten na aankoop van een *Surface Book 3* en een *Surface-pen*.
  - **Klantovereenkomst**: een aanbevolen product is in het verleden gekocht door andere klanten die vergelijkbare aankooppatronen vertonen. John kreeg bijvoorbeeld *Surface Headphones 2* als aanbeveling omdat Jennifer en Brad onlangs *Surface Headphones 2* hebben gekocht. Het model gelooft dat John vergelijkbaar is met Jennifer en Brad omdat ze in het verleden vergelijkbare aankooppatronen hebben gehad.
  - **Productovereenkomst**: een aanbevolen product is vergelijkbaar met andere producten die de klant eerder had gekocht. Het model beschouwt twee producten als vergelijkbaar als ze samen of door vergelijkbare klanten zijn gekocht. Iemand krijgt bijvoorbeeld een aanbeveling voor een *USB-opslagstation* omdat hij of zij eerder een *USB-C naar USB-adapter* heeft gekocht en het model gelooft dat *USB-opslagstation* gelijkaardig is aan *USB-C naar USB-adapter* op basis van historische aankooppatronen.

  Elke productaanbeveling wordt beïnvloed door een of meer van deze factoren. Het percentage aanbevelingen waarbij elke beïnvloedende factor een rol speelde, wordt weergegeven in een grafiek. In het volgende voorbeeld werd 100% van de aanbevelingen beïnvloed door eerdere transacties, 60% door klantovereenkomst en 22% door productovereenkomst. Beweeg over de balken in de grafiek om het exacte percentage te zien waaraan de beïnvloedende factoren hebben bijgedragen.
  
  :::image type="content" source="media/product-recommendation-keyrecommendationfactors.png" alt-text="Belangrijkste aanbevelingsfactoren die door het model zijn geleerd om productaanbevelingen te genereren.":::

- **Gegevensstatistieken**: een overzicht van het aantal transacties, klanten en producten dat het model in overweging heeft genomen. Het is gebaseerd op de invoergegevens die zijn gebruikt om patronen te leren en productaanbevelingen te genereren.

  :::image type="content" source="media/product-recommendation-datastatistics.png" alt-text="Gegevensstatistieken rond invoergegevens die door het model worden gebruikt om patronen te leren.":::
  
  Het model gebruikt alle beschikbare gegevens om patronen te leren. Als u productfiltering gebruikt in de modelconfiguratie, wordt in deze sectie daarom het totale aantal producten weergegeven dat het model heeft geanalyseerd om patronen te leren. Dit kan verschillen van het aantal producten dat voldoet aan de gedefinieerde filtercriteria. Er wordt gefilterd op de uitvoer die door het model wordt gegenereerd.

- **Voorbeelden van productaanbevelingen**: een voorbeeld van aanbevelingen waarvan het model denkt dat ze waarschijnlijk door de klant zullen worden gekocht. Als een productcatalogus wordt toegevoegd, worden de product-id's vervangen door productnamen.

  :::image type="content" source="media/product-recommendation-highconfidence.PNG" alt-text="Lijst met zeer betrouwbare suggesties voor een selecte groep individuele klanten.":::

> [!NOTE]
> In de uitvoerentiteit voor dit model geeft *Score* de kwantitatieve maatstaf van de aanbeveling aan. Het model adviseert producten met een hogere score boven producten met een lagere score. Als u de core wilt bekijken, gaat u naar **Gegevens** > **Entiteiten** en bekijkt u het gegevenstabblad voor de uitvoerentiteit die u voor dit model hebt gedefinieerd.

[!INCLUDE [footer-include](includes/footer-banner.md)]
