---
title: Segmenten exporteren naar Constant Contact (preview)
description: Leer hoe u de verbinding configureert en exporteert naar Constant Contact.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4d2ec29c194dc481ee40048b8ecbed813291b4d2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196480"
---
# <a name="export-segments-to-constant-contact-preview"></a>Segmenten exporteren naar Constant Contact (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar Constant Contact en gebruik deze voor marketingactiviteiten.

## <a name="prerequisites"></a>Vereisten

- Een [Constant Contact-account](https://www.constantcontact.com/account-home) en bijbehorende beheerdersreferenties.
- Een [id van Constant Contact-lijst](https://app.constantcontact.com/pages/contacts/ui#lists) Open een lijst in Constant Contact om de lijst-id in de URL te vinden.
- [Segmenten geconfigureerd](segments.md) in Customer Insights.
- Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.

## <a name="known-limitations"></a>Bekende beperkingen

- Maximaal 1 miljoen klantprofielen per export naar Constant Contact en dit kan tot één uur duren. Het aantal klantprofielen dat u kunt exporteren naar Constant Contact, is afhankelijk van uw contract met Constant Contact.
- Alleen segmenten.

## <a name="set-up-connection-to-constant-contact"></a>Verbinding instellen met Constant Contact

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Constant Contact**.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Standaard zijn dit alleen beheerders. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Bekijk [Gegevensprivacy en naleving](connections.md#data-privacy-and-compliance) en selecteer **Ik ga akkoord**.

1. Selecteer **Verbinden** om de verbinding te initialiseren.

1. Selecteer **Verifiëren met Constant Contact** en geef uw beheerdersreferenties op voor Constant Contact.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen**.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie Constant Contact. Neem contact op met een beheerder als er geen verbinding beschikbaar is.

1. Voer de naam in voor de export.

1. Voer uw **Id van Constant Contact-lijst** in.

1. In de sectie **Gegevensvergelijking** selecteert u in het veld **E-mail** het veld dat het e-mailadres van een klant vertegenwoordigt.

1. Optioneel kunt u **Voornaam** en **Achternaam** exporteren als extra velden om meer gepersonaliseerde e-mails te maken. Selecteer **Kenmerk toevoegen** om deze velden toe te wijzen.

1. Selecteer de segmenten die u wilt exporteren.

1. Selecteer **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
