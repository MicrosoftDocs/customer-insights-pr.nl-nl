---
title: Power Apps-connector (preview)
description: Maak verbinding met Power Apps en Power Automate.
ms.date: 10/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 0b71f723d1e491d422d24b1be6616d2f33c95d40
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055254"
---
# <a name="power-apps-connector-preview"></a>Power Apps-connector (preview)

Breng geharmoniseerde klantprofielen naar uw gepersonaliseerde apps met Microsoft Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Verbinden met Power Apps en Dynamics 365 Customer Insights

Customer Insights is een van de vele [beschikbare bronnen voor gegevens in Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Raadpleeg de Power Apps-documentatie om te leren hoe [hoe u een gegevensverbinding kunt toevoegen aan een app](/powerapps/maker/canvas-apps/add-data-connection). We raden u aan om ook te bekijken [hoe Power Apps delegeren gebruikt om grote gegevenssets in Canvas-apps te verwerken](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Beschikbare entiteiten

Na het toevoegen van Customer Insights als een gegevensverbinding, kunt u de volgende entiteiten kiezen in Power Apps:

- **Klant**: om gegevens uit het [geharmoniseerde klantprofiel](customer-profiles.md) te gebruiken.
- **UnifiedActivity**: om de [activiteitentijdlijn](activities.md) weer te geven in de app.
- **ContactProfile**: om de contactpersonen van een klant weer te geven. Deze entiteit is alleen beschikbaar in Customer Insights-omgevingen voor zakelijke accounts.

## <a name="limitations"></a>Beperkingen

### <a name="retrievable-entities"></a>Ophaalbare entiteiten

U kunt alleen de entiteiten **Klant**, **UnifiedActivity**, **Segmenten** en **ContactProfile** verbinden via de Power Apps-connector. ContactProfile is alleen beschikbaar in Customer Insights-exemplaren voor zakelijke accounts. Andere entiteiten worden weergegeven omdat de onderliggende connector deze ondersteunt via triggers in Power Automate.

U kunt maximaal 100 oproepen per 60 seconden uitvoeren. U kunt het API-eindpunt meerdere keren aanroepen door de parameter $skip te gebruiken. [Meer informatie over de parameter $skip](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Delegering

Delegatie werkt voor de entiteit **Klant** en de entiteit **UnifiedActivity**. 

- Delegatie voor **Klant**-entiteit: om delegatie voor deze entiteit te gebruiken, moeten de velden worden geïndexeerd in [Zoek- en filterindex](search-filter-index.md).  
- Delegatie voor **UnifiedActivity**: delegatie voor deze entiteit werkt alleen voor de velden **ActivityId** en **CustomerId**.  
- Delegatie voor **ContactProfile**: delegatie voor deze entiteit werkt alleen voor de velden **ContactId** en **CustomerId**. ContactProfile is alleen beschikbaar in Customer Insights-omgevingen voor zakelijke accounts.

Ga voor meer informatie over delegatie naar [Power Apps delegeerbare functies en bewerkingen](/powerapps/maker/canvas-apps/delegation-overview). 

## <a name="example-gallery-control"></a>Voorbeeld galeriebesturingselement

U kunt klantprofielen toevoegen aan een [besturingselement van een galerij](/powerapps/maker/canvas-apps/add-gallery).

1. Voeg een besturingselement **Galerie** toe aan een app die u aan het bouwen bent.

    > [!div class="mx-imgBorder"]
    > ![Een galerie-element toevoegen.](media/connector-powerapps9.png "Een galerie-element toevoegen.")

2. Selecteer **Klant** als gegevensbron voor items.

    > [!div class="mx-imgBorder"]
    > ![Een gegevensbron selecteren.](media/choose-datasource-powerapps.png "Een gegevensbron selecteren.")

3. U kunt het gegevenspaneel aan de rechterkant wijzigen om te selecteren welk veld voor de entiteit Klant moet worden weergegeven in de galerie.

4. Als u een willekeurig veld van de geselecteerde klant in de galerie wilt weergeven, vult u de eigenschap **Tekst** van een label in met **{Name_of_the_gallery}.Selected.{property_name}**  
    - Bijvoorbeeld: _Gallery1.Selected.address1_city_

5. Als u de geharmoniseerde tijdlijn voor een klant wilt weergeven, voegt u een galerie-element toe en voegt u de eigenschap **Items** toe met **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Bijvoorbeeld: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE [footer-include](includes/footer-banner.md)]
