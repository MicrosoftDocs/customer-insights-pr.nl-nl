---
title: Rechten van betrokkenen (DSR) onder AVG | Microsoft Docs
description: Reageren op verzoeken van betrokkenen om de mogelijkheden van Dynamics 365 Customer Insights doelgroepinzichten.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350263"
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

## <a name="consent-management-preview"></a>Toestemmingsbeheer (preview)

De functie voor toestemmingsbeheer verzamelt niet rechtstreeks gebruikersgegevens. De functie importeert en verwerkt alleen toestemmingsgegevens die door gebruikers in andere toepassingen worden verstrekt.

Als u toestemmingsgegevens over specifieke gebruikers wilt verwijderen, verwijdert u deze uit de gegevensbronnen die zijn opgenomen in de toestemmingsbeheerfunctie. Nadat de gegevensbron is vernieuwd, worden de verwijderde gegevens ook in Toestemmingscentrum verwijderd. Toepassingen die de toestemmingsentiteit gebruiken, verwijderen ook gegevens die op de bron zijn verwijderd na het [vernieuwen](audience-insights/system.md#refresh-processes). We raden u aan om gegevensbronnen snel te vernieuwen na de reactie op een verzoek van een betrokkene om de gegevens van de gebruiker uit alle andere processen en toepassingen te verwijderen.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]