---
title: Overeenkomstvoorwaarden voor gegevensharmonisatie
description: Match entiteiten om geharmoniseerde klantprofielen te maken.
recommendations: false
ms.date: 07/27/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: eaa3409aaa7541dc88953336942e43afaf6511c6
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304651"
---
# <a name="match-conditions-for-data-unification"></a>Overeenkomstvoorwaarden voor gegevensharmonisatie

Deze stap in harmonisatie definieert de afstemmingsvolgorde en regels voor afstemming tussen verschillende entiteiten. Voor deze stap zijn ten minste twee entiteiten vereist.

> [!NOTE]
> Zodra u uw overeenkomstvoorwaarden hebt gemaakt en **Volgende** hebt geselecteerd, kunt u een geselecteerde entiteit of kenmerk niet verwijderen. Selecteer indien nodig **Terug** om de geselecteerde entiteiten en kenmerken te bekijken voordat u verdergaat.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="include-enriched-entities-preview"></a>Verrijkte entiteiten opnemen (preview)

Als u entiteiten op het gegevensbron-niveau hebt verrijkt om uw harmonisatieresultaten te verbeteren, selecteert u ze. Zie [Verrijking voor gegevensbronnen](data-sources-enrichment.md) voor meer informatie. Als u verrijkte entiteiten hebt geselecteerd op de pagina **Dubbele records**, hoeft u ze niet opnieuw te selecteren.

1. Boven aan de pagina **Overeenkomstvoorwaarden** selecteert u **Verrijkte entiteiten gebruiken**.

1. Kies een of meer verrijkte entiteiten in het deelvenster **Verrijkte entiteiten gebruiken**.

1. Selecteer **Gereed**.

## <a name="specify-the-match-order"></a>De afstemmingsvolgorde opgeven

Elke match verenigt twee of meer entiteiten in één geconsolideerde entiteit. Tegelijkertijd worden de unieke klantrecords behouden. De afstemmingsvolgorde geeft de volgorde aan waarin het systeem probeert de records af te stemmen.

> [!IMPORTANT]
> De eerste entiteit wordt de primaire entiteit genoemd. Deze dient als basis voor uw geharmoniseerde profielen. Extra entiteiten die zijn geselecteerd, worden aan deze entiteit toegevoegd.
>
> Belangrijke aandachtspunten:
>
> - Kies de entiteit met de meest volledige en betrouwbare profielgegevens over uw klanten als de primaire entiteit.
> - Kies de entiteit die verschillende kenmerken heeft die worden gedeeld door andere entiteiten (bijvoorbeeld naam, telefoonnummer of e-mailadres) als de primaire entiteit.

1. Gebruik op de pagina **Overeenkomstvoorwaarden** de pijlen omhoog en omlaag of slepen en neerzetten om de entiteiten in de gewenste volgorde te plaatsen. Selecteer bijvoorbeeld **eCommerceCustomers** als de primaire entiteit en **loyCustomers** als de tweede entiteit.

1. Als u elke record in de entiteit als unieke klant wilt, ongeacht of een overeenkomst is gevonden, selecteert u **Alle records opnemen**. Alle records in deze entiteit die niet overeenkomen met records in andere entiteiten, worden opgenomen in het geharmoniseerde profiel. Records zonder overeenkomst hebben, worden singletons genoemd.
  
De primaire entiteit *Contacts:eCommerce* wordt afgestemd met de volgende entiteit *CustomerLoyalty:Loyalty*. De gegevensset die voortvloeit uit de eerste afstemmingsstap wordt gekoppeld met de volgende entiteit als u meer dan twee entiteiten hebt.

:::image type="content" source="media/m3_match.png" alt-text="Schermopname van de geselecteerde afstemmingsvolgorde voor de entiteiten." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Regels voor vergelijkingsparen definiëren

Afstemmingsregels specificeren de logica waarmee een specifiek paar entiteiten zal worden afgestemd. Een regel bestaat uit een of meer voorwaarden.

De waarschuwing naast de naam van een entiteit betekent dat er geen overeenkomstregel is gedefinieerd voor een vergelijkingspaar.

1. Selecteer **Regel toevoegen** voor een entiteitenpaar om overeenkomstregels te definiëren.

1. In het deelvenster **Regel toevoegen** configureert u de voorwaarden voor de regel.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Schermopname van het deelvenster Regel toevoegen.":::

   - **Entiteit/veld (eerste rij) selecteren**: kies een entiteit en een kenmerk op te geven die waarschijnlijk uniek zijn voor een klant. Dit kan bijvoorbeeld een telefoonnummer of e-mailadres zijn. Maak geen vergelijkingen op basis van kenmerken van het activiteitstype. Voor een aankoop-id wordt bijvoorbeeld waarschijnlijk geen overeenkomst gevonden in andere recordtypen.

   - **Entiteit/veld (tweede rij) selecteren**: kies een kenmerk dat betrekking heeft op het kenmerk van de entiteit die in de eerste rij is opgegeven.

   - **Normaliseren**: kies uit de volgende normalisatieopties voor de geselecteerde kenmerken.
     - **Cijfers**: converteert andere cijfersystemen, zoals Romeinse cijfers, naar Arabische cijfers. *VIII* wordt *8*.
     - **Symbolen**: verwijdert alle symbolen en speciale tekens. *Hoofd&schouder* wordt *Hoofdschouder*​.
     - **Tekst in kleine letters**: alle tekens worden omgezet naar kleine letters. *HOOFDLETTERS en Beginhoofdletters* wordt *hoofdletters en beginhoofdletters*​.
     - **Type (Telefoon, Naam, Adres, Organisatie)**: standaardiseert namen, titels, telefoonnummers, adressen en organisaties.
     - **Van Unicode naar ASCII**: converteert de Unicode-notatie naar ASCII-tekens. */u00B2* wordt *2*.
     - **Spatie**: verwijdert alle spaties. *Hallo   wereld* wordt *Hallowereld*.

   - **Precisie**: stel het precisieniveau in dat voor deze voorwaarde moet worden toegepast.
     - **Basis**: kies uit *Laag (30%)*, *Gemiddeld (60%)*, *Hoog (80%)* en *Exact (100%)*. Selecteer **Exact** om alleen records af te stemmen die voor 100 procent overeenkomen.
     - **Aangepast**: stel een percentage in waaraan records moeten voldoen. Alleen records die deze drempel halen, worden vergeleken.

   - **Naam**: naam voor de regel.

1. Als u alleen entiteiten wilt afstemmen als kenmerken aan meerdere voorwaarden voldoen, selecteert u **Toevoegen** > **Voorwaarde toevoegen** om meer voorwaarden aan een overeenkomstregel toe te voegen. Voorwaarden zijn verbonden met een logische EN-operator en worden dus alleen uitgevoerd als aan alle voorwaarden is voldaan.

1. Overweeg desgewenst geavanceerde opties zoals [uitzonderingen](#add-exceptions-to-a-rule) of [aangepaste overeenkomstvoorwaarden](#specify-custom-match-conditions).

1. Selecteer **Gereed** om de regel te voltooien.

1. U kunt ook [meer regels toevoegen](#add-rules-to-a-match-pair)​.

1. Klik op **Volgende**.

> [!div class="nextstepaction"]
> [Volgende stap: Velden harmoniseren](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Regels toevoegen aan een vergelijkingspaar

Overeenkomstregels staan voor voorwaardensets. Voeg meer regels toe om entiteiten af te stemmen op voorwaarden op basis van meerdere kenmerken.

1. Selecteer **Regel toevoegen** in de entiteit waaraan u regels wilt toevoegen.

1. Volg de stappen in [Regels voor vergelijkingsparen definiëren](#define-rules-for-match-pairs)​.

> [!NOTE]
> De volgorde van regels is belangrijk. Het vergelijkingsalgoritme probeert een bepaalde klantenrecord te vergelijken op basis van uw eerste regel en gaat alleen door naar de tweede regel als er geen overeenkomsten met de eerste regel zijn geïdentificeerd.

## <a name="advanced-options"></a>Geavanceerde opties

### <a name="add-exceptions-to-a-rule"></a>Uitzonderingen toevoegen aan een regel

In de meeste gevallen leidt het matchen van entiteiten tot unieke klantprofielen met samengevoegde gegevens. Definieer uitzonderingen voor een overeenkomstregel om zeldzame gevallen van fout-positieven en fout-negatieven aan te pakken. Uitzonderingen worden toegepast na verwerking van de overeenkomstregels en voorkomen dat alle records die aan de uitzonderingscriteria voldoen, worden gematcht.

Als uw overeenkomstregel bijvoorbeeld achternaam, stad en geboortedatum combineert, zou het systeem een tweeling met dezelfde achternaam die in dezelfde stad woont als hetzelfde profiel identificeren. U kunt een uitzondering specificeren die de profielen niet matcht als de voornaam in de entiteiten die u combineert niet gelijk zijn.

1. Selecteer **Toevoegen** > **Uitzondering toevoegen** in het deelvenster **Regel bewerken**.

1. Geef de uitzonderingscriteria op.

1. Selecteer **Gereed** om de regel op te slaan.

### <a name="specify-custom-match-conditions"></a>Aangepaste overeenkomstvoorwaarden opgeven

U kunt voorwaarden opgeven die de standaardovereenkomstlogica overschrijven. Er zijn vier opties beschikbaar:

|Optie  |Description |Voorbeeld  |
|---------|---------|---------|
|Altijd overeenkomen     | Definieert waarden die altijd overeenkomen.         |  *Mike* en *MikeR* komen altijd overeen.       |
|Nooit overeenkomen     | Definieert waarden die nooit overeenkomen.        | *John* en *Jonathan* komen nooit overeen.        |
|Omleiding            | Definieert waarden die het systeem altijd moet negeren in de overeenkomstfase. |  Negeer de waarden *11111* en *Onbekend* tijdens de overeenkomstfase.        |
|Aliastoewijzing    | Waarden definiëren die het systeem als dezelfde waarde moet beschouwen.         | Overweeg of *Joe* gelijk is aan *Joseph*.        |

1. Selecteer **Aangepast**.

   :::image type="content" source="media/m3_match_custom.png" alt-text="Aangepaste knop":::

1. Kies **Aangepast type** en selecteer **Sjabloon downloaden**. Voor elke overeenkomstoptie hebt u een aparte sjabloon nodig.

1. Open het gedownloade sjabloonbestand en vul de details in. De sjabloon bevat velden om de entiteit en de primaire sleutelwaarden van de entiteit op te geven die in de aangepaste overeenkomst moeten worden gebruikt. Als u bijvoorbeeld wilt dat de primaire sleutel *12345* uit de entiteit *Verkoop* altijd wordt afgestemd met de primaire sleutel *34567* van de entiteit *Contactpersoon*, vult u de sjabloon in:
    - Entiteit1: Verkoop
    - Entity1Key: 12345
    - Entiteit2: Contactpersoon
    - Entity2Key: 34567

   Hetzelfde sjabloonbestand kan aangepaste afstemmingsrecords van meerdere entiteiten specificeren.

   Als u aangepaste overeenkomsten voor ontdubbeling op een entiteit wilt opgeven, geeft u dezelfde entiteit op als Entity1 en Entity2 en stelt u de verschillende primaire sleutelwaarden in.

1. Sla het sjabloonbestand op nadat u alle overschrijvingen hebt toegevoegd.

1. Ga naar **Gegevens** > **Gegevensbronnen** en neem de sjabloonbestanden op als nieuwe entiteiten.

1. Selecteer na het uploaden van de bestanden opnieuw de optie **Aangepast**. Selecteer de vereiste entiteiten in het vervolgkeuzemenu en selecteer **Gereed**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Schermopname van het dialoogvenster om overschrijvingen te kiezen voor een aangepast afstemmingsscenario.":::

1. Het toepassen van de aangepaste overeenkomst hangt af van de overeenkomstoptie die u wilt gebruiken.

   - Ga verder met de volgende stap voor **Altijd overeenkomen** of **Nooit overeenkomen**.
   - Selecteer voor **Omleiding** of **Aliastoewijzing** de optie **Bewerken** op een bestaande overeenkomstregel of maak een nieuwe regel. Kies in de vervolgkeuzelijst Normalisaties de optie **Aangepaste omleiding** of **Aliastoewijzing** en selecteer **Gereed**.

1. Selecteer **Gereed** in het deelvenster **Aangepast** om de aangepaste overeenkomstconfiguratie toe te passen.

> [!div class="nextstepaction"]
> [Volgende stap: Velden harmoniseren](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
