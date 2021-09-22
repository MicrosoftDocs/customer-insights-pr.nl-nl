---
title: Aan de slag met Android SDK
description: Ontdek hoe u de SDK Android personaliseert en uitvoert
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 77e63929bbcc7ecff34a3839af525b76ec3c7f21173ddc5f8f2d69f11c25c441
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036912"
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

## <a name="step-1-integrate-the-sdk-into-your-application"></a>Stap 1. De SDK integreren in uw toepassing
Begin het proces door een werkruimte te selecteren, het mobiele Android-platform te selecteren en de Android SDK te downloaden.

- Gebruik de werkruimtewisselaar in het linkernavigatievenster om uw werkruimte te selecteren.

- Als u geen bestaande werkruimte hebt, selecteert u **Nieuwe werkruimte** en volgt u de stappen voor het maken van een [nieuwe werkruimte](create-workspace.md).

## <a name="step-2-configure-the-sdk"></a>Stap 2. De SDK configureren

1. Nadat u een werkruimte hebt gemaakt, gaat u naar **Beheerder** > **Werkruimte** en selecteert u vervolgens **Installatiehandleiding**. 

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

1. Stel de SDK-configuratie voor betrokkenheidsinzichten in via uw bestand `AndroidManifest.xml` onder de map `manifests`. 
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

1. (Optioneel) Andere configuraties omvatten het instellen van de verzamel-URL voor eindpunten. Ze kunnen worden toegevoegd onder de metagegevens van de opnamesleutel in `AndroidManifest.xml`:
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="step-3-initialize-the-sdk-from-mainactivity"></a>Stap 3. De SDK initialiseren vanuit MainActivity 

Nadat u de SDK hebt geïnitialiseerd, kunt u werken met gebeurtenissen en hun eigenschappen in de MainActivity-omgeving.

    
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

### <a name="set-user-details-for-your-event-optional"></a>Gebruikersgegevens instellen voor uw gebeurtenis (optioneel)

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
