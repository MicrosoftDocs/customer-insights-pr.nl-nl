---
title: Startpagina in doelgroepinzichten
description: Verken de app op de startpagina.
ms.date: 01/07/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: bf9080c564850bca0c239b7317eed2fc0f77d9f3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597229"
---
# <a name="create-a-new-environment"></a>Een nieuwe omgeving maken

## <a name="create-a-trial-environment"></a>Een omgeving voor een proefversie maken

U kunt zich aanmelden voor een proefversie op de [aanmeldingspagina voor proefversies](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Proeven verlopen na 30 dagen.

1. Kies de optie **Aanmelden voor een gratis proefperiode** en **Nu registreren**.

1. Geef uw werk- of schoole-mailadres op, vertel ons meer over uzelf en selecteer **Volgende**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Dialoogvenster voor registratie voor een proefexemplaar":::

1. Geef een **Naam** op voor uw nieuwe omgeving. 

1. Selecteer het type proefversie.

1. Kies de **Regio** voor uw omgeving.

1. Optioneel, voor beheerders van een Dynamics 365-organisatie: selecteer **Geavanceerde instellingen** en geef de URL van uw organisatie op om voorspellingsfuncties zoals klantverloop te gebruiken.

1. Selecteer **Maken**. 

Nadat de omgeving is gemaakt, ziet u de **Demo**-omgeving waarin u de app kunt verkennen met fictieve gegevens. U kunt de voorbeeldgegevens aanpassen aan uw branche. Selecteer het pictogram **Instellingen** in de koptekst en vervolgens **Demo-instellingen**. Bovendien kunt u het visuele thema wijzigen. 

U kunt [overschakelen naar de omgeving](#switch-environments) die u tijdens het aanmeldingsproces hebt gemaakt om met uw eigen gegevens te werken.

## <a name="create-a-new-production-or-sandbox-environment"></a>Een nieuwe productie- of sandbox-omgeving maken

Selecteer in uw omgeving de kiezer voor **Omgevingen** in de app-koptekst en selecteer **Nieuw**​.

Volg de stappen alsof u [een proefomgeving maakt](#create-a-trial-environment). Standaard worden gegevens opgeslagen in het door Customer Insights beheerde data lake U ziet een extra optie bij het selecteren van **Geavanceerde instellingen** om uw gegevens op te slaan in uw eigen Azure Data Lake. Geef uw accountnaam en accountsleutel op om een verbinding tot stand te brengen met uw Azure Data Lake. 

> [!IMPORTANT]
> Door gegevens op te slaan in Azure Data Lake Storage, stemt u ermee in dat gegevens worden overgebracht naar en opgeslagen in de juiste geografische locatie voor dat Azure Storage-account, die kan afwijken van waar gegevens zijn opgeslagen in Dynamics 365 Customer Insights. [Meer informatie op het Microsoft Trust Center.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>De startpagina verkennen

U kunt [toegang krijgen tot doelgroepinzichten van Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) via de volgende URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/)​.
De **Startpagina** bevat een overzicht van segmenten, metingen en verrijkingsgegevens (indien geconfigureerd) nadat de fasen [toewijzen](map-entities.md), [overeenkomen](match-entities.md) en [samenvoegen](merge-entities.md) zijn afgerond.

> [!div class="mx-imgBorder"] 
> ![Inzichten op startpagina](media/home-page-insights.png "Inzichten op startpagina")

Onder **Recente segmenten** ziet u groepen klanten op basis van demografische, gedrags- of transactiekenmerken die u hebt gedefinieerd. Met [Segmenten maken](segments.md) kunt u uw klantenbestand groeperen en uw zakelijke activiteiten beter afstemmen.

**Recente metingen** bevat tegels met [key performance indicators (KPI's)](measures.md) die u hebt gedefinieerd. Bijvoorbeeld de gemiddelde kans op klantverloop of de gemiddelde online uitgaven per klant.

De sectie **Recente verrijkingen** bevat de resultaten van de verrijkingsruns die onlangs zijn voltooid. [Verrijkingen](enrichment-hub.md) voegen informatie toe over uw klantenbestand. Bijvoorbeeld door de interesses en merken waar ze affiniteit mee hebben te begrijpen.

## <a name="switch-environments"></a>Omgevingen omschakelen

Selecteer het besturingselement **Omgeving** in de rechterbovenhoek van de pagina om van omgeving te veranderen.

> [!div class="mx-imgBorder"] 
> ![Omgeving omschakelen](media/home-page-environment-switcher.png "Omgeving omschakelen")

Beheerders kunnen [meerdere omgevingen](manage-environments.md) maken en beheren. Het onderhouden van meer dan één omgeving kan handig zijn als uw organisatie bijvoorbeeld internationaal opereert en u gegevens en inzichten op verschillende manieren moet kunnen scheiden.

## <a name="next-step"></a>Volgende stap

Als u uw eigen inzichten op de startpagina wilt bekijken, moet u eerst [gegevensbronnen toevoegen](data-sources.md) en uw gegevens [harmoniseren](data-unification.md) om klantprofielen op te bouwen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]