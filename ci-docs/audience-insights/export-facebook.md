---
title: Customer Insights-gegevens exporteren naar Facebook Ads Manager
description: Meer informatie over het configureren van de verbinding met Facebook Ads Manager.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c839f9dc7e403412c0e3d936392d45a43bc63545
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269968"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>Connector voor Facebook Ads Manager (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar Facebook Ads Manager om campagnes te maken op Facebook en Instagram.

## <a name="prerequisites"></a>Vereisten

- U moet een [**Facebook Ad-account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) hebben met een [**Facebook Business-account**](https://business.facebook.com/).
- U moet een beheerder zijn van het [**Facebook Ad-account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="connect-to-facebook-ads-manager"></a>Verbinden met Facebook Ads Manager

1. Ga naar **Beheer** > **Exportbestemmingen**.

1. Selecteer onder **Facebook Ads Manager** de optie **Instellen**.

1. Geef uw exportbestemming een herkenbare naam in het veld **Weergavenaam**.

1. Selecteer **Doorgaan met Facebook** om zich aan te melden bij uw Facebook Ad-account.

1. Geef **ads_management** een machtiging na verificatie met Facebook.

1. Selecteer het **Facebook Ads-account** waarmee u wilt werken.

1. Selecteer een **Bestaande aangepaste doelgroep** in de vervolgkeuzelijst of maak een **Nieuwe aangepaste doelgroep**. Zie [**Doelgroepen in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494) voor meer informatie.

1. Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.

1. Selecteer **Volgende** om de export te configureren.

## <a name="configure-the-connector"></a>De connector configureren

1. Selecteer in het veld **Uw sleutel-id kiezen** de optie **E-mail**, **Naam en adres** of **Telefoon** om naar Facebook Ads Manager te verzenden.

1. Wijs de corresponderende kenmerken van uw geharmoniseerde klantentiteit toe aan de geselecteerde sleutel-id.
   > [TIP] U hebt de beste kans op een overeenkomst als u **E-mail** als sleutel-id selecteert. De matching kan verbeteren door toevoeging van extra id's.

1. Selecteer **Kenmerk toevoegen** om extra kenmerken toe te wijzen voor verzending naar Facebook Ads Manager. Kenmerken van Facebook Ads Manager komen overeen met de volgende gebruikersvriendelijke namen: **FN** = **Voornaam**, **LN** = **Achternaam**, **FI** = **Eerste initiaal**, **PHONE** = **Telefoon**, **GEN** = **Geslacht**, **DOB** = **Geboortedatum**, **ST** = **Staat**, **CT** = **Plaats**, **ZIP** = **Postcode**, **COUNTRY** = **Land/regio**

1. Selecteer de segmenten die u wilt exporteren.

1. Selecteer **Opslaan**.

## <a name="export-the-data"></a>De gegevens exporteren

U kunt [gegevens op aanvraag exporteren](export-destinations.md). De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab).

## <a name="known-limitations"></a>Bekende beperkingen

- Maximaal 10 miljoen klantprofielen per export naar Facebook Ads Manager 
- Exporteren naar Facebook Ads Manager is beperkt tot segmenten
- Segmenten met in totaal 10 miljoen profielen exporteren kan tot 90 minuten duren

## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar Facebook Ads Manager te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat Facebook Ads voldoet aan uw privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.
Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]