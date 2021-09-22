---
title: Het iOS-SDK-voorbeeld uitvoeren
description: Voorbeeldproject om meer te weten te komen over de iOS SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 053e626d06d3e17b39b448987410058e45e8ae0385f3ecdef40314cb46ae4bf4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036822"
---
# <a name="run-the-ios-sdk-sample"></a>Het iOS-SDK-voorbeeld uitvoeren

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dit iOS-voorbeeldproject helpt u te begrijpen hoe de SDK werkt in een app. U hoeft geen code te schrijven. Voeg gewoon uw opnamesleutel toe en u kunt meteen gebeurtenissen in uw werkruimte bekijken.

## <a name="prerequisites"></a>Vereisten

- [Xcode versie 9+](https://developer.apple.com/xcode/downloads/)
- [Opnamesleutel](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>Het iOS-SDK-voorbeeld downloaden

1. [Download het iOS-SDK-voorbeeld met betrokkenheidsinzichten](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip).
1. Pak het gecomprimeerde bestand `ei-ios-sample.zip` uit.
1. Open het voorbeeld-app-project in Xcode.
1. Vervang in het bestand `EIConfig.plist` de tekenreeks `“YOUR-INGESTION-KEY”` in het veld `ingestionKey` door uw werkruimte-opnamesleutel uit betrokkenheidsinzichten onder **Beheerder** > **Werkruimte** > **Installatiehandleiding**.
1. Selecteer **Uitvoeren** om het voorbeeldproject te starten.
1. Bekijk de gebeurtenissen in uw werkruimte.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
