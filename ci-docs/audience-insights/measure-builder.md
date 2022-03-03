---
title: Nieuwe metingen maken met de metingbouwer
description: Bouw helemaal vanaf de grond metingen om de belangrijkste gegevens over uw bedrijf te analyseren.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: 5329aea240ba40ec8698b3ddeb67fb5f21c62bbd
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359897"
---
# <a name="use-measure-builder-to-create-measures-from-scratch"></a>Gebruik de metingenbouwer om helemaal vanaf de grond metingen te maken

In dit artikel wordt uitgelegd hoe u vanaf de grond een nieuwe [meting](measures.md) maakt. Met de metingbouwer kunt u berekeningen definiëren met behulp van rekenkundige operatoren, aggregatiefuncties en filters. U kunt een meting bouwen met kenmerken van entiteiten die gerelateerd zijn aan de geharmoniseerde entiteit *Klant*. 

Het maken van metingen in B-naar-C en B-naar-B omgevingen werkt op dezelfde manier. Als uw B-naar-B omgeving echter [gebruikmaakt van accounts met hiërarchieën](relationships.md#set-up-account-hierarchies), kunt u ervoor kiezen de meting te aggregeren over gerelateerde subaccounts.

U kunt ook snel een meting maken door te kiezen uit een reeks veelgebruikte en vooraf gedefinieerde metingen. Zie [Een sjabloon gebruiken om een meting te bouwen](measure-templates.md) voor meer informatie.

# <a name="individual-consumers-b-to-c"></a>[Individuele consumenten (B-to-C)](#tab/b2c)

U kunt metingen maken op het niveau van individuele klanten (klantkenmerk, klantmeting) of op het niveau van het bedrijf/de organisatie (bedrijfsmeting). Klantkenmerk en klantmeting zijn twee typen waarmee u de prestaties per klant kunt volgen. Bijvoorbeeld de totale bestedingen per klant. Met bedrijfsmetingen kunt u de prestaties per bedrijf volgen. Bijvoorbeeld de totale omzet van het bedrijf.

- Klantkenmerk: genereert uitvoer als een nieuw kenmerk, dat wordt opgeslagen als een nieuwe kolom in de door het systeem gegenereerde entiteit met de naam *Klantmeting*. Bij het vernieuwen van een klantkenmerk worden alle andere klantkenmerken in de entiteit *Klantmeting* gelijktijdig vernieuwd. Daarnaast worden klantkenmerken weergegeven in de klantprofielkaart. Nadat het klantkenmerk is uitgevoerd of opgeslagen, kunt u het niet meer wijzigen in een klantmeting.

- Klantmeting: genereert uitvoer als een zelfstandige entiteit en u kunt deze niet wijzigen in een klantkenmerk nadat het is uitgevoerd of opgeslagen. Klantmetingen worden niet weergegeven in de klantprofielkaart.

- Bedrijfsmeting: genereert uitvoer als een zelfstandige entiteit en wordt weergegeven op de startpagina van uw Customer Insights-omgeving.

1. Ga naar **Metingen**.

1. Selecteer **Nieuw** en kies **Bouw uw eigen**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Leeg configuratiescherm voor een B-naar-C-meting. ":::

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
   - **ArgMax**: vindt het gegevensrecord met de maximale waarde van een doelfunctie
   - **ArgMin**: vindt het gegevensrecord met de minimale waarde van een doelfunctie

1. Selecteer **Kenmerk toevoegen** om de gegevens te selecteren die u nodig hebt om dit meetcriterium te maken.
   
   1. Selecteer het tabblad **Kenmerken**. 
   1. Gegevensentiteit: kies de entiteit die het kenmerk bevat dat u wilt meten. 
   1. Gegevenskenmerk: kies het kenmerk dat u in de aggregatiefunctie wilt gebruiken om het meetcriterium te berekenen. U kunt slechts één kenmerk tegelijk selecteren.
   1. U kunt ook een gegevenskenmerk van een bestaand meetcriterium selecteren door het tabblad **Meetcriteria** te selecteren, of u kunt zoeken naar de naam van een entiteit of meetcriterium. 
   1. Selecteer **Toevoegen** om het geselecteerde kenmerk aan het meetcriterium toe te voegen.

1. Om complexere meetcriteria te bouwen, kunt u meer kenmerken toevoegen of wiskundige operatoren gebruiken voor uw functie voor meetcriteria.

1. Om filters toe te voegen, selecteert u het **Filter** in het configuratiegebied. Als u filters toepast, worden alleen de records gebruikt die overeenkomen met de filters om de meting te berekenen.
  
   1. Selecteer in de sectie **Kenmerk toevoegen** van het deelvensteer **Filters** het kenmerk dat u wilt gebruiken om filters te maken.
   1. Stel de filteroperatoren in om het filter voor elk geselecteerd kenmerk te definiëren.
   1. Selecteer **Toepassen** om de filters aan het meetcriterium toe te voegen.

1. Selecteer **Dimensie** om meer velden te kiezen die als kolommen worden toegevoegd aan de metinguitvoerentiteit.
 
   1. Selecteer **Dimensies bewerken** om gegevenskenmerken toe te voegen waarop u de meetwaarden wilt groeperen. Bijvoorbeeld plaats of gender. Standaard is de dimensie *CustomerID* geselecteerd om *meetcriteria op klantniveau* te maken. U kunt de standaarddimensie verwijderen als u *meetcriteria op bedrijfsniveau*​wilt maken.
   1. Selecteer **Gereed** om de dimensies aan het meetcriterium toe te voegen.

1. Als er waarden in uw gegevens zijn die u moet vervangen door een geheel getal, selecteert u **Regels**. Configureer de regel en zorg ervoor dat u alleen hele getallen kiest als vervanging. Vervang bijvoorbeeld *null* door *0*.

1. Als er meerdere paden zijn tussen de gegevensentiteit die u hebt toegewezen en de entiteit *Klant*, moet u een van de geïdentificeerde [entiteitsrelatiepaden​](relationships.md) kiezen. Meetresultaten kunnen variëren, afhankelijk van het geselecteerde pad. 
   
   1. Selecteer **Relatiepad** en kies het entiteitspad dat moet worden gebruikt om uw meting te identificeren. Als er maar één pad is naar de entiteit *Klant*, wordt dit besturingselement niet weergegeven.
   1. Selecteer **Gereed** om uw selectie toe te passen. 

1. Als u meer berekeningen voor het meetcriterium wilt toevoegen, selecteert u **Nieuwe berekening**​. U kunt alleen entiteiten op hetzelfde entiteitspad gebruiken voor nieuwe berekeningen. Meer berekeningen worden weergegeven als nieuwe kolommen in de entiteit voor uitvoer van meetcriteria.

1. Selecteer **...** in de berekening om een berekening uit een meetcriterium te **Dupliceren** **Naam wijzigen** of te **Verwijderen**.

1. In het gebied **Voorbeeld** ziet u het gegevensschema van de entiteit voor uitvoer van meetcriteria, inclusief filters en dimensies. Het voorbeeld reageert dynamisch op wijzigingen in de configuratie.

1. Selecteer **Uitvoeren** om resultaten voor het geconfigureerde meetcriterium te berekenen. Selecteer **Opslaan en sluiten** als u de huidige configuratie wilt behouden en het meetcriterium later wilt uitvoeren.

1. Ga naar **Meetcriteria** om het nieuw gemaakte meetcriterium in de lijst te zien.

# <a name="business-accounts-b-to-b"></a>[Zakelijke accounts (B-to-B)](#tab/b2b)


U kunt metingen maken op het niveau van individuele accounts (klantmeting) of op het niveau van alle accounts (bedrijfsmeting). 

- Klantmeting: genereert uitvoer als zelfstandige entiteit. Klantmetingen worden niet weergegeven in de klantprofielkaart.

- Bedrijfsmeting: genereert uitvoer als een zelfstandige entiteit en wordt weergegeven op de startpagina van uw Customer Insights-omgeving.

1. Ga naar **Metingen**.

1. Selecteer **Nieuw**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Leeg configuratiescherm voor een B-naar-B-meting. ":::

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

1. Selecteer **Kenmerk toevoegen** om de gegevens te selecteren die u nodig hebt om dit meetcriterium te maken.
   
   1. Selecteer het tabblad **Kenmerken**. 
   1. Gegevensentiteit: kies de entiteit die het kenmerk bevat dat u wilt meten. 
   1. Gegevenskenmerk: kies het kenmerk dat u in de aggregatiefunctie wilt gebruiken om het meetcriterium te berekenen. U kunt slechts één kenmerk tegelijk selecteren.
   1. U kunt ook een gegevenskenmerk van een bestaand meetcriterium selecteren door het tabblad **Meetcriteria** te selecteren, of u kunt zoeken naar de naam van een entiteit of meetcriterium. 
   1. Selecteer **Toevoegen** om het geselecteerde kenmerk aan het meetcriterium toe te voegen.

1. Om complexere meetcriteria te bouwen, kunt u meer kenmerken toevoegen of wiskundige operatoren gebruiken voor uw functie voor meetcriteria.

1. Om filters toe te voegen, selecteert u het **Filter** in het configuratiegebied. Als u filters toepast, worden alleen de records gebruikt die overeenkomen met de filters om de meting te berekenen.
  
   1. Selecteer in de sectie **Kenmerk toevoegen** van het deelvensteer **Filters** het kenmerk dat u wilt gebruiken om filters te maken.
   1. Stel de filteroperatoren in om het filter voor elk geselecteerd kenmerk te definiëren.
   1. Selecteer **Toepassen** om de filters aan het meetcriterium toe te voegen.

1. Selecteer **Dimensie** om meer velden te kiezen die als kolommen worden toegevoegd aan de metinguitvoerentiteit.
 
   1. Selecteer **Dimensies bewerken** om gegevenskenmerken toe te voegen waarop u de meetwaarden wilt groeperen. Bijvoorbeeld plaats of gender. Standaard is de dimensie *CustomerID* geselecteerd om *meetcriteria op klantniveau* te maken. U kunt de standaarddimensie verwijderen als u *meetcriteria op bedrijfsniveau*​wilt maken.
   1. Selecteer **Gereed** om de dimensies aan het meetcriterium toe te voegen.

1. Als er waarden in uw gegevens zijn die u moet vervangen door een geheel getal, selecteert u **Regels**. Configureer de regel en zorg ervoor dat u alleen hele getallen kiest als vervanging. Vervang bijvoorbeeld *null* door *0*.

1. U kunt de schakeloptie **Subaccounts totaliseren** gebruiken als u [accounts gebruikt met hiërarchieën](relationships.md#set-up-account-hierarchies).
   - Als deze is ingesteld op **Uit** wordt de meting voor elke account berekend. Elke account krijgt een eigen resultaat.
   - Als deze is ingesteld op **Aan**, selecteert u **Bewerken** om de accounthiërarchie te kiezen op basis van de opgenomen hiërarchieën. De meting levert slechts één resultaat op omdat deze wordt geaggregeerd met subaccounts.

1. Als er meerdere paden zijn tussen de gegevensentiteit die u hebt toegewezen en de entiteit *Klant*, moet u een van de geïdentificeerde [entiteitsrelatiepaden​](relationships.md) kiezen. Meetresultaten kunnen variëren, afhankelijk van het geselecteerde pad. 
   
   1. Selecteer **Relatiepad** en kies het entiteitspad dat moet worden gebruikt om uw meting te identificeren. Als er maar één pad is naar de entiteit *Klant*, wordt dit besturingselement niet weergegeven.
   1. Selecteer **Gereed** om uw selectie toe te passen. 

1. Selecteer **...** in de berekening om een berekening uit een meetcriterium te **Dupliceren** **Naam wijzigen** of te **Verwijderen**.

1. In het gebied **Voorbeeld** ziet u het gegevensschema van de entiteit voor uitvoer van meetcriteria, inclusief filters en dimensies. Het voorbeeld reageert dynamisch op wijzigingen in de configuratie.

1. Selecteer **Uitvoeren** om resultaten voor het geconfigureerde meetcriterium te berekenen. Selecteer **Opslaan en sluiten** als u de huidige configuratie wilt behouden en het meetcriterium later wilt uitvoeren.

1. Ga naar **Meetcriteria** om het nieuw gemaakte meetcriterium in de lijst te zien.

---