---
title: Customer Insights-gegevens exporteren naar Salesforce Marketing Cloud
description: Leer hoe u de verbinding configureert en exporteert naar Salesforce Marketing Cloud.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314597"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a>Segmenten en andere gegevens exporteren naar Salesforce Marketing Cloud (preview)

Gebruik uw klantgegevens in Salesforce Marketing Cloud door ze te exporteren via een SFTP-locatie (Secure File Transfer Protocol).

## <a name="prerequisites-for-connection"></a>Vereisten voor verbinding

- Beschikbaarheid van een SFTP-host en bijbehorende beheerdersreferenties. [Procedure voor het instellen van SFTP-locaties voor Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a>Bekende beperkingen

- Hoe lang een export duurt, is afhankelijk van uw systeemprestaties. We raden twee CPU-cores en 1 Gb geheugen aan als minimale configuratie van uw server. 
- Het exporteren van entiteiten met maximaal 100 miljoen klantprofielen kan 90 minuten duren bij gebruik van de aanbevolen minimale configuratie. 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>De verbinding met Salesforce Marketing Cloud instellen

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Salesforce Marketing Cloud** om de verbinding te configureren.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Geef **Gebruikersnaam**, **Wachtwoord**, **Hostnaam** en **Exportmap** voor uw SFTP-account op.

1. Selecteer **Verifiëren** om de verbinding te testen.

1. Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

U kunt deze export configureren als u toegang hebt tot een verbinding van dit type. Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Bestemming toevoegen** om een nieuwe export te maken.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie SFTP. Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.

1. Kies of u uw gegevens **Gzipped** of **Uitgepakt** wilt exporteren en geef het **veldscheidingsteken** voor de geëxporteerde bestanden op.

1. Selecteer de entiteiten, bijvoorbeeld segmenten, die u wilt exporteren.

   > [!NOTE]
   > Elke geselecteerde entiteit wordt bij het exporteren opgesplitst in maximaal vijf uitvoerbestanden. 

1. Selecteer **Opslaan**.

Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.

De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab). U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand). 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Customer Insights-gegevens importeren vanuit SFTP-locatie naar Salesforce Marketing Cloud

1. Maak [gegevensextensies in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) om het Customer Insights-gegevensbestand te importeren vanuit de SFTP-locatie.

2. [Importeer de gegevens vanuit de SFTP-locatie](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) in de Salesforce Marketing Cloud-gegevensextensie. 

3. Stel de automatisering in om de gegevens te importeren in de gegevensextensies. Leer meer over [automatiseringen voor het neerzetten van bestanden en geplande automatiseringen](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Definieer een [automatisering van het neerzetten van bestanden](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) of een [geplande automatisering](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5). 

Hier is een voorbeeld van [een automatisering met SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens via SFTP te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat de exportbestemming voldoet aan uw privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.
Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
