---
title: Customer Insights-gegevens exporteren naar SFTP-hosts
description: Meer informatie over het configureren van de verbinding met een SFTP-host.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643497"
---
# <a name="connector-for-sftp-preview"></a>Connector voor SFTP (preview)

Gebruik uw klantgegevens in toepassingen van derden door deze te exporteren naar een SFTP-host (Secure File Transfer Protocol).

## <a name="prerequisites"></a>Vereisten

- Beschikbaarheid van een SFTP-host en bijbehorende referenties.

## <a name="connect-to-sftp"></a>Verbinding maken met SFTP

1. Ga naar **Beheer** > **Exportbestemmingen**.

1. Selecteer onder **SFTP** de optie **Instellen**.

1. Geef uw bestemming een herkenbare naam in het veld **Weergavenaam**.

1. Geef **Gebruikersnaam**, **Wachtwoord** en **Hostnaam** voor uw SFTP-account op. Voorbeeld: als de hoofdmap van uw SFTP-server /hoofdmap/map is en u wilt dat de gegevens worden geëxporteerd naar /hoofdmap/map/ci_export_doelmap, dan moet de host sftp://<server_address>/ci_export_doelmap" zijn.

1. Selecteer **Verifiëren** om de verbinding te testen.

1. Kies na succesvolle verificatie of u uw gegevens **Gezipt** of **Niet-gezipt** wilt exporteren en selecteer daarna het **veldscheidingsteken** voor de geëxporteerde bestanden.

1. Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.

1. Selecteer **Volgende** om te beginnen met het configureren van de export.

## <a name="configure-the-connection"></a>De verbinding configureren

1. Selecteer de **klantkenmerken** die u wilt exporteren. U kunt een of meer kenmerken exporteren.

1. Selecteer **Volgende**.

1. Selecteer de segmenten die u wilt exporteren.

1. Selecteer **Opslaan**.

## <a name="export-the-data"></a>De gegevens exporteren

U kunt [gegevens op aanvraag exporteren](export-destinations.md). De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab).

## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens via SFTP te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat de exportbestemming voldoet aan uw privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.
Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.
