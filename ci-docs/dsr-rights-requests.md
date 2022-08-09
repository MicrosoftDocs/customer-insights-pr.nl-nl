---
title: Rechten van betrokkenen (DSR) onder AVG | Microsoft Docs
description: Reageren op verzoeken van betrokkenen voor Dynamics 365 Customer Insights.
ms.date: 05/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6c6ce49c18de3a09d28138316d893e6842919042
ms.sourcegitcommit: ff0f4b5664d995870c91adb87c7d3780a582efca
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2022
ms.locfileid: "9146689"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Rechten van betrokkenen (DSR) onder AVG

De Algemene verordening gegevensbescherming (AVG) van de Europese Unie is sinds 25 mei 2018 van kracht. Het geeft individuen aanzienlijke rechten met betrekking tot hun gegevens. Het gaat bij de AVG om het beschermen en activeren van de privacyrechten van individuen. Meer informatie over de inzet van Microsoft voor beveiliging en compliance vindt u op het [Microsoft Vertrouwenscentrum](https://www.microsoft.com/trust-center).

We doen er alles aan om onze klanten te helpen aan hun AVG-vereisten te voldoen. Het omvat het recht gegevens te verwijderen en te exporteren die persoonlijke informatie bevatten, zoals gebruikers-id's, telefoonnummers en e-mailadressen. Beheerders kunnen gebruikersverzoeken implementeren om persoonlijke gegevens te verwijderen of te exporteren.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Reageren op verwijderverzoeken van betrokkenen in het kader van de AVG voor Dynamics 365 Customer Insights

Het 'recht op verwijdering' van persoonsgegevens uit de klantgegevens van een organisatie is een belangrijke bescherming in de Algemene verordening gegevensbescherming (AVG). Het verwijderen van persoonlijke gegevens omvat het verwijderen van alle persoonlijke gegevens en door het systeem gegenereerde logboeken, behalve auditlogboekinformatie.

#### <a name="manage-data-subject-delete-requests"></a>Verwijderingsverzoeken van betrokkenen beheren

Customer Insights biedt de volgende mogelijkheden binnen het product om persoonlijke gegevens voor een specifieke klant of gebruiker te verwijderen:

- **Verwijderingsverzoeken voor klantgegevens beheren**: klantgegevens in Customer Insights worden opgenomen vanuit originele gegevensbronnen buiten Customer Insights. Verwijderingsverzoeken in het kader van de AVG moeten eerst worden uitgevoerd in de originele gegevensbron.
- **Beheer verwijderingsverzoeken voor gebruikersgegevens van Customer Insights**: gegevens voor gebruikers worden gemaakt door Customer Insights. Alle verwijderingsverzoeken in het kader van de AVG moeten worden uitgevoerd in Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Verzoeken voor het verwijderen van klantgegevens beheren

Een Customer Insights-beheerder kan deze stappen volgen om klantgegevens te verwijderen die in de gegevensbron zijn verwijderd. Zorg ervoor dat het verwijderingsverzoek is uitgevoerd in uw gegevensbron voordat u doorgaat met de onderstaande stappen. 

1. Aanmelden bij Dynamics 365 Customer Insights.
1. Ga naar **Gegevens** > **Gegevensbronnen**
1. Voor elke gegevensbron in de lijst met verwijderde klantgegevens:
   1. Selecteer het verticale weglatingsteken (&vellip;) en selecteer vervolgens **Vernieuwen**.
   1. Controleer de status van de gegevensbron onder **Status**. Een vinkje betekent dat de vernieuwing is geslaagd. Een gevarendriehoek betekent dat er iets mis is gegaan. Neem bij een gevarendriehoek contact op met D365CI@microsoft.com.
1. Voer na een succesvolle vernieuwing van de gegevensbronnen ook de downstream-vernieuwingen uit. Vooral als u geen terugkerende volledige vernieuwing van Customer Insights heeft gepland. 

> [!IMPORTANT]
> Statische segmenten worden niet opgenomen in een volledige vernieuwing of stroomafwaartse vernieuwingen na een verwijderingsverzoek. Om ervoor te zorgen dat klantgegevens ook uit statische segmenten worden verwijderd, maakt u de statische segmenten opnieuw met de vernieuwde brongegevens.

> [!div class="mx-imgBorder"]
> ![Verwijderingsverzoeken voor klantgegevens in het kader van de AVG afhandelen.](media/gdpr-data-sources.png "Verwijderingsverzoeken voor klantgegevens in het kader van de AVG afhandelen")

##### <a name="manage-delete-requests-for-user-data"></a>Verwijderingsverzoeken voor gebruikersgegevens beheren

Een Customer Insights-beheerder kan deze stappen volgen om gegevens van Customer Insights-gebruikers te verwijderen:

1. Aanmelden bij Dynamics 365 Customer Insights.
2. Ga naar **Beheerder** > **Beveiliging** > **Machtigingen**.
3. Schakel het selectievakje in voor de gebruiker die u wilt verwijderen.
4. Selecteer **Verwijderen**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Reageren op exportverzoeken door betrokkenen in het kader van de AVG

Als onderdeel van ons streven om met u samen te werken op uw reis naar naleving van de Algemene verordening gegevensbescherming (AVG), hebben we documentatie ontwikkeld om u te helpen te reageren op verzoeken van betrokkenen.

#### <a name="manage-export-and-view-requests"></a>Export- en weergaveverzoeken beheren

Door het recht op gegevensoverdraagbaarheid mogen betrokkenen een kopie van hun persoonlijke gegevens in elektronische indeling (een "gestructureerde, algemeen gebruikte, machineleesbare en interoperabele indeling") aanvragen die naar een andere gegevensbeheerder kan worden verzonden.

##### <a name="export-customer-data-tenant-admin"></a>Klantgegevens exporteren (tenantbeheerder)

Een tenantbeheerder kan deze stappen volgen om gegevens te exporteren:

1. Verzend een e-mail naar D365CI@microsoft.com met het e-mailadres van de klant in de aanvraag. Het Customer Insights-team verzendt een e-mail naar het geregistreerde e-mailadres van de tenantbeheerder waarin wordt gevraagd om bevestiging voor het exporteren van gegevens.
2. Erken de bevestiging om de gegevens voor de gevraagde klant te exporteren.
3. Ontvang de geëxporteerde gegevens via het e-mailadres van de tenantbeheerder.

##### <a name="export-user-data-tenant-admin"></a>Gebruikersgegevens exporteren (tenantbeheerder)

1. Verzend een e-mail naar D365CI@microsoft.com met het e-mailadres van de gebruiker in de aanvraag. Het Customer Insights-team verzendt een e-mail naar het geregistreerde e-mailadres van de tenantbeheerder waarin wordt gevraagd om bevestiging voor het exporteren van gegevens.
2. Erken de bevestiging om de gegevens voor de gevraagde gebruiker te exporteren.
3. Ontvang de geëxporteerde gegevens via het e-mailadres van de tenantbeheerder.

### <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Afhandeling van gegevensverwijdering in Dynamics 365 Customer Insights

1. Gegevens worden verwijderd (gegevenspartities en gegevenssnapshots) als de gegevenspartities en gegevenssnapshots meer dan 30 dagen inactief zijn, wat betekent dat ze zijn vervangen door een nieuwe gegevenspartitie en snapshot via een vernieuwing van gegevensbronnen.
2. Niet alle gegevens en snapshots worden verwijderd. De meest recente gegevenspartitie en gegevensmomentopname zijn per definitie actief omdat ze worden gebruikt in Customer Insights. Voor de meest recente gegevens maakt het niet uit of de gegevensbronnen in de afgelopen 30 dagen niet zijn vernieuwd.

[!INCLUDE [footer-include](includes/footer-banner.md)]
