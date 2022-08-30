---
title: Segmenten exporteren naar LinkedIn Ads (preview)
description: Procedure voor het configureren van de verbinding en voor het exporteren naar LinkedIn Ads.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4c3928e05db0ebda262b4ad3e928ce85f70035b9
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304697"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Segmenten exporteren naar LinkedIn Ads (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar LinkedIn Ads om matched audiences te maken. Gebruik de matched audiences voor de targeting van bedrijven en contactpersonen.

## <a name="prerequisites"></a>Vereisten

- Een [LinkedIn Campaign Manager-account](https://business.linkedin.com/marketing-solutions/ads) en bijbehorende beheerdersreferenties.
- Een [account-id van LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).
- [Segmenten geconfigureerd](segments.md) in Customer Insights.
- De geëxporteerde segmenten hebben ten minste één specifiek veld nodig, afhankelijk van of u [targeting van contactpersonen](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) of [targeting van bedrijven](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) kiest in LinkedIn. De mogelijke velden staan vermeld in de stap **Gegevensvergelijking** bij het [configureren van de export](#configure-an-export).

## <a name="known-limitations"></a>Bekende beperkingen

- Maximaal 100.000 klantprofielen per export naar LinkedIn Ads en dit kan tot 10 minuten duren.
- Alleen segmenten. Een segment moet minimaal 300 unieke profielen bevatten.

## <a name="set-up-connection-to-linkedin-ads"></a>De verbinding instellen met LinkedIn Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **LinkedIn Ads**.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Standaard zijn dit alleen beheerders. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Geef uw account-id van LinkedIn Campaign Manager op.

1. Bekijk [Gegevensprivacy en naleving](connections.md#data-privacy-and-compliance) en selecteer **Ik ga akkoord**.

1. Selecteer **Verbinden** om de verbinding te initialiseren.

1. Selecteer **Verifiëren met LinkedIn** en geef uw beheerdersreferenties voor LinkedIn Campaign Manager op.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen**.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie LinkedIn Ads. Neem contact op met een beheerder als er geen verbinding beschikbaar is.

1. Voer de naam in voor de export.

1. Kies of u gegevens wilt exporteren om [targeting van contactpersonen](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) of [targeting van bedrijve](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) uit te voeren op LinkedIn.

1. In de sectie **Gegevensvergelijking** selecteert u voor targeting van contactpersonen ten minste één veld met het e-mailadres, de Apple Ad ID, de Google Ad ID, de Google-gebruikers-id of voor- en achternaam van de klant. Als u kiest voor bedrijfstargeting, selecteert u ten minste één veld met een bedrijfsnaam, e-maildomein, LinkedIn-pagina-URL, Ticker-symbool of website.

1. Voeg desgewenst velden toe om uw export verder te definiëren. Selecteer **Kenmerk toevoegen** om deze velden toe te wijzen.

1. Selecteer de segmenten die u wilt exporteren. De matched audiences in LinkedIn Campaign Manager worden automatisch gemaakt met de naam van de segmenten die u hebt geselecteerd om te exporteren. Elk segment resulteert in een aparte matched audience.

1. Selecteer **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
