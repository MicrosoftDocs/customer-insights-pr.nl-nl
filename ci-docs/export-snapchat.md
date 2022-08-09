---
title: Segmenten exporteren naar Snapchat (preview)
description: Leer hoe u de verbinding configureert en exporteert naar Snapchat.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 85443dcb54ebd58182997fbb56a738901f2a051f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195376"
---
# <a name="export-segments-to-snapchat-preview"></a>Segmenten exporteren naar Snapchat (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar Snapchat en gebruik deze voor reclame.

## <a name="prerequisites"></a>Vereisten

- Een een [zakelijk Snapchat-account](https://business.snapchat.com/), een [Snapchat Ads-account](https://ads.snapchat.com/) en de bijbehorende beheerdersreferenties. U moet minimaal lid zijn van een organisatieaccount en gegevensbeheerder van een specifiek advertentieaccount.
- Ten minste één doelgroep in Snapchat Audience Manager van het type SAM (Snap Audience Match).
- [Snapchat-segment/doelgroep-id](https://businesshelp.snapchat.com/s/article/custom-audiences). De id van de doelgroep is te vinden in de URL nadat u de doelgroep in Snapchat Audience Manager hebt geselecteerd.
- [Segmenten geconfigureerd](segments.md) in Customer Insights.
- Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.

## <a name="known-limitations"></a>Bekende beperkingen

- Maximaal 1 miljoen klantprofielen, wat wel 15 minuten kan duren.
- Alleen segmenten.

## <a name="set-up-connection-to-snapchat"></a>Verbinding instellen met Snapchat

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Snapchat**.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Standaard zijn dit alleen beheerders. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Bekijk [Gegevensprivacy en naleving](connections.md#data-privacy-and-compliance) en selecteer **Ik ga akkoord**.

1. Selecteer **Verbinden** om de verbinding te initialiseren.

1. Selecteer **Verifiëren met Snapchat** en geef uw beheerdersreferenties voor Snapchat op.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen**.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie Snapchat. Neem contact op met een beheerder als er geen verbinding beschikbaar is.

1. Voer de naam in voor de export.

1. Voer **Snapchat-segment/doelgroep-id** in.

1. In de sectie **Gegevensvergelijking** selecteert u in het veld **E-mail** het veld dat het e-mailadres van een klant vertegenwoordigt.

1. Selecteer de segmenten die u wilt exporteren.

1. Selecteer **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
