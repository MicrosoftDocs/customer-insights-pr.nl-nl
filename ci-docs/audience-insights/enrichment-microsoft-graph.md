---
title: Klantprofielen verrijken met Microsoft Graph
description: Gebruik eigen gegevens uit de Microsoft Graph om uw klantgegevens te verrijken met merk- en interesseaffiniteiten.
ms.date: 09/28/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4f93a2337815f76b98185ecb3755e08443031748
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405477"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Klantprofielen verrijken met merk- en interesseaffiniteiten (preview)

Gebruik eigen gegevens uit de Microsoft Graph om uw klantgegevens te verrijken met merk- en interesseaffiniteiten. Deze affiniteiten worden bepaald op basis van gegevens van mensen met vergelijkbare demografische gegevens als uw klanten. Deze informatie helpt u om uw klanten beter te begrijpen en te segmenteren op basis van hun affiniteit met specifieke merken en interesses.

Ga in doelgroepinzichten naar **Gegevens** > **Verrijking** om [verrijkingen te configureren en weer te geven](enrichment-hub.md).

Ga naar het tabblad **Ontdekken** en selecteer **Mijn gegevens verrijken** op de tegel **Merken** om de verrijking van merkaffiniteiten te configureren.

Ga naar het tabblad **Ontdekken** en selecteer **Mijn gegevens verrijken** op de tegel **Interesses** om de verrijking van interesseaffiniteiten te configureren.

   > [!div class="mx-imgBorder"]
   > ![Tegels voor merken en interesses](media/BrandsInterest-tile-Hub.png "Tegels voor merken en interesses")

## <a name="about-microsoft-graph"></a>Over Microsoft Graph

We gebruiken online zoekgegevens van de Microsoft Graph om affiniteiten te vinden voor merken en interesses in verschillende demografische segmenten (gedefinieerd door leeftijd, geslacht of locatie). Het online zoekvolume voor een merk of interesse bepaalt hoeveel affiniteit een demografisch segment heeft, vergeleken met andere segmenten, voor dat merk of die interesse.

[Meer informatie over Microsoft Graph](https://docs.microsoft.com/graph/overview).

## <a name="affinity-score-and-confidence"></a>Affiniteitsscore en vertrouwen

De **affiniteitsscore** wordt berekend op een schaal van 100 punten, waarbij 100 het segment vertegenwoordigt dat de hoogste affiniteit heeft voor een merk of interesse.

Het **affiniteitsvertrouwen** wordt ook berekend op een 100-puntsschaal. Het geeft het vertrouwen van het systeem aan dat een segment affiniteit heeft met het merk of de interesse. Het betrouwbaarheidsniveau is gebaseerd op de segmentgrootte en de granulariteit van het segment. De segmentgrootte wordt bepaald door de hoeveelheid gegevens die we voor een bepaald segment hebben. Segmentgranulariteit wordt bepaald door het aantal kenmerken (leeftijd, geslacht, locatie) dat beschikbaar is in een profiel.

We normaliseren de scores voor uw gegevensset niet. Bijgevolg ziet u mogelijk niet alle mogelijke waarden voor de affiniteitsscore voor uw gegevensset. Er is bijvoorbeeld mogelijk geen verrijkt klantprofiel met affiniteitsscore 100 in uw gegevens. Dat is mogelijk als er geen klanten bestaan in het demografische segment dat 100 heeft gescoord voor een bepaald merk of interesse.

> [!TIP]
> Als u [segmenten maakt](segments.md) met behulp van affiniteitsscores, bekijk dan de verdeling van affiniteitsscores voor uw gegevensset voordat u beslist over de juiste scoredrempels. De affiniteitsscore 10 kan bijvoorbeeld als significant worden beschouwd in een gegevensset die een hoogste affiniteitsscore van 25 heeft voor een bepaald merk of interesse.

## <a name="supported-countriesregions"></a>Ondersteunde landen/regio's

We ondersteunen momenteel de volgende opties voor landen/regio's: Australië, Canada (Engels), Frankrijk, Duitsland, Verenigd Koninkrijk of Verenigde Staten (Engels).

Als u een land wilt selecteren, opent u **Verrijking van merken** of **Interesseverrijking** en selecteert u **WIjzigen** naast **Land/regio**. Kies in het deelvenster **Land-/regio-instellingen** een optie en selecteer **Toepassen**.

### <a name="implications-related-to-country-selection"></a>Implicaties met betrekking tot landselectie

- Wanneer [u uw eigen merken kiest](#define-your-brands-or-interests), zullen wij suggesties doen op basis van het geselecteerde land of de geselecteerde regio.

- Bij [het kiezen van een branche](#define-your-brands-or-interests), zullen we de meest relevante merken of interesses identificeren op basis van het geselecteerde land/regio.

- Als bij het [toewijzen van uw velden](#map-your-fields) het veld Land/regio niet wordt toegewezen, gebruiken we Microsoft Graph-gegevens over het geselecteerde land of de geselecteerde regio om uw klantprofielen te verrijken. We zullen die selectie ook gebruiken omklantprofielen te verrijken waarvoor geen land-/regiogegevens beschikbaar zijn.

- Bij het [verrijken van profielen](#refresh-enrichment) verrijken we alle klantprofielen waarvoor we Microsoft Graph-gegevens beschikbaar hebben voor de geselecteerde merken en interesses, inclusief profielen die zich niet in het geselecteerde land of de geselecteerde regio bevinden. Als u bijvoorbeeld Duitsland hebt geselecteerd, verrijken we profielen in de Verenigde Staten als we Microsoft Graph-gegevens beschikbaar hebben voor de geselecteerde merken en interesses in de VS.

## <a name="configure-enrichment"></a>Verrijking configureren

Het configureren van merk- of interesseverrijking bestaat uit twee stappen:

### <a name="define-your-brands-or-interests"></a>Uw merken of interesses definiëren

Selecteer een van de volgende opties:

- **Branche**: het systeem identificeert de topmerken of interesses die relevant zijn voor uw branche en verrijkt uw klantgegevens hiermee.
- **Uw eigen keuze maken**: selecteer maximaal vijf items uit de lijst met merken of interesses die het meest relevant zijn voor uw organisatie.

Als u een merk of interesse wilt toevoegen, voert u dit in het invoerveld in om suggesties te krijgen op basis van overeenkomende termen. Als we geen merk of interesse vermelden waarnaar u op zoek bent, stuur ons dan feedback via de koppeling **Dit voorstellen**.

### <a name="map-your-fields"></a>Uw velden toewijzen

Wijs velden van uw geharmoniseerde klantentiteit toe aan ten minste twee kenmerken om het demografische segment te definiëren dat u wilt dat we gebruiken om uw klantgegevens te verrijken. Selecteer **Bewerken** om de toewijzing van de velden te definiëren en selecteer **Toepassen** wanneer u klaar bent. Selecteer **Opslaan** om de veldtoewijzing te voltooien.

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
