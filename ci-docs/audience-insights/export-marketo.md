---
title: Customer Insights-gegevens exporteren naar Marketo
description: Ontdek hoe u de verbinding met Marketo configureert.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34ccee2894f1f2b552d0c6a88a6810e2dfc677a3
ms.sourcegitcommit: 0b1d3ca11b8ba362a959da0eea15c37e9cdba084
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/18/2020
ms.locfileid: "4570397"
---
# <a name="connector-for-marketo-preview"></a>Connector voor Marketo (preview)

Exporteer segmenten van geharmoniseerde klantprofielen om campagnes te genereren, e-mailmarketing te bieden en specifieke groepen klanten te gebruiken met Marketo.

## <a name="prerequisites"></a>Vereisten

-   U hebt een [Marketo-account](https://login.marketo.com/) en bijbehorende beheerdersreferenties nodig.
-   Er zijn bestaande lijsten met bijbehorende id's in Marketo. Zie [Marketo-lijsten](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) voor meer informatie.
-   U hebt [geconfigureerde segmenten](segments.md).
-   Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.

## <a name="connect-to-marketo"></a>Verbinden met Marketo

1. Ga naar **Beheer** > **Exportbestemmingen**.

1. Selecteer onder **Marketo** de optie **Instellen**.

1. Geef uw exportbestemming een herkenbare naam in het veld **Weergavenaam**.

1. Voer uw **[Marketo-client-id, clientgeheim en REST-eindpunt hostnaam](https://developers.marketo.com/rest-api/authentication/)** in.

1. Voer uw **[Marketo-lijst-id](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** in 

1. Selecteer **Ik ga akkoord** om de **Gegevensprivacy en naleving** te bevestigen en selecteer **Verbinden** om de verbinding met Marketo te initialiseren.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Schermopname voor Marketo-verbinding exporteren":::

1. Selecteer **Volgende** om de export te configureren.

## <a name="configure-the-connector"></a>De connector configureren

1. Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant. 

1. Optioneel kunt u **Voornaam**, **Achternaam**, **Woonplaats**, **Staat** en **Land/regio** exporteren als extra velden om meer gepersonaliseerde e-mails te maken. Selecteer **Kenmerk toevoegen** om deze velden toe te wijzen.

1. Selecteer de segmenten die u wilt exporteren. U kunt in totaal tot 1 miljoen klantprofielen exporteren naar Marketo.

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Velden en segmenten selecteren om naar Marketo te exporteren":::

1. Selecteer **Opslaan**.

## <a name="export-the-data"></a>De gegevens exporteren

U kunt [gegevens op aanvraag exporteren](export-destinations.md). De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab). In Marketo vindt u nu uw segmenten onder [Marketo-lijsten](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

## <a name="known-limitations"></a>Bekende beperkingen

- Maximaal 1 miljoen profielen per export naar Marketo.
- Exporteren naar Marketo is beperkt tot segmenten.
- Segmenten met in totaal 1 miljoen profielen exporteren kan tot 3 uur duren. 
- Het aantal profielen dat u naar Marketo kunt exporteren, is afhankelijk van uw contract met Marketo.

## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar Marketo te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat Marketo voldoet aan uw privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.
Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.
