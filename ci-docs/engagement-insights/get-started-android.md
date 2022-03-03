---
title: Aan de slag met Android SDK
description: Ontdek hoe u de SDK Android personaliseert en uitvoert
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 10/19/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: b06822b2c2d6a859bdf808f7800baef43c4ab874
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226163"
---
# <a name="get-started-with-the-android-sdk"></a>Aan de slag met de Android SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Deze zelfstudie begeleidt u door het instrumenteerproces van uw Android-toepassing met een SDK voor betrokkenheidsinzichten voor Dynamics 365 Customer Insights. Binnen vijf minuten of eerder begint u gebeurtenissen te zien op uw portal.

## <a name="configuration-options"></a>Configuratieopties
De volgende configuratieopties kunnen worden doorgegeven aan de SDK:

- **ingestionKey**: de opnamesleutel wordt gebruikt om gebeurtenissen naar uw werkruimte te verzenden.

## <a name="prerequisites"></a>Vereisten

- Android Studio

- Minimaal Android API-niveau: 16 (Jelly Bean)

- Een opnamesleutel (zie hieronder voor instructies over het verkrijgen hiervan)

## <a name="integrate-the-sdk-into-your-application"></a>De SDK integreren in uw toepassing
Begin het proces door een werkruimte te selecteren, het mobiele Android-platform te selecteren en de Android SDK te downloaden.

- Gebruik de werkruimtewisselaar in het linkernavigatievenster om uw werkruimte te selecteren.

- Als u geen bestaande werkruimte hebt, selecteert u **Nieuwe werkruimte** en volgt u de stappen voor het maken van een [nieuwe werkruimte](create-workspace.md).

- Nadat u een werkruimte hebt gemaakt, gaat u naar **Beheerder** > **Werkruimte** en selecteert u vervolgens **Installatiehandleiding**.

## <a name="configure-the-sdk"></a>De SDK configureren

Nadat u de SDK hebt gedownload, kunt u ermee werken in Android Studio om gebeurtenissen in te schakelen en te definiëren. U kunt dit op twee manieren doen.
### <a name="option-1-use-jitpack-recommended"></a>Optie 1: JitPack gebruiken (aanbevolen)
1. Voeg de JitPack-opslagplaats toe aan uw hoofdmap `build.gradle`:
    ```gradle
    allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
    ```

1. Voeg de afhankelijkheid toe:
    ```gradle
    dependencies {
        implementation 'com.github.microsoft:engagementinsights-sdk-android:v1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-use-download-link"></a>Optie 2: downloadkoppeling gebruiken
1. Download de [Android-SDK voor betrokkenheidsinzichten](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip) en plaats het bestand `eiandroidsdk-debug.aar` in de map `libs`.

1. Open uw bestand `build.gradle` op projectniveau en voeg de volgende fragmenten toe:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

## <a name="enable-auto-instrumentation"></a>Automatische instrumentatie inschakelen

1. Voeg toestemming voor netwerk en internet toe aan uw `AndroidManifest.xml`-bestand onder de map `manifests`.
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```

1. Stel de SDK-configuratie voor betrokkenheidsinzichten in via uw bestand `AndroidManifest.xml`.

1. Kopieer het XML-fragment van de **installatiehandleiding**. `Your-Ingestion-Key` zou nu automatisch moeten worden ingevuld.

   > [!NOTE]
   > U hoeft de sectie `${applicationId}` niet te vervangen. Deze wordt automatisch ingevuld.


   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Schakel Automatisch vastleggen van gebeurtenissen `View` in of uit door het bovenstaande veld `autoCapture` in te stellen op `true` of `false`. 

   >[!NOTE]
   >`Action`-gebeurtenissen moeten handmatig worden toegevoegd.

1. (Optioneel) Andere configuraties omvatten het instellen van de verzamel-URL voor eindpunten. Ze kunnen worden toegevoegd onder de metagegevens van de opnamesleutel in `AndroidManifest.xml`.

   ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
   ```

## <a name="implement-custom-events"></a>Aangepaste gebeurtenissen implementeren

Nadat u de SDK hebt geïnitialiseerd, kunt u werken met gebeurtenissen en de bijbehorende eigenschappen in de `MainActivity`-omgeving.


Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>Eigenschap instellen voor alle gebeurtenissen (optioneel)

Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

De volgende typen worden ondersteund voor eigenschappen van contextgebeurtenissen:
- String
- Datum
- Dubbel
- Lang
- Booleaans
- UUID

### <a name="track-an-event"></a>Een gebeurtenis bijhouden

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

## <a name="set-user-details-for-your-event-optional"></a>Gebruikersgegevens instellen voor uw gebeurtenis (optioneel)

Met de SDK kunt u gebruikersinformatie definiëren die bij elke gebeurtenis kan worden verzonden. U kunt gebruikersinformatie opgeven door de API `setUser(user: User)` aan te roepen op het `Analytics`-niveau.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

De gegevensklasse `User` bevat de volgende tekenreekseigenschappen:

- **localId**: de lokale id van de gebruiker.
- **authId**: de geverifieerde gebruikers-id.
- **authType**: het verificatietype dat wordt gebruikt om de geverifieerde gebruikers-id op te halen.
- **name**: de naam van de gebruiker.
- **email**: het e-mailadres van de gebruiker.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
