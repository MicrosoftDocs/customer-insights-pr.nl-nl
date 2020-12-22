---
title: Schema's voor Customer Insights-entiteiten in Common Data Model
description: Werken met entiteiten in Common Data Model.
ms.date: 04/17/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2cf01029ef6b64fe566022d09ce65bca3603189c
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643902"
---
# <a name="entity-schemas-in-common-data-model"></a>Entiteitsschema's in Common Data Model

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[Common Data Model](https://docs.microsoft.com/common-data-model/) is een declaratieve specificatie en een definitie van standaardentiteiten waarmee veelgebruikte concepten en activiteiten voor verschillende zakelijke en productiviteitstoepassingen worden aangeduid. Dit model wordt ook uitgebreid voor observatie- en analytische gegevens. Common Data Model biedt goed gedefinieerde, modulaire en uitbreidbare zakelijke entiteiten, zoals Account, Business unit, Aanvraag, Contactpersoon, Potentiële klant, Verkoopkans en Product, en interacties met leveranciers, medewerkers en klanten, zoals activiteiten en serviceovereenkomsten. Iedereen kan Common Data Model-definities bouwen en uitbreiden om aanvullende bedrijfsspecifieke ideeën vast te leggen.

Met dit gedeelde gegevensmodel kunnen toepassingen en gegevensintegrators eenvoudiger samenwerken door een uniforme definitie van gegevens te bieden. Common Data Model bevat een uitgebreid metadatasysteem met standaardentiteiten, relaties, hiërarchieën, eigenschappen en meer. Het is afkomstig van Dynamics 365-apps en is open source op GitHub met meer dan 260 standaardentiteiten. Een groot systeem van interne en externe partners draagt branchespecifieke concepten bij aan Common Data Model.

Meerdere systemen en platforms implementeren vandaag Common Data Model, waaronder Power BI-gegevensstromen en Azure Data Services. Het wordt al ondersteund in Common Data Service, Dynamics 365, Power Apps, Power BI, en aankomende Azure-gegevensservices, die direct waarde opleveren voor het [Open Data Initiative](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>Schema's van Customer Insights-entiteiten

Om een 360-gradenbeeld van de klant te krijgen en Customer Insights-modellen beschikbaar te maken in Common Data Model voor uitbreidbaarheid, hebben we de volgende entiteitsschema's gepubliceerd:

| Entiteit | Beschrijving |
|---------|---------|
|[CustomerActivity](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Een activiteit die wordt uitgevoerd door een gebruiker die waarnemingswaarde heeft voor het bedrijf. |
|[CustomerProfile](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Een persoon of organisatie die heeft gehandeld of het potentieel heeft om zakelijke activiteiten uit te oefenen. |
|[MeasureDefinition](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Definitie van KPI's die zijn gepartitioneerd door nul of meer dimensies (zoals Maandelijks actieve gebruikers, Totale uitgaven per klant, Gemiddelde klantwervingskosten) |
|[Segment](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Definieert een groep leden met gemeenschappelijke kenmerken. |
|[SegmentMembership](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Leden die deelnemen aan een bepaald segment. |

Zie de documentatie voor meer informatie over de [entiteitsschema's van Customer Insights in Common Data Model](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Bekijk entiteiten met de Common Data Model Entity Navigator

U kunt entiteiten bekijken in de [Common Data Model Entity Navigator](https://microsoft.github.io/CDM/). Selecteer de knop **Laden uit GitHub!** en navigeer naar **foundationCommon** > **crmCommon** > **oplossingen** > **customerInsights** waar u de lijst met Customer Insights-entiteiten en hun definities vindt.
> [!div class="mx-imgBorder"]
> ![CDM Entity Navigator met entiteit CustomerActivity](media/CDM-entity-navigator.png "CDM Entity Navigator met entiteit CustomerActivity")
