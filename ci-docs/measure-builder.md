---
title: Metingen maken met de opbouwfunctie voor metingen
description: Bouw helemaal vanaf de grond metingen om de belangrijkste gegevens over uw bedrijf te analyseren.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: fac00b8a1b4ca6e09dd29abe46dfe240adcc029e
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170843"
---
# <a name="create-measures-with-measure-builder"></a>Metingen maken met de opbouwfunctie voor metingen

Met de opbouwfunctie voor metingen kunt u berekeningen definiëren met behulp van rekenkundige operatoren, aggregatiefuncties en filters. Definieer metingen met kenmerken van entiteiten die gerelateerd zijn aan de geharmoniseerde entiteit *Klant*.

Het maken van metingen in B-naar-C en B-naar-B omgevingen werkt op dezelfde manier. Als uw B2B-omgeving echter [gebruikmaakt van accounts met hiërarchieën](relationships.md#set-up-account-hierarchies), kunt u ervoor kiezen de meting te aggregeren over gerelateerde subaccounts of niet.

# <a name="individual-consumers-b-to-c"></a>[Individuele consumenten (B-to-C)](#tab/b2c)

Maak metingen op het niveau van individuele klanten (klantkenmerk, klantmeting) of op het niveau van het bedrijf/de organisatie (bedrijfsmeting). Met klantkenmerk en klantmeting kunt u prestaties per klant volgen. Bijvoorbeeld de totale bestedingen per klant. Met bedrijfsmetingen worden prestaties per bedrijf gevolgd. Bijvoorbeeld de totale omzet van het bedrijf.

- Klantkenmerk: genereert uitvoer als een nieuw kenmerk, dat wordt opgeslagen als een nieuwe kolom in de door het systeem gegenereerde entiteit met de naam *Klantmeting*. Bij het vernieuwen van een klantkenmerk worden alle andere klantkenmerken in de entiteit *Klantmeting* gelijktijdig vernieuwd. Daarnaast worden klantkenmerken weergegeven in de klantprofielkaart. Nadat een klantkenmerk is uitgevoerd of opgeslagen, kunt u het niet meer wijzigen in een klantmeting.

- Klantmeting: genereert uitvoer als een zelfstandige entiteit en u kunt deze niet wijzigen in een klantkenmerk nadat het is uitgevoerd of opgeslagen. Klantmetingen worden niet weergegeven in de klantprofielkaart.

- Bedrijfsmeting: genereert uitvoer als een zelfstandige entiteit en wordt weergegeven op de startpagina van uw Customer Insights-omgeving.

1. Ga naar **Metingen**.

1. Selecteer **Nieuw** > **Bouw uw eigen segment**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Leeg configuratiescherm voor een B-naar-C-meting. " lightbox="media/measure-b2c.png":::

1. Selecteer **Details bewerken** naast het meetcriterium Naamloos. Geef een naam op voor het meetcriterium. Voeg optioneel [tags](work-with-tags-columns.md#manage-tags) toe aan het meetcriterium.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialoogvenster Details bewerken.":::

1. Selecteer **Gereed**.

1. U kunt de prestaties op ondernemingsniveau bijhouden door **Type meetcriterium** in te stellen op **Ondernemingsniveau**. **Klantniveau** is standaard geselecteerd. Bij **Klantniveau** wordt automatisch het kenmerk *CustomerId* toegevoegd aan Dimensies, terwijl dit automatisch wordt verwijderd bij **Ondernemingsniveau**.

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

1. Selecteer **Kenmerk toevoegen** om de gegevens te selecteren waarmee deze meting moet worden gemaakt.

   1. Selecteer het tabblad **Kenmerken**.
   1. Gegevensentiteit: kies de entiteit die het kenmerk bevat dat u wilt meten.
   1. Gegevenskenmerk: kies het kenmerk dat u in de aggregatiefunctie wilt gebruiken om het meetcriterium te berekenen. U kunt slechts één kenmerk tegelijk selecteren.
   1. U kunt ook een gegevenskenmerk van een bestaande meting selecteren door het tabblad **Metingen** te selecteren, of u kunt zoeken naar de naam van een entiteit of meting.
   1. Selecteer **Toevoegen**.

1. Als u complexere metingen wilt bouwen, voegt u meer kenmerken toe of gebruikt u wiskundige operatoren voor uw functie voor metingen.

1. Om filters toe te voegen, selecteert u het **Filter** in het configuratiegebied. Als u filters toepast, worden alleen de records gebruikt die overeenkomen met de filters om de meting te berekenen.
  
   1. Selecteer in de sectie **Kenmerk toevoegen** van het deelvensteer **Filters** het kenmerk dat u wilt gebruiken om filters te maken.
   1. Stel de filteroperatoren in om het filter voor elk geselecteerd kenmerk te definiëren.
   1. Selecteer **Toepassen**.

1. Selecteer **Dimensie** om meer velden te kiezen die als kolommen worden toegevoegd aan de metinguitvoerentiteit.

   1. Selecteer **Dimensies bewerken** om gegevenskenmerken toe te voegen waarop u de meetwaarden wilt groeperen. Bijvoorbeeld plaats of gender.
      > [!TIP]
      > Als u **Klantniveau** hebt geselecteerd als waarde bij **Type meetcriterium**, is het kenmerk *CustomerId* al toegevoegd. Als u het kenmerk **Type meetcriterium** verwijdert, wordt overgeschakeld naar **Ondernemingsniveau**.
   1. Selecteer **Gereed**.

1. Als er waarden in uw gegevens zijn moeten worden vervangen door een geheel getal, selecteert u **Regels**. Configureer de regel en zorg ervoor dat u alleen hele getallen kiest als vervanging. Vervang bijvoorbeeld *null* door *0*.

1. Als er meerdere paden zijn tussen de gegevensentiteit die u hebt toegewezen en de entiteit *Klant*, moet u een van de geïdentificeerde [entiteitsrelatiepaden​](relationships.md) kiezen. Meetresultaten kunnen variëren, afhankelijk van het geselecteerde pad.

   1. Selecteer **Relatiepad** en kies het entiteitspad dat moet worden gebruikt om uw meting te identificeren. Als er maar één pad is naar de entiteit *Klant*, wordt dit besturingselement niet weergegeven.
   1. Selecteer **Gereed**.

1. Als u meer berekeningen voor het meetcriterium wilt toevoegen, selecteert u **Nieuwe berekening**​. Gebruik alleen entiteiten op hetzelfde entiteitspad voor nieuwe berekeningen. Meer berekeningen worden weergegeven als nieuwe kolommen in de entiteit voor uitvoer van meetcriteria. Selecteer optioneel **Naam bewerken** om een naam voor de berekening te maken.

1. Selecteer het verticale weglatingsteken (&vellip;) in de berekening voor het **Dupliceren** of **Verwijderen** van een berekening vanuit een meting.

1. In het gebied **Voorbeeld** ziet u het gegevensschema van de entiteit voor uitvoer van meetcriteria, inclusief filters en dimensies. Het voorbeeld reageert dynamisch op wijzigingen in de configuratie.

1. Selecteer **Uitvoeren** om resultaten voor het geconfigureerde meetcriterium te berekenen. Selecteer **Opslaan en sluiten** als u de huidige configuratie wilt behouden en het meetcriterium later wilt uitvoeren. De pagina **Metingen** wordt weergegeven.

# <a name="business-accounts-b-to-b"></a>[Zakelijke accounts (B-to-B)](#tab/b2b)

Maak metingen op het niveau van individuele accounts (klantmeting) of op het niveau van alle accounts (bedrijfsmeting).

- Klantmeting: genereert uitvoer als zelfstandige entiteit. Klantmetingen worden niet weergegeven in de klantprofielkaart.

- Bedrijfsmeting: genereert uitvoer als een zelfstandige entiteit en wordt weergegeven op de startpagina van uw Customer Insights-omgeving.

1. Ga naar **Metingen**.

1. Selecteer **Nieuw**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Leeg configuratiescherm voor een B-naar-B-meting. ":::

1. Selecteer **Details bewerken** naast het meetcriterium Naamloos. Geef een naam op voor het meetcriterium. Voeg optioneel [tags](work-with-tags-columns.md#manage-tags) toe aan het meetcriterium. 
   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialoogvenster Details bewerken.":::

1. Selecteer **Gereed**.

1. Kies in het configuratiegebied de aggregatiefunctie uit het vervolgkeuzemenu **Functie selecteren**. Aggregatiefuncties omvatten:
   - **Sum**
   - **Gemiddeld**
   - **Tellen**
   - **Aantal unieke**
   - **Max.**
   - **Min**
   - **Eerste**: neemt de eerste waarde van de gegevensrecord
   - **Laatste**: neemt de laatste waarde die aan de gegevensrecord is toegevoegd

1. Selecteer **Kenmerk toevoegen** om de gegevens te selecteren waarmee deze meting moet worden gemaakt.

   1. Selecteer het tabblad **Kenmerken**.
   1. Gegevensentiteit: kies de entiteit die het kenmerk bevat dat u wilt meten.
   1. Gegevenskenmerk: kies het kenmerk dat u in de aggregatiefunctie wilt gebruiken om het meetcriterium te berekenen. U kunt slechts één kenmerk tegelijk selecteren.
   1. U kunt ook een gegevenskenmerk van een bestaande meting selecteren door het tabblad **Metingen** te selecteren, of u kunt zoeken naar de naam van een entiteit of meting.
   1. Selecteer **Toevoegen** om het geselecteerde kenmerk aan het meetcriterium toe te voegen.

1. Als u complexere metingen wilt bouwen, voegt u meer kenmerken toe of gebruikt u wiskundige operatoren voor uw functie voor metingen.

1. Om filters toe te voegen, selecteert u het **Filter** in het configuratiegebied. Als u filters toepast, worden alleen de records gebruikt die overeenkomen met de filters om de meting te berekenen.
  
   1. Selecteer in de sectie **Kenmerk toevoegen** van het deelvensteer **Filters** het kenmerk dat u wilt gebruiken om filters te maken.
   1. Stel de filteroperatoren in om het filter voor elk geselecteerd kenmerk te definiëren.
   1. Selecteer **Toepassen** om de filters aan het meetcriterium toe te voegen.

1. Selecteer **Dimensie** om meer velden te kiezen die als kolommen worden toegevoegd aan de metinguitvoerentiteit.

   1. Selecteer **Dimensies bewerken** om gegevenskenmerken toe te voegen waarop u de meetwaarden wilt groeperen. Bijvoorbeeld plaats of gender.
      > [!TIP]
      > Het kenmerk *CustomerId* is al toegevoegd waarmee wordt aangegeven dat dit een metingtype op klantniveau is. Als u het kenmerk verwijdert, wordt overgeschakeld naar bedrijfsniveau.
   1. Selecteer **Gereed** om de dimensies aan het meetcriterium toe te voegen.

1. Als er waarden in uw gegevens zijn moeten worden vervangen door een geheel getal, selecteert u **Regels**. Configureer de regel en zorg ervoor dat u alleen hele getallen kiest als vervanging. Vervang bijvoorbeeld *null* door *0*.

1. Als u [accounts gebruikt met hiërarchieën](relationships.md#set-up-account-hierarchies), bekijk dan **Subaccounts totaliseren**.
   - Als deze is ingesteld op **Uit** wordt de meting voor elke account berekend. Elk account krijgt een eigen resultaat.
   - Als deze is ingesteld op **Aan**, selecteert u **Bewerken** om de accounthiërarchie te kiezen op basis van de opgenomen hiërarchieën. De meting levert slechts één resultaat op omdat deze wordt geaggregeerd met subaccounts.

1. Als er meerdere paden zijn tussen de gegevensentiteit die u hebt toegewezen en de entiteit *Klant*, moet u een van de geïdentificeerde [entiteitsrelatiepaden​](relationships.md) kiezen. Meetresultaten kunnen variëren, afhankelijk van het geselecteerde pad.

   1. Selecteer **Relatiepad** en kies het entiteitspad dat moet worden gebruikt om uw meting te identificeren. Als er maar één pad is naar de entiteit *Klant*, wordt dit besturingselement niet weergegeven.
   1. Selecteer **Gereed** om uw selectie toe te passen.

1. Selecteer het verticale weglatingsteken (&vellip;) in de berekening voor het **Dupliceren** of **Verwijderen** van een berekening vanuit een meting.

1. In het gebied **Voorbeeld** ziet u het gegevensschema van de entiteit voor uitvoer van meetcriteria, inclusief filters en dimensies. Het voorbeeld reageert dynamisch op wijzigingen in de configuratie.

1. Selecteer **Uitvoeren** om resultaten voor het geconfigureerde meetcriterium te berekenen. Selecteer **Opslaan en sluiten** als u de huidige configuratie wilt behouden en het meetcriterium later wilt uitvoeren. De pagina **Metingen** wordt weergegeven.

---

## <a name="next-step"></a>Volgende stap

Gebruik bestaande metingen om [een klantsegment](segments.md) te maken.

[!INCLUDE [footer-include](includes/footer-banner.md)]
