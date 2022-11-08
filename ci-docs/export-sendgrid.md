---
title: Segmenten exporteren naar SendGrid (preview)
description: Leer hoe u de verbinding configureert en exporteert naar SendGrid.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 855e77055eeb24a2c6cff0d45cd23edf93cc0581
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724842"
---
# <a name="export-segments-to-sendgrid-preview"></a>Segmenten exporteren naar SendGrid (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar SendGrid en gebruik ze voor campagnes en e-mailmarketing in SendGrid.

## <a name="prerequisites"></a>Vereisten

- Een [SendGrid-account](https://sendgrid.com/) en bijbehorende beheerdersreferenties.
- [Bestaande contactpersonenlijsten in SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) en de bijbehorende id's.
- Een [API-sleutel voor SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).
- [Segmenten geconfigureerd](segments.md) in Customer Insights.
- Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.

## <a name="known-limitations"></a>Bekende beperkingen

- Privékoppeling in combinatie met Bring your own storage (BYOS) wordt niet ondersteund.
- Maximaal 100.000 klantprofielen kunnen in totaal naar SendGrid worden geëxporteerd en dit kan tot een paar uur duren. Het aantal klantprofielen dat u kunt exporteren naar SendGrid, is afhankelijk van uw contract met SendGrid.
- Alleen segmenten.

## <a name="set-up-connection-to-sendgrid"></a>Verbinding instellen met SendGrid

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **SendGrid**.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Standaard zijn dit alleen beheerders. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Voer uw **API-sleutel voor SendGrid** in.

1. Bekijk [Gegevensprivacy en naleving](connections.md#data-privacy-and-compliance) en selecteer **Ik ga akkoord**.

1. Selecteer **Verbinden** om de verbinding te initialiseren.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen**.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie SendGrid. Neem contact op met een beheerder als er geen verbinding beschikbaar is.

1. Voer de naam in voor de export.

1. Voer uw **lijst-id voor SendGrid** in.

1. In de sectie **Gegevensvergelijking** selecteert u in het veld **E-mail** het veld dat het e-mailadres van een klant vertegenwoordigt.

1. Selecteer desgewenst velden als **Voornaam**, **Achternaam**, **Land/regio**, **Staat**, **Plaats** en **Postcode**.

1. Selecteer de segmenten die u wilt exporteren en houd u aan de bekende beperkingen.

1. Selecteer **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
