---
title: Voorbeeld van Android-SDK
description: Voorbeeldproject om meer te weten te komen over de Android-SDK
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ba51961bc7f9555d7dba5b6a21c8636011438d75cba87bc132b896841c467a33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035820"
---
# <a name="run-the-android-sdk-sample"></a>Het Android-SDK-voorbeeld uitvoeren

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dit Android-voorbeeldproject helpt u te begrijpen hoe de SDK werkt in een app. U hoeft geen code te schrijven. Voeg gewoon uw opnamesleutel toe en u kunt meteen gebeurtenissen in uw werkruimte bekijken.

## <a name="prerequisites"></a>Vereisten

- [Android Studio](https://developer.android.com/studio)
- [Opnamesleutel](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Het Android-SDK-voorbeeld downloaden

1. [Download het Android-SDK-voorbeeld met betrokkenheidsinzichten](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. Pak het gecomprimeerde bestand `ei-android-sample.zip` uit.
1. Open de uitgepakte map in Android Studio.
1. Vervang in het bestand `AndroidManifest.xml` de tekenreeks `"Your-Ingestion-Key"` door uw werkruimte-opnamesleutel uit betrokkenheidsinzichten onder **Beheerder** > **Werkruimte** > **Installatiehandleiding**. 

   > [!NOTE]
   > U hoeft de sectie `${applicationId}` niet te vervangen. Deze wordt automatisch ingevuld.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Selecteer **Uitvoeren** om het voorbeeldproject te starten.
1. Bekijk de gebeurtenissen in uw werkruimte.


[!INCLUDE[footer-include](../includes/footer-banner.md)]