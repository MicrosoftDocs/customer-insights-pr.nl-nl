---
title: Instellingen voor klant-, account- of contactpersoonharmonisatie bijwerken
description: Werk dubbele regels, overeenkomstregels of geharmoniseerde velden bij in de harmonisatie-instellingen voor contactpersonen of accounts.
ms.date: 08/26/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: Scott-Stabbert
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: e893e66fd7691b9703d51ed8f87cfad63880cc3b
ms.sourcegitcommit: 560c4ee16376a9c6fdd7860988ce2d2440194fa5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/01/2022
ms.locfileid: "9392465"
---
# <a name="update-unification-settings"></a>Harmonisatie-instellingen bijwerken

Voer de volgende stappen uit om harmonisatie-instellingen te bekijken of te wijzigen nadat een geharmoniseerd profiel is gemaakt.

1. Ga naar **Gegevens** > **Harmoniseren**.

   Voor individuele klanten (B2C) wordt op de pagina **Harmoniseren** het aantal geharmoniseerde klantprofielen en tegels voor elk van de harmonisatiestappen weergegeven.

   :::image type="content" source="media/m3_unified.png" alt-text="Schermopname van de pagina Gegevens harmoniseren nadat de gegevens zijn geharmoniseerd." lightbox="media/m3_unified.png":::

   Voor zakelijke accounts (B2B) wordt op de pagina **Harmoniseren** het aantal geharmoniseerde accountprofielen en tegels voor elk van de harmonisatiestappen weergegeven. Als contactpersonen geharmoniseerd waren, wordt het aantal geharmoniseerde contactpersoonprofielen en tegels voor elk van de stappen voor harmonisatgie van contactpersonen weergegeven. Kies de juiste tegel onder **Accounts samenvoegen** of **Contactpersonen samenvoegen (preview)**, afhankelijk van wat u wilt bijwerken.

   :::image type="content" source="media/b2b_unified.png" alt-text="Schermopname van de pagina Gegevens harmoniseren nadat account- en contactpersoongegevens zijn geharmoniseerd." lightbox="media/b2b_unified.png":::

   > [!TIP]
   > De tegel **Overeenkomende voorwaarden** wordt alleen weergegeven als er meerdere entiteiten zijn geselecteerd.

1. Kies wat u wilt bijwerken:
   - [Bronvelden](#edit-source-fields) om kenmerken of entiteiten toe te voegen of kenmerktypen te wijzigen. Zie [Een geharmoniseerd veld verwijderen](#remove-a-unified-field) als u een kenmerk wilt verwijderen. Zie [Een geharmoniseerde entiteit verwijderen](#remove-a-unified-entity) als u een entiteit wilt verwijderen.
   - [Dubbele records](#manage-deduplication-rules) om ontdubbelingsregels of samenvoegvoorkeuren te beheren.
   - [Overeenkomstvoorwaarden](#manage-match-rules) om overeenkomstregels voor twee of meer entiteiten bij te werken.
   - [Geharmoniseerde klantvelden](#manage-unified-fields) om velden te combineren of uit te sluiten. U kunt gerelateerde profielen ook in clusters groeperen.
   - [Semantische velden](#manage-semantic-fields-for-unified-contacts) om semantische typen te beheren voor geharmoniseerde contactpersoonvelden.
   - [Relaties](#manage-contact-and-account-relationships) om de relatie tussen contactpersonen en accounts te beheren.

1. Nadat u uw wijzigingen hebt aangebracht, kiest u uw volgende optie:

   - [Voer overeenkomstvoorwaarden uit](#run-matching-conditions) om de kwaliteit van uw overeenkomstvoorwaarden (regels voor ontdubbeling en overeenkomsten) snel te evalueren zonder het geharmoniseerde profiel bij te werken. De optie **Alleen overeenkomstvoorwaarden uitvoeren** wordt niet weergegeven voor één entiteit.
   - [Profielen verenigen](#run-updates-to-the-unified-profile) om overeenkomende voorwaarden uit te voeren en de entiteit geharmoniseerd klantprofiel bij te werken zonder afhankelijkheden (zoals verrijkingen, segmenten of meetcriteria) te beïnvloeden. Afhankelijke processen worden niet uitgevoerd, maar worden vernieuwd zoals [gedefinieerd in het vernieuwingsschema](schedule-refresh.md).
   - [Profielen en afhankelijkheden verenigen](#run-updates-to-the-unified-profile) om overeenkomende voorwaarden uit te voeren en de entiteit geharmoniseerd profiel en alle afhankelijkheden (zoals verrijkingen, segmenten of meetcriteria ) bij te werken. Alle processen worden automatisch opnieuw uitgevoerd. In B2B wordt harmonisatie uitgevoerd op zowel de account- als contactpersoonentiteit, waarbij de geharmoniseerde profielen worden bijgewerkt.

## <a name="edit-source-fields"></a>Bronvelden bewerken

1. Selecteer **Bewerken** in de tegel **Bronvelden**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Schermopname van de pagina Bronvelden met het aantal primaire sleutels, toegewezen en niet-toegewezen velden":::

   Het aantal toegewezen en niet-toegewezen velden wordt weergegeven.

1. Selecteer **Entiteiten en velden selecteren** om andere kenmerken of entiteiten toe te voegen.

1. Optioneel kunt u de primaire sleutel voor een entiteit, de kenmerktypen wijzigen en **Intelligente toewijzing** aan- of uitzetten. Zie [Bronvelden selecteren](map-entities.md) voor meer informatie.

1. Selecteer **Volgende** om wijzigingen aan te brengen in ontdubbelingsregels of selecteer **Opslaan en sluiten** en keer terug naar [Harmonisatie-instellingen bijwerken](#update-unification-settings).

### <a name="remove-a-unified-field"></a>Een geharmoniseerd veld verwijderen

Als u een veld wilt verwijderen dat is geharmoniseerd, moet het veld worden verwijderd uit alle afhankelijkheden, zoals segmenten, metingen, verrijkingen of relaties.

1. Zodra alle afhankelijkheden voor het veld zijn verwijderd, gaat u naar **Gegevens** > **Harmoniseren**.

1. Selecteer **Bewerken** in de tegel **Geharmoniseerde klantvelden**.

1. Selecteer alle exemplaren van het veld en selecteer vervolgens **Uitsluiten**.

   :::image type="content" source="media/m3_remove_attribute1.png" alt-text="Schermopname van de pagina Geharmoniseerde velden en knop Uitsluiten":::

1. Selecteer **Gereed** om te bevestigen en selecteer vervolgens **Opslaan en sluiten**.

   > [!TIP]
   > Als u het bericht 'Kan samenvoegen niet opslaan. De opgegeven resource kan niet worden gewijzigd of verwijderd vanwege downstream afhankelijkheden' te zien krijgt, wordt het veld nog steeds gebruikt in een stroomafwaartse afhankelijkheid:

1. Als het veld wordt gebruikt in een regel voor dubbele records of overeenkomstvoorwaarden, voert u de volgende stappen uit. Ga anders naar de volgende stap.
   1. Selecteer **Bewerken** in de tegel **Ontdubbelingsregels**.
   1. Verwijder het veld uit alle regels waarin het wordt gebruikt, indien van toepassing, en selecteer vervolgens **Volgende**.
   1. Verwijder op de pagina **Overeenkomstvoorwaarden** het veld uit alle regels waarin het wordt gebruikt, indien van toepassing, en selecteer vervolgens **Opslaan en sluiten**.
   1. Selecteer **Harmoniseren** > **Klantprofielen en afhankelijkheden verenigen**. Wacht tot de harmonisatie is voltooid voordat u naar de volgende stap gaat.

1. Selecteer **Bewerken** in de tegel **Bronvelden**.

1. Selecteer **Entiteiten en velden selecteren** en schakel het selectievakje naast elk exemplaar van het veld uit.

   :::image type="content" source="media/m3_remove_attribute2.png" alt-text="Schermopname van het dialoogvenster Entiteiten en velden selecteren met uitgeschakelde selectievakjes":::

1. Selecteer **Toepassen**.

1. Selecteer **Opslaan en sluiten**.

1. Selecteer **Harmoniseren** > **Klantprofielen en afhankelijkheden harmoniseren** om het geharmoniseerde profiel bij te werken.

### <a name="remove-a-unified-entity"></a>Een geharmoniseerde entiteit verwijderen

Als u een entiteit wilt verwijderen die is geharmoniseerd, moet de entiteit worden verwijderd uit alle afhankelijkheden, zoals segmenten, metingen, verrijkingen of relaties.

1. Zodra alle afhankelijkheden voor de entiteit zijn verwijderd, gaat u naar **Gegevens** > **Harmoniseren**.

1. Selecteer **Bewerken** in de tegel **Geharmoniseerde klantvelden**.

1. Selecteer alle velden voor de entiteit en vervolgens **Uitsluiten**.

   :::image type="content" source="media/m3_remove_entity1.png" alt-text="Schermopname van Geharmoniseerde velden met alle velden voor een entiteit geselecteerd en de knop Uitsluiten":::

1. Selecteer **Gereed** om te bevestigen en selecteer vervolgens **Opslaan en sluiten**.

   > [!TIP]
   > Als u het bericht 'Kan samenvoegen niet opslaan. De opgegeven resource kan niet worden gewijzigd of verwijderd vanwege downstream afhankelijkheden' te zien krijgt, wordt de entiteit nog steeds gebruikt in een stroomafwaartse afhankelijkheid:

1. Selecteer **Bewerken** in de tegel **Ontdubbelingsregels**.

1. Verwijder alle regels uit de entiteit, indien van toepassing, en selecteer vervolgens **Volgende**.

1. Op de pagina **Overeenkomstvoorwaarden** selecteert u de entiteit en vervolgens **Verwijderen**.

   :::image type="content" source="media/m3_remove_entity2.png" alt-text="Schermopname van Overeenkomstvoorwaarden met geselecteerde entiteit en knop Verwijderen":::

1. Selecteer **Opslaan en sluiten**.

1. Selecteer **Bewerken** in de tegel **Bronvelden**.

1. Selecteer **Entiteiten en velden selecteren** en schakel het selectievakje naast de entiteit uit.

   :::image type="content" source="media/m3_remove_entity3.png" alt-text="Schermopname van het dialoogvenster Entiteiten en velden selecteren met uitgeschakeld selectievakje voor entiteit":::

1. Selecteer **Toepassen**.

1. Selecteer **Opslaan en sluiten**.

1. Selecteer **Harmoniseren** > **Klantprofielen en afhankelijkheden harmoniseren** om het geharmoniseerde profiel bij te werken.

## <a name="manage-deduplication-rules"></a>Ontdubbelingsregels beheren

1. Selecteer **Bewerken** in de tegel **Ontdubbelingsregels**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Schermopname van de pagina Dubbele records met het aantal dubbele records" lightbox="media/m3_duplicates_edit.png":::

   Het aantal gevonden dubbele records wordt weergegeven onder **Duplicaten**. De kolom **Records ontdubbeld** toont welke entiteiten dubbele records hadden en het percentage dubbele records.

1. Als u een verrijkte entiteit wilt gebruiken, selecteert u **Verrijkte entiteiten gebruiken**. Zie [Verrijking voor gegevensbronnen](data-sources-enrichment.md) voor meer informatie.

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

   1. Selecteer **Gereed**.

1. Selecteer **Volgende** om wijzigingen aan te brengen in overeenkomstvoorwaarden of selecteer **Opslaan en sluiten** en keer terug naar [Harmonisatie-instellingen bijwerken](#update-unification-settings).

## <a name="manage-match-rules"></a>Overeenkomstregels beheren

U kunt de meeste vergelijkingsparameters opnieuw configureren en verfijnen. U kunt geen entiteiten toevoegen of verwijderen. Overeenkomstregels zijn niet van toepassing op één entiteit.

1. Selecteer **Bewerken** in de tegel **Overeenkomstvoorwaarden**.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Schermopname van de pagina met overeenkomstregels en -voorwaarden met statistieken." lightbox="media/m3_match_edit.png":::

   De pagina toont de afstemmingsvolgorde en gedefinieerde regels en de volgende statistieken:
   - **Unieke bronrecords** bevat het aantal individuele bronrecords dat is verwerkt tijdens de laatste vergelijkingsuitvoering.
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

1. Selecteer **Volgende** om wijzigingen aan te brengen in geharmoniseerde velden of selecteer **Opslaan en sluiten** en keer terug naar [Harmonisatie-instellingen bijwerken](#update-unification-settings).

## <a name="manage-unified-fields"></a>Geharmoniseerde velden beheren

1. Selecteer **Bewerken** in de tegel **Geharmoniseerde klantvelden**.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Schermopname van geharmoniseerde klantvelden":::

1. Bekijk de gecombineerde en uitgesloten velden en breng zo nodig wijzigingen aan. Voeg de CustomerID-sleutel of groepsprofielen toe of bewerk deze in clusters. Zie [Klantvelden harmoniseren](merge-entities.md) voor meer informatie.

1. Selecteer **Volgende** voor klanten of accounts om [het geharmoniseerde profiel en de afhankelijkheden](#run-updates-to-the-unified-profile) te beoordelen en bij te werken. Of selecteer **Opslaan en sluiten** en keer terug naar [Harmonisatie-instellingen bijwerken](#update-unification-settings) om meer wijzigingen aan te brengen.

   Selecteer **Volgende** voor contactpersonen om semantische velden te beheren. Of selecteer **Opslaan en sluiten** en keer terug naar [Harmonisatie-instellingen bijwerken](#update-unification-settings) om meer wijzigingen aan te brengen.

## <a name="manage-semantic-fields-for-unified-contacts"></a>Semantische velden voor geharmoniseerde contactpersonen beheren

1. Selecteer **Bewerken** in de tegel **Semantische velden**.

1. Selecteer een nieuw type om het semantische type voor een geharmoniseerd veld te wijzigen. Zie [De semantische velden voor samengevoegde contactpersonen definiëren](data-unification-contacts.md#define-the-semantic-fields-for-unified-contacts) voor meer informatie.

1. Selecteer **Volgende** om de account- en contactpersoonrelatie te beheren of selecteer **Opslaan en sluiten** en keer terug naar [Harmonisatie-instellingen bijwerken](#update-unification-settings) om meer wijzigingen aan te brengen.

## <a name="manage-contact-and-account-relationships"></a>Contactpersoon- en accountrelaties beheren

1. Selecteer **Bewerken** in de tegel **Relaties**.

1. Als u de relatie tussen contactpersoon en account wilt wijzigen, wijzigt u een van de volgende gegevens:

   - **Refererende sleutel van contactpersoonentiteit**: kies het kenmerk van uw bronentiteit dat uw contactpersoonentiteit verbindt met het account.
   - **Naar accountentiteit**: kies de accountentiteit die aan de contactpersoon is gekoppeld.

1. Selecteer **Volgende** om de harmonisatie-instellingen te bekijken en [het geharmoniseerde profiel en de afhankelijkheden bij te werken](#run-updates-to-the-unified-profile) of selecteer **Opslaan en sluiten** en keer terug naar [Harmonisatie-instellingen bijwerken](#update-unification-settings) om meer wijzigingen aan te brengen.

## <a name="run-matching-conditions"></a>Overeenkomstvoorwaarden uitvoeren

Met overeenkomende voorwaarden uitvoeren worden alleen ontdubbelings- en overeenkomstregels uitgevoerd en worden de entiteiten *Deduplication_* en *ConflationMatchPair* bijgewerkt.

1. Op de pagina **Gegevens** > **Harmoniseren** selecteert u **Alleen overeenkomstvoorwaarden uitvoeren**.

   De tegels **Dubbele records** en **Overeenkomstvoorwaarden** tonen de status **In wachtrij** of **Vernieuwen**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Wanneer het matchingproces is voltooid, selecteert u **Bewerken** op de tegel **Overeenkomstvoorwaarden**.

   :::image type="content" source="media/match-KPIs.png" alt-text="Bijgesneden schermopname van de belangrijkste statistieken op de pagina Afstemming met cijfers en details.":::

1. Zie [Ontdubbelingsregels beheren](#manage-deduplication-rules) of [Overeenkomstregels beheren](#manage-match-rules) om wijzigingen aan te brengen.

1. Voer het vergelijkingsproces opnieuw uit of [voer updates uit op het profiel](#run-updates-to-the-unified-profile).

## <a name="run-updates-to-the-unified-profile"></a>Updates uitvoeren op het geharmoniseerde profiel

- Als u overeenkomstvoorwaarden wilt uitvoeren en de entiteit geharmoniseerd profiel wilt bijwerken *zonder* afhankelijkheden (zoals verrijkingen, segmenten of meetcriteria) te beïnvloeden, selecteert u **Klantprofielen harmoniseren**. Selecteer voor accounts de optie **Accounts samenvoegen** > **Profielen verenigen**. Selecteer voor contactpersonen de optie **Contactpersonen samenvoegen (preview)** > **Profielen verenigen**. Afhankelijke processen worden niet uitgevoerd, maar worden vernieuwd zoals [gedefinieerd in het vernieuwingsschema](schedule-refresh.md).
- Als u overeenkomstvoorwaarden wilt uitvoeren, het geharmoniseerde profiel wilt bijwerken en alle afhankelijkheden wilt uitvoeren, selecteert u **Klantprofielen en afhankelijkheden harmoniseren**. Alle processen worden automatisch opnieuw uitgevoerd. Selecteer voor accounts en contactpersonen de optie **Accounts samenvoegen** > **Profielen en afhankelijkheden verenigen**. Er worden overeenkomstvoorwaarden uitgevoerd voor zowel accounts als contactpersonen die beide geharmoniseerde profielen bijwerken en alle andere afhankelijkheden worden uitgevoerd.

Alle tegels behalve **Bronvelden** tonen de status **In wachtrij geplaatst** of **Vernieuwen**.

[!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

De resultaten van een succesvolle uitvoering worden weergegeven op de pagina **Harmoniseren** met het aantal geharmoniseerde profielen.
