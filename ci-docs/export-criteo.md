---
title: Customer Insights-gegevens exporteren naar Criteo
description: Ontdek hoe u de verbinding met Criteo configureert en exporteert.
ms.date: 05/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 854f5f0c53f053fc5d742d69a045db1926fec00c
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808764"
---
# <a name="export-segments-to-criteo-preview"></a>Segmenten exporteren naar Criteo (preview)

Exporteer segmenten van unified customer profiles om campagnes te genereren, bied e-mailmarketing en gebruik specifieke groepen met klanten met Criteo.

## <a name="prerequisites-for-connection"></a>Vereisten voor verbinding

-   U beschikt over een [Criteo Dynamics Retargeting-account](https://www.criteo.com/login/) en bijbehorende beheerdersreferenties.
-   U hebt [geconfigureerde segmenten](segments.md).
-   Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.

## <a name="known-limitations"></a>Bekende beperkingen

- Tot 1 miljoen klantprofielen per export naar Criteo.
- Exporteren naar Criteo is beperkt tot segmenten.
- Het exporteren van segmenten met in totaal 1 miljoen klantprofielen kan tot 30 minuten duren. 
- Het aantal klantprofielen dat u kunt exporteren naar Criteo, is afhankelijk van en wordt beperkt door uw contract met Criteo.

## <a name="set-up-connection-to-criteo"></a>Verbinding met Criteo instellen

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Criteo** om de verbinding te configureren.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Selecteer **Ik ga akkoord** om de **Gegevensprivacy en naleving** te bevestigen en selecteer **Verbinden** om de verbinding met Criteo te initialiseren.

1. Selecteer **Verifiëren met Criteo** en geef uw beheerdersgebruikersnaam en referenties voor Criteo op. 

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

U kunt deze export configureren als u toegang hebt tot een verbinding van dit type. Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Bestemming toevoegen** om een nieuwe export te maken.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie Criteo. Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar. 

1. In de sectie **Gegevensvergelijking** selecteert u in het veld **E-mail** het veld dat het e-mailadres van een klant vertegenwoordigt. 

1. Optioneel kunt u **Id van adverteerder** en **Naam** exporeteren

1. Selecteer de segmenten die u wilt exporteren. 

1. Selecteer **Save**.

Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.

De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab). U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar Criteo te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens in uw opdracht overdragen, maar het is uw verantwoordelijkheid ervoor te zorgen dat Criteo voldoet aan eventuele privacy- of beveiligingsverplichtingen die u hebt. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.
Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.


[!INCLUDE[footer-include](includes/footer-banner.md)]
