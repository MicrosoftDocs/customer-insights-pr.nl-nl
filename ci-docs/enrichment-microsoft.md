---
title: Klantprofielen verrijken met merk- en interessegegevens van Microsoft
description: Eigendomsgegevens van Microsoft gebruiken om uw klantgegevens te verrijken met affiniteiten en share of voice (aandeel in reclametijd).
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
searchScope:
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 61262980cafdcd130430e200e466ce7da6cc4d07
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953759"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Klantprofielen verrijken met affiniteiten en share of voice (preview)

Eigendomsgegevens van Microsoft gebruiken om uw klantgegevens te verrijken met merkaffiniteiten, interesseaffiniteiten en share of voice (SoV). Deze affiniteiten en SoV zijn gebaseerd op gegevens van mensen met een vergelijkbare demografie als uw klanten. Deze informatie helpt u om uw klanten beter te begrijpen en in te delen op basis van hun affiniteiten of SoV met specifieke merken en interesses.

## <a name="how-we-determine-affinities-and-sov"></a>Hoe worden affiniteiten en SoV bepaald

We gebruiken de online zoekgegevens van Microsoft om affiniteiten en SoV te vinden voor merken en interesses in verschillende demografische segmenten (gedefinieerd op leeftijd, geslacht of locatie). Het online zoekvolume voor een merk of interesse vormt de basis voor het bepalen van de affiniteit of SoV. Elk biedt echter een ander perspectief om uw klanten te begrijpen.

- Affiniteit is een vergelijking tussen demografische segmenten. U kunt deze informatie gebruiken om demografische segmenten te identificeren die de hoogste affiniteit hebben voor een bepaald merk of interesse, in vergelijking met andere segmenten.

- Share of voice is een vergelijking tussen uw geselecteerde merken of interesses. U kunt deze informatie gebruiken om te identificeren welk merk of interesse de hoogste share-of-voice heeft voor een bepaald demografisch segment, in vergelijking met andere merken of interesses die u hebt geselecteerd.

## <a name="affinity-level-and-score"></a>Affiniteitsniveau en score

Op elk verrijkt klantprofiel geven we twee gerelateerde waarden: affiniteitsniveau en affiniteitsscore. Deze waarden helpen u te bepalen hoe sterk de affiniteit is voor het demografische segment van dat profiel, voor een merk of interesse, in vergelijking met andere demografische segmenten.

*Affiniteitsniveau* bestaat uit vier niveaus en *Affiniteitsscore* wordt berekend op een schaal van 100 punten die overeenkomt met de affiniteitsniveaus.

|Affiniteitsniveau |Affiniteitsscore  |
|---------|---------|
|Zeer hoog     | 85-100       |
|Hoog     | 70-84        |
|Gemiddeld     | 35-69        |
|Laag     | 1-34        |

Afhankelijk van de granulariteit waarmee u de affiniteit wilt meten, kunt u het affiniteitsniveau of de score gebruiken. De affiniteitsscore geeft u een nauwkeurigere controle.

## <a name="share-of-voice-sov"></a>Share of voice (SoV)

We berekenen SoV op een schaal van 100 punten. De totale SoV voor alle merken of interesses voor elk verrijkt klantprofiel is totaal 100. In tegenstelling tot affiniteiten, is SoV relatief aan de merken en interesses die je selecteert. De SoV-waarden voor 'Microsoft' kunnen bijvoorbeeld verschillen als de geselecteerde merken ('Microsoft', 'GitHub') versus ('Microsoft', 'LinkedIn') zijn.

## <a name="supported-countriesregions"></a>Ondersteunde landen/regio's

We ondersteunen momenteel de volgende opties voor landen/regio's: Australië, Canada (Engels), Frankrijk, Duitsland, Verenigd Koninkrijk of Verenigde Staten (Engels).

## <a name="configure-the-enrichment"></a>De verrijking configureren

1. Ga naar **Gegevens** > **Verrijking** en selecteer het tabblad **Detecteren**.

   - Om verrijking van merkaffiniteiten en SoV te configureren, selecteert u **Mijn gegevens verrijken** op de tegel **Merken**.

   - Om verrijking van interesse-affiniteiten en SoV te configureren, selecteert u **Mijn gegevens verrijken** op de tegel **Interesses**.

   > [!div class="mx-imgBorder"]
   > ![Tegels Merken en Interesses.](media/BrandsInterest-tile-Hub.png "Tegels Merken en Interesses")

1. Bekijk het overzicht en selecteer **Volgende**.

1. Als u uw land of regio wilt wijzigen, selecteert u **Wijzigen** naast **Land/regio**. Kies in het deelvenster **Land-/regio-instellingen** een [ondersteund land of een ondersteunde regio](#supported-countriesregions) en selecteert u **Toepassen**.

   > [!NOTE]
   > Wanneer u uw eigen merken kiest, geeft het systeem suggesties op basis van het geselecteerde land of de geselecteerde regio. Wanneer u een branche kiest, krijgt u de meest relevante merken of interesses op basis van het geselecteerde land of de geselecteerde regio.

1. Kies maximaal vijf merken of interesses met behulp van een of beide van deze opties:

   - **Branche**: selecteer uw branche in de vervolgkeuzelijst en kies vervolgens uit de topmerken of interesses voor die branche.
   - **Uw eigen keuze maken**: voer een merk of interesse in die relevant is voor uw organisatie en kies vervolgens uit de bijpassende suggesties. Als we geen merk of interesse vermelden waarnaar u op zoek bent, stuur ons dan feedback via de koppeling **Dit voorstellen**.

1. Selecteer **Volgende** en bekijk uw standaardverrijkingsvoorkeuren en werk deze indien nodig bij.

   :::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Schermopname van het venster Verrijkingsvoorkeuren.":::

1. Selecteer **Volgende**.

1. Selecteer de **Klantgegevensset** en kies het profiel of segment dat u wilt verrijken met gegevens van Microsoft. De entiteit *Klant* verrijkt al uw klantprofielen, terwijl een segment alleen klantprofielen in dat segment verrijkt.

1. Selecteer **Volgende**.

1. Wijs uw velden van uw geharmoniseerde klantentiteit toe aan de Microsoft-gegevens.

   > [!NOTE]
   > Er zijn ten minste kenmerken voor de geboortedatum of het geslacht vereist. Land/regio en minimaal plaats (en staat/provincie) of postcode zijn vereist. We raden aan de geboortedatum te converteren naar het type DateTime tijdens het opnemen van gegevens. Als alternatief kan het een tekenreeks zijn in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html)-indeling 'jjjj-MM-dd' of 'jjjj-MM-ddTHH:mm:ss'.

1. Selecteer **Volgende** om de veldtoewijzing te voltooien.

1. Geef een naam op voor de verrijking. De **Naam van uitvoerentiteit** wordt automatisch geselecteerd.

   :::image type="content" source="media/enrichment-interests-summary.png" alt-text="Pagina voor beoordeling van interesses en naamgeving.":::

1. Selecteer **Verrijking opslaan** na het bekijken van uw keuzes.

1. Selecteer **Uitvoeren** om het verrijkingsproces te starten of sluit om terug te keren naar de pagina **Verrijkingen**.

   Bij het verrijken van profielen, verrijken we alle klantprofielen waarvoor we gegevens krijgen voor de geselecteerde merken en interesses, inclusief profielen die zich niet in het geselecteerde land of de geselecteerde regio bevinden. Als u bijvoorbeeld Duitsland hebt geselecteerd, verrijken we profielen in de Verenigde Staten als we gegevens beschikbaar hebben voor de geselecteerde merken en interesses in de Verenigde Staten.

## <a name="enrichment-results"></a>Verrijkingsresultaten

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

:::image type="content" source="media/my-enrichments.png" alt-text="Voorbeeldweergave van resultaten na het uitvoeren van het verrijkingsproces.":::

De resultaten omvatten **Affiniteitsniveau** of **Share of Voice**-grafieken.

De entiteiten die zijn gemaakt op basis van de verrijkingen, staan vermeld onder de groep **Verrijking** in **Gegevens** > **Entiteiten**. Verrijkte data voor merken gaat naar de entiteiten **MerkAffiniteitVanMicrosoft** en **MerkShareOfVoiceVanMicrosoft**. Gegevens voor interesses staan in de entiteiten **InteresseAffiniteitVanMicrosoft** en **InteresseShareOfVoiceVanMicrosoft**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Zie verrijkingsgegevens op de klantenkaart

Merk- en interesse-SoV kunnen ook op individuele klantenkaarten worden weergegeven. Ga naar **Klanten** en selecteer een klantprofiel. Op de klantenkaart vindt u grafieken voor het merk- of de interesse-SoV op basis van mensen in het demografische profiel van die klant.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Klantenkaart met verrijkte gegevens.":::

## <a name="next-steps"></a>Volgende stappen

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
