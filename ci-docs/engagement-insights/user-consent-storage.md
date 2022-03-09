---
title: Beheer cookies en gebruikerstoestemming om gebruikersgegevens op te slaan in Dynamics 365 Customer Insights
description: Begrijp hoe cookies en toestemming van de gebruiker worden gebruikt om websitebezoekers te identificeren.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 018263220d4628690e9f0beb8453e58b0356d099
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228979"
---
# <a name="manage-cookies-and-user-consent"></a>Cookies en toestemming van gebruikers beheren

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

De mogelijkheid van Dynamics 365 Customer Insights voor betrokkenheidsinzichten maakt gebruik van cookies en (`localStorage`)-sleutels om websitebezoekers te identificeren.

Cookies zijn kleine bestanden die stukjes informatie opslaan over de interacties van een gebruiker met de website. Ze worden opgeslagen in webbrowsers. Wanneer gebruikers een website bezoeken waarvoor uw gebruikers cookies hebben opgeslagen, stuurt de browser die informatie naar de server, die informatie retourneert die uniek is voor de gebruiker. Dit is de technologie waarmee bijvoorbeeld een online winkelwagentje geselecteerde items erin kan bewaren, zelfs als een gebruiker de website verlaat.

## <a name="user-consent"></a>Gebruikerstoestemming

De [Algemene verordening gegevensbescherming (AVG)](/dynamics365/get-started/gdpr/) is een verordening van de Europese Unie (EU) die bepaalt hoe organisaties moeten omgaan met de privacy en veiligheid van hun gebruikers. Cookies slaan of verzamelen vaak 'persoonlijke gegevens' op, zoals een online id, die onder de AVG valt. Als uw bedrijf in dienst is van en/of verkoopt aan EU-betrokkenen, hebt u met de AVG te maken. [Hier vindt u meer informatie over de manier waarop Microsoft u kan helpen te voldoen aan de AVG](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Om ervoor te zorgen dat de betrokkenheidsinzichten-SDK cookies of andere gevoelige informatie opslaat, moet u aangeven of uw gebruikers toestemming hebben gegeven. Dit gebeurt bij initialisatie van de SDK door een `userConsent`-veld in te stellen in de configuratie.

Als u aangeeft dat er geen toestemming van de gebruiker is, zal de SDK geen gegevens opslaan en geen gebeurtenissen verzenden die kunnen worden gebruikt om gebruikersgedrag bij te houden. Alle eerder opgeslagen gegevens worden uit de browser verwijderd.

Als er geen waarde voor toestemming van de gebruiker is opgegeven, gaat de SDK ervan uit dat de gebruiker heeft ingestemd. Dit betekent dat als u (als onze klant) geen waarde opgeeft voor gebruikerstoestemming in de SDK, er gegevens worden verzameld. Als u echter opgeeft dat de waarde voor toestemming van de gebruiker 'waar' moet zijn, worden er geen gegevens verzameld als een gebruiker weigert of geen expliciete toestemming geeft.

Hieronder staat een codefragment om de web-SDK te initialiseren gebruikerstoestemming:
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Opslag van bezoekersgegevens in functionaliteit voor betrokkenheidsinzichten

### <a name="cookies"></a>Koekjes

- _msei
    - Slaat de anonieme gebruikers-id op. Deze cookie wordt geplaatst in het klantdomein en vervalt na 365 dagen.

### <a name="local-storage"></a>Lokale opslag

Betrokkenheidsinzichten maken ook gebruik van (`localStorage`)-sleutels om niet-gevoelige gegevens bij te houden. Deze gegevens worden volledig in de browser zelf opgeslagen, er wordt geen verkeer van of naar uw servers gestuurd.

- *EISession.Id*
    - Slaat informatie op over de lopende gebruikerssessie, zoals sessie-id, wanneer deze is gestart en wanneer deze verloopt.
- *EISession.Previous*
    - Slaat de URL op van de eerder bezochte pagina in de huidige sessie.

Sleutels in lokale opslag verlopen niet automatisch en worden tijdens de volgende SDK-sessie opnieuw ingesteld.

## <a name="deleting-cookies"></a>Cookies verwijderen

Uw klanten kunnen cookies en lokale opslagsleutels op elk moment handmatig verwijderen via de instellingen van hun browser.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
