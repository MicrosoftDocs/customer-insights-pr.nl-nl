---
title: Abonnementsverloop voorspellen (bevat video)
description: Voorspel of het risico bestaat dat een klant niet langer gebruik zal maken van de abonnementsproducten of -services van uw bedrijf.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 7464707864c418bfcc625ddfd245622131434b33
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610230"
---
# <a name="predict-subscription-churn"></a>Abonnementsverloop voorspellen

Voorspel of het risico bestaat dat een klant niet langer gebruik zal maken van de abonnementsproducten of -services van uw bedrijf. Abonnementgegevens omvatten actieve en inactieve abonnementen voor elke klant, dus er zijn meerdere vermeldingen per klant-id.

U moet over zakelijke kennis beschikken om te begrijpen wat verloop voor uw bedrijf betekent. We ondersteunen op tijd gebaseerde verloopdefinities, wat betekent dat een klant enige tijd na beëindiging van een abonnement wordt geacht dit te hebben laten verlopen.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Probeer het voorspellen van abonnementsverloop uit aan de hand van voorbeeldgegevens: [Voorbeeldhandleiding voor voorspellen van abonnementsverloop](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Vereisten

- Minstens [Inzendermachtigingen](permissions.md).
- Minimaal 10 klantprofielen, bij voorkeur meer dan 1.000 unieke klanten.
- Klant-id. Dit is een unieke id om abonnementen aan uw klanten te koppelen.
- Abonnementsgegevens voor minimaal het dubbele van het geselecteerde tijdvenster. Bij voorkeur twee tot drie jaar abonnementsgegevens. De abonnementsgeschiedenis moet het volgende bevatten:
  - **Abonnements-id:** unieke id van een abonnement.
  - **Einddatum abonnement:** datum waarop het abonnement voor de klant verloopt.
  - **Begindatum abonnement:** datum waarop het abonnement voor de klant ingaat.
  - **Transactiedatum:** datum waarop een abonnement is gewijzigd. Bijvoorbeeld een klant die een abonnement koopt of opzegt.
  - **Is het een terugkerend abonnement:** Booleaans veld (waar/onwaar) dat bepaalt of het abonnement wordt verlengd met dezelfde abonnements-id zonder tussenkomst van de klant.
  - **Herhalingsfrequentie (in maanden):** voor terugkerende abonnementen is dit de maand waarin het abonnement wordt verlengd. Zo heeft een jaarabonnement dat automatisch elk jaar met een jaar wordt verlengd voor een klant bijvoorbeeld de waarde 12.
  - **Abonnementsbedrag**: bedrag dat een klant betaalt voor de verlenging van het abonnement. Het kan helpen bij het identificeren van patronen voor verschillende abonnementsniveaus.
- Minimaal twee activiteitsrecords voor 50% van de klanten waarvoor u het verloop wilt berekenen. Klantactiviteiten moeten het volgende bevatten:
  - **Primaire sleutel:** unieke id voor een activiteit. Bijvoorbeeld een websitebezoek of een gebruiksrecord die aangeeft dat de klant een aflevering van een tv-programma heeft bekeken.
  - **Tijdstempel:** datum en tijd van de gebeurtenis die wordt geïdentificeerd door de primaire sleutel.
  - **Gebeurtenis:** naam van de gebeurtenis die u wilt gebruiken. Een veld met de naam 'UserAction' in een streaming-videoservice kan bijvoorbeeld de waarde 'Bekeken' hebben.
  - **Details:** gedetailleerde informatie over de gebeurtenis. Een veld met de naam 'ShowTitle' in een streaming-videoservice kan bijvoorbeeld de waarde hebben van een video die door de klant is bekeken.
- Minder dan 20% ontbrekende waarden in het gegevensveld van de opgegeven entiteit.

## <a name="create-a-subscription-churn-prediction"></a>Een voorspelling voor abonnementsverloop maken

Selecteer **Concept opslaan** op elk gewenst moment om de voorspelling als concept op te slaan. De conceptvoorspelling wordt weergegeven op het tabblad **Mijn voorspellingen**.

1. Ga naar **Informatie** > **Voorspellingen**.

1. Selecteer op het tabblad **Maken** de optie **Model gebruiken** op de tegel **Klantverloopmodel**.

1. Selecteer **Abonnement** voor het type verloop en vervolgens **Aan de slag**.

1. **Geef dit model een naam** en de **Naam van uitvoerentiteit** om ze te onderscheiden van andere modellen of entiteiten.

1. Selecteer **Volgende**.

### <a name="define-customer-churn"></a>Klantverloop definiëren

1. Voer het aantal **Dagen sinds het abonnement is beëindigd** in waarna het bedrijf het abonnement van een klant als verlopen beschouwt. Deze periode is meestal gekoppeld aan zakelijke activiteiten zoals aanbiedingen of andere marketinginspanningen om te voorkomen dat de klant verloren gaat.

1. Voer het **aantal dagen dat u wilt vooruitkijken om het verloop te voorspellen** in. Voorspel bijvoorbeeld het verlooprisico voor uw klanten in de komende 90 dagen om deze op uw marketinginspanningen voor klantbehoud af te stemmen. Het voorspellen van het verlooprisico voor langere of kortere perioden kan het moeilijker maken om de factoren in uw verlooprisicoprofiel aan te pakken, afhankelijk van uw specifieke zakelijke vereisten.

1. Selecteer **Volgende**.

### <a name="add-required-data"></a>Vereiste gegevens toevoegen

1. Selecteer **Gegevens toevoegen** voor **Abonnementsgeschiedenis**.

1. Selecteer het semantische activiteitstype **Abonnement** dat de vereiste informatie over de abonnementsgeschiedenis bevat. Als de activiteit niet is ingesteld, selecteert u **hier** en maakt u deze.

1. Kies onder **Activiteiten**, als de activiteitskenmerken semantisch zijn toegewezen bij het maken van de activiteit, de specifieke kenmerken of entiteit waarop u de berekening wilt richten. Als er geen semantische toewijzing heeft plaatsgevonden, selecteert u **Bewerken** en wijst u uw gegevens toe.
  
   :::image type="content" source="media/subscription-churn-required.png" alt-text="Vereiste gegevens toevoegen voor abonnementsverloopmodel":::

1. Selecteer **Volgende** en bekijk de kenmerken die vereist zijn voor dit model.

1. Selecteer **Save**.

1. Selecteer **Gegevens toevoegen** voor **Klantactiviteiten**.

1. Selecteer het semantische activiteitstype dat de klantactiviteitsinformatie levert. Als de activiteit niet is ingesteld, selecteert u **hier** en maakt u deze.

1. Kies onder **Activiteiten**, als de activiteitskenmerken semantisch zijn toegewezen bij het maken van de activiteit, de specifieke kenmerken of entiteit waarop u de berekening wilt richten. Als er geen semantische toewijzing heeft plaatsgevonden, selecteert u **Bewerken** en wijst u uw gegevens toe.

1. Selecteer **Volgende** en bekijk de kenmerken die vereist zijn voor dit model.

1. Selecteer **Save**.

1. Voeg meer activiteiten toe of selecteer **Volgende**.

### <a name="set-update-schedule"></a>Updateplanning instellen

1. Kies de frequentie voor het opnieuw trainen van uw model. Deze instelling is belangrijk om de nauwkeurigheid van voorspellingen bij te werken wanneer nieuwe gegevens worden opgenomen in Customer Insights. De meeste bedrijven kunnen eenmaal per maand opnieuw trainen en krijgen een goede nauwkeurigheid voor hun voorspelling.

1. Selecteer **Volgende**.

### <a name="review-and-run-the-model-configuration"></a>De modelconfiguratie controleren en uitvoeren

De stap **Controleren en uitvoeren** toont een samenvatting van de configuratie en biedt een kans om wijzigingen aan te brengen voordat u de voorspelling maakt.

1. Selecteer **Bewerken** in een van de stappen om te controleren en eventuele wijzigingen aan te brengen.

1. Als u tevereden bent over uw selecties, selecteert u **Opslaan en uitvoeren** om te beginnen met het uitvoeren van het model. Selecteer **Gereed**. Het tabblad **Mijn voorspellingen** wordt weergegeven terwijl de voorspelling wordt gemaakt. Het proces kan enkele uren in beslag nemen, afhankelijk van de hoeveelheid gegevens die in de voorspelling is gebruikt.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Resultaten van voorspelling weergeven

1. Ga naar **Informatie** > **Voorspellingen**.

1. Selecteer op het tabblad **Mijn voorspellingen** de voorspelling die u wilt weergeven.

Er zijn drie primaire gegevenssecties op de resultatenpagina:

- **Prestaties trainingsmodel**: beoordelingscijfers A, B of C geven de prestaties van de voorspelling aan en kan u helpen bij het nemen van de beslissing om de resultaten te gebruiken die zijn opgeslagen in de uitvoerentiteit.
  
  :::image type="content" source="media/subscription-churn-modelperformance.PNG" alt-text="Afbeelding van het modelscore-informatievenster met het cijfer A.":::

  Cijfers worden bepaald op basis van de volgende regels:
  - **A** wanneer het model nauwkeurig ten minste 50% van de totale voorspellingen heeft voorspeld, en wanneer het percentage nauwkeurige voorspellingen voor verlopen klanten ten minste 10% groter is dan het historische gemiddelde verlooppercentage.
  - **B** wanneer het model nauwkeurig ten minste 50% van de totale voorspellingen heeft voorspeld, en wanneer het percentage nauwkeurige voorspellingen voor verlopen klanten tot 10% groter is dan het historische gemiddelde verlooppercentage.
  - **C** wanneer het model bij minder dan 50% van de totale voorspellingen nauwkeurig is geweest of wanneer het percentage nauwkeurige voorspellingen voor klanten die verloren gaan lager is dan het historisch gemiddelde verlooppercentage.
  
- **Waarschijnlijkheid van verloop (aantal klanten)**: groepen klanten op basis van hun voorspelde verlooprisico. Optioneel kunt u [segmenten van klanten maken](prediction-based-segment.md) met een hoog verlooprisico. Dergelijke segmenten helpen u te begrijpen waar uw grens voor segmentlidmaatschap moet liggen.  

  :::image type="content" source="media/subscription-churn-resultdistribution.PNG" alt-text="Grafiek die de verdeling van de verloopresultaten toont, onderverdeeld in bereiken van 0-100%":::

- **Meest invloedrijke factoren:** er zijn veel factoren waarmee rekening wordt gehouden bij het maken van uw voorspelling. Voor elke factor wordt het belang berekend van de gecombineerde voorspellingen die een model maakt. Gebruik deze factoren om uw voorspellingsresultaten te helpen valideren. Of gebruik deze informatie later om [segmenten te maken](.//prediction-based-segment.md) die het verlooprisico voor klanten kunnen helpen beïnvloeden.

  :::image type="content" source="media/subscription-churn-influentialfactors.PNG" alt-text="Lijst met invloedrijke factoren en hun belang bij het voorspellen van het verloopresultaat.":::

> [!NOTE]
> In de uitvoerentiteit voor dit model is *ChurnScore* de voorspelde waarschijnlijkheid van verloop en *IsChurn* een binair label gebaseerd op *ChurnScore* met een drempel van 0,5. Als deze standaarddrempel niet werkt voor uw scenario, [maakt u een nieuw segment](segments.md) met uw geprefereerde drempel. Als u de verloopscore wilt bekijken, gaat u naar **Gegevens** > **Entiteiten** en bekijkt u het gegevenstabblad voor de uitvoerentiteit die u voor dit model hebt gedefinieerd.

[!INCLUDE [footer-include](includes/footer-banner.md)]
