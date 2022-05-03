---
title: Productaanbevelingen voorspellen
description: Voorspel de producten die een klant waarschijnlijk zal kopen of gebruiken.
ms.date: 01/13/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: fe6c0e8ba8236243682a4105535a0026c4343c3d
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646404"
---
# <a name="product-recommendation-prediction"></a>Productaanbevelingen voorspellen

Het productaanbevelingsmodel maakt sets met voorspellende productaanbevelingen. Aanbevelingen zijn gebaseerd op eerder aankoopgedrag en klanten met vergelijkbare aankooppatronen. U kunt voorspellingen voor nieuwe productaanbevelingen maken op de pagina **Informatie** > **Voorspellingen**. Selecteer **Mijn voorspellingen** om andere voorspellingen te bekijken die u hebt gemaakt.

Productaanbevelingen kunnen onderhevig zijn aan lokale wet- en regelgeving en verwachtingen van de klant, waarmee het model niet specifiek rekening houdt.  Als gebruiker van deze voorspellende mogelijkheid, **moet u de aanbevelingen beoordelen voordat u ze aan uw klanten doorgeeft** om ervoor te zorgen dat u voldoet aan alle toepasselijke wet- of regelgeving en de verwachtingen van de klant voor wat u mogelijk aanbeveelt. 

Bovendien geeft de uitvoer van dit model aanbevelingen op basis van het product-id. Uw leveringsmechanisme moet de voorspelde product-id's toewijzen aan de juiste inhoud voor uw klanten om rekening te houden met lokalisatie, afbeeldingsinhoud en andere bedrijfsspecifieke inhoud of gedragingen.

## <a name="sample-guide"></a>Voorbeeldgids

Als je deze functie wilt proberen, maar geen gegevens hebt om aan de onderstaande vereisten te voldoen, kunt u [een voorbeeldimplementatie maken](sample-guide-predict-product-recommendation.md)​.

## <a name="prerequisites"></a>Vereisten

- Minimaal [inzendermachtigingen](permissions.md) in Customer Insights.

- Zakelijke kennis om verschillende soorten producten voor uw bedrijf te begrijpen en te begrijpen hoe uw klanten ermee omgaan. We ondersteunen het aanbevelen van producten die eerder door uw klanten zijn gekocht of aanbevelingen voor nieuwe producten.

- Gegevens over uw transacties, aankopen en hun geschiedenis:
    - Transactie-id's om aankopen of transacties te onderscheiden.
    - Klant-id's om transacties toe te wijzen aan uw klanten.
    - Transactiegebeurtenisdatums die de datums specificeren waarop de transactie plaatsvond.
    - Informatie over product-id voor de transactie.
    - (Optioneel) Een gegevensentiteit voor een productcatalogus om een productfilter te gebruiken.
    - (Optioneel) Of een transactie een retour is of niet.
    - Het semantische gegevensschema vereist de volgende informatie:
        - **Transactie-id:** een unieke identificatie van een aankoop of transactie.
        - **Transactiedatum:** de datum van de aankoop of de transactie.
        - **Waarde van de transactie**: de numerieke waarde van de aankoop of de transactie.
        - **Unieke product-id**: de id van het gekochte product of de gekochte service als uw gegevens zich op regelitemniveau bevinden.
        - (Optioneel) **Aankoop of retour:** Een booleaans veld waarin de waarde *waar* aangeeft dat een transactie een retour was. Als de gegevens voor Aankoop of retour niet zijn opgegeven en het model en **Waarde van de transactie** negatief is, zullen we deze informatie ook gebruiken om een retour af te leiden.
- Voorgestelde gegevenskenmerken:
    - Voldoende historische gegevens: ten minste één jaar aan transactiegegevens, bij voorkeur twee tot drie jaar om enige seizoensinvloeden op te nemen.
    - Meerdere aankopen per klant: drie of meer transacties per klant-id
    - Aantal klanten: minimaal 100 klanten, bij voorkeur meer dan 10.000 klanten. Het model zal mislukken bij minder dan 100 klanten.

> [!NOTE]
> - Het model vereist de transactiegeschiedenis van uw klanten. De definitie van een transactie is vrij flexibel. Alle gegevens die een interactie tussen gebruiker en product beschrijven, kunnen als input dienen. Bijvoorbeeld het aanschaffen van een product, het volgen van een les of het bijwonen van een gebeurtenis.
> - Er kan momenteel slechts één transactiehistorie-entiteit worden geconfigureerd. Als er meerdere aankoop-entiteiten zijn, voegt u deze samen in Power Query vóór de gegevensopname.
> - Als order- en ordergegevens verschillende entiteiten zijn, voegt u deze samen voordat u ze in het model gebruikt. Het model werkt niet alleen met een bestellings-id of ontvangst-id in een entiteit.


## <a name="create-a-product-recommendation-prediction"></a>Een voorspelling voor een productaanbeveling maken

1. Ga in Customer Insights naar **Informatie** > **Voorspellingen**.

1. Selecteer de tegel **Model voor productaanbevelingen** en selecteer **Dit model gebruiken**.
   > [!div class="mx-imgBorder"]
   > ![Tegel Productaanbevelingsmodel met knop Dit model gebruiken.](media/product-recommendation-usethismodel.PNG "Tegel Productaanbevelingsmodel met knop Dit model gebruiken")

1. Bekijk de informatie over de modelvereisten. Als u over de vereiste gegevens beschikt, selecteert u **Aan de slag**.

### <a name="name-model"></a>Model een naam geven

1. Geef het model een naam om het van andere modellen te onderscheiden.

1. Voer een naam in voor de uitvoerentiteit met alleen letters en cijfers, zonder spaties. Dat is de naam die de modelentiteit zal gebruiken. Selecteer vervolgens **Volgende**.

### <a name="define-product-recommendation-configuration"></a>De configuratie van productaanbevelingen definiëren

1. Stel het **Aantal producten** in dat u een klant wilt aanbevelen. Deze waarde is afhankelijk van de manier waarop uw leveringsmethode de gegevens vult. Als u drie producten kunt aanbevelen, stelt u deze waarde dienovereenkomstig in.
   
   >[!TIP]
   > U kunt op elk moment **Concept opslaan** selecteren om de voorspelling als concept op te slaan. U vindt de conceptvoorspelling op het tabblad **Mijn voorspellingen**.

1. Kies of u producten wilt opnemen die klanten onlangs hebben gekocht in het veld **Verwachte herhaalde aankopen**.

1. Stel het **Terugkijkvenster** in. Deze instelling specificeert de tijdsbestek die het model in overweging neemt voordat het product opnieuw aan de gebruiker wordt aanbevolen. Geef bijvoorbeeld aan dat een klant om de twee jaar een laptop koopt. In dit tijdsbestek wordt de aankoopgeschiedenis van de afgelopen twee jaar bekeken en als ze een item vinden, wordt het uit de aanbevelingen gefilterd.

1. Selecteer **Volgende**

### <a name="add-required-data"></a>Vereiste gegevens toevoegen

1. Selecteer **Gegevens toevoegen** en kies in het zijvenster het type activiteit met de vereiste gegevens van de transactie- of aankoopgeschiedenis.

1. Kies onder **De activiteiten kiezen** de specifieke activiteiten van de geselecteerde activiteit waarop de berekening moet worden gericht.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Zijvenster met het kiezen van specifieke activiteiten onder het semantische type.":::

1. Als u de activiteit nog niet hebt toegewezen aan een semantisch type, selecteert u **Bewerken** om dat te doen. De begeleide ervaring voor het toewijzen van semantische activiteiten wordt geopend. Wijs uw gegevens toe aan de overeenkomende velden in het geselecteerde type activiteit.

   :::image type="content" source="media/product-recommendation-set-activity-type.PNG" alt-text="Activiteitstype pagina-instelling.":::

1. Selecteer na het toewijzen van de activiteit aan het corresponderende semantische type de optie **Volgende** om door te gaan 
 
1. Wijs de semantische kenmerken toe aan de velden die nodig zijn om het model uit te voeren.

1. Selecteer **Opslaan**.

1. Selecteer **Volgende**.


### <a name="configure-product-filters"></a>Productfilters configureren

Soms zijn alleen bepaalde producten gunstig of geschikt voor het type voorspelling dat u opstelt. Met productfilters kunt u een subset van producten met specifieke kenmerken identificeren die u aan uw klanten kunt aanbevelen. Het model gebruikt alle beschikbare producten om patronen te leren, maar gebruikt alleen de producten die overeenkomen met het productfilter in de uitvoer.

1. In de stap **Productgegevens toevoegen** voegt u uw productcatalogus toe met informatie voor elk product. Wijs de vereiste informatie toe en selecteer **Volgende**.

3. Maak in de stap **Productfilters** een keuze uit de volgende opties.

   * **Geen filters**: gebruik alle producten in Productaanbevelingen voorspellen.

   * **Specifieke productfilters definiëren**: gebruik specifieke producten in Productaanbevelingen voorspellen.

1. Selecteer **Volgende**.

1. Als u ervoor kiest om een productfilter te definiëren, moet u deze nu definiëren. Selecteer in het deelvenster **Kenmerken van productcatalogus** de kenmerken van uw *Productcatalogus-entiteit* die u in het filter wilt opnemen.

   :::image type="content" source="media/product-filters-sidepane.png" alt-text="Zijpaneel met kenmerken in de Productcatalogus-entiteit om te selecteren voor productfilters.":::

1. Kies of u het productfilter **en**- of **of**-connectors wilt laten gebruiken om uw selectie van kenmerken uit de productcatalogus logisch te combineren.
   
   :::image type="content" source="media/product-filters-sample.png" alt-text="Voorbeeldconfiguratie van productfilters gecombineerd met logische EN-connectors.":::

1. Selecteer **Volgende**.

### <a name="set-update-schedule-and-review-configuration"></a>Het updateschema opstellen en de configuratie bekijken

1. Stel een frequentie in voor het opnieuw trainen van uw model. Deze instelling is belangrijk om de nauwkeurigheid van voorspellingen bij te werken wanneer nieuwe gegevens worden geïmporteerd in Customer Insights. De meeste bedrijven kunnen eenmaal per maand opnieuw trainen en krijgen een goede nauwkeurigheid voor hun voorspelling.

1. Selecteer **Volgende**.

1. Bekijk de configuratie. U kunt teruggaan naar elk willekeurig deel van de voorspellingsconfiguratie door **Bewerken** te selecteren onder de weergegeven waarde. Of u kunt een configuratiestap selecteren vanuit de voortgangsindicator.

1. Selecteer **Opslaan en uitvoeren** om het voorspellingsproces te starten als alle waarden correct zijn geconfigureerd. Op het tabblad **Mijn voorspellingen** kunt u de status van uw voorspellingen bekijken. Het proces kan enkele uren in beslag nemen, afhankelijk van de hoeveelheid gegevens die in de voorspelling is gebruikt.

## <a name="review-a-prediction-status-and-results"></a>Een voorspellingsstatus en resultaten bekijken

1. Ga naar het tabblad **Mijn voorspellingen** in **Informatie** > **Voorspellingen**.
   > [!div class="mx-imgBorder"]
   > ![Weergave van de pagina Mijn voorspellingen.](media/product-recommendation-mypredictions.PNG "Weergave van de pagina Mijn voorspellingen")

1. Selecteer de voorspelling die u wilt beoordelen.
   - **Voorspellingsnaam:** de naam van de voorspelling die is opgegeven bij het maken ervan.
   - **Voorspellingstype:** het type model dat voor de voorspelling is gebruikt
   - **Uitvoerentiteit:** naam van de entiteit om de uitvoer van de voorspelling op te slaan. U kunt een entiteit met deze naam vinden onder **Gegevens** > **Entiteiten**.    
      *Score* in de uitvoerentiteit is een kwantitatieve maatstaf van de aanbeveling. Het model adviseert producten met een hogere score boven producten met een lagere score.
   - **Voorspeld veld:** dit veld wordt alleen ingevuld voor bepaalde typen voorspellingen en wordt niet gebruikt in Productaanbevelingen voorspellen.
   - **Status:** de huidige status van de uitvoering van de voorspelling.
        - **In wachtrij:** de voorspelling wacht momenteel op het uitvoeren van andere processen.
        - **Vernieuwen:** de voorspelling is momenteel bezig met het 'scorefase' van de verwerking om resultaten te produceren die naar de uitvoerentiteit zullen worden overgebracht.
        - **Mislukt:** de voorspelling is mislukt. Selecteer **Logboeken** voor nadere details.
        - **Geslaagd:** de voorspelling is geslaagd. Selecteer **Weergave** onder de verticale puntjes om de voorspelling te beoordelen
   - **Bewerkt:** de datum waarop de configuratie voor de voorspelling is gewijzigd.
   - **Laatst vernieuwd:** de datum waarop de voorspelling is vernieuwd resulteert in de uitvoerentiteit.

1. Selecteer de verticale puntjes naast de voorspelling waarvoor u de resultaten wilt beoordelen en selecteer **Weergave**.
   > [!div class="mx-imgBorder"]
   > ![Weergave van opties in het menu met verticale puntjes voor een voorspelling, waaronder bewerken, vernieuwen, weergeven, logboeken en verwijderen.](media/product-recommendation-verticalellipses.PNG "Weergave van opties in het menu met verticale puntjes voor een voorspelling, waaronder bewerken, vernieuwen, weergeven, logboeken en verwijderen")

1. Er zijn vijf primaire gegevenssecties op de resultatenpagina:
    1. **Prestaties trainingsmodel:** mogelijke scores zijn A, B of C. Deze score geeft de prestatie van de voorspelling aan en kan u helpen de beslissing te nemen om gebruik te maken van de resultaten die in de uitvoerentiteit zijn opgeslagen.
        - Scores worden bepaald op basis van de volgende regels:
            - **A** Het model wordt beschouwd als een model van kwaliteit **A** als de metriek "Succes bij K" ten minste 10% meer dan de basislijn is. 
            - **B** Het model wordt beschouwd als een model van kwaliteit **B** als de metriek "Succes bij K" 0% tot 10% meer dan de basislijn is.
            - **C** Het model wordt beschouwd als een model van kwaliteit **C** als de metriek "Succes bij K" minder dan de basislijn is.
               
               > [!div class="mx-imgBorder"]
               > ![Weergave van het modelprestatieresultaat.](media/product-recommendation-modelperformance.PNG "Weergave van het modelprestatieresultaat")
            - **Basislijn**: het model neemt de beste aanbevolen producten op basis van het aantal aankopen voor alle klanten, en gebruikt geleerde regels die door het model zijn geïdentificeerd om een reeks aanbevelingen voor de klanten te maken. De voorspellingen worden vervolgens vergeleken met de beste producten, zoals berekend door het aantal klanten dat het product heeft gekocht. Als een klant ten minste één product in zijn aanbevolen producten heeft dat ook te zien was in de best gekochte producten, worden ze beschouwd als een onderdeel van de basislijn. Als er 10 van deze klanten waren die een aanbevolen product hadden gekocht op een totaal van 100 klanten, zou de basislijn 10% zijn.
            - **Succes bij K**: door gebruik te maken van een validatieset van transacties, worden aanbevelingen gemaakt voor alle klanten en vergeleken met de validatieset van transacties. In een periode van 12 maanden kan bijvoorbeeld maand 12 worden gereserveerd als een validatieset van gegevens. Als het model ten minste één ding voorspelt dat u in maand 12 zou kopen op basis van wat het van de afgelopen 11 maanden heeft geleerd, zou de klant de metriek "Succesbij K" verhogen.
    
    1. **Meest voorgestelde producten (met aantal):** de top vijf producten die zijn voorspeld voor uw klanten.
       > [!div class="mx-imgBorder"]
       > ![Grafiek met de top 5 van meest aanbevolen producten.](media/product-recommendation-topproducts.PNG "Grafiek met de top 5 van meest aanbevolen producten")
    
    1. **Belangrijkste aanbevelingsfactoren:** het model gebruikt de transactiegeschiedenis van de klant om productaanbevelingen te doen. Het leert patronen op basis van eerdere aankopen en vindt overeenkomsten tussen klanten en producten. Deze overeenkomsten worden vervolgens gebruikt om productaanbevelingen te genereren.
    Hieronder volgen de factoren die van invloed kunnen zijn op een productaanbeveling die door het model wordt gegenereerd. 
        - **Transacties uit het verleden**: aankooppatronen in het verleden werden door het model gebruikt om productaanbevelingen te genereren. Het model kan bijvoorbeeld een _Surface Arc Mouse_ adviseren als iemand onlangs een _Surface Book 3_ en een _Surface-pen_ heeft aangeschaft. Het model heeft geleerd dat historisch gezien veel klanten een _Surface Arc Mouse_ kochten na aankoop van een _Surface Book 3_ en een _Surface-pen_.
        - **Klantovereenkomst**: een aanbevolen product is in het verleden gekocht door andere klanten die vergelijkbare aankooppatronen vertonen. John kreeg bijvoorbeeld _Surface Headphones 2_ als aanbeveling omdat Jennifer en Brad onlangs _Surface Headphones 2_ hebben gekocht. Het model gelooft dat John vergelijkbaar is met Jennifer en Brad omdat ze in het verleden vergelijkbare aankooppatronen hebben gehad.
        - **Productovereenkomst**: een aanbevolen product is vergelijkbaar met andere producten die de klant eerder had gekocht. Het model beschouwt twee producten als vergelijkbaar als ze samen of door vergelijkbare klanten zijn gekocht. Iemand krijgt bijvoorbeeld een aanbeveling voor een _USB-opslagstation_ omdat hij of zij eerder een _USB-C naar USB-adapter_ heeft gekocht en het model gelooft dat _USB-opslagstation_ gelijkaardig is aan _USB-C naar USB-adapter_ op basis van historische aankooppatronen.

        Elke productaanbeveling wordt beïnvloed door een of meer van deze factoren. Het percentage aanbevelingen waarbij elke beïnvloedende factor een rol speelde, wordt weergegeven in een grafiek. In het volgende voorbeeld werd 100% van de aanbevelingen beïnvloed door eerdere transacties, 60% door klantovereenkomst en 22% door productovereenkomst. Beweeg over de balken in de grafiek om het exacte percentage te zien waaraan de beïnvloedende factoren hebben bijgedragen.

        > [!div class="mx-imgBorder"]
        > ![Belangrijke aanbevelingsfactoren.](media/product-recommendation-keyrecommendationfactors.png "Belangrijkste aanbevelingsfactoren die door het model zijn geleerd om productaanbevelingen te genereren")
       
     
   1. **Gegevensstatistieken**: biedt een overzicht van het aantal transacties, klanten en producten dat het model in overweging heeft genomen. Het is gebaseerd op de invoergegevens die zijn gebruikt om patronen te leren en productaanbevelingen te genereren.

      > [!div class="mx-imgBorder"]
      > ![Gegevensstatistieken.](media/product-recommendation-datastatistics.png "Gegevensstatistieken rond inout-gegevens die door het model worden gebruikt om patronen te leren")

      In dit gedeelte worden statistieken weergegeven rond de gegevenspunten die door het model zijn gebruikt om patronen te leren en productaanbevelingen te genereren. Filteren, zoals geconfigureerd in de modelconfiguratie, is van toepassing op de uitvoer die door het model wordt gegenereerd. Het model gebruikt echter alle beschikbare gegevens om patronen te leren. Als u productfiltering gebruikt in de modelconfiguratie, zal deze sectie daarom het totale aantal producten tonen dat het model heeft geanalyseerd om patronen te leren. Dit kan verschillen van het aantal producten dat voldoet aan de gedefinieerde filtercriteria.

   1. **Zeer betrouwbare productaanbevelingen**: een voorbeeld van aanbevelingen aan uw klanten waarvan het model denkt dat ze waarschijnlijk door de klant zullen worden gekocht.    
      Als een productcatalogus wordt toegevoegd, worden de product-id's vervangen door productnamen. Productnamen bieden meer bruikbare en intuïtieve informatie over de voorspellingen.
       > [!div class="mx-imgBorder"]
       > ![Lijst met zeer betrouwbare suggesties voor een selecte groep individuele klanten.](media/product-recommendation-highconfidence.PNG "Lijst met zeer betrouwbare suggesties voor een selecte groep individuele klanten")

## <a name="manage-predictions"></a>Voorspellingen beheren

Het is mogelijk om voorspellingen te optimaliseren, problemen op te lossen, voorspellingen te vernieuwen of deze te verwijderen. Bekijk een bruikbaarheidsrapport voor invoergegevens om erachter te komen hoe u een voorspelling sneller en betrouwbaarder kunt maken. Zie [Voorspellingen beheren](manage-predictions.md) voor meer informatie.


[!INCLUDE [footer-include](includes/footer-banner.md)]