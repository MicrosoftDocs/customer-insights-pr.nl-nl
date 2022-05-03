---
title: Aan de slag met zakelijke accounts als primaire doelgroep
description: Aan de slag met zakelijke accounts als primaire doelgroep Dynamics 365 Customer Insights.
ms.date: 10/19/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-connections
- customerInsights
ms.openlocfilehash: f16c8ad50ed290562fa9f223a3e8c86228e5331e
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646247"
---
# <a name="work-with-business-accounts"></a>Werken met zakelijke accounts

Met Dynamics 365 Customer Insights kunt u uw omgeving configureren voor verschillende primaire doelgroepen: individuele consumenten (B2C) en zakelijke accounts (B2B). In B2C-scenario's staan individuen centraal in de gegevens. Voor B2B zijn de primaire doelgroepen accounts (organisaties of bedrijven) en contactpersonen. Dit artikel helpt u om aan de slag te gaan met een omgeving voor zakelijke accounts. Het geeft een overzicht van de verschillen voor de functiegebieden in Customer Insights, afhankelijk van de focus van uw omgeving. Raadpleeg de documenten van de functiegebieden voor meer informatie over de verschillen. 

## <a name="create-an-environment-for-business-accounts"></a>Een omgeving maken voor zakelijke accounts

Beheerders kunnen [een omgeving maken in een bestaande organisatie](create-environment.md). In een stap in het proces voor het maken van een nieuwe omgeving wordt beheerders gevraagd om het primaire doel publiek van de omgeving. Als het de eerste configuratie is na aanschaf van een licentie, helpt een begeleide ervaring bij het creëren van de eerste omgeving.

U kunt vervolgens [gegevens opnemen](data-sources.md) voor zakelijke accounts en gerelateerde contactpersonen als gegevensbronnen uit alle ondersteunde bronnen.

Na het harmoniseren van de gegevens gaat u [accounthiërarchieën opgeven](relationships.md#set-up-account-hierarchies) als onderdeel van de relatieconfiguratie. U kunt ook [semantische toewijzingen configureren](semantic-mappings.md) om contactpersoon- en accountentiteiten te verbinden. 

## <a name="switch-between-primary-target-audience"></a>Schakelen tussen primaire doelgroepen

Als uw organisatie omgevingen onderhoudt voor individuele klanten en zakelijke accounts, kunt u met de schakeloptie in het linkerdeelvenster de primaire doelgroep kiezen.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Schakeloptie om de primaire doelgroep te schakelen tussen individuele klanten en zakelijke accounts.":::

## <a name="supported-feature-areas"></a>Ondersteunde functiegebieden

- [Activiteiten](activities.md): ondersteuning voor accounts en gerelateerde contactpersonen om activiteiten te maken en weer te geven in een tijdlijn.
- [Relaties](relationships.md): de activiteitenwizard helpt bij het maken van relaties tussen de entiteiten zodat in de accountweergave alle activiteiten van contactpersonen kunnen worden weergegeven. Contactpersonen kunnen inzoomen om de contactweergave te bekijken en hiërarchieën kunnen worden gebruikt voor aggregaties van accountactiviteiten.
- [Metingen](measures.md): ondersteunt metingen die worden gemaakt met de opbouwfunctie voor metingen op basis van één berekening. Er is een optionele instelling voor het totaliseren van subaccounts bij het maken van metingen.
- [Segmenten](segments.md): ondersteunt segmenten die helemaal opnieuw zijn gemaakt met de segmentbouwer. Nieuwe operators maken het mogelijk om de rekeninghiërarchie te gebruiken bij het bouwen van segmenten.
- [Gegevensopname](data-sources.md): alle functies in dit gebied zijn gelijk voor zakelijke accounts en individuele klanten.
- [Gegevensharmonisering](data-unification.md): alle functies in dit gebied zijn gelijk voor zakelijke accounts en individuele klanten.
- [Verrijking](enrichment-hub.md): sommige verrijkingstypes zijn alleen beschikbaar voor scenario's met individuele klanten, terwijl andere alleen beschikbaar zijn voor zakelijke accounts.
- [Voorspellingen en kant-en-klare modellen](predictions-overview.md): voorspelling van transactieverloop bevat aanvullende stappen voor zakelijke accounts. Andere voorspellingen zijn alleen beschikbaar voor individuele klanten.
- [Activering en export](export-destinations.md): export is beschikbaar voor zakelijke accounts en individuele klanten. Voor sommige exports is extra configuratie vereist en moeten contactgegevens in de onderliggende segmenten worden geprojecteerd om geldig te zijn voor zakelijke accounts.
- [Systeeminstellingen](system.md) en [gebruikersbeheer](permissions.md): alle functies in dit gebied zijn gelijk voor zakelijke accounts en individuele klanten.

