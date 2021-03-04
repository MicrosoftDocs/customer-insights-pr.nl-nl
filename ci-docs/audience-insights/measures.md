---
title: Metingen maken en beheren
description: Definieer maatregelen om de prestaties van uw bedrijf te analyseren en weer te geven.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 5bcee3b4c51880740715575b18fd7a4dbf87e6d0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269922"
---
# <a name="define-and-manage-measures"></a>Meetcriteria definiëren en beheren

Metingen helpen u het klantgedrag en de bedrijfsprestaties beter te begrijpen door relevante waarden te halen uit [geharmoniseerde profielen](data-unification.md)​. Een bedrijf wil bijvoorbeeld de *totale uitgaven per klant* zien om inzicht te krijgen in de aankoopgeschiedenis van individuele klanten. Of meet *totale verkoop van het bedrijf* om inzicht te krijgen in de totale inkomsten van het hele bedrijf.  

Metingen worden gemaakt met behulp van de metingenbouwer, een gegevensqueryplatform met verschillende operators en eenvoudige toewijzingsopties. Hiermee kunt u de gegevens filteren, resultaten groeperen, [entiteitsrelatiepaden](relationships.md) detecteren en een voorbeeld van de uitvoer bekijken.

Gebruik de metingenbouwer om bedrijfsactiviteiten te plannen door klantgegevens op te vragen en inzichten te verkrijgen. Als u bijvoorbeeld een meting maakt van *totale uitgaven per klant* en *totaal rendement per klant*, helpt dit u een groep klanten met hoge uitgaven en toch een hoog rendement te identificeren. U kunt [een segment maken](segments.md) om de volgende beste acties aan te sturen. 

## <a name="create-a-measure"></a>Een meetcriterium maken

In deze sectie wordt uitgelegd hoe u een geheel nieuwe meting maakt. U kunt een meting bouwen met gegevenskenmerken van gegevensentiteiten waarvoor een relatie is ingesteld om verbinding te maken met de entiteit Klant. 

1. Ga in doelgroepinzichten naar **Metingen**.

1. Selecteer **Nieuw**.

1. Selecteer **Naam bewerken** en geef een **Naam** op voor de meting. 
   > [!NOTE]
   > Als uw nieuwe meetconfiguratie slechts twee velden heeft, bijvoorbeeld CustomerID en één berekening, wordt de uitvoer als een nieuwe kolom toegevoegd aan de door het systeem gegenereerde entiteit met de naam Customer_Measure. En u kunt de waarde van de meting zien in het geharmoniseerde klantprofiel. Andere metingen zullen hun eigen entiteiten genereren.

1. Kies in het configuratiegebied de aggregatiefunctie in het vervolgkeuzemenu **Functie selecteren**. Aggregatiefuncties omvatten: 
   - **Sum**
   - **Gemiddeld**
   - **Tellen**
   - **Aantal unieke**
   - **Max.**
   - **Min**
   - **Eerste**: neemt de eerste waarde van de gegevensrecord
   - **Laatste**: neemt de laatste waarde die aan de gegevensrecord is toegevoegd

   :::image type="content" source="media/measure-operators.png" alt-text="Operators voor de berekening van metingen.":::

1. Selecteer **Kenmerk toevoegen** om de gegevens te selecteren die u nodig hebt om deze meting te maken.
   
   1. Selecteer het tabblad **Kenmerken**. 
   1. Gegevensentiteit: kies de entiteit die het kenmerk bevat dat u wilt meten. 
   1. Gegevenskenmerk: kies het kenmerk dat u in de aggregatiefunctie wilt gebruiken om de meting te berekenen. U kunt slechts één kenmerk tegelijk selecteren.
   1. U kunt ook een gegevenskenmerk van een bestaande meting selecteren door het tabblad **Metingen** te selecteren. Of u kunt zoeken naar de naam van een entiteit of meting. 
   1. Selecteer **Toevoegen** om het geselecteerde kenmerk aan de meting toe te voegen.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Selecteer een kenmerk om in berekeningen te gebruiken.":::

1. Om complexere metingen te bouwen, kunt u meer kenmerken toevoegen of wiskundige operatoren gebruiken voor uw meetfunctie.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Maak een complexe meting met wiskundige operatoren.":::

1. Om filters toe te voegen, selecteert u het **Filter** in het configuratiegebied. 
  
   1. Selecteer in de sectie **Kenmerk toevoegen** van het deelvenster **Filters** het kenmerk dat u wilt gebruiken om filters te maken.
   1. Stel de filteroperatoren in om het filter voor elk geselecteerd kenmerk te definiëren.
   1. Selecteer **Toepassen** om de filters aan de meting toe te voegen.

1. Om dimensies toe te voegen, selecteert u **Dimensie** in het configuratiegebied. Dimensies worden weergegeven als kolommen in de entiteit voor metingenuitvoer.
   1. Selecteer **Dimensies bewerken** om gegevenskenmerken toe te voegen waarop u de meetwaarden wilt groeperen. Bijvoorbeeld plaats of gender. Standaard is de dimensie *CustomerID* geselecteerd om *metingen op klantniveau* te maken. U kunt de standaarddimensie verwijderen als u *metingen op bedrijfsniveau*​wilt maken.
   1. Selecteer **Gereed** om de dimensies aan de meting toe te voegen.

1. Als er meerdere paden zijn tussen de gegevensentiteit die u hebt toegewezen en de entiteit Klant, moet u een van de geïdentificeerde [entiteitsrelatiepaden](relationships.md)​kiezen. Meetresultaten kunnen variëren, afhankelijk van het geselecteerde pad.
   1. Selecteer **Gegevensvoorkeuren** en kies het entiteitspad dat moet worden gebruikt om uw meting te identificeren.
   1. Selecteer **Gereed** om uw selectie toe te passen. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Selecteer het entiteitspad voor de meting.":::

1. Als u meer berekeningen voor de meting wilt toevoegen, selecteert u **Nieuwe berekening**​. U kunt alleen entiteiten op hetzelfde entiteitspad gebruiken voor nieuwe berekeningen. Meer berekeningen worden weergegeven als nieuwe kolommen in de entiteit voor metingenuitvoer.

1. Selecteer **...** in de berekening om een berekening uit een meting te **Dupliceren** **Naam wijzigen** of te **Verwijderen**.

1. In het gebied **Voorbeeld** ziet u het gegevensschema van de entiteit voor metingenuitvoer, inclusief filters en dimensies. Het voorbeeld reageert dynamisch op wijzigingen in de configuratie.

1. Selecteer **Uitvoeren** om resultaten voor de geconfigureerde meting te berekenen. Selecteer **Opslaan en sluiten** als u de huidige configuratie wilt behouden en de meting later wilt uitvoeren.

1. Ga naar **Metingen** om de nieuw gemaakte meting in de lijst te zien.

## <a name="manage-your-measures"></a>Uw meetcriteria beheren

Nadat u [een meting hebt gemaakt](#create-a-measure), ziet u een lijst met metingen op de pagina **Metingen**.

U vindt informatie over het type meting, de maker, de datum waarop de meting is gemaakt en de status. Wanneer u een meting uit de lijst selecteert, kunt u een voorbeeld van de uitvoer bekijken en een .CSV-bestand downloaden.

Selecteer om al uw meetcriteria tegelijkertijd te vernieuwen de optie **Alles vernieuwen** zonder een specifiek meetcriterium te selecteren.

> [!div class="mx-imgBorder"]
> ![Acties om afzonderlijke meetcriteria te beheren](media/measure-actions.png "Acties om afzonderlijke meetcriteria te beheren")

Selecteer een meting in de lijst voor de volgende opties:

- Selecteer de naam van het meetcriterium om de details te zien.
- **Bewerk** de configuratie van het meetcriterium.
- **Vernieuw** de meting op basis van de laatste gegevens.
- **Hernoem** het meetcriterium.
- **Verwijder** het meetcriterium.
- **Activeren** of **Deactiveren**. Inactieve metingen worden niet vernieuwd tijdens een [geplande vernieuwing](system.md#schedule-tab)​.

> [!TIP]
> Er zijn [zes soorten status](system.md#status-types) voor taken/processen. Bovendien zijn de meeste processen [afhankelijk van andere stroomafwaartse processen](system.md#refresh-policies). U kunt de status van een proces selecteren om voortgangsdetails te zien van de volledige taak. Na het selecteren van **Details bekijken** voor een van de taken vindt u aanvullende informatie: verwerkingstijd, de laatste verwerkingsdatum en alle fouten en waarschuwingen die bij de taak horen.

## <a name="next-step"></a>Volgende stap

U kunt bestaande metingen gebruiken om [een klantsegment](segments.md)​te maken.


[!INCLUDE[footer-include](../includes/footer-banner.md)]