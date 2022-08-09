---
title: Segmenten exporteren naar Mailchimp (preview)
description: Leer hoe u de verbinding configureert en exporteert naar Mailchimp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 54aec10e24b6356e2e4317cf33e740a1a086a2dd
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196848"
---
# <a name="export-segments-to-mailchimp-preview"></a>Segmenten exporteren naar Mailchimp (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar Mailchimp om nieuwsbrieven en e-mailcampagnes te maken.

## <a name="prerequisites"></a>Vereisten

- Een [Mailchimp-account](https://mailchimp.com/) en bijbehorende beheerdersreferenties.
- [Bestaande doelgroepen in Mailchimp](https://mailchimp.com/help/create-audience/) en bijbehorende [doelgroep-id´s](https://mailchimp.com/help/find-audience-id/).
- [Geconfigureerde segmenten](segments.md).
- Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.

## <a name="known-limitations"></a>Bekende beperkingen

- Maximaal 1 miljoen klantprofielen per export naar Mailchimp en dit kan tot drie uur duren. Het aantal klantprofielen dat u kunt exporteren naar Mailchimp, is afhankelijk van uw contract met Mailchimp.
- Alleen segmenten.

## <a name="set-up-connection-to-mailchimp"></a>Verbinding instellen met Mailchimp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Mailchimp**.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Standaard zijn dit alleen beheerders. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Bekijk [Gegevensprivacy en naleving](connections.md#data-privacy-and-compliance) en selecteer **Ik ga akkoord**.

1. Selecteer **Verbinden** om de verbinding te initialiseren.

1. Selecteer **Verifiëren met Mailchimp** en geef uw Mailchimp-referenties op.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen**.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie Mailchimp. Neem contact op met een beheerder als er geen verbinding beschikbaar is.

1. Voer de naam in voor de export.

1. Voer uw **doelgroep-id van Mailchimp** in

1. In de sectie **Gegevensvergelijking** selecteert u in het veld **E-mail** het veld dat het e-mailadres van een klant vertegenwoordigt.

1. Optioneel kunt u **Voornaam** en **Achternaam** exporteren om meer gepersonaliseerde e-mails te maken. Selecteer **Kenmerk toevoegen** om deze velden toe te wijzen.

1. Selecteer de segmenten die u wilt exporteren.

1. Selecteer **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
