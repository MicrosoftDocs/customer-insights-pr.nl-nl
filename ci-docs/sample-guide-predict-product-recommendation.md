---
title: Voorbeeldgids voor voorspelling van productaanbevelingen
description: Gebruik deze voorbeeldhandleiding om het standaard voorspellingsmodel voor productaanbevelingen uit te proberen.
ms.date: 09/19/2022
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
ms.openlocfilehash: 2b42a89e3f4ec8cf4f0769128b8536973365f1cb
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610138"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Voorbeeldgids voor voorspelling van productaanbevelingen

Deze gids laat u een compleet voorbeeld van productaanbevelingsvoorspelling zien aan de hand van voorbeeldgegevens. We raden u aan deze voorspelling uit te proberen [in een nieuwe omgeving](manage-environments.md).

## <a name="scenario"></a>Scenario

Contoso is een bedrijf dat hoogwaardige koffie en koffiemachines produceert. Ze verkopen de producten via hun Contoso Coffee-website. Het doel is om te begrijpen welke producten ze moeten aanbevelen aan hun terugkerende klanten. Weten wat klanten **waarschijnlijk zullen kopen** kan hen helpen marketinginspanningen te besparen door zich op specifieke artikelen te richten.

## <a name="prerequisites"></a>Vereisten

- Minimaal [inzendermachtigingen](permissions.md) in Customer Insights.

## <a name="task-1---ingest-data"></a>Taak 1 - Gegevens opnemen

Lees de artikelen [over gegevensopname](data-sources.md) en [verbinding met een Power Query-gegevensbron](connect-power-query.md). Bij de volgende informatie wordt ervan uitgegaan dat u vertrouwd bent met opnemen van gegevens in het algemeen.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Klantgegevens opnemen van het e-commerceplatform

1. Maak een Power Query-gegevensbron met de naam **eCommerce** en selecteer de connector **Tekst/CSV**.

1. Voer de URL voor eCommerce-contactpersonen in: https://aka.ms/ciadclasscontacts.

1. Selecteer tijdens het bewerken van de gegevens de optie **Transformeren** en vervolgens **Eerste rij als kolomkoppen gebruiken**.

1. Werk het gegevenstype voor de onderstaande kolommen bij:
   - **DateOfBirth**: datum
   - **CreatedOn**: datum/tijd/zone

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformeer geboortedatum naar datum.":::

1. Wijzig in het veld **Naam** in het rechterdeelvenster uw gegevensbron in **eCommerceContacts**.

1. De gegevensbron **Opslaan**.

### <a name="ingest-online-purchase-data"></a>Online aankoopgegevens opnemen

1. Voeg nog een gegevensset toe aan dezelfde **eCommerce**-gegevensbron. Kies opnieuw de connector **Tekst/CSV**.

1. Voer de URL in voor de gegevens voor online aankopen: https://aka.ms/ciadclassonline.

1. Selecteer tijdens het bewerken van de gegevens de optie **Transformeren** en vervolgens **Eerste rij als kolomkoppen gebruiken**.

1. Werk het gegevenstype voor de onderstaande kolommen bij:
   - **PurchasedOn**: datum/tijd
   - **TotalPrice**: valuta

1. Wijzig in het veld **Naam** in het deelvenster aan de zijkant uw gegevensbron van Query in **eCommercePurchases**.

1. De gegevensbron **Opslaan**.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Klantgegevens opnemen uit het loyaliteitsschema

1. Maak een gegevensbron met de naam **LoyaltyScheme** en selecteer de connector **Tekst/CSV**.

1. Voer de URL voor loyale klanten in: https://aka.ms/ciadclasscustomerloyalty.

1. Selecteer tijdens het bewerken van de gegevens de optie **Transformeren** en vervolgens **Eerste rij als kolomkoppen gebruiken**.

1. Werk het gegevenstype voor de onderstaande kolommen bij:
   - **DateOfBirth**: datum
   - **RewardsPoints**: geheel getal
   - **CreatedOn**: datum/tijd

1. Wijzig in het veld **Naam** in het rechterdeelvenster uw gegevensbron in **loyCustomers**.

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

## <a name="task-4---configure-product-recommendation-prediction"></a>Taak 4 - Voorspelling van productaanbevelingen configureren

Als de geharmoniseerde klantprofielen beschikbaar zijn en de activiteit is gemaakt, voert u de voorspelling van de productaanbeveling uit.

1. Ga naar **Informatie** > **Voorspellingen**.

1. Selecteer op het tabblad **Maken** de optie **Model gebruiken** op de tegel **Productaanbevelingen (preview)**.

1. Selecteer **Aan de slag**.

1. Geef het model de naam **OOB productaanbevelingsmodel voorspelling** en de uitvoer-entiteit **OOBproductRecommendationModelPrediction**​.

1. Selecteer **Volgende**.

1. Modelvoorkeuren definiëren:
   - **Aantal producten**: **5** om te definiëren hoeveel producten u uw klanten wilt aanbevelen.
   - **Verwachte herhaalde aankopen**: **Ja** als u eerder gekochte producten in de aanbeveling wilt opnemen.
   - **Terugkijkvenster:** **365 dagen** om te bepalen hoe ver het model terugkijkt voordat het een product opnieuw aanbeveelt.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Modelvoorkeuren voor het aanbevelingsmodel voor producten.":::

1. Selecteer **Volgende**.

1. Selecteer in de stap **Aankoopgeschiedenis toevoegen** de optie **Gegevens toevoegen**.

1. Selecteer **SalesOrderLine** en de entiteit eCommercePurchases en selecteer daarna **Volgende**. De vereiste gegevens worden automatisch ingevuld vanuit de activiteit. Selecteer **Opslaan** en daarna **Volgende**.

1. Sla de stappen **Productgegevens toevoegen** en **Productfilters** over omdat we geen productgegevens hebben.

1. Selecteer in de stap **Gegevensupdates** de optie **Maandelijks** voor het modelschema.

1. Selecteer **Volgende**.

1. Selecteer nadat u alle details hebt nagekeken **Opslaan en uitvoeren**.

## <a name="task-5---review-model-results-and-explanations"></a>Taak 5 - Bekijk modelresultaten en uitleg

Laat het model de training en score van de gegevens voltooien. Bekijk de [uitleg van het productaanbevelingsmodel bekijken](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-purchased-products"></a>Taak 6 - Maak een segment met veel gekochte producten

Door het model uit te voeren, wordt een nieuwe entiteit gemaakt, die wordt vermeld in **Gegevens** > **Entiteiten**. U kunt een nieuw segment maken op basis van de entiteit die door het model is gemaakt.

1. Selecteer op de resultatenpagina de optie **Segment maken**.

1. Maak een regel met behulp van de entiteit **OOBProductRecommendationModelPrediction** en definieer het segment:
   - **Veld**: ProductID
   - **Waarde**: selecteer de drie beste product-id's

1. Selecteer **Opslaan** en **Uitvoeren** voor het segment.

U hebt nu een segment dat dynamisch wordt bijgewerkt en dat de klanten identificeert die mogelijk geïnteresseerd zijn om de vijf meest aanbevolen producten te kopen. Zie [Segmenten maken en beheren](segments.md) voor meer informatie.

> [!TIP]
> U kunt ook een segment maken voor een voorspellingsmodel vanaf de pagina **Segmenten** door **Nieuw** te selecteren en **Maken van** > **Intelligentie** te selecteren. Zie [Een nieuw segment maken met snelle segmenten](segment-quick.md) voor meer informatie.

[!INCLUDE [footer-include](includes/footer-banner.md)]
