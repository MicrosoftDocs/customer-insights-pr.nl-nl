---
title: De harmonisatie-instellingen bijwerken
description: Werk dubbele regels, overeenkomstregels of geharmoniseerde velden bij in de harmonisatie-instellingen.
ms.date: 06/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 1af7f018abd412c833ff22b3880f0e4508ff4953
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139570"
---
# <a name="update-the-unification-settings"></a>De harmonisatie-instellingen bijwerken

Voer de volgende stappen uit om harmonisatie-instellingen te bekijken of te wijzigen nadat een geharmoniseerd profiel is gemaakt.

1. Ga naar **Gegevens** > **Harmoniseren**.

   :::image type="content" source="media/m3_unified.png" alt-text="Schermopname van de pagina Gegevens harmoniseren nadat de gegevens zijn geharmoniseerd.":::

   > [!TIP]
   > De tegel **Overeenkomende voorwaarden** wordt alleen weergegeven als er meerdere entiteiten zijn geselecteerd.

1. Kies wat u wilt bijwerken:
   - [Bronvelden](#edit-source-fields) om entiteiten of kenmerken toe te voegen of kenmerktypen te wijzigen.
   - [Dubbele records](#manage-deduplication-rules) om ontdubbelingsregels of samenvoegvoorkeuren te beheren.
   - [Overeenkomstvoorwaarden](#manage-match-rules) om overeenkomstregels voor twee of meer entiteiten bij te werken.
   - [Geharmoniseerde klantvelden](#manage-unified-fields) om velden te combineren of uit te sluiten. U kunt gerelateerde profielen ook in clusters groeperen.

1. Nadat u uw wijzigingen hebt aangebracht, kiest u uw volgende optie:

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Schermopname van de pagina Gegevens harmoniseren met de harmonisatie-opties gemarkeerd.":::

   - [Voer overeenkomstvoorwaarden uit](#run-matching-conditions) om de kwaliteit van uw overeenkomstvoorwaarden (regels voor ontdubbeling en overeenkomsten) snel te evalueren zonder het geharmoniseerde profiel bij te werken. De optie **Alleen overeenkomstvoorwaarden uitvoeren** wordt niet weergegeven voor één entiteit.
   - [Klantprofielen harmoniseren](#run-updates-to-the-unified-customer-profile) om overeenkomende voorwaarden uit te voeren en de entiteit unified customer profile bij te werken zonder afhankelijkheden (zoals verrijkingen, segmenten of metingen) te beïnvloeden. Afhankelijke processen worden niet uitgevoerd, maar worden vernieuwd zoals [gedefinieerd in het vernieuwingsschema](system.md#schedule-tab).
   - [Klantprofielen en afhankelijkheden harmoniseren](#run-updates-to-the-unified-customer-profile) om overeenkomende voorwaarden uit te voeren en de entiteit unified customer profile bij te werken en alle afhankelijkheden (zoals verrijkingen, segmenten of metingen) te beïnvloeden. Alle processen worden automatisch opnieuw uitgevoerd.

## <a name="edit-source-fields"></a>Bronvelden bewerken

U kunt een kenmerk of een entiteit niet verwijderen als deze al zijn geharmoniseerd.

1. Selecteer **Bewerken** in de tegel **Bronvelden**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Schermopname van de pagina Bronvelden met het aantal primaire sleutels, toegewezen en niet-toegewezen velden":::

   Het aantal toegewezen en niet-toegewezen velden wordt weergegeven.

1. Selecteer **Entiteiten en velden selecteren** om andere kenmerken of entiteiten toe te voegen. Gebruik de zoekopdracht of schuif om de kenmerken en entiteiten waarin u bent interessante te zoeken en te selecteren. Selecteer **Toepassen**.

1. Optioneel kunt u de primaire sleutel voor een entiteit, de kenmerktypen wijzigen en **Intelligente toewijzing** aan- of uitzetten. Zie [Primaire sleutel en semantisch type voor kenmerken selecteren](map-entities.md#select-primary-key-and-semantic-type-for-attributes) voor meer informatie.

1. Selecteer **Volgende** om wijzigingen aan te brengen in ontdubbelingsregels of selecteer **Opslaan en sluiten** en keer terug naar [De harmonisatie-instellingen bijwerken](#update-the-unification-settings).

## <a name="manage-deduplication-rules"></a>Ontdubbelingsregels beheren

1. Selecteer **Bewerken** in de tegel **Ontdubbelingsregels**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Schermopname van de pagina Dubbele records met het aantal dubbele records" lightbox="media/m3_duplicates_edit.png":::

   Het aantal gevonden dubbele records wordt weergegeven onder **Duplicaten**. De kolom **Records ontdubbeld** toont welke entiteiten dubbele records hadden en het percentage dubbele records.

1. Als u een verrijkte entiteit hebt toegevoegd, selecteert u **Verrijkte entiteiten gebruiken**. Zie [Verrijking voor gegevensbronnen](data-sources-enrichment.md) voor meer informatie.

1. Kies een van de volgende opties om ontdubbelingsregels te beheren:
   - **Een nieuwe regel maken** : selecteer **Regel toevoegen** onder de betreffende entiteit. Zie [Ontdubbelingsregels definiëren](remove-duplicates.md#define-deduplication-rules) voor meer informatie.
   - **Regelvoorwaarden wijzigen**: selecteer de regel en vervolgens **Bewerken**. Wijzig velden, voeg voorwaarden toe of verwijder deze, of voeg uitzonderingen toe of verwijder deze.
   - **Voorbeeld**: selecteer de regel en vervolgens **Voorbeeld** om de resultaten van de laatste uitvoering voor deze regel te bekijken.
   - **Een regel deactiveren**: selecteer de regel en vervolgens **Deactiveren** om een ontdubbelingsregel te behouden en deze uit te sluiten van het matchingproces.
   - **Een regel dupliceren**: selecteer de regel en vervolgens **Dupliceren** om een soortgelijke regel met aanpassingen te maken.
   - **Een regel verwijderen**: selecteer de regel en vervolgens **Verwijderen**.

1. Selecteer de entiteit om de samenvoegvoorkeuren te wijzigen. U kunt de voorkeuren alleen wijzigen als er een regel is gemaakt.
   1. Selecteer **Samenvoegvoorkeuren bewerken** en wijzig de optie **Te bewaren record**.
   1. Om samenvoegvoorkeuren voor individuele kenmerken van een entiteit te wijzigen, selecteert u **Geavanceerd** en breng de nodige wijzigingen aan.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Schermopname van geavanceerde samenvoegvoorkeuren met e-mail en volledig adres die het meest recent zijn":::

   1. Selecteer **Gereed**.

1. Selecteer **Volgende** om wijzigingen aan te brengen in overeenkomstvoorwaarden of selecteer **Opslaan en sluiten** en keer terug naar [De harmonisatie-instellingen bijwerken](#update-the-unification-settings).

## <a name="manage-match-rules"></a>Overeenkomstregels beheren

U kunt de meeste vergelijkingsparameters opnieuw configureren en verfijnen. U kunt geen entiteiten toevoegen of verwijderen. Overeenkomstregels zijn niet van toepassing op één entiteit.

1. Selecteer **Bewerken** in de tegel **Overeenkomstvoorwaarden**.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Schermopname van de pagina met overeenkomstregels en -voorwaarden met statistieken." lightbox="media/m3_match_edit.png":::

   De pagina toont de afstemmingsvolgorde en gedefinieerde regels en de volgende statistieken:
   - **Unieke bronrecords** toont het aantal individuele bronrecords dat is verwerkt tijdens de laatste vergelijkingsuitvoering.
   - **Overeenkomende en niet-overeenkomende records** geeft aan hoeveel unieke records er overblijven na verwerking van de overeenkomstregels.
   - **Alleen overeenkomende records** toont het aantal overeenkomsten voor al uw vergelijkingsparen.

1. Om de resultaten van alle regels en hun scores te zien, selecteert u **Laatste uitvoering bekijken**. De resultaten worden weergegeven inclusief de alternatieve contactpersoon-id's. U kunt de resultaten downloaden.

1. Om de resultaten en scores van een bepaalde regel te bekijken, selecteert u de regel en vervolgens **Voorbeeld**. De resultaten worden weergegeven. U kunt de resultaten downloaden.

1. Om de resultaten en scores van een bepaalde voorwaarde bij een regel te bekijken, selecteert u de regel en vervolgens **Bewerken**. Selecteer in het bewerkingsdeelvenster **Voorbeeld** onder de voorwaarde. U kunt de resultaten downloaden.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Grafische weergave van overeenkomende en niet-overeenkomende records, inclusief een lijst van de gegevens.":::

1. Als u een verrijkte entiteit hebt toegevoegd, selecteert u **Verrijkte entiteiten gebruiken**. Zie [Verrijking voor gegevensbronnen](data-sources-enrichment.md) voor meer informatie.

1. Kies een van de volgende opties om regels te beheren:
   - **Een nieuwe regel maken** : selecteer **Regel toevoegen** onder de betreffende entiteit. Zie [Regels voor vergelijkingsparen definiëren](match-entities.md#define-rules-for-match-pairs) voor meer informatie.
   - **Wijzig de volgorde van uw regels** als u meerdere regels hebt gedefinieerd: sleep de regels en zet ze neer in de gewenste volgorde. Zie [Afstemmingsvolgorde opgeven](match-entities.md#specify-the-match-order) voor meer informatie.
   - **Regelvoorwaarden wijzigen**: selecteer de regel en vervolgens **Bewerken**. Wijzig velden, voeg voorwaarden toe of verwijder deze, of voeg uitzonderingen toe of verwijder deze.
   - **Een regel deactiveren**: selecteer de regel en vervolgens **Deactiveren** om een overeenkomstregel te behouden en deze uit te sluiten van het matchingproces.
   - **Een regel dupliceren**: selecteer de regel en vervolgens **Dupliceren** om een soortgelijke regel met aanpassingen te maken.
   - **Een regel verwijderen**: selecteer de regel en vervolgens **Verwijderen**.

1. Selecteer **Volgende** om wijzigingen aan te brengen in geharmoniseerde velden of selecteer **Opslaan en sluiten** en keer terug naar [De harmonisatie-instellingen bijwerken](#update-the-unification-settings).

## <a name="manage-unified-fields"></a>Geharmoniseerde velden beheren

1. Selecteer **Bewerken** in de tegel **Geharmoniseerde klantvelden**.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Schermopname van geharmoniseerde klantvelden":::

1. Bekijk de gecombineerde en uitgesloten velden en breng zo nodig wijzigingen aan. Voeg de CustomerID-sleutel of groepsprofielen toe of bewerk deze in clusters. Zie [Klantvelden harmoniseren](merge-entities.md) voor meer informatie.

1. Selecteer **Volgende** om de harmonisatie-instellingen te bekijken en [het geharmoniseerde profiel en de afhankelijkheden bij te werken](#run-updates-to-the-unified-customer-profile) of selecteer **Opslaan en sluiten** en keer terug naar [De harmonisatie-instellingen bijwerken](#update-the-unification-settings) om meer wijzigingen aan te brengen.

## <a name="run-matching-conditions"></a>Overeenkomstvoorwaarden uitvoeren

Met overeenkomende voorwaarden uitvoeren worden alleen ontdubbelings- en overeenkomstregels uitgevoerd en worden de entiteiten *Ontdubbeling* en *ConflationMatchPair* bijgewerkt.

1. Op de pagina **Gegevens** > **Harmoniseren** selecteert u **Alleen overeenkomstvoorwaarden uitvoeren**.

   De tegels **Dubbele records** en **Overeenkomstvoorwaarden** tonen de status **In wachtrij** of **Vernieuwen**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Wanneer het matchingproces is voltooid, selecteert u **Bewerken** op de tegel **Overeenkomstvoorwaarden**.

   :::image type="content" source="media/match-KPIs.png" alt-text="Bijgesneden schermopname van de belangrijkste statistieken op de pagina Afstemming met cijfers en details.":::

1. Zie [Ontdubbelingsregels beheren](#manage-deduplication-rules) of [Overeenkomstregels beheren](#manage-match-rules) om wijzigingen aan te brengen.

1. Voer het matchingproces opnieuw uit of [voer updates uit op het klantprofiel](#run-updates-to-the-unified-customer-profile).

## <a name="run-updates-to-the-unified-customer-profile"></a>Updates uit op het geharmoniseerde klantprofiel

1. Selecteer op de pagina **Gegevens** > **Harmoniseren**:

   - **Klantprofielen harmoniseren**: voert overeenkomende voorwaarden uit en werkt de entiteit unified customer profile bij zonder afhankelijkheden (zoals verrijkingen, segmenten of metingen) te beïnvloeden. Afhankelijke processen worden niet uitgevoerd, maar worden vernieuwd zoals [gedefinieerd in het vernieuwingsschema](system.md#schedule-tab).

   - **Klantprofielen en afhankelijkheden harmoniseren**: voert overeenkomende voorwaarden uit en werkt het geharmoniseerde profiel en alle afhankelijkheden bij. Alle processen worden automatisch opnieuw uitgevoerd. Nadat alle downstreamprocessen zijn voltooid, weerspiegelt het klantprofiel de bijgewerkte gegevens.

   De tegels **Dubbele records**, **Overeenkomstvoorwaarden** en **Geharmoniseerde klantvelden** tonen de status **In wachtrij** of **Vernieuwen**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

De resultaten van een succesvolle uitvoering worden weergegeven op de pagina **Harmoniseren** met het aantal geharmoniseerde klantprofielen.
