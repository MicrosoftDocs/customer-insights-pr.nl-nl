---
title: Bedrijfsprofielen verrijken met verbeterde bedrijfsgegevens
description: Verrijk en normaliseer bedrijfsgegevens met de modellen van Microsoft.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 131ef3d1e123628779609ddec368cfef8f4d607e
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054242"
---
# <a name="enrich-company-profiles-with-enhanced-company-data"></a>Bedrijfsprofielen verrijken met verbeterde bedrijfsgegevens

Gebruik de modellen en gecompileerde bedrijfsgegevens van Microsoft om uw bedrijfsprofielen te corrigeren, aan te vullen en te standaardiseren. We gebruiken de [Common Data Model-indeling](/common-data-model/schema/core/applicationcommon/account) voor betere nauwkeurigheid en inzichten.

U kunt ook [bedrijfsgegevens in gegevensbronnen verbeteren](data-sources-enrichment.md) om de afstemmingsnauwkeurigheid in het gegevensharmonisatieproces te verbeteren.

Voor openbare bedrijven in de Verenigde Staten is informatie zoals omzet, aandelenkoers, branche en meer beschikbaar.  

## <a name="how-we-enhance-company-data"></a>Hoe we bedrijfsgegevens verbeteren

Ons model doorloopt een proces in twee stappen om een bedrijfsprofiel te verbeteren. Ten eerste wordt de bedrijfsnaam genormaliseerd. *Microsoft Corp* wordt bijvoorbeeld gecorrigeerd en gestandaardiseerd naar *Microsoft Corporation*. Er wordt geprobeerd een match te vinden in de gecompileerde bedrijfsgegevens van Microsoft. Als een match wordt gevonden, verrijken we het bedrijfsprofiel met informatie uit onze verzamelde bedrijfsgegevens, waaronder de bedrijfsnaam.

### <a name="example"></a>Voorbeeld

Uw bedrijfsinformatie heeft mogelijk geen gestandaardiseerde indeling en bevat mogelijk spelfouten. Het model probeert deze problemen op te lossen en consistente informatie te maken.

```Input
Microsft
```

```Output
- AccountName: Microsoft Corporation
- MainPhoneNumber: 8006427676
- Website: https://www.microsoft.com/
- Street1: One Microsoft Way
- City: Redmond
- StateOrProvince: Washington
- County: King
- ZipOrPostalCode: 98052
- CountryOrRegion: United States
```

## <a name="limitations"></a>Beperkingen

Het model doet het volgende niet:

- Bevestig de identiteit van het bedrijf. We controleren niet of de invoer een bestaande organisatie is of dat een bedrijf de uitvoer als standaardnaam gebruikt.
- Bedien bedrijven wereldwijd. De verzamelde bedrijfsgegevens van Microsoft hebben wereldwijde dekking, maar bieden de meeste dekking in Australië, Canada, het Verenigd Koninkrijk en de Verenigde Staten.
- Standaardiseren van bedrijfsadressen wereldwijd. We ondersteunen momenteel het standaardiseren van adressen in deze landen of regio's: Australië, Canada, Frankrijk, Duitsland, Italië, Japan, het Verenigd Koninkrijk en de Verenigde Staten.
- Garandeer de nauwkeurigheid of actualiteit van gegevens. Omdat bedrijfsinformatie vaak verandert, kunnen we niet garanderen dat de verstrekte verbeterde bedrijfsgegevens altijd exact of up-to-date zijn.

## <a name="configure-the-enrichment"></a>De verrijking configureren

1. Ga naar **Gegevens** > **Verrijking** en selecteer het tabblad **Detecteren**.

1. Selecteer **Mijn gegevens verrijken** op de tegel **Verbeterde bedrijfsgegevens**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Verrijkingstegel in de verrijkingshub voor bedrijfsgegevens.":::

1. Bekijk het overzicht en selecteer **Volgende**.

1. Selecteer de **Klantgegevensset** en kies het profiel of segment dat u wilt verrijken. De entiteit *Klant* verrijkt al uw klantprofielen, terwijl een segment alleen klantprofielen in dat segment verrijkt.

1. Geef op welke typen velden uit uw bedrijfsprofielen moeten worden gebruikt om te vergelijken met de door Microsoft gecompileerde bedrijfsgegevens. Deze selectie heeft invloed op de toewijzingsvelden waartoe u in de volgende stap toegang hebt.

1. Selecteer **Volgende**.

1. Wijs uw bedrijfsvelden toe aan de bedrijfsgegevens van Microsoft. Voeg meer velden toe voor een hogere matchnauwkeurigheid.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Stap voor het toewijzen van gegevens bij het configureren van een bedrijfsverrijking.":::

1. Selecteer **Volgende** om de veldtoewijzing te voltooien.

1. Geef een **naam** op voor de verrijking en de **uitvoerentiteit**.

1. Selecteer **Verrijking opslaan** na het bekijken van uw keuzes.

1. Selecteer **Uitvoeren** om het verrijkingsproces te starten of sluit om terug te keren naar de pagina **Verrijkingen**.

## <a name="view-enrichment-results"></a>Verrijkingsresultaten bekijken

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

### <a name="overview-card"></a>Overzichtskaart

Op de tegel **Overzicht klantwijzigingen** staan details over wat onder de verrijking valt

- **Verwerkte en gewijzigde bedrijven**: het aantal klant-bedrijfsprofielen dat succesvol is verrijkt.
- **Bedrijven verwerkt en niet gewijzigd**: het aantal klant-bedrijfsprofielen dat is herkend maar niet gewijzigd. Dit gebeurt meestal wanneer de invoergegevens geldig zijn en niet kunnen worden verbeterd door de verrijking.
- **Bedrijven niet verwerkt en niet gewijzigd**: het aantal klant-bedrijfsprofielen dat niet werd herkend. Dit gebeurt meestal voor invoergegevens die ongeldig zijn of niet worden ondersteund door de verrijking.

## <a name="next-steps"></a>Volgende stappen

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
