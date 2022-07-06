---
title: Segmenten exporteren naar Braze (preview)
description: Ontdek hoe u de verbinding met Braze configureert en exporteert.
ms.date: 06/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 314a61f82c4040a8dbd6dff1dd5d92e20464f82a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081109"
---
# <a name="export-segments-to-braze-preview"></a>Segmenten exporteren naar Braze (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar Braze en gebruik deze voor marketingactiviteiten.

## <a name="prerequisites"></a>Vereisten

- Een [Braze-account](https://www.braze.com/) en bijbehorende beheerdersreferenties.
- Bestaande [segmenten in Braze](https://www.braze.com/docs/user_guide/engagement_tools/segments/creating_a_segment/).
- [Segmenten geconfigureerd](segments.md) in Customer Insights.
- Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld dat een e-mailadres en een Braze-klant-id vertegenwoordigt.

## <a name="known-limitations"></a>Bekende beperkingen

- Exporteren naar Braze is beperkt tot segmenten.
- Het exporteren van tot 1 miljoen klantprofielen naar Braze kan tot 40 minuten duren.
- Het aantal klantprofielen dat u kunt exporteren naar Braze, is afhankelijk van en wordt beperkt door uw contract met Braze.

## <a name="set-up-connection-to-braze"></a>Verbinding met Braze instellen

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Braze** om de verbinding te configureren.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Geef uw [Braze API-sleutel](https://www.braze.com/docs/api/basics/) op om door te gaan met aanmelden.

1. Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.

1. Selecteer **Verbinden** om de verbinding met Braze te initialiseren.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

U kunt deze export configureren als u toegang hebt tot een verbinding van dit type. Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Bestemming toevoegen** om een nieuwe export te maken.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie Braze. Als u deze sectie niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.  

1. Voeg een **weergavenaam** toe voor uw export.

1. Voeg de API-identifier toe van het Braze-segment waarnaar u wilt exporteren in het veld **API-id voor Braze Segment**. U kunt de id vinden in de segmentdetails op het Braze-platform.

1. In de sectie **Gegevensvergelijking** selecteert u in het veld **E-mail** het veld dat het e-mailadres van een klant vertegenwoordigt. Selecteer in het veld **Klant-id** het veld dat de Braze-id van de klant vertegenwoordigt. Dit is vereist om segmenten naar Braze te exporteren. U kunt eventueel meer velden kiezen.

1. Selecteer **Save**.

Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.

De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab). U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar Braze te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens in uw opdracht overdragen, maar het is uw verantwoordelijkheid ervoor te zorgen dat Braze voldoet aan eventuele privacy- of beveiligingsverplichtingen die u hebt. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.

Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.
