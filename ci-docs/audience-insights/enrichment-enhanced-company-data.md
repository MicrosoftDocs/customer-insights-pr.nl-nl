---
title: Verbetering van bedrijfsgegevens
description: Verrijk en normaliseer bedrijfsgegevens met de modellen van Microsoft.
ms.date: 11/05/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9bfb96d47de4ec98325e644c60752fc7cab2706c
ms.sourcegitcommit: 6efcba688d1db1a5d6343c229f292a26c48fc007
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/05/2021
ms.locfileid: "7770164"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>De verrijking van bedrijfsprofielen met verbeterde bedrijfsgegevens

Gebruik de modellen en gecompileerde bedrijfsgegevens van Microsoft om uw bedrijfsprofielen te corrigeren, aan te vullen en te standaardiseren. We gebruiken de [Common Data Model-indeling](/common-data-model/schema/core/applicationcommon/account) voor betere nauwkeurigheid en inzichten.

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
3.  Garandeer de nauwkeurigheid of actualiteit van gegevens. Omdat bedrijfsinformatie vaak verandert, kunnen we niet garanderen dat de verstrekte verbeterde bedrijfsgegevens altijd exact of up-to-date zijn.

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

U kunt een gedetailleerd overzicht van elk verrijkt profiel openen door **Verrijkte gegevens weergeven** te selecteren.

## <a name="next-steps"></a>Volgende stappen

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
