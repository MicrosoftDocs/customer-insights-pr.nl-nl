---
title: Een geharmoniseerd contactpersoonprofiel maken (preview)
description: Doorloop het proces voor gegevensharmonisering om een enkele hoofdgegevensset van contactpersonen te maken.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- ci-match
- ci-merge
- customerInsights
ms.openlocfilehash: 721f47563582a94b5b8244ca5d5d7d1350695512
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/16/2022
ms.locfileid: "9305013"
---
# <a name="create-a-unified-contact-profile-preview"></a>Een geharmoniseerd contactpersoonprofiel maken (preview)

Na [harmonisatie van zakelijke accounts](map-entities.md) kunt u optioneel contactpersonen voor die accounts harmoniseren en de geharmoniseerde contactpersonen aan de geharmoniseerde accounts koppelen. Het proces voor harmonisatie van contactpersonen wijst contactpersoongegevens uit meerdere gegevensbronnen toe, verwijdert duplicaten, stemt de gegevens af tussen entiteiten, stelt semantische toewijzing in, creëert relaties tussen contactpersonen en accounts en maakt vervolgens een geharmoniseerd contactpersoonprofiel.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

De eerste paar stappen zijn identiek aan de stappen bij het harmoniseren van accounts.

## <a name="prerequisites"></a>Vereisten

Account- en contactpersoonrecords moeten een unieke sleutel hebben (een zogenaamde refererende sleutel) die ze verbindt. Bijvoorbeeld een account-id die bestaat in de accountrecord en contactpersoonrecord, en die de account en contactpersoon aan elkaar koppelt.

## <a name="preview-limitations"></a>Preview-beperkingen

- Contactpersonen zonder een koppeling naar een account worden verwijderd.
- Als een account wordt gededupliceerd, wordt een winnende record geïdentificeerd op basis van de samenvoegvoorkeuren. Verliezende records worden niet geselecteerd en worden daarom verwijderd. Contactpersonen die aan de verliezende records zijn gekoppeld worden verwijderd.
- Een account kan meerdere contactpersonen hebben, maar een contactpersoon is maar aan één account gekoppeld.
- De kenmerken van contactpersonen die in de semantische toewijzingsstap zijn toegewezen, zijn de enige kenmerken die op de klantkaart kunnen worden weergegeven. Er zijn echter 17 kenmerken beschikbaar.

## <a name="select-source-fields"></a>Bronvelden selecteren

1. Selecteer onder **Contactpersonen samenvoegen (preview)** de optie **Aan de slag**.

1. [Selecteer de entiteiten en velden](map-entities.md) voor uw contactpersoongegevens, inclusief de primaire sleutels en kenmerktypen.

1. Selecteer **Volgende**.

## <a name="remove-duplicate-records"></a>Dubbele records verwijderen

1. Optioneel kunt u [ontdubbelingsregels definiëren](remove-duplicates.md) voor uw geselecteerde entiteiten.

1. Selecteer **Volgende**.

## <a name="match-conditions"></a>Overeenkomstvoorwaarden

1. [Definieer de afstemmingsvolgorde en regels](match-entities.md) voor afstemming tussen entiteiten.

1. Selecteer **Volgende**.

## <a name="unify-contact-fields"></a>Contactpersoonvelden samenvoegen

1. [Combineer contactpersoonvelden en sluit deze uit](merge-entities.md).

1. Selecteer **Volgende**.

## <a name="define-the-semantic-fields-for-unified-contacts"></a>De semantische velden voor samengevoegde contactpersonen definiëren

Deze stap in het harmonisatieproces wijst uw geharmoniseerde contactpersoonvelden toe aan semantische typen. In B2B bevatten de klantenkaarten accounts. Wanneer de kaart is geselecteerd, worden alle contactpersonen weergegeven die aan het account zijn gekoppeld. De velden die u in deze stap toewijst, zijn de velden die op de kaarten worden weergegeven.

1. Selecteer het semantische type dat aan elk geharmoniseerd velden is toegewezen. Selecteer **Geen** als een semantisch type niet beschikbaar is.

   :::image type="content" source="media/semantic_mapping.png" alt-text="Schermopname van de pagina Semantische velden voor het definiëren van de semantische typen." lightbox="media/semantic_mapping.png":::

1. Nadat u alle geharmoniseerde velden hebt toegewezen, selecteert u **Volgende**.

## <a name="set-the-relationship-between-contacts-and-accounts"></a>De relatie tussen contactpersonen en accounts instellen

Bij deze stap in het harmonisatieproces worden uw contactpersoongegevens gekoppeld aan de bijbehorende accountgegevens.

1. Voer voor elke entiteit de volgende informatie in:

   - **Refererende sleutel van contactpersoonentiteit**: kies het kenmerk van uw bronentiteit dat uw contactpersoonentiteit verbindt met het account.
   - **Naar accountentiteit**: kies de accountentiteit die aan de contactpersoon is gekoppeld.

   :::image type="content" source="media/contact_relationship.png" alt-text="Schermopname van de pagina Relatie voor het verbinden van de contactpersoon- en accountentiteiten.":::

1. Selecteer **Volgende**.

## <a name="review-contact-unification"></a>Harmonisatie van contactpersonen bekijken

Bekijk het overzicht van wijzigingen, maak het geharmoniseerde profiel en beoordeel de resultaten.

### <a name="review-and-create-contact-profiles"></a>Contactprofielen beoordelen en maken

Deze laatste stap in het harmonisatieproces toont een samenvatting van de stappen in het proces en biedt de mogelijkheid om wijzigingen aan te brengen voordat u het geharmoniseerde contactpersoonprofiel maakt.

:::image type="content" source="media/b2b_review_contacts.png" alt-text="Schermopname van Contactpersoonprofielen beoordelen en maken":::

1. Selecteer **Bewerken** in een van de stappen voor harmonisatie van contactpersonen om te controleren en eventuele wijzigingen aan te brengen.

1. Als u tevreden bent met uw selecties, selecteert u **Contactpersoonprofielen maken**. De pagina **Harmoniseren** wordt weergegeven terwijl het geharmoniseerde contactpersoonprofiel wordt gemaakt.
  
   :::image type="content" source="media/b2b_unify_refreshing.png" alt-text="Schermopname van pagina Contactpersonen harmoniseren met tegels met de status In wachtrij geplaatst of Vernieuwen.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Het harmonisatie-algoritme duurt enige tijd om te voltooien en u kunt de configuratie niet wijzigen totdat het is voltooid.

### <a name="view-the-results-of-contact-unification"></a>De resultaten van contactpersoonharmonisatie bekijken

Nadat de harmonisatie is voltooid, toont de pagina **Gegevens** > **Harmoniseren** het aantal geharmoniseerde contactpersoonprofielen. De resultaten van elke stap in het unificatieproces worden op elke tegel weergegeven. Bijvoorbeeld, **Bronvelden** toont het aantal toegewezen kenmerken (velden) en **Dubbele records** toont het aantal gevonden dubbele records.

:::image type="content" source="media/unified_contacts.png" alt-text="Schermopname van de pagina Gegevens harmoniseren nadat contactpersonen zijn geharmoniseerd.":::

> [!TIP]
> De tegel **Overeenkomende voorwaarden** wordt alleen weergegeven als er meerdere entiteiten zijn geselecteerd.

We raden u aan de resultaten te bekijken, met name de kwaliteit van uw [regels voor overeenkomsten](data-unification-update.md#manage-match-rules) en verfijn ze indien nodig.

Wanneer nodig [brengt u wijzigingen aan in de instellingen voor harmonisatie van contactpersonen](data-unification-update.md) en vervolgens voert u het geharmoniseerde profiel opnieuw uit.

### <a name="verify-output-entities-from-data-unification"></a>Uitvoerentiteiten van gegevensharmonisatie verifiëren

Ga naar **Gegevens** > **Entiteiten** om de uitvoerentiteiten te verifiëren.

De geharmoniseerde contactpersoonprofielentiteit, genaamd *ContactProfile*, wordt weergegeven in de sectie **Ssemantische entiteiten**. Bij de eerste succesvolle harmonisatie-uitvoering wordt de geharmoniseerde entiteit *ContactProfile* gemaakt. Alle volgende uitvoeringen breiden die entiteit uit.

De entiteit *ContactsCustomer* (preview) wordt gemaakt en weergegeven in de sectie **Profielen**. Deze entiteit bevat de contactpersoongegevens zonder de koppelingen naar de accounts. Deze entiteit wordt gebruikt als invoer in de stappen voor semantische toewijzing en relaties van harmonisatie van contactpersonen.

Ontdubbelings- en samenvoegingsentiteiten worden gemaakt en weergegeven in de sectie **Systeem**. Er wordt een ontdubbelingsentiteit gemaakt voor elk van de bronentiteiten met de naam **Deduplication_DataSource_Entity**. De entiteit **ContactsConflationMatchPairs** bevat informatie over overeenkomsten tussen entiteiten.

Een entiteit voor ontdubbelingsuitvoer bevat de volgende informatie:
- Id's/sleutels
  - Velden Primaire sleutel en Alternatieve id. Het veld Alternatieve id bestaat uit alle alternatieve id's die voor een record zijn geïdentificeerd.
  - Het veld Deduplication_GroupId toont de groep of cluster die is geïdentificeerd binnen een entiteit die alle vergelijkbare records groepeert op basis van de opgegeven ontdubbelingsvelden. Dit wordt gebruikt voor systeemverwerkingsdoeleinden. Als er geen handmatige ontdubbelingsregels zijn opgegeven en door het systeem gedefinieerde ontdubbelingsregels van toepassing zijn, is het mogelijk dat u dit veld niet in de uitvoerentiteit voor ontdubbeling vindt.
  - Deduplication_WinnerId: dit veld bevat de winnende id van de geïdentificeerde groepen of clusters. Als de Deduplication_WinnerId hetzelfde is als de primaire sleutelwaarde voor een record, betekent dit dat de record de winnende record is.
- Velden die worden gebruikt om de ontdubbelingsregels te definiëren.
- Regel- en scorevelden om aan te geven welke van de ontdubbelingsregels zijn toegepast en welke score is geretourneerd door het matching-algoritme.

## <a name="next-step"></a>Volgende stap

Configureer [activiteiten](activities.md), [verrijking](enrichment-hub.md) of [relaties](relationships.md) voor meer inzichten over uw contactpersonen.
