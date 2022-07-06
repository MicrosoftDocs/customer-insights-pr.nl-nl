---
title: Klantvelden harmoniseren voor gegevensharmonisatie
description: Voeg entiteiten samen om geharmoniseerde klantprofielen te maken.
recommendations: false
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-merge
- ci-match
- ci-relationships
- customerInsights
ms.openlocfilehash: ceb2724ad490c1ba44fd9b7ff2be04721892fca4
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081164"
---
# <a name="unify-customer-fields-for-data-unification"></a>Klantvelden harmoniseren voor gegevensharmonisatie

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

In deze stap van het harmonisatieproces kiest u kenmerken en sluit u kenmerken uit om samen te voegen binnen uw geharmoniseerde-profielentiteit. Als drie entiteiten bijvoorbeeld e-mailgegevens bevatten, wilt u misschien alle drie de afzonderlijke e-mailvelden behouden of ze samenvoegen tot één e-mailveld voor het geharmoniseerde profiel. Sommige kenmerken worden automatisch door het systeem gecombineerd. U kunt stabiele en unieke klant-id's maken en gerelateerde profielen groeperen in een cluster.

:::image type="content" source="media/m3_unify.png" alt-text="Samenvoegpagina in het gegevensharmonisatieproces waarop een tabel wordt weergegeven met samengevoegde velden die het uniforme klantprofiel definiëren.":::

## <a name="review-and-update-the-customer-fields"></a>Velden voor klantprofiel bekijken en bewerken

1. Bekijk de lijst met velden die worden geharmoniseerd in het tabblad **Klantvelden** van de tabel. Breng eventueel wijzigingen aan.

   1. Voor elke combinatie van velden kunt u:
      - [Bewerken](#edit-a-merged-field)
      - [Naam wijzigen](#rename-fields)
      - [Scheiden](#separate-merged-fields)
      - [Uitsluiten](#exclude-fields)
      - [Omhoog of omlaag verplaatsen](#change-the-order-of-fields)

   1. Voor afzonderlijke velden kunt u:
      - [Velden combineren](#combine-fields-manually)
      - [Een groep velden combineren](#combine-a-group-of-fields)
      - [Naam wijzigen](#rename-fields)
      - [Uitsluiten](#exclude-fields)
      - [Omhoog of omlaag verplaatsen](#change-the-order-of-fields)

1. Desgewenst [het genereren van de klant-id configureren](#configure-customer-id-generation).

1. Desgewenst [profielen groeperen in huishoudens of clusters](#group-profiles-into-households-or-clusters).

> [!div class="nextstepaction"]
> [Volgende stap: Harmonisatie bekijken](review-unification.md)

### <a name="edit-a-merged-field"></a>Een samengevoegd veld bewerken

1. Selecteer een samengevoegd veld en kies **Bewerken**. Het deelvenster Velden combineren wordt weergegeven.

1. Geef op hoe u de velden wilt combineren of samenvoegen door een van de drie opties te kiezen:
    - **Belang**: geeft de winnende waarde aan op basis van de mate van belang die voor de deelnemende velden is opgegeven. Dit is de standaard samenvoegingsoptie. Selecteer **Omhoog/omlaag verplaatsen** om de rangorde van belang in te stellen.

      :::image type="content" source="media/importance-merge-option.png" alt-text="De optie Belang in het dialoogvenster voor het samenvoegen van velden.":::

    - **Meest recente** : geeft de winnende waarde aan op basis van de meest recente. Vereist een datum of een numeriek veld voor elke deelnemende entiteit in het bereik van samenvoegvelden om de recentheid te definiëren.

      :::image type="content" source="media/recency-merge-option.png" alt-text="De optie Recentheid in het dialoogvenster voor het samenvoegen van velden.":::

    - **Minst recente** : geeft de winnende waarde aan op basis van de minst recente. Vereist een datum of een numeriek veld voor elke deelnemende entiteit in het bereik van samenvoegvelden om de recentheid te definiëren.

1. U kunt meer velden toevoegen om deel te nemen aan het samenvoegproces.

1. U kunt de naam van het samenvoegveld wijzigen.

1. Selecteer **Gereed** om uw wijzigingen toe te passen.

### <a name="rename-fields"></a>Naam van velden wijzigen

Wijzig de weergavenaam van samengevoegde of afzonderlijke velden. U kunt de naam van de uitvoerentiteit niet wijzigen.

1. Selecteer het veld en kies **Naam wijzigen**.

1. Voer de nieuwe weergavenaam in.

1. Selecteer **Gereed**.

### <a name="separate-merged-fields"></a>Aparte samengevoegde velden

Zoek het kenmerk in de tabel om samengevoegde velden te scheiden. Gescheiden velden worden weergegeven als individuele gegevenspunten in het uniforme klantprofiel.

1. Selecteer het samengevoegde veld en kies **Afzonderlijke velden**.

1. Bevestig de scheiding.

### <a name="exclude-fields"></a>Velden uitsluiten

Een samengevoegd of afzonderlijk veld uitsluiten van het geharmoniseerde klantprofiel. Als het veld in andere processen wordt gebruikt, bijvoorbeeld in een segment, verwijder het dan uit deze processen voordat u het uitsluit van het klantprofiel.

1. Selecteer een veld en kies **Uitsluiten**.

1. Bevestig de uitsluiting.

Om de lijst met alle uitgesloten velden te zien, selecteert u **Uitgesloten velden**. Indien nodig kunt u het uitgesloten veld lezen.

### <a name="change-the-order-of-fields"></a>De volgorde van velden wijzigen

Sommige entiteiten bevatten meer details dan andere. Als een entiteit de nieuwste gegevens over een veld bevat, kunt u deze prioriteit geven boven andere entiteiten bij het samenvoegen van waarden.

1. Selecteer het veld.
  
1. Kies **Omhoog/omlaag verplaatsen** om de volgorde in te stellen of sleep ze naar de gewenste positie.

### <a name="combine-fields-manually"></a>Velden handmatig combineren

Combineer afzonderlijke velden om een samengevoegd kenmerk te maken.

1. Selecteer **Combineren** > **Velden**. Het deelvenster Velden combineren wordt weergegeven.

1. Geef het beleid voor de winnende samenvoeging op via het vervolgkeuzemenu **Velden combineren op**.

1. Selecteer **Veld toevoegen** om meerdere velden te combineren.

1. Geef informatie op voor **Naam** en **Naam van uitvoerveld**.

1. Selecteer **Gereed** om de wijzigingen toe te passen.

### <a name="combine-a-group-of-fields"></a>Een groep velden combineren

Behandel een groep velden als een enkele eenheid. Als onze records bijvoorbeeld de velden Address1, Address2, City, State en Zip bevatten, willen we liever niet samenvoegen in Address2 van een andere record, omdat we denken dat dit onze gegevens completer zou maken.

1. Selecteer **Combineren** > **Groep velden**.

1. Geef het beleid voor de winnende samenvoeging op via het vervolgkeuzemenu **Groepen rangschikken op**.

1. Selecteer **Toevoegen** en kies of u meer velden of groepen aan de velden wilt toevoegen.

1. Geef een **Naam** en een **Uitvoernaam** op voor elk gecombineerd veld.

1. Geef een **Naam** op voor de groep velden.

1. Selecteer **Gereed** om de wijzigingen toe te passen.

## <a name="configure-customer-id-generation"></a>Het genereren van de klant-id configureren

Definieer hoe u klant-id-waarden genereert, de unieke klantprofiel-id's. De stap voor het harmoniseren van velden in het gegevensharmonisatieproces genereert de unieke klantprofiel-id. De id is de *CustomerId* in de entiteit *Klant* die het resultaat is van het proces van gegevensharmonisatie.

De *CustomerId*  is gebaseerd op een hash van de eerste waarde van de niet-null winnende primaire sleutels. Deze sleutels zijn afkomstig van de entiteiten die worden gebruikt bij gegevensharmonisatie en worden beïnvloed door de afstemmingsvolgorde. De gegenereerde klant-id kan dus veranderen wanneer een primaire-sleutelwaarde verandert in de primaire entiteit van de afstemmingsvolgorde. De waarde van de primaire sleutel vertegenwoordigt dus mogelijk niet altijd dezelfde klant.

Door een stabiele klant-id te configureren, kunt u dat gedrag vermijden.

1. Ga naar het tabblad **Sleutels**.

1. Wijs de rij **CustomerId** aan en selecteer **Configureren**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Controle om het genereren van de id aan te passen.":::

1. Selecteer maximaal vijf velden die een unieke klant-id vormen en stabieler zijn. Records die niet overeenkomen met uw configuratie, gebruiken in plaats daarvan een door het systeem geconfigureerde id.  

1. Selecteer **Gereed**.

## <a name="group-profiles-into-households-or-clusters"></a>Groepeer profielen in huishoudens of clusters

U kunt regels definiëren om gerelateerde profielen in een cluster te groeperen. Er zijn momenteel twee soorten clusters beschikbaar: huishoudelijke en aangepaste clusters. Het systeem kiest automatisch een huishouden met vooraf gedefinieerde regels als de entiteit *Klant* de semantische velden *Person.LastName* en *Location.Address* bevat. U kunt ook een cluster maken met uw eigen regels en voorwaarden, vergelijkbaar met [afstemmingsregels](match-entities.md#define-rules-for-match-pairs).

1. Selecteer **Geavanceerd** > **Cluster maken**.

   :::image type="content" source="media/create-cluster.png" alt-text="Besturingselement om een nieuwe cluster te maken.":::

1. Kies tussen een cluster van het type **Huishouden** of **Aangepast**. Als de semantische velden *Person.LastName* en *Location.Address* bestaan in de entiteit *Klant*, wordt automatisch huishouden geselecteerd.

1. Geef een naam op voor het cluster en selecteer **Gereed**.

1. Selecteer het tabblad **Clusters** om het cluster te vinden dat u hebt gemaakt.

1. Geef de regels en voorwaarden op om uw cluster te definiëren.

1. Selecteer **Gereed**. Het cluster wordt gemaakt wanneer het harmonisatieproces is voltooid. De cluster-id's worden als nieuwe velden toegevoegd aan de entiteit *Customer*.

> [!div class="nextstepaction"]
> [Volgende stap: Harmonisatie bekijken](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
