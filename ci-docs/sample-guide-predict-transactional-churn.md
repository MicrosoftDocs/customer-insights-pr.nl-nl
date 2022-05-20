---
title: Voorbeeldhandleiding transactieverloop voorspellen
description: Gebruik deze voorbeeldhandleiding om het standaard voorspellingsmodel voor transactieverloop uit te proberen.
ms.date: 05/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3edbf2a471313379c28db874d7f19c3265a23299
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741313"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Voorbeeldhandleiding transactieverloop voorspellen

We laten u een compleet voorbeeld van transactieverloop-voorspelling in Customer Insights zien aan de hand van de onderstaande voorbeeldgegevens. Alle gegevens die in deze handleiding worden gebruikt, zijn geen echte klantgegevens en maken deel uit van de Contoso gegevensset in de *Demo*-omgeving binnen uw Customer Insights-abonnement.

## <a name="scenario"></a>Scenario

Contoso is een bedrijf dat koffie- en koffiemachines van hoge kwaliteit produceert, die ze verkopen via hun Contoso Coffee-website. Hun doel is te weten te komen welke klanten die hun producten normaal gesproken regelmatig kopen, in de komende 60 dagen geen actieve klant meer zijn. Weten welke van hun klanten **waarschijnlijk zal verlopen**, kan hen helpen zich marketinginspanningen te besparen door zich te concentreren op het behouden van hun klanten.

## <a name="prerequisites"></a>Vereisten

- Minimaal [inzendermachtigingen](permissions.md) in Customer Insights.
- We raden u aan de volgende stappen te implementeren [in een nieuwe omgeving](manage-environments.md).

## <a name="task-1---ingest-data"></a>Taak 1 - Gegevens opnemen

Lees de artikelen [over gegevensopname](data-sources.md) en [gegevensbronnen importeren met behulp van Power Query-connectoren](connect-power-query.md) in het bijzonder. Bij de volgende informatie wordt ervan uitgegaan dat u bekend bent met opnemen van gegevens in het algemeen. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Klantgegevens opnemen van het e-commerceplatform

1. Maak een gegevensbron met de naam **eCommerce**, kies de importoptie en selecteer de connector **Tekst/CSV**.

1. Voer de URL in voor eCommerce-contacten in https://aka.ms/ciadclasscontacts.

1. Selecteer tijdens het bewerken van de gegevens **Transformeren** en dan **De eerste rij als kopteksten gebruiken**.

1. Werk het gegevenstype voor de onderstaande kolommen bij:

   - **DateOfBirth**: datum
   - **CreatedOn**: datum/tijd/zone

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Geboortedatum transformeren naar datum.":::

1. Wijzig in het veld **Naam** in het rechterdeelvenster uw gegevensbron van **Query** in **eCommerceContacts**.

1. Sla de gegevensbron op.

### <a name="ingest-online-purchase-data"></a>Online aankoopgegevens opnemen

1. Voeg nog een gegevensset toe aan dezelfde **eCommerce**-gegevensbron. Kies opnieuw de connector **Tekst/CSV**.

1. Voer de URL in voor de gegevens voor **Online aankopen** https://aka.ms/ciadclassonline.

1. Selecteer tijdens het bewerken van de gegevens **Transformeren** en dan **De eerste rij als kopteksten gebruiken**.

1. Werk het gegevenstype voor de onderstaande kolommen bij:

   - **PurchasedOn**: datum/tijd
   - **TotalPrice**: valuta
   
1. Wijzig in het veld **Naam** in het rechterdeelvenster uw gegevensbron van **Query** in **eCommercePurchases**.

1. Sla de gegevensbron op.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Klantgegevens opnemen uit het loyaliteitsschema

1. Maak een gegevensbron met de naam **LoyaltyScheme**, kies de importoptie en selecteer de connector **Tekst/CSV**.

1. Voer de URL in voor eCommerce-contacten in https://aka.ms/ciadclasscustomerloyalty.

1. Selecteer tijdens het bewerken van de gegevens **Transformeren** en dan **De eerste rij als kopteksten gebruiken**.

1. Werk het gegevenstype voor de onderstaande kolommen bij:

   - **DateOfBirth**: datum
   - **RewardsPoints**: geheel getal
   - **CreatedOn**: datum/tijd

1. Wijzig in het veld **Naam** in het rechterdeelvenster uw gegevensbron van **Query** in **loyCustomers**.

1. Sla de gegevensbron op.

## <a name="task-2---data-unification"></a>Taak 2 - Gegevensharmonisatie

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-transaction-churn-prediction"></a>Taak 3 - Configureer de voorspelling van het transactieverloop

Met de geharmoniseerde klantprofielen kunnen we nu de voorspelling van het transactieverloop uitvoeren. Zie het artikel [Voorspelling van transactieverloop](predict-transactional-churn.md) voor gedetailleerde stappen. 

1. Ga naar **Intelligence** > **Ontdekken** en selecteer het **Klantverloopmodel**.

1. Selecteer de optie **Transactie** en selecteer **Aan de slag**.

1. Geef het model de naam **OOB voorspelling eCommerce transactieverloop** en de uitvoerentiteit **OOBeCommerceChurnPrediction**.

1. Definieer twee voorwaarden voor het verloopmodel:

   * **Voorspellingsvenster**: **minstens 60** dagen. Deze instelling bepaalt hoe ver in de toekomst we het klantverloop willen voorspellen.

   * **Definitie van verloop**: **minstens 60** dagen. De duur zonder aankoop waarna een klant als verlopen wordt beschouwd.

     :::image type="content" source="media/model-levers.PNG" alt-text="Selecteer de modelhendels Voorspellingsvenster en Definitie van verloop.":::

1. Selecteer **Aankoopgeschiedenis (vereist)** en selecteer **Gegevens toevoegen** voor aankoopgeschiedenis.

1. Voeg de entiteit **eCommercePurchases : eCommerce** toe en wijs de velden van eCommerce toe aan de overeenkomstige velden die vereist zijn voor het model.

1. Voeg de entiteit **eCommercePurchases : eCommerce** samen met **eCommerceContacts : eCommerce**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Voeg eCommerce-entiteiten samen.":::

1. Selecteer **Volgende** om de modelplanning in te stellen.

   Het model moet regelmatig worden getraind om nieuwe patronen te leren wanneer er nieuwe gegevens worden opgenomen. Selecteer voor dit voorbeeld **Maandelijks**.

1. Selecteer nadat u alle details hebt nagekeken **Opslaan en uitvoeren**.

## <a name="task-4---review-model-results-and-explanations"></a>Taak 4 - Bekijk modelresultaten en uitleg

Laat het model de training en score van de gegevens voltooien. U kunt nu de uitleg van het verloopmodel bekijken. Zie [Een voorspellingsstatus en resultaten beoordelen](predict-transactional-churn.md#review-a-prediction-status-and-results) voor meer informatie.

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Taak 5 - Maak een segment van klanten met een hoog verlooprisico

Door het productiemodel uit te voeren, wordt een nieuwe entiteit gemaakt die u kunt zien in **Gegevens** > **Entiteiten**.   

U kunt een nieuw segment maken op basis van de entiteit die door het model is gemaakt.

1.  Ga naar **Segmenten**. Selecteer **Nieuw** en kies **Maken van** > **Intelligence**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Een segment maken met de modeluitvoer.":::

1. Selecteer het **OOBeCommerceChurnPrediction**-eindpunt en definieer het segment: 
   - Veld: ChurnScore
   - Operator: groter dan
   - Waarde: 0,6

U hebt nu een segment dat dynamisch wordt bijgewerkt en dat klanten met een hoog verlooprisico identificeert.

Zie [Segmenten maken en beheren](segments.md) voor meer informatie.


[!INCLUDE [footer-include](includes/footer-banner.md)]
