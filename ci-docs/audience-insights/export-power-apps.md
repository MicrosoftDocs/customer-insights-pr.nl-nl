---
title: Power Apps-connector
description: Maak verbinding met Power Apps en Power Automate.
ms.date: 08/21/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b6ec103e29e218b2f27bfc1193300ea793a6b30b
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405467"
---
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Apps-connector (preview)

Breng geharmoniseerde klantprofielen naar uw gepersonaliseerde apps met Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Verbinden met Power Apps en Dynamics 365 Customer Insights

Customer Insights is een van de vele [beschikbare bronnen voor gegevens in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).

Raadpleeg de Power Apps-documentatie om te leren hoe [hoe u een gegevensverbinding kunt toevoegen aan een app](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection). We raden u aan om ook te bekijken [hoe Power Apps delegeren gebruikt om grote gegevenssets in Canvas-apps te verwerken](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Beschikbare entiteiten

Na het toevoegen van Customer Insights als een gegevensverbinding, kunt u de volgende entiteiten kiezen in Power Apps:

- Klant: om gegevens uit het [geharmoniseerde klantprofiel](customer-profiles.md) te gebruiken.
- Geharmoniseerde klantactiviteit: om de [geharmoniseerde tijdlijn](activities.md) in de app weer te geven.

## <a name="limitations"></a>Beperkingen

### <a name="retrievable-entities"></a>Ophaalbare entiteiten

U kunt alleen de entiteiten **Klant**, **UnifiedActivity** en **Segmenten** ophalen via de Power Apps-connector. Andere entiteiten worden weergegeven omdat de onderliggende connector deze ondersteunt via triggers in Power Automate.  

### <a name="delegation"></a>Overdracht

Delegatie werkt voor de entiteit Klant en de entiteit UnifiedActivity. 

- Delegatie voor **Klant**-entiteit: om delegatie voor deze entiteit te gebruiken, moeten de velden worden geïndexeerd in [Zoek- en filterindex](search-filter-index.md).  

- Delegatie voor **UnifiedActivity**: delegatie voor deze entiteit werkt alleen voor de velden **ActivityId** en **CustomerId**.  

- Zie [Delegeerbare functies en bewerkingen in Power Apps](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps) voor meer informatie over delegeren . 

## <a name="example-gallery-control"></a>Voorbeeld galeriebesturingselement

U voegt bijvoorbeeld klantprofielen toe aan een [galeriebesturingselement](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).

1. Voeg een besturingselement **Galerie** toe aan een app die u aan het bouwen bent.

> [!div class="mx-imgBorder"]
> ![Een galerie-element toevoegen](media/connector-powerapps9.png "Een galerie-element toevoegen")

1. Selecteer **Klant** als gegevensbron voor items.

    > [!div class="mx-imgBorder"]
    > ![Een gegevensbron selecteren](media/choose-datasource-powerapps.png "Een gegevensbron selecteren")

1. U kunt het gegevenspaneel aan de rechterkant wijzigen om te selecteren welk veld voor de entiteit Klant moet worden weergegeven in de galerie.

1. Als u een willekeurig veld van de geselecteerde klant in de galerie wilt weergeven, vult u de eigenschap Tekst van een label in: **{Name_of_the_gallery}.Selected.{property_name}**

    Voorbeeld: Gallery1.Selected.address1_city

1. Als u de geharmoniseerde tijdlijn voor een klant wilt weergeven, voegt u een galerie-element toe en voegt u de eigenschap Items toe: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    Voorbeeld: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)
