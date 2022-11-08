---
title: Segmenten exporteren naar Marketo (preview)
description: Leer hoe u de verbinding configureert en exporteert naar Marketo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cba40b74b86a40fc41db856760c9361b755a8864
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724934"
---
# <a name="export-segments-to-marketo-preview"></a>Segmenten exporteren naar Marketo (preview)

Exporteer segmenten van geharmoniseerde klantprofielen om campagnes te genereren, e-mailmarketing te bieden en specifieke groepen klanten te gebruiken met Marketo.

## <a name="prerequisites"></a>Vereisten

- Een [Marketo-account](https://login.marketo.com/) en bijbehorende beheerdersreferenties.
- Een [client-id, clientgeheim en hostnaam van REST-eindpunt van Marketo](https://developers.marketo.com/rest-api/authentication/).
- [Bestaande lijsten in Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) en de bijbehorende id's.
- [Geconfigureerde segmenten](segments.md).
- Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.

## <a name="known-limitations"></a>Bekende beperkingen

- Privékoppeling in combinatie met Bring your own storage (BYOS) wordt niet ondersteund.
- Maximaal 1 miljoen klantprofielen per export naar Marketo en dit kan tot 3 uur duren. Het aantal klantprofielen dat u kunt exporteren naar Marketo, is afhankelijk van uw contract met Marketo.
- Alleen segmenten.

## <a name="set-up-connection-to-marketo"></a>Verbinding met Marketo instellen

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Marketo**.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Standaard zijn dit alleen beheerders. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Voer uw **client-id, clientgeheim en hostnaam van REST-eindpunt van Marketo** in. De hostnaam van het REST-eindpunt is alleen de hostnaam zonder https://. Voorbeeld: xyz-abc-123.mktorest.com.

1. Bekijk [Gegevensprivacy en naleving](connections.md#data-privacy-and-compliance) en selecteer **Ik ga akkoord**.

1. Selecteer **Verbinden** om de verbinding te initialiseren.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen**.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie Marketo. Neem contact op met een beheerder als er geen verbinding beschikbaar is.

1. Voer de naam in voor de export.

1. Voer uw **Lijst-id van Marketo** in. De lijst-ID is een puur numerieke waarde. Als uw lijst-id van Marketo bijvoorbeeld ST12345A7 is, verwijdert u het teken voor en na de cijfers en voert u *12345* in.

1. Selecteer in de sectie **Gegevensvergelijking** ten minste één veld dat het e-mailadres van een klant of de Marketo-id van een klant vertegenwoordigt.

1. Optioneel kunt u **Voornaam**, **Achternaam**, **Plaats**, **Staat** en **Land/regio** exporteren om meer gepersonaliseerde e-mails te maken. Selecteer **Kenmerk toevoegen** om deze velden toe te wijzen.

1. Selecteer de segmenten die u wilt exporteren.

1. Selecteer **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

In Marketo vindt u uw segmenten onder [Marketo-lijsten](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

[!INCLUDE [footer-include](includes/footer-banner.md)]
