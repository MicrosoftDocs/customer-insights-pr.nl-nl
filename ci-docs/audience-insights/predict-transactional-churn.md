---
title: Transactieverloop voorspellen
description: Voorspel of het risico bestaat dat een klant de producten of services van uw bedrijf niet meer zal kopen.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: b0e587739f9f4d03942d70a72de4f9378822054d
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095596"
---
# <a name="transactional-churn-prediction-preview"></a>Transactieverloop voorspellen (preview)

Met deze functie kunt u voorspellen of een klant uw producten of services binnen een bepaald tijdsbestek niet meer zal kopen. U kunt nieuwe verloopvoorspellingen maken op **Intelligence** > **Voorspellingen**. Selecteer **Mijn voorspellingen** om andere voorspellingen te bekijken die u hebt gemaakt.

> [!TIP]
> Probeer de zelfstudie over transactieverloop voorspellen aan de hand van voorbeeldgegevens: [Voorbeeldhandleiding transactieverloop voorspellen](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Vereisten

- Minimaal [inzendermachtigingen](permissions.md) in Customer Insights.
- Zakelijke kennis om te begrijpen wat verloop voor uw bedrijf betekent. We ondersteunen op tijd gebaseerde verloopdefinities, wat betekent dat een klant na een periode zonder aankopen wordt beschouwd als verlopen.
- Gegevens over uw transacties/aankopen en hun geschiedenis:
    - Transactie-id's om aankopen/transacties te onderscheiden.
    - Klant-id's om transacties af te stemmen op uw klanten.
    - Transactiegebeurtenisdatums, die de datums definiëren waarop de transactie plaatsvond.
    - Het semantische gegevensschema voor aankopen/transacties vereist de volgende informatie:
        - **Transactie-id:** een unieke identificatie van een aankoop of transactie.
        - **Transactiedatum:** de datum van de aankoop of de transactie.
        - **Waarde van de transactie:** het bedrag in de valuta/numerieke waarde van de transactie/het item.
        - (Optioneel) **Unieke product-id:** de id van het gekochte product of de gekochte service als uw gegevens zich op regelitemniveau bevinden.
        - (Optioneel) **Of deze transactie een retour was:** een waar/onwaar-veld dat aangeeft of de transactie een retour was of niet. Als de **Waarde van de transactie** negatief is, gebruiken we deze informatie ook om een retour af te leiden.
- (Optioneel) Gegevens over klantactiviteiten:
    - Activiteits-id's om activiteiten van hetzelfde type te onderscheiden.
    - Klant-id's om activiteiten te koppelen aan uw klanten.
    - Activiteitsinformatie met de naam en datum van de activiteit.
    - Het semantische gegevensschema voor klantactiviteiten omvat:
        - **Primaire sleutel:** een unieke id voor een activiteit. Bijvoorbeeld een websitebezoek of een gebruiksrecord waaruit blijkt dat de klant een monster van uw product heeft geprobeerd.
        - **Tijdstempel:** de datum en tijd van de gebeurtenis die wordt geïdentificeerd door de primaire sleutel.
        - **Gebeurtenis:** de naam van de gebeurtenis die u wilt gebruiken. Een veld met de naam 'UserAction' in een supermarkt kan bijvoorbeeld een kortingsbon zijn die door de klant wordt gebruikt.
        - **Details:** gedetailleerde informatie over de gebeurtenis. Een veld met de naam 'CouponValue' in een supermarkt kan bijvoorbeeld de valutawaarde van de kortingsbon zijn.
- Voorgestelde gegevenskenmerken:
    - Voldoende historische gegevens: transactiegegevens voor minimaal het dubbele van het geselecteerde tijdvenster. Bij voorkeur twee tot drie jaar abonnementsgegevens. 
    - Meerdere aankopen per klant: idealiter ten minste twee transacties per klant.
    - Aantal klanten: minimaal 10 klantprofielen, bij voorkeur meer dan 1.000 unieke klanten. Het model zal mislukken met minder dan 10 klanten en onvoldoende historische gegevens.
    - Compleetheid van gegevens: minder dan 20% ontbrekende waarden in het gegevensveld van de opgegeven entiteit.

> [!NOTE]
> Voor een bedrijf met een hoge aankoopfrequentie van klanten (om de paar weken) wordt het aanbevolen om een korter voorspellingsvenster en verloopdefinitie te selecteren. Kies voor een lage aankoopfrequentie (om de paar maanden of eenmaal per jaar) een langer voorspellingsvenster en verloopdefinitie.

## <a name="create-a-transactional-churn-prediction"></a>Een voorspelling voor transactieverloop maken

1. Ga in Customer Insights naar **Informatie** > **Voorspellingen**.

1. Selecteer de tegel **Klantverloopmodel (preview)** en selecteer **Dit model gebruiken**.
   
1. Kies in het deelvenster **Klantverloopmodel** de optie **Transactie** en selecteer **Aan de slag**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Schermafbeelding met geselecteerde transactieoptie in het deelvenster Klantverloopmodel.":::

### <a name="name-model"></a>Model een naam geven

1. Geef het model een naam om het van andere modellen te onderscheiden.

1. Geef een naam op voor de uitvoerentiteit met alleen letters en cijfers, zonder spaties. Dat is de naam die de modelentiteit zal gebruiken. 

1. Selecteer **Volgende**.

### <a name="define-customer-churn"></a>Klantverloop definiëren

1. Stel een aantal dagen in om het verloop in het veld **Klanten identificeren die kunnen verlopen in de volgende**. Voorspel bijvoorbeeld het verlooprisico voor uw klanten in de komende 90 dagen om deze op uw marketinginspanningen voor klantbehoud af te stemmen. Het voorspellen van het verlooprisico voor een langere of kortere periode kan het moeilijker maken om de factoren in uw verlooprisicoprofiel mee te nemen, maar het hangt af van uw specifieke zakelijke vereisten. 
   >[!TIP]
   > U kunt op elk gewenst moment **Opslaan en sluiten** selecteren om de voorspelling als concept op te slaan. U vindt de conceptvoorspelling op het tabblad **Mijn voorspellingen** om door te gaan.

1. Voer het aantal dagen in om verloop te definiëren in het veld **Een klant is verlopen als hij geen aankopen heeft gedaan in:**. Als een klant bijvoorbeeld in de afgelopen 30 dagen geen aankopen heeft gedaan, kan deze voor uw bedrijf als verlopen worden beschouwd. 

1. Selecteer **Volgende** om door te gaan

### <a name="add-required-data"></a>Vereiste gegevens toevoegen

1. Selecteer **Gegevens toevoegen** voor **Aankoopgeschiedenis** en kies de entiteit die de transactie-/ aankoopgeschiedenisinformatie verstrekt, zoals beschreven in de [vereisten](#prerequisites).

1. Wijs de semantische velden toe aan kenmerken binnen uw aankoopgeschiedenis-entiteit en selecteer **Volgende**. Zie de [vereisten](#prerequisites) voor beschrijvingen van de velden.

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="Wijs semantische velden van de entiteit Aankoop toe.":::

1. Als de onderstaande velden niet zijn ingevuld, configureert u de relatie tussen de entiteit Aankoopgeschiedenis en de entiteit Klant.
    1. Selecteer de **entiteit Aankoopgeschiedenis**.
    1. Selecteer het **Veld** dat de klant identificeert in de entiteit Aankoopgeschiedenis. Het moet betrekking hebben op de primaire klant-id van uw entiteit Klant.
    1. Selecteer de **entiteit Klant** die overeenkomt met uw primaire klantentiteit.
    1. Voer een naam in waarmee de relatie wordt omschreven.

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="De pagina Aankoopgeschiedenis waarop het maken van een relatie met klant te zien is.":::
   
1. Selecteer **Volgende**.

1. Selecteer eventueel **Gegevens toevoegen** bij **Klantactiviteiten**. Kies de entiteit die de informatie over de klantactiviteit verstrekt, zoals beschreven in de vereisten.

1. Wijs de semantische velden toe aan kenmerken binnen de entiteit Klantactiviteiten en selecteer **Volgende**. Zie de [vereisten](#prerequisites) voor beschrijvingen van de velden.

   :::image type="content" source="media/map-transaction-data-fields.png" alt-text="Wijs klantvelden toe voor transactiegegevens.":::

1. Selecteer een activiteitstype dat overeenkomt met het type klantactiviteit dat u configureert. Selecteer **Nieuw maken** en kies een beschikbaar activiteitstype of maak een nieuw type aan.

1. U moet de relatie tussen uw entiteit voor klantactiviteit en de entiteit Klant configureren.
    1. Selecteer het veld dat de klant identificeert in de tabel Klantactiviteiten. Het kan rechtstreeks verband houden met de primaire klant-id van de entiteit Klant.
    1. Selecteer de entiteit Klant die overeenkomt met uw primaire entiteit Klant.
    1. Voer een naam in waarmee de relatie wordt omschreven.

1. Selecteer **Opslaan**.

1. Herhaal de bovenstaande stappen als u nog andere klantactiviteiten hebt die u wilt opnemen.

1. Selecteer **Volgende**.

### <a name="set-schedule-and-review-configuration"></a>Schema instellen en configuratie bekijken

1. Stel een frequentie in voor het opnieuw trainen van uw model. Deze instelling is belangrijk om de nauwkeurigheid van voorspellingen bij te werken wanneer nieuwe gegevens worden opgenomen. De meeste bedrijven kunnen eenmaal per maand opnieuw trainen en krijgen een goede nauwkeurigheid voor hun voorspelling.

1. Selecteer **Volgende**.

1. Controleer de configuratie van de voorspelling. U kunt teruggaan naar eerdere stappen door **Bewerken** te selecteren onder de getoonde waarde. Of u kunt een configuratiestap selecteren vanuit de voortgangsindicator.

1. Selecteer **Opslaan en uitvoeren** om het voorspellingsproces te starten als alle waarden correct zijn geconfigureerd. Op het tabblad **Mijn voorspellingen** kunt u de status van uw voorspellingen bekijken. Het proces kan enkele uren in beslag nemen, afhankelijk van de hoeveelheid gegevens die in de voorspelling is gebruikt.

## <a name="review-a-prediction-status-and-results"></a>Een voorspellingsstatus en resultaten bekijken

1. Ga naar **Intelligence** > **Voorspellingen** en selecteer het tabblad **Mijn voorspellingen**.

1. Selecteer de voorspelling die u wilt beoordelen.
   - **Naam voorspelling:** naam van de voorspelling die bij het maken is opgegeven.
   - **Type voorspelling:** type model dat is gebruikt voor de voorspelling
   - **Uitvoerentiteit:** naam van de entiteit om de uitvoer van de voorspelling op te slaan. U kunt een entiteit met deze naam vinden onder **Gegevens** > **Entiteiten**.    
     In de uitvoerentiteit is *ChurnScore* de voorspelde waarschijnlijkheid van verloop en *IsChurn* een binair label gebaseerd op *ChurnScore* met een drempel van 0,5. De standaarddrempel werkt mogelijk niet voor uw scenario. [Maak een nieuw segment](segments.md#create-a-new-segment) met uw gewenste drempel.
     Niet alle klanten hoeven actieve klanten te zijn. Sommigen van hen hebben misschien al een lange tijd geen activiteit gehad en worden al als verlopen beschouwd, op basis van uw verloopdefinitie. Het voorspellen van het verlooprisico voor klanten die al zijn verlopen is niet nuttig omdat ze niet de beoogde doelgroep zijn.
   - **Veld Voorspeld:** dit veld wordt alleen ingevuld voor bepaalde soorten voorspellingen en wordt niet gebruikt bij verloopvoorspelling.
   - **Status:** de status of the voorspellingsuitvoering.
        - **In de wachtrij:** voorspelling wacht tot andere processen worden uitgevoerd.
        - **Vernieuwen:** de voorspelling wordt momenteel uitgevoerd en zal resultaten produceren die naar de uitvoerentiteit zullen stromen.
        - **Mislukt:** voorspellingsuitvoering is mislukt. [Controleer de logbestanden](manage-predictions.md#troubleshoot-a-failed-prediction) voor meer informatie.
        - **Geslaagd:** de voorspelling is geslaagd. Selecteer **Weergave** onder de verticale puntjes om de voorspelling te beoordelen
   - **Bewerkt:** de datum waarop de configuratie voor de voorspelling is gewijzigd.
   - **Laatst vernieuwd:** de datum waarop de voorspelling is vernieuwd resulteert in de uitvoerentiteit.

1. Selecteer de verticale puntjes naast de voorspelling waarvoor u de resultaten wilt beoordelen en selecteer **Weergave**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Weergeven om de resultaten van een voorspelling te zien.":::   

1. Er zijn drie primaire gegevenssecties op de resultatenpagina:
    1. **Prestaties trainingsmodel:** mogelijke scores zijn A, B of C. Deze score geeft de prestatie van de voorspelling aan en kan u helpen de beslissing te nemen om gebruik te maken van de resultaten die in de uitvoerentiteit zijn opgeslagen. Scores worden bepaald op basis van de volgende regels:
         
         - **A** wanneer het model nauwkeurig ten minste 50% van de totale voorspellingen heeft voorspeld, en wanneer het percentage nauwkeurige voorspellingen voor verlopen klanten met ten minste 10% groter is dan het basislijnpercentage.
            
         - **B** wanneer het model nauwkeurig ten minste 50% van de totale voorspellingen heeft voorspeld, en wanneer het percentage nauwkeurige voorspellingen voor verlopen klanten tot 10% groter is dan het basislijnpercentage.
            
         - **C** wanneer het model nauwkeurig minder dan 50% van de totale voorspellingen heeft voorspeld, of wanneer het percentage nauwkeurige voorspellingen voor verlopen klanten minder is dan het basislijnpercentage.
               
         - **Basislijn** neemt de invoer van het voorspellingstijdvenster voor het model (bijvoorbeeld een jaar) en het model deelt de tijd in fracties door deze door 2 te delen totdat de tijdsperiode van een maand of minder wordt bereikt. Het gebruikt deze breuken om een bedrijfsregel te maken voor klanten die in dit tijdsbestek niets hebben gekocht. Deze klanten worden als verlopen beschouwd. De op tijd gebaseerde bedrijfsregel met de hoogste kans om te goed voorspellen wie waarschijnlijk zal verlopen, wordt gekozen als basislijnmodel.
            
    1. **Waarschijnlijkheid van verloop (aantal klanten):** groepen klanten op basis van hun voorspelde verlooprisico. Deze gegevens kunnen u later helpen als u een klantensegment wilt maken met een hoog verlooprisico. Dergelijke segmenten helpen u te begrijpen waar uw grens voor segmentlidmaatschap moet liggen.
       
    1. **Meest invloedrijke factoren:** er zijn veel factoren waarmee rekening wordt gehouden bij het maken van uw voorspelling. Voor elke factor wordt het belang berekend van de gecombineerde voorspellingen die een model maakt. U kunt deze factoren gebruiken om uw voorspellingsresultaten te valideren. Of u kunt deze informatie later gebruiken om [segmenten te maken](segments.md) die het klantverlooprisico kunnen helpen beïnvloeden.

## <a name="manage-predictions"></a>Voorspellingen beheren

Het is mogelijk om voorspellingen te optimaliseren, problemen op te lossen, voorspellingen te vernieuwen of deze te verwijderen. Bekijk een bruikbaarheidsrapport voor invoergegevens om erachter te komen hoe u een voorspelling sneller en betrouwbaarder kunt maken. Zie [Voorspellingen beheren](manage-predictions.md) voor meer informatie.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
