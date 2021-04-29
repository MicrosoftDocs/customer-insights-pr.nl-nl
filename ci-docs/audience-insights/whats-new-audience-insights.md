---
title: Nieuwe en komende functies
description: Informatie over nieuwe functies, verbeteringen en bugfixes.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 2159481f9355de738a7b457dcf0849a45c3e08db
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896229"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Wat is er nieuw in de doelgroepinzichten-mogelijkheid van Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

We kondigen vol trots onze meest recente updates aan. Dit artikel geeft een overzicht van openbare preview-functies, verbeteringen in de algemene beschikbaarheid en functie-updates. Als u de langetermijnplannen voor functies wilt zien, bekijkt u de [releaseplannen voor Dynamics 365 en Power Platform](/dynamics365/release-plans/).

We implementeren updates per regio. In sommige regio's komen functies dus mogelijk eerder beschikbaar dan in andere. Tenzij anders gespecificeerd, hoeft u geen actie te ondernemen en updaten we de app automatisch zonder downtime.

> [!TIP]
> Voor het indienen en beoordelen van functieverzoeken en productsuggesties gaat u naar de [Dynamics 365 Application Ideas-portal](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="march-2021-updates"></a>Updates van maart 2021

De updates in maart 2021 bevatten verschillende functies, prestatie-upgrades en bugfixes.

### <a name="activities"></a>Activiteiten

- **Activiteitswizard en semantische typen** We hebben onze ervaring met het toewijzen van activiteiten verbeterd en bijgewerkt om het uitvoeren van activiteittoewijzing te begeleiden en te vereenvoudigen. In deze nieuwe ervaring krijgen gebruikers een begeleide ervaring als hulpmiddel bij het voltooien van elke stap van het proces. Bij de stap van het toewijzen van activiteiten kan de gebruiker niet alleen kiezen uit vele typen activiteiten, maar ook semantisch gegevens toewijzen aan *Subscription* en/of *SalesOrderLine* volgens industriestandaard schema's, die kunnen worden gebruikt voor verbruik stroomafwaarts.    
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

- **Segmenten exporteren naar RollWorks** We hebben onze exportbestemmingen uitgebreid met RollWorks. U kunt nu segmenten exporteren van Customer Insights naar RollWorks-doelgroepen en deze gebruiken als basis voor uw B2B-reclame.    
   Zie [Exporteren naar RollWorks](export-rollworks.md) voor meer informatie.

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

  Beheerders kunnen omgevingsconfiguraties kopiëren naar een nieuwe omgeving in dezelfde organisatie. Met deze functie wordt de kopieeromgevingfunctionaliteit uit voor gevallen waarin gegevensbronnen op basis van een Common Data Service-data lake of een Common Data Model-map worden gebruikt.

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


## <a name="december-2020-updates"></a>Updates van december 2020

De updates van december 2020 bevatten verschillende functies, prestatie-upgrades en bugfixes.

### <a name="new-and-updated-features-in-december-2020"></a>Nieuwe en bijgewerkte functies in december 2020

#### <a name="data-enrichment"></a>Gegevensverrijking

- **Verbeterde verrijkingen van affiniteit met merken en interesses**
  
  We hebben onze affiniteitsscores vereenvoudigd om ze gemakkelijker te begrijpen en te gebruiken. U kunt nu snel klanten identificeren op basis van hoeveel affiniteit ze hebben voor een bepaald merk of een bepaalde interesse.

  Daarnaast hebben we nieuwe configuratieopties toegevoegd om beter te kunnen bepalen hoe u wilt dat uw klantprofielen worden verrijkt. 

  Zie [Klantprofielen verrijken met merk- en interesseaffiniteiten](enrichment-microsoft.md) voor meer informatie.

- **Bepalen welke profielen u wilt verrijken**

  U kunt nu alleen een subset van uw klantprofielen verrijken met de optie om een segmententiteit te selecteren in plaats van de standaard klantentiteit. Maak een segment met de klantprofielen die u wilt verrijken en selecteer dit in de verrijkingsconfiguratie voor uw klantgegevensset.
  Deze functie is momenteel alleen beschikbaar voor verrijkingen die worden geleverd door Experian en HERE Technologies. We zullen deze mogelijkheid binnenkort voor meer verrijkingen mogelijk maken.

  Zie voor meer informatie [Klantprofielen verrijken met demografische gegevens van Experian](enrichment-experian.md) of [Verrijking van klantprofielen met HERE Technologies](enrichment-here.md)​.

#### <a name="extensibility"></a>Uitbreidbaarheid

- **Uw segmenten activeren via Autopilot**

  Exporteer segmenten naar Autopilot en gebruik ze voor marketingdoeleinden. Zie [Connector voor Autopilot (preview)](export-autopilot.md) voor meer informatie.

- **Uw segmenten activeren via SendGrid**

  Exporteer segmenten naar SendGrid en gebruik ze voor marketingdoeleinden. Zie [Connector voor SendGrid](export-sendgrid.md) voor meer informatie.

#### <a name="system-administration"></a>Systeembeheer

- **Bijgewerkte ervaring met omgevingsbeheer**
  
  U kunt nu omgevingen rechtstreeks vanuit de omgevingskiezer in de app-koptekst maken, bewerken, verwijderen en opnieuw instellen. 
  
  Bovendien wordt de omgeving die u gebruikt, boven aan het omgevingspaneel vastgezet, zodat u er niet meer naar hoeft te zoeken.

  Zie [Omgevingen beheren](manage-environments.md) voor meer informatie.

## <a name="november-2020-updates"></a>Updates van november 2020

De updates van november 2020 bevatten verschillende functies, prestatie-upgrades en bugfixes.

### <a name="new-and-updated-features-in-november-2020"></a>Nieuwe en bijgewerkte functies in november 2020

#### <a name="data-enrichment"></a>Gegevensverrijking

- **Breng uw eigen verrijkingsgegevens mee via aangepaste import via Secure File Transfer Protocol (SFTP)**
  
  Dankzij de aangepaste import van SFTP kunt u verrijkingsgegevens importeren die niet door het proces van gegevensharmonisatie hoeven te gaan. Meer informatie over aangepaste SFTP-import.

  Zie [Klantprofielen verrijken met aangepaste gegevens (preview)](enrichment-SFTP-custom-import.md) voor meer informatie.
 
- **Verrijk uw klantgegevens met locatiegegevens van HERE Technologies**

  Met de gegevensverrijkingsservices van HERE Technologies kunt u een nauwkeuriger locatie-inzicht van uw klanten opbouwen met adresnormalisatie, extractie van breedtegraad en lengtegraad en meer. Meer informatie over verrijken met HERE Technologies.

  Zie [Verrijking van klantprofielen met HERE Technologies](enrichment-here.md) voor meer informatie.

#### <a name="data-unification"></a>Gegevensharmonisatie

- **Flexibiliteit om gegevensprofilering in te schakelen voor geselecteerde entiteiten en velden vanuit uw opslagaccount**

  U kunt aangeven welke gegevensentiteiten en velden uit een Common Data Model-map in uw Azure Data Lake-opslagaccount u wilt inschakelen voor gegevensprofilering als onderdeel van het gegevensopnameproces.

  Zie [Verbinden met een Common Data Model-map](connect-common-data-model.md#connect-to-a-common-data-model-folder) voor meer informatie.

#### <a name="extensibility"></a>Uitbreidbaarheid

- **Activeer uw segmenten via Google Ads**

  Exporteer segmenten van Google Ads-doelgroeplijsten en gebruik deze lijsten om te adverteren op Google Zoeken, Google Display Network, YouTube en Gmail. Meer informatie over het activeren van uw segmenten via Google Ads.

  Zie [Connector voor Google Ads](export-google-ads.md) voor meer informatie.

- **Activeer uw segmenten via Marketo**

  Exporteer segmenten naar Marketo-doelgroepen en gebruik deze doelgroepen voor marketingautomatisering. Meer informatie over het activeren van uw segmenten via Marketo. 

  Zie [Connector voor Marketo](export-marketo.md) voor meer informatie.

- **Activeer uw segmenten via DotDigital**

  Exporteer segmenten naar DotDigital en gebruik ze voor marketingdoeleinden. Meer informatie over het activeren van uw segmenten via DotDigital. 

  Zie [Connector voor DotDigital](export-dotdigital.md) voor meer informatie.

#### <a name="predictions"></a>Voorspellingen

- **Transactieverloop voorspellen**

  Met de functie voor het voorspellen van transactieverloop kunt u, zonder de hulp van een datawetenschapper, de kans voorspellen dat een klant stopt met het kopen van producten of services.  Met de voorspellingsscore kunt u andere informatie over uw klanten, zoals klantwaarde, combineren om segmenten met een hoog verlooprisico of hoogwaardige klanten te creëren. Gebruik dit segment om klanten rechtstreeks te targeten via marketingactiviteiten, klantenondersteuning en andere scenario's om het verlooprisico te verminderen.
 
  Configureer de definitie van verloop als een tijdvenster dat specifiek is voor uw bedrijf en bepaal wanneer klanten als verloop worden beschouwd. Een supermarkt kan bijvoorbeeld overwegen een klant te laten verlopen als hij in de afgelopen 30 dagen niets heeft gekocht.
 
  Terwijl u doorgaat met het maken van de voorspelling, begeleiden we u bij de keuze van de gegevens die nodig zijn en leert u gegevens over uw bedrijf toe te wijzen aan velden die nodig zijn om het verloop voor uw klanten te voorspellen. U kunt ook een planning instellen om het model opnieuw te trainen op basis van nieuwe informatie in uw systeem om zich aan te passen aan veranderende bedrijfsomstandigheden.
 
  Zie [Transactieverloop voorspellen (preview)](predict-transactional-churn.md) voor meer informatie.

#### <a name="system-administration"></a>Systeembeheer

- **Omgeving opnieuw instellen**

  Reset alles in een omgeving van een geselecteerd exemplaar om opnieuw te beginnen.

  Zie [Een bestaande omgeving resetten](manage-environments.md#reset-an-existing-environment) voor meer informatie.


- **Verbinding maken met uw Azure Data Lake-opslagaccount met behulp van een service-principal**

  Schrijf gegevensuitvoer naar en lees gegevens uit uw opslagaccount met behulp van een Azure service-principal. Bestaande verbindingen met opslagaccounts kunnen de accountsleutel blijven gebruiken. Ze bieden ook een upgrade-optie om de service-principal in de toekomst te gebruiken. Nieuwe verbindingen worden gebaseerd op de service-principal-verificatiemethode voor uw opslagaccount.

  Zie [Verbinding maken met een Azure Data Lake Storage Gen2-account met een Azure Service Principal voor doelgroepinzichten](connect-service-principal.md) voor meer informatie.

## <a name="october-2020-updates"></a>Updates van oktober 2020

De updates van oktober 2020 bevatten verschillende functies, prestatie-upgrades en bugfixes.

### <a name="new-and-updated-features-in-october-2020"></a>Nieuwe en bijgewerkte functies in oktober 2020

#### <a name="extensibility"></a>Uitbreidbaarheid

- **Exporteren naar MailChimp**

Exporteer segmenten naar bestaande doelgroeplijsten in Mailchimp om uw klanten een gepersonaliseerde e-mailervaring te bieden.

Zie [Connector voor Mailchimp](export-mailchimp.md) voor meer informatie.

#### <a name="data-enrichment"></a>Gegevensverrijking

- **De bronrecords in een Match-entiteit ontdubbelen**

Specificeer ontdubbelingsregels voor entiteiten die in het matchproces worden gebruikt om dubbele records te identificeren. Voeg ze samen tot één record en koppel alle bronrecords aan dit samengevoegde record. Dit gededupliceerde record wordt vervolgens gebruikt in het matchingproces in verschillende entiteiten.

Zie [Ontdubbeling op een match-entiteit definiëren](match-entities.md#define-deduplication-on-a-match-entity) voor meer informatie.

#### <a name="system-administration"></a>Systeembeheer

- **Indeling: nieuwe vernieuwingsoptie in Samenvoegen**

Tot voor kort voerde het systeem, als u het samenvoegingsproces uitvoert, alle downstream-processen uit die afhankelijk zijn van samenvoeging en daaropvolgende processen. U kunt nu de uitvoer van het samenvoegingsproces (de geharmoniseerde klantentiteit) verifiëren voordat u deze gebruikt in downstream-verwerking, zoals segmenten of metingen.
Op de samenvoegpagina kunt u er nu voor kiezen om alleen de samenvoegingsstap uit te voeren en alleen dit proces uit te voeren. Om ook alle downstream-processen te vernieuwen, kunt u kiezen voor samenvoeg- en downstream-processen uitvoeren. 

## <a name="september-2020-updates"></a>Updates van september 2020

De updates van september 2020 omvatten verschillende functies, prestatie-upgrades en bugfixes.

### <a name="new-and-updated-features-in-september-2020"></a>Nieuwe en bijgewerkte functies in september 2020

#### <a name="activities"></a>Activiteiten

- **Intelligente voorspelling van kenmerksemantiek**

Deze nieuwe functie voorspelt de semantische typen van invoerkenmerken die worden doorgegeven aan het gegevensunificatieproces. Het maakt gebruik van Machine Learning-modellen die de nauwkeurigheid verbeteren en tijd besparen.

#### <a name="enrichments"></a>Verrijkingen

- **Demografische gegevensverrijking met Experian**

De demografische gegevensverrijking van Experian is nu beschikbaar als preview. Experian is een wereldleider in kredietrapportage en marketingdiensten voor consumenten en bedrijven. Met [De Experian-services voor gegevensverrijking](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage) kunt u een dieper inzicht in uw klanten opbouwen door uw klantprofielen te verrijken met demografische gegevens zoals de grootte van het huishouden, het inkomen en meer.

Als u deze functie wilt gebruiken, moet u een actief Experian-abonnement hebben.

Zie voor meer informatie [Klantprofielen verrijken met demografische gegevens van Experian](enrichment-experian.md)


#### <a name="system-administration"></a>Systeembeheer

- **Deelvenster Taakdetails**

In het deelvenster Taakdetails ziet u details over taken die door het systeem worden uitgevoerd. Het is een handige manier om problemen met de configuratie te identificeren en oplossingen te vinden.
Bekijk de foutmeldingen om te zien hoe u mogelijke problemen aanpakt.
 
- **Verwerkingsinformatie toegevoegd aan meer pagina's**

Door deze verbetering wordt informatie over de status van uw entiteiten toegevoegd op de pagina **Entiteiten** en **Klanten**.
 
Bovendien kunt u op beide pagina's details vinden over de voortgang van processen, samen met de taakdetails.

- **Verbeteringen aan de systeemstatuspagina**

We hebben de structuur van de tabel met statusdetails verbeterd onder **Systeem** > **Status** als u gegevensexports bekijkt.
 
Bovendien zijn fouten in de kolom **Details** nu meer gedetailleerd en actiegericht. 
 
- **Met Annuleren keert de taak terug naar de vorige staat**

Wanneer u een taak annuleert bijvoorbeeld tijdens het afstemmingsproces, keert deze terug naar de laatste staat. Als het afstemmingsproces bijvoorbeeld gisteren is voltooid en u annuleert het vandaag, keert het terug naar de status van gisteren.


## <a name="august-2020-updates"></a>Updates augustus 2020

De updates van augustus 2020 omvatten verschillende functies, prestatie-upgrades en bugfixes.

### <a name="new-and-updated-features-in-august-2020"></a>Nieuwe en bijgewerkte functies in augustus 2020

#### <a name="data-unification"></a>Gegevensharmonisatie

- **Verbeterde ervaring voor de kaartfase tijdens gegevensunificatie**

  Dankzij de voorzieningen in de kaartfase van het gegevensunificatieproces kunt u op eenvoudiger entiteiten en kenmerken selecteren en semantiek definiëren.

  De wijzigingen omvatten:
  
  - Minder interacties nodig om entiteiten en velden toe te voegen
  - Verbeterde zoekmogelijkheden op de kaartpagina
  - Visuele en gemakkelijke identificatie van het voorgestelde veldtype

#### <a name="enrichment"></a>Verrijking

- **Verrijking van interesse-affiniteiten beschikbaar in meer markten**

  We breiden de beschikbaarheid van de verrijking van interesse-affiniteiten uit buiten de Verenigde Staten naar vijf andere markten: Canada, Australië, Verenigd Koninkrijk, Frankrijk en Duitsland. Met deze uitbreiding kunt u uw klantgegevens verrijken met meer interesses die van toepassing zijn op deze markten. We verrijken ook uw klantprofielen die zich in deze markten bevinden door gebruik te maken van lokale bedrijfseigen gegevens van Microsoft.
  Zie [Klantprofielen verrijken met merk- en interesseaffiniteiten](enrichment-microsoft.md) voor meer informatie


## <a name="july-2020-updates"></a>Updates juli 2020

De updates van juli 2020 omvatten verschillende functies, prestatie-upgrades en bugfixes.

### <a name="new-and-updated-features-in-july-2020"></a>Nieuwe en bijgewerkte functies in juli 2020

#### <a name="extensibility"></a>Uitbreidbaarheid

- **Power Automate-trigger voor voltooid harmoniseringsproces**

  We hebben onze triggers uitgebreid voor Power Automate en laten u een melding of actie maken wanneer een vernieuwing van het harmoniseringsproces (toewijzing, afstemming, samenvoeging) is voltooid.    
  Zie [Power Automate-connector](export-power-automate.md) voor meer informatie

#### <a name="enrichment"></a>Verrijking

- **Verrijking van merkaffiniteiten beschikbaar in meer markten**

  We breiden de beschikbaarheid van de verrijking van merkaffiniteiten uit buiten de Verenigde Staten naar vijf andere markten: Canada, Australië, Verenigd Koninkrijk, Frankrijk en Duitsland. Met deze extensie kunt u uw klantgegevens verrijken met lokale merken in deze markten. We verrijken ook uw klantprofielen die zich in deze markten bevinden door gebruik te maken van lokale bedrijfseigen gegevens van Microsoft.
  Zie [Klantprofielen verrijken met merk- en interesseaffiniteiten](enrichment-microsoft.md) voor meer informatie

## <a name="june-2020-updates"></a>Updates juni 2020

De updates van juni 2020 omvatten verschillende functies, prestatie-upgrades en bugfixes.

### <a name="new-and-updated-features-in-june-2020"></a>Nieuwe en bijgewerkte functies in juni 2020

#### <a name="enrichment"></a>Verrijking

- **Verrijking met bedrijfsgegevens uit Leadspace**
  
  Definieer velden in geharmoniseerde klantprofielen die worden gebruikt om gerelateerde bedrijfsgegevens op te zoeken vanuit Leadspace. Nadat het verrijkingsproces is uitgevoerd, worden B2B-profielen verrijkt met meer kenmerken, waaronder bedrijfsgrootte, locatie, branche en meer.    
  Door deze samenwerking kunt u de kwaliteit van uw data verbeteren met input van externe services. Om deze verrijking te gebruiken, hebt u een licentie van Leadspace nodig om toegang te krijgen tot hun B2B-bedrijfsgegevens. Het systeem gebruikt die licentie om uw gegevens continu te verrijken.    
  Zie [Verrijking van bedrijfsprofielen met Leadspace](enrichment-leadspace.md) voor meer informatie.

- **Pagina van verrijkingshub**

  Alle beschikbare gegevensverrijking van eigen en externe verrijkingsproviders wordt op dezelfde plaats geconfigureerd. Het configureren van gegevensverrijking is een naadloze ervaring die wordt beheerd vanaf een gemeenschappelijke plek.    
  Zie [Verrijking voor klantprofielen](enrichment-hub.md) voor meer informatie.

- **Aparte verrijking van merk- en interesseaffiniteit**

  De affiniteiten met merken en interesses zijn nu beschikbaar als twee onafhankelijke verrijkingen. Aparte verrijkingen geven u de flexibiliteit om ze elk afzonderlijk te configureren en te beheren, afhankelijk van uw zakelijke vereisten of behoeften.    
  Zie [Klantprofielen verrijken met merk- en interesseaffiniteiten](enrichment-microsoft.md) voor meer informatie.

#### <a name="extensibility"></a>Uitbreidbaarheid

- **Klikbare URL's voor geharmoniseerde activiteiten in de invoegtoepassing Dynamics 365 Klantenkaart**

  De geharmoniseerde activiteiten in de Klantenkaart-invoegtoepassing tonen nu klikbare URL's als dergelijke URL's zijn gedefinieerd tijdens de configuratie van activiteiten.    
  Zie [Invoegtoepassing Klantenkaart](customer-card-add-in.md) voor meer informatie.

- **Merk- en interesseaffiniteiten beschikbaar in de invoegtoepassing Dynamics 365 Klantenkaart**

  Met een nieuw besturingselement in de invoegtoepassing Dynamics 365 Klantenkaart kunt u merk- en interesseverrijkingen weergeven voor uw contactpersonen in apps voor klantbetrokkenheid in Dynamics 365.    
  Zie [Invoegtoepassing Klantenkaart](customer-card-add-in.md) voor meer informatie.

- **Meer Power Automate-triggers**

  We hebben onze triggers voor Power Automate uitgebreid en de volgende triggers toegevoegd:
  - Ontvang een melding of voer een actie uit wanneer een geautomatiseerde volledige vernieuwing (gegevensbronnen, harmonisering, segmenten, metingen, exporten) is voltooid
  - Definieer een drempel voor een zakelijke maatregel. Zo kunt u bijvoorbeeld een melding maken die wordt verzonden wanneer de gedefinieerde drempel wordt overschreden. De trigger biedt bovendien informatie waarmee u complexere werkstromen kunt bouwen in Power Automate.    
  Zie [Power Automate-connector](export-power-automate.md) voor meer informatie

- **Exporteren naar Facebook Advertentiebeheer**
  
  Met deze mogelijkheid kunt u segmenten exporteren naar Facebook Ads Manager. Segmenten worden geëxporteerd als aangepaste doelgroepen om geharmoniseerde klantprofielen in Facebook marketingcampagnes en advertenties te gebruiken. De aangepaste doelgroepen zijn ook bruikbaar om campagnes op Instagram te maken via Facebook Advertentiebeheer.    
  Zie [Connector voor Facebook Advertentiebeheer](export-facebook.md) voor meer informatie.

#### <a name="predictions"></a>Voorspellingen

- **Voorspelling voor abonnementsverloop**

  Volg een begeleide ervaring om een verloopvoorspelling op te stellen in abonnementsgebieden zoals cloudservices, klantlidmaatschap en andere sectoren. 

  Met de functie voor het voorspellen van het verloop van abonnementen kunt u de waarschijnlijkheid voorspellen dat een klant stopt met het gebruik van op abonnementen gebaseerde producten of services zonder de hulp van een datawetenschapper in te roepen. Met de voorspellingsscore kunt u andere informatie over uw klanten combineren om segmenten met een hoog verlooprisico te creëren. Met behulp van dit segment kunt u klanten direct targeten in marketing, klantenondersteuning en andere scenario's om het risico van verloop voor specifieke klanten te verkleinen en zo de omzet te verbeteren en de kosten te verlagen.

  Binnen de ervaring kunt u de definitie van verloop configureren als een tijdgebaseerd venster dat specifiek is voor uw bedrijf. Een bedrijf voor videostreaming dat een maandelijks abonnement heeft, zou bijvoorbeeld kunnen overwegen dat een klant 15 dagen na afloop van zijn abonnement als verloop moet worden beschouwd.

  Terwijl u doorgaat met de voorspelling, zullen we u helpen bij het bepalen van de gegevens die nodig zijn en kunt u gegevens over uw bedrijf toewijzen aan velden die nodig zijn om het verloop te voorspellen voor uw klanten. Als bedrijfsinformatie verandert, kunt u ook een schema instellen om u bij te scholen in nieuwe informatie in uw systeem om zich aan te passen aan veranderende bedrijfsomstandigheden.    
  Zie [Voorspelling voor abonnementsverloop (preview)](predict-subscription-churn.md) voor meer informatie.

#### <a name="segments"></a>Segmenten

- **Vergelijkbare klanten zoeken**
  
  Vind vergelijkbare klanten in uw klantenbestand met behulp van kunstmatige intelligentie. Een Machine Learning-model voor binaire classificatie kent een overeenkomstscore toe aan klanten in het uitgebreide segment. De score is gebaseerd op de overeenkomst met klanten in het bronsegment. Afhankelijk van de overeenkomstscore worden klantprofielen toegevoegd aan een nieuw gemaakt segment.

  Bij digitale marketing wordt soms naar lookalike-modellering verwezen en wordt een AI-model gebruikt om klanten te vinden die lijken op een ander segment van uw klanten door rekening te houden met meer kenmerken. U kunt niet alleen de kenmerken kiezen, maar ook het maximale aantal klanten specificeren dat deel zou moeten uitmaken van dit nieuwe segment. Het AI-model berekent vervolgens de overeenkomstscores voor elke klant op basis van de door u geselecteerde kenmerken en vindt klanten met de hogere gemiddelde overeenkomstscore. Het resulterende segment omvat klanten die lijken op de klant in uw oorspronkelijke segment.    
  Zie [Vergelijkbare klanten](find-similar-customer-segments.md) voor meer informatie.

- **Segmentoverlapping en onderscheidende factoren**

  Met segmentoverlapping kunt u zien hoeveel en welke klanten gemeenschappelijk zijn voor twee of meer segmenten. Bijvoorbeeld, hoe een segment met veel uitgevers overlapt met een segment met hoge tevredenheid van klanten of hoe een segment met groeiende klanten overlapt met segment met klanten met een lage tevredenheid. Bovendien kunt u analyseren hoe de overlap verandert op basis van een extra kenmerk naar keuze.

  Onderscheidende factoren voor segmenten laten zien wat het ene segment onderscheidt van de rest van uw klanten of van een ander segment. Het enige dat u hoeft te doen, is een segment identificeren en het systeem zal profielkenmerken en meetcriteria identificeren die het segment onderscheiden in de vorm van een gerangschikte lijst van onderscheidende factoren, van de sterkste tot de zwakste.    
  Zie [Segmentinzichten (preview)](segment-insights.md) voor meer informatie.

- **Levensduur van segmenten**
  
  Definieer een schema om een segment te activeren of te deactiveren.    
  Zie [Bestaande segmenten beheren](segments.md#manage-existing-segments) voor meer informatie.

## <a name="may-2020-updates"></a>Updates voor mei 2020

De updates van mei 2020 omvatten verschillende functies, prestatie-upgrades en bugfixes.

### <a name="new-and-updated-features-in-may-2020"></a>Nieuwe en bijgewerkte functies in mei 2020

#### <a name="data-ingestion"></a>Gegevensopname

- **Realtime gegevensopname: geschiedenisweergaven**

  Wanneer u onze API gebruikt om realtime updates op te nemen, kunt u tot 30 dagen aan geaggregeerde geschiedenis voor deze updates bekijken. U hebt toegang tot aggregaties van alle succesvolle of mislukte API-aanroepen, inclusief hun resultaat, bronsysteem en andere nuttige metagegevens.    
  Zie [Realtime gegevensopname](real-time-data-ingestion.md) voor meer informatie.

- **Realtime gegevensopname: profielupdates**

  Met deze uitbreiding van de realtime gegevensopname kunt u binnen enkele seconden wijzigingen in specifieke gebruikersprofielvelden zien.    
  Naast de realtime functionaliteit voor activiteiten, ondersteunt het systeem updates met lage latentie van profielvelden. Realtime updates voor profielvelden hebben een vervaltijd en vormen daarom geen vervanging voor geplande vernieuwingen.    
  Zie [Realtime gegevensopname](real-time-data-ingestion.md) voor meer informatie.

#### <a name="extensibility"></a>Uitbreidbaarheid

- **Bijgewerkte tijdlijn en paginering op de invoegtoepassing Klantenkaart**

  De tijdlijn van de invoegtoepassingsoplossing Klantenkaart komt overeen met de activiteitentijdlijn. De paginering van de tijdlijn is verbeterd, en toont nu tot 50 activiteiten tegelijk. U kunt ook meer activiteiten in de tijdlijn laden.    
  Zie [Invoegtoepassing Klantenkaart](customer-card-add-in.md) voor meer informatie.

- **Power Automate-trigger voor segmentwijzigingen**

  Triggers voor Power Automate definiëren waarvan u een stroom kunt bouwen. Met de nieuw toegevoegde trigger kunt u een drempel voor een segment definiëren. Zo kunt u bijvoorbeeld een melding maken die wordt verzonden wanneer de gedefinieerde drempel wordt overschreden.    
  Zie [Power Automate-connector](export-power-automate.md) voor meer informatie.

- **Multitenant-ondersteuning voor aangepaste modellen**

  Configureer werkstromen voor aangepaste modellen met een webservice van een andere Azure Machine Learning-tenant. U kunt zich aanmelden bij de Azure Machine Learning-tenant wanneer u een nieuwe werkstroom voor aangepaste modellen maakt. Deze mogelijkheid is een aanvulling op de bestaande mogelijkheid om te integreren met uw eigen aangepaste Azure Machine Learning-webservice.    
  Zie [Aangepaste Machine Learning-modellen](custom-models.md) voor meer informatie.

#### <a name="segments"></a>Segmenten

- **Automatisering van entiteitspad**

  Bij het maken van een segment moeten gebruikers het entiteitspad definiëren. Deze mogelijkheid vormt een eerste stap in het automatiseren van de definitie van het entiteitspad, zodat u zich kunt concentreren op de segmentatiecriteria die u in gedachten hebt.    
  Als de entiteit waarmee u uw klanten wilt segmenteren rechtstreeks verband houdt met de geharmoniseerde klantentiteit, hoeft u het entiteitspad niet meer te definiëren. Als er echter meer dan één mogelijk entiteitspad is, moet u dit nog steeds handmatig definiëren.

- **Acties op meerdere segmenten**
  
  Gebruikers kunnen meerdere segmenten selecteren en er met een enkele klik acties op uitvoeren, zoals het vernieuwen van de segmenten.    

- **Segmenten vernieuwen**

  Gebruikers kunnen een enkel segment vernieuwen of alleen de segmenten selecteren die ze willen vernieuwen.    

  
- **Verbeteringen aan samengestelde segmenten**

  Gebruikers kunnen segmenten maken, bewerken en verwijderen die zijn gebaseerd op andere segmenten. Bijvoorbeeld een segment dat is gebouwd op een ander segment dat is gebouwd op een derde segment.    

- **Lijstpagina voor segmenten**

  Het nieuwe ontwerp van de segmentenpagina gebruikt een lijstindeling waarmee u meer segmenten tegelijk kunt bekijken. Er wordt een zoekveld toegevoegd om snel segmenten te vinden. Gebruikers kunnen nu acties zoals downloaden of verwijderen op meerdere segmenten tegelijk toepassen. Er wordt een nieuwe trendervaring geïntroduceerd om snel significante veranderingen in segmenten te identificeren.    
  Zie [Segmenten maken en beheren](segments.md) voor meer informatie.

#### <a name="system-administration"></a>Systeembeheer

- **Customer Insights beschikbaar in Microsoft Dynamics 365 Online Government**

  Met steeds meer kanalen voor interacties, zijn burgergegevens verspreid over talloze systemen, wat leidt tot in silo's opgenomen gegevens en een gefragmenteerde weergave van informatie over burgerinteracties. Zonder een volledig overzicht van de interacties van elke burger via de verschilende kanalen, is het voor regeringen onmogelijk om op grote schaal te moderniseren. Microsoft zet zich in om de technologische behoeften van de overheid te ondersteunen om te voldoen aan de verwachtingen van de burger voor consistente en responsieve ervaringen.    
  Met releasewave 1 van 2020, komt Dynamics 365 Customer Insights beschikbaar voor de Government Community Cloud (GCC), een omgeving die is gebouwd om te voldoen aan de hogere nalevingsbehoeften van Amerikaanse overheidsinstanties. Agentschappen krijgen een geharmoniseerd beeld van burgers en gebruiken vooraf gebouwde AI om inzichten af te leiden die interacties verbeteren, werknemers meer mogelijkheden bieden en gemeenschappen transformeren, terwijl IT-complexiteit wordt verminderd en wordt voldaan aan Amerikaanse nalevings- en beveiligingsnormen. Dynamics 365 Government voldoet aan de hoge vereisten van het US Federal Risk and Authorization Management Program (FedRAMP), waardoor Amerikaanse federale instanties kunnen profiteren van de kostenbesparingen en rigoureuze beveiliging van de Microsoft Cloud.

## <a name="april-2020-updates"></a>Updates van april 2020

De updates van april 2020 omvatten verschillende functies, prestatie-upgrades en bugfixes.

### <a name="new-and-updated-features-in-april-2020"></a>Nieuwe en bijgewerkte functies in april 2020

#### <a name="activities"></a>Activiteiten

- **Activiteitsentiteit toewijzen aan standaard activiteitstype**
  
  Configuratie en opslag van activiteiten zijn momenteel gebaseerd op een statisch ontwerp om ze in een tijdlijn te kunnen weergeven. De semantische betekenis van activiteiten, die potentieel heeft voor meerdere gebruikssituaties in AI-modellen, wordt momenteel niet volledig benut. We zijn van plan om de activiteitentijdlijn dynamischer te maken, gebaseerd op het activiteitstype en een beter semantisch begrip van de activiteiten. Deze functie is bedoeld om het activiteitstype te identificeren zoals gedefinieerd in Common Data Model voor elke opgenomen activiteit.
  Zie [Klantactiviteiten](activities.md) voor meer informatie.

#### <a name="data-ingestion"></a>Gegevensopname

- **Realtime gegevensopname: activiteiten**
  
  Realtime gegevensopname levert gegevens onmiddellijk op voor consumptie, totdat de volgende geplande vernieuwing deze gegevens uit de gegevensbron haalt.    
  Zie [Realtime gegevensopname](real-time-data-ingestion.md) voor meer informatie.

- **Verbeteringen bij gegevensvoorbereiding**
  
  Meer informatie over de gegevens die worden opgenomen in een entiteit. Met het gegevensoverzicht kunt u de kenmerken van de gegevenskwaliteit begrijpen die kunnen helpen om de juiste actie te ondernemen.    
  Zie [Entiteitsgegevens verkennen](entities.md#exploring-a-specific-entitys-data) voor meer informatie.

- **Analytische gegevens van Dynamics 365 opnemen met Common Data Service**
  
  Common Data Service is beschikbaar als een manier om gegevensbronnen te maken. Bestaande Dynamics 365-klanten kunnen analytische entiteiten vanuit Common Data Service opnemen in Customer Insights. Eén gegevensbron kan tegelijkertijd dezelfde door Common Data Service beheerde lake in een Customer Insights-omgeving gebruiken.    
  Zie [Verbinding met gegevens maken in een door Common Data Service beheerd data lake](connect-common-data-service-lake.md) voor meer informatie.

#### <a name="extensibility"></a>Uitbreidbaarheid

- **Exporteren naar LiveRamp**

  Activeer uw gegevens in LiveRamp® om verbinding te maken met meer dan 500 platforms in digitale, sociale en tv-ecosystemen. Gebruik uw gegevens in LiveRamp voor het targeten, verdringen en personaliseren van advertentiecampagnes.    
  Zie [LiveRamp&reg;-connector](export-liveramp.md) voor meer informatie.

- **Teams-invoegtoepassing voor Customer Insights**
  
  De bot biedt zoekmogelijkheden voor geharmoniseerde klantprofielen. Deze toont een kaart met maximaal 15 velden uit het resulterende klantprofiel. Meerdere overeenkomsten retourneren een lijst met resultaten waarin u een profiel kunt selecteren.    
  Zie [Teams-bot voor Customer Insights](export-teams-bot.md) voor meer informatie.

#### <a name="measures"></a>Metingen

- **Lijstpagina met metingen**
  
  Verbeteringen op de metingenpagina omvatten ondersteuning voor acties op een enkele meting en op meerdere metingen tegelijk. Bovendien vindt u een zoekveld om snel metingen te vinden en te volgen.    
  Zie [Segmenten maken en beheren](segments.md) voor meer informatie.

- **Verbeteringen aan samengestelde metingen**
  
  Gebruikers kunnen metingen maken, bewerken en verwijderen die zijn gebaseerd op andere metingen. Bijvoorbeeld een meting die is gebouwd op een andere meting die is gebouwd op een derde meting.

#### <a name="segments"></a>Segmenten

- **Nog een operator**
  
  De operator In set maakt segmentatie voor klanten mogelijk via verschillende mogelijke tekenreekswaarden. Voordat deze operator werd toegevoegd, moesten zulke segmenten worden geconstrueerd met meerdere OF-voorwaarden. Met de operator In set kunt u dat doen met één enkele voorwaarde.    
  Zie [Segmenten maken en beheren](segments.md) voor meer informatie.

#### <a name="system-administration"></a>Systeembeheer

- **Configuratie-instellingen kopiëren naar een nieuwe omgeving**
  
  Kopieer uw configuratie van de ene omgeving naar de andere. Tijdens het maken van een nieuwe omgeving kunt u een bestaande omgeving selecteren waaruit u de configuratie wilt kopiëren. We ondersteunen momenteel het kopiëren van gegevensbronnen, gegevensvereniging, relaties, metingen en segmenten. Referenties voor gegevensbronnen en feitelijke gegevens worden niet gekopieerd.    
  Zie [Omgevingen beheren](manage-environments.md) voor meer informatie.


[!INCLUDE[footer-include](../includes/footer-banner.md)]