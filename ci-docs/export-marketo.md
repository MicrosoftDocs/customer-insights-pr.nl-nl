---
title: Segmenten exporteren naar Marketo (preview)
description: Leer hoe u de verbinding configureert en exporteert naar Marketo.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8cd24cf436bd5fdfd4ec3834d35baa1495e37ca4
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053199"
---
# <a name="export-segments-to-marketo-preview"></a>Segmenten exporteren naar Marketo (preview)

Exporteer segmenten van geharmoniseerde klantprofielen om campagnes te genereren, e-mailmarketing te bieden en specifieke groepen klanten te gebruiken met Marketo.

## <a name="prerequisites-for-connection"></a>Vereisten voor verbinding

-   U hebt een [Marketo-account](https://login.marketo.com/) en bijbehorende beheerdersreferenties nodig.
-   Er zijn bestaande lijsten met bijbehorende id's in Marketo. Zie [Marketo-lijsten](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) voor meer informatie.
-   U hebt [geconfigureerde segmenten](segments.md).
-   Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.

## <a name="known-limitations"></a>Bekende beperkingen

- Tot 1 miljoen klantprofielen per export naar Marketo.
- Exporteren naar Marketo is beperkt tot segmenten.
- Het exporteren van segmenten met in totaal 1 miljoen klantprofielen kan tot drie uur duren. 
- Het aantal klantprofielen dat u kunt exporteren naar Marketo, is afhankelijk van en wordt beperkt door uw contract met Marketo.

## <a name="set-up-connection-to-marketo"></a>Verbinding met Marketo instellen

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Marketo** om de verbinding te configureren.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Voer uw **[Marketo-client-id, clientgeheim en REST-eindpunt hostnaam](https://developers.marketo.com/rest-api/authentication/)** in. De hostnaam van het REST-eindpunt is alleen de hostnaam zonder `https://`. Voorbeeld: `xyz-abc-123.mktorest.com`. 

1. Selecteer **Ik ga akkoord** om de **Gegevensprivacy en naleving** te bevestigen en selecteer **Verbinden** om de verbinding met Marketo te initialiseren.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

U kunt deze export configureren als u toegang hebt tot een verbinding van dit type. Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Bestemming toevoegen** om een nieuwe export te maken.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie Marketo. Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.

1. Voer uw **[Lijst-id van Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** in. De lijst-ID is een puur numerieke waarde. Als uw lijst-id van Marketo bijvoorbeeld ST12345A7 is, verwijdert u het teken voor en na de cijfers en voert u `12345` in. 

1. Selecteer in de sectie **Gegevensvergelijking** ten minste één veld dat het e-mailadres van een klant of de Marketo-id van een klant vertegenwoordigt. 

1. Optioneel kunt u **Voornaam**, **Achternaam**, **Plaats**, **Staat** en **Land/regio** exporteren om meer gepersonaliseerde e-mails te maken. Selecteer **Kenmerk toevoegen** om deze velden toe te wijzen.

1. Selecteer de segmenten die u wilt exporteren. U kunt in totaal tot 1 miljoen klantprofielen exporteren naar Marketo.

1. Selecteer **Opslaan**.

Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.

De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab). U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand). In Marketo vindt u nu uw segmenten onder [Marketo-lijsten](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).


## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar Marketo te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat Marketo voldoet aan uw privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.
Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.


[!INCLUDE [footer-include](includes/footer-banner.md)]
