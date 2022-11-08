---
title: Customer Insights-gegevens exporteren naar HubSpot
description: Leer hoe u de verbinding configureert en exporteert naar HubSpot.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b34f1d54fa499f6c6b80fa547a8aaf61af3b35a1
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725348"
---
# <a name="export-segments-to-hubspot-preview"></a>Segmenten exporteren naar HubSpot (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar HubSpoten gebruik deze voor e-marketing.

## <a name="prerequisites-for-a-connection"></a>Vereisten voor een verbinding

- Een [HubSpot-account](https://www.hubspot.com/) en bijbehorende beheerdersreferenties.
- [API-sleutel](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key) van HubSpot.
- [Segmenten geconfigureerd](segments.md) in Customer Insights.

## <a name="known-limitations"></a>Bekende beperkingen

- Privékoppeling in combinatie met Bring your own storage (BYOS) wordt niet ondersteund.
- Tot 100.000 klantprofielen per export naar HubSpot, wat tot 15 minuten kan duren. Het aantal klantprofielen dat u kunt exporteren naar HubSpot, is afhankelijk van en wordt beperkt door uw contract met HubSpot.
- Alleen segmenten.

## <a name="set-up-connection-to-hubspot"></a>Verbinding met HubSpot instellen

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **HubSpot** om de verbinding te configureren.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Voer desgevraagd uw HubSpot-referenties in.

1. Bekijk [Gegevensprivacy en naleving](connections.md#data-privacy-and-compliance) en selecteer **Ik ga akkoord**.

1. Selecteer **Verbinden** om de verbinding met HubSpot te initialiseren.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen** om een nieuwe export te maken.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie HubSpot. Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.

1. In de sectie **Gegevensvergelijking** selecteert u in het veld **E-mail** het veld dat het e-mailadres van een klant vertegenwoordigt. Herhaal dezelfde stappen voor andere optionele velden.

1. Selecteer de segmenten die u wilt exporteren.

1. Selecteer **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
