---
title: Segmenten exporteren naar Braze (preview)
description: Ontdek hoe u de verbinding met Braze configureert en exporteert.
ms.date: 10/06/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a3967008ec166cb6f099659b0791f1318126c0da
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725210"
---
# <a name="export-segments-to-braze-preview"></a>Segmenten exporteren naar Braze (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar Braze en gebruik deze voor marketingactiviteiten.

## <a name="prerequisites"></a>Vereisten

- Een [Braze-account](https://www.braze.com/) en bijbehorende beheerdersreferenties.
- Een [API-sleutel van Braze](https://www.braze.com/docs/api/basics/)
- Uw [Braze REST-eindpunt](https://www.braze.com/docs/api/basics/#api-definitions) 
- [Segmenten geconfigureerd](segments.md) in Customer Insights.
- Geharmoniseerde klantprofielen in de geëxporteerde segmenten bevatten een veld dat een e-mailadres en een Braze-klant-id vertegenwoordigt.

## <a name="known-limitations"></a>Bekende beperkingen

- Privékoppeling in combinatie met Bring your own storage (BYOS) wordt niet ondersteund.
- Maximaal 1 miljoen klantprofielen,per export naar Braze en dit kan wel 40 minuten kan duren. Het aantal klantprofielen dat u kunt exporteren naar Braze, is afhankelijk van uw contract met Braze.
- Alleen segmenten.
- Azure Private Link wordt niet ondersteund voor de Braze-export.

## <a name="set-up-connection-to-braze"></a>Verbinding met Braze instellen

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Braze**.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Standaard zijn dit alleen beheerders. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Geef uw Braze API-sleutel op om door te gaan met aanmelden.

1. Bekijk [Gegevensprivacy en naleving](connections.md#data-privacy-and-compliance) en selecteer **Ik ga akkoord**.

1. Selecteer **Verbinden** om de verbinding te initialiseren.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen**.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie Braze. Neem contact op met een beheerder als er geen verbinding beschikbaar is.

1. Voer uw REST-eindpunt in de notatie `rest.iad-03.braze.com` in het veld **Hostnaam** in.

1. Voer de naam in voor de export.

1. In de sectie **Gegevensvergelijking** selecteert u in het veld **E-mail** het veld dat het e-mailadres van een klant vertegenwoordigt. Selecteer in het veld **Klant-id** het veld dat de Braze-id van de klant vertegenwoordigt. De segmenten in Braze worden gemaakt met dezelfde naam voor het segment als in Dynamics 365 Customer Insights. U kunt meer, optionele velden kiezen voor gegevensvergelijking.

1. Selecteer de entiteiten of segmenten die u wilt exporteren.

1. Selecteer **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
