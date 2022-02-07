---
title: Entiteiten samenvoegen in gegevensharmonisatie
description: Voeg entiteiten samen om geharmoniseerde klantprofielen te maken.
ms.date: 01/28/2022
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
  - ci-merge
---

# <a name="merge-entities"></a>Entiteiten samenvoegen

De samenvoegingsfase is de laatste fase in het proces van gegevensharmonisatie. Het doel is het afstemmen van conflicterende gegevens. Voorbeelden van conflicterende gegevens kunnen een klantnaam zijn die in twee van uw gegevenssets is gevonden, maar in elk een beetje anders verschijnt ("Grant Marshall" versus "Grant Marshal"), of een telefoonnummer met een andere indeling(617-803-091X versus 617803091X). Het samenvoegen van die conflicterende gegevenspunten gebeurt op een kenmerk-per-kenmerkbasis.

:::image type="content" source="media/merge-fields-page.png" alt-text="Samenvoegpagina in het gegevensharmonisatieproces waarop een tabel wordt weergegeven met samengevoegde velden die het uniforme klantprofiel definiëren.":::

Na het voltooien van de [afstemmingsfase](match-entities.md), kunt u de samenvoegingsfase starten door de tegel **Samenvoegen** te selecteren op de pagina **Harmoniseren**.

## <a name="review-system-recommendations"></a>Systeemaanbevelingen bekijken

Bij **Gegevens** > **Harmoniseren** > **Samenvoegen** kiest u welke kenmerken u wel en niet wilt opnemen voor samenvoeging in uw uniforme klantprofielentiteit. Het uniforme klantprofiel is het resultaat van het gegevensharmonisatieproces. Sommige kenmerken worden automatisch door het systeem samengevoegd.

Als u de kenmerken wilt weergeven die zijn opgenomen in een van uw automatisch samengevoegde kenmerken, selecteert u dat samengevoegde kenmerk op het tabblad **Klantvelden** van de tabel. De kenmerken waaruit dat samengevoegde kenmerk is samengesteld, worden weergegeven in twee nieuwe rijen onder het samengevoegde kenmerk.

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>Samengevoegde velden scheiden, hernoemen, uitsluiten en bewerken

U kunt wijzigen hoe in het systeem samengevoegde kenmerken worden verwerkt om het uniforme klantprofiel te genereren. Selecteer **Meer weergeven** en kies wat u wilt veranderen.

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Opties in het vervolgkeuzemenu Meer weergeven om samengevoegde kenmerken te beheren.":::

Zie de volgende gedeelten voor meer informatie.

## <a name="separate-merged-fields"></a>Aparte samengevoegde velden

Zoek het kenmerk in de tabel om samengevoegde velden te scheiden. Gescheiden velden worden weergegeven als individuele gegevenspunten in het uniforme klantprofiel. 

1. Selecteer het samengevoegde veld.
  
1. Selecteer **Meer weergeven** en kies **Afzonderlijke velden**.
 
1. Bevestig de scheiding.

1. Selecteer **Opslaan** en **Uitvoeren** om de wijzigingen te verwerken.

## <a name="rename-merged-fields"></a>Samengevoegde velden hernoemen

Wijzig de weergavenaam van samengevoegde kenmerken. U kunt de naam van de uitvoerentiteit niet wijzigen.

1. Selecteer het samengevoegde veld.
  
1. Selecteer **Meer weergeven** en kies **Naam wijzigen**.

1. Bevestig de gewijzigde weergavenaam. 

1. Selecteer **Opslaan** en **Uitvoeren** om de wijzigingen te verwerken.

## <a name="exclude-merged-fields"></a>Samengevoegde velden uitsluiten

Sluit een kenmerk uit van het uniforme klantprofiel. Als het veld in andere processen wordt gebruikt, bijvoorbeeld in een segment, verwijder het dan uit deze processen voordat u het uitsluit van het klantprofiel. 

1. Selecteer een samengevoegd veld.
  
1. Selecteer **Meer weergeven** en kies **Uitsluiten**.

1. Bevestig de uitsluiting.

1. Selecteer **Opslaan** en **Uitvoeren** om de wijzigingen te verwerken. 

Selecteer op de pagina **Samenvoegen** **Uitgesloten velden** om de lijst met alle uitgesloten velden te zien. In dit deelvenster kunt u uitgesloten velden weer toevoegen.

## <a name="edit-a-merged-field"></a>Een samengevoegd veld bewerken

1.  Selecteer een samengevoegd veld.

1.  Selecteer **Meer weergeven** en kies **Bewerken**.

1.  Geef op hoe u de velden wilt combineren of samenvoegen door een van de drie opties te kiezen:
    - **Belang**: geeft de winnende waarde aan op basis van de mate van belang die voor de deelnemende velden is opgegeven. Dit is de standaard samenvoegingsoptie. Selecteer **Omhoog/omlaag verplaatsen** om de rangorde van belang in te stellen.
    :::image type="content" source="media/importance-merge-option.png" alt-text="De optie Belang in het dialoogvenster voor het samenvoegen van velden."::: 
    - **Meest recente** : geeft de winnende waarde aan op basis van de meest recente. Vereist een datum of een numeriek veld voor elke deelnemende entiteit in het bereik van samenvoegvelden om de recentheid te definiëren.
    :::image type="content" source="media/recency-merge-option.png" alt-text="De optie Recentheid in het dialoogvenster voor het samenvoegen van velden.":::
    - **Minst recente** : geeft de winnende waarde aan op basis van de minst recente. Vereist een datum of een numeriek veld voor elke deelnemende entiteit in het bereik van samenvoegvelden om de recentheid te definiëren.

1.  U kunt meer velden toevoegen om deel te nemen aan het samenvoegproces.

1.  U kunt de naam van het samenvoegveld wijzigen.

1. Selecteer **Gereed** om uw wijzigingen toe te passen.

1. Selecteer **Opslaan** en **Uitvoeren** om de wijzigingen te verwerken. 

## <a name="combine-fields-manually"></a>Velden handmatig combineren

Geef handmatig een samengevoegd kenmerk op.

1. Selecteer **Combineren** op de pagina **Samenvoegen**.

1. Kies de optie **Velden**.

1. Geef het beleid voor de winnende samenvoeging op via het vervolgkeuzemenu **Velden combineren op**.

1. Kies een veld dat u wilt toevoegen. Selecteer **Velden toevoegen** om meer velden te combineren.

1. Geef informatie op voor **Naam** en **Naam van uitvoerveld**.

1. Selecteer **Gereed** om de wijzigingen toe te passen.

1. Selecteer **Opslaan** en **Uitvoeren** om de wijzigingen te verwerken. 

## <a name="combine-a-group-of-fields"></a>Een groep velden combineren

Behandel een groep velden als een enkele eenheid. Bijvoorbeeld wanneer onze records de velden Address1, Address2, City, State en Zip bevatten. Dan willen we waarschijnlijk niet het veld Address2 van een ander record samenvoegen, vanuit de gedachte dat dit onze gegevens completer zou maken

1. Selecteer **Combineren** op de pagina **Samenvoegen**.

1. Kies de optie **Groep velden**.

1. Geef het beleid voor de winnende samenvoeging op via het vervolgkeuzemenu **Groepen rangschikken op**.

1. Selecteer **Toevoegen** en kies of u meer velden of extra groepen aan de velden wilt toevoegen.

1. Geef een **Naam** en een **Uitvoernaam** op voor elk gecombineerd veld.

1. Geef een **Naam** op voor de groep velden. 

1. Selecteer **Gereed** om de wijzigingen toe te passen.

1. Selecteer **Opslaan** en **Uitvoeren** om de wijzigingen te verwerken.

## <a name="change-the-order-of-fields"></a>De volgorde van velden wijzigen

Sommige entiteiten bevatten meer details dan andere. Als een entiteit de nieuwste gegevens over een veld bevat, kunt u deze prioriteit geven boven andere entiteiten bij het samenvoegen van waarden.

1. Selecteer het samengevoegde veld.
  
1. Selecteer **Meer weergeven** en kies **Bewerken**.

1. Selecteer in het deelvenster **Velden combineren** **Omhoog/omlaag** om de volgorde in te stellen of gebruik slepen en neerzetten om de velden op de gewenste positie te plaatsen.

1. Bevestig de wijziging.

1. Selecteer **Opslaan** en **Uitvoeren** om de wijzigingen te verwerken.

## <a name="configure-customer-id-generation"></a>Het genereren van een unieke klant-id configureren 

Na het configureren van samenvoegvelden, kunt u definiëren hoe u CustomerId-waarden, de unieke klantprofiel-id's, genereert. In de samenvoegstap in het proces van gegevensharmonisatie wordt de unieke klantprofiel-id gegenereerd. De id is de CustomerId in de entiteit *Klant* die het resultaat is van het proces van gegevensharmonisatie. 

De CustomerId in de entiteit Klant is gebaseerd op een hash van de eerste waarde van de niet-null winnende primaire sleutels. Deze sleutels zijn afkomstig van de entiteiten die worden gebruikt in de overeenkomst- en samenvoegfase en worden beïnvloed door de overeenkomstvolgorde. De gegenereerde CustomerID kan dus veranderen wanneer een primaire sleutelwaarde verandert in de primaire entiteit van de matchorder. De waarde van de primaire sleutel vertegenwoordigt dus mogelijk niet altijd dezelfde klant.

Door een stabiele klant-id te configureren, kunt u dat gedrag vermijden.

**Een unieke klant-id configureren**

1. Ga naar **Unify** > **Samenvoegen**.

1. Ga naar het tabblad **Sleutels**. 

1. Houd de muisaanwijzer op de rij **CustomerId** en selecteer de optie **Configureren**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Controle om het genereren van de id aan te passen.":::

1. Selecteer maximaal vijf velden die een unieke klant-id vormen en stabieler zijn. Records die niet overeenkomen met uw configuratie, gebruiken in plaats daarvan een door het systeem geconfigureerde id.  

1. Selecteer **Gereed** en voer het samenvoegproces uit om uw wijzigingen toe te passen.

## <a name="group-profiles-into-households-or-clusters"></a>Groepeer profielen in huishoudens of clusters

Als onderdeel van het configuratieproces voor het genereren van klantprofielen kunt u regels definiëren om gerelateerde profielen in een cluster te groeperen. Er zijn momenteel twee soorten clusters beschikbaar: huishoudelijke en aangepaste clusters. Het systeem kiest automatisch een huishouden met vooraf gedefinieerde regels als de entiteit *Klant* de semantische velden *Person.LastName* en *Location.Address* bevat. U kunt ook een cluster maken met uw eigen regels en voorwaarden, vergelijkbaar met [afstemmingsregels](match-entities.md#define-rules-for-match-pairs).

**Een huishouden of cluster definiëren**

1. Ga naar **Unify** > **Samenvoegen**.

1. Op het tabblad **Samenvoegen** selecteer **Geavanceerd** > **Cluster maken**.

   :::image type="content" source="media/create-cluster.png" alt-text="Besturingselement om een nieuwe cluster te maken.":::

1. Kies tussen een cluster van het type **Huishouden** of **Aangepast**. Als de semantische velden *Person.LastName* en *Location.Address* bestaan in de entiteit *Klant*, wordt automatisch huishouden geselecteerd.

1. Geef een naam op voor het cluster en selecteer **Gereed**.

1. Selecteer het tabblad **Clusters** om het cluster te vinden dat u hebt gemaakt.

1. Geef de regels en voorwaarden op om uw cluster te definiëren.

1. Selecteer **Uitvoeren** om het samenvoegproces uit te voeren en het cluster te maken.

Nadat het samenvoegproces is uitgevoerd, worden de cluster-id's als nieuwe velden toegevoegd aan de entiteit *Klant*.

## <a name="run-your-merge"></a>Uw samenvoeging uitvoeren

Of u kenmerken handmatig samenvoegt of deze laat samenvoegen door het systeem, u kunt altijd uw samenvoeging uitvoeren. Selecteer **Uitvoeren** op de pagina **Samenvoegen** om het proces te starten.

> [!div class="mx-imgBorder"]
> ![Samenvoegen van gegevens opslaan en uitvoeren.](media/configure-data-merge-save-run.png "Samenvoegen van gegevens opslaan en uitvoeren")

Kies **Alleen samenvoegen uitvoeren** als u alleen de uitvoer weerspiegeld wilt zien in de uniforme klantentiteit. Downstreamprocessen worden vernieuwd zoals dat is [gedefinieerd in de vernieuwingsplanning](system.md#schedule-tab).

Kies **Samenvoegen en downstreamprocessen uitvoeren** om het systeem te vernieuwen met uw wijzigingen. Alle processen, inclusief verrijking, segmenten en metingen, worden automatisch opnieuw uitgevoerd. Nadat alle downstreamprocessen zijn voltooid, weerspiegelen de klantprofielen alle wijzigingen die u hebt aangebracht.

Als u meer wijzigingen wilt aanbrengen en de stap opnieuw wilt uitvoeren, kunt u een samenvoeging in uitvoering annuleren. Selecteer **Vernieuwen...** en selecteer **Taak annuleren** in het zijvenster dat wordt weergegeven.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

:::image type="content" source="media/process-detail-path.png" alt-text="Inzoompad om naar procesdetails te gaan vanuit de taakstatuskoppeling.":::

## <a name="next-step"></a>Volgende stap

Configureer [activiteiten](activities.md), [verrijking](enrichment-hub.md) of [relaties](relationships.md) voor meer inzichten over uw klanten.

Als u al activiteiten, een verrijking of segmenten hebt geconfigureerd, worden deze automatisch verwerkt om de nieuwste klantgegevens te gebruiken.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
