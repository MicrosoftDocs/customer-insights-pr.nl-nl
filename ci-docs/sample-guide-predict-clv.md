---
title: Voorbeeldgids voor voorspelling van de levensduurwaarde van klanten (CLV)
description: Gebruik deze voorbeeldgids om het voorspellingsmodel voor de levensduurwaarden van klanten uit te proberen.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 2013533ed225a396d21e51e63297d7608ce58ac6
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051631"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Voorbeeldgids voor voorspelling van de levensduurwaarde van klanten (CLV)

In deze gids wordt een end-to-end voorbeeld van de voorspelling van de levensduurwaarde van klanten (CLV) in Customer Insights uitgelegd aan de hand van voorbeeldgegevens.

## <a name="scenario"></a>Scenario

Contoso is een bedrijf dat hoogwaardige koffie en koffiemachines produceert. Ze verkopen de producten via hun Contoso Coffee-website. Het bedrijf inzicht krijgen in de waarde (omzet) die hun klanten in de komende 12 maanden kunnen genereren. Als ze de verwachte waarde van hun klanten in de komende 12 maanden kennen, kunnen ze hun marketinginspanningen op hoogwaardige klanten concentreren.

## <a name="prerequisites"></a>Vereisten

- Minimaal [inzendermachtigingen](permissions.md) in Customer Insights.
- We raden u aan de volgende stappen te implementeren [in een nieuwe omgeving](manage-environments.md).

## <a name="task-1---ingest-data"></a>Taak 1 - Gegevens opnemen

Lees de artikelen [over gegevensopname](data-sources.md) en [gegevensbronnen importeren met behulp van Power Query-connectoren](connect-power-query.md). Bij de volgende informatie wordt ervan uitgegaan dat u bekend bent met opnemen van gegevens in het algemeen.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Klantgegevens opnemen van het e-commerceplatform

1. Maak een gegevensbron met de naam **eCommerce**, kies de importoptie en selecteer de connector **Tekst/CSV**.

1. Voer de URL voor eCommerce-contactpersonen [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts) in.

1. Selecteer tijdens het bewerken van de gegevens **Transformeren** en dan **De eerste rij als kopteksten gebruiken**.

1. Werk het gegevenstype voor de onderstaande kolommen bij:
   - **DateOfBirth**: datum
   - **CreatedOn**: datum/tijd/zone

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformeer geboortedatum naar datum.":::

1. Wijzig in het veld 'Naam' in het rechterdeelvenster uw gegevensbron van **Query** in **eCommerceContacts**.

1. De gegevensbron **Opslaan**.

### <a name="ingest-online-purchase-data"></a>Online aankoopgegevens opnemen

1. Voeg nog een gegevensset toe aan dezelfde **eCommerce**-gegevensbron. Kies opnieuw de connector **Tekst/CSV**.

1. Voer de URL in voor de gegevens voor **Online aankopen** https://aka.ms/ciadclassonline.

1. Selecteer tijdens het bewerken van de gegevens **Transformeren** en dan **De eerste rij als kopteksten gebruiken**.

1. Werk het gegevenstype voor de onderstaande kolommen bij:
   - **PurchasedOn**: datum/tijd
   - **TotalPrice**: valuta

1. Wijzig in het veld **Naam** in het deelvenster aan de zijkant uw gegevensbron van **Query** in **eCommercePurchases**.

1. De gegevensbron **Opslaan**.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Klantgegevens opnemen uit het loyaliteitsschema

1. Maak een gegevensbron met de naam **LoyaltyScheme**, kies de importoptie en selecteer de connector **Tekst/CSV**.

1. Voer de URL in voor eCommerce-contacten in https://aka.ms/ciadclasscustomerloyalty.

1. Selecteer tijdens het bewerken van de gegevens **Transformeren** en dan **De eerste rij als kopteksten gebruiken**.

1. Werk het gegevenstype voor de onderstaande kolommen bij:
   - **DateOfBirth**: datum
   - **RewardsPoints**: geheel getal
   - **CreatedOn**: datum/tijd

1. Wijzig in het veld **Naam** in het rechterdeelvenster uw gegevensbron van **Query** in **loyCustomers**.

1. De gegevensbron **Opslaan**.

### <a name="ingest-customer-data-from-website-reviews"></a>Klantgegevens van website-reviews opnemen

1. Maak een gegevensbron met de naam **Website**, kies de importoptie en selecteer de connector **Tekst/CSV**.

1. Voer de URL in voor eCommerce-contacten in https://aka.ms/CI-ILT/WebReviews.

1. Selecteer tijdens het bewerken van de gegevens **Transformeren** en dan **De eerste rij als kopteksten gebruiken**.

1. Werk het gegevenstype voor de onderstaande kolommen bij:

   - **ReviewRating**: decimaal getal
   - **ReviewDate**: datum

1. Wijzig in het veld 'Naam' in het rechterdeelvenster uw gegevensbron van **Query** in **Beoordelingen**.

1. De gegevensbron **Opslaan**.

## <a name="task-2---data-unification"></a>Taak 2 - Gegevensharmonisatie

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>Taak 3 - De voorspelling van de levensduurwaarde van klanten configureren

Met de geharmoniseerde klantprofielen kunnen we nu de voorspelling voor de levensduurwaarde van klanten uitvoeren. Zie [Voorspellingen van de levensduurwaarde van de klant](predict-customer-lifetime-value.md) voor gedetailleerde stappen.

1. Ga naar **Informatie**  > **Voorspellingen** en selecteer **Model voor waarde voor levensduur van klant**.

1. Neem de informatie in het zijvenster door en selecteer **Aan de slag**.

1. Geef het model **OOB eCommerce CLV-voorspelling** en de uitvoerentiteit **OOBeCommerceCLVPrediction** een naam.

1. Definieer modelvoorkeuren voor het CLV-model:
   - **Periode van voorspellingstijd**: **12 maanden of 1 jaar**. Deze instelling definieert hoe ver in de toekomst de levensduurwaarde van de klant moet worden voorspeld.
   - **Actieve klanten**: specificeer wat actieve klanten voor uw bedrijf betekenen. Stel de historische tijdsbestek in waarin een klant ten minste één transactie moet hebben gehad om als actief te worden beschouwd. Het model voorspelt alleen levensduurwaarde voor actieve klanten. Kies ervoor om het model de tijdsperiode te laten berekenen op basis van historische transactiegegevens of een specifiek tijdsbestek op te geven. In deze voorbeeldgids kiezen we voor **Model het aankoopinterval laten berekenen**, wat de standaardoptie is.
   - **Klanten met hoge waarde**: definieer klanten met hoge waarde als een percentiel van best betalende klanten. Het model gebruikt deze invoer om resultaten te leveren die passen bij uw bedrijfsdefinitie van klanten met hoge waarde. U kunt ervoor kiezen om het model klanten met hoge waarde te laten definiëren. Het gebruikt een heuristische regel waarmee het percentiel wordt afgeleid. U kunt ook klanten met hoge waarde definiëren als een percentiel van best betalende klanten in de toekomst. In deze voorbeeldgids definiëren we klanten met hoge waarde handmatig als **top 30% van actieve betalende klanten** en selecteren **Volgende**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Voorkeurenstap in de begeleide ervaring voor het CLV-model.":::

1. Selecteer in de stap **Vereiste gegevens** de optie **Gegevens toevoegen** om de transactiegeschiedenisgegevens te verstrekken.

1. Voeg de entiteit **eCommercePurchaces : eCommerce** toe en wijs de kenmerken toe die vereist zijn door het model:
   - Transactie-id: eCommerce.eCommercePurchases.PurchaseId
   - Transactiedatum: eCommerce.eCommercePurchases.PurchasedOn
   - Transactiebedrag: eCommerce.eCommercePurchases.TotalPrice
   - Product-id: eCommerce.eCommercePurchases.ProductId

1. Selecteer **Volgende**.

1. Stel de relatie in tussen de entiteit **eCommercePurchases : eCommerce** en **eCommerceContacten : eCommerce**.

1. Via de stap **Aanvullende gegevens (optioneel)** kunt u meer klantactiviteitsgegevens toevoegen. Deze gegevens kunnen helpen om meer inzicht te krijgen in klantinteracties met uw bedrijf, wat kan bijdragen aan CLV. Door toevoeging van belangrijke klantinteracties zoals weblogs, klantenservicelogboeken of geschiedenis van beloningsprogramma's kan de nauwkeurigheid van voorspellingen worden verbeterd. Selecteer **Gegevens toevoegen** om meer klantactiviteitsgegevens op te nemen.

1. Voeg de entiteit Klantactiviteit toe en wijs de bijbehorende veldnamen toe aan de overeenkomstige velden die door het model worden vereist:
   - Entiteit Klantactiviteit: Reviews:Website
   - Primaire sleutel: Website.Reviews.ReviewId
   - Timestamp Website.Reviews.ReviewDate
   - Gebeurtenis (naam activiteit): Website.Reviews.ActivityTypeDisplay
   - Details (bedrag of waarde): Website.Reviews.ReviewRating

1. Selecteer **Volgende** en configureer de activiteit en de relatie tussen de transactiegegevens en de klantgegevens:  
   - Type activiteit: kies bestaande
   - Activiteitslabel: Review
   - Overeenkomstig label: Website.Reviews.UserId
   - Klantentiteit: eCommerceContacts:eCommerce
   - Relatie: WebsiteReviews

1. Selecteer **Volgende** om de modelplanning in te stellen.

   Het model moet regelmatig trainen om nieuwe patronen te leren wanneer er nieuwe gegevens worden opgenomen. Kies voor dit voorbeeld de optie **Maandelijks**.

1. Selecteer nadat u alle details hebt nagekeken **Opslaan en uitvoeren**.

## <a name="task-4---review-model-results-and-explanations"></a>Taak 4 - Bekijk modelresultaten en uitleg

Laat het model de training en score van de gegevens voltooien. Vervolgens kunt u de resultaten en uitleg van het CLV-model bekijken. Zie [Een voorspellingsstatus en resultaten beoordelen](predict-customer-lifetime-value.md#review-prediction-status-and-results) voor meer informatie.

## <a name="task-5---create-a-segment-of-high-value-customers"></a>Taak 5 - Een segment van klanten met hoge waarde maken

Door het model uit te voeren, wordt een nieuwe entiteit gemaakt, die wordt vermeld in **Gegevens** > **Entiteiten**. U kunt een nieuw klantsegment maken op basis van de entiteit die door het model is gemaakt.

1. Ga naar **Segmenten**. 

1. Selecteer **Nieuw** en kies **Maken van** > **Informatie**.

   ![Een segment maken met de modeluitvoer.](media/segment-intelligence.png)

1. Selecteer de entiteit **OOBeCommerceCLVPrediction** en definieer het segment:
  - Veld: CLVScore
  - Operator: groter dan
  - Waarde: 1500

1. Selecteer **Beoordeling** en **Opslaan** voor het segment.

U hebt nu een segment dat klanten identificeert waarvan wordt voorspeld dat ze in de komende 12 maanden meer dan $ 1500 aan inkomsten zullen genereren. Dit segment wordt dynamisch bijgewerkt als er meer gegevens worden opgenomen.

Zie [Segmenten maken en beheren](segments.md) voor meer informatie.
