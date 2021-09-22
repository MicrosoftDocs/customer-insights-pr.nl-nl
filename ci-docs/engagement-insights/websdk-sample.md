---
title: Een web-SDK-voorbeeld uitvoeren
description: Ontdek hoe u een web-SDK-voorbeeld personaliseert en uitvoert.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036597"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Het web-SDK-voorbeeld uitvoeren voor Dynamics 365 Customer Insights-functionaliteit voor betrokkenheidsinzichten

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

De web-SDK-bibliotheek voor de functionaliteit voor betrokkenheidsinzichten is een JavaScript-bibliotheek met voorbeeldcode die u op uw website kunt gebruiken.

## <a name="prerequisites"></a>Vereisten

- Installeer [Visual Studio-code](https://code.visualstudio.com/).
- [Installeer de Live Server-extensie](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) in Visual Studiocode en raak vertrouwd met het uitvoeren van Live Server.
- U moet de [opnamesleutel](instrument-website.md) hebben.

## <a name="run-sample"></a>Voorbeeld uitvoeren

1. [Download het web SDK-voorbeeld](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Pak het gecomprimeerde bestand `ei_websdk_sample.zip` uit.

1. Open de uitgepakte map in Visual Studio-code.

1. In het `ei_websdk_sample.html`-bestand vervangt u de tekenreeks "INGESTION_KEY" door uw opnamesleutel van de betrokkenheidsinzichten-portal en de tekenreeks "NAME" door de algemene naam waarin u de SDK wilt laten instantiëren. Zorg ervoor dat u alle exemplaren vervangt.

1. Open het `ei_websdk_sample.html`-bestand met Live Server in Visual Studio-code door **Ga live** op de statusbalk te selecteren.

1. Wanneer u de pagina opent, moet automatisch een weergavegebeurtenis worden verzonden. Door op een van de knoppen op de pagina te klikken, worden actiegebeurtenissen verzonden. Met de knop **Gebeurtenissen volgen** stuurt u ook aangepaste gebeurtenissen. Als u de knop **Ga naar Bing** selecteert, wordt een actiegebeurtenis verzonden voordat u naar de Bing-website gaat.

1. Bekijk de gebeurtenissen die stromen wanneer u naar uw werkruimte navigeert. Deze werkruimte is gekoppeld aan de opnamesleutel die is ingevoerd in stap 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]