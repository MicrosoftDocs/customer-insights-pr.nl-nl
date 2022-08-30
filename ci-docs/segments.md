---
title: Overzicht van segmenten
description: Overzicht van segmenten en hoe u segmenten kunt maken en beheren.
ms.date: 08/12/2022
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
ms.openlocfilehash: d4de3a6af6bc7d54305a23e3fbd3cc95d464d352
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304789"
---
# <a name="segments-overview"></a>Overzicht van segmenten

Met segmenten kunt u uw klanten groeperen op basis van demografische, transactionele of gedragskenmerken. U kunt segmenten gebruiken om promotiecampagnes, verkoopactiviteiten en acties voor klantenondersteuning te targeten om uw zakelijke doelstellingen te bereiken.

Klant- of contactpersoonprofielen die overeenkomen met de filters van een segmentdefinitie worden aangeduid als *leden* van een segment. Er zijn enkele [servicelimieten](/dynamics365/customer-insights/service-limits) van toepassing.

## <a name="create-a-segment"></a>Een segment maken

Kies hoe u een segment maakt op basis van uw doelgroep.

# <a name="individual-consumers-b-to-c"></a>[Individuele consumenten (B-to-C)](#tab/b2c)

- Complexe segmenten met segmentbouwer: [Uw eigen segmenten bouwen](segment-builder.md)
- Eenvoudige segmenten met één operator: [Snel segment](segment-quick.md)
- Via AI mogelijk gemaakte manier om vergelijkbare klanten te vinden: [Vergelijkbare klanten](find-similar-customer-segments.md)
- Via AI mogelijk gemaakte suggesties op basis van metingen of kenmerken: [Voorgestelde segmenten op basis van metingen](suggested-segments.md)
- Suggesties op basis van activiteiten: [Voorgestelde segmenten op basis van klantactiviteit](suggested-segments-activity.md)

# <a name="business-accounts-b-to-b"></a>[Zakelijke accounts (B-to-B)](#tab/b2b)

Segment van accounts of segment van contactpersonen (preview) met segmentbuilder: [Bouw uw eigen](segment-builder.md)

> [!NOTE]
> De meeste exportbestemmingen vereisen contactpersoongegevens voor marketingdoeleinden. Maak daarom segmenten van contactpersonen die u voor die exports kunt gebruiken.

---

## <a name="manage-existing-segments"></a>Bestaande segmenten beheren

Ga naar de pagina **Segmenten** om de segmenten te bekijken die u hebt gemaakt, hun status en toestand, en de laatste keer dat de gegevens zijn vernieuwd. U kunt de lijst met segmenten sorteren op elke kolom of het zoekvak gebruiken om het segment te vinden dat u wilt beheren.

> [!TIP]
> In B2B-omgevingen geeft de kolom **Doelgroeptype** aan of een segment is gebaseerd op accounts of contactpersonen.

Selecteer een segment om beschikbare acties te bekijken.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Geselecteerd segment met vervolgkeuzelijst met opties en beschikbare opties." lightbox="media/segments-selected-segment.png":::

- [**Bekijk**](#view-segment-details) de segmentdetails, zoals trend van ledentelling en een voorbeeld van segmentleden.
- **Download** de lijst van leden als .CSV-bestand.
- **Bewerk** het segment om de eigenschappen te wijzigen.
- **Maak een duplicaat** van een segment. U kunt ervoor kiezen om de eigenschappen meteen te bewerken of het duplicaat op te slaan.
- [**Vernieuw**](#refresh-segments) het segment om de nieuwste gegevens op te nemen.
- **Activeer** of **Deactiveer** het segment. Inactieve segmenten worden niet vernieuwd gedurende een [geplande vernieuwing](schedule-refresh.md) en hebben de **Status** **Overgeslagen**, wat aangeeft dat er niet eens is geprobeerd te vernieuwen. Actieve segmenten worden vernieuwd op basis van hun type: statisch of dynamisch.
- Selecteer **Statisch maken** of **Dynamisch maken** voor het segmenttype. Statische segmenten moeten handmatig worden vernieuwd. Dynamische segmenten worden automatisch vernieuwd tijdens systeemvernieuwingen.
- [**Zoek vergelijkbare klanten**](find-similar-customer-segments.md) uit het segment.
- **Wijzig de naam** van het segment.
- **Tag** om [tags te beheren](work-with-tags-columns.md#manage-tags) voor het segment.
- Selecteer [**Exports beheren**](#export-segments) om exportgerelateerde segmenten te bekijken en te beheren. [Meer informatie over exports.](export-destinations.md)
- **Verwijder** het segment.
- **Kolommen** om de [kolommen aan te passen](work-with-tags-columns.md#customize-columns) die worden weergegeven.
- **Filter** om te [filteren op tags](work-with-tags-columns.md#filter-on-tags).
- **Naam zoeken** om op segmentnaam te zoeken.

## <a name="view-segment-details"></a>Segmentdetails bekijken

Selecteer op de pagina **Segmenten** een segment om de verwerkingsgeschiedenis en segmentleden te bekijken.

Het bovenste deel van de pagina bevat een trendgrafiek waarin wijzigingen in het aantal leden worden gevisualiseerd. Beweeg over gegevenspunten om het aantal leden op een specifieke datum te bekijken. Wijzig het tijdsbereik van de visualisatie.

:::image type="content" source="media/segment-time-range.png" alt-text="Tijdsbereik van segment.":::

Het onderste gedeelte bevat een lijst met de segmentleden.

> [!NOTE]
> Velden die in deze lijst worden weergegeven, zijn gebaseerd op de kenmerken van de entiteiten van uw segment.
>
> De lijst is een voorbeeld van de overeenkomende segmentleden en toont de eerste 100 records van uw segment, zodat u het snel kunt evalueren en indien nodig de definities kunt bekijken. Als u alle overeenkomende records wilt zien, selecteert u **Meer bekijken**, waarmee de pagina [**Entiteiten**](entities.md) wort geopend of [het segment geëxporteerd](export-destinations.md).

## <a name="refresh-segments"></a>Segmenten vernieuwen

Segmenten kunnen volgens een automatische planning worden vernieuwd of kunnen op aanvraag handmatig worden vernieuwd. Als u een of meer segmenten handmatig wilt vernieuwen, selecteert u ze en kiest u **Vernieuwen**.

Om [een automatische vernieuwing te plannen](schedule-refresh.md), gaat u naar **Beheerder** > **Systeem** > **Planning**. De volgende regels zijn van toepassing:

- Alle segmenten met het type **Dynamisch** of **Uitbreiding** worden automatisch vernieuwd in het ingestelde tempo. Nadat de vernieuwing is voltooid, geeft **Status** aan of er problemen waren bij het vernieuwen van het segment. **Laatst vernieuwd** toont een tijdstempel van de meest recente succesvolle vernieuwing. Als er een fout optreedt, selecteert u de fout om details te bekijken van wat er is gebeurd.
- Segmenten met het type **Statisch** worden *niet* automatisch vernieuwd. **Laatst vernieuwd** toont een tijdstempel van de laatste keer dat het statische segment handmatig is uitgevoerd of vernieuwd.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Segmenten exporteren

Exporteer segmenten naar andere apps om de gegevens verder te gebruiken. Exporteer een segment vanaf de pagina met segmenten of de [pagina met exports](export-destinations.md).

1. Ga naar de pagina **Segmenten** en selecteer het segment dat u wilt exporteren.

1. Selecteer **Exports beheren**. De pagina **Exports (preview) voor segment** wordt geopend. Geef alle geconfigureerde exports weer die zijn gegroepeerd op het gegeven of ze het huidige segment bevatten of niet.

   1. Om het geselecteerde segment aan een export toe te voegen, selecteert u **Bewerken** en selecteert u het corresponderende segment. Sla vervolgens op. In omgevingen voor individuele klanten selecteert u de export in de lijst en selecteert u **Segment toevoegen** om hetzelfde resultaat te bereiken.

   1. Als u een nieuwe export wilt maken met het geselecteerde segment, selecteert u **Export toevoegen**. Zie [Een nieuwe export instellen](export-destinations.md#set-up-a-new-export) voor meer informatie over het maken van exports..

1. Selecteer **Vorige** om terug te gaan naar de hoofdpagina voor segmenten.

## <a name="track-usage-of-a-segment"></a>Gebruik van een segment bijhouden

Als u segmenten in apps gebruikt die zijn gebaseerd op dezelfde Microsoft Dataverse-organisatie die is verbonden met Customer Insights, kunt u het gebruik van een segment bijhouden. Voor [Customer Insights-segmenten die worden gebruikt in klantreizen van Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), informeert het systeem u over het gebruik van dat segment.

Bij het bewerken van een segment dat wordt gebruikt binnen de Customer Insights-omgeving, of in een klantreis in Marketing, informeert een banner in de [segmentbouwer](segment-builder.md) u over de afhankelijkheden. Inspecteer de afhankelijkheidsdetails rechtstreeks vanuit de banner of door **Gebruik** te selecteren in de segmentbouwer.

Het deelvenster **Segmentgebruik** laat de details van het gebruik van dit segment zien in op Dataverse gebaseerde apps. Voor segmenten die worden gebruikt in klantreizen, vindt u een koppeling om de reis te inspecteren in Marketing waar dit segment wordt gebruikt. Als u toegangsrechten hebt voor de Marketing-app, kunt u daar meer details bekijken.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Zijvenster met details van het segmentgebruik in de segmentbouwer.":::

Het systeem informeert u over het gebruik van een bijgehouden segment wanneer u het probeert te verwijderen. Als het segment dat u gaat verwijderen wordt gebruikt in een klantreis in Marketing, stopt die reis voor alle gebruikers in het segment. Als de reis deel uitmaakt van een marketingcampagne, heeft de verwijdering gevolgen voor die campagne zelf. U kunt het segment echter nog steeds verwijderen, ondanks de waarschuwingen.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Dialoogvenster om het verwijderen van een segment te bevestigen wanneer een segment wordt gebruikt in een Dataverse-toepassing.":::

### <a name="supported-apps"></a>Ondersteunde apps

Het gebruik wordt momenteel bijgehouden in het volgende op Dataverse gebaseerde apps:

- [Klantreizen in Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

[!INCLUDE [footer-include](includes/footer-banner.md)]
