---
title: Segmenten in doelgroepinzichten
description: Overzicht van segmenten en hoe u segmenten kunt maken en beheren.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6cb7bd62bf0f61e6dc5811b20e5011e4a086c743
ms.sourcegitcommit: 84283d523a891298fca8aaf629d9f9ab2a1bc067
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2021
ms.locfileid: "6111381"
---
# <a name="segments-overview"></a>Overzicht van segmenten

Met segmenten kunt u uw klanten groeperen op basis van demografische, transactionele of gedragskenmerken. U kunt segmenten gebruiken om promotiecampagnes, verkoopactiviteiten en acties voor klantenondersteuning te targeten om uw zakelijke doelstellingen te bereiken.

Klantprofielen die overeenkomen met de filters van een segmentdefinitie worden aangeduid als *leden* van een segment. Er zijn enkele [servicelimieten](service-limits.md) van toepassing.

## <a name="create-a-new-segment"></a>Een nieuw segment maken

Er zijn meerdere manieren om een nieuw segment te maken: 

- Complex segment met segmentbouwer: [Leeg segment](segment-builder.md#create-a-new-segment)
- Eenvoudige segmenten met één operator: [Snel segment](segment-builder.md#quick-segments)
- Via AI mogelijk gemaakte manier om vergelijkbare klanten te vinden: [Vergelijkbare klanten](find-similar-customer-segments.md)
- Via AI mogelijk gemaakte suggesties op basis van meetcriteria of kenmerken: [Voorgestelde segmenten om meetcriteria te verbeteren](suggested-segments.md)
- Suggesties op basis van activiteiten: [Voorgestelde segmenten op basis van klantactiviteit](suggested-segments-activity.md)

## <a name="manage-existing-segments"></a>Bestaande segmenten beheren

Ga naar de pagina **Segmenten** om al uw opgeslagen segmenten te bekijken en te beheren.

Elk segment wordt weergegeven door een rij met aanvullende informatie over het segment.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Geselecteerd segment met vervolgkeuzelijst met opties en beschikbare opties.":::

De volgende actie is beschikbaar wanneer u een segment selecteert:

- **Bekijk** de segmentdetails, inclusief trend van ledentelling en voorbeeld van segmentleden.
- **Bewerk** het segment om de eigenschappen te wijzigen.
- **Maak een duplicaat** van een segment. U kunt ervoor kiezen om de eigenschappen meteen te bewerken of gewoon het duplicaat op te slaan.
- **Vernieuw** het segment om de nieuwste gegevens op te nemen.
- **Activeer** of **Deactiveer** het segment. Segmenten hebben twee mogelijke statussen: actief of inactief. Deze statussen zijn handig bij het bewerken van een segment. Voor inactieve segmenten bestaat de segmentdefinitie, maar bevat deze nog geen klanten. Wanneer u een segment activeert, verandert de status van 'inactief' in 'actief' en wordt gezocht naar klanten die voldoen aan de segmentdefinitie. Als een [geplande vernieuwing](system.md#schedule-tab) is geconfigureerd, hebben inactieve segmenten de **Status** **Overgeslagen**, wat aangeeft dat er niet eens is geprobeerd te vernieuwen. Wanneer een inactief segment wordt geactiveerd, wordt het vernieuwd en opgenomen in geplande vernieuwingen.
  U kunt ook de functionaliteit **Later plannen** in de vervolgkeuzelisjt **Activeren/Deactiveren** gebruiken om een toekomstige datum en tijd op te geven voor activering en deactivering van een bepaald segment.
- **Wijzig de naam** van het segment.
- **Download** de lijst van leden als .CSV-bestand.
- **Exports beheren** om exportgerelateerde segmenten te bekijken en te beheren. [Meer informatie over exports.](export-destinations.md)
- **Verwijder** het segment.

## <a name="refresh-segments"></a>Segmenten vernieuwen

U kunt alle segmenten tegelijk vernieuwen door **Alles vernieuwen** te selecteren op de pagina **Segmenten** of u kunt een of meerdere segmenten vernieuwen wanneer u deze selecteert en **Vernieuwen** uit de opties kiezen. U kunt ook een terugkerende vernieuwing configureren via **Beheerder** > **Systeem** > **Schema**.

> [!TIP]
> Er zijn [zes soorten status](system.md#status-types) voor taken/processen. Bovendien zijn de meeste processen [afhankelijk van andere stroomafwaartse processen](system.md#refresh-policies). U kunt de status van een proces selecteren om voortgangsdetails te zien van de volledige taak. Na het selecteren van **Details bekijken** voor een van de taken vindt u aanvullende informatie: verwerkingstijd, de laatste verwerkingsdatum en alle fouten en waarschuwingen die bij de taak horen.

## <a name="export-segments"></a>Segmenten exporteren

U kunt een segment exporteren vanaf de pagina met segmenten of de [pagina met exports](export-destinations.md). 

1. Ga naar de pagina **Segmenten**.

1. Selecteer **Meer weergeven [...]** voor het segment dat u wilt exporteren.

1. Selecteer **Exports beheren** van de vervolgkeuzelijst met acties.

1. De pagina **Exports (preview) voor segment** wordt geopend. U kunt alle geconfigureerde exports zien gegroepeerd op exports die het huidige segment wel of niet bevatten.

   1. Als u het geselecteerde segment aan een export wilt toevoegen, selecteert u de export in de lijst en selecteert u **Segment toevoegen**.

   1. Als u een nieuwe export wilt maken met het geselecteerde segment, selecteert u **Export toevoegen**. Zie [Een nieuwe export instellen](export-destinations.md#set-up-a-new-export) voor meer informatie over het maken van exports..

1. Selecteer **Vorige** om terug te gaan naar de hoofdpagina voor segmenten.

## <a name="view-processing-history-and-segment-members"></a>Verwerkingsgeschiedenis en segmentleden weergeven

U kunt geconsolideerde gegevens over een segment bekijken door de details te controleren.

Selecteer op de pagina **Segmenten** het segment dat u wilt controleren.

Het bovenste deel van de pagina bevat een trendgrafiek waarin wijzigingen in het aantal leden worden gevisualiseerd. Beweeg over gegevenspunten om het aantal leden op een specifieke datum te bekijken.

U kunt het tijdsbereik van de visualisatie bijwerken.

> [!div class="mx-imgBorder"]
> ![Tijdsbereik van segment](media/segment-time-range.png "Tijdsbereik van segment")

Het onderste gedeelte bevat een lijst met de segmentleden.

> [!NOTE]
> Velden die in deze lijst worden weergegeven, zijn gebaseerd op de kenmerken van de entiteiten van uw segment.
>
>De lijst is een voorbeeld van de overeenkomende segmentleden en toont de eerste 100 records van uw segment, zodat u het snel kunt evalueren en indien nodig de definities kunt bekijken. Als u alle overeenkomende records wilt bekijken, moet u [het segment exporteren](export-destinations.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
