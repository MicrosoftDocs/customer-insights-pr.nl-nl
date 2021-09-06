---
title: Power Apps-connector
description: Maak verbinding met Power Apps en Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: fc0af656cd5b436d9efd65b2a2c75dde9c9deb9dbcdd56ffc6a960f5878a631f
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031743"
---
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Apps-connector (preview)

Breng geharmoniseerde klantprofielen naar uw gepersonaliseerde apps met Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Verbinden met Power Apps en Dynamics 365 Customer Insights

Customer Insights is een van de vele [beschikbare bronnen voor gegevens in Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Raadpleeg de Power Apps-documentatie om te leren hoe [hoe u een gegevensverbinding kunt toevoegen aan een app](/powerapps/maker/canvas-apps/add-data-connection). We raden u aan om ook te bekijken [hoe Power Apps delegeren gebruikt om grote gegevenssets in Canvas-apps te verwerken](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Beschikbare entiteiten

Na het toevoegen van Customer Insights als een gegevensverbinding, kunt u de volgende entiteiten kiezen in Power Apps:

- Klant: om gegevens uit het [geharmoniseerde klantprofiel](customer-profiles.md) te gebruiken.
- Geharmoniseerde activiteit: om de [activiteitentijdlijn weer te geven](activities.md) in de app.

## <a name="limitations"></a>Beperkingen

### <a name="retrievable-entities"></a>Ophaalbare entiteiten

U kunt alleen de entiteiten **Klant**, **UnifiedActivity** en **Segmenten** ophalen via de Power Apps-connector. Andere entiteiten worden weergegeven omdat de onderliggende connector deze ondersteunt via triggers in Power Automate.  

### <a name="delegation"></a>Overdracht

Delegatie werkt voor de entiteit Klant en de entiteit UnifiedActivity. 

- Delegatie voor **Klant**-entiteit: om delegatie voor deze entiteit te gebruiken, moeten de velden worden geïndexeerd in [Zoek- en filterindex](search-filter-index.md).  

- Delegatie voor **UnifiedActivity**: delegatie voor deze entiteit werkt alleen voor de velden **ActivityId** en **CustomerId**.  

- Zie [Delegeerbare functies en bewerkingen in Power Apps](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps) voor meer informatie over delegeren . 

## <a name="example-gallery-control"></a>Voorbeeld galeriebesturingselement

U voegt bijvoorbeeld klantprofielen toe aan een [galeriebesturingselement](/powerapps/maker/canvas-apps/add-gallery).

1. Voeg een besturingselement **Galerie** toe aan een app die u aan het bouwen bent.

> [!div class="mx-imgBorder"]
> ![Een galerie-element toevoegen.](media/connector-powerapps9.png "Een galerie-element toevoegen")

1. Selecteer **Klant** als gegevensbron voor items.

    > [!div class="mx-imgBorder"]
    > ![Een gegevensbron selecteren.](media/choose-datasource-powerapps.png "Een gegevensbron selecteren")

1. U kunt het gegevenspaneel aan de rechterkant wijzigen om te selecteren welk veld voor de entiteit Klant moet worden weergegeven in de galerie.

1. Als u een willekeurig veld van de geselecteerde klant in de galerie wilt weergeven, vult u de eigenschap Tekst van een label in: **{Name_of_the_gallery}.Selected.{property_name}**

    Voorbeeld: Gallery1.Selected.address1_city

1. Als u de geharmoniseerde tijdlijn voor een klant wilt weergeven, voegt u een galerie-element toe en voegt u de eigenschap Items toe: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    Voorbeeld: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]