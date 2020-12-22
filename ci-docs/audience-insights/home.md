---
title: Startpagina in doelgroepinzichten
description: Verken de app op de startpagina.
ms.date: 09/30/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: bd16966eabb126d9c9945ededc53273df02c3369
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405495"
---
# <a name="create-a-new-environment"></a>Een nieuwe omgeving maken

## <a name="create-a-trial-environment"></a>Een omgeving voor een proefversie maken

U kunt zich aanmelden voor een proefversie op de [aanmeldingspagina voor proefversies](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Proeven verlopen na 30 dagen.

1. Kies de optie **Aanmelden voor een gratis proefperiode** en **Nu registreren**.

1. Geef uw werk- of schoole-mailadres op, vertel ons meer over uzelf en selecteer **Volgende**.

1. Geef een **Naam** op voor uw nieuwe omgeving. 

1. Selecteer het type proefversie.

1. Kies de **Regio** voor uw omgeving.

1. Optioneel, voor beheerders van een Dynamics 365-organisatie: selecteer **Geavanceerde instellingen** en geef de URL van uw organisatie op om voorspellingsfuncties zoals klantverloop te gebruiken.

1. Selecteer **Maken**. 

Nadat de omgeving is gemaakt, ziet u de **Demo**-omgeving waarin u de app kunt verkennen met fictieve gegevens. U kunt de voorbeeldgegevens aanpassen aan uw branche. Selecteer het pictogram **Instellingen** in de koptekst en vervolgens **Demo-instellingen**. Bovendien kunt u het visuele thema wijzigen. 

U kunt [overschakelen naar de omgeving](#change-between-environments) die u tijdens het aanmeldingsproces hebt gemaakt om met uw eigen gegevens te werken.

## <a name="create-a-new-production-or-sandbox-environment"></a>Een nieuwe productie- of sandbox-omgeving maken

Selecteer in uw omgeving het pictogram **Instellingen** in de koptekst en vervolgens **Nieuwe omgeving**.

Volg de stappen alsof u [een proefomgeving maakt](#create-a-trial-environment). U ziet een extra optie bij het selecteren van **Geavanceerde instellingen** om uw gegevens op te slaan in uw eigen Azure Data Lake. Geef uw accountnaam en accountsleutel op om een verbinding tot stand te brengen met uw Azure Data Lake. Standaard worden gegevens opgeslagen in het door Customer Insights beheerde data lake

> [!IMPORTANT]
> Door gegevens op te slaan in Azure Data Lake Storage, stemt u ermee in dat gegevens worden overgebracht naar en opgeslagen in de juiste geografische locatie voor dat Azure Storage-account, die kan afwijken van waar gegevens zijn opgeslagen in Dynamics 365 Customer Insights. [Meer informatie op het Microsoft Trust Center.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>De startpagina verkennen

U kunt [toegang krijgen tot uw Customer Insights-omgeving](https://home.ci.ai.dynamics.com/) op de volgende URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
De **start** pagina toont een overzicht van uw klantenbestand en de belangrijkste metrische gegevens om de status van uw bedrijf bij te houden.

> [!div class="mx-imgBorder"] 
> ![Inzichten op startpagina](media/home-page-insights.png "Inzichten op startpagina")

Onder **Recente segmenten** ziet u groepen klanten op basis van demografische, gedrags- of transactiekenmerken die u hebt gedefinieerd. [Segmenten maken](segments.md) helpt u om uw bedrijfsactiviteiten gerichter aan te pakken.

**Recente metingen** toont tegels met [metingen](measures.md). Metingen zijn key performance indicators (KPI's) die u hebt gedefinieerd. Bijvoorbeeld de gemiddelde kans op klantverloop of gemiddelde online uitgaven per klant.

De sectie **Recente verrijkingen** bevat de resultaten van de verrijkingsruns die onlangs zijn voltooid. Verrijkingen voegen informatie toe over uw klantenbestand. Bijvoorbeeld door de interesses en merken waar ze affiniteit mee hebben te begrijpen. Deze informatie kan worden ontgrendeld met de mogelijkheden voor [verrijking](enrichment-microsoft-graph.md), na het voltooien van de fasen voor [toewijzen](map-entities.md), [afstemmen](match-entities.md) en [samenvoegen](merge-entities.md).

## <a name="change-between-environments"></a>Overschakelen tussen omgevingen

Zodra u [gegevensbronnen](data-sources.md) hebt ingesteld en geconfigureerd, wilt u overschakelen van een demo-omgeving naar een live omgeving. Door gebruik te maken van de productieomgeving kunt u met uw eigen klantgegevens werken. Selecteer het besturingselement **Omgeving** in de rechterbovenhoek van de pagina om van omgeving te veranderen.

> [!div class="mx-imgBorder"] 
> ![Omgeving omschakelen](media/home-page-environment-switcher.png "Omgeving omschakelen")

Beheerders kunnen [meerdere omgevingen](manage-environments.md) maken en beheren. Het onderhouden van meer dan één omgeving kan handig zijn als uw organisatie bijvoorbeeld internationaal opereert en u gegevens en inzichten op verschillende manieren moet kunnen scheiden.

## <a name="next-step"></a>Volgende stap

Als u uw eigen inzichten op de startpagina wilt bekijken, moet u eerst [gegevensbronnen toevoegen](data-sources.md) en uw gegevens [harmoniseren](data-unification.md) om klantprofielen op te bouwen.
