---
title: Overzicht van segmenten
description: Overzicht van segmenten en hoe u segmenten kunt maken en beheren.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: 8b2c2f9b84bf8b7f37d1468b871946ecb3e6aa98
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9050941"
---
# <a name="segments-overview"></a>Overzicht van segmenten

Met segmenten kunt u uw klanten groeperen op basis van demografische, transactionele of gedragskenmerken. U kunt segmenten gebruiken om promotiecampagnes, verkoopactiviteiten en acties voor klantenondersteuning te targeten om uw zakelijke doelstellingen te bereiken.

Klantprofielen die overeenkomen met de filters van een segmentdefinitie worden aangeduid als *leden* van een segment. Er zijn enkele [servicelimieten](/dynamics365/customer-insights/service-limits) van toepassing.

## <a name="create-a-new-segment"></a>Een nieuw segment maken

Er zijn meerdere manieren om een nieuw segment te maken: 

# <a name="individual-consumers-b-to-c"></a>[Individuele consumenten (B-to-C)](#tab/b2c)

- Complex segment met segmentbouwer: [Bouw onze eigen](segment-builder.md#create-a-new-segment) 
- Eenvoudige segmenten met één operator: [Snel segment](segment-builder.md#quick-segments) 
- Via AI mogelijk gemaakte manier om vergelijkbare klanten te vinden: [Vergelijkbare klanten](find-similar-customer-segments.md) 
- Via AI mogelijk gemaakte suggesties op basis van meetcriteria of kenmerken: [Voorgestelde segmenten om meetcriteria te verbeteren](suggested-segments.md) 
- Suggesties op basis van activiteiten: [Voorgestelde segmenten op basis van klantactiviteit](suggested-segments-activity.md) 

# <a name="business-accounts-b-to-b"></a>[Zakelijke accounts (B-to-B)](#tab/b2b)

- Complex segment met segmentbouwer: [Bouw onze eigen](segment-builder.md#create-a-new-segment)

---

## <a name="manage-existing-segments"></a>Bestaande segmenten beheren

Ga naar de pagina **Segmenten** om al uw opgeslagen segmenten te bekijken en te beheren.

Elk segment wordt weergegeven door een rij met aanvullende informatie over het segment.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Geselecteerd segment met vervolgkeuzelijst met opties en beschikbare opties." lightbox="media/segments-selected-segment.png":::

De volgende acties zijn beschikbaar wanneer u een segment selecteert:

- **Bekijk** de segmentdetails, inclusief trend van ledentelling en voorbeeld van segmentleden.
- **Download** de lijst van leden als .CSV-bestand.
- **Bewerk** het segment om de eigenschappen te wijzigen.
- **Maak een duplicaat** van een segment. U kunt ervoor kiezen om de eigenschappen meteen te bewerken of het duplicaat op te slaan.
- **Vernieuw** het segment om de nieuwste gegevens op te nemen.
- **Activeer** of **Deactiveer** het segment. Voor inactieve segmenten bestaat de segmentdefinitie, maar bevat deze nog geen klanten. Een actief segment zoekt naar klanten die voldoen aan de segmentdefinitie. Als een [geplande vernieuwing](system.md#schedule-tab) is geconfigureerd, hebben inactieve segmenten de **Status** **Overgeslagen**, wat aangeeft dat er niet eens is geprobeerd te vernieuwen. Wanneer een inactief segment wordt geactiveerd, wordt het vernieuwd en opgenomen in geplande vernieuwingen.
  U kunt ook de functionaliteit **Later plannen** in de vervolgkeuzelisjt **Activeren/Deactiveren** gebruiken om een toekomstige datum en tijd op te geven voor activering en deactivering van een bepaald segment.
- **[Zoek vergelijkbare klanten](find-similar-customer-segments.md)** uit het segment.
- **Wijzig de naam** van het segment.
- **Tag** om [tags te beheren](work-with-tags-columns.md#manage-tags) voor het segment.
- **Download** de lijst van leden als .CSV-bestand.
- **Exports beheren** om exportgerelateerde segmenten te bekijken en te beheren. [Meer informatie over exports.](export-destinations.md)
- **Verwijder** het segment.
- **Kolommen** om de [kolommen aan te passen](work-with-tags-columns.md#customize-columns) die worden weergegeven.
- **Filter** om te [filteren op tags](work-with-tags-columns.md#filter-on-tags).
- **Naam zoeken** om op segmentnaam te zoeken.

## <a name="refresh-segments"></a>Segmenten vernieuwen

U kunt alle segmenten tegelijk vernieuwen door **Alles vernieuwen** te selecteren op de pagina **Segmenten** of u kunt een of meerdere segmenten vernieuwen wanneer u deze selecteert en **Vernieuwen** uit de opties kiezen. U kunt ook een terugkerende vernieuwing configureren via **Beheerder** > **Systeem** > **Schema**. Wanneer een terugkerende vernieuwing is geconfigureerd, zijn de volgende regels van toepassing:

- Alle segmenten met het type **Dynamisch** of **Uitbreiding** worden automatisch vernieuwd in het ingestelde tempo. Nadat het vernieuwen is voltooid, geeft **Status** aan of er problemen waren bij het vernieuwen van het segment. **Laatst vernieuwd** toont een tijdstempel van de meest recente succesvolle vernieuwing. Als er een fout optreedt, selecteert u de fout om details te bekijken van wat er is gebeurd.
- Segmenten met het type **Statisch** worden *niet* automatisch vernieuwd. **Laatst vernieuwd** toont een tijdstempel van de laatste keer dat de statische segmenten handmatig zijn uitgevoerd of vernieuwd.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Segmenten exporteren

U kunt een segment exporteren vanaf de pagina met segmenten of de [pagina met exports](export-destinations.md). 

1. Ga naar de pagina **Segmenten**.

1. Selecteer het verticale weglatingsteken (&vellip;) voor het segment dat u wilt exporteren.

1. Selecteer **Exports beheren** uit de vervolgkeuzelijst met acties.

1. De pagina **Exports (preview) voor segment** wordt geopend. U kunt alle geconfigureerde exports bekijken gegroepeerd op of ze het huidige segment bevatten of niet.

   1. Om het geselecteerde segment aan een export toe te voegen, selecteert u **Bewerken** en selecteert u het corresponderende segment. Sla vervolgens op. In omgevingen voor individuele klanten kunt u in plaats daarvan de export in de lijst selecteren en selecteert u **Segment toevoegen** om hetzelfde resultaat te bereiken.

   1. Als u een nieuwe export wilt maken met het geselecteerde segment, selecteert u **Export toevoegen**. Zie [Een nieuwe export instellen](export-destinations.md#set-up-a-new-export) voor meer informatie over het maken van exports..

1. Selecteer **Vorige** om terug te gaan naar de hoofdpagina voor segmenten.

## <a name="track-usage-of-a-segment"></a>Gebruik van een segment bijhouden

Als u segmenten in apps gebruikt die zijn gebaseerd op dezelfde Microsoft Dataverse-organisatie die is verbonden met Customer Insights, kunt u het gebruik van een segment bijhouden. Voor [Customer Insights-segmenten die worden gebruikt in klantreizen van Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), informeert het systeem u over het gebruik van dat segment.

Bij het bewerken van een segment dat wordt gebruikt binnen de Customer Insights-omgeving, of in een klantreis in Marketing, informeert een banner in de [segmentbouwer](segment-builder.md) u over de afhankelijkheden. U kunt de afhankelijkheidsdetails rechtstreeks vanuit de banner bekijken of door **Gebruik** te selecteren in de segmentbouwer.

Het deelvenster **Segmentgebruik** laat de details van het gebruik van dit segment zien in op Dataverse gebaseerde apps. Voor segmenten die worden gebruikt in klantreizen, vindt u een koppeling om de reis te inspecteren in Marketing waar dit segment wordt gebruikt. Als u toegangsrechten hebt voor de Marketing-app, kunt u daar meer details bekijken.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Zijvenster met details van het segmentgebruik in de segmentbouwer.":::

Het systeem informeert u over het gebruik van een bijgehouden segment wanneer u het probeert te verwijderen. Als het segment dat u gaat verwijderen wordt gebruikt in een klantreis in Marketing, stopt die reis voor alle gebruikers in het segment. Als de reis deel uitmaakt van een marketingcampagne, heeft de verwijdering gevolgen voor die campagne zelf. U kunt het segment echter nog steeds verwijderen, ondanks de waarschuwingen.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Dialoogvenster om het verwijderen van een segment te bevestigen wanneer een segment wordt gebruikt in een Dataverse-toepassing.":::

### <a name="supported-apps"></a>Ondersteunde apps

Het gebruik wordt momenteel bijgehouden in het volgende op Dataverse gebaseerde apps:

- [Klantreizen in Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="view-processing-history-and-segment-members"></a>Verwerkingsgeschiedenis en segmentleden weergeven

U kunt geconsolideerde gegevens over een segment bekijken door de details te controleren.

Selecteer op de pagina **Segmenten** het segment dat u wilt controleren.

Het bovenste deel van de pagina bevat een trendgrafiek waarin wijzigingen in het aantal leden worden gevisualiseerd. Beweeg over gegevenspunten om het aantal leden op een specifieke datum te bekijken.

U kunt het tijdsbereik van de visualisatie bijwerken.

> [!div class="mx-imgBorder"]
> ![Tijdsbereik van segment.](media/segment-time-range.png "Tijdsbereik van segment")

Het onderste gedeelte bevat een lijst met de segmentleden.

> [!NOTE]
> Velden die in deze lijst worden weergegeven, zijn gebaseerd op de kenmerken van de entiteiten van uw segment.
>
>De lijst is een voorbeeld van de overeenkomende segmentleden en toont de eerste 100 records van uw segment, zodat u het snel kunt evalueren en indien nodig de definities kunt bekijken. Als u alle overeenkomende records wilt bekijken, moet u [het segment exporteren](export-destinations.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
