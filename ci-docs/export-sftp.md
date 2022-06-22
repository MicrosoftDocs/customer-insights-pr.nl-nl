---
title: Customer Insights-gegevens exporteren naar SFTP-hosts (met video)
description: Leer hoe u de verbinding configureert en exporteert naar een SFTP-locatie.
ms.date: 06/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b56d628c8286ba6697cccc9b002f609aa929951b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947178"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a>Segmenten en andere gegevens exporteren naar SFTP (preview)

Gebruik uw klantgegevens in toepassIngen van derden door ze te exporteren naar een SFTP-locatie (Secure File Transfer Protocol).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites-for-connection"></a>Vereisten voor verbinding

- Beschikbaarheid van een SFTP-host en bijbehorende inloggegevens.

## <a name="known-limitations"></a>Bekende beperkingen

- SFTP-bestemmingen achter firewalls worden momenteel niet ondersteund. 
- Hoe lang een export duurt, is afhankelijk van uw systeemprestaties. We raden twee CPU-cores en 1 Gb geheugen aan als minimale configuratie van uw server.
- Het exporteren van entiteiten met maximaal 100 miljoen klantprofielen kan 90 minuten duren bij gebruik van de aanbevolen minimale configuratie van twee CPU-cores en 1 Gb geheugen.

## <a name="set-up-connection-to-sftp"></a>Verbinding instellen MET SFTP

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **SFTP** om de verbinding te configureren.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Geef **Gebruikersnaam**, **Wachtwoord**, **Hostnaam** en **Exportmap** voor uw SFTP-account op.

1. Selecteer **Verifiëren** om de verbinding te testen.

1. Kies of u uw gegevens **Gzipped** of **Uitgepakt** wilt exporteren en geef het **veldscheidingsteken** voor de geëxporteerde bestanden op.

1. Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

U kunt deze export configureren als u toegang hebt tot een verbinding van dit type. Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Bestemming toevoegen** om een nieuwe export te maken.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie SFTP. Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.

1. Selecteer de entiteiten, bijvoorbeeld segmenten, die u wilt exporteren.

   > [!NOTE]
   > Elke geselecteerde entiteit wordt bij het exporteren opgesplitst in maximaal vijf uitvoerbestanden.

1. Selecteer **Opslaan**.

Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.

De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab).
U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand).

> [!TIP]
> Export van entiteiten die een grote hoeveelheid gegevens bevatten, kan leiden tot meerdere CSV-bestanden in dezelfde map voor elke export. Het splitsen van exports gebeurt om prestatieredenen om de tijd die nodig is om een export te voltooien tot een minimum te beperken.

## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens via SFTP te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat de exportbestemming voldoet aan uw privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.
Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
