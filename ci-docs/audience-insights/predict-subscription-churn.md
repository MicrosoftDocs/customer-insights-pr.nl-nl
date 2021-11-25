---
title: Voorspelling voor abonnementsverloop
description: Voorspel of het risico bestaat dat een klant niet langer gebruik zal maken van de abonnementsproducten of -services van uw bedrijf.
ms.date: 08/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f9397729d2f79d079b4dea2ee92d0823b6d987e4
ms.sourcegitcommit: fb9f118b4e16b5aabb3e503463efca21718f5d72
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/12/2021
ms.locfileid: "7799722"
---
# <a name="subscription-churn-prediction-preview"></a>Voorspelling voor abonnementsverloop (preview)

Voorspelling voor abonnementsverloop helpt voorspellen of het risico bestaat dat een klant niet langer gebruik zal maken van de abonnementsproducten of -services van uw bedrijf. U kunt een nieuwe voorspelling voor abonnementsverloop maken op de pagina **Informatie** > **Voorspellingen**. Selecteer **Mijn voorspellingen** om andere voorspellingen te bekijken die u hebt gemaakt.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Probeer de zelfstudie over abonnementsverloop voorspellen aan de hand van voorbeeldgegevens: [Voorbeeldhandleiding abonnementsverloop voorspellen](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Vereisten

- Minstens [Inzendermachtigingen](permissions.md).
- Zakelijke kennis om te begrijpen wat verloop voor uw bedrijf betekent. We ondersteunen op tijd gebaseerde verloopdefinities, wat betekent dat een klant enige tijd na beëindiging van een abonnement wordt geacht dit te hebben laten verlopen.
- Gegevens over uw abonnementen en hun geschiedenis:
    - Abonnements-id's om abonnementen te onderscheiden.
    - Klant-id's om abonnementen te koppelen aan uw klanten.
    - Gebeurtenisdatums voor abonnementen, die begindatums, einddatums en de datums waarop de abonnementsgebeurtenissen hebben plaatsgevonden definiëren.
    - Abonnementsinformatie om te bepalen of het een terugkerend abonnement is en hoe vaak het wordt verlengd.
    - Het semantische gegevensschema voor abonnementen vereist de volgende informatie:
        - **Abonnements-id:** een unieke id van een abonnement.
        - **Einddatum abonnement:** de datum waarop het abonnement voor de klant verloopt.
        - **Begindatum abonnement:** de datum waarop het abonnement voor de klant ingaat.
        - **Transactiedatum:** de datum waarop een abonnement is gewijzigd. Bijvoorbeeld een klant die een abonnement koopt of opzegt.
        - **Is het een terugkerend abonnement:** een booleaans veld waar/onwaar dat bepaalt of het abonnement wordt verlengd met dezelfde abonnements-id zonder tussenkomst van de klant
        - **Herhalingsfrequentie (in maanden):** voor terugkerende abonnementen is dit de periode waarvoor het abonnement wordt verlengd. Dit wordt weergegeven in maanden. Zo heeft een jaarabonnement dat automatisch elk jaar met een jaar wordt verlengd voor een klant bijvoorbeeld de waarde 12.
        - (Optioneel) **Abonnementsbedrag:** het bedrag dat een klant betaalt voor de verlenging van het abonnement. Het kan helpen bij het identificeren van patronen voor verschillende abonnementsniveaus.
- Gegevens over klantactiviteiten:
    - Activiteits-id's om activiteiten van hetzelfde type te onderscheiden.
    - Klant-id's om activiteiten te koppelen aan uw klanten.
    - Activiteitsinformatie met de naam en datum van de activiteit.
    - Het semantische gegevensschema voor klantactiviteiten omvat:
        - **Primaire sleutel:** een unieke id voor een activiteit. Bijvoorbeeld een websitebezoek of een gebruiksrecord die aangeeft dat de klant een aflevering van een tv-programma heeft bekeken.
        - **Tijdstempel:** de datum en tijd van de gebeurtenis die wordt geïdentificeerd door de primaire sleutel.
        - **Gebeurtenis:** de naam van de gebeurtenis die u wilt gebruiken. Een veld met de naam 'UserAction' in een streaming-videoservice kan bijvoorbeeld de waarde 'Bekeken' hebben.
        - **Details:** gedetailleerde informatie over de gebeurtenis. Een veld met de naam 'ShowTitle' in een streaming-videoservice kan bijvoorbeeld de waarde hebben van een video die door de klant is bekeken.
- Voorgestelde gegevenskenmerken:
    - Voldoende historische gegevens: abonnementsgegevens voor minimaal het dubbele van het geselecteerde tijdvenster. Bij voorkeur twee tot drie jaar abonnementsgegevens.
    - Abonnementsstatus: gegevens omvatten actieve en inactieve abonnementen voor elke klant, dus er zijn meerdere vermeldingen per klant-id.
    - Aantal klanten: minimaal 10 klantprofielen, bij voorkeur meer dan 1.000 unieke klanten. Het model zal mislukken met minder dan 10 klanten en onvoldoende historische gegevens.
    - Compleetheid van gegevens: minder dan 20% ontbrekende waarden in het gegevensveld van de opgegeven entiteit.
   
   > [!NOTE]
   > U hebt minimaal twee activiteitsrecords nodig voor 50% van de klanten waarvoor u het verloop wilt berekenen.

## <a name="create-a-subscription-churn-prediction"></a>Een voorspelling voor abonnementsverloop maken

1. Ga in doelgroepinzichten naar **Intelligence** > **Voorspellingen**.
1. Selecteer de tegel **Abonnementsverloopmodel (preview)** en selecteer **Dit model gebruiken**.
   > [!div class="mx-imgBorder"]
   > ![Tegel Abonnementverloopmodel met knop Dit model gebruiken.](media/subscription-churn-usethismodel.PNG "Tegel Abonnementverloopmodel met knop Dit model gebruiken")

### <a name="name-model"></a>Model een naam geven

1. Geef het model een naam om het van andere modellen te onderscheiden.
1. Geef een naam op voor de uitvoerentiteit met alleen letters en cijfers, zonder spaties. Dat is de naam die de modelentiteit zal gebruiken. Selecteer vervolgens **Volgende**.

### <a name="define-customer-churn"></a>Klantverloop definiëren

1. Voer het aantal **Dagen sinds het abonnement is beëindigd** in waarna het bedrijf het abonnement van een klant als verlopen beschouwt. Deze periode is meestal gekoppeld aan zakelijke activiteiten zoals aanbiedingen of andere marketinginspanningen om te voorkomen dat de klant verloren gaat.
1. Voer het aantal **Dagen om de toekomst te kijken om verloop te voorspellen** in om een venster in te stellen voor het voorspellen van verloop. Bijoorbeeld om het risico van klantverloop voor uw klanten in de komende 90 dagen te voorspellen voor afstemming van uw marketinginspanningen tot behoud. Het voorspellen van het verlooprisico voor langere of kortere perioden kan het moeilijker maken om de factoren in uw verlooprisicoprofiel aan te pakken, afhankelijk van uw specifieke zakelijke vereisten. Selecteer **Volgende** om door te gaan
   >[!TIP]
   > U kunt op elk gewenst moment **Opslaan en sluiten** selecteren om de voorspelling als concept op te slaan. U vindt de conceptvoorspelling op het tabblad **Mijn voorspellingen** om door te gaan.

### <a name="add-required-data"></a>Vereiste gegevens toevoegen

1. Selecteer **Gegevens toevoegen** voor **Abonnementsgeschiedenis** en kies de entiteit die de informatie over de abonnementsgeschiedenis levert zoals beschreven in de [vereisten](#prerequisites).
1. Als de onderstaande velden niet zijn ingevuld, configureert u de relatie vanuit uw entiteit Abonnementsgeschiedenis met de entiteit Klant.
    1. Selecteer de **entiteit Abonnementsgeschiedenis**.
    1. Selecteer het **veld** dat de klant identificeert in de entiteit Abonnementsgeschiedenis. Het moet betrekking hebben op de primaire klant-id van uw entiteit Klant.
    1. Selecteer de **entiteit Klant** die overeenkomt met uw primaire klantentiteit.
    1. Voer een naam in waarmee de relatie wordt omschreven.
       > [!div class="mx-imgBorder"]
       > ![Pagina Abonnementsgeschiedenis waarop het maken van een relatie met de klant wordt getoond.](media/subscription-churn-subscriptionhistoryrelationship.PNG "Pagina Abonnementsgeschiedenis waarop het maken van een relatie met de klant wordt getoond")
1. Selecteer **Volgende**.
1. Wijs de semantische velden toe aan kenmerken binnen uw entiteit Abonnementsgeschiedenis en selecteer **Opslaan**. Zie de [vereisten](#prerequisites) voor beschrijvingen van de velden.
   > [!div class="mx-imgBorder"]
   > ![Pagina Abonnementsgeschiedenis met semantische kenmerken die zijn toegewezen aan velden in de geselecteerde entiteit voor abonnementsgeschiedenis.](media/subscription-churn-subscriptionhistorymapping.PNG "Pagina Abonnementsgeschiedenis met semantische kenmerken die zijn toegewezen aan velden in de geselecteerde entiteit voor abonnementsgeschiedenis")
1. Selecteer **Gegevens toevoegen** voor **Klantactiviteiten** en kies de entiteit die de informatie over de klantactiviteiten levert zoals beschreven in de vereisten.
1. Selecteer een activiteitstype dat overeenkomt met het type klantactiviteit dat u configureert.  Selecteer **Nieuwe maken** en geef een naam op als u geen optie ziet die overeenkomt met het activiteitstype dat u nodig hebt.
1. U moet de relatie tussen uw entiteit voor klantactiviteit en de entiteit Klant configureren.
    1. Selecteer het veld dat de klant identificeert in de tabel met klantactiviteiten, die rechtstreeks kan worden gerelateerd aan de primaire klant-id van uw entiteit Klant.
    1. Selecteer de entiteit Klant die overeenkomt met uw primaire entiteit Klant.
    1. Voer een naam in waarmee de relatie wordt omschreven.
1. Selecteer **Volgende**.
1. Wijs de semantische velden toe aan kenmerken binnen uw entiteit Klantactiviteit en selecteer **Opslaan**. Zie de [vereisten](#prerequisites) voor beschrijvingen van de velden.
1. (Optioneel) Herhaal de bovenstaande stappen als u nog andere klantactiviteiten hebt die u wilt opnemen.
   > [!div class="mx-imgBorder"]
   > ![Definieer de entiteitsrelatie.](media/subscription-churn-customeractivitiesmapping.PNG "Pagina Klantactiviteiten met semantische kenmerken die zijn toegewezen aan velden in de geselecteerde entiteit voor klantactiviteit")
1. Selecteer **Volgende**.

### <a name="set-schedule-and-review-configuration"></a>Schema instellen en configuratie bekijken

1. Stel een frequentie in voor het opnieuw trainen van uw model. Deze instelling is belangrijk om de nauwkeurigheid van voorspellingen bij te werken wanneer nieuwe gegevens worden opgenomen in doelgroepinzichten. De meeste bedrijven kunnen eenmaal per maand opnieuw trainen en krijgen een goede nauwkeurigheid voor hun voorspelling.
1. Selecteer **Volgende**.
1. Bekijk de configuratie. U kunt teruggaan naar elk willekeurig deel van de voorspellingsconfiguratie door **Bewerken** te selecteren onder de weergegeven waarde. Of u kunt een configuratiestap selecteren vanuit de voortgangsindicator.
1. Selecteer **Opslaan en uitvoeren** om het voorspellingsproces te starten als alle waarden correct zijn geconfigureerd. Op het tabblad **Mijn voorspellingen** kunt u de status van uw voorspellingen bekijken. Het proces kan enkele uren in beslag nemen, afhankelijk van de hoeveelheid gegevens die in de voorspelling is gebruikt.

## <a name="review-a-prediction-status-and-results"></a>Een voorspellingsstatus en resultaten bekijken

1. Ga naar het tabblad **Mijn voorspellingen** in **Informatie** > **Voorspellingen**.
   > [!div class="mx-imgBorder"]
   > ![Weergave van de pagina Mijn voorspellingen.](media/subscription-churn-mypredictions.PNG "Weergave van de pagina Mijn voorspellingen")
1. Selecteer de voorspelling die u wilt beoordelen.
   - **Voorspellingsnaam:** de naam van de voorspelling die is opgegeven bij het maken ervan.
   - **Voorspellingstype:** het type model dat voor de voorspelling is gebruikt
   - **Uitvoerentiteit:** naam van de entiteit om de uitvoer van de voorspelling op te slaan. U kunt een entiteit met deze naam vinden onder **Gegevens** > **Entiteiten**.    
     In de uitvoerentiteit is *ChurnScore* de voorspelde waarschijnlijkheid van verloop en *IsChurn* een binair label gebaseerd op *ChurnScore* met een drempel van 0,5. De standaarddrempel werkt mogelijk niet voor uw scenario. [Maak een nieuw segment](segments.md#create-a-new-segment) met uw gewenste drempel.
   - **Voorspeld veld:** dit veld wordt alleen ingevuld voor sommige typen voorspellingen en wordt niet gebruikt in de voorspelling voor abonnementsverloop.
   - **Status:** de huidige status van de uitvoering van de voorspelling.
        - **In wachtrij:** de voorspelling wacht momenteel op het uitvoeren van andere processen.
        - **Vernieuwen:** de voorspelling is momenteel bezig met het 'scorefase' van de verwerking om resultaten te produceren die naar de uitvoerentiteit zullen worden overgebracht.
        - **Mislukt:** de voorspelling is mislukt. Selecteer **Logboeken** voor nadere details.
        - **Geslaagd:** de voorspelling is geslaagd. Selecteer **Weergave** onder de verticale puntjes om de voorspelling te beoordelen
   - **Bewerkt:** de datum waarop de configuratie voor de voorspelling is gewijzigd.
   - **Laatst vernieuwd:** de datum waarop de voorspelling is vernieuwd resulteert in de uitvoerentiteit.
1. Selecteer de verticale puntjes naast de voorspelling waarvoor u de resultaten wilt beoordelen en selecteer **Weergave**.
   > [!div class="mx-imgBorder"]
   > ![Weergave van opties in het menu met verticale puntjes voor een voorspelling, waaronder bewerken, vernieuwen, weergeven, logboeken en verwijderen.](media/subscription-churn-verticalellipses.PNG "Weergave van opties in het menu met verticale puntjes voor een voorspelling, waaronder bewerken, vernieuwen, weergeven, logboeken en verwijderen")
1. Er zijn drie primaire gegevenssecties op de resultatenpagina:
    1. **Prestaties trainingsmodel:** mogelijke scores zijn A, B of C. Deze score geeft de prestatie van de voorspelling aan en kan u helpen de beslissing te nemen om gebruik te maken van de resultaten die in de uitvoerentiteit zijn opgeslagen.
        - Scores worden bepaald op basis van de volgende regels:
            - **A** wanneer het model bij ten minste 50% van de totale voorspellingen nauwkeurig is geweest en wanneer het percentage nauwkeurige voorspellingen voor klanten die verloren zijn gegaan minstens 10% van het historische gemiddelde verlooppercentage groter is dan het historische gemiddelde verlooppercentage.
            - **B** wanneer het model bij ten minste 50% van de totale voorspellingen nauwkeurig is geweest wanneer het percentage nauwkeurige voorspellingen voor klanten die verloren zijn gegaan tot 10% van het historische gemiddelde verlooppercentage groter is dan het historische gemiddelde verlooppercentage.
            - **C** wanneer het model bij minder dan 50% van de totale voorspellingen nauwkeurig is geweest of wanneer het percentage nauwkeurige voorspellingen voor klanten die verloren gaan lager is dan het historisch gemiddelde verlooppercentage.
               > [!div class="mx-imgBorder"]
               > ![Weergave van het modelprestatieresultaat.](media/subscription-churn-modelperformance.PNG "Weergave van het modelprestatieresultaat")
    1. **Waarschijnlijkheid van verloop (aantal klanten):** groepen klanten op basis van hun voorspelde verlooprisico. Deze gegevens kunnen u later helpen als u een klantensegment wilt maken met een hoog verlooprisico. Dergelijke segmenten helpen u te begrijpen waar uw grens voor segmentlidmaatschap moet liggen.
       > [!div class="mx-imgBorder"]
       > ![Grafiek die de verdeling van de verloopresultaten toont, onderverdeeld in bereiken van 0-100%.](media/subscription-churn-resultdistribution.PNG "Grafiek die de verdeling van de verloopresultaten toont, onderverdeeld in bereiken van 0-100%")
    1. **Meest invloedrijke factoren:** er zijn veel factoren waarmee rekening wordt gehouden bij het maken van uw voorspelling. Voor elk van de factoren wordt het belang berekend bij de geaggregeerde voorspellingen die een model opstelt. U kunt deze factoren gebruiken om uw voorspellingsresultaten te valideren. Of u kunt deze informatie later gebruiken om [segmenten te maken](segments.md) die het klantverlooprisico kunnen helpen beïnvloeden.
       > [!div class="mx-imgBorder"]
       > ![Lijst met invloedrijke factoren en hun belang bij het voorspellen van het verloopresultaat.](media/subscription-churn-influentialfactors.PNG "Lijst met invloedrijke factoren en hun belang bij het voorspellen van het verloopresultaat")

## <a name="manage-predictions"></a>Voorspellingen beheren

Het is mogelijk om voorspellingen te optimaliseren, problemen op te lossen, voorspellingen te vernieuwen of deze te verwijderen. Bekijk een bruikbaarheidsrapport voor invoergegevens om erachter te komen hoe u een voorspelling sneller en betrouwbaarder kunt maken. Zie [Voorspellingen beheren](manage-predictions.md) voor meer informatie.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
