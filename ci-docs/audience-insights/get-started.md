---
title: Aan de slag met de doelgroepinzichten in Dynamics 365 Customer Insights
description: Een overzicht van doelgroepinzichten helpt resources om snel aan de slag te kunnen.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5e8545bc9bf0d953150248fa859c6ca71a12f9cf
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645258"
---
# <a name="get-started-with-dynamics-365-customer-insights-audience-insights-capability"></a>Aan de slag met de doelgroepinzichten in Dynamics 365 Customer Insights

Met doelgroepinzichten hebt u meer inzicht in uw klanten. Verbind gegevens uit verschillende transactie-, gedrags- en observatiebronnen om een 360-graden klantbeeld te creëren. Gebruik deze inzichten om klantgerichte ervaringen en processen te stimuleren. Harmoniseer en begrijp klantgegevens en zet ze in voor intelligente inzichten en acties.

## <a name="step-1-create-an-environment"></a>Stap 1: Een omgeving maken

U moet eerst een omgeving maken waarin u kunt werken. Als uw organisatie al een licentie heeft aangeschaft, zie [Een omgeving maken](create-environment.md). Als u met een proefversie van doelgroepinzichten wilt beginnen, raadpleegt u [Een proefomgeving instellen](../trial-signup.md). 

## <a name="step-2-explore-audience-insights"></a>Stap 2: Doelgroepinzichten verkennen

Als u zich voor de eerste keer aanmeldt bij doelgroepinzichten, kunt u instellingen configureren en het product verkennen.

1. [Meld u aan bij doelgroepinzichten](https://home.ci.ai.dynamics.com) met uw gebruikersaccount van Microsoft Azure Active Directory (AAD).

1. [Wijzig de omgeving](manage-environments.md#switch-environments) om demogegevens weer te geven en [doelgroepinzichten te verkennen](home.md).

##  <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Stap 3: Relaties voor uw gegevens opnemen, harmoniseren en instellen

Geharmoniseerde profielen vormen de basis om meer inzicht te krijgen en met de gegevens te werken. Haal gegevens op uit verschillende bronnen en voer het proces van gegevensharmonisatie uit om geharmoniseerde profielen te combineren. Geef relaties op tussen de opgenomen entiteiten en gebruik verrijkingsfuncties om informatie aan de profielen toe te voegen. 

1. Neem gegevens op door gegevensbronnen te maken op basis van meerdere opties. Kies tussen [Power Query-connectors](connect-power-query.md), een [Common Data Model-map](connect-common-data-model.md) of [Microsoft Dataverse](connect-common-data-service-lake.md). 

1. Voer het [proces van gegevensharmonisatie](data-unification.md) uit door de fasen van [toewijzing](map-entities.md), [overeenkomst](match-entities.md) en [samenvoeging](merge-entities.md) te doorlopen.

1. Leer de [entiteiten die het systeem maakt](entities.md), kennen en maak [relaties tussen de opgenomen entiteiten](relationships.md).
    
## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Stap 4: Geharmoniseerde profielen verbeteren met voorspellingen, activiteiten en metingen

Met ingestelde geharmoniseerde profielen kunt u uw gegevens verbeteren en de informatie die ze bieden verder vergroten.

1. Kies uit een groeiende bibliotheek van verrijkingsaanbieders om [uw klantgegevens te verrijken](enrichment-hub.md).

1. Gebruik [kant-en-klare modellen](predictions-overview.md) om het waarschijnlijke verloop of verwachte omzetten te voorspellen.

1. [Configureer activiteiten](activities.md) op basis van opgenomen gegevens en visualiseer interacties met uw klanten in een chronologische tijdlijn. 

1. [Bouw metingen in](measures.md) om uw bedrijfsdoelen en KPI's te meten.
 
## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Stap 5: Segmenten maken en gegevens activeren via verschillende exportopties

Nu uw gegevens compleet zijn en een breed scala aan informatie over uw klanten bevatten, is het tijd om op zoek te gaan naar manieren om die gegevens te verwerken. 

1. [Maak segmenten](segments.md), subsets van uw klantenbestand, om ervoor te zorgen dat uw acties relevant zijn voor de beoogde klanten.

1. Blader door de groeiende catalogus van [exportopties](export-destinations.md) waar u klantgegevens kunt gebruiken. U kunt gegevens bijvoorbeeld gegevens gebruiken om aanbiedingen te beheren en klanten te bereiken via digitale marketing.

1. Bekijk integratieopties, bijvoorbeeld met de [rechtstreekse verbinding met betrokkenheidsinzichten](../engagement-insights/integrate-audience-insights-engagement-insights.md) of met andere Dynamics 365-apps met de [invoegtoepassing Klantenkaart](customer-card-add-in.md).  


[!INCLUDE[footer-include](../includes/footer-banner.md)]
