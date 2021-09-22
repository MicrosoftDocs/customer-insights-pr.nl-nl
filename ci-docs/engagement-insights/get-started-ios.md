---
title: Aan de slag met iOS SDK
description: Ontdek hoe u de SDK voor iOS personaliseert en uitvoert
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: de8291fc429ae6433301a47bfdf9a3271b1b77294fd58448c7aa6bd0783edc97
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036867"
---
# <a name="get-started-with-the-ios-sdk"></a>Aan de slag met de iOS SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Deze zelfstudie begeleidt u door het instrumenteerproces van uw iOS-toepassing met een SDK voor betrokkenheidsinzichten voor Dynamics 365 Customer Insights. Binnen vijf minuten of eerder begint u gebeurtenissen te zien op uw portal.

## <a name="configuration-options"></a>Configuratieopties

De volgende configuratieopties kunnen worden doorgegeven aan de SDK via het meegeleverde bestand `EIConfig.plist`:

- **ingestionKey**: de opnamesleutel die wordt gebruikt om gebeurtenissen naar uw project te verzenden.
- **autocollectAction**: een Booleaanse waarde om automatische instrumentatie van de actiegebeurtenis in of uit te schakelen.
- **autocollectView**: een Booleaanse waarde om automatische instrumentatie van de weergavegebeurtenis in of uit te schakelen.
- **endpointUrl**: de eindpunt-URL waar de gebeurtenis naartoe worden geleid.

## <a name="prerequisites"></a>Vereisten

- Xcode versie 9+
- iOS versie 8.2+
- Een opnamesleutel (zie de instructies hieronder voor het verkrijgen hiervan)

## <a name="integrate-the-sdk-into-your-application"></a>De SDK integreren in uw toepassing

Begin het proces door een werkruimte te selecteren waarin u wilt werken, het mobiele iOS-platform te selecteren en de SDK te downloaden.

- Gebruik de werkruimtewisselaar in het linkernavigatievenster om uw werkruimte te selecteren.

- Als u geen bestaande werkruimte hebt, selecteert u **Nieuwe werkruimte** en volgt u de stappen voor het maken van een [nieuwe werkruimte](create-workspace.md).

## <a name="configure-the-sdk"></a>De SDK configureren

Nadat u de SDK hebt gedownload, kunt u ermee werken in Xcode om gebeurtenissen in te schakelen en te definiëren.

1. Nadat u een werkruimte hebt gemaakt, gaat u naar **Beheerder** > **Werkruimte** en selecteert u vervolgens **Installatiehandleiding**.

1. Download de [iOS-SDK voor betrokkenheidsinzichten](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip) en plaats het bestand `EIObjC.xcframework` in de map `Frameworks`.

1. Als een map `Frameworks` niet bestaat, maakt u deze in de projectmap.

## <a name="enable-auto-instrumentation"></a>Automatische instrumentatie inschakelen
 
U kunt automatische instrumentatie eenvoudig inschakelen zonder codering. Wanneer het project actief is, houdt het automatisch de gebeurtenissen `view` en `action` bij met behulp van de geconfigureerde opnamesleutel. 

1. Voer een update uit en neem het meegeleverde bestand `EIConfig.plist` op in uw projectmap voor de volgende velden:
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = YES
    - autocollectAction = YES

2. Voeg vervolgens het bestand `EIConfig.plist` toe aan uw project in Xcode. 



Als u automatische instrumentatie wilt uitschakelen, werkt u de volgende bestanden bij in het meegeleverde bestand `EIConfig.plist` in uw projectmap. 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>Aangepaste gebeurtenissen implementeren

1. Open uw project in Xcode en ga naar **Algemene instellingen**. 
1. Voeg `EIObjC.xcframework` toe aan het project onder de sectie 'Frameworks, bibliotheken en ingesloten inhoud'.

1. Importeer het frameworkheader-bestand in AppDelegate.m met het volgende fragment:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. Initialiseer de SDK voor betrokkenheidsinzichten vanuit de toepassing: didFinishLaunchingWithOptions.
1. Kopieer het XML-fragment van de **installatiehandleiding**.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. Een gebeurtenis bijhouden:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>Gebruikersgegevens instellen voor uw gebeurtenis

Met de SDK kunt u gebruikersinformatie definiëren die bij elke gebeurtenis kan worden verzonden. U kunt gebruikersinformatie opgeven door de API `setUser:(nonnull EIUser *)user` aan te roepen in de SDK.

Als u gebruikersgegevens opgeeft op het `Analytics`-niveau beschikken alle telemetrieën over deze informatie. Als u echter op gebeurtenisniveau specificeert door de API `setUser:(nonnull EIUser *)user` aan te roepen voor het EIEvent-object, bevat alleen die specifieke gebeurtenis de informatie.

De gegevensklasse `EIUser` bevat de volgende NSString-eigenschappen:

- **localId**: de lokale id van de gebruiker.
- **authId**: de geverifieerde gebruikers-id.
- **authType**: het verificatietype dat wordt gebruikt om de geverifieerde gebruikers-id te verkrijgen.
- **name**: de naam van de gebruiker.
- **email**: het e-mailadres van de gebruiker.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
