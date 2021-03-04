---
title: Verrijking van bedrijfsprofielen met de verrijking door derden van Leadspace
description: Algemene informatie over de verrijking door derden van Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 12eed91a7ca4ef7fde0d53cca4a1dfd398b4634f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269416"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Verrijking van bedrijfsprofielen met Leadspace (preview)

Leadspace is een data science-bedrijf dat een B2B-platform voor klantgegevens biedt. Het stelt klanten met geharmoniseerde klantprofielen voor bedrijven in staat hun gegevens te verrijken. Verrijkingen zijn onder andere aanvullende kenmerken, zoals bedrijfsgrootte, locatie, branche en meer.

## <a name="prerequisites"></a>Vereisten

Als u Leadspace wilt configureren, moet aan de volgende vereisten worden voldaan:

- U hebt een actieve Leadspace-licentie en de "permanente sleutel" (ook wel **Leadspace-token** genoemd). Neem rechtstreeks contact op met [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) voor details over hun product.
- U hebt [Beheerders](permissions.md#administrator)machtigingen.
- U hebt [geharmoniseerde klantprofielen](customer-profiles.md) voor bedrijven.

## <a name="configuration"></a>Configuratie

1. Ga in doelgroepinzichten naar **Gegevens** > **Verrijking**.

1. Selecteer **Mijn gegevens verrijken** op de Leadspace-tegel.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Schermopname van de Leadspace-tegel.":::

1. Selecteer **Aan de slag** en voer een actief **Leadspace-token** in (permanente sleutel). Bekijk en geef toestemming voor **Gegevensprivacy en naleving** door het selectievakje **Ik ga akkoord** in te schakelen. Bevestig de invoer door **Verbinden met Leadspace** te selecteren.

1. Selecteer **Gegevens toewijzen** en kies de gegevensset die u wilt verrijken met bedrijfsgegevens van Leadspace. U kunt de entiteit *Klant* selecteren om al uw klantprofielen te verrijken of een segmententiteit selecteren om alleen klantprofielen in dat segment te verrijken.

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Kies tussen klantprofiel- en segmentverrijking.":::

1. Klik op **Volgende** en bepaal welke velden van uw geharmoniseerde profielen moeten worden gebruikt om overeenkomende bedrijfsgegevens van Leadspace te zoeken. Het veld **Naam van bedrijf** is verplicht. Voor een hogere matchnauwkeurigheid kunt u maximaal twee andere velden, **Bedrijfswebsite** en **Bedrijfslocatie** toevoegen.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Deelvenster Leadspace-veldtoewijzing.":::
   
1. Selecteer **Toepassen** om de veldtoewijzing te voltooien.

1. Selecteer **Uitvoeren** om de bedrijfsprofielen te verrijken. Hoe lang een verrijking duurt, hangt af van het aantal geharmoniseerde klantprofielen.

## <a name="enrichment-results"></a>Verrijkingsresultaten

Nadat u de verrijking hebt vernieuwd, kunt u de nieuw verrijkte bedrijfsgegevens bekijken onder [Mijn verrijkingen](enrichment-hub.md). U kunt het tijdstip van de laatste update en het aantal verrijkte profielen terugvinden.

U kunt een gedetailleerd overzicht van elk verrijkt profiel openen door **Verrijkte gegevens weergeven** te selecteren.

Zie [De API's van Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API) voor meer informatie.

## <a name="next-steps"></a>Volgende stappen

Bouw voort op uw verrijkte klantgegevens. Maak [segmenten](segments.md), [metingen](measures.md) en [exporteer de gegevens](export-destinations.md) om uw klanten gepersonaliseerde ervaringen te bieden.

## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar Leadspace te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat Leadspace voldoet aan uw privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.
Uw Dynamics 365 Customer Insights-beheerder kan deze verrijking op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]