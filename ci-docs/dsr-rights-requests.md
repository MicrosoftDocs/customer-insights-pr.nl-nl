---
title: Rechten van betrokkenen (DSR) onder AVG | Microsoft Docs
description: Reageren op verzoeken van betrokkenen om de mogelijkheden van Dynamics 365 Customer Insights doelgroepinzichten.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6faaeb6a1ee34c3e5c8e7d465b37cee589bc920c
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483656"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Rechten van betrokkenen (DSR) onder AVG

De Algemene verordening gegevensbescherming (AVG) van de Europese Unie is sinds 25 mei 2018 van kracht. Het geeft individuen aanzienlijke rechten met betrekking tot hun gegevens. Het gaat bij de AVG om het beschermen en activeren van de privacyrechten van individuen. Meer informatie over de inzet van Microsoft voor beveiliging en compliance vindt u op het [Microsoft Vertrouwenscentrum](https://www.microsoft.com/trust-center).

We doen er alles aan om onze klanten te helpen aan hun AVG-vereisten te voldoen. Het omvat het recht gegevens te verwijderen en te exporteren die persoonlijke informatie bevatten, zoals gebruikers-id's, telefoonnummers en e-mailadressen. Beheerders kunnen gebruikersverzoeken implementeren om persoonlijke gegevens te verwijderen of te exporteren.

## <a name="audience-insights"></a>Doelgroepinzichten

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Reageren op AVG-verwijderingsverzoeken voor gebruikersgegevens van betrokkenen voor Dynamics 365 Customer Insights doelgroepinzichten

Het 'recht op verwijdering' van persoonsgegevens uit de klantgegevens van een organisatie is een belangrijke bescherming in de Algemene verordening gegevensbescherming (AVG). Het verwijderen van persoonlijke gegevens omvat het verwijderen van alle persoonlijke gegevens en door het systeem gegenereerde logboeken, behalve auditlogboekinformatie.

#### <a name="manage-data-subject-delete-requests"></a>Verwijderingsverzoeken van betrokkenen beheren

Doelgroepinzichten bieden de volgende mogelijkheden binnen het product om persoonlijke gegevens voor een specifieke klant of gebruiker te verwijderen:

- **Verwijderingsverzoeken voor klantgegevens beheren**: klantgegevens in Customer Insights worden opgenomen vanuit originele gegevensbronnen buiten Customer Insights. Alle verwijderingsverzoeken in het kader van de AVG moeten worden uitgevoerd in de originele gegevensbron.
- **Beheer verwijderingsverzoeken voor gebruikersgegevens van Customer Insights**: gegevens voor gebruikers worden gemaakt door Customer Insights. Alle verwijderingsverzoeken in het kader van de AVG moeten worden uitgevoerd in Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Verzoeken voor het verwijderen van klantgegevens beheren

Een Customer Insights-beheerder kan deze stappen volgen om klantgegevens te verwijderen die in de gegevensbron zijn verwijderd:

1. Aanmelden bij Dynamics 365 Customer Insights.
2. Ga in doelgroepinzichten naar **Gegevens** > **Gegevensbronnen**
3. Voor elke gegevensbron in de lijst met verwijderde klantgegevens:
   1. Selecteer (...) en selecteer vervolgens **Vernieuwen**.
   2. Controleer de status van de gegevensbron onder **Status**. Een vinkje betekent dat de vernieuwing is geslaagd. Een gevarendriehoek betekent dat er iets mis is gegaan. Neem bij een gevarendriehoek contact op met D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Verwijderingsverzoeken voor klantgegevens in het kader van de AVG afhandelen.](audience-insights/media/gdpr-data-sources.png "Verwijderingsverzoeken voor klantgegevens in het kader van de AVG afhandelen")

##### <a name="manage-delete-requests-for-user-data"></a>Verwijderingsverzoeken voor gebruikersgegevens beheren

Een Customer Insights-beheerder kan deze stappen volgen om gegevens van Customer Insights-gebruikers te verwijderen:

1. Aanmelden bij Dynamics 365 Customer Insights.
2. Ga in doelgroepinzichten naar **Beheer** > **Machtigingen**.
3. Schakel het selectievakje in voor de gebruiker die u wilt verwijderen.
4. Selecteer **Verwijderen**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Reageren op exportverzoeken door betrokkenen in het kader van de AVG

Als onderdeel van ons streven om met u samen te werken op uw reis naar naleving van de Algemene verordening gegevensbescherming (AVG), hebben we documentatie ontwikkeld om u te helpen voorbereiden. Deze documentatie beschrijft de stappen die u vandaag kunt nemen om AVG-naleving te ondersteunen wanneer u doelgroepinzichten gebruikt.

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

## <a name="engagement-insights"></a>Betrokkenheidsinzichten

### <a name="deleting-and-exporting-event-data-containing-end-user-identifiable-information"></a>Gebeurtenisgegevens met identificeerbare informatie van de eindgebruiker verwijderen en exporteren

In de volgende secties wordt beschreven hoe u gebeurtenisgegevens verwijdert en exporteert die mogelijk persoonlijke gegevens bevatten.

Gegevens verwijderen of exporteren:

1. Tag gebeurteniseigenschappen die gegevens bevatten met persoonlijke informatie.
2. Verwijder of exporteer gegevens die zijn gekoppeld aan specifieke waarden (bijvoorbeeld: een opgegeven gebruikers-id).

#### <a name="tag-and-update-event-properties"></a>Gebeurteniseigenschappen taggen en bijwerken

Persoonlijke gegevens krijgen een tag op het niveau van een gebeurteniseigenschap. Tag eerst de eigenschappen die u wilt meenemen voor verwijdering of export.

Volg deze stappen om een evenementeigenschap te taggen alsof deze persoonlijke informatie bevat:

1. Open de werkruimte met de gebeurtenis.

1. Ga naar **Gegevens** > **Gebeurtenissen** om de lijst met gebeurtenissen in de geselecteerde werkruimte te zien.
  
1. Selecteer de gebeurtenis die u wilt taggen.

1. Selecteer **Eigenschappen bewerken** om het deelvenster te openen waarop alle eigenschappen van de geselecteerde gebeurtenis worden vermeld.
     
1. Selecteer **...** en kies **Bewerken** om het dialoogvenster **Eigenschap bijwerken** te openen.

   ![Gebeurtenis bewerken.](engagement-insights/media/edit-event.png "Gebeurtenis bewerken")

1. Kies in het venster **Eigenschap bijwerken** het beletselteken **...** in de rechterbovenhoek en kies het vak **Bevat EUII**. Kies **Bijwerken** om uw wijzigingen op te slaan.

   ![Sla uw wijzigingen op.](engagement-insights/media/update-property.png "Uw wijzigingen opslaan")

   > [!NOTE]
   > Elke keer dat het gebeurtenisschema verandert of u een nieuwe gebeurtenis maakt, is het raadzaam de bijbehorende gebeurteniseigenschappen te evalueren en indien nodig te taggen of de tag te verwijderen alsof ze persoonlijke gegevens bevatten.

#### <a name="delete-or-export-tagged-event-data"></a>De gebeurtenisgegevens met tag verwijderen of exporteren

Als alle gebeurteniseigenschappen op de juiste manier van een tag zijn voorzien, zoals beschreven in de vorige stap, kan een omgevingsbeheerder een verwijderingsverzoek indienen voor de gebeurtenisgegevens met tag.

EUII-verwijderings- of exportverzoeken beheren

1. Ga naar **Beheer** > **Omgeving** > **Instellingen**.

1. Selecteer in de sectie **Identificeerbare informatie van de eindgebruiker (EUII) beheren** de optie **EUII beheren**.

##### <a name="deletion"></a>Verwijdering

Voor verwijdering kunt u een lijst met door komma's gescheiden gebruikers-id's invoeren in de sectie **Identificeerbare informatie van de eindgebruiker (EUII) verwijderen**. Deze id's worden vervolgens vergeleken met alle gebeurteniseigenschappen met tag van alle projecten in de huidige omgeving via exacte reeksovereenkomsten. 

Als een eigenschapwaarde overeenkomt met een van de opgegeven id's, wordt de bijbehorende gebeurtenis definitief verwijderd. Vanwege de onomkeerbaarheid van deze actie, moet u de verwijdering bevestigen nadat u **Verwijderen** hebt geselecteerd.

##### <a name="export"></a>Export

Het exportproces is identiek aan het verwijderingsproces als het gaat om het definiëren van gebeurteniseigenschapwaarden in de sectie **Identificeerbare informatie van de eindgebruiker (EUII) exporteren**. Bovendien moet u een **URL voor Azure Blob Storage** opgeven om de exportbestemming op te geven. De Azure Blob-URL moet een [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview) bevatten.

Nadat u **Exporteren** hebt geselecteerd, worden alle gebeurtenissen van het huidige team die overeenkomende eigenschappen met tags bevatten in CSV-indeling naar de exportbestemming geëxporteerd.

### <a name="good-practices"></a>Aanbevolen procedures

* Probeer geen gebeurtenissen te verzenden die persoonlijke gegevens bevatten.
* Als u gebeurtenissen met EUII-gegevens moet verzenden, beperk dan het aantal gebeurtenissen en gebeurteniseigenschappen die EUII-gegevens bevatten. In het ideale geval beperkt u zich tot één zo'n gebeurtenis.
* Zorg ervoor dat zo min mogelijk mensen toegang hebben tot de verzonden persoonsgegevens.
* Voor gebeurtenissen die persoonlijke gegevens bevatten, moet u ervoor zorgen dat u één eigenschap instelt om een unieke identificatiecode uit te zenden die gemakkelijk kan worden gekoppeld aan een specifieke gebruiker (bijvoorbeeld een gebruikers-id). Dit maakt het eenvoudiger om gegevens te scheiden en om de juiste gegevens te exporteren of te verwijderen.
* Tag slechts één eigenschap per gebeurtenis als eigenschap die persoonsgegevens bevat. Het liefst één die alleen een unieke id bevat.
* Tag geen eigenschappen die uitgebreide waarden bevatten (bijvoorbeeld een volledige hoofdtekst van een verzoek). De functionaliteit voor betrokkenheidsinzichten maakt gebruik van exacte reeksovereenkomsten bij de beslissing welke gebeurtenissen moeten worden verwijderd of geëxporteerd.

[!INCLUDE[footer-include](includes/footer-banner.md)]