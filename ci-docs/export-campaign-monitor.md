---
title: Segmenten exporteren naar Campaign Monitor (preview)
description: Leer hoe u de verbinding configureert en exporteert naar Campaign Monitor.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c04fc26dc690cf32b45913257e82b9a0f617185
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196296"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Segmenten exporteren naar Campaign Monitor (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar Campaign Monitor en gebruik deze voor marketingactiviteiten.

## <a name="prerequisites"></a>Vereisten

- Een [Campaign Monitor-account](https://www.campaignmonitor.com/) en bijbehorende beheerdersreferenties.
- Een [Id van Campaign Monitor-lijst](https://www.campaignmonitor.com/api/getting-started/#your-list-id).
- Een [gegenereerde API-sleutel](https://www.campaignmonitor.com/api/getting-started/) van **Accountinstellingen** in Campaign Monitor om de API-lijst-id te verkrijgen.
- [Segmenten geconfigureerd](segments.md) in Customer Insights.
- Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.

## <a name="known-limitations"></a>Bekende beperkingen

- Maximaal 1 miljoen klantprofielen per export naar Campaign Monitor en dit kan tot 20 minuten duren. Het aantal klantprofielen dat u kunt exporteren naar Campaign Monitor, is afhankelijk van uw contract met Campaign Monitor.
- Alleen segmenten.

## <a name="set-up-connection-to-campaign-monitor"></a>Verbinding instellen met Campaign Monitor

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Campaign Monitor**.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Standaard zijn dit alleen beheerders. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Bekijk [Gegevensprivacy en naleving](connections.md#data-privacy-and-compliance) en selecteer **Ik ga akkoord**.

1. Selecteer **Verbinden** om de verbinding met Campaign Monitor te initialiseren.

1. Selecteer **Verifiëren met Campaign Monitor** en geef uw beheerdersreferenties voor Campaign Monitor op.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen** om een nieuwe export te maken.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie Campaign Monitor. Neem contact op met een beheerder als er geen verbinding beschikbaar is.

1. Voer de naam in voor de export.

1. Voer uw **Id van Campaign Monitor-lijst** in.

1. In de sectie **Gegevensvergelijking** selecteert u in het veld **E-mail** het veld dat het e-mailadres van een klant vertegenwoordigt. Deze is vereist voor het exporteren van segmenten naar Campaign Monitor.

1. Selecteer de segmenten die u wilt exporteren.

1. Selecteer **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
