---
title: Webgebeurtenissen herkennen van eerder geverifieerde bezoekers met 'onbekend naar bekend'
description: Met de functie 'onbekend naar bekend' kunt u gebeurtenissen op een website koppelen aan bezoekers die eerder zijn geverifieerd.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: d1bbc3315b55e2ee233dc672456e0c27e4ad0fbd5937af09cc790c96ee274000
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036777"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>Webgebeurtenissen herkennen van eerder geverifieerde bezoekers

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Met de functie **onbekend naar bekend** in de betrokkenheidsinzichten kunnen gebeurtenissen op een website worden gekoppeld aan bezoekers die eerder zijn geverifieerd. Als de functie is uitgeschakeld, worden bezoekers die tijdens een eerder bezoek zijn geverifieerd en daarna zijn vertrokken, niet geïdentificeerd als zij zich bij terugkomst niet opnieuw verifiëren. 

Iemand heeft bijvoorbeeld vorige week een website bezocht, zich aangemeld bij zijn gebruikersaccount op de site, en de productcatalogus doorgebladerd. Deze persoon komt de volgende week terug om meer producten te bekijken zonder in te loggen op zijn of haar account. De eigenaar van de site die de functie **onbekend naar bekend** gebruikt, weet dat dezelfde persoon is teruggekeerd en wat deze op de site heeft gedaan. Dit maakt nauwkeurigere rapportage en analyse van website-activiteiten mogelijk.

## <a name="enable-unknown-to-known"></a>Onbekend naar bekend inschakelen

U moet een [werkruimtebeheerder](user-roles.md) zijn om deze functie in te schakelen. 

1. Ga in betrokkenheidsinzichten naar **Beheer** > **Werkruimte**. 
2. Selecteer het tabblad **Instellingen**.
3. Zet in de sectie **Onbekend naar bekend** de schakelaar op **Ingeschakeld**.

![Onbekend naar bekend inschakelen](media/U2Ktoggle.png "Onbekend naar bekend inschakelen")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>JavaScript-code toevoegen aan het trackingfragment van uw site

Een website kan **user authId** vastleggen met het volgende JavaScript-voorbeeld met behulp van de [doelgroepinzichten-web SDK](advanced-SDK-implementation.md). Om de functie **onbekend naar bekend** te laten werken, moet u authId vastleggen *en* userMapping:True in te schakelen in uw JavaScript-fragment (zie het voorbeeld hieronder).

```
[…]
window, document
{
src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js",
name:"myproject",
cfg:{
ingestionKey:<paste your ingestion key>",
autoCapture:{
view:true,
click:true
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
