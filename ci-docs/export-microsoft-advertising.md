---
title: Segmenten exporteren naar Microsoft Advertising (preview)
description: Leer hoe u de verbinding configureert en exporteert naar Microsoft Advertising.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196526"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Segmenten exporteren naar Microsoft Advertising (preview)

Exporteer Customer Insights-segmenten naar Microsoft Advertising om doelgroepen met overeenkomende klanten te maken. Gebruik deze doelgroepen voor uw advertentiecampagnes.

## <a name="prerequisites"></a>Vereisten

- Een [Microsoft Advertising-account](https://ads.microsoft.com/) en bijbehorende beheerdersreferenties.
- Klant-id en account -id van Microsoft Advertising. U vindt de klant-id (`cid`) en account-id (`aid`) in de parameters van de URL wanneer u bent aangemeld bij Microsoft Advertising.
- De gebruiksvoorwaarden voor Customer Match worden geaccepteerd.
- [Segmenten geconfigureerd](segments.md) in Customer Insights.
- Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.

## <a name="known-limitations"></a>Bekende beperkingen

- Maximaal 500.000 klantprofielen per export naar Microsoft Advertising en dit kan tot 10 minuten duren.
- Alleen segmenten.

## <a name="set-up-connection-to-microsoft-advertising"></a>De verbinding met Microsoft Advertising instellen

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Microsoft Advertising**.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. De standaardoptie is beheerders. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Voer de **Klant-id van Microsoft Advertising** in.

1. Bekijk [Gegevensprivacy en naleving](connections.md#data-privacy-and-compliance) en selecteer **Ik ga akkoord**.

1. Selecteer **Verbinden** om de verbinding te initialiseren.

1. Selecteer **Verifiëren met Microsoft Advertising** en geef uw beheerdersreferenties voor Microsoft Advertising op.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen**.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie Microsoft Advertising. Neem contact op met een beheerder als er geen verbinding beschikbaar is.

1. Voer de naam in voor de export.

1. Selecteer de segmenten die moeten worden geëxporteerd. De doelgroepen met overeenkomende klanten in Microsoft Advertising worden automatisch gemaakt met de naam van de segmenten die zijn geselecteerd voor export. Elk segment resulteert in een afzonderlijke doelgroep met overeenkomende klanten.

1. Voer uw **klant-id en account-id voor Microsoft Advertising** in.

1. In de sectie **Gegevensvergelijking** selecteert in u het veld **E-mail** met een e-mailadres van de klant.

1. Selecteer **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
