---
title: Segmenten exporteren naar DotDigital (preview)
description: Leer hoe u de verbinding configureert en exporteert naar DotDigital.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: af0cce4edb9d47247c79ae08491366349da98b1c
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081161"
---
# <a name="export-segments-to-dotdigital-preview"></a>Segmenten exporteren naar DotDigital (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar DotDigital-adresboeken en gebruik ze voor campagnes, e-mailmarketing en om klantsegmenten op te bouwen met DotDigital. 

## <a name="prerequisites-for-a-connection"></a>Vereisten voor een verbinding

-   U hebt een [DotDigital-account](https://dotdigital.com/) en hebt een [API-gebruiker](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user) gemaakt. U hebt de API-gebruikersreferenties nodig om een verbinding te maken
-   Er zijn bestaande adresboeken met bijbehorende id's in DotDigital. De id is te vinden in de URL wanneer u een adresboek selecteert en opent. Zie [DotDigital-adresboeken](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) voor meer informatie.
-   U hebt [segmenten geconfigureerd](segments.md) in Customer Insights.
-   Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.

## <a name="known-limitations"></a>Bekende beperkingen

- Tot 1 miljoen klantprofielen per export naar DotDigital.
- Exporteren naar DotDigital is beperkt tot segmenten.
- Het exporteren van segmenten met in totaal 1 miljoen klantprofielen kan tot 3 uur duren vanwege beperkingen aan de kant van de provider. 
- Het aantal klantprofielen dat u kunt exporteren naar DotDigital, is afhankelijk van en wordt beperkt door uw contract met DotDigital.

## <a name="set-up-connection-to-dotdigital"></a>Verbinding met DotDigital instellen

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **DotDigital** om de verbinding te configureren.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Voer uw **DotDigital API-gebruikersnaam en wachtwoord** in. 

1. Voer uw **[DotDigital adresboek-id](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)** in.

1. Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen.

1. Selecteer **Verbinden** om de verbinding met DotDigital te initialiseren.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Opslaan** om de verbinding te voltooien. 

## <a name="configure-an-export"></a>Een export configureren

U kunt deze export configureren als u toegang hebt tot een verbinding van dit type. Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Bestemming toevoegen** om een nieuwe export te maken.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie DotDigital. Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.


1. In de sectie **Gegevensvergelijking** selecteert u in het veld **E-mail** het veld dat het e-mailadres van een klant vertegenwoordigt. Herhaal dezelfde stappen voor andere optionele velden, zoals **Voornaam**, **Achternaam**, **Voor- en achternaam**, **Geslacht** en **Postcode**.

1. Selecteer de segmenten die u wilt exporteren. U kunt in totaal tot 1 miljoen klantprofielen exporteren naar DotDigital.

1. Selecteer **Opslaan**.

Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.

De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab). U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand). 
 
In DotDigital kunt u nu uw segmenten vinden in [DotDigital-adresboeken](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).


## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar DotDigital te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat DotDigital voldoet aan uw privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.
Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.


[!INCLUDE [footer-include](includes/footer-banner.md)]
