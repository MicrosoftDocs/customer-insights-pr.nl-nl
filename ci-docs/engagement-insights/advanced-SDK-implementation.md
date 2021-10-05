---
title: Geavanceerde web SDK-scenario's
description: Geavanceerde scenario's waarmee u rekening moet houden bij het instrumenteren van uw website met een SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 4c6646ecadbb604000d6c95b685cf6e420969a6d
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558695"
---
# <a name="advanced-web-sdk-instrumentation"></a>Geavanceerde web-SDK-instrumentatie

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dit artikel leidt u door geavanceerde scenario's om te overwegen bij de [instrumentatie van uw website](instrument-website.md) met een Dynamics 365 Customer Insights betrokkenheidsinzichten-SDK.

## <a name="setting-user-details-for-your-event"></a>Gebruikersgegevens instellen voor uw gebeurtenis

Met de SDK kunt u gebruikersinformatie definiëren die bij elke gebeurtenis kan worden verzonden. U kunt de gebruikersgegevens specificeren in een eigenschap met de naam `user` (de verwachte gegevens voor deze eigenschap zijn het `IUser`-object), vergelijkbaar met `src`, `name` en `cfg` in de configuratie van codefragmenten.

Het `IUser`-object bevat de volgende tekenreekseigenschappen:

- **localId**: de lokale id van de gebruiker.
- **authId**: de geverifieerde gebruikers-id.
- **authType**: het verificatietype dat wordt gebruikt om de geverifieerde gebruikers-id te verkrijgen.
- **name**: de naam van de gebruiker.
- **email**: het e-mailadres van de gebruiker.

Het volgende voorbeeld toont een codefragment dat gebruikersinformatie verzendt. Waar u functies ziet die worden voorafgegaan door een asterisk-symbool *, vervangt u de functie met uw aangepaste implementatie:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

U kunt ook gebruikersinformatie opgeven door de `setUser(user: IUser)`-API aan te roepen. Telemetrie die wordt verzonden na het aanroepen van de `setUser`-API, bevat de gebruikersinformatie.

## <a name="adding-custom-properties-for-each-event"></a>Aangepaste eigenschappen toevoegen voor elke gebeurtenis

Met de SDK kunt u aangepaste eigenschappen opgeven die bij elke gebeurtenis kunnen worden verzonden. U kunt de aangepaste eigenschappen opgeven als een object dat sleutel/waarde-paren bevat (de waarde kan van het type `string | number | boolean`). U kunt het object toevoegen in een eigenschap genaamd `props`, gelijk aan `src`, `name` en `cfg` in de codefragmentconfiguratie.

Het volgende voorbeeld toont een codefragment dat aangepaste eigenschappen verzendt.

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

U kunt ook aangepaste eigenschappen opgeven door de `setProperty(name: string, value: string | number | boolean)`-API aan te roepen.

## <a name="sending-custom-events"></a>Aangepaste gebeurtenissen verzenden

U kunt de SDK gebruiken om aangepaste gebeurtenissen te verzenden. U moet een naam opgeven voor de gebeurtenis en eigenschappen die met de gebeurtenis moeten worden verzonden.

Het volgende voorbeeld toont een codefragment dat een aangepaste gebeurtenis traceert. De "NAAM" is de waarde in de `name`-sleutel in de fragmentconfiguratie. Het is ook de variabelenaam in het vensterobject waarin de SDK is geladen.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]
