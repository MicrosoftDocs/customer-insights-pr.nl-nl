---
title: Customer Insights-gegevens exporteren naar Marketo
description: Leer hoe u de verbinding configureert en exporteert naar Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0d5eaa769973c861d89287bba0ed29509ab2efc653bdd8e177cc49b3560c698e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033487"
---
# <a name="export-segments-to-marketo-preview"></a>Segmenten exporteren naar Marketo (preview)

Exporteer segmenten van geharmoniseerde klantprofielen om campagnes te genereren, e-mailmarketing te bieden en specifieke groepen klanten te gebruiken met Marketo.

## <a name="prerequisites-for-connection"></a>Vereisten voor verbinding

-   U hebt een [Marketo-account](https://login.marketo.com/) en bijbehorende beheerdersreferenties nodig.
-   Er zijn bestaande lijsten met bijbehorende id's in Marketo. Zie [Marketo-lijsten](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) voor meer informatie.
-   U hebt [geconfigureerde segmenten](segments.md).
-   Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.

## <a name="known-limitations"></a>Bekende beperkingen

- Maximaal 1 miljoen profielen per export naar Marketo.
- Exporteren naar Marketo is beperkt tot segmenten.
- Segmenten met in totaal 1 miljoen profielen exporteren kan tot 3 uur duren. 
- Het aantal profielen dat u naar Marketo kunt exporteren, is afhankelijk van uw contract met Marketo.

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

1. Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant. 

1. Optioneel kunt u **Voornaam**, **Achternaam**, **Plaats**, **Staat** en **Land/regio** exporteren om meer gepersonaliseerde e-mails te maken. Selecteer **Kenmerk toevoegen** om deze velden toe te wijzen.

1. Selecteer de segmenten die u wilt exporteren. U kunt in totaal tot 1 miljoen klantprofielen exporteren naar Marketo.

1. Selecteer **Opslaan**.

Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.

De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab). U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand). In Marketo vindt u nu uw segmenten onder [Marketo-lijsten](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).


## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar Marketo te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat Marketo voldoet aan uw privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.
Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
