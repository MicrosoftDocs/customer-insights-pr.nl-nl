---
title: Voorbeeldhandleiding transactieverloop voorspellen
description: Gebruik deze voorbeeldhandleiding om het standaard voorspellingsmodel voor transactieverloop uit te proberen.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ccc32b6e5e96adf6f2fa8c6d52960a07d1513f3
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609678"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Voorbeeldhandleiding transactieverloop voorspellen

Deze gids leidt u door een compleet voorbeeld van voorspelling van transactieverloop aan de hand van de voorbeeldgegevens. We raden u aan deze voorspelling uit te proberen [in een nieuwe omgeving](manage-environments.md).

## <a name="scenario"></a>Scenario

Contoso is een bedrijf dat hoogwaardige koffie en koffiemachines produceert. Ze verkopen de producten via hun Contoso Coffee-website. Hun doel is te weten te komen welke klanten die hun producten normaal gesproken regelmatig kopen, in de komende 60 dagen geen actieve klant meer zijn. Weten welke van hun klanten **waarschijnlijk zal verlopen**, kan hen helpen zich marketinginspanningen te besparen door zich te concentreren op het behouden van hun klanten.

## <a name="prerequisites"></a>Vereisten

- Minstens [Inzendermachtigingen](permissions.md).

## <a name="task-1---ingest-data"></a>Taak 1 - Gegevens opnemen

Lees de artikelen [over gegevensopname](data-sources.md) en [verbinding met een Power Query-gegevensbron](connect-power-query.md). Bij de volgende informatie wordt ervan uitgegaan dat u vertrouwd bent met opnemen van gegevens in het algemeen.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Klantgegevens opnemen van het e-commerceplatform

1. Maak een gegevensbron met de naam **eCommerce** en selecteer de connector **Tekst/CSV**.

1. Voer de URL in voor eCommerce-contacten in https://aka.ms/ciadclasscontacts.

1. Selecteer tijdens het bewerken van de gegevens de optie **Transformeren** en vervolgens **Eerste rij als kolomkoppen gebruiken**.

1. Werk het gegevenstype voor de onderstaande kolommen bij:

   - **DateOfBirth**: datum
   - **CreatedOn**: datum/tijd/zone

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Geboortedatum transformeren naar datum.":::

1. Wijzig in het veld **Naam** in het rechterdeelvenster uw gegevensbron in **eCommerceContacts**.

1. Sla de gegevensbron op.

### <a name="ingest-online-purchase-data"></a>Online aankoopgegevens opnemen

1. Voeg nog een gegevensset toe aan dezelfde **eCommerce**-gegevensbron. Kies opnieuw de connector **Tekst/CSV**.

1. Voer de URL in voor de gegevens voor online aankopen: https://aka.ms/ciadclassonline.

1. Selecteer tijdens het bewerken van de gegevens de optie **Transformeren** en vervolgens **Eerste rij als kolomkoppen gebruiken**.

1. Werk het gegevenstype voor de onderstaande kolommen bij:

   - **PurchasedOn**: datum/tijd
   - **TotalPrice**: valuta

1. Wijzig in het veld **Naam** in het rechterdeelvenster uw gegevensbron in **eCommercePurchases**.

1. Sla de gegevensbron op.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Klantgegevens opnemen uit het loyaliteitsschema

1. Maak een gegevensbron met de naam **LoyaltyScheme** en selecteer de connector **Tekst/CSV**.

1. Voer de URL in voor eCommerce-contacten in https://aka.ms/ciadclasscustomerloyalty.

1. Selecteer tijdens het bewerken van de gegevens de optie **Transformeren** en vervolgens **Eerste rij als kolomkoppen gebruiken**.

1. Werk het gegevenstype voor de onderstaande kolommen bij:

   - **DateOfBirth**: datum
   - **RewardsPoints**: geheel getal
   - **CreatedOn**: datum/tijd

1. Wijzig in het veld **Naam** in het rechterdeelvenster uw gegevensbron in **loyCustomers**.

1. Sla de gegevensbron op.

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

## <a name="task-4---configure-transaction-churn-prediction"></a>Taak 4 - Configureer de voorspelling van het transactieverloop

Met de geharmoniseerde klantprofielen en activiteit beschikbaar kunnen we nu de voorspelling van het transactieverloop uitvoeren.

1. Ga naar **Informatie** > **Voorspellingen**.

1. Selecteer op het tabblad **Maken** de optie **Model gebruiken** op de tegel **Klantverloopmodel**.

1. Selecteer **Transactioneel** voor het type verloop en vervolgens **Aan de slag**.

1. Geef het model de naam **OOB voorspelling eCommerce transactieverloop** en de uitvoerentiteit **OOBeCommerceChurnPrediction**.

1. Selecteer **Volgende**.

1. Modelvoorkeuren definiëren:

   - **Voorspellingsvenster**: **60** dagen om te bepalen hoe ver in de toekomst we het klantverloop willen voorspellen.

   - **Definitie van verloop**: **60** dagen om de duur zonder aankoop aan te geven waarna een klant als verlopen wordt beschouwd.

     :::image type="content" source="media/model-levers.PNG" alt-text="Selecteer de modelvoorkeuren Voorspellingsvenster en Definitie van verloop.":::

1. Selecteer **Volgende**.

1. Selecteer **Aankoopgeschiedenis (vereist)** en selecteer **Gegevens toevoegen** voor aankoopgeschiedenis.

1. Selecteer **SalesOrderLine** en de entiteit eCommercePurchases en selecteer daarna **Volgende**. De vereiste gegevens worden automatisch ingevuld vanuit de activiteit. Selecteer **Opslaan** en daarna **Volgende**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Voeg eCommerce-entiteiten samen.":::

1. Sla de stap **Aanvullende gegevens (optioneel)** over.

1. Selecteer in de stap **Gegevensupdates** de optie **Maandelijks** voor het modelschema.

1. Selecteer nadat u alle details hebt nagekeken **Opslaan en uitvoeren**.

## <a name="task-5---review-model-results-and-explanations"></a>Taak 5 - Bekijk modelresultaten en uitleg

Laat het model de training en score van de gegevens voltooien. Bekijk de uitleg van het verloopmodel. Zie [Resultaten van voorspelling weergeven](predict-transactional-churn.md#view-prediction-results) voor meer informatie.

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Taak 6 - Maak een segment van klanten met een hoog verlooprisico

Door het productiemodel uit te voeren, wordt een nieuwe entiteit gemaakt, die wordt vermeld in **Gegevens** > **Entiteiten**. U kunt een nieuw segment maken op basis van de entiteit die door het model is gemaakt.

1. Selecteer op de resultatenpagina de optie **Segment maken**.

1. Maak een regel met behulp van de entiteit **OOBeCommerceChurnPrediction** en definieer het segment:
   - **Veld**: ChurnScore
   - **Operator**: groter dan
   - **Waarde**: 0.6

1. Selecteer **Opslaan** en **Uitvoeren** voor het segment.

U hebt nu een segment dat dynamisch wordt bijgewerkt en dat klanten met een hoog verlooprisico identificeert. Zie [Segmenten maken en beheren](segments.md) voor meer informatie.

> [!TIP]
> U kunt ook een segment maken voor een voorspellingsmodel vanaf de pagina **Segmenten** door **Nieuw** te selecteren en **Maken van** > **Intelligentie** te selecteren. Zie [Een nieuw segment maken met snelle segmenten](segment-quick.md) voor meer informatie.

[!INCLUDE [footer-include](includes/footer-banner.md)]
