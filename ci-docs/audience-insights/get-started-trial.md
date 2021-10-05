---
title: Een proefversie van Customer Insights maken en configureren
description: Stappen om een proefabonnement te krijgen voor Dynamics 365 Customer Insights en het te configureren.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 3a235e924395a606b9332de3d205289288a597a9
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558817"
---
# <a name="set-up-a-trial-environment"></a>Een proefomgeving installeren 

Met een proefversie van Dynamics 365 Customer Insights kunt u de belangrijkste mogelijkheden bekijken en meer te weten komen over de verschillende functies. Een proefabonnement wordt na afloop verwijderd. Proefomgevingen worden gemaakt door individuele gebruikers die beheerder van hun proefomgeving worden. Ze kunnen meer gebruikers uitnodigen voor hun proefperiode en de verschillende functies configureren.

## <a name="create-a-trial-environment"></a>Een omgeving voor een proefversie maken

U kunt zich aanmelden voor een proefversie op de [aanmeldingspagina voor proefversies](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

1. Kies de optie **Aanmelden voor een gratis proefperiode** en **Nu registreren**.

1. Geef uw e-mailadres voor werk of school op, vertel ons meer over uzelf en selecteer **Aan de slag**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Dialoogvenster voor registratie voor een proefexemplaar":::

1. Controleer de algemene voorwaarden en selecteer **Doorgaan** om te bevestigen.

1. Geef een **Naam** op voor uw nieuwe omgeving. 

1. Stel het **Type** omgeving in als **Proefversie**.

1. In het veld **Selecteer een demo uit een bedrijfstak** kunt u optioneel een branchespecifieke gegevensset kiezen. U kunt ook later [omschakelen naar een demo uit een bedrijfstak](#use-industry-specific-demo-data-sets-in-audience-insights) en beginnen met de standaard gegevensset.

1. Kies de **Regio** voor uw omgeving.

1. Als u de beheerder van een Dynamics 365-organisatie bent kunt u ook **Geavanceerde instellingen** selecteren en de URL van uw organisatie opgeven om voorspellingsfuncties te gebruiken als voorspelling over klantverloop. 

1. Selecteer **Maken**. 

De instelling van de omgeving kan enkele ogenblikken in beslag nemen. Na voltooiing wordt u doorverwezen naar de demo-omgeving of de bedrijfstakdemo die u in de bovenstaande stap hebt gekozen. U kunt de app nu verkennen met alleen-lezen demogegevens. Zie [Scenariospecifieke demogegevens in uw eigen omgeving maken](#create-scenario-specific-demo-data-in-your-own-environment) als u uw eigen gegevens aan de omgeving wilt toevoegen.

:::image type="content" source="media/trial-environment.png" alt-text="Schermafbeelding van een nieuwe proefomgeving.":::

## <a name="use-industry-specific-demo-data-sets-in-audience-insights"></a>Bedrijfstakspecifieke demogegevenssets gebruiken in doelgroepinzichten

Reële gegevensbronnen met elkaar verbinden is een van de cruciale stappen in het gebruik van de kracht van Customer Insights. Om functies uit te proberen zonder uw eigen gegevens te belemmeren, kunt u optioneel bedrijfstakspecifieke demogegevens gebruiken. Er zijn demogegevenssets beschikbaar voor de volgende bedrijfstakken: 

-   Auto-industrie
-   Bankwezen
-   Consumptiegoederen
-   Overheid
-   Gezondheidszorg
-   Horeca
-   Verzekering
-   Productie
-   Professionele services
-   Detailhandel

### <a name="see-industry-specific-demo-data-in-trials"></a>Bekijk bedrijfstakspecifieke demogegevens in proefversies

Voor een alleen-lezen versie van Customer Insights, toegesneden op een specifieke bedrijfstak of scenario, start u in de demo-omgeving. 
 
1.  Kies in doelgroepinzichten de **Demo**-omgeving in de omgevingskiezer.

2.  Kies bij **Start** een optie in het vervolgkeuzemenu Selecteer een demo uit een bedrijfstak.

:::image type="content" source="media/trial-select-industry-demo.png" alt-text="Kies een bedrijfstak voor de proefomgeving.":::

### <a name="create-scenario-specific-demo-data-in-your-own-environment"></a>Scenariospecifieke demogegevens in uw eigen omgeving maken

Selecteer als beheerder de omgevingskiezer in de app-header om een nieuwe omgeving te maken. In de nieuwe omgeving configureert u uw eigen gegevensbronnen en stelt u de app in naar uw wensen. 

1.  Ga in doelgroepinzichten naar **Gegevens** > **Gegevensbronnen**.

2.  Om uw eigen gegevensbronnen te importeren, gaat u naar de [gids voor gegevensopname](data-sources.md).     
   Als u liever werkt met voorbeeldgegevens waarmee u gegevensopname kunt uitproberen, kunt u de demogegevens uit een bedrijfstak in uw omgeving opnemen. Kies de optie **Importeren uit Datahub** en volg de onderstaande stappen.

3.  Selecteer de bedrijfstakkaart die bij uw scenario past. 

4.  Controleer de voorgestelde naam van de gegevensbron en wijzig deze eventueel. 

5.  Selecteer **Volgende** om de voorbeeldgegevens op te nemen. 

U kunt nu de opgenomen gegevens gebruiken om Customer Insights af te stemmen op uw scenario. Als u een omgeving wilt zien die specifiek is voor de opgenomen demogegevens, kiest u de optie **<Industry>-demo** in de omgevingskiezer.

## <a name="limitations-in-trials"></a>Beperkingen in proefversies

- Proefversies zijn standaard 30 dagen actief. U kunt ze echter vanaf dag 23 verlengen wanneer u zich aanmeldt bij uw proefversie.
- U kunt uw eigen Azure Data Lake-opslagaccount niet gebruiken om uitvoergegevens op te slaan in een proefversie. U kunt echter gegevens van een Data Lake-opslagaccount opnemen.
- U kunt maximaal 3 GB aan gegevens opslaan in de Dataverse-omgeving die automatisch wordt ingericht wanneer u een proefversie van Customer Insights start.

## <a name="copy-data-from-a-trial-to-a-paid-subscription"></a>Gegevens kopiëren van een proefversie naar een betaald abonnement

Over het algemeen raden we aan opnieuw te beginnen met uw eigen gegevens bij het upgraden naar de betaalde versie van Customer Insights. 

Optioneel kunt u uw gegevens uit een proefomgeving kopiëren als u Customer Insights aanschaft. U moet de beheerder van de Customer Insights-proefversie en de algemene beheerder van uw Microsoft 365-tenant zijn, of de Dynamics 365-beheerder in uw organisatie om de instellingen van een proefomgeving naar een betaalde omgeving te migreren. 

Nadat u voor de eerste keer bent ingelogd op uw betaalde exemplaar van Customer Insights, wordt u gevraagd een nieuwe omgeving te maken. In dit proces kunt u ervoor kiezen de configuratie uit een bestaande omgeving te kopiëren en de meeste instellingen te migreren. Als u de hierboven genoemde machtigingen hebt, wordt de proefomgeving in deze lijst weergegeven. Zie [De omgevingsconfiguratie kopiëren](manage-environments.md#copy-the-environment-configuration) voor meer informatie.

## <a name="next-steps"></a>Volgende stappen

Bekijk de volgende artikelen om u op weg te helpen met het configureren van Customer Insights. 

- [Voeg meer gebruikers toe en wijs machtigingen toe](permissions.md).
- [Uw gegevensbronnen opnemen](data-sources.md) en deze het [proces voor gegevensharmonisatie](data-unification.md) laten doorlopen om [uniforme klantprofielen](customer-profiles.md) te krijgen.
- [Verrijk de uniforme klantprofielen](enrichment-hub.md) of [voer voorspellende modellen uit](predictions-overview.md).
- Maak [segmenten](segments.md) om klanten te groeperen en [meetcriteria](measures.md) KPI's te bekijken.
- Stel [verbindingen](connections.md) en [exports](export-destinations.md) in om subsets van uw gegevens in andere toepassingen te verwerken.
