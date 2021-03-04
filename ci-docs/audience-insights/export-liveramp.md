---
title: LiveRamp-connector
description: Ontdek hoe u gegevens kunt exporteren naar LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 64d781f52e8124fc3e83a7b84f468830c5249cfd
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270152"
---
# <a name="liverampreg-connector-preview"></a>LiveRamp&reg;-connector (preview)

Activeer uw gegevens in LiveRamp om verbinding te maken met meer dan 500 platforms in digitale, sociale en tv-ecosystemen. Werk met uw gegevens in LiveRamp om advertentiecampagnes te targeten, onderdrukken en personaliseren.

## <a name="prerequisites"></a>Vereisten

- U hebt een LiveRamp-abonnement nodig om deze connector te kunnen gebruiken.
- U kunt een abonnement nemen door rechtstreeks [contact op te nemen met LiveRamp](https://liveramp.com/contact/). [Meer informatie over LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="connect-to-liveramp"></a>Verbinding maken met LiveRamp

1. Ga in doelgroepinzichten naar **Beheer** > **Exportbestemmingen**.

1. Selecteer op de tegel **LiveRamp** de optie **Instellen**.

1. Geef uw bestemming een herkenbare naam in het veld **Weergavenaam**.

1. Verschaf een **gebruikersnaam** en **wachtwoord** voor uw LiveRamp Secure FTP-account (SFTP).
Deze referenties kunnen verschillen van uw LiveRamp Onboarding-referenties.

1. Selecteer **Verifiëren** om de verbinding met LiveRamp te testen.

1. Geef na succesvolle verificatie uw toestemming voor **Gegevensprivacy en naleving** door het selectievakje **Ik ga akkoord** in te schakelen.

1. Selecteer **Volgende** om de LiveRamp-connector in te stellen.

## <a name="configure-the-connector"></a>De connector configureren

1. Selecteer in het veld **Uw sleutelidentificatie kiezen** de optie **E-mail**, **Naam en adres** of **Telefoon** om naar LiveRamp te sturen voor identiteitsresolutie.

1. Wijs de corresponderende kenmerken van uw geharmoniseerde klantentiteit toe aan de geselecteerde sleutel-id.

1. Selecteer **Kenmerk toevoegen** om extra kenmerken toe te wijzen voor verzending naar LiveRamp.

   > [!TIP]
   > Als u meer kenmerken voor sleutel-id's naar LiveRamp verzendt, krijgt u waarschijnlijk een hoger overeenkomstpercentage.

1. Selecteer de segmenten die u naar LiveRamp wilt exporteren.

1. Selecteer **Opslaan**.

> [!div class="mx-imgBorder"]
> ![LiveRamp-connector met kenmerktoewijzing](media/export-liveramp-segments.png "LiveRamp-connector met kenmerktoewijzing")

## <a name="export-the-data"></a>De gegevens exporteren

De export begint spoedig als aan alle voorwaarden voor export is voldaan. De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab).
Zodra de export is voltooid, kunt u zich aanmelden bij LiveRamp Onboarding om uw gegevens te activeren en te distribueren.

## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar LiveRamp te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat LiveRamp voldoet aan uw privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.
Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.

[!INCLUDE[footer-include](../includes/footer-banner.md)]