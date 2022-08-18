---
title: Toestemming van klant gebruiken
description: Respecteer de toestemmingsvoorkeuren van uw klanten in Customer Insights door toestemmingsgegevens te importeren.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 6c951219410b55adc34691f677158b574cea1e01
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245689"
---
# <a name="use-customer-consent"></a>Toestemming van klant gebruiken

Regelgeving over gegevensbescherming en -privacy geven individuen het recht om te bepalen hoe een organisatie hun persoonlijke gegevens gebruikt. Voorbeelden van dergelijke regelgeving zijn de Algemene Verordening Gegevensbescherming in de Europese Unie of de California Consumer Privacy Act in de Verenigde Staten. Deze regelgeving stelt mensen in staat ervoor te kiezen hun persoonlijke gegevens niet te laten verzamelen, te verwerken door of te delen met derden.  

Klanten kunnen ervoor kiezen hun toestemming voor bepaalde vormen van contact in te trekken of te onthouden. Ze kunnen u ook vragen hen af te melden voor het verzamelen, opslaan, gebruiken of verkopen van hun persoonlijke gegevens. Het is belangrijk dat uw organisatie de voorkeuren voor toestemming en privacy van alle klanten respecteert.  

Dynamics 365 Customer Insights helpt u de verzoeken van uw klanten te honoreren door hun voorkeuren te importeren en op te slaan als onderdeel van de geharmoniseerde klantprofielen.

Als toestemmingsgegevens apart van uw klantprofielen worden opgeslagen, [voegt u de toestemmingsgegevens toe als een nieuwe gegevensbron](#import-and-unify-consent-data). De gegevensbron die de toestemmingsgegevens bevat, wordt toegevoegd aan het gegevensharmonisatieproces. Succesvolle harmonisatie van toestemmingsgegevens en klantprofielen leidt vervolgens tot geharmoniseerde klantprofielen die de toestemmingsinformatie bevatten. Ga voor klantprofielen die al toestemmingsinformatie bevatten rechtstreeks naar de sectie [toestemmingsgegevens gebruiken](#use-consent-data).

## <a name="prerequisites"></a>Vereisten

De volgende informatie moet beschikbaar zijn in uw brongegevens om toestemmingsgegevens te harmoniseren met andere klantprofielen:

- Alternatieve sleutel om de toestemmingsinformatie toe te wijzen aan gebruikersprofielen in Customer Insights. Bijvoorbeeld een telefoonnummer of een e-mailadres.
- Toestemmingswaarde om de status van de toestemming van de klant te bepalen.

Denk ook aan het toevoegen van de volgende *optionele* informatie:

- Primaire sleutel om de toestemmingsstatus bij te werken als een klant om een wijziging vraagt.
- Type toestemming, als er meer dan één manier is om klantgegevens te verwerken.
- Datum van toestemming of andere soorten gegevens die relevant zijn voor uw toestemmingsscenario's.

Voorbeeldtabel van een eenvoudige toestemmingsdatabase met meerdere toestemmingsopties:

|Toestemmings-id (primaire sleutel)   |E-mailadres (alternatieve sleutel)  |Toestemmingsoptie  |Toestemmingswaarde  |
|---------|---------|---------|---------|
|0    |  holly@contoso.com       |  Nieuwsbrief       |  False       |
|2    |  holly@contoso.com       |  Productupdates       |  True       |
|5    |  frank@contoso.com       |  Nieuwsbrief       | True        |
|4    |  frank@contoso.com       |  Productupdates       |  False       |

## <a name="import-and-unify-consent-data"></a>Toestemmingsgegevens importeren en harmoniseren

Importeer toestemmingsgegevens op dezelfde manier als andere gegevensbronnen naar Customer Insights. Zie [Overzicht gegevensbronnen](data-sources.md) voor meer informatie over ondersteunde gegevensbronnen en hoe u deze kunt importeren.

Zie [Overzicht van gegevensharmonisatie](data-unification.md) voor meer informatie over het harmoniseren van uw gegevensbronnen.

## <a name="use-consent-data"></a>Toestemmingsgegevens gebruiken

Zodra uw toestemmingsgegevens deel uitmaken van uw uniforme klantprofielen, kunt u deze gebruiken in Customer Insights. Maak bijvoorbeeld een segment met een regel die ervoor zorgt dat u de privacy- en gegevensbeschermingsvoorkeuren van uw klanten respecteert. Regels die toestemmingsvoorkeuren ondersteunen, worden gebruikt om gebruikers uit te sluiten van een segment op basis van profielkenmerken. Voeg een regel aan een segment toe dat klantprofielen uitsluit die geen toestemming hebben gegeven om met hen contact op te nemen.

Verwijzend naar de voorbeeldtabel hierboven, zou een segment deze regel kunnen bevatten: `Consent option=Newsletter & Consent value=True`. Deze configuratie resulteert in een segment dat contactvoorkeuren respecteert om een nieuwsbrief te verzenden.

Zie [Segmenten maken](segment-builder.md) voor meer informatie over het bouwen van segmenten.

Zodra het segment is gemaakt, kunt u een van de vele [export opties](export-destinations.md) gebruiken om het segment in andere toepassingen te gebruiken.

## <a name="ensure-updated-consent-status"></a>Actuele toestemmingsstatus waarborgen

Het is belangrijk om de toestemmingsstatus voor uw klanten up-to-date te houden. De geplande vernieuwing in Customer Insights importeert altijd de meest recente status van uw gegevensbronnen. Deze informatie wordt vervolgens verwerkt door middel van gegevensharmonisatie en resulteert in bijgewerkte klantprofielen. Deze bijgewerkte profielen worden vervolgens gebruikt om segmenten te vernieuwen om ervoor te zorgen dat u met de meest actuele informatie werkt.

Met andere woorden, zorg ervoor dat de brongegevens die in Customer Insights worden geïmporteerd, altijd over de nieuwste informatie beschikken.

Zie [Segmenten handmatig vernieuwen](segments.md#refresh-segments) of [een geplande vernieuwing configureren](schedule-refresh.md) voor meer informatie.

[!INCLUDE [footer-include](includes/footer-banner.md)]
