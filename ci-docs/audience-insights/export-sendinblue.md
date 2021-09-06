---
title: Gegevens uit Customer Insights exporteren naar Sendinblue
description: Leer hoe u de verbinding configureert en exporteert naar Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: be52554763b57e1c1ef2f960d52bbae79ac9827913c97ac73b429f66bbf4db37
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036049"
---
# <a name="export-segments-to-sendinblue-preview"></a>Segmenten exporteren naar Sendinblue (preview)

Exporteer de segmenten van geharmoniseerde klantprofielen om campagnes te genereren, e-mailmarketing te bieden en specifieke groepen met klanten te gebruiken met Sendinblue.

## <a name="prerequisites-for-connection"></a>Vereisten voor verbinding

-   U hebt een [Sendinblue-account](https://www.sendinblue.com/) en bijbehorende beheerdersreferenties.
-   Er zijn bestaande lijsten in Sendinblue en de bijbehorende id's.
-   U hebt [geconfigureerde segmenten](segments.md).
-   Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.

## <a name="known-limitations"></a>Bekende beperkingen

- Tot 1 miljoen profielen per export naar Sendinblue.
- Het exporteren naar Sendinblue is beperkt tot segmenten.
- Het exporteren van segmenten met in totaal 1 miljoen profielen kan tot 90 minuten duren. 
- Het aantal profielen dat u kunt exporteren naar Sendinblue is afhankelijk en beperkt van uw contract met Sendinblue.

## <a name="set-up-connection-to-sendinblue"></a>Verbinding instellen met Sendinblue

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Sendinblue** om de verbinding te configureren.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Standaard zijn dit alleen beheerders. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Voer uw **[SendinBlue API-sleutel](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)** in.

1. Selecteer **Ik ga akkoord** om **Gegevensprivacy en naleving** te bevestigen en selecteer **Verbinden** om de verbinding met Sendinblue te initialiseren.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

U kunt deze export configureren als u toegang hebt tot een verbinding van dit type. Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Bestemming toevoegen** om een nieuwe export te maken.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie Sendinblue. Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.

1. Voer uw **Sendinblue-lijst-id** in 

1. Selecteer in de sectie **Gegevensvergelijking** in het veld **E-mail** het veld in uw geharmoniseerde klantprofiel voor het e-mailadres van een klant. 

1. Optioneel kunt u **Voornaam**, **Achternaam** en **Telefoon** exporteren om meer gepersonaliseerde e-mails te maken. Selecteer **Kenmerk toevoegen** om deze velden toe te wijzen.

1. Selecteer de segmenten die u wilt exporteren. 

1. Selecteer **Opslaan**.

Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.

De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab). U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights inschakelt om gegevens te verzenden naar Sendinblue, staat u de overdracht van gegevens buiten de nalevingsgrens toe voor Dynamics 365 Customer Insights, inclusief mogelijk gevoelige gegevens zoals persoonsgegevens. Microsoft zal dergelijke gegevens in uw opdracht overdragen, maar u bent er zelf verantwoordelijk voor dat Sendinblue voldoet aan alle privacy- of beveiligingsverplichtingen die u hebt. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.
Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
