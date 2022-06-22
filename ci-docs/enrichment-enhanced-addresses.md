---
title: Verrijking van adresverbetering (met video)
description: Verrijk en normaliseer adresgegevens van klantprofielen met de modellen van Microsoft.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
searchScope:
- ci-data-sources-enrichment
- ci-data-sources-enrichment-details
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: f6279b9bb721d99d66f73e8dc839a92f1ad90140
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953805"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Verrijking van klantprofielen met uitgebreide adressen

Adressen in uw gegevens kunnen ongestructureerd, onvolledig of onjuist zijn. Gebruik de modellen van Microsoft om uw adressen te normaliseren en te verrijken met de [Common Data Model-indeling](/common-data-model/schema/core/applicationcommon/address) voor betere nauwkeurigheid en inzichten.

U kunt ook [adressen in gegevensbronnen verrijken](data-sources-enrichment.md) om de afstemmingsnauwkeurigheid in het gegevensharmonisatieproces te verbeteren. 

## <a name="how-we-enhance-addresses"></a>Adressen uitbreiden

Ons model doorloopt een proces in twee stappen om een adres uit te breiden. Eerst wordt het adres geparseerd om de onderdelen ervan te identificeren en worden deze onderdelen in een gestructureerde indeling geplaatst. Vervolgens gebruiken we AI om de waarden in het adres te corrigeren, aan te vullen en te standaardiseren.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWNewo]

### <a name="example"></a>Voorbeeld

Adresgegevens kunnen een afwijkende notatie hebben en spelfouten bevatten. Met het model kunnen deze problemen worden opgelost en kunnen consistente adressen in uniforme klantprofielen worden gemaakt.

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

Verbeterde adressen werken alleen met de waarden die al bestaan in uw opgenomen adresgegevens. Het model doet het volgende niet:

1. Controleren of het adres een geldig adres is.
2. Controleren of de waarden, zoals postcodes of straatnamen, geldig zijn.
3. Waarden wijzigen die niet worden herkend.

Het model maakt gebruik van op machine learning gebaseerde methoden om adressen uit te breiden. Zoals bij elk op machine learning gebaseerd model, is 100 procent nauwkeurigheid niet gegarandeerd.

## <a name="supported-countries-or-regions"></a>Ondersteunde landen of regio's

We ondersteunen momenteel uitgebreide adressen in de volgende landen of regio's:

- Australië
- Canada
- Frankrijk
- Duitsland
- Italië
- Japan
- Verenigd Koninkrijk
- Verenigde Staten

## <a name="configure-the-enrichment"></a>De verrijking configureren

1. Ga naar **Gegevens** > **Verrijking** en selecteer het tabblad **Detecteren**.

1. Selecteer **Mijn gegevens verrijken** op de tegel **Uitgebreide adressen**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Schermopname van de tegel Uitgebreide adressen.":::

1. Bekijk het overzicht en selecteer **Volgende**.

1. Selecteer de **Klantgegevensset** en kies het profiel of segment dat u wilt verrijken. De entiteit *Klant* verrijkt al uw klantprofielen, terwijl een segment alleen klantprofielen in dat segment verrijkt.

1. Selecteer hoe adressen worden opgemaakt in uw gegevensset. Kies **Adres met één kenmerk** als adressen in uw gegevens één veld gebruiken. Kies **Adres met meerdere kenmerken** als adressen in uw gegevens meerdere gegevensvelden gebruiken.

1. Selecteer **Volgende** en wijs de adresvelden van uw verenigde klantentiteit toe.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Veldtoewijzingspagina voor uitgebreide adressen.":::

   > [!NOTE]
   > Land/regio is verplicht in zowel adressen met enkelvoudige kenmerken als adressen met meervoudige kenmerken. Adressen die geen geldige of ondersteunde waarden voor land/regio bevatten, worden niet verrijkt.

1. Selecteer **Volgende** om de veldtoewijzing te voltooien.

1. Geef een **naam** op voor de verrijking en de **uitvoerentiteit**.

1. Selecteer **Verrijking opslaan** na het bekijken van uw keuzes.

## <a name="enrichment-results"></a>Verrijkingsresultaten

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Het **Aantal klanten dat wordt verrijkt per veld** biedt een gedetailleerde beschrijving van de dekking van elk verrijkt veld.

### <a name="overview-card"></a>Overzichtskaart

Op de kaart **Overzicht klantwijzigingen** staan details over wat onder de verrijking valt:

- **Verwerkte en gewijzigde adressen**: het aantal klantprofielen met adressen dat succesvol is verrijkt.
- **Adressen verwerkt en niet gewijzigd**: het aantal klantprofielen met adressen dat is herkend maar niet gewijzigd. Dit gebeurt meestal wanneer de invoergegevens geldig zijn en niet kunnen worden verbeterd door de verrijking.
- **Adressen niet verwerkt en niet gewijzigd**: het aantal klantprofielen met adressen die niet werden herkend. Meestal voor invoergegevens die ongeldig zijn of niet worden ondersteund door de verrijking.

## <a name="next-steps"></a>Volgende stappen

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
