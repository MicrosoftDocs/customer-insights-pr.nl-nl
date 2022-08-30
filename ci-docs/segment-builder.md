---
title: Complexe segmenten maken met de opbouwfunctie voor segmenten
description: Gebruik de opbouwfunctie voor segmenten om complexe segmenten te maken van klanten door ze te groeperen op basis van verschillende kenmerken.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 7f691fd0b2ea76a2960d5adf766a4b166f02ebb4
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304743"
---
# <a name="create-complex-segments-with-segment-builder"></a>Complexe segmenten maken met de opbouwfunctie voor segmenten

Definieer complexe filters rond de geharmoniseerde klant of geharmoniseerde contactpersoon en de bijhorende gerelateerde entiteiten. Elk segment maakt na verwerking een reeks klant- of contactpersoonrecords die u kunt exporteren en waarop u actie kunt ondernemen.

> [!TIP]
> Segmenten op basis van **individuele klanten** nemen automatisch beschikbare contactgegevens voor segmentleden op. In **zakelijke account** kiest u, als u zowel accounts als contactpersonen hebt [geharmoniseerd](data-unification.md), of het segment is gebaseerd op accounts of zakelijke contactpersonen. Gebruik een segment met contactpersonen om te exporteren naar een bestemming die contactpersoongegevens verwacht. Gebruik een segment met accounts om te exporteren naar een bestemming die accountgegevens verwacht.

## <a name="segment-builder"></a>Opbouwfunctie voor segmenten

In de volgende afbeelding worden de verschillende aspecten van de opbouwfunctie voor segmenten geïllustreerd. Er wordt een segment weergegeven dat resulteert in een groep klanten. De klanten hebben goederen besteld in een specifieke tijdsbestek en ze hebben beloningspunten verzameld of een bepaald bedrag uitgegeven.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elementen van de segmentbouwer." lightbox="media/segment-builder-overview.png":::

1. Organiseer uw segment met regels en subregels. Elke regel of subregel bestaat uit voorwaarden. Combineer de voorwaarden met logische operators.

1. Kies het [relatiepad](relationships.md) tussen entiteiten die van toepassing zijn op een regel. Het relatiepad bepaalt welke kenmerken in een voorwaarde kunnen worden gebruikt.

1. Beheer regels en subregels. Wijzig de positie van een regel of verwijder deze.

1. Voeg voorwaarden toe en bouw het juiste niveau van nesting met behulp van subregels.

1. Pas setbewerkingen toe op verbonden regels.

1. Gebruik het kenmerkdeelvenster om beschikbare entiteitskenmerken toe te voegen of om voorwaarden te creëren op basis van kenmerken. Het deelvenster toont de lijst met entiteiten en kenmerken, gebaseerd op het geselecteerde relatiepad, die beschikbaar zijn voor de geselecteerde regel.

1. Voeg voorwaarden toe aan bestaande regels en subregels op basis van kenmerken of voeg deze toe aan een nieuwe regel.

1. Maak wijzigingen ongedaan en voer ze opnieuw uit tijdens het bouwen van het segment.

Het bovenstaande voorbeeld illustreert de segmentatiemogelijkheid. We hebben een segment gedefinieerd voor klanten die ten minste voor $ 500 aan goederen online hebben gekocht *en* interesse hebben in softwareontwikkeling.

## <a name="create-a-new-segment-with-segment-builder"></a>Een nieuw segment maken met behulp van de opbouwfunctie voor segmenten

1. Ga naar **Segmenten**.

1. Selecteer **Nieuw** > **Bouw uw eigen segment**. Op de pagina voor het samenstellen van segmenten definieert of stelt u regels op. Een regel bestaat uit een of meer voorwaarden die een set klanten definiëren.

   > [!NOTE]
   > Voor omgevingen op basis van zakelijke accounts selecteert u **Nieuw** > **Segment van accounts** of **Segment van contactpersonen (preview)** op basis van het type segment dat u wilt maken. Als een [accounthiërarchie](relationships.md#set-up-account-hierarchies) is gedefinieerd en u regels wilt maken om gegevens uit te filteren op basis van de onderliggende en bovenliggende relatie, selecteert u **Hiërarchie gebruiken? (preview)**, selecteert u de hiërarchie en selecteert u vervolgens **Toepassen**.
   >
   > :::image type="content" source="media/segment_acct_hierarchy.png" alt-text="Deelvenster Segment accounthiërarchie selecteren.":::

1. Selecteer **Details bewerken** naast het segment Naamloos. Geef een naam op voor uw segment en werk de voorgestelde **Naam van uitvoerentiteit** voor het segment bij. Voeg optioneel een beschrijving en [tags](work-with-tags-columns.md#manage-tags) toe aan het segment.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Dialoogvenster Details bewerken.":::

1. Kies in de sectie **Rule1** een kenmerk van een entiteit waarop u klanten wilt filteren. U kunt op twee manieren kenmerken kiezen:
   - Bekijk de lijst met beschikbare entiteiten en kenmerken in het deelvenster **Toevoegen aan regel** en selecteer het pictogram **+** naast het kenmerk dat u wilt toevoegen. Kies of u het kenmerk aan een bestaande regel wilt toevoegen of het wilt gebruiken om een nieuwe regel te maken.
   - Typ de naam van het kenmerk in het regelgedeelte om overeenkomende suggesties weer te geven.

1. Kies de operators om de overeenkomende waarden van de voorwaarde op te geven. Kenmerk kan een van de vier gegevenstypen als waarde hebben: numeriek, tekenreeks, datum of booleaans. Afhankelijk van het gegevenstype van het attribuut zijn er verschillende operators beschikbaar om de voorwaarde op te geven.

1. Selecteer **Voorwaarde toevoegen** om meer voorwaarden aan een regel toe te voegen. Als u een regel onder de huidige regel wilt maken, selecteert u **Subregel toevoegen**.

1. Als een regel andere entiteiten gebruikt dan de entiteit *Klant* (of de entiteit *ContactProfile* voor B2B), selecteert u **Relatiepad instellen** om de geselecteerde entiteit toe te wijzen aan de geharmoniseerde klantentiteit. Als er maar één mogelijk relatiepad is, selecteert het systeem automatisch dit pad. Verschillende [relatiepaden](relationships.md#relationship-paths) kunnen verschillende resultaten opleveren. Elke regel kan zijn eigen relatiepad hebben.

   :::image type="content" source="media/relationship-path.png" alt-text="Potentieel relatiepad bij het maken van een regel op basis van een entiteit die is toegewezen aan de geharmoniseerde klantentiteit.":::

1. Als u meerdere voorwaarden in een regel hebt opgenomen, kiest u welke logische operator ze verbindt.  
   - **EN**-operator: er moet aan alle voorwaarden worden voldaan om een record in het segment op te nemen. Gebruik deze optie wanneer u voorwaarden definieert voor verschillende entiteiten.
   - **OF**-operator: er moet aan een van de voorwaarden worden voldaan om een record in het segment op te nemen. Gebruik deze optie wanneer u meerdere voorwaarden definieert voor dezelfde entiteit.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Regel met twee EN-voorwaarden.":::

   Bij gebruik van de OF-operator moeten alle voorwaarden zijn gebaseerd op entiteiten die in het relatiepad zijn opgenomen.

1. U kunt meerdere regels maken om verschillende sets klantrecords te maken. Combineer groepen om de klanten op te nemen die nodig zijn voor uw bedrijfsscenario. Als u een entiteit niet in een regel kunt opnemen vanwege het opgegeven relatiepad, maakt u speciaal een nieuwe regel maken om er kenmerken uit te kiezen.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Voeg een nieuwe regel toe aan een segment en kies de set-operator.":::

   1. Selecteer **Regel toevoegen**.
   1. Selecteer een van de set-operators: **Samenvoegen**, **Doorsnede** of **Uitsluiten**.

      - **Verbinding** verbindt de twee groepen.
      - **Overlappen** overlapt de twee groepen. Alleen gegevens die *voorkomen* in beide groepen blijven in de verenigde groep.
      - **Behalve** combineert de twee groepen. Alleen gegevens in groep A die *niet voorkomen* in groep B worden bewaard.

1. De uitvoerentiteit bevat standaard automatisch alle kenmerken van klantprofielen die overeenkomen met de gedefinieerde filters. In B2B wordt, bij gebruik van de entiteit *ContactProfile*, de account-id automatisch opgenomen. Als een segment is gebaseerd op andere entiteiten dan de entiteit *Klant* of om kenmerken van *ContactProfile*, selecteert u **Projectkenmerken** om meer kenmerken van deze entiteiten toe te voegen aan de uitvoerentiteit.
 
   Bijvoorbeeld: een segment is gebaseerd op een entiteit die inkoopgegevens bevat die verband houden met de entiteit *Klant*. Het segment zoekt naar alle klanten uit Spanje die in het lopende jaar goederen hebben gekocht. U kunt ervoor kiezen om kenmerken zoals de prijs van de goederen of de aankoopdatum toe te voegen aan alle overeenkomende klantrecords in de uitvoerentiteit. Deze informatie kan nuttig zijn om seizoenscorrelaties en de totale uitgaven te analyseren.

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Voorbeeld van geprojecteerde kenmerken die in het zijvenster zijn geselecteerd om aan de entiteit voor uitvoer toe te voegen.":::
 
   Een voorbeelduitvoer voor een segment op basis van zakelijke accounts met geprojecteerde kenmerken van contactpersonen kan er als volgt uitzien:

   |Id  |Accountnaam  |Omzet  |Naam van contactpersoon  | Rol van contactpersoon|
   |---------|---------|---------|---------|---|
   |10021     | Contoso | 100 K | [Abbie Moss, Ruth Soto]  | [CEO, inkoopmanager]

   > [!NOTE]
   > - **Projectkenmerken** werkt alleen voor entiteiten die een een-op-veel-relatie hebben met de entiteit *Klant* of *ContactProfile*. Eén klant kan bijvoorbeeld meerdere abonnementen hebben.
   > - Als het kenmerk dat u wilt projecteren meer dan één stap verwijderd is van de entiteit *Klantr* of *ContactProfile*, zoals gedefinieerd door de relatie, moet dat kenmerk worden gebruikt in elke regel van de segmentquery die u maakt.
   > - Als het kenmerk dat u wilt projecteren slechts één stap verwijderd is van de entiteit *Klant* of *ContactProfile*, hoeft dat kenmerk niet aanwezig te zijn in elke regel van de segmentquery die u maakt.
   > - Bij het gebruik van set-operators wordt rekening gehouden met **geprojecteerde kenmerken**.

1. Selecteer **Uitvoeren** om het segment te maken. Selecteer **Opslaan** als u de huidige configuratie wilt behouden en het segment later wilt uitvoeren. De pagina **Segmenten** wordt weergegeven.

### <a name="segment-builder-tips"></a>Tips voor de opbouwfunctie voor segmenten

Houd bij het maken van een segment met de opbouwfunctie voor segmenten rekening met de volgende tips:

- De opbouwfunctie voor segmenten stelt geen geldige waarden van entiteiten voor bij het instellen van de operators voor de voorwaarden. U kunt naar **Gegevens** > **Entiteiten** gaan en de entiteitsgegevens downloaden om te zien welke waarden er beschikbaar zijn.
- Met voorwaarden op basis van datums kunt u schakelen tussen vaste datums en een zwevend datumbereik.
- Als u meerdere regels voor uw segment heeft, heeft de regel die u aan het bewerken bent, een verticale blauwe lijn ernaast.
- U kunt regels en voorwaarden naar andere plaatsen in de segmentdefinitie verplaatsen. Selecteer het verticale weglatingsteken (&vellip;) naast een regel of voorwaarde en kies hoe en waar u deze wilt verplaatsen.
- Met de opties **Ongedaan maken** en **Opnieuw** in de opdrachtbalk kunt u wijzigingen ongedaan maken.
- Nadat u een segment hebt gemaakt, kunt u met sommige segmenten [het gebruik van het segment bijhouden](segments.md#track-usage-of-a-segment).

## <a name="next-steps"></a>Volgende stappen

[Exporteer een segment](export-destinations.md) en verken de [Klantenkaartintegratie](customer-card-add-in.md) om segmenten in andere toepassingen te gebruiken.

[!INCLUDE [footer-include](includes/footer-banner.md)]
