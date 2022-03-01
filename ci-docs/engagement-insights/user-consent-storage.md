---
title: Cookies en toestemming van de gebruiker beheren om gebruikersgegevens op te slaan
description: Begrijp hoe cookies en toestemming van de gebruiker worden gebruikt om websitebezoekers te identificeren.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7b3195a92c969ab36e5b43f4c2e4221ff477a0a8958838e1256528f58fe13dce
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036732"
---
# <a name="manage-cookies-and-user-consent"></a>Cookies en toestemming van gebruikers beheren

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dynamics 365 Customer Insights-functionaliteit voor betrokkenheidsinzichten maakt gebruik van cookies en lokale opslag (`localStorage`) om websitebezoekers te identificeren.

Cookies zijn kleine bestanden die stukjes informatie opslaan over de interacties van een gebruiker met de website. Ze worden opgeslagen in webbrowsers. Wanneer gebruikers een website bezoeken waarvoor uw gebruikers cookies hebben opgeslagen, stuurt de browser die informatie naar de server, die informatie retourneert die uniek is voor de gebruiker. Dit is de technologie waarmee bijvoorbeeld een online winkelwagentje geselecteerde items erin kan bewaren, zelfs als een gebruiker de website verlaat.

## <a name="user-consent"></a>Gebruikerstoestemming

De [Algemene verordening gegevensbescherming (AVG)](/dynamics365/get-started/gdpr/) is een verordening van de Europese Unie (EU) die bepaalt hoe organisaties moeten omgaan met de privacy en veiligheid van hun gebruikers. Cookies slaan of verzamelen vaak 'persoonlijke gegevens' op, zoals een online id, die onder de AVG valt. Als uw bedrijf in dienst is van en/of verkoopt aan EU-betrokkenen, hebt u met de AVG te maken. [Hier vindt u meer informatie over de manier waarop Microsoft u kan helpen te voldoen aan de AVG](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Om ervoor te zorgen dat de betrokkenheidsinzichten-SDK cookies of andere gevoelige informatie opslaat, moet u aangeven of uw gebruikers toestemming hebben gegeven. Dit gebeurt bij het initialiseren van de SDK.

Als u aangeeft dat er geen toestemming van de gebruiker is, zal de SDK geen gegevens opslaan en geen gebeurtenissen verzenden die kunnen worden gebruikt om gebruikersgedrag bij te houden. Alle eerder opgeslagen gegevens worden uit de browser verwijderd.

Als er geen waarde voor toestemming van de gebruiker is opgegeven, gaat de SDK ervan uit dat de gebruiker heeft ingestemd. Dit betekent dat als u (als onze klant) geen waarde opgeeft voor gebruikerstoestemming in de SDK, er gegevens worden verzameld. Als u echter opgeeft dat de waarde voor toestemming van de gebruiker 'waar' moet zijn, worden er geen gegevens verzameld als een gebruiker weigert of geen expliciete toestemming geeft.

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Opslag van bezoekersgegevens in functionaliteit voor betrokkenheidsinzichten

### <a name="cookies"></a>Koekjes

- _msei
    - Slaat de anonieme gebruikers-id op. Deze cookie wordt geplaatst in het klantdomein en vervalt na 365 dagen.

### <a name="local-storage"></a>Lokale opslag

In de functionaliteit voor betrokkenheidsinzichten wordt ook gebruikgemaakt van lokale opslag (`localStorage`) om niet-gevoelige gegevens te volgen. Deze gegevens worden volledig in de browser zelf opgeslagen, er wordt geen verkeer van of naar uw servers gestuurd.

- *EISession.Id* 
    - Slaat informatie op over de lopende gebruikerssessie, zoals sessie-id, wanneer deze is gestart en wanneer deze verloopt.
- *EISession.Previous*
    - Slaat de URL op van de eerder bezochte pagina in de huidige sessie.
    
Sleutels in lokale opslag verlopen niet automatisch. Ze worden tijdens de volgende sessie gereset door de SDK.

## <a name="deleting-cookies"></a>Cookies verwijderen

Uw klanten kunnen cookies en lokale opslagsleutels op elk moment handmatig verwijderen via de instellingen van hun browser.


[!INCLUDE[footer-include](../includes/footer-banner.md)]