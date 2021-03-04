---
title: Productaanbevelingen voorspellen
description: Voorspel de producten die een klant waarschijnlijk zal kopen of gebruiken.
ms.date: 02/15/2021
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a2eb2b4697e51a0abb933b654a9b0b150dfa6a3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270483"
---
# <a name="product-recommendation-prediction-preview"></a>Productaanbevelingen voorspellen (preview)

Het productaanbevelingsmodel maakt sets met voorspellende productaanbevelingen. Aanbevelingen zijn gebaseerd op eerder aankoopgedrag en klanten met vergelijkbare aankooppatronen. U kunt voorspellingen voor nieuwe productaanbevelingen maken op de pagina **Informatie** > **Voorspellingen**. Selecteer **Mijn voorspellingen** om andere voorspellingen te bekijken die u hebt gemaakt.

Productaanbevelingen kunnen onderhevig zijn aan lokale wet- en regelgeving en aan de verwachtingen van de klant, waarmee het model niet specifiek rekening houdt.  Als gebruiker van deze voorspellende mogelijkheid **moet u de aanbevelingen bekijken voordat u ze aan uw klanten verstrekt** om ervoor te zorgen dat u voldoet aan alle toepasselijke wet- of regelgeving, evenals aan de verwachtingen van de klant voor wat u mogelijk aanbeveelt. 

Bovendien geeft de uitvoer van dit model aanbevelingen op basis van het product-id. Uw leveringsmechanisme moet voorspelde product-id's nemen en deze toewijzen aan geschikte inhoud voor uw klanten om rekening te houden met lokalisatie, afbeeldingsinhoud en andere bedrijfsspecifieke inhoud of gedrag.

## <a name="sample-guide"></a>Voorbeeldgids

Als je deze functie wilt proberen, maar geen gegevens hebt om aan de onderstaande vereisten te voldoen, kunt u [een voorbeeldimplementatie maken](sample-guide-predict-product-recommendation.md)​.

## <a name="prerequisites"></a>Vereisten

- Minimaal [inzendermachtigingen](permissions.md) in Customer Insights.
- Zakelijke kennis om verschillende soorten producten voor uw bedrijf te begrijpen en te begrijpen hoe uw klanten ermee omgaan. We ondersteunen het aanbevelen van producten die eerder door uw klanten zijn gekocht of aanbevelingen voor nieuwe producten.
- Gegevens over uw transacties, aankopen en hun geschiedenis:
    - Transactie-id's om aankopen of transacties te onderscheiden.
    - Klant-id's om transacties toe te wijzen aan uw klanten.
    - Transactiegebeurtenisdatums die de datums specificeren waarop de transactie plaatsvond.
    - (Optioneel) Product-id-informatie voor de transactie.
    - (Optioneel) Of een transactie een retour is of niet.
    - Het semantische gegevensschema vereist de volgende informatie:
        - **Transactie-id:** een unieke identificatie van een aankoop of transactie.
        - **Transactiedatum**: de datum van de aankoop of de transactie.
        - **Waarde van de transactie**: de numerieke waarde van de aankoop of de transactie.
        - **Unieke product-id**: de id van het gekochte product of de gekochte service als uw gegevens zich op regelitemniveau bevinden.
        - (Optioneel) **Aankoop of retour**: een waar/onwaar-veld dat aangeeft of de transactie een retour was of niet. Als de **Waarde van de transactie** negatief is, gebruiken we deze informatie ook om een retour af te leiden.


## <a name="create-a-product-recommendation-prediction"></a>Een voorspelling voor een productaanbeveling maken

1. Ga in Customer Insights naar **Informatie** > **Voorspellingen**.

1. Selecteer de tegel **Model voor productaanbevelingen (preview)** en selecteer **Dit model gebruiken**.
   > [!div class="mx-imgBorder"]
   > ![Tegel Productaanbevelingsmodel met knop Dit model gebruiken](media/product-recommendation-usethismodel.PNG "Tegel Productaanbevelingsmodel met knop Dit model gebruiken")

1. Bekijk de informatie over de modelvereisten. Als u over de vereiste gegevens beschikt, selecteert u **Aan de slag**.

### <a name="name-model"></a>Model een naam geven

1. Geef het model een naam om het van andere modellen te onderscheiden.

1. Voer een naam in voor de uitvoerentiteit met alleen letters en cijfers, zonder spaties. Dat is de naam die de modelentiteit zal gebruiken. Selecteer vervolgens **Volgende**.

### <a name="define-product-recommendation-configuration"></a>Definieer de configuratie van productaanbevelingen

1. Stel het **Aantal producten** in dat u een klant wilt aanbevelen. Deze waarde is afhankelijk van de manier waarop uw leveringsmethode de gegevens vult. Als u drie producten kunt aanbevelen, stelt u deze waarde dienovereenkomstig in.
   
   >[!TIP]
   > U kunt op elk gewenst moment **Opslaan en sluiten** selecteren om de voorspelling als concept op te slaan. U vindt de conceptvoorspelling op het tabblad **Mijn voorspellingen**.

1. U kunt kiezen voor de optie **Producten voorstellen die onlangs door klanten zijn aangeschaft**.

1. Als u ervoor hebt gekozen *geen* aanbeveling te doen voor onlangs gekochte producten, stelt u het **Terugkijkvenster** in. Deze instelling specificeert de tijdsbestek die het model in overweging neemt voordat het product opnieuw aan de gebruiker wordt aanbevolen. Geef bijvoorbeeld aan dat een klant elke 2 jaar een laptop koopt. In dit venster wordt de aankoopgeschiedenis van de afgelopen 2 jaar bekeken en als ze een artikel vinden, wordt het uit de aanbevelingen gefilterd.

1. Selecteer **Volgende**

### <a name="add-required-data"></a>Vereiste gegevens toevoegen

1. Selecteer **Gegevens toevoegen** voor **Transactiegeschiedenis van klant** en kies de entiteit die de transactie-/ aankoopgeschiedenisinformatie verstrekt, zoals beschreven in de [vereisten](#prerequisites).

1. Wijs de semantische velden toe aan kenmerken binnen uw aankoopgeschiedenis-entiteit en selecteer **Volgende**. Zie de [vereisten](#prerequisites) voor beschrijvingen van de velden.
   > [!div class="mx-imgBorder"]
   > ![De entiteitsrelatie definiëren](media/product-recommendation-purchasehistorymapping.PNG "Aankoopgeschiedenispagina met semantische kenmerken die zijn toegewezen aan velden in de geselecteerde aankoopgeschiedenisentiteit")

1. Als de onderstaande velden niet zijn ingevuld, configureert u de relatie tussen de entiteit Aankoopgeschiedenis en de entiteit *Klant*.
    1. Selecteer de **entiteit Aankoopgeschiedenis**.
    1. Selecteer het **Veld** dat de klant identificeert in de entiteit Aankoopgeschiedenis. Het moet betrekking hebben op de primaire klant-id van uw entiteit *Klant*.
    1. Selecteer de **entiteit Klant** die overeenkomt met uw primaire klantentiteit.
    1. Voer een naam in waarmee de relatie wordt omschreven.
       > [!div class="mx-imgBorder"]
       > ![De pagina Aankoopgeschiedenis waarop het maken van een relatie met klant te zien is](media/model-purchase-join.png "De pagina Aankoopgeschiedenis waarop het maken van een relatie met klant te zien is")

1. Selecteer **Opslaan**.

1. Selecteer **Volgende**.

### <a name="set-schedule-and-review-configuration"></a>Schema instellen en configuratie bekijken

1. Stel een frequentie in voor het opnieuw trainen van uw model. Deze instelling is belangrijk om de nauwkeurigheid van voorspellingen bij te werken wanneer nieuwe gegevens worden geïmporteerd in Customer Insights. De meeste bedrijven kunnen eenmaal per maand opnieuw trainen en krijgen een goede nauwkeurigheid voor hun voorspelling.

1. Selecteer **Volgende**.

1. Bekijk de configuratie. U kunt teruggaan naar elk willekeurig deel van de voorspellingsconfiguratie door **Bewerken** te selecteren onder de weergegeven waarde. Of u kunt een configuratiestap selecteren vanuit de voortgangsindicator.

1. Selecteer **Opslaan en uitvoeren** om het voorspellingsproces te starten als alle waarden correct zijn geconfigureerd. Op het tabblad **Mijn voorspellingen** kunt u de status van uw voorspellingen bekijken. Het proces kan enkele uren in beslag nemen, afhankelijk van de hoeveelheid gegevens die in de voorspelling is gebruikt.

## <a name="review-a-prediction-status-and-results"></a>Een voorspellingsstatus en resultaten bekijken

1. Ga naar het tabblad **Mijn voorspellingen** in **Informatie** > **Voorspellingen**.
   > [!div class="mx-imgBorder"]
   > ![Weergave van de pagina Mijn voorspellingen](media/product-recommendation-mypredictions.PNG "Weergave van de pagina Mijn voorspellingen")

1. Selecteer de voorspelling die u wilt beoordelen.
   - **Voorspellingsnaam:** de naam van de voorspelling die is opgegeven bij het maken ervan.
   - **Voorspellingstype:** het type model dat voor de voorspelling is gebruikt
   - **Uitvoerentiteit:** naam van de entiteit om de uitvoer van de voorspelling op te slaan. U kunt een entiteit met deze naam vinden onder **Gegevens** > **Entiteiten**.
   - **Veld Voorspeld:** dit veld wordt alleen ingevuld voor bepaalde soorten voorspellingen en wordt niet gebruikt bij verloopvoorspelling.
   - **Status:** de huidige status van de uitvoering van de voorspelling.
        - **In wachtrij:** de voorspelling wacht momenteel op het uitvoeren van andere processen.
        - **Vernieuwen:** de voorspelling is momenteel bezig met het 'scorefase' van de verwerking om resultaten te produceren die naar de uitvoerentiteit zullen worden overgebracht.
        - **Mislukt:** de voorspelling is mislukt. Selecteer **Logboeken** voor nadere details.
        - **Geslaagd:** de voorspelling is geslaagd. Selecteer **Weergave** onder de verticale puntjes om de voorspelling te beoordelen
   - **Bewerkt:** de datum waarop de configuratie voor de voorspelling is gewijzigd.
   - **Laatst vernieuwd:** de datum waarop de voorspelling is vernieuwd resulteert in de uitvoerentiteit.

1. Selecteer de verticale puntjes naast de voorspelling waarvoor u de resultaten wilt beoordelen en selecteer **Weergave**.
   > [!div class="mx-imgBorder"]
   > ![Weergave van opties in het menu met verticale puntjes voor een voorspelling, waaronder bewerken, vernieuwen, weergeven, logboeken en verwijderen](media/product-recommendation-verticalellipses.PNG "Weergave van opties in het menu met verticale puntjes voor een voorspelling, waaronder bewerken, vernieuwen, weergeven, logboeken en verwijderen")

1. Er zijn drie primaire gegevenssecties op de resultatenpagina:
    1. **Prestaties trainingsmodel:** mogelijke scores zijn A, B of C. Deze score geeft de prestatie van de voorspelling aan en kan u helpen de beslissing te nemen om gebruik te maken van de resultaten die in de uitvoerentiteit zijn opgeslagen.
        - Scores worden bepaald op basis van de volgende regels:
            - **A** Het model wordt beschouwd als een model van kwaliteit **A** als de metriek "Succes bij K" ten minste 10% meer dan de basislijn is. 
            - **B** Het model wordt beschouwd als een model van kwaliteit **B** als de metriek "Succes bij K" 0 tot 10% meer dan de basislijn is.
            - **C** Het model wordt beschouwd als een model van kwaliteit **C** als de metriek "Succes bij K" minder dan de basislijn is.
               
               > [!div class="mx-imgBorder"]
               > ![Weergave van het modelprestatieresultaat](media/product-recommendation-modelperformance.PNG "Weergave van het modelprestatieresultaat")
            - **Basislijn**: het model neemt de beste aanbevolen producten op basis van het aantal aankopen voor alle klanten, en gebruikt geleerde regels die door het model zijn geïdentificeerd om een reeks aanbevelingen voor de klanten te maken. De voorspellingen worden vervolgens vergeleken met de beste producten, zoals berekend door het aantal klanten dat het product heeft gekocht. Als een klant ten minste één product in zijn aanbevolen producten heeft dat ook te zien was in de best gekochte producten, worden ze beschouwd als een onderdeel van de basislijn. Als er 10 van deze klanten waren die een aanbevolen product hadden gekocht op een totaal van 100 klanten, zou de basislijn 10% zijn.
            - **Succes bij K**: door gebruik te maken van een validatieset van transacties, worden aanbevelingen gemaakt voor alle klanten en vergeleken met de validatieset van transacties. In een periode van 12 maanden kan bijvoorbeeld maand 12 worden gereserveerd als een validatieset van gegevens. Als het model ten minste één ding voorspelt dat u in maand 12 zou kopen op basis van wat het van de afgelopen 11 maanden heeft geleerd, zou de klant de metriek "Succesbij K" verhogen.
    
    1. **Meest voorgestelde producten (met telling)**: de top 5 producten die zijn voorspeld voor uw klanten.
       > [!div class="mx-imgBorder"]
       > ![Grafiek met de top 5 van meest aanbevolen producten](media/product-recommendation-topproducts.PNG "Grafiek met de top 5 van meest aanbevolen producten")
    
    1. **Zeer betrouwbare productaanbevelingen**: een voorbeeld van aanbevelingen aan uw klanten waarvan het model denkt dat ze waarschijnlijk door de klant zullen worden gekocht.
       > [!div class="mx-imgBorder"]
       > ![Lijst met zeer betrouwbare suggesties voor een selecte groep individuele klanten](media/product-recommendation-highconfidence.PNG "Lijst met zeer betrouwbare suggesties voor een selecte groep individuele klanten")

## <a name="fix-a-failed-prediction"></a>Een mislukte voorspelling corrigeren

1. Ga naar het tabblad **Mijn voorspellingen** in **Informatie** > **Voorspellingen**.

1. Selecteer de voorspelling waarvoor u foutlogboeken wilt bekijken en selecteer **Logboeken**.

1. Bekijk alle fouten. Er zijn verschillende typen fouten die kunnen optreden en deze beschrijven welke toestand de fout heeft veroorzaakt. Een fout waarbij er niet genoeg gegevens beschikbaar zijn om een nauwkeurige voorspelling te maken wordt bijvoorbeeld doorgaans hersteld door extra gegevens in Customer Insights te laden.

## <a name="refresh-a-prediction"></a>Een voorspelling vernieuwen

Voorspellingen worden automatisch volgens dezelfde [planning vernieuwd als uw gegevens](system.md#schedule-tab), zoals geconfigureerd in instellingen.

1. Ga naar het tabblad **Mijn voorspellingen** in **Informatie** > **Voorspellingen**.

1. Selecteer de verticale puntjes naast de voorspelling die u wilt vernieuwen.

1. Selecteer **Vernieuwen**.

## <a name="delete-a-prediction"></a>Een voorspelling verwijderen

Als u een voorspelling verwijdert, wordt ook de uitvoerentiteit ervan verwijderd.

1. Ga naar het tabblad **Mijn voorspellingen** in **Informatie** > **Voorspellingen**.

1. Selecteer de verticale puntjes naast de voorspelling die u wilt verwijderen.

1. Selecteer **Verwijderen**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]