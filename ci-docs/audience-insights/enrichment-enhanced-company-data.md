---
title: Verbetering van bedrijfsgegevens
description: Verrijk en normaliseer bedrijfsgegevens met de modellen van Microsoft.
ms.date: 01/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e9cf93f28ba6918c72039670e42d26c8aaa7f922
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376316"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>De verrijking van bedrijfsprofielen met verbeterde bedrijfsgegevens

Gebruik de modellen en gecompileerde bedrijfsgegevens van Microsoft om uw bedrijfsprofielen te corrigeren, aan te vullen en te standaardiseren. We gebruiken de [Common Data Model-indeling](/common-data-model/schema/core/applicationcommon/account) voor betere nauwkeurigheid en inzichten.

U kunt ook [bedrijfsgegevens in gegevensbronnen verbeteren](data-sources-enrichment.md) om de afstemmingsnauwkeurigheid in het gegevensharmonisatieproces te verbeteren. 

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

Er gelden een paar beperkingen ten aanzien van de verbeterde gegevens. De items in de onderstaande lijst worden niet ondersteund door het model.

1.  Bevestig de identiteit van het bedrijf. We controleren niet of de invoer een bestaande organisatie is of dat een bedrijf de uitvoer als standaardnaam gebruikt.
2.  Bedien bedrijven wereldwijd. De verzamelde bedrijfsgegevens van Microsoft hebben wereldwijde dekking, maar bieden de meeste dekking in Australië, Canada, het Verenigd Koninkrijk en de Verenigde Staten.
3.  Standaardiseren van bedrijfsadressen wereldwijd. We ondersteunen momenteel het standaardiseren van adressen in deze landen of regio's: Australië, Canada, Frankrijk, Duitsland, Italië, Japan, het Verenigd Koninkrijk en de Verenigde Staten.
4.  Garandeer de nauwkeurigheid of actualiteit van gegevens. Omdat bedrijfsinformatie vaak verandert, kunnen we niet garanderen dat de verstrekte verbeterde bedrijfsgegevens altijd exact of up-to-date zijn.

## <a name="configure-the-enrichment"></a>De verrijking configureren

1. Ga naar **Gegevens** > **Verrijking**.

1. Selecteer **Mijn gegevens verrijken** op de tegel **Verbeterde bedrijfsgegevens**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Verrijkingstegel in de verrijkingshub voor bedrijfsgegevens.":::

1. Selecteer de **Klantgegevensset** en kies de entiteit met de adressen die u wilt verrijken. U kunt de entiteit *Klant* selecteren om adressen in al uw klantprofielen te verrijken of u kunt een segmententiteit selecteren om adressen alleen in klantprofielen in dat segment te verrijken.

1. Geef op welke typen velden uit uw bedrijfsprofielen moeten worden gebruikt om te vergelijken met de door Microsoft gecompileerde bedrijfsgegevens. Deze selectie heeft invloed op de toewijzingsvelden waartoe u in de volgende stap toegang hebt.

1.  Wijs de bedrijfsvelden vanuit uw uniforme klantentiteit toe. Hoe meer sleutel-id's en velden u toewijst, hoe groter de kans op een hoger matchpercentage.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Stap voor het toewijzen van gegevens bij het configureren van een bedrijfsverrijking.":::

1. Selecteer **Volgende** om de veldtoewijzing te voltooien.

1. Geef een naam op voor de verrijking en de uitvoerentiteit.

1. Selecteer **Verrijking opslaan** na het bekijken van uw keuzes.

## <a name="enrichment-results"></a>Verrijkingsresultaten

Selecteer **Uitvoeren** vanaf de opdrachtbalk om het verrijkingsproces te starten. U kunt de verrijking ook automatisch laten uitvoeren als onderdeel van een [geplande vernieuwing](system.md#schedule-tab). De verwerkingstijd is afhankelijk van de grootte van uw klantgegevens.

Nadat het verrijkingsproces is voltooid, kunt u de nieuwe verrijkte klantprofielgegevens bekijken onder **Mijn verrijkingen**. Ook vindt u daar het tijdstip van de laatste update en het aantal verrijkte profielen.

U kunt een sample van de verrijkte gegevens zien in de tegel **Preview van verrijkte klanten**. Selecteer **Meer bekijken** en selecteer het tabblad **Gegevens** om toegang te krijgen tot een gedetailleerd overzicht van elk verrijkt profiel.

### <a name="overview-card"></a>Overzichtskaart

Op de overzichtskaart staan details over wat onder de verrijking valt. 

* **Verwerkte en gewijzigde bedrijven**: het aantal klant-bedrijfsprofielen dat succesvol is verrijkt.

* **Bedrijven verwerkt en niet gewijzigd**: het aantal klant-bedrijfsprofielen dat is herkend maar niet gewijzigd. Dit gebeurt meestal wanneer de invoergegevens geldig zijn en niet kunnen worden verbeterd door de verrijking.

* **Bedrijven niet verwerkt en niet gewijzigd**: het aantal klant-bedrijfsprofielen dat niet werd herkend. Dit gebeurt meestal voor invoergegevens die ongeldig zijn of niet worden ondersteund door de verrijking.

## <a name="next-steps"></a>Volgende stappen

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
