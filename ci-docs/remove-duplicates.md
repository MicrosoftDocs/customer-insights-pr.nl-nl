---
title: Duplicaten verwijderen voordat u gegevens harmoniseert
description: De tweede stap in het harmonisatieproces is het selecteren van de record die moet worden bewaard als er duplicaten worden gevonden.
recommendations: false
ms.date: 08/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: 3f84c1c149f0befcbe489ccdd8a666ce6d5d798a
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304467"
---
# <a name="remove-duplicates-before-unifying-data"></a>Duplicaten verwijderen voordat u gegevens harmoniseert

Met deze optionele stap bij de harmonisatie kunt u regels instellen voor het afhandelen van dubbele records **binnen** een entiteit. Bij deduplicatie worden meerdere records voor een klant geïdentificeerd en de beste record om te bewaren geselecteerd (op basis van basisvoorkeuren voor samenvoegen) of de records samengevoegd tot één record (op basis van geavanceerde samenvoegvoorkeuren). Bronrecords worden met alternatieve id's aan de samengevoegde record gekoppeld. Als er geen regels zijn geconfigureerd, worden door het systeem gedefinieerde regels toegepast.

## <a name="default-deduplication"></a>Standaarddeduplicatie

De door het systeem gedefinieerde regels zijn van toepassing als geen deduplicatieregels worden toegevoegd.

- De primaire sleutel wordt gededupliceerd.
  Van alle records met dezelfde primaire sleutel, heeft de record **Meest gevuld** (de record met de minste nulwaarden) prioriteit.
- Eventuele afstemmingsregels tussen entiteiten worden toegepast op de entiteit.
  In de afstemmingsstap geldt bijvoorbeeld dat, als entiteit A wordt vergeleken met entiteit B op *FullName* en *DateofBirth*, entiteit A ook wordt gededupliceerd door *FullName* en *DateofBirth*. Omdat *FullName* en *DateofBirth* geldige sleutels zijn voor het identificeren van een klant in entiteit A, zijn deze sleutels ook geldig voor het identificeren van dubbele klanten in entiteit A.

## <a name="include-enriched-entities-preview"></a>Verrijkte entiteiten opnemen (preview)

Als u entiteiten op het gegevensbron-niveau hebt verrijkt om uw harmonisatieresultaten te verbeteren, selecteert u ze. Zie [Verrijking voor gegevensbronnen](data-sources-enrichment.md) voor meer informatie.

1. Boven aan de pagina **Dubbele records** selecteert u **Verrijkte entiteiten gebruiken**.

1. Kies een of meer verrijkte entiteiten in het deelvenster **Verrijkte entiteiten gebruiken**.

1. Selecteer **Gereed**.

## <a name="define-deduplication-rules"></a>Ontdubbelingsregels definiëren

1. Selecteer op de pagina **Dubbele records** een entiteit en selecteer **Regel toevoegen** om de ontdubbelingsregels te definiëren.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Schermopname van de pagina Dubbele records met de entiteit gemarkeerd en Regel toevoegen weergegeven"  lightbox="media/m3_duplicates_showmore.png":::

   1. Vul in het deelvenster **Regel toevoegen** de volgende gegevens in:
      - **Veld selecteren**: maak uw keuze in de lijst met beschikbare velden van de entiteit die u op duplicaten wilt controleren. Kies velden die waarschijnlijk uniek zijn voor elke afzonderlijke klant, bijvoorbeeld een e-mailadres of de combinatie van naam, plaats en telefoonnummer.
      - **Normaliseren**: kies uit de volgende normalisatieopties voor de geselecteerde kenmerken.
        - **Cijfers**: converteert andere cijfersystemen, zoals Romeinse cijfers, naar Arabische cijfers. *VIII* wordt *8*.
        - **Symbolen**: verwijdert alle symbolen en speciale tekens. *Hoofd&schouder* wordt *Hoofdschouder*​.
        - **Tekst in kleine letters: alle tekens worden omgezet in kleine letters**. *HOOFDLETTERS en Beginhoofdletters* wordt *hoofdletters en beginhoofdletters*​.
        - **Type (Telefoon, Naam, Adres, Organisatie)**: standaardiseert namen, titels, telefoonnummers, adressen enz.
        - **Van Unicode naar ASCII**: converteert de Unicode-notatie naar ASCII-tekens. */u00B2* wordt *2*.
        - **Spatie**: verwijdert alle spaties. *Hallo   wereld* wordt *Hallowereld*.
      - **Precisie**: stel het precisieniveau in dat voor deze voorwaarde moet worden toegepast.
        - **Basis**: kies uit *Laag (30%)*, *Gemiddeld (60%)*, *Hoog (80%)* en *Exact (100%)*. Selecteer **Exact** om alleen records af te stemmen die voor 100 procent overeenkomen.
        - **Aangepast**: stel een percentage in waaraan records moeten voldoen. Alleen records die deze drempel halen, worden vergeleken.
      - **Naam**: naam voor de regel.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Schermopname van het deelvenster Regel toevoegen voor het verwijderen van duplicaten.":::

   1. Selecteer desgewenst **Toevoegen** > **Voorwaarde toevoegen** om meer voorwaarden aan de regel toe te voegen. Voorwaarden zijn verbonden met een logische EN-operator en worden dus alleen uitgevoerd als aan alle voorwaarden is voldaan.

   1. Kies desgewenst **Toevoegen** > **Uitzondering toevoegen** om [uitzonderingen aan de regel toe te voegen](match-entities.md#add-exceptions-to-a-rule). Uitzonderingen worden gebruikt om zeldzame gevallen van valse positieven en valse negatieven aan te pakken.

   1. Selecteer **Gereed** om de regel te maken.

1. U kunt ook [meer regels toevoegen](#define-deduplication-rules)​.

1. Selecteer een entiteit en vervolgens **Voorkeuren voor samenvoegen bewerken**.

1. In het deelvenster **Voorkeuren voor samenvoegen**:
   1. Kies een van de drie opties om te bepalen welke record moet worden bewaard als er een duplicaat wordt gevonden:
      - **Meest gevuld**: identificeert de record met de meeste gevulde kenmerkvelden als de winnende record. Dit is de standaard samenvoegingsoptie.
      - **Meest recent**: identificeert het winnende record op basis van recentheid. Vereist een datum of een numeriek veld om de recentheid te definiëren.
      - **Minst recent**: identificeert het winnende record op basis van minst recent zijn. Vereist een datum of een numeriek veld om de recentheid te definiëren.

      In het geval van een gelijke stand is de winnende record degene met de MAX(PK) of de grotere primaire-sleutelwaarde.

   1. Selecteer desgewenst, om samenvoegvoorkeuren te definiëren voor individuele kenmerken van een entiteit, **Geavanceerd** onder aan het deelvenster. U kunt er bijvoorbeeld voor kiezen om de meest recente e-mail EN het meest volledige adres uit verschillende records te bewaren. Vouw de entiteit uit om alle kenmerken te bekijken en definieer welke optie moet worden gebruikt voor afzonderlijke kenmerken. Als u een op recentheid gebaseerde optie kiest, moet u ook een datum-/tijdveld opgeven dat de recentheid definieert.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Deelvenster met geavanceerde samenvoegvoorkeuren met recente e-mail en volledig adres":::

   1. Selecteer **Gereed** om uw samenvoegvoorkeuren toe te passen.

1. Na het definiëren van de ontdubbelingsregels en samenvoegvoorkeuren, selecteert u **Volgende**.
  
> [!div class="nextstepaction"]
> [Volgende stap voor een enkele entiteit: Velden harmoniseren](merge-entities.md)

> [!div class="nextstepaction"]
> [Volgende stap voor meerdere entiteiten: Overeenkomende voorwaarden](match-entities.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
