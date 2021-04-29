---
title: Verrijking van bedrijfsprofielen met de verrijking door derden van Leadspace
description: Algemene informatie over de verrijking door derden van Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ccf4f661ecffb281556a4545b1f26ee809c697cd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895907"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Verrijking van bedrijfsprofielen met Leadspace (preview)

Leadspace is een data science-bedrijf dat een B2B-platform voor klantgegevens biedt. Het stelt klanten met geharmoniseerde klantprofielen voor bedrijven in staat hun gegevens te verrijken. Verrijkingen voegen meer kenmerken toe zoals bedrijfsgrootte, locatie, branche en meer.

## <a name="prerequisites"></a>Vereisten

Als u Leadspace wilt configureren, moet aan de volgende vereisten worden voldaan:

- U hebt een actieve Leadspace-licentie.
- U hebt [geharmoniseerde klantprofielen](customer-profiles.md) voor bedrijven.
- Een Leadspace-verbinding is al geconfigureerd door een beheerder of u hebt [beheerdersmachtigingen](permissions.md#administrator) en de "eeuwigdurende sleutel" (waarnaar wordt verwezen als **Leadspace-token**). Neem rechtstreeks contact op met [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) voor details over hun product.

## <a name="configure-the-enrichment"></a>De verrijking configureren

1. Ga in doelgroepinzichten naar **Gegevens** > **Verrijking**.

1. Selecteer **Mijn gegevens verrijken** op de tegel van Leadspace en selecteer vervolgens **Aan de slag**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Schermopname van de Leadspace-tegel.":::

1. Selecteer een [verbinding](connections.md) in de vervolgkeuzelijst. Neem contact op met een beheerder als er geen verbinding beschikbaar is. Als u een beheerder bent, kunt u een verbinding maken door **Verbinding toevoegen** te selecteren en **Leadspace** te kiezen. 

1. Selecteer **Verbinding maken met Leadspace** om de verbinding te bevestigen.

1. Selecteer **Volgende** en kies de **klantgegevensset** die u wilt verrijken met bedrijfsgegevens van Leadspace. U kunt de entiteit **Klant** selecteren om al uw klantprofielen te verrijken of een segmententiteit selecteren om alleen klantprofielen in dat segment te verrijken.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Schermopname bij het kiezen van de klantgegevensset.":::

1. Selecteer **Volgende** en bepaal welk type velden uit uw geharmoniseerde profielen worden gebruikt om overeenkomende bedrijfsgegevens van Leadspace te zoeken. Het veld **Naam van bedrijf** is verplicht. Voor een hogere matchnauwkeurigheid kunt u maximaal twee andere velden, **Bedrijfswebsite** en **Bedrijfslocatie** toevoegen.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Deelvenster Leadspace-veldtoewijzing.":::

1. Selecteer **Volgende** om de veldtoewijzing te voltooien.

1. Geef een naam op voor de verrijking en selecteer **Verrijking opslaan** na het bekijken van uw keuzes.


## <a name="configure-the-connection-for-leadspace"></a>De verbinding configureren voor Leadspace 

U moet een beheerder zijn om verbindingen te kunnen configureren. Selecteer **Verbinding toevoegen** bij het configureren van een verrijking *of* ga naar **Beheerder** > **Verbindingen** en selecteer **Instellen** op de Leadspace-tegel.

1. Selecteer **Aan de slag** 

1. Voer een naam in voor de verbinding in het vak **Weergavenaam**.

1. Geef een geldig Leadspace-token op.

1. **Gegevensprivacy en naleving** bekijken en toestemming geven door het selectievakje **Ik ga akkoord** in te schakelen

1. Selecteer **Verifiëren** om de configuratie te valideren.

1. Voltooi de verificatie en selecteer **Opslaan**.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Configuratiepagina voor Leadspace-verbinding.":::

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
