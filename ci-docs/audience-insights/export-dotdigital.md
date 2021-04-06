---
title: Customer Insights-gegevens exporteren naar DotDigital
description: Ontdek hoe u de verbinding met DotDigital configureert.
ms.date: 11/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 51a28bdf0de34f0555d8ad7e3d13b2ef8911d417
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598011"
---
# <a name="connector-for-dotdigital-preview"></a>Connector voor DotDigital (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar DotDigital-adresboeken en gebruik ze voor campagnes, e-mailmarketing en om klantsegmenten op te bouwen met DotDigital. 

## <a name="prerequisites"></a>Vereisten

-   U hebt een [DotDigital-account](https://dotdigital.com/) en bijbehorende beheerdersreferenties nodig.
-   Er zijn bestaande adresboeken met bijbehorende id's in DotDigital. De id is te vinden in de URL wanneer u een adresboek selecteert en opent. Zie [DotDigital-adresboeken](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) voor meer informatie.
-   U hebt [geconfigureerde segmenten](segments.md) in doelgroepinzichten.
-   Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.

## <a name="connect-to-dotdigital"></a>Verbinden met DotDigital

1. Ga naar **Beheer** > **Exportbestemmingen**.

1. Selecteer onder **DotDigital** de optie **Instellen**.

1. Geef uw exportbestemming een herkenbare naam in het veld **Weergavenaam**.

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Configuratiedeelvenster voor DotDigital-export.":::

1. Voer uw **DotDigital-gebruikersnaam en wachtwoord** in.

1. Voer uw **[DotDigital adresboek-id](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)** in.

1. Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.

1. Selecteer **Verbinden** om de verbinding met DotDigital te initialiseren.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Volgende** om de export te configureren.

## <a name="configure-the-connector"></a>De connector configureren

1. Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant. Herhaal dezelfde stappen voor andere optionele velden, zoals **Voornaam**, **Achternaam**, **Voor- en achternaam**, **Geslacht** en **Postcode**.

1. Selecteer de segmenten die u wilt exporteren. U kunt in totaal tot 1 miljoen klantprofielen exporteren naar DotDigital.

1. Selecteer **Opslaan**.

## <a name="export-the-data"></a>De gegevens exporteren

U kunt [gegevens op aanvraag exporteren](export-destinations.md). De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab). In DotDigital kunt u nu uw segmenten vinden in [DotDigital-adresboeken](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

## <a name="known-limitations"></a>Bekende beperkingen

- Maximaal 1 miljoen profielen per export naar DotDigital.
- Exporteren naar DotDigital is beperkt tot segmenten.
- Segmenten exporteren met in totaal 1 miljoen profielen kan tot 3 uur duren vanwege beperkingen aan de providerzijde. 
- Het aantal profielen dat u naar DotDigital kunt exporteren, is afhankelijk van uw contract met DotDigital.

## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar DotDigital te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat DotDigital voldoet aan uw privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.
Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]