---
title: Voorspelling van transactieverloop
description: Voorspel of het risico bestaat dat een klant de producten of services van uw bedrijf niet meer zal kopen.
ms.date: 10/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: ac484f74e388aa23422a89e25dabb555f2ad4118
ms.sourcegitcommit: 1565f4f7b4e131ede6ae089c5d21a79b02bba645
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/14/2021
ms.locfileid: "7643371"
---
# <a name="transaction-churn-prediction-preview"></a>Voorspelling van transactieverloop (preview)

Met deze functie kunt u voorspellen of een klant uw producten of services binnen een bepaald tijdsbestek niet meer zal kopen. U kunt nieuwe verloopvoorspellingen maken op **Intelligence** > **Voorspellingen**. Selecteer **Mijn voorspellingen** om andere voorspellingen te bekijken die u hebt gemaakt. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Voor omgevingen die zijn gebaseerd op zakelijke accounts, kunnen we het transactieverloop voor een account voorspellen en ook voor een combinatie van account en informatie van een ander niveau, zoals productcategorie. Door een dimensie toe te voegen, kunt u erachter komen hoe waarschijnlijk het is dat het account 'Contoso' stopt met het kopen van de productcategorie 'kantoorbenodigdheden'. Daarnaast kunnen we voor zakelijke accounts ook AI gebruiken om een lijst met mogelijke redenen te genereren waarom een account waarschijnlijk verloop zal vertonen voor een categorie informatie van een secundair niveau.

> [!TIP]
> Probeer de tutorial voor voorspelling van het transactieverloop met voorbeeldgegevens: [Voorbeeldgids voor voorspelling van transactieverloop (preview)](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Vereisten

- Minimaal [inzendermachtigingen](permissions.md) in Customer Insights.
- Zakelijke kennis om te begrijpen wat verloop voor uw bedrijf betekent. We ondersteunen op tijd gebaseerde verloopdefinities, wat betekent dat een klant na een periode zonder aankopen wordt beschouwd als verlopen.
- Gegevens over uw transacties/aankopen en hun geschiedenis:
    - Transactie-id's om aankopen/transacties te onderscheiden.
    - Klant-id's om transacties af te stemmen op uw klanten.
    - Transactiegebeurtenisdatums, die de datums definiëren waarop de transactie plaatsvond.
    - Het semantische gegevensschema voor aankopen/transacties vereist de volgende informatie:
        - **Transactie-id**: een unieke identificatie van een aankoop of transactie.
        - **Transactiedatum**: de datum van de aankoop of de transactie.
        - **Waarde van de transactie**: het bedrag in de valuta/numerieke waarde van de transactie/het item.
        - (Optioneel) **Unieke product-id**: de id van het gekochte product of de gekochte service als uw gegevens zich op regelitemniveau bevinden.
        - (Optioneel) **Of deze transactie een retour was**: een waar/onwaar-veld dat aangeeft of de transactie een retour was of niet. Als de **Waarde van de transactie** negatief is, gebruiken we deze informatie ook om een retour af te leiden.
- (Optioneel) Gegevens over klantactiviteiten:
    - Activiteits-id's om activiteiten van hetzelfde type te onderscheiden.
    - Klant-id's om activiteiten te koppelen aan uw klanten.
    - Activiteitsinformatie met de naam en datum van de activiteit.
    - Het semantische gegevensschema voor klantactiviteiten omvat:
        - **Primaire sleutel:** een unieke id voor een activiteit. Bijvoorbeeld een websitebezoek of een gebruiksrecord waaruit blijkt dat de klant een monster van uw product heeft geprobeerd.
        - **Tijdstempel:** de datum en tijd van de gebeurtenis die wordt geïdentificeerd door de primaire sleutel.
        - **Gebeurtenis:** de naam van de gebeurtenis die u wilt gebruiken. Een veld met de naam 'UserAction' in een supermarkt kan bijvoorbeeld een kortingsbon zijn die door de klant wordt gebruikt.
        - **Details:** gedetailleerde informatie over de gebeurtenis. Een veld met de naam 'CouponValue' in een supermarkt kan bijvoorbeeld de valutawaarde van de kortingsbon zijn.
- (Optioneel) Gegevens over uw klanten:
    - Deze gegevens moeten worden afgestemd op meer statische kenmerken om ervoor te zorgen dat het model het beste presteert.
    - Het semantische gegevensschema voor klantgegevens omvat:
        - **Klant-id** een unieke id voor een klant.
        - **Aanmaakdatum:** de datum waarop de klant voor het eerst is toegevoegd.
        - **Staat of provincie:** de staat of provincie van een klant.
        - **Land:** het land van een klant.
        - **Branche:** het branchetype van een klant. Een veld met de naam 'Branche' voor een koffiebrander kan bijvoorbeeld aangeven of de klant retail was.
        - **Classificatie:** de categorisering van een klant voor uw bedrijf. Een veld met de naam 'Waardesegment' voor een koffiebrander kan bijvoorbeeld het klantniveau aangeven op basis van de klantgrootte.
- Voorgestelde gegevenskenmerken:
    - Voldoende historische gegevens: transactiegegevens voor minimaal het dubbele van het geselecteerde tijdvenster. Bij voorkeur twee tot drie jaar transactiegeschiedenis. 
    - Meerdere aankopen per klant: idealiter ten minste twee transacties per klant.
    - Aantal klanten: minimaal 10 klantprofielen, bij voorkeur meer dan 1.000 unieke klanten. Het model zal mislukken met minder dan 10 klanten en onvoldoende historische gegevens.
    - Compleetheid van gegevens: minder dan 20% ontbrekende waarden in het gegevensveld van de opgegeven entiteit.

> [!NOTE]
> Voor een bedrijf met een hoge aankoopfrequentie van klanten (om de paar weken) wordt het aanbevolen om een korter voorspellingsvenster en verloopdefinitie te selecteren. Kies voor een lage aankoopfrequentie (om de paar maanden of eenmaal per jaar) een langer voorspellingsvenster en verloopdefinitie.

## <a name="create-a-transaction-churn-prediction"></a>Een voorspelling van transactieverloop maken

1. Ga in Customer Insights naar **Informatie** > **Voorspellingen**.

1. Selecteer de tegel **Klantverloopmodel (preview)** en selecteer **Dit model gebruiken**.

1. In het deelvenster **Klantverloopmodel** kies **Transactie** en selecteer **Aan de slag**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Schermafbeelding met geselecteerde optie Transactie in het deelvenster Klantverloopmodel.":::

### <a name="name-model"></a>Model een naam geven

1. Geef het model een naam om het van andere modellen te onderscheiden.

1. Geef een naam op voor de uitvoerentiteit met alleen letters en cijfers, zonder spaties. Dat is de naam die de modelentiteit zal gebruiken. 

1. Selecteer **Volgende**.

### <a name="define-customer-churn"></a>Klantverloop definiëren

1. Stel een aantal dagen in om het verloop in het veld **Klanten identificeren die kunnen verlopen in de volgende**. Voorspel bijvoorbeeld het verlooprisico voor uw klanten in de komende 90 dagen om deze op uw marketinginspanningen voor klantbehoud af te stemmen. Het voorspellen van het verlooprisico voor een langere of kortere periode kan het moeilijker maken om de factoren in uw verlooprisicoprofiel mee te nemen, maar het hangt af van uw specifieke zakelijke vereisten.
   >[!TIP]
   > U kunt op elk gewenst moment **Opslaan en sluiten** selecteren om de voorspelling als concept op te slaan. U vindt de conceptvoorspelling op het tabblad **Mijn voorspellingen** om door te gaan.

1. Voer het aantal dagen in om verloop te definiëren in het veld **Een klant is verlopen als hij geen aankopen heeft gedaan in:**. Als een klant bijvoorbeeld in de afgelopen 30 dagen geen aankopen heeft gedaan, kan deze voor uw bedrijf als verlopen worden beschouwd. 

1. Selecteer **Volgende** om door te gaan.

### <a name="add-required-data"></a>Vereiste gegevens toevoegen

1. Selecteer **Gegevens toevoegen** en kies in het zijvenster het type activiteit met de vereiste gegevens van de transactie- of aankoopgeschiedenis.

1. Kies onder **De activiteiten kiezen** de specifieke activiteiten van de geselecteerde activiteit waarop de berekening moet worden gericht.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Zijvenster met het kiezen van specifieke activiteiten onder het semantische type.":::

1. Als u de activiteit nog niet hebt toegewezen aan een semantisch type, selecteert u **Bewerken** om dat te doen. De begeleide ervaring voor het toewijzen van semantische activiteiten wordt geopend. Wijs uw gegevens toe aan de overeenkomende velden in het geselecteerde type activiteit.

   :::image type="content" source="media/product-recommendation-set-activity-type.PNG" alt-text="Activiteitstype pagina-instelling.":::

1. Selecteer na het toewijzen van de activiteit aan het corresponderende semantische type de optie **Volgende** om door te gaan

1. Wijs de semantische kenmerken toe aan de velden die nodig zijn om het model uit te voeren. Als de onderstaande velden niet zijn ingevuld, configureert u de relatie tussen de entiteit Aankoopgeschiedenis en de entiteit *Klant*.

1. Selecteer **Volgende**.

### <a name="select-prediction-level"></a>Voorspellingsniveau selecteren

De meeste voorspellingen worden op klantniveau gemaakt. In sommige situaties is dat misschien niet gedetailleerd genoeg om aan uw zakelijke behoeften te voldoen. U kunt deze functie gebruiken om bijvoorbeeld het verloop voor een filiaal van een klant te voorspellen, in plaats van voor de klant als geheel.

1. Om een voorspelling te maken op een gedetailleerder niveau dan de klant, selecteert u **Entiteit voor een secundair niveau selecteren**. Als de optie niet beschikbaar is, controleert u of u het vorige gedeelte hebt voltooid.

1. Vouw de entiteiten uit waarvan u het secundaire niveau wilt kiezen, of gebruik het zoekfiltervak om de geselecteerde opties te filteren.

1. Kies het kenmerk dat u als secundair niveau wilt gebruiken en selecteer vervolgens **Toevoegen**

1. Selecteer **Volgende**

> [!NOTE]
> De entiteiten die in deze sectie beschikbaar zijn, worden weergegeven omdat ze een relatie hebben met de entiteit die u in de vorige sectie hebt gekozen. Als u de entiteit niet ziet die u wilt toevoegen, zorg er dan voor dat deze een geldige relatie heeft in **Relaties**. Alleen één-op-één- en veel-op-één-relaties zijn geldig voor deze configuratie.

### <a name="add-additional-data-optional"></a>Aanvullende gegevens toevoegen (optioneel)

Configureer de relatie van uw klantactiviteitentiteit met de entiteit *Klant*.

1. Selecteer het veld dat de klant identificeert in de tabel Klantactiviteiten. Het kan rechtstreeks verband houden met de primaire klant-id van de entiteit *Klant*.

1. Selecteer de entiteit die uw primaire *Klant*-entiteit is.

1. Voer een naam in waarmee de relatie wordt omschreven.

#### <a name="customer-activities"></a>Klantactiviteiten

1. Selecteer eventueel **Gegevens toevoegen** bij **Klantactiviteiten**.

1. Selecteer het type semantische activiteit dat de gegevens bevat die u wilt gebruiken, en selecteer vervolgens een of meer activiteiten in de sectie **Activiteiten**.

1. Selecteer een activiteitstype dat overeenkomt met het type klantactiviteit dat u configureert. Selecteer **Nieuw maken** en kies een beschikbaar activiteitstype of maak een nieuw type aan.

1. Selecteer **Volgende** en vervolgens **Opslaan**.

1. Herhaal de bovenstaande stappen als u nog andere klantactiviteiten hebt die u wilt opnemen.

#### <a name="customers-data"></a>Klantgegevens

1. Optioneel, selecteer **Gegevens toevoegen** voor **Klantengegevens**.

1. Wijs de semantische kenmerken toe aan velden in uw eigen klantgegevens zoals geïdentificeerd. De gegevens in de gebruikte velden mogen niet vaak veranderen om de beste prestaties van het model te garanderen. Als u bijvoorbeeld een veld selecteert voor 'Classificatie' dat elke maand verandert, wordt alleen de laatste waarde gebruikt in de voorspelling, hoewel historisch gezien dezelfde waarde mogelijk niet van toepassing is op de klant bij het bouwen van de voorspellingpatronen.

1. Selecteer **Volgende**.

### <a name="provide-an-optional-list-of-benchmark-accounts-business-accounts-only"></a>Geef een optionele lijst met benchmarkaccounts op (alleen zakelijke accounts)

Voeg een lijst toe met uw zakelijke klanten en accounts die u als benchmarks wilt gebruiken. U krijgt [details voor deze benchmark-accounts](#review-a-prediction-status-and-results) inclusief hun verloopscore en de kenmerken die het meeste invloed hadden op hun verloopvoorspelling.

1. Selecteer **+ Klanten toevoegen**.

1. Kies de klanten die als benchmark fungeren.

1. Selecteer **Volgende** om door te gaan.

### <a name="set-schedule-and-review-configuration"></a>Schema instellen en configuratie bekijken

1. Stel een frequentie in voor het opnieuw trainen van uw model. Deze instelling is belangrijk om de nauwkeurigheid van voorspellingen bij te werken wanneer nieuwe gegevens worden opgenomen. De meeste bedrijven kunnen eenmaal per maand opnieuw trainen en krijgen een goede nauwkeurigheid voor hun voorspelling.

1. Selecteer **Volgende**.

1. Controleer de configuratie van de voorspelling. U kunt teruggaan naar eerdere stappen door **Bewerken** te selecteren onder de getoonde waarde. Of u kunt een configuratiestap selecteren vanuit de voortgangsindicator.

1. Selecteer **Opslaan en uitvoeren** om het voorspellingsproces te starten als alle waarden correct zijn geconfigureerd. Op het tabblad **Mijn voorspellingen** kunt u de status van uw voorspellingen bekijken. Het proces kan enkele uren in beslag nemen, afhankelijk van de hoeveelheid gegevens die in de voorspelling is gebruikt.

## <a name="review-a-prediction-status-and-results"></a>Een voorspellingsstatus en resultaten bekijken

1. Ga naar **Intelligence** > **Voorspellingen** en selecteer het tabblad **Mijn voorspellingen**.

1. Selecteer de voorspelling die u wilt beoordelen.
   - **Naam voorspelling**: naam van de voorspelling die bij het maken is opgegeven.
   - **Type voorspelling**: type model dat is gebruikt voor de voorspelling
   - **Uitvoerentiteit**: naam van de entiteit om de uitvoer van de voorspelling op te slaan. U kunt een entiteit met deze naam vinden onder **Gegevens** > **Entiteiten**.
     In de uitvoerentiteit is *ChurnScore* de voorspelde waarschijnlijkheid van verloop en *IsChurn* een binair label gebaseerd op *ChurnScore* met een drempel van 0,5. De standaarddrempel werkt mogelijk niet voor uw scenario. [Maak een nieuw segment](segments.md#create-a-new-segment) met uw gewenste drempel.
     Niet alle klanten hoeven actieve klanten te zijn. Sommigen van hen hebben misschien al een lange tijd geen activiteit gehad en worden al als verlopen beschouwd, op basis van uw verloopdefinitie. Het voorspellen van het verlooprisico voor klanten die al verloop vertonen, is niet nuttig omdat ze geen doelgroep van belang zijn.
   - **Veld Voorspeld**: dit veld wordt alleen ingevuld voor bepaalde soorten voorspellingen en wordt niet gebruikt bij verloopvoorspelling.
   - **Status**: de status of the voorspellingsuitvoering.
        - **In de wachtrij**: voorspelling wacht tot andere processen worden uitgevoerd.
        - **Vernieuwen**: de voorspelling wordt momenteel uitgevoerd en zal resultaten produceren die naar de uitvoerentiteit zullen stromen.
        - **Mislukt**: voorspellingsuitvoering is mislukt. [Controleer de logbestanden](manage-predictions.md#troubleshoot-a-failed-prediction) voor meer informatie.
        - **Geslaagd**: de voorspelling is geslaagd. Selecteer **Weergave** onder de verticale puntjes om de voorspelling te beoordelen
   - **Bewerkt**: de datum waarop de configuratie voor de voorspelling is gewijzigd.
   - **Laatst vernieuwd**: de datum waarop de voorspelling is vernieuwd resulteert in de uitvoerentiteit.

1. Selecteer de verticale puntjes naast de voorspelling waarvoor u de resultaten wilt beoordelen en selecteer **Weergave**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Weergeven om de resultaten van een voorspelling te zien.":::

1. Er zijn drie primaire gegevenssecties op de resultatenpagina:
   - **Prestaties trainingsmodel**: mogelijke scores zijn A, B of C. Deze score geeft de prestatie van de voorspelling aan en kan u helpen de beslissing te nemen om gebruik te maken van de resultaten die in de uitvoerentiteit zijn opgeslagen. Scores worden bepaald op basis van de volgende regels: 
        - **A** wanneer het model nauwkeurig ten minste 50% van de totale voorspellingen heeft voorspeld, en wanneer het percentage nauwkeurige voorspellingen voor verlopen klanten met ten minste 10% groter is dan het basislijnpercentage.
            
        - **B** wanneer het model nauwkeurig ten minste 50% van de totale voorspellingen heeft voorspeld, en wanneer het percentage nauwkeurige voorspellingen voor verlopen klanten tot 10% groter is dan het basislijnpercentage.
            
        - **C** wanneer het model nauwkeurig minder dan 50% van de totale voorspellingen heeft voorspeld, of wanneer het percentage nauwkeurige voorspellingen voor verlopen klanten minder is dan het basislijnpercentage.
               
        - **Basislijn** neemt de invoer van het voorspellingstijdvenster voor het model (bijvoorbeeld een jaar), en het model deelt de tijd in fracties door deze door 2 te delen totdat de tijdsperiode van een maand of minder wordt bereikt. Het gebruikt deze breuken om een bedrijfsregel te maken voor klanten die in dit tijdsbestek niets hebben gekocht. Deze klanten worden als verlopen beschouwd. De op tijd gebaseerde bedrijfsregel met de hoogste kans om te goed voorspellen wie waarschijnlijk zal verlopen, wordt gekozen als basislijnmodel.
            
    - **Waarschijnlijkheid van verloop (aantal klanten)**: groepen klanten op basis van hun voorspelde verlooprisico. Deze gegevens kunnen u later helpen als u een klantensegment wilt maken met een hoog verlooprisico. Dergelijke segmenten helpen u te begrijpen waar uw grens voor segmentlidmaatschap moet liggen.
       
    - **Meest invloedrijke factoren**: er zijn veel factoren waarmee rekening wordt gehouden bij het maken van uw voorspelling. Voor elke factor wordt het belang berekend van de gecombineerde voorspellingen die een model maakt. U kunt deze factoren gebruiken om de resultaten van uw voorspelling te valideren, of u kunt deze informatie later gebruiken om [segmenten te maken](segments.md) die het verlooprisico voor klanten kunnen helpen beïnvloeden.


1. Voor zakelijke accounts vindt u een informatiepagina over **Analyse van invloedrijke functies**. Deze bevat vier secties met gegevens:

    - Het item dat in het rechterdeelvenster is geselecteerd, bepaalt de inhoud op deze pagina. Selecteer een item in **Topklanten** of **Benchmarkklanten**. Beide lijsten zijn gerangschikt op afnemende waarde van de verloopscore, of de score nu alleen voor de klant is of een gecombineerde score is voor klanten en een secundair niveau zoals productcategorie.
        
        - **Topklanten**: lijst van 10 klanten met het hoogste risico op klantverloop en het laagste risico op klantverloop op basis van hun klantverloopscore. 
        - **Benchmarklanten**: lijst met maximaal 10 klanten die zijn geselecteerd bij het configureren van het model.
 
    - **Verloopscore:** weergave van de verloopscore voor het geselecteerde item in het rechterdeelvenster.
    
    - **Verdeling van verlooprisico:** weergave van verdeling van verlooprisico over klanten en het percentiel waarin de geselecteerde klant zich bevindt. 
    
    - **Belangrijke functies die het risico op verloop verhogen en verlagen:** voor het geselecteerde item in het rechterdeelvenster worden de top vijf kenmerken weergegeven die het verlooprisico hebben verhoogd en verlaagd. Voor elke invloedrijke feature vind je de waarde van de feature voor dat item en de invloed ervan op de verloopscore. De gemiddelde waarde van elk kenmerk in de segmenten met een laag, gemiddeld en hoog klantverloop wordt ook weergegeven. Het helpt om de waarden van de belangrijkste invloedrijke functies voor het geselecteerde item beter te contextualiseren en te vergelijken met klantsegmenten met een laag, gemiddeld en hoog verloop.

       - Laag: accounts of combinaties van account en secundair niveau met een verloopscore tussen 0 en 0,33
       - Gemiddeld: accounts of combinaties van accounts en secundaire niveaus met een verloopscore tussen 0,33 en 0,66
       - Hoog: accounts of combinaties van accounts en secundaire niveaus met een verloopscore groter dan 0,66
    
       Wanneer u klantverloop op accountniveau voorspelt, worden alle accounts in aanmerking genomen bij het afleiden van de gemiddelde kenmerkwaarden voor klantverloopsegmenten. Voor verloopvoorspellingen op secundair niveau voor elk account, hangt de afleiding van verloopsegmenten af van het secundair niveau van het item dat in het deelvenster is geselecteerd. Als een artikel bijvoorbeeld een secundair niveau van productcategorie = kantoorbenodigdheden heeft, worden alleen de artikelen met kantoorbenodigdheden als productcategorie in aanmerking genomen bij het bepalen van de gemiddelde kenmerkwaarden voor verloopsegmenten. Deze logica wordt toegepast om te zorgen voor een eerlijke vergelijking van de kenmerkwaarden van het item met de gemiddelde waarden over de segmenten met laag, gemiddeld en hoog verloop.

       In sommige gevallen is de gemiddelde waarde van segmenten met laag, gemiddeld of hoog verloop leeg of niet beschikbaar omdat er geen items zijn die behoren tot de overeenkomstige verloopsegmenten op basis van de bovenstaande definitie.

## <a name="manage-predictions"></a>Voorspellingen beheren

Het is mogelijk om voorspellingen te optimaliseren, problemen op te lossen, voorspellingen te vernieuwen of deze te verwijderen. Bekijk een bruikbaarheidsrapport voor invoergegevens om erachter te komen hoe u een voorspelling sneller en betrouwbaarder kunt maken. Ga voor meer informatie naar [Voorspellingen beheren](manage-predictions.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
