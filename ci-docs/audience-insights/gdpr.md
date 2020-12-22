---
title: Rechten van betrokkenen (DSR) onder AVG | Microsoft Docs
description: Reageren op verzoeken van betrokkenen om de mogelijkheden van Dynamics 365 Customer Insights doelgroepinzichten.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f276a73feca52023391ad92fbc84359921b85328
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405496"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Rechten van betrokkenen (DSR) onder AVG

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Reageren op AVG-verwijderingsverzoeken voor gebruikersgegevens van betrokkenen voor Dynamics 365 Customer Insights doelgroepinzichten

Het 'recht op verwijdering' van persoonsgegevens uit de klantgegevens van een organisatie is een belangrijke bescherming in de Algemene verordening gegevensbescherming (AVG). Het verwijderen van persoonlijke gegevens omvat het verwijderen van alle persoonlijke gegevens en door het systeem gegenereerde logboeken, behalve auditlogboekinformatie.

### <a name="manage-data-subject-delete-requests"></a>Verwijderingsverzoeken van betrokkenen beheren

Doelgroepinzichten bieden de volgende mogelijkheden binnen het product om persoonlijke gegevens voor een specifieke klant of gebruiker te verwijderen:

- **Verwijderingsverzoeken voor klantgegevens beheren**: klantgegevens in Customer Insights worden opgenomen vanuit originele gegevensbronnen buiten Customer Insights. Alle verwijderingsverzoeken in het kader van de AVG moeten worden uitgevoerd in de originele gegevensbron.
- **Beheer verwijderingsverzoeken voor gebruikersgegevens van Customer Insights**: gegevens voor gebruikers worden gemaakt door Customer Insights. Alle verwijderingsverzoeken in het kader van de AVG moeten worden uitgevoerd in Customer Insights.

#### <a name="manage-delete-requests-for-customer-data"></a>Verwijderingsverzoeken voor klantgegevens beheren

Een Customer Insights-beheerder kan deze stappen volgen om klantgegevens te verwijderen die in de gegevensbron zijn verwijderd:

1. Aanmelden bij Dynamics 365 Customer Insights.
2. Ga in doelgroepinzichten naar **Gegevens** > **Gegevensbronnen**
3. Voor elke gegevensbron in de lijst met verwijderde klantgegevens:
   1. Selecteer (...) en selecteer vervolgens **Vernieuwen**.
   2. Controleer de status van de gegevensbron onder **Status**. Een vinkje betekent dat de vernieuwing is geslaagd. Een gevarendriehoek betekent dat er iets mis is gegaan. Neem bij een gevarendriehoek contact op met D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Verwijderingsverzoeken voor klantgegevens in het kader van de AVG afhandelen](media/gdpr-data-sources.png "Verwijderingsverzoeken voor klantgegevens in het kader van de AVG afhandelen")

#### <a name="manage-delete-requests-for-user-data"></a>Verwijderingsverzoeken voor gebruikersgegevens beheren

Een Customer Insights-beheerder kan deze stappen volgen om gegevens van Customer Insights-gebruikers te verwijderen:

1. Aanmelden bij Dynamics 365 Customer Insights.
2. Ga in doelgroepinzichten naar **Beheer** > **Machtigingen**.
3. Schakel het selectievakje in voor de gebruiker die u wilt verwijderen.
4. Selecteer **Verwijderen**.

> [!div class="mx-imgBorder"]
> ![AVG-verwijderingsverzoeken voor gebruikersgegevens beheren](media/gdpr-permissions.png "AVG-verwijderingsverzoeken voor gebruikersgegevens afhandelen")

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Reageren op exportverzoeken door betrokkenen in het kader van de AVG

Als onderdeel van ons streven om met u samen te werken op uw reis naar naleving van de Algemene verordening gegevensbescherming (AVG), hebben we documentatie ontwikkeld om u te helpen voorbereiden. Deze documentatie beschrijft de stappen die u vandaag kunt nemen om AVG-naleving te ondersteunen wanneer u doelgroepinzichten gebruikt.

### <a name="manage-export-and-view-requests"></a>Export- en weergaveverzoeken beheren

Door het recht op gegevensoverdraagbaarheid mogen betrokkenen een kopie van hun persoonlijke gegevens in elektronische indeling (een "gestructureerde, algemeen gebruikte, machineleesbare en interoperabele indeling") aanvragen die naar een andere gegevensbeheerder kan worden verzonden.

#### <a name="export-customer-data-tenant-admin"></a>Klantgegevens exporteren (tenantbeheerder)

Een tenantbeheerder kan deze stappen volgen om gegevens te exporteren:

1. Verzend een e-mail naar D365CI@microsoft.com met het e-mailadres van de klant in de aanvraag. Het Customer Insights-team verzendt een e-mail naar het geregistreerde e-mailadres van de tenantbeheerder waarin wordt gevraagd om bevestiging voor het exporteren van gegevens.
2. Erken de bevestiging om de gegevens voor de gevraagde klant te exporteren.
3. Ontvang de geëxporteerde gegevens via het e-mailadres van de tenantbeheerder.

#### <a name="export-user-data-tenant-admin"></a>Gebruikersgegevens exporteren (tenantbeheerder)

1. Verzend een e-mail naar D365CI@microsoft.com met het e-mailadres van de gebruiker in de aanvraag. Het Customer Insights-team verzendt een e-mail naar het geregistreerde e-mailadres van de tenantbeheerder waarin wordt gevraagd om bevestiging voor het exporteren van gegevens.
2. Erken de bevestiging om de gegevens voor de gevraagde gebruiker te exporteren.
3. Ontvang de geëxporteerde gegevens via het e-mailadres van de tenantbeheerder.
