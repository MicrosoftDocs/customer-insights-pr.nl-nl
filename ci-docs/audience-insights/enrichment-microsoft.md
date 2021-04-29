---
title: Klantprofielen verrijken met gegevens van Microsoft
description: Gebruik bedrijfseigen gegevens van Microsoft om uw klantgegevens te verrijken met merk- en interesseaffiniteiten.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6f19033236190547f68d2b91ec6b32074bf7912a
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896596"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Klantprofielen verrijken met merk- en interesseaffiniteiten (preview)

Gebruik bedrijfseigen gegevens van Microsoft om uw klantgegevens te verrijken met merk- en interesseaffiniteiten. Deze affiniteiten worden bepaald op basis van gegevens van mensen met vergelijkbare demografische gegevens als uw klanten. Deze informatie helpt u om uw klanten beter te begrijpen en te segmenteren op basis van hun affiniteit met specifieke merken en interesses.

Ga in doelgroepinzichten naar **Gegevens** > **Verrijking** om [verrijkingen te configureren en weer te geven](enrichment-hub.md).

Ga naar het tabblad **Ontdekken** en selecteer **Mijn gegevens verrijken** op de tegel **Merken** om de verrijking van merkaffiniteiten te configureren.

Ga naar het tabblad **Ontdekken** en selecteer **Mijn gegevens verrijken** op de tegel **Interesses** om de verrijking van interesseaffiniteiten te configureren.

   > [!div class="mx-imgBorder"]
   > ![Tegels voor merken en interesses](media/BrandsInterest-tile-Hub.png "Tegels voor merken en interesses")

## <a name="how-we-determine-affinities"></a>Hoe we affiniteiten bepalen

We gebruiken de online zoekgegevens van Microsoft om affiniteiten te vinden voor merken en interesses in verschillende demografische segmenten (gedefinieerd door leeftijd, geslacht of locatie). Het online zoekvolume voor een merk of interesse bepaalt hoeveel affiniteit een demografisch segment heeft, vergeleken met andere segmenten, voor dat merk of die interesse. merk of interesse.

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

## <a name="supported-countriesregions"></a>Ondersteunde landen/regio's

We ondersteunen momenteel de volgende opties voor landen/regio's: Australië, Canada (Engels), Frankrijk, Duitsland, Verenigd Koninkrijk of Verenigde Staten (Engels).

Als u een land wilt selecteren, opent u **Verrijking van merken** of **Interesseverrijking** en selecteert u **WIjzigen** naast **Land/regio**. Kies in het deelvenster **Land-/regio-instellingen** een optie en selecteer **Toepassen**.

### <a name="implications-related-to-country-selection"></a>Implicaties met betrekking tot landselectie

- Wanneer u [uw eigen merken kiest](#define-your-brands-or-interests), geeft het systeem suggesties op basis van het geselecteerde land of de geselecteerde regio.

- Wanneer u [een branche kiest](#define-your-brands-or-interests), krijgt u de meest relevante merken of interesses op basis van het geselecteerde land of de geselecteerde regio.

- Wanneer u [profielen verrijkt](#refresh-enrichment), verrijken we alle klantprofielen waarvoor we gegevens krijgen voor de geselecteerde merken en interesses. Inclusief profielen die zich niet in het geselecteerde land of de geselecteerde regio bevinden. Als u bijvoorbeeld Duitsland hebt geselecteerd, verrijken we profielen in de Verenigde Staten als we gegevens beschikbaar hebben voor de geselecteerde merken en interesses in de Verenigde Staten.

## <a name="configure-enrichment"></a>Verrijking configureren

Een begeleide ervaring helpt u bij het configureren van de verrijkingen. 

### <a name="define-your-brands-or-interests"></a>Uw merken of interesses definiëren

Selecteer een van de volgende opties:

- **Branche**: het systeem identificeert de topmerken of interesses die relevant zijn voor uw branche en verrijkt uw klantgegevens hiermee.
- **Uw eigen keuze maken**: selecteer maximaal vijf items uit de lijst met merken of interesses die het meest relevant zijn voor uw organisatie.

Als u een merk of interesse wilt toevoegen, voert u dit in het invoerveld in om suggesties te krijgen op basis van overeenkomende termen. Als we geen merk of interesse vermelden waarnaar u op zoek bent, stuur ons dan feedback via de koppeling **Dit voorstellen**.

### <a name="review-enrichment-preferences"></a>Verrijkingsvoorkeuren beoordelen

Beoordeel uw standaardverrijkingsvoorkeuren en werk deze indien nodig bij.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Schermopname van het venster Verrijkingsvoorkeuren.":::

### <a name="select-entity-to-enrich"></a>Te verrijken entiteit selecteren

Selecteer **Verrijkte entiteit** en kies de gegevensset die u wilt verrijken met bedrijfsgegevens van Microsoft. U kunt de entiteit Klant selecteren om al uw klantprofielen te verrijken of een segmententiteit selecteren om alleen klantprofielen in dat segment te verrijken.

### <a name="map-your-fields"></a>Uw velden toewijzen

Wijs velden van uw geharmoniseerde klantentiteit toe om het demografische segment te definiëren dat u door het systeem wilt laten gebruiken om uw klantgegevens te verrijken. Wijs land/regio toe en ten minste geboortedatum of genderkenmerken. Bovendien moet u ten minste een plaats (en staat/provincie) of postcode toewijzen. Selecteer **Bewerken** om de toewijzing van de velden te definiëren en selecteer **Toepassen** wanneer u klaar bent. Selecteer **Opslaan** om de veldtoewijzing te voltooien.

De volgende indelingen en waarden worden ondersteund. Waarden zijn niet hoofdlettergevoelig:

- **Geboortedatum**: we raden aan om de geboortedatum te converteren naar het type DateTime tijdens het opnemen van gegevens. Als alternatief kan het een tekenreeks zijn in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html)-indeling 'jjjj-MM-dd' of 'jjjj-MM-dd THH: mm: ssZ'.
- **Geslacht**: Man, Vrouw, Onbekend
- **Postcode**: vijfcijferige postcodes voor de VS, standaard postcode overal elders
- **Plaats**: plaatsnaam in het Engels
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

> [!TIP]
> Er zijn [zes soorten status](system.md#status-types) voor taken/processen. Bovendien zijn de meeste processen [afhankelijk van andere stroomafwaartse processen](system.md#refresh-policies). U kunt de status van een proces selecteren om voortgangsdetails te zien van de volledige taak. Na het selecteren van **Details bekijken** voor een van de taken vindt u aanvullende informatie: verwerkingstijd, de laatste verwerkingsdatum en alle fouten en waarschuwingen die bij de taak horen.

## <a name="enrichment-results"></a>Verrijkingsresultaten

Na het uitvoeren van het verrijkingsproces gaat u naar **Mijn verrijkingen** om het totale aantal verrijkte klanten en een uitsplitsing van merken of interesses in de verrijkte klantprofielen te bekijken.

:::image type="content" source="media/my-enrichments.png" alt-text="Voorbeeldweergave van resultaten na het uitvoeren van het verrijkingsproces":::

Bekijk de verrijkte gegevens door **Verrijkte gegevens weergeven** te selecteren in de grafiek. Verrijkte gegevens voor merken gaan naar de entiteit **BrandAffinityFromMicrosoft**. Gegevens voor interesses bevinden zich in de entiteit **InterestAffinityFromMicrosoft**. U vindt deze entiteiten ook in de groep **Verrijking** in **Gegevens** > **Entiteiten**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Zie verrijkingsgegevens op de klantenkaart

Merk- en interesse-affiniteiten kunnen ook worden bekeken op individuele klantenkaarten. Ga naar **Klanten** en selecteer een klantprofiel. Op de klantkaart vindt u grafieken voor de merken of interesses waarvoor mensen in het demografische profiel van die klant affiniteit hebben.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Klantenkaart met verrijkte gegevens":::

## <a name="next-steps"></a>Volgende stappen

Bouw voort op uw verrijkte klantgegevens. U kunt [Segmenten](segments.md) en [Maatregelen](measures.md) maken en [de gegevens zelfs exporteren](export-destinations.md) om uw klanten gepersonaliseerde ervaringen te bieden.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
