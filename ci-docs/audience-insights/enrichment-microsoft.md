---
title: Klantprofielen verrijken met gegevens van Microsoft
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
ms.openlocfilehash: 12704ec46832e9463e6115db6c4df64e72bf4f97
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2022
ms.locfileid: "8372667"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Klantprofielen verrijken met affiniteiten en share of voice (preview)

Eigendomsgegevens van Microsoft gebruiken om uw klantgegevens te verrijken met merkaffiniteiten, interesseaffiniteiten en share of voice (SoV). Deze affiniteiten en SoV zijn gebaseerd op gegevens van mensen met een vergelijkbare demografie als uw klanten. Deze informatie helpt u om uw klanten beter te begrijpen en in te delen op basis van hun affiniteiten of SoV met specifieke merken en interesses.

Ga in doelgroepinzichten naar **Gegevens** > **Verrijking** om [verrijkingen te configureren en weer te geven](enrichment-hub.md).

Om verrijking van merkaffiniteiten en SoV te configureren, gaat u naar het tabblad **Ontdekken** en selecteert u **Verrijk mijn gegevens** op de tegel **Merken**.

Om verrijking van interesse-affiniteiten en SoV te configureren, gaat u naar het tabblad **Ontdekken** en selecteert u **Verrijk mijn gegevens** op de tegel **Interesses**.

   > [!div class="mx-imgBorder"]
   > ![Tegels Merken en Interesses.](media/BrandsInterest-tile-Hub.png "Tegels Merken en Interesses")

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

Als u een land of regio wilt selecteren, opent u **Verrijking met merken** of **Verrijking met interesses** en selecteert u **Wijzigen** naast **Land/Regio**. Kies in het deelvenster **Land-/regio-instellingen** een optie en selecteer **Toepassen**.

### <a name="implications-related-to-country-selection"></a>Implicaties met betrekking tot landselectie

- Wanneer u [uw eigen merken kiest](#define-your-brands-or-interests), geeft het systeem suggesties op basis van het geselecteerde land of de geselecteerde regio.

- Wanneer u [een branche kiest](#define-your-brands-or-interests), krijgt u de meest relevante merken of interesses op basis van het geselecteerde land of de geselecteerde regio.

- Bij het [verrijken van profielen](#refresh-enrichment), verrijken we alle klantprofielen waarvoor we gegevens krijgen voor de geselecteerde merken en interesses, inclusief profielen die zich niet in het geselecteerde land of de geselecteerde regio bevinden. Als u bijvoorbeeld Duitsland hebt geselecteerd, verrijken we profielen in de Verenigde Staten als we gegevens beschikbaar hebben voor de geselecteerde merken en interesses in de Verenigde Staten.

## <a name="configure-enrichment"></a>Verrijking configureren

Een begeleide ervaring helpt u bij het configureren van de verrijkingen. 

### <a name="define-your-brands-or-interests"></a>Uw merken of interesses definiëren

Kies maximaal vijf merken of interesses met behulp van een of beide van deze opties:

- **Branche**: selecteer uw branche in de vervolgkeuzelijst en kies vervolgens uit de topmerken of interesses voor die branche.
- **Uw eigen keuze maken**: voer een merk of interesse in die relevant is voor uw organisatie en kies vervolgens uit de bijpassende suggesties. Als we geen merk of interesse vermelden waarnaar u op zoek bent, stuur ons dan feedback via de koppeling **Dit voorstellen**.

### <a name="review-enrichment-preferences"></a>Verrijkingsvoorkeuren beoordelen

Beoordeel uw standaardverrijkingsvoorkeuren en werk deze indien nodig bij.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Schermopname van het venster Verrijkingsvoorkeuren.":::

### <a name="select-entity-to-enrich"></a>Te verrijken entiteit selecteren

Selecteer **Verrijkte entiteit** en kies de gegevensset die u wilt verrijken met gegevens van Microsoft. U kunt de entiteit Klant selecteren om al uw klantprofielen te verrijken of een segmententiteit selecteren om alleen klantprofielen in dat segment te verrijken.

### <a name="map-your-fields"></a>Uw velden toewijzen

Wijs velden van uw geharmoniseerde klantentiteit toe om het demografische segment te definiëren dat u door het systeem wilt laten gebruiken om uw klantgegevens te verrijken. Wijs land/regio toe en ten minste geboortedatum of genderkenmerken. Bovendien moet u ten minste een plaats (en staat/provincie) of postcode toewijzen. Selecteer **Bewerken** om de toewijzing van de velden te definiëren en selecteer **Toepassen** wanneer u klaar bent. Selecteer **Opslaan** om de veldtoewijzing te voltooien.

De volgende indelingen en waarden worden ondersteund (waarden zijn niet hoofdlettergevoelig):

- **Geboortedatum**: we raden aan om de geboortedatum te converteren naar het type DateTime tijdens het opnemen van gegevens. Als alternatief kan het een tekenreeks zijn in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html)-indeling 'jjjj-MM-dd' of 'jjjj-MM-ddTHH:mm:ss'.
- **Geslacht**: Man, Vrouw, Onbekend.
- **Postcode**: vijfcijferige postcodes voor Verenigde Staten, standaard postcode overal elders.
- **Plaats**: plaatsnaam in het Engels.
- **Staat/provincie**: afkorting van twee letters voor de VS en Canada. Afkorting van twee of drie letters voor Australië. Niet van toepassing op Frankrijk, Duitsland of het VK.
- **Land/regio**:

  - VS: Verenigde Staten van Amerika, Verenigde Staten, VS, VS, Amerika
  - CA: Canada, CA
  - GB: Verenigd Koninkrijk, VK, Groot-Brittannië, GB, Verenigd Koninkrijk van Groot-Brittannië en Noord-Ierland, Verenigd Koninkrijk van Groot-Brittannië
  - AU: Australië, AU, Gemenebest van Australië
  - FR: Frankrijk, FR, Franse Republiek
  - DE: Duitsland, Duits, Deutschland, Allemagne, DE, Federale Republiek Duitsland, Republiek Duitsland

## <a name="review-and-name-the-enrichment"></a>De verrijking bekijken en een naam geven

Tot slot gaat u de informatie bekijken en een naam voor de verrijking opgeven.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Pagina voor beoordeling van interesses en naamgeving.":::

## <a name="refresh-enrichment"></a>Verrijking vernieuwen

Voer de verrijking uit na het configureren van merken, interesses en de veldtoewijzing voor demografische gegevens. Start het proces door **Uitvoeren** te selecteren op de configuratiepagina voor merken of interesses. Bovendien kunt u het systeem de verrijking automatisch laten uitvoeren als onderdeel van een geplande vernieuwing.

Afhankelijk van de omvang van uw klantgegevens kan het enkele minuten duren voordat een verrijking is voltooid.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Verrijkingsresultaten

Na het uitvoeren van het verrijkingsproces gaat u naar **Mijn verrijkingen** om het totale aantal verrijkte klanten en een uitsplitsing van merken of interesses in de verrijkte klantprofielen te bekijken.

:::image type="content" source="media/my-enrichments.png" alt-text="Voorbeeldweergave van resultaten na het uitvoeren van het verrijkingsproces.":::

U vindt een grafiek met het aantal verrijkte klantprofielen in de loop van de tijd en voorbeelden van de verrijkte entiteiten. Bekijk de verrijkte gegevens door **Bekijk meer** in de grafieken **Affiniteitsniveau** of **Share of Voice** te selecteren. Verrijkte data voor merken gaat naar de entiteiten **MerkAffiniteitVanMicrosoft** en **MerkShareOfVoiceVanMicrosoft**. Gegevens voor interesses staan in de entiteiten **InteresseAffiniteitVanMicrosoft** en **InteresseShareOfVoiceVanMicrosoft**. U vindt deze entiteiten ook in de groep **Verrijking** in **Gegevens** > **Entiteiten**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Zie verrijkingsgegevens op de klantenkaart

Merk- en interesse-SoV kunnen ook op individuele klantenkaarten worden weergegeven. Ga naar **Klanten** en selecteer een klantprofiel. Op de klantenkaart vindt u grafieken voor het merk- of de interesse-SoV op basis van mensen in het demografische profiel van die klant.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Klantenkaart met verrijkte gegevens.":::

## <a name="next-steps"></a>Volgende stappen

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
