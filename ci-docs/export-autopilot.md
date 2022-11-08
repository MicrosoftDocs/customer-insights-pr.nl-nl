---
title: Segmenten exporteren naar Autopilot (preview)
description: Leer hoe u de verbinding configureert en exporteert naar Autopilot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b4b14ba9de2c7e20175fac664a705f2212a411fd
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724751"
---
# <a name="export-segments-to-autopilot-preview"></a>Segmenten exporteren naar Autopilot (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar Autopilot en gebruik ze voor e-mailmarketing in Autopilot.

## <a name="prerequisites-for-a-connection"></a>Vereisten voor een verbinding

- Een [Autopilot-account](https://www.autopilothq.com/) en bijbehorende beheerdersreferenties.
- Een [API-sleutel van Autopilot](https://autopilot.docs.apiary.io/#)
- [Segmenten geconfigureerd](segments.md) in Customer Insights.
- Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.

## <a name="known-limitations"></a>Bekende beperkingen

- Privékoppeling in combinatie met Bring your own storage (BYOS) wordt niet ondersteund.
- Maximaal 100.000 klantprofielen per export naar Autopilot en dit kan tot een paar uur duren. Het aantal klantprofielen dat u kunt exporteren naar Autopilot, is afhankelijk van uw contract met Autopilot.
- Alleen segmenten.

## <a name="set-up-connection-to-autopilot"></a>Verbinding instellen met Autopilot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Autopilot**.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Standaard zijn dit alleen beheerders. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Voer uw API-sleutel voor Autopilot in.

1. Bekijk [Gegevensprivacy en naleving](connections.md#data-privacy-and-compliance) en selecteer **Ik ga akkoord**.

1. Selecteer **Verbinden** om de verbinding te initialiseren.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen**.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie Autopilot. Neem contact op met een beheerder als er geen verbinding beschikbaar is.

1. Voer de naam in voor de export.

1. In de sectie **Gegevensvergelijking** selecteert u in het veld **E-mail** het veld dat het e-mailadres van een klant vertegenwoordigt.

1. Exporteer eventueel andere velden, zoals **Voornaam** en **Achternaam**.

1. Selecteer de segmenten die u wilt exporteren en houd u aan de bekende beperkingen.

1. Selecteer **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
