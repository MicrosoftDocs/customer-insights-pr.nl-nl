---
title: Voorbeeldgids voor voorspelling van productaanbevelingen
description: Gebruik deze voorbeeldhandleiding om het standaard voorspellingsmodel voor productaanbevelingen uit te proberen.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b219935dfbd9f7acc1104d83e2ca281801a1a4251ae4c19fc03d4b1ce46f4613
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035179"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a>Voorbeeldgids voor voorspelling van productaanbevelingen (preview)

We laten u een compleet voorbeeld van productaanbevelingsvoorspelling zien aan de hand van de onderstaande voorbeeldgegevens.

## <a name="scenario"></a>Scenario

Contoso is een bedrijf dat koffie en koffiemachines van hoge kwaliteit produceert, die ze verkopen via hun Contoso Coffee-website. Het doel is om te begrijpen welke producten ze moeten aanbevelen aan hun terugkerende klanten. Weten wat klanten **eerder zullen kopen**, kan hen helpen marketinginspanningen te besparen door zich op specifieke artikelen te richten.

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

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformeer geboortedatum naar datum.":::

5. Wijzig in het veld 'Naam' in het rechterdeelvenster uw gegevensbron van **Query** in **eCommerceContacts**.

6. De gegevensbron **Opslaan**.

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

## <a name="task-2---data-unification"></a>Taak 2 - Gegevensharmonisatie

Nadat we de gegevens hebben opgenomen, beginnen we nu met het proces voor gegevensharmonisatie om een geharmoniseerd klantprofiel te maken. Zie [Gegevensharmonisatie](data-unification.md) voor meer informatie.

### <a name="map"></a>Toewijzen

1. Na het opnemen van de gegevens, wijst u contacten uit eCommerce en Loyaliteitsgegevens toe aan veelgebruikte gegevenstypen. Ga naar **Gegevens** > **Unify** > **Toewijzen**.

2. Selecteer de entiteiten die het klantprofiel vertegenwoordigen: **eCommerceContacts** en **loyCustomers**.

   ![harmoniseer eCommerce- en loyaliteitsgegevensbronnen.](media/unify-ecommerce-loyalty.png)

3. Selecteer **ContactId** als de primaire sleutel voor **eCommerceContacts** en **LoyaltyID** als de primaire sleutel voor **loyCustomers**.

   ![Harmoniseer LoyaltyId als primaire sleutel.](media/unify-loyaltyid.png)

### <a name="match"></a>Bij elkaar zoeken

1. Ga naar het tabblad **Matchen** en selecteer **Volgorde instellen**.

2. Kies in de vervolgkeuzelijst **Primair** de optie **eCommerceContacts : eCommerce** als primaire bron en neem alle records op.

3. Kies in de vervolgkeuzelijst **Entiteit 2** de optie **loyCustomers: LoyaltyScheme** en neem alle records op.

   ![Harmoniseer match eCommerce en Loyaliteit](media/unify-match-order.png)

4. Selecteer **Een nieuwe regel maken**

5. Voeg uw eerste voorwaarde toe met FullName.

   - Selecteer voor eCommerceContacts de optie **FullName** in de vervolgkeuzelijst.
   - Selecteer voor loyCustomers de optie **FullName** in de vervolgkeuzelijst.
   - Selecteer de vervolgkeuzelijst **Normaliseren** en kies **Type (telefoon, naam, adres, ...)**.
   - Stel **Precisieniveau**: **Basic** en **Waarde**: **Hoog** in.

6. Voer de naam **FullName, Email** in voor de nieuwe regel.

   - Voeg een tweede voorwaarde voor het e-mailadres toe door **Voorwaarde toevoegen** te selecteren
   - Kies voor entiteit eCommerceContacts de optie **E-mail** in de vervolgkeuzelijst.
   - Kies voor entiteit loyCustomers de optie **E-mail** in de vervolgkeuzelijst.
   - Laat Normaliseren leeg.
   - Stel **Precisieniveau**: **Basic** en **Waarde**: **Hoog** in.

   ![Harmoniseer de matchregel voor naam en e-mailadres.](media/unify-match-rule.png)

7. Selecteer **Opslaan** en **Uitvoeren**.

### <a name="merge"></a>Samenvoeging

1. Ga naar het tabblad **Samenvoegen**.

1. Bij **ContactId** voor de entiteit **loyCustomers** wijzigt u de weergavenaam in **ContactIdLOYALTY** om deze te onderscheiden van de andere opgenomen id's.

   ![hernoem contactid van loyaliteits-id.](media/unify-merge-contactid.png)

1. Selecteer **Opslaan** en **Uitvoeren** om het samenvoegingsproces te starten.

## <a name="task-3---configure-product-recommendation-prediction"></a>Taak 3 - Voorspelling van productaanbevelingen configureren

Met de geharmoniseerde klantprofielen op hun plaats, kunnen we nu het abonnementsverloop voorspellen.

1. Ga naar **Informatie** > **Voorspelling** en kies **Productaanbeveling**​.

1. Selecteer **Aan de slag**.

1. Geef het model de naam **OOB productaanbevelingsmodel voorspelling** en de uitvoer-entiteit **OOBproductRecommendationModelPrediction**​.

1. Definieer drie voorwaarden voor het model:

   - **Aantal producten**: stel deze waarde in op **5**​. Deze instelling bepaalt hoeveel producten u uw klanten wilt aanbevelen.

   - **Verwachte herhaalde aankopen**: selecteer **Ja** om aan te geven dat u producten wilt opnemen in de aanbeveling die uw klanten eerder hebben gekocht.

   - **Terugkijkvenster**: selecteer minimaal **365 dagen**​. Deze instelling bepaalt hoe ver het model terugkijkt naar de activiteit van de klant om deze te gebruiken als invoer voor de aanbevelingen.
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Modelvoorkeuren voor het aanbevelingsmodel voor producten.":::

1. Selecteer **Vereiste gegevens** en selecteer **Gegevens toevoegen** voor aankoopgeschiedenis.

1. Voeg de entiteit **eCommercePurchases : eCommerce** toe en wijs de velden van eCommerce toe aan de overeenkomstige velden die vereist zijn voor het model.

1. Voeg de entiteit **eCommercePurchases : eCommerce** samen met **eCommerceContacts : eCommerce**.

   ![Voeg eCommerce-entiteiten samen.](media/model-purchase-join.png)

1. Selecteer **Volgende** om de modelplanning in te stellen.

   Het model moet regelmatig worden getraind om nieuwe patronen te leren wanneer er nieuwe gegevens worden opgenomen. Selecteer voor dit voorbeeld **Maandelijks**.

1. Selecteer nadat u alle details hebt nagekeken **Opslaan en uitvoeren**.


## <a name="task-4---review-model-results-and-explanations"></a>Taak 4 - Bekijk modelresultaten en uitleg

Laat het model de training en score van de gegevens voltooien. U kunt nu de uitleg van het productaanbevelingsmodel bekijken. Zie [Een voorspellingsstatus en resultaten beoordelen](predict-subscription-churn.md#review-a-prediction-status-and-results) voor meer informatie.

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Taak 5 - Maak een segment met veel gekochte producten

Door het productiemodel uit te voeren, wordt een nieuwe entiteit gemaakt die u kunt zien in **Gegevens** > **Entiteiten**.

U kunt een nieuw segment maken op basis van de entiteit die door het model is gemaakt.

1. Ga naar **Segmenten**. Selecteer **Nieuw** en kies **Maken van** > **Intelligence**.

   ![Een segment maken met de modeluitvoer.](media/segment-intelligence.png)

1. Selecteer het eindpunt **OOBProductRecommendationModelPrediction** en definieer het segment:

   - Veld: ProductID
   - Operator: waarde
   - Waarde: selecteer de drie beste product-id's

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Maak een segment van de modelresultaten.":::

U hebt nu een segment dat dynamisch wordt bijgewerkt en dat de klanten identificeert die meer bereid zijn de drie meest aanbevolen producten te kopen 

Zie [Segmenten maken en beheren](segments.md) voor meer informatie.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
