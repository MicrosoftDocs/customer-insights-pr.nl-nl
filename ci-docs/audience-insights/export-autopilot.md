---
title: Customer Insights-gegevens exporteren naar Autopilot
description: Ontdek hoe u de verbinding met Autopilot configureert.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d039c4afd84eaad942d214d4e6fb8ef7b1ec72a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596124"
---
# <a name="connector-for-autopilot-preview"></a>Connector voor Autopilot (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar Autopilot en gebruik ze voor e-mailmarketing in Autopilot. 

## <a name="prerequisites"></a>Vereisten

-   U hebt een [Autopilot-account](https://www.autopilothq.com/) en bijbehorende beheerdersreferenties nodig.
-   U hebt [geconfigureerde segmenten](segments.md) in doelgroepinzichten.
-   Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.

## <a name="connect-to-autopilot"></a>Verbinding maken met Autopilot

1. Ga naar **Beheer** > **Exportbestemmingen**.

1. Selecteer onder **Autopilot** de optie **Instellen**.

1. Geef uw exportbestemming een herkenbare naam in het veld **Weergavenaam**.

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Configuratiedeelvenster voor Autopilot-verbinding.":::

1. Voer uw **Autopilot API-sleutel** [Autopilot API-sleutel](https://autopilot.docs.apiary.io/#)​in.

1. Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.

1. Selecteer **Verbinden** om de verbinding met Autopilot te initialiseren.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Volgende** om de export te configureren.

## <a name="configure-the-connector"></a>De connector configureren

1. Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant. Herhaal dezelfde stappen voor andere optionele velden, zoals **Voornaam**, **Achternaam**.

1. Selecteer de segmenten die u wilt exporteren. Wij **raden u sterk aan niet meer dan 100.000 klantprofielen in totaal te exporteren** naar Autopilot. 

1. Selecteer **Opslaan**.

## <a name="export-the-data"></a>De gegevens exporteren

U kunt [gegevens op aanvraag exporteren](export-destinations.md). De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab).

## <a name="known-limitations"></a>Bekende beperkingen

- U kunt in totaal tot 100.000 klantprofielen exporteren naar Autopilot.
- Exporteren naar Autopilot is beperkt tot segmenten.
- Het exporteren van maximaal 100.000 profielen naar Autopilot kan enkele uren duren. 
- Het aantal profielen dat u naar Autopilot kunt exporteren, is afhankelijk van uw contract met Autopilot.

## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar Autopilot te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat Autopilot voldoet aan uw privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.
Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]