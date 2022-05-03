---
title: LiveRamp-connector
description: Leer hoe u de verbinding configureert en exporteert naar LiveRamp.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 973f69c94c625fe4ec543ca5fb57289c4102ea97
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646431"
---
# <a name="export-segments-to-liverampreg-preview"></a>Segmenten exporteren naar LiveRamp&reg; (preview)

Activeer uw gegevens in LiveRamp om verbinding te maken met meer dan 500 platforms op digitaal, sociaal en tv. Werk met uw gegevens in LiveRamp om advertentiecampagnes te targeten, onderdrukken en personaliseren.

## <a name="prerequisites-for-a-connection"></a>Vereisten voor een verbinding

- U hebt een LiveRamp-abonnement nodig om deze connector te kunnen gebruiken.
- U kunt een abonnement nemen door rechtstreeks [contact op te nemen met LiveRamp](https://liveramp.com/contact/). [Meer informatie over LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="set-up-connection-to-liveramp"></a>Verbinding instellen met LiveRamp

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **LiveRamp** om de verbinding te configureren.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Verschaf een **gebruikersnaam** en **wachtwoord** voor uw LiveRamp Secure FTP-account (SFTP).
Deze referenties kunnen verschillen van uw LiveRamp Onboarding-referenties.

1. Selecteer **Verifiëren** om de verbinding met LiveRamp te testen.

1. Geef na succesvolle verificatie uw toestemming voor **Gegevensprivacy en naleving** door het selectievakje **Ik ga akkoord** in te schakelen.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

U kunt deze export configureren als u toegang hebt tot een verbinding van dit type. Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Bestemming toevoegen** om een nieuwe export te maken.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie LiveRamp. Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.

1. Selecteer in het veld **Uw sleutelidentificatie kiezen** de optie **E-mail**, **Naam en adres** of **Telefoon** om naar LiveRamp te sturen voor identiteitsresolutie.
   > [!div class="mx-imgBorder"]
   > ![LiveRamp-connector met kenmerktoewijzing.](media/export-liveramp-segments.png "LiveRamp-connector met kenmerktoewijzing")

1. Wijs de bijbehorende kenmerken toe van uw entiteit *Klant* voor de geselecteerde sleutel-id.

1. Selecteer **Kenmerk toevoegen** om meer kenmerken toe te wijzen om naar LiveRamp te verzenden.

   > [!TIP]
   > Als u meer kenmerken voor sleutel-id's naar LiveRamp verzendt, krijgt u waarschijnlijk een hoger overeenkomstpercentage.

1. Selecteer de segmenten die u naar LiveRamp wilt exporteren.

1. Selecteer **Opslaan**.

Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.

De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab). U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar LiveRamp te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat LiveRamp voldoet aan uw privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.
Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
