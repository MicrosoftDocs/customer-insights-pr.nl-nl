---
title: Segmenten exporteren naar ActiveCampaign
description: Leer hoe u de verbinding configureert en exporteert naar ActiveCampaign.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e62888a6d618fb1154890e607d8c23d3767d35f7
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725394"
---
# <a name="export-segments-to-activecampaign-preview"></a>Segmenten exporteren naar ActiveCampaign (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar ActiveCampaign en gebruik ze voor marketingactiviteiten.

## <a name="prerequisites"></a>Vereisten

- Een [ActiveCampaign-account](https://www.activecampaign.com/) en bijbehorende beheerdersreferenties.
- Een [Id van ActiveCampaign-lijst](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).
- Een [API-sleutel van ActiveCampaign](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) en hostnaam van het REST-eindpunt.
- [Segmenten geconfigureerd](segments.md) in Customer Insights.
- Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld voor e-mailadres.

## <a name="known-limitations"></a>Bekende beperkingen

- Privékoppeling in combinatie met Bring your own storage (BYOS) wordt niet ondersteund.
- Maximaal 1 miljoen klantprofielen per export naar ActiveCampaign en dit kan tot 90 minuten duren. Het aantal klantprofielen dat u kunt exporteren naar ActiveCampaign, is afhankelijk van en wordt beperkt door uw contract met ActiveCampaign.
- Alleen segmenten.

## <a name="set-up-connection-to-activecampaign"></a>Verbinding instellen met ActiveCampaign

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **ActiveCampaign**.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Standaard zijn dit alleen beheerders. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Voer uw ActiveCampaign API-sleutel en hostnaam van REST-eindpunt in. De hostnaam van het REST-eindpunt is alleen de hostnaam zonder https://.

1. Bekijk [Gegevensprivacy en naleving](connections.md#data-privacy-and-compliance) en selecteer **Ik ga akkoord**.

1. Selecteer **Verbinden** om de verbinding te initialiseren.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen**.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie ActiveCampaign. Neem contact op met een beheerder als er geen verbinding beschikbaar is.

1. Voer de naam in voor de export.

1. Voer uw **Id van ActiveCampaign-lijst** in.

1. In de sectie **Gegevensvergelijking** selecteert u in het veld **E-mail** het veld dat het e-mailadres van een klant vertegenwoordigt.

1. Optioneel kunt u **Voornaam**, **Achternaam** en **Telefoon** exporteren om meer gepersonaliseerde e-mails te maken. Selecteer **Kenmerk toevoegen** om deze velden toe te wijzen.

1. Selecteer de segmenten die u wilt exporteren.

1. Selecteer **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
