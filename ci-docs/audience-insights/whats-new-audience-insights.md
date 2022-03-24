---
title: Nieuwe en komende functies
description: Informatie over nieuwe functies, verbeteringen en bugfixes.
ms.date: 03/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 9195770255bd798636b9532d6e1ca928345b3708
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376456"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Wat is er nieuw in de doelgroepinzichten-mogelijkheid van Dynamics 365 Customer Insights

We kondigen vol trots onze meest recente updates aan. Dit artikel geeft een overzicht van openbare preview-functies, verbeteringen in de algemene beschikbaarheid en functie-updates. Als u de langetermijnplannen voor functies wilt zien, bekijkt u de [releaseplannen voor Dynamics 365 en Power Platform](/dynamics365/release-plans/).

We implementeren updates per regio. In sommige regio's komen functies dus mogelijk eerder beschikbaar dan in andere. Tenzij anders gespecificeerd, hoeft u geen actie te ondernemen en updaten we de app automatisch zonder downtime.

> [!TIP]
> Voor het indienen en beoordelen van functieverzoeken en productsuggesties gaat u naar de [Dynamics 365 Application Ideas-portal](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


## <a name="february-2022-updates"></a>Updates van februari 2022

De updates in februari 2022 omvatten nieuwe functies, prestatie-upgrades en bugfixes.

### <a name="general-availability-for-prediction-models"></a>Algemene beschikbaarheid voor voorspellingsmodellen

Kant-en-klare voorspellingsmodellen, inclusief **abonnementsverloop**, **transactieverloop** en **levensduurwaarde van klant (CLV)** komen algemeen beschikbaar als onderdeel van Customer Insights. 

Zie [Overzicht van voorspellingen](predictions-overview.md) voor meer informatie.

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Nieuw gegevensbron: Integratie met Azure Synapse Analytics (preview)

Azure Synapse Analytics is een enterprise analytics-service die sneller inzichten verkrijgt in datawarehouses en big data-systemen.

Als uw organisatie al gebruikmaakt van geavanceerde analysemogelijkheden van Azure Synapse Analytics en de uitvoer opslaat in de Data Lake-databases, kunt u die gegevens eenvoudig opnemen in Customer Insights. Zie [Verbinding maken met een Azure Synapse-gegevensbron (preview)](connect-synapse.md) voor meer informatie.

### <a name="liveramp-enrichment-preview"></a>LiveRamp-verrijking (preview)

LiveRamp biedt deterministische offline identiteitsresolutie en consolidatie van klantgegevens. U kunt persoonlijke identificatiegegevens in uw klantgegevens toewijzen aan de AbiliTec-identiteitsgrafiek en AbiliTec-id's ontvangen. U kunt deze id's vervolgens gebruiken voor een betere harmonisatie van uw klantgegevens.

Zie [Klantprofielen verrijken met identiteitsgegevens van LiveRamp (preview)](enrichment-liveramp.md) voor meer informatie.

### <a name="enrichment-for-data-sources-preview"></a>Verrijking voor gegevensbronnen (preview)

Gebruik gegevens uit bronnen zoals Microsoft en andere partners om uw klantgegevens te verrijken voordat gegevens worden geharmoniseerd. Gegevensbronverrijkingen zorgen ervoor dat gegevens vollediger zijn en een hogere kwaliteit hebben waardoor betere resultaten kunnen worden behaald nadat u uw gegevens hebt geharmoniseerd.

Zie [Verrijking voor gegevensbronnen (preview)](data-sources-enrichment.md) voor meer informatie.

### <a name="change-owner-of-environment"></a>Eigenaar van omgeving wijzigen

Hoewel meerdere gebruikers beheerdersmachtigingen kunnen hebben in Customer Insights, is slechts één gebruiker de eigenaar van een omgeving. Dankzij een verbeterde ervaring kunt u de eigenaren van een omgeving wijzigen en het eigendom claimen als een voormalige eigenaar de organisatie heeft verlaten. 

Zie [De eigenaar van een omgeving wijzigen](manage-environments.md#change-the-owner-of-an-environment) voor meer informatie.

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>Gegevensvoorbereidingsproces geeft een beschadigingsreden voor beschadigde records

Het gegevensvoorbereidingsproces toont nu de reden voor beschadiging voor alle velden met beschadigde gegevens op individueel recordniveau voor gemakkelijke identificatie. 

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


## <a name="december-2021-updates"></a>Updates van december 2021

De updates in december 2021 omvatten nieuwe functies, prestatie-upgrades en bugfixes.

### <a name="forward-customer-insights-logs-to-azure-monitor"></a>Customer Insights-logboeken doorsturen naar Azure Monitor

Customer Insights biedt een directe integratie met Azure Monitor. Deze functie omvat controlegebeurtenissen en operationele gebeurtenissen. Met Azure Monitor-resourcelogboeken kunt u logboeken bewaken en naar Azure Storage, Azure Log Analytics verzenden of deze naar Azure Event Hubs streamen.

Zie [Doorsturen van logboeken in Dynamics 365 Customer Insights met Azure Monitor (preview)](diagnostics.md) voor meer informatie.

### <a name="enrich-customer-profiles-with-engagement-data"></a>Klantprofielen verrijken met betrokkenheidsgegevens

Gebruik gegevens van Microsoft Office 365 om uw klantaccountprofielen te verrijken met inzichten over contacten via Office 365-apps. De betrokkenheidsgegevens bestaan uit e-mail- en vergaderactiviteiten, die op accountniveau worden samengevoegd. Bijvoorbeeld het aantal e-mails van een zakelijk account of het aantal vergaderingen met het account. Er worden geen gegevens over individuele gebruikers gedeeld. Deze verrijking is alleen beschikbaar in de volgende regio's: VK, Europa, Noord-Amerika.

Zie [Klantprofielen verrijken met betrokkenheidsgegevens (preview)](enrichment-office.md) voor meer informatie.

### <a name="advanced-data-unification-features"></a>Geavanceerde functies voor gegevensharmonisatie

#### <a name="enable-conflict-resolution-policies-at-the-individual-attribute-level"></a>Beleid voor conflictoplossing inschakelen op individueel kenmerkniveau

Bij het ontdubbelen van klantenrecords binnen een entiteit, wilt u mogelijk geen volledige record als winnaar kiezen. We bieden u nu de mogelijkheid om de beste velden uit verschillende records samen te voegen op basis van regels voor elk kenmerk. U kunt er bijvoorbeeld voor kiezen om de meest recente e-mail EN het meest volledige adres uit verschillende records te bewaren. 

U kunt nu afzonderlijke samenvoegregels voor afzonderlijke kenmerken definiëren, terwijl u records binnen één entiteit ontdubbelt en samenvoegt. Voorheen kon u slechts één enkele samenvoegregel selecteren (records bijhouden op basis van volledigheid van recentheidsgegevens) en die regel werd op recordniveau toegepast op alle kenmerken. Dat is niet ideaal als sommige gegevens die u wilt bewaren in record A staan en andere goede gegevens in record B.

Zie [Ontdubbeling op een match-entiteit definiëren](match-entities.md#define-deduplication-on-a-match-entity) voor meer informatie.

#### <a name="custom-rules-for-matching"></a>Aangepaste regels voor overeenkomsten

Er zijn momenten waarop u een uitzondering op algemene regels moet specificeren om records NIET te matchen. Dit kan gebeuren wanneer meerdere personen voldoende informatie delen, waardoor het systeem hen als één persoon zou zien. Bijvoorbeeld een tweeling met dezelfde achternaam, die in dezelfde stad woont en dezelfde geboortedatum heeft.

Uitzonderingen zorgen ervoor dat onjuiste gegevensharmonisatie kan worden aangepakt in de harmonisatieregels. U kunt meerdere uitzonderingen aan een regel toevoegen.

Zie [Uitzonderingen toevoegen aan een regel](match-entities.md#add-exceptions-to-a-rule) voor meer informatie.

#### <a name="provide-additional-conflict-resolution-policies-and-enable-grouping-of-attributes"></a>Aanvullend beleid voor conflictoplossing bieden en het groeperen van kenmerken inschakelen

Met deze functie kunt u een groep velden als een enkele eenheid behandelen. Bijvoorbeeld wanneer onze records de velden Address1, Address2, City, State en Zip bevatten. Mogelijk willen we het veld Address2 in een andere record niet samenvoegen, vanuit de gedachte dat dit onze gegevens completer zou maken.

Nu kunt u een groep gerelateerde velden combineren en één beleid voor samenvoegen toepassen op de groep. 

Zie [Een groep velden combineren](merge-entities.md#combine-a-group-of-fields) voor meer informatie.


## <a name="november-2021-updates"></a>Updates van november 2021

De updates in november 2021 omvatten nieuwe functies, prestatie-upgrades en bugfixes.

### <a name="segment-membership-now-available-in-dataverse"></a>Segmentlidmaatschap nu beschikbaar in Dataverse

Informatie over segmentlidmaatschap voor klantprofielen is nu beschikbaar in Dataverse samen met de klantprofielen en inzichten. Dynamics 365-actieapps en modelgestuurde apps kunnen deze gegevens gebruiken om details van het segmentlidmaatschap voor een bepaalde klant op te zoeken.

### <a name="activities-support-contact-level-details-for-business-accounts"></a>Activiteiten ondersteunen contactgegevens op contactpersoonniveau voor zakelijke accounts

U kunt nu activiteiten voor contactpersonen configureren, weergeven en filteren op de tijdlijnen van uw zakelijke accountactiviteiten om beter te begrijpen welke accountcontactpersonen hebben deelgenomen aan specifieke activiteiten.

## <a name="october-2021-updates"></a>Updates van oktober 2021

De updates in oktober 2021 omvatten nieuwe functies, prestatie-upgrades en bugfixes.

### <a name="b-to-b"></a>B2B

Vanaf oktober 2021 kunt u in Customer Insights werken met zakelijke accounts en hun gerelateerde contacten. Voorheen was de app vooral gericht op individuele consumenten. Verschillende functiegebieden zijn bijgewerkt om B2B-scenario's te ondersteunen naast een nieuw omgevingstype. Zie voor een overzicht van ondersteunde B2B-functies het onderwerp [Werken met zakelijke accounts in doelgroepinzichten](work-with-business-accounts.md).

In de volgende secties worden enkele van de belangrijkste gebieden belicht die zijn aangepast om zakelijke accounts en individuele consumenten te ondersteunen.

#### <a name="export-segments-based-on-business-accounts"></a>Segmenten exporteren op basis van zakelijke accounts

Alle segmentexports in doelgroepinzichten zijn beschikbaar in de context van zakelijke accounts. Voor de meeste segmentexports is extra configuratie vereist en moeten [contactgegevens worden geprojecteerd](segment-builder.md#create-a-new-segment) in de onderliggende segmenten om geldig te zijn voor zakelijke accounts. Zie [Segmenten exporteren](export-destinations.md#export-segments) voor meer informatie.

#### <a name="use-the-linkedin-ads-export-with-business-accounts"></a>De LinkedIn Ads-export gebruiken met zakelijke accounts

De LinkedIn Ads-export is nu beschikbaar voor contact- en bedrijfstargeting in de context van zakelijke accounts. Wanneer u bedrijfstargeting selecteert als uw primaire focus van de LinkedIn-export, kunt u segmenten exporteren die zijn gebaseerd op zakelijke accounts zonder dat u contactgegevens hoeft te projecteren. Zie voor meer informatie de documenten over [LinkedIn-advertenties exporteren](export-linkedin-ads.md) en het verschil tussen [contacttargeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) en [bedrijfstargeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting). 

#### <a name="create-measures-based-on-business-accounts-and-their-hierarchy"></a>Meetcriteria maken op basis van zakelijke accounts en hun hiërarchie

Met de opbouwfunctie voor meetcriteria kunt u meetcriteria met betrekking tot zakelijke accounts maken en desgewenst de hiërarchie-informatie gebruiken. Hiërarchie-informatie wordt gebruikt om een berekening van meetcriteria samen te tellen voor een account en alle gerelateerde subaccounts. U kunt bijvoorbeeld meetcriteria maken, zoals de totale omzet voor elke groep zakelijke accounts die wordt geïdentificeerd door hun hiërarchie. Zie [Metingen definiëren en beheren](measures.md) voor meer informatie.

#### <a name="create-segments-based-on-business-accounts-and-their-hierarchy"></a>Segmenten maken op basis van zakelijke accounts en hun hiërarchie

Met de opbouwfunctie voor segmenten kunt u segmenten van zakelijke accounts maken die optioneel contactgegevens bevatten voor elke account in een segment. Als u een accounthiërarchie hebt ingesteld, kunt u informatie over de accounthiërarchie gebruiken bij het maken van segmenten. Zie [Een nieuw segment maken](segment-builder.md#create-a-new-segment) voor meer informatie.

#### <a name="retain-your-business-accounts-with-deep-insights-to-their-churn-tendency"></a>Uw zakelijke accounts met diepe inzichten in hun verlooptendens behouden

Het voorspellingsmodel voor klantverloop ondersteunt nu ook zakelijke accounts. U kunt het risico op klantverloop evalueren, niet alleen voor een account, maar ook voor een combinatie van een account en een product- of servicecategorie die ze van u kopen. Deze toevoeging helpt u te begrijpen of het waarschijnlijker is dat een account in het algemeen of alleen voor een bepaalde categorie goederen of diensten niet meer bij u koopt. Om u verder te helpen bij het gebruik van dit AI-model, worden ook redenen vermeld waarom een account waarschijnlijk verloopt. Zie voor meer informatie [Voorspelling van transactieverloop (preview)](predict-transactional-churn.md).

#### <a name="see-contacts-of-a-business-account-in-customer-view"></a>Contactpersonen van een zakelijke account bekijken in Klantweergave

Als zakelijke accounts worden toegewezen aan gerelateerde accounts, worden deze gerelateerde contactpersonen als onderdeel van de weergave met klantgegevens weergegeven in de Customer Insights-app. Zie [Klantprofielen](customer-profiles.md) voor meer informatie.


## <a name="september-2021-updates"></a>Updates van september 2021

De updates in september 2021 omvatten nieuwe functies, prestatie-upgrades en bugfixes.

### <a name="activities"></a>Activiteiten

- **Verbeteringen in de tijdlijn van activiteiten** We hebben de filters voor de activiteitentijdlijn op klantprofielen uitgebreid. Bovendien kunt u het nieuwe filterdeelvenster gebruiken om te filteren op activiteitstype en op datum. Datums kunnen worden gefilterd met verschillende voorwaarden. Voor meer informatie, zie [Activiteitentijdlijnen op klantprofielen bekijken](activities.md#view-activity-timelines-on-customer-profiles).

### <a name="relationships"></a>Relaties

- **Ondersteuning voor relaties met meerdere hops** Gebruik relaties met meerdere hops bij het configureren van activiteiten en het definiëren van relaties tussen entiteiten. Relaties met meerdere hops gebruiken een tussenliggende entiteit om twee entiteiten te verbinden. Bij het configureren van een activiteit kunt u een relatie met meerdere hops gebruiken om uw activiteitenentiteit te verbinden met een tussenliggende entiteit en vervolgens met een klantentiteit. U kunt relaties met meerdere hops combineren met relaties met meerdere paden. Zie voor meer informatie [Relaties met meerdere hops](relationships.md#multi-hop-relationship).

- **Ondersteuning voor relaties met meerdere paden** Gebruik relaties met meerdere paden bij het configureren van activiteiten en het definiëren van relaties tussen entiteiten. Relaties met meerdere paden relateren een bronentiteit aan meer dan één entiteit. Bij het configureren van een activiteit kunt u een relatie met meerdere paden gebruiken om uw activiteitenentiteit te verbinden met meer dan een klantentiteit. U kunt relaties met meerdere paden combineren met relaties met meerdere hops. Zie voor meer informatie [Relaties met meerdere paden](relationships.md#multi-path-relationship).

## <a name="august-2021-updates"></a>Updates augustus 2021

De updates in juli en augustus 2021 bevatten een nieuwe functie, prestatie-upgrades en oplossingen van fouten.

### <a name="extensibility"></a>Uitbreidbaarheid

- **Segmenten exporteren naar Klaviyo** We hebben onze [exportbestemmingen uitgebreid met Klaviyo](export-klaviyo.md). U kunt nu segmenten exporteren om campagnes te maken, e-mailmarketing uit te voeren en te werken met specifieke groepen klanten met Klaviyo. 


## <a name="june-2021-updates"></a>Updates juni 2021

De updates van juni 2021 omvatten verschillende functies, prestatie-upgrades en bugfixes.

### <a name="data-ingestion"></a>Gegevensopname

- **Verbeterde voortgangsupdates voor gegevensharmonisatie** U kunt nu gedetailleerdere, verbeterde dynamische statusupdates bekijken in de stappen voor het [gegevensharmonisatieproces](data-unification.md). Met deze functie kunt u de gedetailleerde voortgang bijhouden om de processtroom te begrijpen en actie te ondernemen als een stap aandacht behoeft.

### <a name="extensibility"></a>Uitbreidbaarheid

- **Segmenten en andere gegevens exporteren naar Salesforce Marketing Cloud** We hebben onze exportbestemmingen uitgebreid met [Salesforce Marketing Cloud](export-salesforce.md). U kunt nu segmenten en andere typen gegevens exporteren naar Salesforce Marketing Cloud via een branded SFTP-export. Gegevensimport kan volledig worden geautomatiseerd in Salesforce en worden gebruikt om effectievere marketingcampagnes te ontwikkelen.  
 
- **Segmenten exporteren naar ActiveCampaign** We hebben onze exportbestemmingen uitgebreid met [Active Campaign](export-active-campaign.md). U kunt nu segmenten exporteren om campagnes te genereren, e-mailmarketing uit te voeren en te werken met specifieke groepen klanten in ActiveCampaign.
 
- **Segmenten exporteren naar Sendinblue** We hebben onze exportbestemmingen uitgebreid met [Sendinblue](export-sendinblue.md). U kunt nu segmenten exporteren om campagnes te genereren, e-mailmarketing uit te voeren en te werken met specifieke groepen klanten met Sendinblue.
 
### <a name="ux-updates"></a>UX-updates 

- **Nieuwe en verbeterde klantenpagina en pagina met profieldetails** We hebben de pagina Klanten en de profieldetailpagina's opnieuw ontworpen voor een verbeterde gebruikerservaring en betere prestaties. Met deze wijzigingen kunt u klanten bekijken, sorteren, zoeken en filteren. Filters worden nu weergegeven in de URL om de zoekresultaten naadloos met andere gebruikers te delen. Zoekresultaten kunnen ook als segment worden opgeslagen.    
  De detailpagina voor klantprofielen groepeert nu gegevens in verschillende subsecties, zoals demografische gegevens, id's en andere profielkenmerken voor een betere leesbaarheid. Andere secties op de pagina met profieldetails zijn nu interactiever. In het activiteitengedeelte kunt u nu bijvoorbeeld filteren en sorteren.


## <a name="may-2021-updates"></a>Updates voor mei 2021

De updates in mei 2021 bevatten verschillende functies, prestatie-upgrades en bugfixes.

### <a name="data-ingestion"></a>Gegevensopname

- **Bekijk of wijzig metagegevens of entiteitsdefinitie bij het bijvoegen van gegevens vanuit uw Azure Data Lake Storage** U kunt nu metagegevens of entiteitsdefinities bekijken en bewerken in doelgroepinzichten wanneer u gegevens vanuit een Common Data Model-map opneemt in uw Azure Data Lake Storage. Deze mogelijkheid biedt realtime feedback, modelvalidatie en foutcontrole. Hiermee kunt u zowel model.json als manifest.json naadloos bewerken.

### <a name="extensibility"></a>Uitbreidbaarheid

- **Verbeterde segmentexport, aangepast schema en duplicering** U kunt nu [alle exports voor een specifiek segment bekijken](export-destinations.md#view-exports-and-export-details) in een lijst. Deze nieuwe weergave helpt om te beheren hoe een specifiek segment wordt gebruikt en om bestaande exports aan te passen of nieuwe te maken.    
  U kunt [aangepaste vernieuwingsschema'ss](export-destinations.md#schedule-and-run-exports) definiëren voor afzonderlijke exports of meerdere exports tegelijk. Tot nu toe werden alle exports uitgevoerd bij elke systeemvernieuwing.    
  In plaats van helemaal opnieuw een nieuwe export te maken, kunt u beginnen op basis van een bestaande export om wat tijd te besparen.

- **Segmenten exporteren naar Microsoft Advertising** We hebben onze exportbestemmingen uitgebreid met Microsoft Advertising. Maak doelgroepen met overeenkomende klanten in Microsoft Advertising met uw geharmoniseerde klantprofielgegevens en gebruik deze doelgroepen voor uw advertentiecampagnes. Zie [Segmenten exporteren naar Microsoft Advertising](export-microsoft-advertising.md) voor meer informatie.

- **Segmenten exporteren naar LinkedIn Ads** We hebben onze exportbestemmingen uitgebreid met LinkedIn Ads en stellen u in staat om targeting van contactpersonen en targeting van bedrijven via LinkedIn te ontgrendelen door uw geharmoniseerde klantprofielgegevens te exporteren. Zie [Segmenten exporteren naar LinkedIn Ads](export-linkedin-ads.md) voor meer informatie.


- **Segmenten exporteren naar Omnisend** We hebben onze exportbestemmingen uitgebreid met Omnisend. Gebruik de segmenten die zijn gemaakt in doelgroepinzichten om campagnes te genereren, e-mailmarketing te bieden en specifieke groepen met klanten te gebruiken met Omnisend. Zie [Segmenten exporteren naar Omnisend](export-omnisend.md) voor meer informatie

### <a name="predictions"></a>Voorspellingen

- **Rapport over bruikbaarheid van invoergegevens** Het bruikbaarheidsrapport voor invoergegevens biedt een geconsolideerd overzicht van de fouten en waarschuwingen die uw kant-en-klare voorspellingen mogelijk genereren. Het geeft ook aanbevelingen om de prestaties van het model te verbeteren.    
  Het rapport is beschikbaar nadat een model zijn trainingsproces heeft voltooid. Het wordt voor elk model afzonderlijk gemaakt, ongeacht of dit met succes is voltooid of niet.
  Momenteel is deze functie alleen beschikbaar voor het model voor transactieverloop. Zie [Bruikbaarheidsrapport voor gegevensinvoer](manage-predictions.md#input-data-usability-report) voor meer informatie.

### <a name="relationships"></a>Relaties

- **Relatievisualizer** Met de weergave van de relatievisualisatie kunt u alle bestaande relaties tussen entiteiten en hun kardinaliteit bekijken. Relaties zijn nu georganiseerd in groepen: door gebruiker gemaakte relaties, systeemrelaties en overgenomen relaties. U kunt een weergave ook als afbeelding exporteren. Zie [Relatie weergeven](relationships.md#view-relationships) voor meer informatie. 

## <a name="april-2021-updates"></a>Updates van april 2021

De updates in april 2021 bevatten verschillende functies, prestatie-upgrades en bugfixes.

### <a name="data-unification"></a>Gegevensharmonisatie
 
- **Verbeterde samenvoegervaring voor gegevensharmonisatie**    
  
   We hebben nu een verbeterde gebruikerservaring bij de samenvoegconfiguratie van het gegevensharmonisatieproces. De wijzigingen omvatten een intuïtieve volgorde van de samengevoegde velden en gedetailleerde statistieken over gecombineerde en singleton-velden.

- **Volgorde van entiteiten wijzigen en alle bronrecords in de entiteit Klant configureren**  
      
   U kunt nu de volgorde van entiteiten wijzigen en entiteiten verwijderen uit een bestaand samenvoegingsplan in het gegevensharmonisatieproces. Het biedt flexibiliteit om de entiteiten in het matchproces opnieuw te ordenen op basis van zakelijke behoeften. Bovendien maken we het mogelijk om alle niet-overeenkomende records in de definitieve entiteit *Klant* op te nemen, waarmee de gegevenssetdefinitie van klantprofielen kan worden gedefinieerd.

### <a name="enrichments"></a>Verrijkingen

 - **Nieuwe verrijking: uitgebreide adressen**    
  
   We zijn verheugd over de introductie van een nieuwe verrijking waarmee adressen in uw klantgegevens worden uitgebreid. Adressen in uw gegevens kunnen ongestructureerd, onvolledig of onjuist zijn. Voor deze functie worden modellen van Microsoft gebruikt om uw adressen te normaliseren en te verrijken met de Common Data Model-indeling voor betere nauwkeurigheid en inzichten.
 
   Zie voor meer informatie [Verrijking van klantprofielen met uitgebreide adressen](enrichment-enhanced-addresses.md).

- **Begeleide configuratie-ervaring voor verrijkingen**    
  
   We hebben de configuratie-ervaring voor verrijkingen opnieuw bekeken met een eenvoudige, begeleide ervaring. U hebt nu een duidelijk stapsgewijs proces voor het maken en bewerken van verrijkingen.
 
   Bovendien hebben we de configuratie van verbindingen voor verrijkingen van derden gescheiden, zodat dezelfde verbinding door meerdere verrijkingen kan worden gebruikt. Alleen beheerders kunnen nieuwe verbindingen configureren, maar de gemaakte verbindingen zijn altijd beschikbaar voor zowel beheerders als inzenders.    

   Zie [Overzicht van verbindingen](connections.md) voor meer informatie.

- **Meerdere verrijkingen van hetzelfde type**    
  
   We staan gebruikers nu toe om meerdere verrijkingen van hetzelfde verrijkingstype te maken en te beheren. U kunt nu bijvoorbeeld twee afzonderlijke adresverrijkingen maken om twee verschillende klantsegmenten te verrijken. Er zijn limieten van toepassing op het aantal verrijkingen van hetzelfde type dat kan worden gemaakt, en de limieten variëren afhankelijk van het verrijkingstype.
  
   Zie [Verrijking voor klantprofielen](enrichment-hub.md) voor meer informatie.

## <a name="march-2021-updates"></a>Updates van maart 2021

De updates in maart 2021 bevatten verschillende functies, prestatie-upgrades en bugfixes.

### <a name="activities"></a>Activiteiten

- **Activiteitswizard en semantische typen**

   We hebben onze ervaring met het toewijzen van activiteiten verbeterd en bijgewerkt om het uitvoeren van activiteittoewijzing te begeleiden en te vereenvoudigen. In deze nieuwe ervaring krijgen gebruikers een begeleide ervaring als hulpmiddel bij het voltooien van elke stap van het proces. Bij de stap van het toewijzen van activiteiten kan de gebruiker niet alleen kiezen uit vele typen activiteiten, maar ook semantisch gegevens toewijzen aan *Subscription* en/of *SalesOrderLine* volgens industriestandaard schema's, die kunnen worden gebruikt voor verbruik stroomafwaarts.   

   Zie [Klantactiviteiten](activities.md) voor meer informatie.

### <a name="data-ingestion"></a>Gegevensopname

- **Verbinding maken met on-premises gegevensbronnen via Power Platform-gegevensstromen en -gateways** We zijn verheugd de preview aan te kondigen van Power Platform-gegevensstromen en on-premises-connectiviteit met behulp van gateways in Customer Insights met een bijbehorende Power Platform- of Dataverse-omgeving. Alle nieuwe gegevensbronnen die zijn gemaakt in een Customer Insights-omgeving met een gekoppelde Dataverse-omgeving worden standaard ingesteld op Power Platform-gegevensstromen die de on-premises gegevensconnectiviteit en een uitgebreide set connectors en transformatiemogelijkheden bieden.

### <a name="extensibility"></a>Uitbreidbaarheid

- **Exports georganiseerd in verbindingen en exports** We hebben de naam van de pagina **Exportbestemmingen** gewijzigd in **Verbindingen** en een aparte pagina toegevoegd voor **Exports**. Als onderdeel van deze update zetten we bestaande exports om in paren van een verbinding en een export met die verbinding. Beheerders hebben nu meer duidelijkheid over uitgaande gegevens op de pagina **Verbindingen**. Alle gebruikersrollen hebben toegang tot de pagina **Exports**, maar alleen beheerders kunnen ervoor kiezen om bijdragers toe te staan specifieke exports met gedeelde verbindingen te bewerken.     
  Zie [Overzicht van verbindingen](connections.md) en [Overzicht van exports](export-destinations.md) voor meer informatie.

- **Segmenten exporteren naar Campaign Monitor** We hebben onze exportbestemmingen uitgebreid met Campaign Monitor. U kunt nu segmenten exporteren van Customer Insights naar Campaign Monitor-lijsten en deze gebruiken als basis voor uw marketingcampagnes.    
   Zie [Exporteren naar Campaign Monitor](export-campaign-monitor.md) voor meer informatie.

- **Segmenten exporteren naar Constant Contact** We hebben onze exportbestemmingen uitgebreid met Constant Contact. U kunt nu segmenten exporteren van Customer Insights naar Constant Contact-lijsten en deze gebruiken als basis voor uw marketingcampagnes.   
   Zie [Exporteren naar Constant Contact](export-constant-contact.md) voor meer informatie.

- **Segmenten exporteren naar RollWorks** We hebben onze exportbestemmingen uitgebreid met RollWorks. U kunt nu segmenten van Customer Insights exporteren naar RollWorks-doelgroepen en deze gebruiken als basis voor uw B2B-reclames.    
   Zie [Exporteren naar RollWorks ](export-rollworks.md) voor meer informatie.

- **Segmenten exporteren naar Snapchat** We hebben onze exportbestemmingen uitgebreid met Snapchat. U kunt nu segmenten exporteren van Customer Insights naar Snapchat-doelgroepen en deze gebruiken als basis voor uw reclame.     
   Zie [Exporteren naar Snapchat](export-snapchat.md) voor meer informatie.

### <a name="predictions"></a>Voorspellingen

- **Productfilters gebruiken in voorspellende productaanbevelingen** We hebben de mogelijkheid toegevoegd om productfilters te gebruiken in ons productaanbevelingsmodel. U kunt nu een voorspelling maken die alleen een subset van uw producten gebruikt.    
   Zie [Productfilters configureren](predict-product-recommendation.md#configure-product-filters) voor meer informatie.

- **Segmenten op basis van modelvoorspellingen** We hebben een snelle manier toegevoegd om segmenten te maken met behulp van de resultaten van een voorspellingsmodel. Vanaf de modelresultatenpagina kunt u eenvoudig een nieuw segment maken door de nieuwe optie **Segment maken** te selecteren.    
  Zie [Een segment maken op basis van een voorspellingsmodel](prediction-based-segment.md) voor meer informatie.

- **Uitleg voor productaanbevelingen** We hebben informatie toegevoegd waarin de belangrijkste factoren worden uitgelegd die door het AI-model zijn geleerd om productaanbevelingen te genereren en de mate waarin die factoren bijdragen aan de productaanbevelingen. Deze informatie wordt toegevoegd aan het scherm met modelresultaten.    
   Zie [Een voorspellingsstatus en resultaten beoordelen](predict-product-recommendation.md#review-a-prediction-status-and-results) voor meer informatie.

## <a name="february-2021-updates"></a>Updates van februari 2021

De updates van februari 2021 omvatten verschillende functies, prestatie-upgrades en bugfixes.

#### <a name="extensibility"></a>Uitbreidbaarheid

- **Segmenten exporteren naar AdRoll**

  We hebben onze exportbestemmingen uitgebreid met AdRoll. U kunt nu segmenten van Customer Insights naar AdRoll-doelgroepen exporteren en deze als basis voor uw advertenties gebruiken. Zie [Connector voor AdRoll](export-adroll.md) voor meer informatie.

#### <a name="segments"></a>Segmenten
 
- **Een segment dupliceren**
  
  Om een nieuw segment te maken op basis van een bestaand segment, kunt u nu een segment dupliceren en het gedupliceerde segment bewerken om het verder te verfijnen. 

- **Extra kenmerken toevoegen aan een segment**

  U kunt nu kenmerken in uw segmentuitvoer opnemen, zelfs als deze kenmerken geen deel uitmaken van het klantprofiel. Neem bijvoorbeeld abonnement-id's op in een segment, ook al is het onderdeel van de abonnementsentiteit die een M:1-relatie heeft met de klantentiteit. Zolang het kenmerk toebehoort aan een entiteit die gerelateerd is aan de klantentiteit, kunt u deze kenmerken nu opnemen.  

#### <a name="predictions"></a>Voorspellingen

- **Voorspellende productaanbevelingen maken**

  Begrijpen waar klanten in geïnteresseerd zijn, is een van de eerste stappen die nodig zijn om de bedrijfsomzet te verbeteren en klantloyaliteit op te bouwen door middel van personalisatie en betrokkenheid. Aanbevelingen doen voor producten die niet zijn afgestemd op de interesses van uw klant, kan tot een gevoel van onthechting tussen de klant en uw bedrijf leiden en uiteindelijk de algehele potentiële inkomsten en ervaring voor een klant beperken. 

  Met uw eigen gegevens kunt u nu voorspellingen maken ten aanzien van de producten die uw klanten waarschijnlijk in de toekomst willen kopen. Zie [Productaanbevelingen voorspellen](predict-product-recommendation.md) voor meer informatie.

#### <a name="system-administration"></a>Systeembeheer

- **De kopieeromgeving ondersteunt meer soorten gegevensbronnen**

  Beheerders kunnen omgevingsconfiguraties kopiëren naar een nieuwe omgeving in dezelfde organisatie. Deze functie breidt de functionaliteit voor het kopiëren van omgevingen uit voor gevallen waarin gegevensbronnen op basis van een door Microsoft Dataverse beheerde data lake of een Common Data Model-map worden gebruikt.

## <a name="january-2021-updates"></a>Updates januari 2021

De updates van januari 2021 omvatten verschillende functies, prestatie-upgrades en bugfixes.

#### <a name="extensibility"></a>Uitbreidbaarheid

- **Uitgebreide functionaliteit en verbeterde prestaties voor SFTP-export** U kunt nu alle uitvoerentiteiten van Customer Insights naar een SFTP-host exporteren. Voorheen was de export beperkt tot segmententiteiten. Bovendien zorgt de prestatie van de SFTP-export voor een hoger gegevensvolume in minder tijd, afhankelijk van de prestaties van uw SFTP-host.    
  Zie [Connector voor SFTP (preview)](export-sftp.md) voor meer informatie.  

#### <a name="segments"></a>Segmenten

- **Door Machine Learning aangedreven voorgestelde segmenten om de statistieken te verbeteren** Er is een nieuwe manier om segmenten te ontdekken en te maken. Het systeem gebruikt een AI-model om segmenten voor te stellen die kunnen helpen bij de verbetering van een KPI (meting) die u al volgt. We laten de mate van invloed zien van kenmerken die u selecteert op een meting of een ander primair kenmerk. Deze informatie helpt bij het vinden van potentiële segmenten die kansen bieden.    
  Zie [Voorgestelde segmenten (preview)](suggested-segments.md) voor meer informatie.

#### <a name="data-unification"></a>Gegevensharmonisatie

- **Verbeterde overeenkomstervaring** In het gebied voor gegevensharmonisatie is de overeenkomstervaring bijgewerkt. Hiermee kunt u de overeenkomstregels configureren en bekijken, inclusief gedetailleerde statistieken om verder uit te leggen hoe het matchen werkt. Er zijn opties om een overeenkomstregel uit te schakelen, zodat deze niet meer actief is terwijl de configuratie behouden blijft, overeenkomstregels te slepen en neer te zetten en meer.
  Zie [Entiteiten matchen](match-entities.md) voor meer informatie.

- **Ontdubbelingsuitvoer van het matchproces is beschikbaar als een entiteit** Uitvoer van het ontdubbelingsproces van het matchingsproces wordt nu in een afzonderlijke entiteit geschreven voor verdere analyse. Deze entiteit bestaat uit de velden die worden gebruikt in het ontdubbelingsproces en de winnende record en de bijbehorende alternatieve records die worden samengevoegd met de winnende record.
  Zie [Ontdubbelingsuitvoer als een entiteit](match-entities.md#deduplication-output-as-an-entity) voor meer informatie.

#### <a name="system-administration"></a>Systeembeheer

- **Naadloos gegevens delen met Microsoft Dataverse** U kunt nu Customer Insights-uitvoer delen met Microsoft Dataverse-toepassingen met behulp van de Microsoft Dataverse beheerde data lake. Zodra u een Dataverse-omgeving koppelt aan Customer Insights, krijgt u de mogelijkheid om het delen van gegevens in te schakelen.
  Zie [Omgevingen beheren](manage-environments.md) voor meer informatie.




[!INCLUDE[footer-include](../includes/footer-banner.md)]