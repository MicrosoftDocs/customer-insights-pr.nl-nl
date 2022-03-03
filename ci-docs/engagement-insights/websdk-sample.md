---
title: Een web-SDK-voorbeeld uitvoeren
description: Ontdek hoe u een web-SDK-voorbeeld personaliseert en uitvoert.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a50a10db784ec7c1943c94e74000713309787e5c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225325"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Het web-SDK-voorbeeld uitvoeren voor Dynamics 365 Customer Insights-functionaliteit voor betrokkenheidsinzichten

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

De web-SDK-bibliotheek voor de functionaliteit voor betrokkenheidsinzichten is een JavaScript-bibliotheek met voorbeeldcode die u op uw website kunt gebruiken.

## <a name="prerequisites"></a>Vereisten

- Installeer [Visual Studio-code](https://code.visualstudio.com/).
- [Installeer de Live Server-extensie](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) in Visual Studiocode en raak vertrouwd met het uitvoeren van Live Server.
- U moet een [werkruimte voor betrokkenheidsinzichten](create-workspace.md) hebben.

## <a name="run-sample"></a>Voorbeeld uitvoeren

1. [Download het web SDK-voorbeeld](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Pak het gecomprimeerde bestand `ei_websdk_sample.zip` uit.

1. Open de uitgepakte map in Visual Studio-code.

1. Ga naar de betrokkenheidsinzichten-portal voor uw werkruimte. Selecteer **Beheerder** > **Werkruimte** en vervolgens **Installatiegids**. Volg de eerste optie en selecteer **Code kopiëren** om het JavaScript-codefragment te kopiëren.

1. Ga naar het bestand `ei_websdk_sample.html` en plak het gekopieerde codefragment onder deze regel:

   - <-- PASTE THE JAVASCRIPT CODE SNIPPET FROM ENGAGMENT INSIGHTS PORTAL HERE BELOW THIS LINE -->

1. Open het `ei_websdk_sample.html`-bestand met Live Server in Visual Studio-code door **Ga live** op de statusbalk te selecteren.

1. Wanneer u de pagina opent, moet automatisch een weergavegebeurtenis worden verzonden. Door op een van de knoppen op de pagina te klikken, worden actiegebeurtenissen verzonden. Met de knop **Gebeurtenissen volgen** stuurt u ook aangepaste gebeurtenissen. Als u de knop **Ga naar Bing** selecteert, wordt een actiegebeurtenis verzonden voordat u naar de Bing-website gaat.

1. Bekijk de gebeurtenissen die stromen wanneer u naar uw werkruimte navigeert. Deze werkruimte is gekoppeld aan de opnamesleutel die is ingevoerd in stap 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
