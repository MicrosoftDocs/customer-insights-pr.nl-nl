---
title: Segmenten exporteren naar AdRoll (preview)
description: Leer hoe u de verbinding configureert en exporteert naar AdRoll.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8110eab199920ab8fc2ea15678139faf264a242a
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195744"
---
# <a name="export-segments-to-adroll-preview"></a>Segmenten exporteren naar AdRoll (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar AdRoll en gebruik ze voor advertenties.

## <a name="prerequisites"></a>Vereisten

- Een [AdRoll-account](https://www.adroll.com/) en bijbehorende beheerdersreferenties.
- Een [AdRoll-adverteerders-id](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [Segmenten geconfigureerd](segments.md) in Customer Insights.
- Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.

## <a name="known-limitations"></a>Bekende beperkingen

- Maximaal 250.000 klantprofielen per export naar AdRoll en dit kan tot 10 minuten duren. Het aantal klantprofielen dat u kunt exporteren naar AdRoll, is afhankelijk van uw contract met AdRoll.
- Alleen segmenten. Een segment moet minimaal 100 klantprofielen bevatten.

## <a name="set-up-connection-to-adroll"></a>Verbinding met AdRoll instellen

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **AdRoll**.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Standaard zijn dit alleen beheerders. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Bekijk [Gegevensprivacy en naleving](connections.md#data-privacy-and-compliance) en selecteer **Ik ga akkoord**.

1. Selecteer **Verbinden** om de verbinding te initialiseren.

1. Selecteer **Verifiëren met AdRoll** en geef uw beheerdersreferenties voor AdRoll op.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen**.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie AdRoll. Neem contact op met een beheerder als er geen verbinding beschikbaar is.

1. Voer de naam in voor de export.

1. Voer uw **AdRoll-adverteerders-id** in.

1. In de sectie **Gegevensvergelijking** selecteert u in het veld **E-mail** het veld dat het e-mailadres van een klant vertegenwoordigt.

1. Selecteer de segmenten die u wilt exporteren.

1. Selecteer **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
