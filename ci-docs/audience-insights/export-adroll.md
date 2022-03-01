---
title: Customer Insights-gegevens exporteren naar AdRoll
description: Ontdek hoe u de verbinding met AdRoll configureert.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697068"
---
# <a name="connector-for-adroll-preview"></a>Connector voor AdRoll (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar AdRoll en gebruik ze voor advertenties. 

## <a name="prerequisites"></a>Vereisten

-   U hebt een [AdRoll-account](https://www.adroll.com/) en bijbehorende beheerdersreferenties nodig.
-   U hebt [geconfigureerde segmenten](segments.md) in doelgroepinzichten.
-   Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.

## <a name="connect-to-adroll"></a>Verbinding maken met AdRoll

1. Ga naar **Beheer** > **Exportbestemmingen**.

1. Selecteer onder **AdRoll** de optie **Instellen**.

1. Geef uw exportbestemming een herkenbare naam in het veld **Weergavenaam**.

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Configuratiedeelvenster voor AdRoll-verbinding.":::

1. Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.

1. Selecteer **Verbinden** om de verbinding met AdRoll te initialiseren.

1. Selecteer **Verifiëren met AdRoll** en geef uw beheerdersreferenties voor AdRoll op. 

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Voer uw **AdRoll-adverteerders-id** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles)​ in.

1. Selecteer **Volgende** om de export te configureren.

## <a name="configure-the-connector"></a>De connector configureren

1. Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant. Het is vereist om segmenten naar AdRoll te exporteren.

1. Selecteer de segmenten die u wilt exporteren. Selecteer een segment met minimaal 100 leden. U kunt geen kleinere segmenten exporteren. Bovendien is de maximale grootte van een te exporteren segment 250.000 leden per export. 

1. Selecteer **Opslaan**.

## <a name="export-the-data"></a>De gegevens exporteren

U kunt [gegevens op aanvraag exporteren](export-destinations.md). De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab).

## <a name="known-limitations"></a>Bekende beperkingen

- U kunt in totaal tot 250.000 profielen per export exporteren naar AdRoll.
- U kunt geen segmenten met minder dan 100 profielen naar AdRoll exporteren. 
- Exporteren naar AdRoll is beperkt tot segmenten.
- Het exporteren van maximaal 250.000 profielen naar AdRoll kan tot 10 minuten duren. 
- Het aantal profielen dat u naar AdRoll kunt exporteren, is afhankelijk van uw contract met AdRoll.

## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar AdRoll te verzenden, staat u de overdracht toe van gegevens buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat AdRoll voldoet aan uw privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.

Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.
