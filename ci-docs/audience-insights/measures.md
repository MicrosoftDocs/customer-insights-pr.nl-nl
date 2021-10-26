---
title: Meetcriteria maken en beheren
description: Definieer meetcriteria om de prestaties van uw bedrijf te analyseren en weer te geven.
ms.date: 09/30/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 39acca78c022bc15ebc15dc80f21fe175da04d4d
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/11/2021
ms.locfileid: "7622853"
---
# <a name="define-and-manage-measures"></a>Meetcriteria definiëren en beheren

Meetcriteria helpen u het klantgedrag en de bedrijfsprestaties beter te begrijpen. Ze kijken naar relevante waarden uit [geharmoniseerde profielen](data-unification.md). Een bedrijf wil bijvoorbeeld de *totale uitgaven per klant* bekijken om de aankoopgeschiedenis van een individuele klant te begrijpen of de *totale omzet van het bedrijf* meten om inzicht te krijgen in de omzet op geaggregeerd niveau in het hele bedrijf.  

Meetcriteria worden gemaakt met behulp van de opbouwfunctie voor meetcriteria, een gegevensqueryplatform met verschillende operators en eenvoudige toewijzingsopties. Hiermee kunt u de gegevens filteren, resultaten groeperen, [entiteitsrelatiepaden](relationships.md) detecteren en een voorbeeld van de uitvoer bekijken.

Gebruik de opbouwfunctie voor meetcriteria om bedrijfsactiviteiten te plannen door klantgegevens op te vragen en inzichten te verkrijgen. Als u bijvoorbeeld een meetcriterium maakt van *totale uitgaven per klant* en *totaal rendement per klant*, helpt dit u een groep klanten met hoge uitgaven en toch een hoog rendement te identificeren. U kunt [een segment maken](segments.md) om de volgende beste acties aan te sturen. 

## <a name="build-your-own-measure-from-scratch"></a>Uw eigen meetcriterium bouwen

In deze sectie wordt uitgelegd hoe u een geheel nieuw meetcriterium maakt. U kunt een meting maken met gegevenskenmerken van gegevensentiteiten waarvoor een relatie is ingesteld om verbinding te maken met de entiteit geharmoniseerd klantprofiel.

# <a name="individual-customers-b2c"></a>[Individuele klanten (B2C)](#tab/b2c)

1. Ga in doelgroepinzichten naar **Meetcriteria**.

1. Selecteer **Nieuw** en kies **Bouw uw eigen**.

1. Selecteer **Naam bewerken** en geef een **Naam** op voor het meetcriterium. 

1. Kies in het configuratiegebied de aggregatiefunctie uit het vervolgkeuzemenu **Functie selecteren**. Aggregatiefuncties omvatten: 
   - **Sum**
   - **Gemiddeld**
   - **Tellen**
   - **Aantal unieke**
   - **Max.**
   - **Min**
   - **Eerste**: neemt de eerste waarde van de gegevensrecord
   - **Laatste**: neemt de laatste waarde die aan de gegevensrecord is toegevoegd

   :::image type="content" source="media/measure-operators.png" alt-text="Operators voor berekeningen van meetcriteria.":::

1. Selecteer **Kenmerk toevoegen** om de gegevens te selecteren die u nodig hebt om dit meetcriterium te maken.
   
   1. Selecteer het tabblad **Kenmerken**. 
   1. Gegevensentiteit: kies de entiteit die het kenmerk bevat dat u wilt meten. 
   1. Gegevenskenmerk: kies het kenmerk dat u in de aggregatiefunctie wilt gebruiken om het meetcriterium te berekenen. U kunt slechts één kenmerk tegelijk selecteren.
   1. U kunt ook een gegevenskenmerk van een bestaand meetcriterium selecteren door het tabblad **Meetcriteria** te selecteren, of u kunt zoeken naar de naam van een entiteit of meetcriterium. 
   1. Selecteer **Toevoegen** om het geselecteerde kenmerk aan het meetcriterium toe te voegen.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Selecteer een kenmerk om in berekeningen te gebruiken.":::

1. Om complexere meetcriteria te bouwen, kunt u meer kenmerken toevoegen of wiskundige operatoren gebruiken voor uw functie voor meetcriteria.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Maak een complex meetcriterium met wiskundige operatoren.":::

1. Om filters toe te voegen, selecteert u het **Filter** in het configuratiegebied. 
  
   1. Selecteer in de sectie **Kenmerk toevoegen** van het deelvensteer **Filters** het kenmerk dat u wilt gebruiken om filters te maken.
   1. Stel de filteroperatoren in om het filter voor elk geselecteerd kenmerk te definiëren.
   1. Selecteer **Toepassen** om de filters aan het meetcriterium toe te voegen.

1. Om dimensies toe te voegen, selecteert u **Dimensie** in het configuratiegebied. Dimensies worden weergegeven als kolommen in de entiteit voor uitvoer van meetcriteria.
 
   1. Selecteer **Dimensies bewerken** om gegevenskenmerken toe te voegen waarop u de meetwaarden wilt groeperen. Bijvoorbeeld plaats of gender. Standaard is de dimensie *CustomerID* geselecteerd om *meetcriteria op klantniveau* te maken. U kunt de standaarddimensie verwijderen als u *meetcriteria op bedrijfsniveau*​wilt maken.
   1. Selecteer **Gereed** om de dimensies aan het meetcriterium toe te voegen.

1. Als er waarden in uw gegevens zijn die u moet vervangen door een geheel getal, selecteert u **Regels**. Configureer de regel en zorg ervoor dat u alleen hele getallen kiest als vervanging. Vervang bijvoorbeeld *null* door *0*.

1. Als er meerdere paden zijn tussen de gegevensentiteit die u hebt toegewezen en de entiteit *Klant*, moet u een van de geïdentificeerde [entiteitsrelatiepaden​](relationships.md) kiezen. Meetresultaten kunnen variëren, afhankelijk van het geselecteerde pad. 
   
   1. Selecteer **Relatiepad** en kies het entiteitspad dat moet worden gebruikt om uw meting te identificeren. Als er maar één pad is naar de entiteit *Klant*, wordt dit besturingselement niet weergegeven.
   1. Selecteer **Gereed** om uw selectie toe te passen. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Selecteer het entiteitspad voor het meetcriterium.":::

1. Als u meer berekeningen voor het meetcriterium wilt toevoegen, selecteert u **Nieuwe berekening**​. U kunt alleen entiteiten op hetzelfde entiteitspad gebruiken voor nieuwe berekeningen. Meer berekeningen worden weergegeven als nieuwe kolommen in de entiteit voor uitvoer van meetcriteria.

1. Selecteer **...** in de berekening om een berekening uit een meetcriterium te **Dupliceren** **Naam wijzigen** of te **Verwijderen**.

1. In het gebied **Voorbeeld** ziet u het gegevensschema van de entiteit voor uitvoer van meetcriteria, inclusief filters en dimensies. Het voorbeeld reageert dynamisch op wijzigingen in de configuratie.

1. Selecteer **Uitvoeren** om resultaten voor het geconfigureerde meetcriterium te berekenen. Selecteer **Opslaan en sluiten** als u de huidige configuratie wilt behouden en het meetcriterium later wilt uitvoeren.

1. Ga naar **Meetcriteria** om het nieuw gemaakte meetcriterium in de lijst te zien.

# <a name="business-accounts-b2b"></a>[Zakelijke accounts (B2B)](#tab/b2b)

1. Ga in doelgroepinzichten naar **Meetcriteria**.

1. Selecteer **Nieuw** en kies **Bouw uw eigen**.

1. Selecteer **Naam bewerken** en geef een **Naam** op voor het meetcriterium. 

1. Kies in het configuratiegebied de aggregatiefunctie uit het vervolgkeuzemenu **Functie selecteren**. Aggregatiefuncties omvatten: 
   - **Sum**
   - **Gemiddeld**
   - **Tellen**
   - **Aantal unieke**
   - **Max.**
   - **Min**
   - **Eerste**: neemt de eerste waarde van de gegevensrecord
   - **Laatste**: neemt de laatste waarde die aan de gegevensrecord is toegevoegd

   :::image type="content" source="media/measure-operators.png" alt-text="Operators voor berekeningen van meetcriteria.":::

1. Selecteer **Kenmerk toevoegen** om de gegevens te selecteren die u nodig hebt om dit meetcriterium te maken.
   
   1. Selecteer het tabblad **Kenmerken**. 
   1. Gegevensentiteit: kies de entiteit die het kenmerk bevat dat u wilt meten. 
   1. Gegevenskenmerk: kies het kenmerk dat u in de aggregatiefunctie wilt gebruiken om het meetcriterium te berekenen. U kunt slechts één kenmerk tegelijk selecteren.
   1. U kunt ook een gegevenskenmerk van een bestaand meetcriterium selecteren door het tabblad **Meetcriteria** te selecteren, of u kunt zoeken naar de naam van een entiteit of meetcriterium. 
   1. Selecteer **Toevoegen** om het geselecteerde kenmerk aan het meetcriterium toe te voegen.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Selecteer een kenmerk om in berekeningen te gebruiken.":::

1. Om complexere meetcriteria te bouwen, kunt u meer kenmerken toevoegen of wiskundige operatoren gebruiken voor uw functie voor meetcriteria.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Maak een complex meetcriterium met wiskundige operatoren.":::

1. Om filters toe te voegen, selecteert u het **Filter** in het configuratiegebied. 
  
   1. Selecteer in de sectie **Kenmerk toevoegen** van het deelvensteer **Filters** het kenmerk dat u wilt gebruiken om filters te maken.
   1. Stel de filteroperatoren in om het filter voor elk geselecteerd kenmerk te definiëren.
   1. Selecteer **Toepassen** om de filters aan het meetcriterium toe te voegen.

1. Om dimensies toe te voegen, selecteert u **Dimensie** in het configuratiegebied. Dimensies worden weergegeven als kolommen in de entiteit voor uitvoer van meetcriteria.
 
   1. Selecteer **Dimensies bewerken** om gegevenskenmerken toe te voegen waarop u de meetwaarden wilt groeperen. Bijvoorbeeld plaats of gender. Standaard is de dimensie *CustomerID* geselecteerd om *meetcriteria op klantniveau* te maken. U kunt de standaarddimensie verwijderen als u *meetcriteria op bedrijfsniveau*​wilt maken.
   1. Selecteer **Gereed** om de dimensies aan het meetcriterium toe te voegen.

1. Als er waarden in uw gegevens zijn die u moet vervangen door een geheel getal, selecteert u **Regels**. Configureer de regel en zorg ervoor dat u alleen hele getallen kiest als vervanging. Vervang bijvoorbeeld *null* door *0*.

1. U kunt de schakeloptie **Subaccounts totaliseren** gebruiken als u [accounts gebruikt met hiërarchieën](relationships.md#set-up-account-hierarchies).
   - Als deze is ingesteld op **Uit** wordt de meting voor elke account berekend. Elke account krijgt een eigen resultaat.
   - Als deze is ingesteld op **Aan**, selecteert u **Bewerken** om de accounthiërarchie te kiezen op basis van de opgenomen hiërarchieën. De meting levert slechts één resultaat op omdat deze wordt geaggregeerd met subaccounts.

1. Als er meerdere paden zijn tussen de gegevensentiteit die u hebt toegewezen en de entiteit *Klant*, moet u een van de geïdentificeerde [entiteitsrelatiepaden​](relationships.md) kiezen. Meetresultaten kunnen variëren, afhankelijk van het geselecteerde pad. 
   
   1. Selecteer **Relatiepad** en kies het entiteitspad dat moet worden gebruikt om uw meting te identificeren. Als er maar één pad is naar de entiteit *Klant*, wordt dit besturingselement niet weergegeven.
   1. Selecteer **Gereed** om uw selectie toe te passen. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Selecteer het entiteitspad voor het meetcriterium.":::

1. Selecteer **...** in de berekening om een berekening uit een meetcriterium te **Dupliceren** **Naam wijzigen** of te **Verwijderen**.

1. In het gebied **Voorbeeld** ziet u het gegevensschema van de entiteit voor uitvoer van meetcriteria, inclusief filters en dimensies. Het voorbeeld reageert dynamisch op wijzigingen in de configuratie.

1. Selecteer **Uitvoeren** om resultaten voor het geconfigureerde meetcriterium te berekenen. Selecteer **Opslaan en sluiten** als u de huidige configuratie wilt behouden en het meetcriterium later wilt uitvoeren.

1. Ga naar **Meetcriteria** om het nieuw gemaakte meetcriterium in de lijst te zien.

---

## <a name="use-a-template-to-build-a-measure"></a>Een sjabloon gebruiken om een meetcriterium op te stellen

U kunt vooraf gedefinieerde sjablonen van veelgebruikte meetcriteria gebruiken om deze te maken. Gedetailleerde beschrijvingen van de sjablonen en een begeleide ervaring helpen u bij het efficiënt maken van meetcriteria. Sjablonen bouwen voort op toegewezen gegevens uit de entiteit *Unified Activity*. Zorg er dus voor dat u [klantactiviteiten](activities.md) hebt geconfigureerd voordat u een meetcriterium maakt op basis van een sjabloon.

# <a name="individual-customers-b2c"></a>[Individuele klanten (B2C)](#tab/b2c)

U kunt vooraf gedefinieerde sjablonen van veelgebruikte meetcriteria gebruiken om deze te maken. Gedetailleerde beschrijvingen van de sjablonen en een begeleide ervaring helpen u bij het efficiënt maken van meetcriteria. Sjablonen bouwen voort op toegewezen gegevens uit de entiteit *Unified Activity*. Zorg er dus voor dat u [klantactiviteiten](activities.md) hebt geconfigureerd voordat u een meetcriterium maakt op basis van een sjabloon.

Beschikbare sjablonen voor meetcriteria: 
- Gemiddelde transactiewaarde (ATV)
- Totale transactiewaarde
- Gemiddelde dagelijkse omzet
- Gemiddelde jaaromzet
- Aantal transacties
- Verdiende loyaliteitspunten
- Verzilverde loyaliteitspunten
- Saldo loyaliteitspunten
- Actieve levensduur van klant
- Lidmaatschapsduur van loyaliteitsprogramma
- Tijd sinds laatste aankoop

De volgende procedure beschrijft de stappen om een nieuw meetcriterium op te stellen met behulp van een sjabloon.

1. Ga in doelgroepinzichten naar **Meetcriteria**.

1. Selecteer **Nieuw** en selecteer **Een sjabloon kiezen**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Schermopname van het vervolgkeuzemenu bij het maken van een nieuw meetcriterium met markering op sjabloon.":::

1. Zoek de sjabloon die bij uw behoeften past en selecteer **Sjabloon kiezen**.

1. Bekijk de vereiste gegevens en selecteer **Aan de slag** als u over alle gegevens beschikt.

1. Stel in het deelvenster **Naam bewerken** de naam in voor uw meetcriterium en de uitvoerentiteit. 

1. Selecteer **Gereed**.

1. Definieer in de sectie **Tijdsperiode instellen** het tijdsbestek van de te gebruiken gegevens. Kies of u wilt dat het nieuwe meetcriterium de hele gegevensset omvat door **Altijd** te selecteren of dat u wilt dat het meetcriterium zich concentreert op een **Specifieke tijdsperiode**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Schermopname die de tijdsperiode laat zien bij het configureren van een meetcriterium vanuit een sjabloon.":::

1. Selecteer in de volgende sectie de optie **Gegevens toevoegen** om de activiteiten te kiezen en de bijbehorende gegevens toe te wijzen vanuit uw entiteit *Unified Activity*.

    1. Stap 1 van 2: kies onder **Type activiteit** het type entiteit dat u wilt gebruiken. Selecteer voor **Activiteiten** de entiteiten die u wilt toewijzen.
    1. Stap 2 van 2: kies het kenmerk van de entiteit *Unified Activity* voor het onderdeel dat is vereist door de formule. Voor Gemiddelde transactiewaarde is dit bijvoorbeeld het kenmerk dat de transactiewaarde vertegenwoordigt. Kies voor **Tijdstempel van activiteit** het kenmerk van de entiteit Unified Activity dat de datum en tijd van de activiteit vertegenwoordigt.
   
1. Zodra de gegevenstoewijzing is geslaagd, ziet u de status als **Voltooid** en de naam van de toegewezen activiteiten en kenmerken.

   :::image type="content" source="media/measure-template-configured.png" alt-text="Schermopname van een voltooide configuratie van een meetsjabloon.":::

1. U kunt nu **Uitvoeren** selecteren om de resultaten van het meetcriterium te berekenen. Selecteer **Concept opslaan** om het later te verfijnen.

# <a name="business-accounts-b2b"></a>[Zakelijke accounts (B2B)](#tab/b2b)

Deze functie is alleen beschikbaar voor metingen die zijn gemaakt in omgevingen met individuele klanten als primaire doelgroep.

---

## <a name="manage-your-measures"></a>Uw meetcriteria beheren

U vindt de lijst met meetcriteria op de pagina **Meetcriteria**.

U vindt informatie over het type meetcriterium, de maker, de datum waarop het meetcriterium is gemaakt en de status. Wanneer u een meetcriterium uit de lijst selecteert, kunt u een voorbeeld van de uitvoer bekijken en een CSV-bestand downloaden.

Selecteer om al uw meetcriteria tegelijkertijd te vernieuwen de optie **Alles vernieuwen** zonder een specifiek meetcriterium te selecteren.

> [!div class="mx-imgBorder"]
> ![Acties om afzonderlijke meetcriteria te beheren.](media/measure-actions.png "Acties om afzonderlijke meetcriteria te beheren.")

Selecteer een meetcriterium in de lijst voor de volgende opties:

- Selecteer de naam van het meetcriterium om de details te zien.
- **Bewerk** de configuratie van het meetcriterium.
- **Vernieuw** het meetcriterium op basis van de laatste gegevens.
- **Hernoem** het meetcriterium.
- **Verwijder** het meetcriterium.
- **Activeren** of **Deactiveren**. Inactieve meetcriteria worden niet vernieuwd tijdens een [geplande vernieuwing](system.md#schedule-tab)​.

> [!TIP]
> Er zijn [zes soorten status](system.md#status-types) voor taken/processen. Bovendien zijn de meeste processen [afhankelijk van andere stroomafwaartse processen](system.md#refresh-policies). U kunt de status van een proces selecteren om voortgangsdetails te zien van de volledige taak. Na het selecteren van **Zie details** voor een van de taken van de functie vindt u aanvullende informatie: verwerkingstijd, de laatste verwerkingsdatum en alle fouten en waarschuwingen die bij de taak horen.

## <a name="next-step"></a>Volgende stap

U kunt bestaande meetcriteria gebruiken om [een klantsegment](segments.md) te maken.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
