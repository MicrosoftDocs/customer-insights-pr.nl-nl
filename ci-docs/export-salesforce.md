---
title: Gegevens exporteren naar Marketing Cloud van Salesforce (preview)
description: Leer hoe u de verbinding configureert en exporteert naar Salesforce Marketing Cloud.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197032"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Gegevens exporteren naar Marketing Cloud van Salesforce (preview)

Gebruik uw klantgegevens in Salesforce Marketing Cloud door ze te exporteren via een SFTP-locatie (Secure File Transfer Protocol).

## <a name="prerequisites"></a>Vereisten

- Een [SFTP-host voor Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) en bijbehorende beheerdersreferenties.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>De verbinding met Salesforce Marketing Cloud instellen

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Salesforce Marketing Cloud**.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Standaard zijn dit alleen beheerders. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Geef **Gebruikersnaam**, **Wachtwoord**, **Hostnaam** en **Exportmap** voor uw SFTP-account op.

1. Selecteer **Verifiëren** om de verbinding te testen.

1. Bekijk [Gegevensprivacy en naleving](connections.md#data-privacy-and-compliance) en selecteer **Ik ga akkoord**.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen**.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie SFTP. Neem contact op met een beheerder als er geen verbinding beschikbaar is.

1. Voer de naam in voor de export.

1. Kies of u uw gegevens **Gzipped** of **Uitgepakt** wilt exporteren en geef het **veldscheidingsteken** voor de geëxporteerde bestanden op.

1. Selecteer de entiteiten, bijvoorbeeld segmenten, die u wilt exporteren.

   > [!NOTE]
   > Elke geselecteerde entiteit wordt bij het exporteren opgesplitst in maximaal vijf uitvoerbestanden.

1. Selecteer **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Customer Insights-gegevens importeren vanuit SFTP-locatie naar Salesforce Marketing Cloud

1. Maak [gegevensextensies in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) om het Customer Insights-gegevensbestand te importeren vanuit de SFTP-locatie.

2. [Importeer de gegevens vanuit de SFTP-locatie](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) in de Salesforce Marketing Cloud-gegevensextensie.

3. Stel de automatisering in om de gegevens te importeren in de gegevensextensies. Leer meer over [automatiseringen voor het neerzetten van bestanden en geplande automatiseringen](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Definieer een [automatisering van het neerzetten van bestanden](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) of een [geplande automatisering](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).

Hier is een voorbeeld van [een automatisering met SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

[!INCLUDE [footer-include](includes/footer-banner.md)]
