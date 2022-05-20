---
title: Voorbeeldgids voor voorspelling van productaanbevelingen
description: Gebruik deze voorbeeldhandleiding om het standaard voorspellingsmodel voor productaanbevelingen uit te proberen.
ms.date: 05/16/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: cc72cce15fa0c9e92dbf202c803e99514c9ce2b1
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762680"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Voorbeeldgids voor voorspelling van productaanbevelingen

We laten u een compleet voorbeeld van productaanbevelingsvoorspelling zien aan de hand van de onderstaande voorbeeldgegevens.

## <a name="scenario"></a>Scenario

Contoso is een bedrijf dat koffie- en koffiemachines van hoge kwaliteit produceert, die ze verkopen via hun Contoso Coffee-website. Het doel is om te begrijpen welke producten ze moeten aanbevelen aan hun terugkerende klanten. Weten wat klanten **eerder zullen kopen**, kan hen helpen marketinginspanningen te besparen door zich op specifieke artikelen te richten.

## <a name="prerequisites"></a>Vereisten

- Minimaal [inzendermachtigingen](permissions.md) in Customer Insights.
- We raden u aan de volgende stappen te implementeren [in een nieuwe omgeving](manage-environments.md).

## <a name="task-1---ingest-data"></a>Taak 1 - Gegevens opnemen

Lees de artikelen [over gegevensopname](data-sources.md) en [gegevensbronnen importeren met behulp van Power Query-connectoren](connect-power-query.md) in het bijzonder. Bij de volgende informatie wordt ervan uitgegaan dat u bekend bent met opnemen van gegevens in het algemeen.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Klantgegevens opnemen van het e-commerceplatform

1. Maak een gegevensbron met de naam **eCommerce**, kies de importoptie en selecteer de connector **Tekst/CSV**.

1. Voer de URL in voor eCommerce-contacten in: [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Selecteer tijdens het bewerken van de gegevens **Transformeren** en dan **De eerste rij als kopteksten gebruiken**.

1. Werk het gegevenstype voor de onderstaande kolommen bij:
   - **DateOfBirth**: datum
   - **CreatedOn**: datum/tijd/zone

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformeer geboortedatum naar datum.":::

1. Wijzig in het veld 'Naam' in het rechterdeelvenster uw gegevensbron van **Query** in **eCommerceContacts**.

1. De gegevensbron **Opslaan**.

### <a name="ingest-online-purchase-data"></a>Online aankoopgegevens opnemen

1. Voeg nog een gegevensset toe aan dezelfde **eCommerce**-gegevensbron. Kies opnieuw de connector **Tekst/CSV**.

1. Voer de URL in voor de gegevens voor **Online aankopen** [https://aka.ms/ciadclassonline](https://aka.ms/ciadclassonline).

1. Selecteer tijdens het bewerken van de gegevens **Transformeren** en dan **De eerste rij als kopteksten gebruiken**.

1. Werk het gegevenstype voor de onderstaande kolommen bij:
   - **PurchasedOn**: datum/tijd
   - **TotalPrice**: valuta

1. Wijzig in het veld **Naam** in het deelvenster aan de zijkant uw gegevensbron van **Query** in **eCommercePurchases**.

1. De gegevensbron **Opslaan**.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Klantgegevens opnemen uit het loyaliteitsschema

1. Maak een gegevensbron met de naam **LoyaltyScheme**, kies de importoptie en selecteer de connector **Tekst/CSV**.

1. Voer de URL in voor eCommerce-contacten in [https://aka.ms/ciadclasscustomerloyalty](https://aka.ms/ciadclasscustomerloyalty).

1. Selecteer tijdens het bewerken van de gegevens **Transformeren** en dan **De eerste rij als kopteksten gebruiken**.

1. Werk het gegevenstype voor de onderstaande kolommen bij:
   - **DateOfBirth**: datum
   - **RewardsPoints**: geheel getal
   - **CreatedOn**: datum/tijd

1. Wijzig in het veld **Naam** in het rechterdeelvenster uw gegevensbron van **Query** in **loyCustomers**.

1. De gegevensbron **Opslaan**.

## <a name="task-2---data-unification"></a>Taak 2 - Gegevensharmonisatie

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-product-recommendation-prediction"></a>Taak 3 - Voorspelling van productaanbevelingen configureren

Met de geharmoniseerde klantprofielen kunnen we nu de voorspelling van de productaanbeveling uitvoeren.

1. Ga naar **Informatie** > **Voorspelling** en kies **Productaanbeveling**​.

1. Selecteer **Aan de slag**.

1. Geef het model de naam **OOB productaanbevelingsmodel voorspelling** en de uitvoer-entiteit **OOBproductRecommendationModelPrediction**​.

1. Definieer drie voorwaarden voor het model:

   - **Aantal producten**: stel deze waarde in op **5**​. Deze instelling bepaalt hoeveel producten u uw klanten wilt aanbevelen.

   - **Verwachte herhaalde aankopen**: selecteer **Ja** om aan te geven dat u producten wilt opnemen in de aanbeveling die uw klanten eerder hebben gekocht.

   - **Terugkijkvenster**: selecteer minimaal **365 dagen**​. Deze instelling bepaalt hoe ver het model terugkijkt naar de activiteit van de klant om deze te gebruiken als invoer voor de aanbevelingen.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Modelvoorkeuren voor het aanbevelingsmodel voor producten.":::

1. Selecteer in de stap **Vereiste gegevens toevoegen** de optie **Gegevens toevoegen**.

1. Kies in het deelvenster **Gegevens toevoegen** de entiteit **SalesOrderLine** als de aankoopgeschiedenisentiteit. Op dit moment is deze waarschijnlijk nog niet geconfigureerd. Open de koppeling in het deelvenster om de activiteit te maken met de volgende stappen:
   1. Voer een **Activiteitsnaam** in en kies *eCommercePurchases:eCommerce* als **Activiteitsentiteit**. De **Primaire sleutel** is *PurchaseId*.
   1. Definieer en benoem de relatie met de *entiteit eCommerceContacten:eCommerce* en kies **ContactId** als de refererende sleutel.
   1. Stel voor Activiteitsharmonisatie **Gebeurtenisactiviteit** in als *TotalPrice* en Timestamp op *PurchasedOn*. U kunt meer velden opgeven zoals beschreven in [Klantactiviteiten](activities.md).
   1. Kies voor **Activiteitstype** de optie *SalesOrderLine*. Wijs de volgende activiteitsvelden toe:
      - Orderregel-id: PurchaseId
      - Order-id: PurchaseId
      - Ordergegevens: PurchasedOn
      - Product-id: ProductId
      - Bedrag: TotalPrice
   1. Bekijk en voltooi de activiteit voordat u teruggaat naar de modelconfiguratie.

1. Terug in de stap **Activiteiten selecteren** kiest u de nieuw aangemaakte activiteit in de sectie **Activiteiten**. Selecteer **Volgende** en de kenmerktoewijzing is al ingevuld. Selecteer **Opslaan**.

1. In deze voorbeeldgids slaan we **Productgegevens toevoegen** en **Productfilters** over omdat we geen productgegevens hebben.

1. Stel in de stap **Gegevensupdates** het modelschema in.

   Het model moet regelmatig worden getraind om nieuwe patronen te leren wanneer er nieuwe gegevens worden opgenomen. Selecteer voor dit voorbeeld **Maandelijks**.

1. Selecteer nadat u alle details hebt nagekeken **Opslaan en uitvoeren**. Het duurt een paar minuten om het model de eerste keer uit te voeren.

## <a name="task-4---review-model-results-and-explanations"></a>Taak 4 - Bekijk modelresultaten en uitleg

Laat het model de training en score van de gegevens voltooien. U kunt nu de uitleg van het productaanbevelingsmodel bekijken. Zie [Een voorspellingsstatus en resultaten beoordelen](predict-transactional-churn.md#review-a-prediction-status-and-results) voor meer informatie.

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Taak 5 - Maak een segment met veel gekochte producten

Door het productiemodel uit te voeren, wordt een nieuwe entiteit gemaakt die u kunt zien in **Gegevens** > **Entiteiten**.

U kunt een nieuw segment maken op basis van de entiteit die door het model is gemaakt.

1. Ga naar **Segmenten**. Selecteer **Nieuw** en kies **Maken van informatie**.

   ![Een segment maken met de modeluitvoer.](media/segment-intelligence.png)

1. Selecteer het eindpunt **OOBProductRecommendationModelPrediction** en definieer het segment:

   - Veld: ProductID
   - Waarde: selecteer de drie beste product-id's

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Maak een segment van de modelresultaten.":::

U hebt nu een segment dat dynamisch wordt bijgewerkt en dat de klanten identificeert die mogelijk geïnteresseerd zijn om de drie meest aanbevolen producten te kopen.

Zie [Segmenten maken en beheren](segments.md) voor meer informatie.

[!INCLUDE [footer-include](includes/footer-banner.md)]
