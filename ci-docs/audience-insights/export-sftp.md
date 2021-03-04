---
title: Customer Insights-gegevens exporteren naar SFTP-hosts
description: Meer informatie over het configureren van de verbinding met een SFTP-host.
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267992"
---
# <a name="connector-for-sftp-preview"></a>Connector voor SFTP (preview)

Gebruik uw klantgegevens in toepassingen van derden door deze te exporteren naar een SFTP-host (Secure File Transfer Protocol).

## <a name="prerequisites"></a>Vereisten

- Beschikbaarheid van een SFTP-host en bijbehorende inloggegevens.

## <a name="connect-to-sftp"></a>Verbinding maken met SFTP

1. Ga naar **Beheer** > **Exportbestemmingen**.

1. Selecteer onder **SFTP** de optie **Instellen**.

1. Geef uw bestemming een herkenbare naam in het veld **Weergavenaam**.

1. Geef **Gebruikersnaam**, **Wachtwoord**, **Hostnaam** en **Exportmap** voor uw SFTP-account op.

1. Selecteer **Verifiëren** om de verbinding te testen.

1. Kies na succesvolle verificatie of u uw gegevens **Gzipped** of **Uitgepakt** wilt exporteren en selecteer het **veldscheidingsteken** voor de geëxporteerde bestanden.

1. Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.

1. Selecteer **Volgende** om te beginnen met het configureren van de export.

## <a name="configure-the-export"></a>De export configureren

1. Selecteer de entiteiten, bijvoorbeeld segmenten, die u wilt exporteren.

   > [!NOTE]
   > Elke geselecteerde entiteit bevat bij het exporteren maximaal vijf uitvoerbestanden. 

1. Selecteer **Opslaan**.

## <a name="export-the-data"></a>De gegevens exporteren

U kunt [gegevens op aanvraag exporteren](export-destinations.md). De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab).

## <a name="known-limitations"></a>Bekende beperkingen

- Hoe lang een export duurt, is afhankelijk van uw systeemprestaties. We raden twee CPU-cores en 1 Gb geheugen aan als minimale configuratie van uw server. 
- Het exporteren van entiteiten met maximaal 100 miljoen klantprofielen kan 90 minuten duren bij gebruik van de aanbevolen minimale configuratie van twee CPU-cores en 1 Gb geheugen. 

## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens via SFTP te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat de exportbestemming voldoet aan uw privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.
Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]