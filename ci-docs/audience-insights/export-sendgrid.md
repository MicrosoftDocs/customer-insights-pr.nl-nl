---
title: Customer Insights-gegevens exporteren naar SendGrid
description: Ontdek hoe u de verbinding met SendGrid configureert.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268726"
---
# <a name="connector-for-sendgrid-preview"></a>Connector voor SendGrid (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar SendGrid en gebruik ze voor campagnes en e-mailmarketing in SendGrid. 

## <a name="prerequisites"></a>Vereisten

-   U hebt een [SendGrid-account](https://sendgrid.com/) en bijbehorende beheerdersreferenties nodig.
-   Er zijn bestaande contactpersonenlijsten met bijbehorende id's in SendGrid. Zie [SendGrid - Contactpersonen beheren](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)​voor meer informatie.
-   U hebt [geconfigureerde segmenten](segments.md) in doelgroepinzichten.
-   Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.

## <a name="connect-to-sendgrid"></a>Verbinding maken met SendGrid

1. Ga naar **Beheer** > **Exportbestemmingen**.

1. Selecteer onder **SendGrid** de optie **Instellen**.

1. Geef uw exportbestemming een herkenbare naam in het veld **Weergavenaam**.

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="SendGrid-configuratiedeelvenster voor exporteren.":::

1. Voer uw **SendGrid API-sleutel** [SendGrid API-sleutel](https://sendgrid.com/docs/ui/account-and-settings/api-keys/) in.

1. Voer uw **[SendGrid-lijst-id](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)** in.

1. Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.

1. Selecteer **Verbinden** om de verbinding met SendGrid te initialiseren.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Volgende** om de export te configureren.

## <a name="configure-the-connector"></a>De connector configureren

1. Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant. Herhaal dezelfde stappen voor andere optionele velden, zoals **Voornaam**, **Achternaam**, **Land/regio**, **Staat**, **Plaats** en **Postcode**.

1. Selecteer de segmenten die u wilt exporteren. Wij **raden u sterk aan niet meer dan 100.000 klantprofielen in totaal te exporteren** naar SendGrid. 

1. Selecteer **Opslaan**.

## <a name="export-the-data"></a>De gegevens exporteren

U kunt [gegevens op aanvraag exporteren](export-destinations.md). De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab).

## <a name="known-limitations"></a>Bekende beperkingen

- Tot 100.000 profielen in totaal naar SendGrid.
- Exporteren naar SendGrid is beperkt tot segmenten.
- Het exporteren van maximaal 100.000 profielen naar SendGrid kan enkele uren duren. 
- Het aantal profielen dat u naar SendGrid kunt exporteren, is afhankelijk van uw contract met SendGrid.

## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar SendGrid te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat SendGrid voldoet aan uw privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.
Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]