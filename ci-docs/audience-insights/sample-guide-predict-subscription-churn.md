---
title: Voorbeeldhandleiding abonnementsverloop voorspellen
description: Gebruik deze voorbeeldhandleiding om het standaard voorspellingsmodel voor abonnementsverloop uit te proberen.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2537cfb5dde0d1ce1af16f585f0bf91d15ea1870
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/01/2020
ms.locfileid: "4653974"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a>Voorbeeldhandleiding abonnementsverloop voorspellen (preview)

We laten u een compleet voorbeeld van abonnementsverloop-voorspelling zien aan de hand van de onderstaande voorbeeldgegevens. 

## <a name="scenario"></a>Scenario

Contoso is een bedrijf dat koffie- en koffiemachines van hoge kwaliteit produceert, die ze verkopen via hun Contoso Coffee-website. Onlangs zijn ze begonnen met een abonnementsbedrijf voor hun klanten om regelmatig koffie te halen. Hun doel is om te begrijpen welke geabonneerde klanten hun abonnement in de komende maanden kunnen opzeggen. Weten welke van hun klanten **waarschijnlijk zal verlopen**, kan hen helpen zich marketinginspanningen te besparen door zich te concentreren op het behouden van hun klanten.

## <a name="prerequisites"></a>Vereisten

- Minimaal [inzendermachtigingen](permissions.md) in Customer Insights.
- We raden u aan de volgende stappen te implementeren [in een nieuwe omgeving](manage-environments.md).

## <a name="task-1---ingest-data"></a>Taak 1 - Gegevens opnemen

Lees vooral de artikelen [over gegevensopname](data-sources.md) en [gegevensbronnen importeren met Power Query-connectors](connect-power-query.md). Bij de volgende informatie wordt ervan uitgegaan dat u bekend bent met opnemen van gegevens in het algemeen. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Klantgegevens opnemen van het e-commerceplatform

1. Maak een gegevensbron met de naam **eCommerce**, kies de importoptie en selecteer de connector **Tekst/CSV**.

1. Voer de URL in voor eCommerce-contacten in https://aka.ms/ciadclasscontacts.

1. Selecteer tijdens het bewerken van de gegevens **Transformeren** en dan **De eerste rij als kopteksten gebruiken**.

1. Werk het gegevenstype voor de onderstaande kolommen bij:

   - **DateOfBirth**: datum
   - **CreatedOn**: datum/tijd/zone

   [!div class="mx-imgBorder"]
   ![DoB transformeren naar datum](media/ecommerce-dob-date.PNG "geboortedatum naar datum transformeren")

1. Wijzig in het veld 'Naam' in het rechterdeelvenster uw gegevensbron van **Query** in **eCommerceContacts**.

1. Sla de gegevensbron op.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Klantgegevens opnemen uit het loyaliteitsschema

1. Maak een gegevensbron met de naam **LoyaltyScheme**, kies de importoptie en selecteer de connector **Tekst/CSV**.

1. Voer de URL in voor eCommerce-contacten in https://aka.ms/ciadclasscustomerloyalty.

1. Selecteer tijdens het bewerken van de gegevens **Transformeren** en dan **De eerste rij als kopteksten gebruiken**.

1. Werk het gegevenstype voor de onderstaande kolommen bij:

   - **DateOfBirth**: datum
   - **RewardsPoints**: geheel getal
   - **CreatedOn**: datum/tijd

1. Wijzig in het veld 'Naam' in het rechterdeelvenster uw gegevensbron van **Query** in **loyCustomers**.

1. Sla de gegevensbron op.

### <a name="ingest-subscription-information"></a>Abonnementsgegevens opnemen

1. Maak een gegevensbron met de naam **Abonnementsgeschiedenis**, kies de importoptie en selecteer de connector **Tekst/CSV**.

1. Voer de URL in voor eCommerce-contacten in https://aka.ms/ciadchurnsubscriptionhistory.

1. Selecteer tijdens het bewerken van de gegevens **Transformeren** en dan **De eerste rij als kopteksten gebruiken**.

1. Werk het gegevenstype voor de onderstaande kolommen bij:

   - **SubscriptioID**: geheel getal
   - **SubscriptionAmount**: valuta
   - **SubscriptionEndDate**: datum/tijd
   - **SubscriptionStartDate**: datum/tijd
   - **TransactionDate**: datum/tijd
   - **IsRecurring**: waar/onwaar
   - **Is_auto_renew**: waar/onwaar
   - **RecurringFrequencyInMonths**: geheel getal

1. Wijzig in het veld 'Naam' in het rechterdeelvenster uw gegevensbron van **Query** in **Abonnementsgeschiedenis**.

1. Sla de gegevensbron op.

### <a name="ingest-customer-data-from-website-reviews"></a>Klantgegevens van website-reviews opnemen

1. Maak een gegevensbron met de naam **Website**, kies de importoptie en selecteer de connector **Tekst/CSV**.

1. Voer de URL in voor eCommerce-contacten in https://aka.ms/ciadclasswebsite.

1. Selecteer tijdens het bewerken van de gegevens **Transformeren** en dan **De eerste rij als kopteksten gebruiken**.

1. Werk het gegevenstype voor de onderstaande kolommen bij:

   - **ReviewRating**: geheel getal
   - **ReviewDate**: datum

1. Wijzig in het veld 'Naam' in het rechterdeelvenster uw gegevensbron van **Query** in **Webreviews**.

## <a name="task-2---data-unification"></a>Taak 2 - Gegevensharmonisatie

Na het opnemen van de gegevens beginnen we nu met het proces **Toewijzen, Matchen, Samenvoegen** om een geharmoniseerd klantprofiel te maken. Zie [Gegevensharmonisatie](data-unification.md) voor meer informatie.

### <a name="map"></a>Toewijzen

1. Na het opnemen van de gegevens, wijst u contacten uit eCommerce en Loyaliteitsgegevens toe aan veelgebruikte gegevenstypen. Ga naar **Gegevens** > **Unify** > **Toewijzen**.

1. Selecteer de entiteiten die het klantprofiel vertegenwoordigen: **eCommerceContacts** en **loyCustomers**. 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="harmoniseer eCommerce- en loyaliteitsgegevensbronnen.":::

1. Selecteer **ContactId** als de primaire sleutel voor **eCommerceContacts** en **LoyaltyID** als de primaire sleutel voor **loyCustomers**.

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Harmoniseer LoyaltyId als primaire sleutel.":::

### <a name="match"></a>Bij elkaar zoeken

1. Ga naar het tabblad **Matchen** en selecteer **Volgorde instellen**.

1. Kies in de vervolgkeuzelijst **Primair** de optie **eCommerceContacts: eCommerce** als primaire bron en neem alle records op.

1. Kies in de vervolgkeuzelijst **Entiteit 2** de optie **loyCustomers: LoyaltyScheme** en neem alle records op.

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Harmoniseer match eCommerce en Loyaliteit":::

1. Selecteer **Een nieuwe regel maken**

1. Voeg uw eerste voorwaarde toe met FullName.

   * Selecteer voor eCommerceContacts **FullName** in de vervolgkeuzelijst.
   * Selecteer voor loyCustomers **FullName** in de vervolgkeuzelijst.
   * Selecteer de vervolgkeuzelijst **Normaliseren** en kies **Type (telefoon, naam, adres, ...)**.
   * Stel **Precisieniveau**: **Basic** en **Waarde**: **Hoog** in.

1. Voer de naam **FullName, Email** in voor de nieuwe regel.

   * Voeg een tweede voorwaarde voor het e-mailadres toe door **Voorwaarde toevoegen** te selecteren
   * Kies voor entiteit eCommerceContacts **EMail** in de vervolgkeuzelijst.
   * Kies voor entiteit loyCustomers **EMail** in de vervolgkeuzelijst. 
   * Laat Normaliseren leeg. 
   * Stel **Precisieniveau**: **Basic** en **Waarde**: **Hoog** in.

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Harmoniseer de matchregel voor naam en e-mailadres.":::

7. Selecteer **Opslaan** en **Uitvoeren**.

### <a name="merge"></a>Samenvoeging

1. Ga naar het tabblad **Samenvoegen**.

1. Bij **ContactId** voor de entiteit **loyCustomers** wijzigt u de weergavenaam in **ContactIdLOYALTY** om deze te onderscheiden van de andere opgenomen id's.

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="hernoem contactid van loyaliteits-id.":::

1. Selecteer **Opslaan** en **Uitvoeren** om het samenvoegingsproces te starten.


## <a name="task-3---configure-the-subscription-churn-prediction"></a>Taak 3 - Configureer de voorspelling van het abonnementsverloop

Met de geharmoniseerde klantprofielen op hun plaats, kunnen we nu het abonnementsverloop voorspellen. Zie het artikel [Abonnementsverloop voorspellen (preview)](predict-subscription-churn.md) voor gedetailleerde stappen. 

1. Ga naar **Intelligence** > **Ontdekken** en selecteer het **Klantverloopmodel**.

1. Selecteer de optie **Abonnement** en selecteer **Aan de slag**.

1. Geef het model de naam **OOB voorspelling abonnementsverloop** en de uitvoerentiteit **OOBSubscriptionChurnPrediction**.

1. Definieer twee voorwaarden voor het verloopmodel:

   * **Dagen sinds het einde van het abonnement**: **minstens 60** dagen. Als een klant zijn abonnement in deze periode niet verlengt nadat het abonnement is afgelopen, wordt de klant beschouwd als verlopen. 

   * **Definitie van verloop**: **minstens 93** dagen. De duur waarin volgens de voorspelling van het model klanten kunnen verlopen. Hoe verder u in de toekomst kijkt, hoe minder nauwkeurig de resultaten zijn.

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Selecteer de modelhendels Voorspellingsvenster en Definitie van verloop.":::

1. Selecteer **Vereiste gegevens toevoegen** en selecteer **Gegevens toevoegen** voor abonnementsgeschiedenis.

1. Voeg de entiteit **Subscription : SubscriptionHistory** toe en wijs de velden van eCommerce toe aan de overeenkomstige velden die vereist zijn voor het model.

1. Voeg de entiteit **Subscription : SubscriptionHistory** samen met **eCommerceContacts : eCommerce** en geef de relatie de naam **eCommerceSubscription**.

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Voeg eCommerce-entiteiten samen.":::

1. Voeg onder Klantactiviteiten de entiteitg **webReviews: Website** toe en wijs de velden van webReviews toe aan de overeenkomstige velden die vereist zijn voor het model. 
   - Primaire sleutel: ReviewId
   - Tijdstempel: ReviewDate
   - Gebeurtenis: ReviewRating

1. Configureer een activiteit voor website-reviews. Selecteer de activiteit **Review** en voeg de entiteit **webReviews: Website** samen met **eCommerceContacts: eCommerce**.

1. Selecteer **Volgende** om de modelplanning in te stellen.

   Het model moet regelmatig worden getraind om nieuwe patronen te leren wanneer er nieuwe gegevens worden opgenomen. Selecteer voor dit voorbeeld **Maandelijks**.

1. Selecteer nadat u alle details hebt nagekeken **Opslaan en uitvoeren**.

## <a name="task-4---review-model-results-and-explanations"></a>Taak 4 - Bekijk modelresultaten en uitleg

Laat het model de training en score van de gegevens voltooien. U kunt nu de uitleg van het abonnementverloopmodel bekijken. Zie [Een voorspellingsstatus en resultaten beoordelen](predict-subscription-churn.md#review-a-prediction-status-and-results) voor meer informatie.

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Taak 5 - Maak een segment van klanten met een hoog verlooprisico

Door het productiemodel uit te voeren, wordt een nieuwe entiteit gemaakt die u kunt zien in **Gegevens** > **Entiteiten**.   

U kunt een nieuw segment maken op basis van de entiteit die door het model is gemaakt.

1.  Ga naar **Segmenten**. Selecteer **Nieuw** en kies **Maken van** > **Intelligence**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Een segment maken met de modeluitvoer.":::

1. Selecteer het eindpunt **OOBSubscriptionChurnPrediction** en definieer het segment: 
   - Veld: ChurnScore
   - Operator: groter dan
   - Waarde: 0,6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Stel een segment abonnementverloop in.":::

U hebt nu een segment dat dynamisch wordt bijgewerkt en dat klanten met een hoog verlooprisico identificeert voor dit abonnementsbedrijf.

Zie [Segmenten maken en beheren](segments.md) voor meer informatie.