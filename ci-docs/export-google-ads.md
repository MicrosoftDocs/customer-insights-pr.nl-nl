---
title: Segmenten exporteren naar Google Ads (preview)
description: Leer hoe u de verbinding configureert en exporteert naar Google Ads.
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: fd7498ecf17ef8a3a8f22dcc49ae204bef88b47f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196572"
---
# <a name="export-segments-to-google-ads-preview"></a>Segmenten exporteren naar Google Ads (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar een Google Ads-doelgroepenlijst en gebruik ze om te adverteren op Google Search, Gmail, YouTube en Google Display Network.

## <a name="prerequisites"></a>Vereisten

- Een [Google Ads-account](https://ads.google.com/) en bijbehorende beheerdersreferenties.
- Een [klant-id voor Google Ads](https://support.google.com/google-ads/answer/1704344).
- Er moet worden voldaan aan de vereisten van het [Customer Match-beleid](https://support.google.com/adspolicy/answer/6299717).
- Er moet worden voldaan aan de vereisten van de [hermarketinglijstformaten](https://support.google.com/google-ads/answer/7558048).
- [Geconfigureerde segmenten](segments.md).
- Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten velden die een e-mailadres, telefoon, mobiele adverteerder-id, gebruikers-id van derden of adres vertegenwoordigen.

## <a name="known-limitations"></a>Bekende beperkingen

- Maximaal 1 miljoen klantprofielen per export naar Google Ads en dit kan tot 30 minuten duren vanwege beperkingen aan de kant van de provider.
- Alleen segmenten.
- Het matchen in Google Ads kan tot 48 uur duren.

## <a name="set-up-connection-to-google-ads"></a>Verbinding met Google Ads instellen

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Google Ads**.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Standaard zijn dit alleen beheerders. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Voer uw klant-id voor Google Ads in.

1. Bekijk [Gegevensprivacy en naleving](connections.md#data-privacy-and-compliance) en selecteer **Ik ga akkoord**.

1. Selecteer **Verifiëren met Google Ads** en geef uw Google Ads-referenties op.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen**.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie Google Ads. Neem contact op met een beheerder als er geen verbinding beschikbaar is.

1. Voer de naam in voor de export.

1. Geef aan of u een bestaande doelgroep wilt gebruiken of een nieuwe doelgroep wilt maken:
   - Als u een bestaande Google Ads-doelgroep wilt bijwerken, voert u uw [doelgroep-id voor Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns) in.
   - Als u een nieuwe doelgroep wilt maken, laat u het veld Doelgroep-id voor Google Ads leeg. In Customer Insights wordt automatisch een nieuwe doelgroep in uw Google Ads-account gemaakt en wordt de naam van het geëxporteerde segment gebruikt.

1. Selecteer in de sectie **Gegevensvergelijking** een of meer gegevensvelden om te exporteren en selecteer het veld dat de corresponderende gegevensvelden in Customer Insights vertegenwoordigt.

1. Selecteer de segmenten die u wilt exporteren.

1. Selecteer **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
