---
title: Segmenten exporteren naar DotDigital (preview)
description: Leer hoe u de verbinding configureert en exporteert naar DotDigital.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cabaea84e31f8fe97bc558a8dca8d93bc40f43b7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196066"
---
# <a name="export-segments-to-dotdigital-preview"></a>Segmenten exporteren naar DotDigital (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar DotDigital-adresboeken en gebruik ze voor campagnes, e-mailmarketing en om klantsegmenten op te bouwen met DotDigital.

## <a name="prerequisites"></a>Vereisten

- Een [DotDigital-account](https://dotdigital.com/) en een [API-gebruiker](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user).
- Een DotDigital-id van een [nieuw](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) of bestaand adresboek in DotDigital. De id is te vinden in de URL wanneer u een adresboek selecteert en opent.
- [Segmenten geconfigureerd](segments.md) in Customer Insights.
- Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.

## <a name="known-limitations"></a>Bekende beperkingen

- Maximaal 1 miljoen klantprofielen per export naar DotDigital en dit kan tot drie uur duren vanwege beperkingen aan de kant van de provider. Het aantal klantprofielen dat u kunt exporteren naar DotDigital, is afhankelijk van uw contract met DotDigital.
- Alleen segmenten.

## <a name="set-up-connection-to-dotdigital"></a>Verbinding met DotDigital instellen

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **DotDigital**.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Standaard zijn dit alleen beheerders. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Voer uw **DotDigital API-gebruikersnaam en wachtwoord** in.

1. Voer uw **adresboek-id voor DotDigital** in.

1. Bekijk [Gegevensprivacy en naleving](connections.md#data-privacy-and-compliance) en selecteer **Ik ga akkoord**.

1. Selecteer **Verbinden** om de verbinding te initialiseren.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen**.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie DotDigital. Neem contact op met een beheerder als er geen verbinding beschikbaar is.

1. Voer de naam in voor de export.

1. In de sectie **Gegevensvergelijking** selecteert u in het veld **E-mail** het veld dat het e-mailadres van een klant vertegenwoordigt.

1. U kunt desgewenst **Voornaam**, **Achternaam**, **Volledige naam**, **Geslacht** en **Postcode** exporteren.

1. Selecteer de segmenten die u wilt exporteren.

1. Selecteer **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

In DotDigital vindt u uw segmenten in [DotDigital-adresboeken](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

[!INCLUDE [footer-include](includes/footer-banner.md)]
