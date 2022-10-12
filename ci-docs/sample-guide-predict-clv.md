---
title: Voorbeeldgids voor voorspelling van de levensduurwaarde van klanten (CLV)
description: Gebruik deze voorbeeldgids om het voorspellingsmodel voor de levensduurwaarden van klanten uit te proberen.
ms.date: 09/15/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: fec43b279326daa17fb179181f5e310c99d48bb7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609632"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Voorbeeldgids voor voorspelling van de levensduurwaarde van klanten (CLV)

In deze gids wordt een end-to-end voorbeeld van de voorspelling van de levensduurwaarde van klanten (CLV) in Customer Insights uitgelegd aan de hand van voorbeeldgegevens. We raden u aan deze voorspelling uit te proberen [in een nieuwe omgeving](manage-environments.md).

## <a name="scenario"></a>Scenario

Contoso is een bedrijf dat hoogwaardige koffie en koffiemachines produceert. Ze verkopen de producten via hun Contoso Coffee-website. Het bedrijf inzicht krijgen in de waarde (omzet) die hun klanten in de komende 12 maanden kunnen genereren. Als ze de verwachte waarde van hun klanten in de komende 12 maanden kennen, kunnen ze hun marketinginspanningen op hoogwaardige klanten concentreren.

## <a name="prerequisites"></a>Vereisten

- Minstens [Inzendermachtigingen](permissions.md).

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

1. De gegevensbron **Opslaan**.

### <a name="ingest-online-purchase-data"></a>Online aankoopgegevens opnemen

1. Voeg nog een gegevensset toe aan dezelfde **eCommerce**-gegevensbron. Kies opnieuw de connector **Tekst/CSV**.

1. Voer de URL in voor de gegevens voor **Online aankopen** https://aka.ms/ciadclassonline.

1. Selecteer tijdens het bewerken van de gegevens de optie **Transformeren** en vervolgens **Eerste rij als kolomkoppen gebruiken**.

1. Werk het gegevenstype voor de onderstaande kolommen bij:
   - **PurchasedOn**: datum/tijd
   - **TotalPrice**: valuta

1. Wijzig in het veld **Naam** in het deelvenster aan de zijkant uw gegevensbron van Query in **eCommercePurchases**.

1. De gegevensbron **Opslaan**.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Klantgegevens opnemen uit het loyaliteitsschema

1. Maak een gegevensbron met de naam **LoyaltyScheme** en selecteer de connector **Tekst/CSV**.

1. Voer de URL voor loyaliteitsklanten in: https://aka.ms/ciadclasscustomerloyalty.

1. Selecteer tijdens het bewerken van de gegevens de optie **Transformeren** en vervolgens **Eerste rij als kolomkoppen gebruiken**.

1. Werk het gegevenstype voor de onderstaande kolommen bij:
   - **DateOfBirth**: datum
   - **RewardsPoints**: geheel getal
   - **CreatedOn**: datum/tijd

1. Wijzig in het veld **Naam** in het rechterdeelvenster uw gegevensbron in **loyCustomers**.

1. De gegevensbron **Opslaan**.

### <a name="ingest-customer-data-from-website-reviews"></a>Klantgegevens van website-reviews opnemen

1. Maak een gegevensbron met de naam **Website** en selecteer de connector **Tekst/CSV**.

1. Voer de URL in voor reviews van websites: https://aka.ms/CI-ILT/WebReviews.

1. Selecteer tijdens het bewerken van de gegevens de optie **Transformeren** en vervolgens **Eerste rij als kolomkoppen gebruiken**.

1. Werk het gegevenstype voor de onderstaande kolommen bij:
   - **ReviewRating**: decimaal getal
   - **ReviewDate**: datum

1. Wijzig in het veld **Naam** in het rechterdeelvenster uw gegevensbron in **Reviews**.

1. De gegevensbron **Opslaan**.

## <a name="task-2---data-unification"></a>Taak 2 - Gegevensharmonisatie

Bekijk het artikel [over gegevensharmonisatie](data-unification.md). In de volgende informatie wordt ervan uitgegaan dat u vertrouwd bent met harmoniseren van gegevens in het algemeen.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Taak 3 - Activiteit voor transactiegeschiedenis maken

Bekijk het artikel [over klantactiviteiten](activities.md). In de volgende informatie wordt ervan uitgegaan dat u vertrouwd bent met het maken van activiteiten in het algemeen.

1. Maak een activiteit met de naam **eCommercePurchases** met de entiteit *eCommercePurchases:eCommerce* en de bijbehorende primaire sleutel **PurchaseId**.

1. Maak een relatie tussen *eCommercePurchases:eCommerce* en *eCommerceContacts:eCommerce* met **ContactID** als refererende sleutel om de twee entiteiten te verbinden.

1. Selecteer **TotalPrice** voor **EventActivity** en **PurchasedOn** voor **TimeStamp**.

1. Selecteer **SalesOrderLine** bij **Activiteitstype** en voer een semantische toewijzing van de activiteitsgegevens uit.

1. Voer de activiteit uit.

1. Voeg nog een activiteit toe en wijs de bijbehorende veldnamen toe aan de overeenkomstige velden:
   - **Activiteitsentiteit**: Reviews:Website
   - **Primaire sleutel**: ReviewId
   - **Timestamp**: ReviewDate
   - **Gebeurtenisactiviteit**: ActivityTypeDisplay
   - **Aanvullende details**: ReviewRating
   - **Activiteitstype**: Review

1. Voer de activiteit uit.

## <a name="task-4---configure-customer-lifetime-value-prediction"></a>Taak 4 - De voorspelling van de levensduurwaarde van klanten configureren

Als de geharmoniseerde klantprofielen beschikbaar zijn en de activiteit is gemaakit, voert u de voorspelling voor de levensduurwaarde van klanten (CLV) uit. Zie [Voorspellingen van de levensduurwaarde van de klant](predict-customer-lifetime-value.md) voor gedetailleerde stappen.

1. Ga naar **Informatie** > **Voorspellingen**.

1. Selecteer op het tabblad **Maken** de optie **Model gebruiken** op de tegel **Levensduurwaarde van klant**.

1. Selecteer **Aan de slag**.

1. Geef het model **OOB eCommerce CLV-voorspelling** en de uitvoerentiteit **OOBeCommerceCLVPrediction** een naam.

1. Modelvoorkeuren definiëren:
   - **Tijdsperiode voor voorspelling**: **12 maanden of 1 jaar** om te bepalen hoe ver in de toekomst u de levensduurwaarde van de klant wilt voorspellen.
   - **Actieve klanten**: **Het aankoopinterval laten berekenen door het model**. Dit is het tijdsbestek waarin een klant ten minste één transactie moet hebben uitgevoerd om als actief te worden beschouwd.
   - **Klanten met hoge waarde**: definieer handmatig klanten met hoge waarde als **top 30% van actieve betalende klanten**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Voorkeurenstap in de begeleide ervaring voor het CLV-model.":::

1. Selecteer **Volgende**.

1. Selecteer in de stap **Vereiste gegevens** de optie **Gegevens toevoegen** om de transactiegeschiedenisgegevens te verstrekken.

    :::image type="content" source="media/clv-model-required.png" alt-text="Voeg vereiste gegevensstap toe in de begeleide ervaring voor het CLV-model.":::

1. Selecteer **SalesOrderLine** en de entiteit eCommercePurchases en selecteer daarna **Volgende**. De vereiste gegevens worden automatisch ingevuld vanuit de activiteit. Selecteer **Opslaan** en daarna **Volgende**.

1. Via de stap **Aanvullende gegevens (optioneel)** kunt u meer klantactiviteitsgegevens toevoegen om meer inzicht te krijgen in klantinteracties. Selecteer voor dit voorbeeld **Gegevens toevoegen** en voeg de webbeoordelingsactiviteit toe.

1. Selecteer **Volgende**.

1. Selecteer in de stap **Gegevensupdates** de optie **Maandelijks** voor het modelschema.

1. Selecteer **Volgende**.

1. Selecteer nadat u alle details hebt nagekeken **Opslaan en uitvoeren**.

## <a name="task-5---review-model-results-and-explanations"></a>Taak 5 - Bekijk modelresultaten en uitleg

Laat het model de training en score van de gegevens voltooien. Bekijk de [resultaten en uitleg van het CLV-model](predict-customer-lifetime-value.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-value-customers"></a>Taak 6 - Een segment van klanten met hoge waarde maken

Door het model uit te voeren, wordt een nieuwe entiteit gemaakt, die wordt vermeld in **Gegevens** > **Entiteiten**. U kunt een nieuw klantsegment maken op basis van de entiteit die door het model is gemaakt.

1. Selecteer op de resultatenpagina de optie **Segment maken**.

1. Maak een regel met behulp van de entiteit **OOBeCommerceCLVPrediction** en definieer het segment:
   - **Veld**: CLVScore
   - **Operator**: groter dan
   - **Waarde**: 1500

1. Selecteer **Opslaan** en **Uitvoeren** voor het segment.

U hebt nu een segment dat klanten identificeert waarvan wordt voorspeld dat ze in de komende 12 maanden meer dan $ 1500 aan inkomsten zullen genereren. Dit segment wordt dynamisch bijgewerkt als er meer gegevens worden opgenomen. Zie [Segmenten maken en beheren](segments.md) voor meer informatie.

> [!TIP]
> U kunt ook een segment maken voor een voorspellingsmodel vanaf de pagina **Segmenten** door **Nieuw** te selecteren en **Maken van** > **Intelligentie** te selecteren. Zie [Een nieuw segment maken met snelle segmenten](segment-quick.md) voor meer informatie.

[!INCLUDE [footer-include](includes/footer-banner.md)]
