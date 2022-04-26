---
title: Nieuwe en komende functies
description: Informatie over nieuwe functies, verbeteringen en bugfixes.
ms.date: 04/05/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 2f081306271a170cf3e250fc1a193cedb70aeec6
ms.sourcegitcommit: 0363559a1af7ae16da2a96b09d6a4a8a53a8cbb8
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/05/2022
ms.locfileid: "8547666"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Wat is er nieuw in de doelgroepinzichten-mogelijkheid van Dynamics 365 Customer Insights

We kondigen vol trots onze meest recente updates aan. Dit artikel geeft een overzicht van openbare preview-functies, verbeteringen in de algemene beschikbaarheid en functie-updates. Als u de langetermijnplannen voor functies wilt zien, bekijkt u de [releaseplannen voor Dynamics 365 en Power Platform](/dynamics365/release-plans/).

We implementeren updates per regio. In sommige regio's komen functies dus mogelijk eerder beschikbaar dan in andere. Tenzij anders gespecificeerd, hoeft u geen actie te ondernemen en updaten we de app automatisch zonder downtime.

> [!TIP]
> Voor het indienen en beoordelen van functieverzoeken en productsuggesties gaat u naar de [Dynamics 365 Application Ideas-portal](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


## <a name="march-2022-updates"></a>Updates van maart 2022

De updates in maart 2022 omvatten nieuwe functies, prestatie-upgrades en bugfixes.

### <a name="liveramp-abilitec-enrichment-preview"></a>LiveRamp AbiliTec-verrijking (preview)

LiveRamp biedt identiteitsresolutie en consolidatie van klantgegevens. U kunt persoonlijke identificatiegegevens in uw klantgegevens toewijzen aan de AbiliTec-identiteitsgrafiek en AbiliTec-id's ontvangen. U kunt deze id's vervolgens gebruiken voor een betere harmonisatie van uw klantgegevens.

Zie [Klantprofielen verrijken met identiteitsgegevens van LiveRamp (preview)](enrichment-liveramp.md) voor meer informatie.

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Segmenten en meetcriteria ordenen met tags en filters
Als uw organisatie veel segmenten of meetcriteria bijhoudt, kan het soms een uitdaging zijn om de juiste te vinden. Met deze nieuwe functie kunt u lijsten ordenen met behulp van tags en kolommen. Het helpt om snel en gemakkelijk gegevens te vinden en de weergaven aan te passen.

Zie [Werken met tags en kolommen](work-with-tags-columns.md) voor meer informatie.

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Gegevens delen met Dataverse inschakelen bij gebruik van uw eigen opslagaccount

Als uw omgeving wordt Azure Data Lake Storage gebruikt voor het opslaan van Customer Insights-gegevens, is er wat extra configuratie nodig om het delen van gegevens met Microsoft Dataverse mogelijk te maken.
Eerder kon u het delen van gegevens met Dataverse alleen inschakelen wanneer uw gegevens waren opgeslagen in ons beheerde data lake. 

Zie [Het delen van gegevens met Dataverse inschakelen vanuit uw eigen Azure Data Lake Storage (preview)](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview) voor meer informatie.

### <a name="new-export-destinations-iterable-and-braze"></a>Nieuwe exportbestemmingen: Iterable en Braze

We blijven ons ecosysteem van exportbestemmingen uitbreiden met nieuwe verbindingen. U kunt nu segmenten exporteren naar Iterable en Braze om hun activeringsservices te gebruiken.

Zie [Segmenten exporteren naar Iterable (preview)](export-iterable.md) en [Segmenten exporteren naar Braze (preview)](export-braze.md) voor meer informatie.

### <a name="improvements-to-marketo-and-google-ads-export"></a>Verbeteringen aan Marketo- en Google Ads-export

Veranderende API's in verbonden services leiden tot updates voor connectors zodat deze betrouwbaar en soepel blijven werken. We hebben enkele updates uitgebracht voor de exports naar Marketo en Google Ads-services:

- Google Ads: de nieuwe versie van de Google Ads-exportconnector vereenvoudigt de verificatie-ervaring en stelt u nu in staat automatisch nieuwe Google Ads-doelgroepen te maken. 
- Marketo: de nieuwe versie van de Marketo-exportconnector biedt ondersteuning voor de Marketo-id, zodat u dubbele gegevens kunt voorkomen, bestaande records kunt bijwerken en nieuwe records kunt maken in Marketo. 


## <a name="february-2022-updates"></a>Updates van februari 2022

De updates in februari 2022 omvatten nieuwe functies, prestatie-upgrades en bugfixes.

### <a name="general-availability-for-prediction-models"></a>Algemene beschikbaarheid voor voorspellingsmodellen

Kant-en-klare voorspellingsmodellen, inclusief **abonnementsverloop**, **transactieverloop** en **levensduurwaarde van klant (CLV)** komen algemeen beschikbaar als onderdeel van Customer Insights. 

Zie [Overzicht van voorspellingen](predictions-overview.md) voor meer informatie.

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Nieuw gegevensbron: Integratie met Azure Synapse Analytics (preview)

Azure Synapse Analytics is een enterprise analytics-service die sneller inzichten verkrijgt in datawarehouses en big data-systemen.

Organisaties die al gebruikmaken van Azure Synapse Analytics kunnen die gegevens opnemen in Customer Insights. 

Zie [Verbinding maken met een Azure Synapse-gegevensbron (preview)](connect-synapse.md) voor meer informatie.

### <a name="liveramp-enrichment-preview"></a>LiveRamp-verrijking (preview)

LiveRamp biedt identiteitsresolutie en consolidatie van klantgegevens. U kunt persoonlijke identificatiegegevens in uw klantgegevens toewijzen aan de AbiliTec-identiteitsgrafiek en AbiliTec-id's ontvangen. U kunt deze id's vervolgens gebruiken voor een betere harmonisatie van uw klantgegevens.

Zie [Klantprofielen verrijken met identiteitsgegevens van LiveRamp (preview)](enrichment-liveramp.md) voor meer informatie.

### <a name="enrichment-for-data-sources-preview"></a>Verrijking voor gegevensbronnen (preview)

Gebruik gegevens uit bronnen zoals Microsoft en andere partners om uw klantgegevens te verrijken voordat gegevens worden geharmoniseerd. Gegevensbronverrijkingen zorgen ervoor dat gegevens vollediger zijn en een hogere kwaliteit hebben waardoor betere resultaten kunnen worden behaald nadat u uw gegevens hebt geharmoniseerd.

Zie [Verrijking voor gegevensbronnen (preview)](data-sources-enrichment.md) voor meer informatie.

### <a name="change-owner-of-environment"></a>Eigenaar van omgeving wijzigen

Hoewel meerdere gebruikers beheerdersmachtigingen kunnen hebben in Customer Insights, is slechts één gebruiker de eigenaar van een omgeving. Dankzij een verbeterde ervaring kunt u de eigenaren van een omgeving wijzigen en het eigendom claimen als een voormalige eigenaar de organisatie heeft verlaten. 

Zie [De eigenaar van een omgeving wijzigen](manage-environments.md#change-the-owner-of-an-environment) voor meer informatie.

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>Gegevensvoorbereidingsproces geeft een beschadigingsreden voor beschadigde records

Gegevensvoorbereiding toont nu de reden voor beschadiging voor alle velden met beschadigde gegevens. De informatie wordt verstrekt op individueel recordniveau voor gemakkelijke identificatie. 

Zie [Beschadigde gegevensbronnen](entities.md#corrupted-data-sources) voor meer informatie.

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Einde van preview voor rapportagefuncties in de mogelijkheid voor betrokkenheidsinzichten

De Dynamics 365 Customer Insights preview van de mogelijkheden voor betrokkenheidsinzichten is op 15 februari 2022 beëindigd.  
Deze wijziging betekent dat de proefervaring van Customer Insights niet langer de mogelijkheid biedt om trechters of andere rapportagefunctionaliteit te maken.

We nodigen u uit om de vele andere functies van [Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/), het Microsoft-klantgegevensplatform (CDP) te verkennen en te evalueren.    
 
Gedurende een overgangsperiode hebben bestaande preview-deelnemers nog steeds toegang tot enkele preview-mogelijkheden en -functionaliteit:

- Ontvang code om een website of mobiele app in te stellen 
- Bekijk gebeurtenissen en gebeurteniseigenschappen 
- Verbeter geharmoniseerde profielen met opgenomen en verfijnde gebeurtenissen om te profiteren van de volledige waarde van hun klantgegevens
  
Tijdens de overgangsperiode worden vastgelegde gebeurtenissen nog steeds gestreamd naar het verbonden Data Lake. Zodra deze functionaliteit is uitgeschakeld, stopt het delen van gegevens tussen engagement-inzichten en doelgroep-inzichten en worden er geen nieuwe gebeurtenissen naar de verbonden opslag verzonden.
Neem rechtstreeks contact op met uw Microsoft-accountteam als u vragen hebt over de beëindiging van de preview van de mogelijkheden. Uw accountteam houdt u op de hoogte van komende lanceringen. 

## <a name="january-2022-updates"></a>Updates januari 2022

De updates in januari 2022 omvatten nieuwe functies, prestatie-upgrades en bugfixes.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Gevoelsanalyse van de feedback van uw klant

Customer Insights biedt een nieuwe door AI aangedreven functie om het klantgevoel te synthetiseren en specifieke zakelijke aspecten te identificeren als kansen voor gerichte verbeteringen. Door de schriftelijke feedback van uw klanten te analyseren, kunt u tegen lage kosten nauwkeurige inzichten verwerven. Sentimentanalyse op basis van NLP-modellen (Natural Language Processing) die twee afgeleide inzichten genereren voor elke klant-id. Een gevoelsscore (van –5 tot 5) en een lijst van toepasselijke zakelijke aspecten. 

Zie [Gevoel in klantfeedback analyseren (preview)](sentiment-analysis.md) voor meer informatie.


[!INCLUDE[footer-include](../includes/footer-banner.md)]