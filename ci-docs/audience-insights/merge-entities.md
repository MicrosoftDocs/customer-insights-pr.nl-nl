---
title: Entiteiten samenvoegen in gegevensharmonisatie
description: Voeg entiteiten samen om geharmoniseerde klantprofielen te maken.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 24b523786158ff36c314601846ee25ea64cfabbe
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650128"
---
# <a name="merge-entities"></a>Entiteiten samenvoegen

De samenvoegingsfase is de laatste fase in het proces voor gegevensharmonisatie. Het doel is het afstemmen van conflicterende gegevens. Voorbeelden van conflicterende gegevens kunnen een klantnaam zijn die in twee van uw gegevenssets is gevonden, maar in elk een beetje anders verschijnt ("Grant Marshall" versus "Grant Marshal"), of een telefoonnummer met een andere indeling(617-803-091X versus 617803091X). Het samenvoegen van die conflicterende gegevenspunten gebeurt op een kenmerk-per-kenmerkbasis.

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

1. Selecteer het samengevoegde veld.
  
1. Selecteer **Meer weergeven** en kies **Uitsluiten**.

1. Bevestig de uitsluiting.

1. Selecteer **Opslaan** en **Uitvoeren** om de wijzigingen te verwerken. 

Selecteer op de pagina **Samenvoegen** **Uitgesloten velden** om de lijst met alle uitgesloten velden te zien. In dit deelvenster kunt u uitgesloten velden weer toevoegen.

## <a name="manually-combine-fields"></a>Velden handmatig combineren

Geef handmatig een samengevoegd kenmerk op. 

1. Selecteer op de pagina **Samenvoegen** **Velden combineren**.

1. Geef informatie op voor **Naam** en **Naam van uitvoerveld**.

1. Kies een veld dat u wilt toevoegen. Selecteer **Velden toevoegen** om meer velden te combineren.

1. Bevestig de uitsluiting.

1. Selecteer **Opslaan** en **Uitvoeren** om de wijzigingen te verwerken. 

## <a name="change-the-order-of-fields"></a>De volgorde van velden wijzigen

Sommige entiteiten bevatten meer details dan andere. Als een entiteit de nieuwste gegevens over een veld bevat, kunt u deze prioriteit geven boven andere entiteiten bij het samenvoegen van waarden.

1. Selecteer het samengevoegde veld.
  
1. Selecteer **Meer weergeven** en kies **Bewerken**.

1. Selecteer in het deelvenster **Velden combineren** **Omhoog/omlaag** om de volgorde in te stellen of gebruik slepen en neerzetten om de velden op de gewenste positie te plaatsen.

1. Bevestig de wijziging.

1. Selecteer **Opslaan** en **Uitvoeren** om de wijzigingen te verwerken.

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
