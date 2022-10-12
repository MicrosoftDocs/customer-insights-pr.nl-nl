---
title: Voorbeeldhandleiding abonnementsverloop voorspellen
description: Gebruik deze voorbeeldhandleiding om het standaard voorspellingsmodel voor abonnementsverloop uit te proberen.
ms.date: 09/19/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 7e754be9a2cb9450949c6b3667bbd37aa39cf0bf
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610000"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Voorbeeldhandleiding abonnementsverloop voorspellen

Deze gids leidt u door een compleet voorbeeld van voorspelling van abonnementsverloop aan de hand van de voorbeeldgegevens. We raden u aan deze voorspelling uit te proberen [in een nieuwe omgeving](manage-environments.md).

## <a name="scenario"></a>Scenario

Contoso is een bedrijf dat hoogwaardige koffie en koffiemachines produceert. Ze verkopen de producten via hun Contoso Coffee-website. Onlangs zijn ze begonnen met een abonnementsbedrijf voor hun klanten om regelmatig koffie te halen. Hun doel is om te begrijpen welke geabonneerde klanten hun abonnement in de komende maanden kunnen opzeggen. Weten welke van hun klanten **waarschijnlijk zal verlopen**, kan hen helpen zich marketinginspanningen te besparen door zich te concentreren op het behouden van hun klanten.

## <a name="prerequisites"></a>Vereisten

- Minimaal [inzendermachtigingen](permissions.md) in Customer Insights.

## <a name="task-1---ingest-data"></a>Taak 1 - Gegevens opnemen

Lees de artikelen [over gegevensopname](data-sources.md) en [verbinding met een Power Query-gegevensbron](connect-power-query.md). Bij de volgende informatie wordt ervan uitgegaan dat u vertrouwd bent met opnemen van gegevens in het algemeen.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Klantgegevens opnemen van het e-commerceplatform

1. Maak een Power Query-gegevensbron met de naam **eCommerce** en selecteer de connector **Tekst/CSV**.

1. Voer de URL in voor eCommerce-contacten in https://aka.ms/ciadclasscontacts.

1. Selecteer tijdens het bewerken van de gegevens de optie **Transformeren** en vervolgens **Eerste rij als kolomkoppen gebruiken**.

1. Werk het gegevenstype voor de onderstaande kolommen bij:
   - **DateOfBirth**: datum
   - **CreatedOn**: datum/tijd/zone

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformeer geboortedatum naar datum.":::

1. Wijzig in het veld **Naam** in het rechterdeelvenster uw gegevensbron in **eCommerceContacts**.

1. Sla de gegevensbron op.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Klantgegevens opnemen uit het loyaliteitsschema

1. Maak een gegevensbron met de naam **LoyaltyScheme** en selecteer de connector **Tekst/CSV**.

1. Voer de URL voor loyaliteitsklanten in: https://aka.ms/ciadclasscustomerloyalty.

1. Selecteer tijdens het bewerken van de gegevens de optie **Transformeren** en vervolgens **Eerste rij als kolomkoppen gebruiken**.

1. Werk het gegevenstype voor de onderstaande kolommen bij:
   - **DateOfBirth**: datum
   - **RewardsPoints**: geheel getal
   - **CreatedOn**: datum/tijd

1. Wijzig in het veld **Naam** in het rechterdeelvenster uw gegevensbron in **loyCustomers**.

1. Sla de gegevensbron op.

### <a name="ingest-subscription-information"></a>Abonnementsgegevens opnemen

1. Maak een gegevensbron met de naam **SubscriptionHistory** en selecteer de connector **Tekst/CSV**.

1. Voer de URL voor abonnementen in: https://aka.ms/ciadchurnsubscriptionhistory.

1. Selecteer tijdens het bewerken van de gegevens de optie **Transformeren** en vervolgens **Eerste rij als kolomkoppen gebruiken**.

1. Werk het gegevenstype voor de onderstaande kolommen bij:
   - **SubscriptioID**: geheel getal
   - **SubscriptionAmount**: valuta
   - **SubscriptionEndDate**: datum/tijd
   - **SubscriptionStartDate**: datum/tijd
   - **TransactionDate**: datum/tijd
   - **IsRecurring**: waar/onwaar
   - **Is_auto_renew**: waar/onwaar
   - **RecurringFrequencyInMonths**: geheel getal

1. Wijzig in het veld **Naam** in het rechterdeelvenster uw gegevensbron in **SubscriptionHistory**.

1. Sla de gegevensbron op.

### <a name="ingest-customer-data-from-website-reviews"></a>Klantgegevens van website-reviews opnemen

1. Maak een gegevensbron met de naam **Website** en selecteer de connector **Tekst/CSV**.

1. Voer de URL in voor reviews van websites: https://aka.ms/ciadclasswebsite.

1. Selecteer tijdens het bewerken van de gegevens de optie **Transformeren** en vervolgens **Eerste rij als kolomkoppen gebruiken**.

1. Werk het gegevenstype voor de onderstaande kolommen bij:
   - **ReviewRating**: geheel getal
   - **ReviewDate**: datum

1. Wijzig in het veld **Naam** in het rechterdeelvenster uw gegevensbron in **webReviews**.

## <a name="task-2---data-unification"></a>Taak 2 - Gegevensharmonisatie

Bekijk het artikel [over gegevensharmonisatie](data-unification.md). In de volgende informatie wordt ervan uitgegaan dat u vertrouwd bent met harmoniseren van gegevens in het algemeen.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Taak 3 - Activiteit voor transactiegeschiedenis maken

Bekijk het artikel [over klantactiviteiten](activities.md). In de volgende informatie wordt ervan uitgegaan dat u vertrouwd bent met het maken van activiteiten in het algemeen.

1. Maak een activiteit met de naam **SubscriptionHistory** met de entiteit *Subscription* en de bijbehorende primaire sleutel **CustomerId**.

1. Maak een relatie tussen *SubscriptionHistory:Subscription* en *eCommerceContacts:eCommerce* met **CustomerID** als refererende sleutel om de twee entiteiten te verbinden.

1. Selecteer **SubscriptionType** voor **EventActivity** en **SubscriptionEndDate** voor **TimeStamp**.

1. Selecteer **Subscription** bij **Activiteitstype** en voer een semantische toewijzing van de activiteitsgegevens uit.

1. Voer de activiteit uit.

1. Voeg nog een activiteit toe en wijs de bijbehorende veldnamen toe aan de overeenkomstige velden:
   - Entiteit Klantactiviteit: Reviews:Website
   - Primaire sleutel: Website.Reviews.ReviewId
   - Timestamp Website.Reviews.ReviewDate
   - Gebeurtenis (naam activiteit): Website.Reviews.ActivityTypeDisplay
   - Details (bedrag of waarde): Website.Reviews.ReviewRating

1. Voer de activiteit uit.

## <a name="task-4---configure-the-subscription-churn-prediction"></a>Taak 4 - Configureer de voorspelling van het abonnementsverloop

Met de geharmoniseerde klantprofielen op hun plaats en de activiteit gemaakt, kunnen we nu het abonnementsverloop voorspellen. Zie [Voorspelling van abonnementsverloop](predict-subscription-churn.md) voor gedetailleerde stappen.

1. Ga naar **Informatie** > **Voorspellingen**.

1. Selecteer op het tabblad **Maken** de optie **Model gebruiken** op de tegel **Klantverloopmodel**.

1. Selecteer **Abonnement** voor het type verloop en vervolgens **Aan de slag**.

1. Geef het model de naam **OOB voorspelling abonnementsverloop** en de uitvoerentiteit **OOBSubscriptionChurnPrediction**.

1. Modelvoorkeuren definiëren:
   - **Dagen sinds abonnement afgelopen**: **60** dagen om aan te geven dat een klant als verlopen wordt beschouwd als deze het abonnement niet verlengt in deze periode nadat het abonnement is afgelopen.
   - **Dagen om de toekomst te kijken om verloop te voorspellen**: **93** dagen. Dit is de voorspelde duur voor verloop van klanten volgens het model. Hoe verder u in de toekomst kijkt, hoe minder nauwkeurig de resultaten zijn.

   :::image type="content" source="media/model-subs-levers.PNG" alt-text="Selecteer de modelvoorkeuren en definitie van verloop.":::

1. Selecteer **Volgende**.

1. Selecteer in de stap **Vereiste gegevens** de optie **Gegevens toevoegen** om de abonnementsgeschiedenis te verstrekken.

1. Selecteer **Abonnement** en de entiteit SubscriptionHistory en selecteer **Volgende**. De vereiste gegevens worden automatisch ingevuld vanuit de activiteit. Selecteer **Save**.

1. Selecteer **Gegevens toevoegen** voor Klantactiviteiten.

1. Voeg voor dit voorbeeld de webbeoordelingsactiviteit toe.

1. Selecteer **Volgende**.

1. Selecteer in de stap **Gegevensupdates** de optie **Maandelijks** voor het modelschema.

1. Selecteer nadat u alle details hebt nagekeken **Opslaan en uitvoeren**.

## <a name="task-5---review-model-results-and-explanations"></a>Taak 5 - Bekijk modelresultaten en uitleg

Laat het model de training en score van de gegevens voltooien. Bekijk de uitleg van het verloopmodel voor abonnementen. Zie [Resultaten van voorspelling weergeven](predict-subscription-churn.md#view-prediction-results) voor meer informatie.

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Taak 6 - Maak een segment van klanten met een hoog verlooprisico

Door het model uit te voeren, wordt een nieuwe entiteit gemaakt, die wordt vermeld in **Gegevens** > **Entiteiten**. U kunt een nieuw segment maken op basis van de entiteit die door het model is gemaakt.

1. Selecteer op de resultatenpagina de optie **Segment maken**.

1. Maak een regel met behulp van de entiteit **OOBSubscriptionChurnPrediction** en definieer het segment:
   - **Veld**: ChurnScore
   - **Operator**: groter dan
   - **Waarde**: 0.6

1. Selecteer **Opslaan** en **Uitvoeren** voor het segment.

U hebt nu een segment dat dynamisch wordt bijgewerkt en dat klanten met een hoog verlooprisico identificeert voor dit abonnementsbedrijf. Zie [Segmenten maken en beheren](segments.md) voor meer informatie.

> [!TIP]
> U kunt ook een segment maken voor een voorspellingsmodel vanaf de pagina **Segmenten** door **Nieuw** te selecteren en **Maken van** > **Intelligentie** te selecteren. Zie [Een nieuw segment maken met snelle segmenten](segment-quick.md) voor meer informatie.

[!INCLUDE [footer-include](includes/footer-banner.md)]
