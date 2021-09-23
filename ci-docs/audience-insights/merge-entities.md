---
title: Entiteiten samenvoegen in gegevensharmonisatie
description: Voeg entiteiten samen om geharmoniseerde klantprofielen te maken.
ms.date: 09/14/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b038cd3f5b433fedf918d34bbfaf2261e11c5c17
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494313"
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

1.  U kunt extra velden toevoegen die deelnemen aan het samenvoegproces.

1.  U kunt de naam van het samenvoegveld wijzigen.

1. Selecteer **Gereed** om uw wijzigingen toe te passen.

1. Selecteer **Opslaan** en **Uitvoeren** om de wijzigingen te verwerken. 

## <a name="manually-combine-fields"></a>Velden handmatig combineren

Geef handmatig een samengevoegd kenmerk op. 

1. Selecteer op de pagina **Samenvoegen** **Velden combineren**.

1. Geef het beleid voor de winnende samenvoeging op via het vervolgkeuzemenu **Velden combineren op**.

1. Kies een veld dat u wilt toevoegen. Selecteer **Velden toevoegen** om meer velden te combineren.

1. Geef informatie op voor **Naam** en **Naam van uitvoerveld**.

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

De CustomerId in de entiteit Klant is gebaseerd op een hash van de eerste waarde van de niet-null winnende primaire sleutels. Deze sleutels zijn afkomstig van de entiteiten die worden gebruikt in de overeenkomst- en samenvoegfase en worden beïnvloed door de overeenkomstvolgorde.De gegenereerde CustomerID kan dus veranderen wanneer een primaire sleutelwaarde verandert in de primaire entiteit van de matchorder. De waarde van de primaire sleutel vertegenwoordigt daarom mogelijk niet altijd dezelfde klant.

Door een stabiele klant-id te configureren, kunt u dat gedrag vermijden.

**Een unieke klant-id configureren**

1. Ga naar **Unify** > **Samenvoegen**.

1. Selecteer op de pagina **Samenvoegen** het tabblad **Sleutels**. 

1. Houd de muisaanwijzer op de rij **CustomerId** en selecteer de optie **Configureren**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Controle om het genereren van de id aan te passen.":::

1. Selecteer maximaal vijf velden die een unieke klant-id vormen en stabieler zijn. Records die niet overeenkomen met uw configuratie, gebruiken in plaats daarvan een door het systeem geconfigureerde id.  

1. Selecteer **Gereed** en voer het samenvoegproces uit om uw wijzigingen toe te passen.

## <a name="run-your-merge"></a>Uw samenvoeging uitvoeren

Of u kenmerken handmatig samenvoegt of deze laat samenvoegen door het systeem, u kunt altijd uw samenvoeging uitvoeren. Selecteer **Uitvoeren** op de pagina **Samenvoegen** om het proces te starten.

> [!div class="mx-imgBorder"]
> ![Samenvoegen van gegevens opslaan en uitvoeren.](media/configure-data-merge-save-run.png "Samenvoegen van gegevens opslaan en uitvoeren")

Kies **Alleen samenvoegen uitvoeren** als u alleen de uitvoer weerspiegeld wilt zien in de uniforme klantentiteit. Downstreamprocessen worden vernieuwd zoals dat is [gedefinieerd in de vernieuwingsplanning](system.md#schedule-tab).

Kies **Samenvoegen en downstreamprocessen uitvoeren** om het systeem te vernieuwen met uw wijzigingen. Alle processen, inclusief verrijking, segmenten en metingen, worden automatisch opnieuw uitgevoerd. Nadat alle downstreamprocessen zijn voltooid, weerspiegelen de klantprofielen alle wijzigingen die u hebt aangebracht.

Als u meer wijzigingen wilt aanbrengen en de stap opnieuw wilt uitvoeren, kunt u een samenvoeging in uitvoering annuleren. Selecteer **Vernieuwen...** en selecteer **Taak annuleren** in het zijvenster dat wordt weergegeven.

> [!TIP]
> Nadat u het samenvoegingsproces hebt uitgevoerd, selecteert u de processtatus om het deelvenster **Taakdetails** te openen. Het geeft een overzicht van de verwerkingstijd, de laatste verwerkingsdatum, en alle fouten en waarschuwingen in verband met de taak. Selecteer **Details bekijken** om te zien welke entiteiten hebben deelgenomen aan het vergelijkingsproces, of het conflict is opgelost en of de updates met succes zijn gepubliceerd.  
> Er zijn [zes soorten status](system.md#status-types) voor taken/processen. Bovendien zijn de meeste processen [afhankelijk van andere stroomafwaartse processen](system.md#refresh-policies).  
> :::image type="content" source="media/process-detail-path.png" alt-text="Inzoompad om naar procesdetails te gaan vanuit de taakstatuskoppeling.":::

## <a name="next-step"></a>Volgende stap

Configureer [activiteiten](activities.md), [verrijking](enrichment-hub.md) of [relaties](relationships.md) voor meer inzichten over uw klanten.

Als u al activiteiten, een verrijking of segmenten hebt geconfigureerd, worden deze automatisch verwerkt om de nieuwste klantgegevens te gebruiken.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
