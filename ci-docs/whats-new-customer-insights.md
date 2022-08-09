---
title: Nieuwe functies in Dynamics 365 Customer Insights
description: Informatie over nieuwe functies, verbeteringen en bugfixes.
ms.date: 06/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: f3ae0fe6631ee7c8d79664528be383ec53e93fe8
ms.sourcegitcommit: 92e5a798ca75c7f10aa5025a9bbd2ffb4d4ae7d2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/05/2022
ms.locfileid: "9114240"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Nieuwe functies in Dynamics 365 Customer Insights

We kondigen vol trots onze meest recente updates aan. Dit artikel geeft een overzicht van openbare preview-functies, verbeteringen in de algemene beschikbaarheid en functie-updates. Als u de langetermijnplannen voor functies wilt zien, bekijkt u de [releaseplannen voor Dynamics 365 en Power Platform](/dynamics365/release-plans/).

We implementeren updates per regio. In sommige regio's komen functies dus mogelijk eerder beschikbaar dan in andere. Tenzij anders gespecificeerd, hoeft u geen actie te ondernemen en werken we de app automatisch bij zonder downtime.

> [!TIP]
> Voor het indienen en beoordelen van functieverzoeken en productsuggesties gaat u naar de [Dynamics 365 Application Ideas-portal](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="june-2022-updates"></a>Updates juni 2022

De updates in juni 2022 omvatten nieuwe functies, prestatie-upgrades en bugfixes.

### <a name="updated-user-experience-for-data-sources-and-data-ingestion"></a>Bijgewerkte gebruikerservaring voor gegevensbronnen en gegevensopname

Het importeren van gegevens uit een breed scala van gegevensbronnen vormt de basis voor het consolideren van uw klantgegevens in Dynamics 365 Customer Insights. We hebben de gebruikerservaring voor het importeren en koppelen van gegevensbronnen opnieuw bekeken. Deze update is bedoeld om het voor u gemakkelijker te maken om gegevens in Customer Insights op te nemen.

Zie [Overzicht gegevensbronnen](data-sources.md) voor meer informatie.

### <a name="export-to-inmobi"></a>Exporteren naar InMobi

InMobi helpt merken om consumenten te begrijpen, te identificeren, contact te maken en te werven. U kunt segmenten en andere gegevens exporteren naar de InMobi-service exporteren via Azure Blob Storage-accounts.

Zie [Exporteren naar InMobi (preview)](export-inmobi.md) voor meer informatie.

### <a name="lockbox-support-in-customer-insights"></a>Lockbox-ondersteuning in Customer Insights

Klanten-Lockbox biedt een interface om verzoeken om gegevenstoegang te beoordelen en goed te keuren (of af te wijzen). Deze verzoeken doen zich voor wanneer gegevenstoegang tot klantgegevens nodig is om een ondersteuningscase op te lossen.

Zie [Veilig toegang krijgen tot klantgegevens met Klanten-Lockbox (preview)](security-overview.md#securely-access-customer-data-with-customer-lockbox-preview) voor meer informatie.

### <a name="connect-to-your-data-using-azure-private-link"></a>Verbinding maken met uw gegevens met behulp van Azure Private Link

Met Azure Private Link maakt Customer Insights verbinding met uw Azure Data Lake Storage-account via een privé-eindpunt in uw virtuele netwerk. Voor gegevens in een opslagaccount, dat niet is blootgesteld aan het openbare internet, maakt Private Link de verbinding met dat beperkte netwerk mogelijk.

Zie [Private Link in Customer Insights gebruiken](security-overview.md#private-links-tab) voor meer informatie.

## <a name="may-2022-updates"></a>Updates voor mei 2022

De updates in mei 2022 omvatten nieuwe functies, prestatie-upgrades en bugfixes.

### <a name="updated-data-unification-experience"></a>Bijgewerkte ervaring voor gegevensharmonisatie

 Met gegevensharmonisatie kunt u gegevensbronnen die ooit ongelijksoortig waren, samenbrengen in één hoofdgegevensset die een geharmoniseerde weergave van die gegevens biedt. Gegevens kunnen worden geharmoniseerd in een enkele entiteit of in meerdere entiteiten. Eerst [selecteert u entiteiten en bronvelden](map-entities.md), [verwijdert u dubbele records](remove-duplicates.md), geeft u regels op voor [overeenkomende voorwaarden](match-entities.md) en definieert u welke [velden moeten worden opgenomen in de geharmoniseerde klantprofielen](merge-entities.md).

Ga voor meer informatie naar [Overzicht van gegevensharmonisatie](data-unification.md).

### <a name="refreshed-home-page-in-customer-insights"></a>Vernieuwde startpagina in Customer Insights

De **startpagina** begeleidt u door het configuratieproces voor de belangrijkste functies en biedt een overzicht van segmenten, metingen en verrijkingsgegevens. We hebben de ervaring vernieuwd om in één oogopslag meer relevante informatie te bieden.

Zie [Customer Insights ontdekken](home.md) voor meer informatie.

### <a name="track-usage-of-a-segment"></a>Gebruik van een segment bijhouden

U kunt nu [het gebruik van een segment bijhouden](segments.md#track-usage-of-a-segment) in apps, die zijn gebaseerd op de Dataverse-organisatie die is verbonden met Customer Insights. Voor [Customer Insights-segmenten die worden gebruikt in klantreizen van Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), informeert het systeem u over het gebruik van dat segment.

### <a name="export-to-criteo"></a>Exporteren naar Criteo

Criteo is een online platform dat gebruikers helpt bij het beheren van digitale advertenties. U kunt nu segmenten van geharmoniseerde klantprofielen exporteren om campagnes te genereren, e-mailmarketing te bieden en specifieke klantgroepen te gebruiken met Criteo.

Zie [Segmenten exporteren naar Criteo (preview)](export-criteo.md) voor meer informatie.

### <a name="refined-documentation-structure-for-environment-creation"></a>Verfijnde documentatiestructuur voor het maken van een omgeving

We hebben de Help-documenten met betrekking tot het maken en beheren van omgevingen in Customer Insights opnieuw bekeken. De artikelen zijn nu gegroepeerd onder het knooppunt Omgevingen in de inhoudsopgave. De geherstructureerde artikelen geven meer houvast voor de verschillende manieren om omgevingen in te richten en hebben een duidelijkere structuur. Als u feedback wilt geven, laat het ons dan weten via de knoppen aan het einde van de Help-artikelen.

Zie [Procedure: Een nieuwe omgeving maken](create-environment.md) voor meer informatie.

## <a name="april-2022-updates"></a>Updates van april 2022

De updates in april 2022 omvatten nieuwe functies, prestatie-upgrades en bugfixes.

### <a name="dun--bradstreet-enrichment-preview"></a>Dun & Bradstreet-gegevens verrijken (preview)

Dun & Bradstreet biedt commerciële gegevens, analyses en inzichten voor bedrijven. Het stelt klanten met geharmoniseerde klantprofielen voor bedrijven in staat hun gegevens te verrijken. Verrijkingen omvatten kenmerken, waaronder DUNS-nummer, bedrijfsgrootte, locatie, branche en meer.

Zie [Verrijking van bedrijfsprofielen met Dun & Bradstreet (preview)](enrichment-dnb.md) voor meer informatie.

### <a name="define-the-measure-type-when-creating-a-new-measure"></a>Het type maateenheid definiëren bij het maken van een nieuwe meting

U kunt nu onderscheid maken tussen metingen voor individuele profielen en metingen voor uw hele bedrijf. Terwijl zakelijke metingen worden weergegeven op de startpagina van Customer Insights, worden klantmetingen weergegeven in de gedetailleerde klantweergaven.

Zie [Gebruik de metingenbouwer om helemaal vanaf de grond metingen te maken](measure-builder.md) voor meer informatie.

### <a name="consolidation-of-customer-insights-documentation"></a>Consolidatie van Customer Insights-documentatie

We hebben onze documentatieartikelen opnieuw bekeken en de vermeldingen van betrokkenheidsinzichten en doelgroepinzichten verwijderd. In de toekomst verwijzen we consequent naar de productnaam Customer Insights wanneer we schrijven over de kernfuncties van de toepassing. Deze wijziging leidt ook tot een aanzienlijke herstructurering van de inhoudsopgave, de URL-structuur en de bestandspaden in de opslagplaats van de onderliggende documentatie. Al uw bladwijzers of bestaande koppelingen blijven werken en leiden om naar de bijgewerkte URL's.

Als u ons wilt laten weten hoe u die verandering waarneemt of ziet dat iets niet werkt zoals verwacht, laat het ons dan weten door [feedback in te indienen voor deze pagina](https://github.com/MicrosoftDocs/customer-insights/issues/new?title=&body=%0A%0A%5BEnter%20feedback%20here%5D%0A%0A%0A---%0A%23%23%23%23%20Document%20Details%0A%0A%E2%9A%A0%20*Do%20not%20edit%20this%20section.%20It%20is%20required%20for%20docs.microsoft.com%20%E2%9E%9F%20GitHub%20issue%20linking.*%0A%0A*%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Version%20Independent%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Content%3A%20%5BNew%20and%20upcoming%20features%20-%20Dynamics%20365%20Customer%20Insights%5D(https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fdynamics365%2Fcustomer-insights%2Fwhats-new-customer-insights)%0A*%20Content%20Source%3A%20%5Bci-docs%2Fwhats-new-customer-insights.md%5D(https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fcustomer-insights%2Fblob%2Fmain%2Fci-docs%2Fwhats-new-customer-insights.md)%0A*%20Service%3A%20**customer-insights**%0A*%20Sub-service%3A%20**audience-insights**%0A*%20GitHub%20Login%3A%20%40m-hartmann%0A*%20Microsoft%20Alias%3A%20**mhart**).

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

Zie [Het delen van gegevens met Dataverse inschakelen vanuit uw eigen Azure Data Lake Storage (preview)](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview) voor meer informatie.

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
  
Tijdens de overgangsperiode worden vastgelegde gebeurtenissen nog steeds gestreamd naar het verbonden Data Lake. Zodra deze functionaliteit is uitgeschakeld, stopt het delen van gegevens en worden er geen nieuwe gebeurtenissen naar de verbonden opslag verzonden.
Neem rechtstreeks contact op met uw Microsoft-accountteam als u vragen hebt over de beëindiging van de preview van de mogelijkheden. Uw accountteam houdt u op de hoogte van komende lanceringen. 

## <a name="january-2022-updates"></a>Updates januari 2022

De updates in januari 2022 omvatten nieuwe functies, prestatie-upgrades en bugfixes.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Gevoelsanalyse van de feedback van uw klant

Customer Insights biedt een nieuwe door AI aangedreven functie om het klantgevoel te synthetiseren en specifieke zakelijke aspecten te identificeren als kansen voor gerichte verbeteringen. Door de schriftelijke feedback van uw klanten te analyseren, kunt u tegen lage kosten nauwkeurige inzichten verwerven. Sentimentanalyse op basis van NLP-modellen (Natural Language Processing) die twee afgeleide inzichten genereren voor elke klant-id. Een gevoelsscore (van –5 tot 5) en een lijst van toepasselijke zakelijke aspecten. 

Zie [Gevoel in klantfeedback analyseren (preview)](sentiment-analysis.md) voor meer informatie.


[!INCLUDE [footer-include](includes/footer-banner.md)]