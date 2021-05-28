---
title: Verrijking van adresuitbreiding
description: Verrijk en normaliseer adresgegevens van klantprofielen met de modellen van Microsoft.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965572"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Verrijking van klantprofielen met uitgebreide adressen

Adressen in uw gegevens kunnen ongestructureerd, onvolledig of onjuist zijn. Gebruik de modellen van Microsoft om uw adressen te normaliseren en te verrijken met de [Common Data Model-indeling](/common-data-model/schema/core/applicationcommon/address) voor betere nauwkeurigheid en inzichten.

## <a name="how-we-enhance-addresses"></a>Adressen uitbreiden

Ons model doorloopt een proces in twee stappen om een adres uit te breiden. Eerst wordt het adres geparseerd om de onderdelen ervan te identificeren en worden deze onderdelen in een gestructureerde indeling geplaatst. Vervolgens gebruiken we kunstmatige intelligentie om de waarden in het adres te corrigeren, aan te vullen en te standaardiseren.

### <a name="example"></a>Voorbeeld

Adresgegevens hebben mogelijk een afwijkende indeling en kunnen spelfouten bevatten. Met het model kunnen deze problemen worden opgelost en kunnen consistente adressen in uniforme klantprofielen worden gemaakt.

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a>Beperkingen

Uitgebreide adressen werken alleen met de waarden die al bestaan in uw opgenomen adresgegevens. Het model doet het volgende niet: 

1. Controleren of het adres een geldig adres is.
2. Controleren of de waarden, zoals postcodes of straatnamen, geldig zijn.
3. Waarden wijzigen die niet worden herkend.

Het model maakt gebruik van op machine learning gebaseerde methoden om adressen uit te breiden. Hoewel we een hoge betrouwbaarheidsdrempel toepassen voor gevallen waarin met het model een invoerwaarde wordt gewijzigd, zoals bij elk op ML gebaseerd model, is 100% nauwkeurigheid niet gegarandeerd.

## <a name="supported-countries-or-regions"></a>Ondersteunde landen of regio's

We ondersteunen momenteel uitgebreide adressen in de volgende landen of regio's: 

- Australië
- Canada
- Verenigd Koninkrijk
- Verenigde Staten

Adressen moeten een waarde voor land/regio bevatten. Adressen voor landen of regio's die niet worden ondersteund en adressen waarvoor geen land of regio is opgegeven, worden niet verwerkt.

## <a name="configure-the-enrichment"></a>De verrijking configureren

1. Ga naar **Gegevens** > **Verrijking**.

1. Selecteer **Mijn gegevens verrijken** op de tegel **Uitgebreide adressen**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Schermopname van de tegel Uitgebreide adressen.":::

1. Selecteer de **Klantgegevensset** en kies de entiteit met de adressen die u wilt verrijken. U kunt de entiteit *Klant* selecteren om adressen in al uw klantprofielen te verrijken of u kunt een segmententiteit selecteren om adressen alleen in klantprofielen in dat segment te verrijken.

1. Selecteer hoe adressen worden opgemaakt in uw gegevensset. Kies **Adres met één kenmerk** als adressen in uw gegevens één veld gebruiken. Kies **Adres met meerdere kenmerken** als adressen in uw gegevens meerdere gegevensvelden gebruiken.

   > [!NOTE]
   > Land/regio is verplicht in zowel adressen met één kenmerk als in adressen met meerdere kenmerken. Adressen die geen geldige of ondersteunde waarden voor land/regio bevatten, worden niet verrijkt

1.  Wijs de adresvelden vanuit uw uniforme klantentiteit toe.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Veldtoewijzingspagina voor uitgebreide adressen.":::

1. Selecteer **Volgende** om de veldtoewijzing te voltooien.

1. Geef een naam op voor de verrijking en de uitvoerentiteit.

1. Selecteer **Verrijking opslaan** na het bekijken van uw keuzes.

## <a name="enrichment-results"></a>Verrijkingsresultaten

Selecteer **Uitvoeren** vanaf de opdrachtbalk om het verrijkingsproces te starten. U kunt de verrijking ook automatisch laten uitvoeren als onderdeel van een [geplande vernieuwing](system.md#schedule-tab). De verwerkingstijd is afhankelijk van de grootte van uw klantgegevens.

Nadat het verrijkingsproces is voltooid, kunt u de nieuwe verrijkte klantprofielgegevens bekijken onder **Mijn verrijkingen**. Ook vindt u daar het tijdstip van de laatste update en het aantal verrijkte profielen.

U kunt een gedetailleerd overzicht van elk verrijkt profiel openen door **Verrijkte gegevens weergeven** te selecteren.

## <a name="next-steps"></a>Volgende stappen

Bouw voort op uw verrijkte klantgegevens. Maak [segmenten](segments.md), [metingen](measures.md) en [exporteer de gegevens](export-destinations.md) om uw klanten gepersonaliseerde ervaringen te bieden.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
