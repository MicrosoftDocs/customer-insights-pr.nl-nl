---
title: Segmenten exporteren naar Omnisend (preview)
description: Leer hoe u de verbinding configureert en exporteert naar Omnisend.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c23d6d3538c4df6006c14064f95379169af06622
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196158"
---
# <a name="export-segments-to-omnisend-preview"></a>Segmenten exporteren naar Omnisend (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar Omnisend en gebruik deze voor marketingactiviteiten.

## <a name="prerequisites"></a>Vereisten

- Een [Omnisend-account](https://www.omnisend.com/) en bijbehorende beheerdersreferenties.
- Een [API-sleutel van Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).
- [Segmenten geconfigureerd](segments.md) in Customer Insights.
- Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.

## <a name="known-limitations"></a>Bekende beperkingen

- Er kunnen maximaal 1 miljoen klantprofielen naar Omnisend worden geëxporteerd en dit kan tot vier uur duren. Het aantal klantprofielen dat u kunt exporteren naar Omnisend, is afhankelijk van en wordt beperkt door uw contract met Omnisend.
- Alleen segmenten.

## <a name="set-up-connection-to-omnisend"></a>Verbinding instellen met Omnisend

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Omnisend**.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Standaard zijn dit alleen beheerders. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Voer uw Omnisend API-sleutel in.

1. Bekijk [Gegevensprivacy en naleving](connections.md#data-privacy-and-compliance) en selecteer **Ik ga akkoord**.

1. Selecteer **Verbinden** om de verbinding te initialiseren.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen**.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie Omnisend. Neem contact op met een beheerder als er geen verbinding beschikbaar is.

1. Voer de naam in voor de export.

1. In de sectie **Gegevensvergelijking** selecteert u in het veld **E-mail** het veld dat het e-mailadres van een klant vertegenwoordigt.

1. Optioneel kunt u **Voornaam**, **Achternaam**, **Adres**, **Land/regio**, **Staat**, **Plaats** en **Postcode** exporteren om meer gepersonaliseerde e-mails te maken. Selecteer **Kenmerk toevoegen** om deze velden toe te wijzen.

1. Selecteer de segmenten die u wilt exporteren.

1. Selecteer **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
