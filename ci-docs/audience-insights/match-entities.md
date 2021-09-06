---
title: Entiteiten matchen voor gegevensharmonisatie
description: Match entiteiten om geharmoniseerde klantprofielen te maken.
ms.date: 02/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7ad08b8b782654939c6bfc2ca330a3d31e71054a2f2c97a921971d1056b7cd38
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033671"
---
# <a name="match-entities"></a>Entiteiten toewijzen

De afstemmingsfase geeft aan hoe u uw datasets kunt combineren in een geharmoniseerde klantprofielgegevensset. Na het voltooien van de [toewijzingsstap](map-entities.md) in het gegevensharmonisatieproces bent u klaar om uw entiteiten te matchen. De afstemmingsfase vereist minimaal twee toegewezen entiteiten.

De matchpagina bestaat uit drie secties: 
- Belangrijke metrische gegevens die het aantal overeenkomende records samenvatten
- Afstemmingsvolgorde en regels voor matchen tussen entiteiten
- Regels voor ontdubbeling van matchentiteiten

## <a name="specify-the-match-order"></a>De afstemmingsvolgorde opgeven

Ga naar **Gegevens** > **Harmoniseren** > **Afstemming** en selecteer **Volgorde instellen** om de afstemmingsfase te starten.

Elke match verenigt twee of meer entiteiten in één geconsolideerde entiteit. Tegelijkertijd worden de unieke klantrecords behouden. We hebben bijvoorbeeld twee entiteiten geselecteerd: **eCommerce:eCommerceContacts** als de primaire entiteit en **LoyaltyScheme:loyCustomers** als tweede entiteit. De volgorde van de entiteiten geeft aan in welke volgorde wordt geprobeerd de records te matchen.

:::image type="content" source="media/match-page.png" alt-text="Schermopname van de pagina Afstemming in het gedeelte Harmoniseren van het gegevensharmonisatieproces.":::
  
De primaire entiteit *eCommerce: eCommerceContacts* wordt afgestemd met de volgende entiteit *LoyaltyScheme: loyCustomers*.​ De gegevensset die het resultaat is van de eerste afstemmingsstap wordt vergeleken met de volgende entiteit als u meer dan twee entiteiten hebt.

> [!IMPORTANT]
> De entiteit die u kiest als uw primaire entiteit dient als basis voor uw geharmoniseerde gegevensset voor profielen. Extra entiteiten die tijdens de afstemmingsfase worden geselecteerd, worden aan deze entiteit toegevoegd. Dit betekent niet dat de geharmoniseerde entiteit *alle* gegevens bevat die in deze entiteit zijn opgenomen.
>
> Er zijn twee overwegingen die u kunnen helpen bij het kiezen van de hiërarchie van uw entiteiten:
>
> - Kies de entiteit met de meest volledige en betrouwbare profielgegevens over uw klanten als primaire entiteit.
> - Kies de entiteit die verschillende kenmerken gemeen heeft met andere entiteiten (bijvoorbeeld naam, telefoonnummer of e-mailadres) als primaire entiteit.

Nadat u de vergelijkingsvolgorde hebt opgegeven, ziet u de gedefinieerde vergelijkingsparen in de sectie **Details van afgestemde records** in **Gegevens** > **Verenigen** > **Afstemmen**​. De belangrijkste statistieken blijven leeg totdat het vergelijkingsproces is voltooid.

## <a name="define-rules-for-match-pairs"></a>Regels voor vergelijkingsparen definiëren

Afstemmingsregels specificeren de logica waarmee een specifiek paar entiteiten zal worden afgestemd.

De waarschuwing **Heeft regels nodig** naast de naam van een entiteit suggereert dat er geen overeenkomstregel is gedefinieerd voor een vergelijkingspaar. 

:::image type="content" source="media/match-rule-add.png" alt-text="Schermopname van de sectie Details van afgestemde records met het gemarkeerde besturingselement om regels toe te voegen.":::

1. Selecteer **Regels toevoegen** onder een entiteit in de sectie **Details van afgestemde records** om overeenkomstregels te definiëren.

1. Configureer in het deelvenster **Regel maken** de voorwaarden voor de regel.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Schermopname van een geopende overeenkomstregel waaraan voorwaarden zijn toegevoegd.":::

   - **Entiteit/Veld (eerste rij)**: kies een gerelateerde entiteit en een kenmerk om een recordeigenschap op te geven die waarschijnlijk uniek is voor een klant. Dit kan bijvoorbeeld een telefoonnummer of e-mailadres zijn. Maak geen vergelijkingen op basis van kenmerken van het activiteitstype. Voor een aankoop-id wordt bijvoorbeeld waarschijnlijk geen overeenkomst gevonden in andere recordtypen.

   - **Entiteit/Veld (tweede rij)**: kies een kenmerk dat betrekking heeft op het kenmerk van de entiteit opgegeven in de eerste rij.

   - **Normaliseren**: kies uit de volgende normalisatieopties voor de geselecteerde kenmerken. 
     - Spatie: verwijdert alle spaties. *Hallo   wereld* wordt *Hallowereld*.
     - Symbolen: hiermee verwijdert u alle symbolen en speciale tekens. *Hoofd&schouder* wordt *Hoofdschouder*​.
     - Tekst in kleine letters: alle tekens worden omgezet in kleine letters. *HOOFDLETTERS en Beginhoofdletters* wordt *hoofdletters en beginhoofdletters*​.
     - Van Unicode naar ASCII: converteert de Unicode-notatie naar ASCII-tekens. */u00B2* wordt *2*.
     - Cijfers: converteert andere cijfersystemen, zoals Romeinse cijfers, naar Arabische cijfers. *VIII* wordt *8*.
     - Semantische typen: standaardiseert namen, titels, telefoonnummers, adressen, enzovoort. 

   - **Precisie**: stel het precisieniveau in dat voor deze voorwaarde moet worden toegepast. 
     - **Basis**: kies uit *Laag*, *Gemiddeld*, *Hoog* en *Exact*. Selecteer **Exact** als u alleen records wilt afstemmen die 100 procent overeenkomen. Selecteer een van de andere niveaus om records af te stemmen die niet 100 procent identiek zijn.
     - **Aangepast**: stel een percentage in waaraan records moeten voldoen. Alleen records die deze drempel halen, worden vergeleken.

1. Geef een **naam** op voor de regel.

1. [Voeg meer voorwaarden toe](#add-conditions-to-a-rule) of selecteer **Gereed** om de regel af te ronden.

1. U kunt ook [meer regels toevoegen](#add-rules-to-a-match-pair)​.

1. Selecteer **Opslaan** om uw wijzigingen toe te passen.

### <a name="add-conditions-to-a-rule"></a>Voorwaarden toevoegen aan een regel

Als u entiteiten alleen wilt matchen als kenmerken aan meerdere voorwaarden voldoen, voegt u meer voorwaarden toe aan een overeenkomstregel. Voorwaarden zijn verbonden met een logische EN-operator en worden dus alleen uitgevoerd als aan alle voorwaarden is voldaan.

1. Ga naar **Gegevens** > **Verenigen** > **Afstemmen** en selecteer **Bewerken** voor de regel waaraan u voorwaarden wilt toevoegen.

1. Selecteer in het deelvenster **Regel bewerken** de optie **Voorwaarde toevoegen**.

1. Selecteer **Gereed** om de regel op te slaan.

### <a name="add-rules-to-a-match-pair"></a>Regels toevoegen aan een vergelijkingspaar

Overeenkomstregels staan voor voorwaardensets. Voeg meer regels toe om entiteiten te matchen op voorwaarden op basis van meerdere kenmerken.

1.  Ga naar **Gegevens** > **Verenigen** > **Afstemmen** en selecteer **Regel toevoegen** voor de entiteit waaraan u regels wilt toevoegen.

2. Volg de stappen in [Regels voor vergelijkingsparen definiëren](#define-rules-for-match-pairs)​.

> [!NOTE]
> De volgorde van regels is belangrijk. Het vergelijkingsalgoritme probeert te matchen op basis van uw eerste regel en gaat alleen verder naar de tweede regel als er geen overeenkomsten zijn geïdentificeerd met de eerste regel.

### <a name="change-the-entity-order-in-match-rules"></a>De entiteitsvolgorde in matchregels wijzigen

U kunt entiteiten voor matchregels opnieuw rangschikken om de volgorde te wijzigen waarin ze worden verwerkt. Regels die conflicteren vanwege een gewijzigde volgorde, worden verwijderd. U moet verwijderde regels opnieuw maken met een bijgewerkte configuratie.

1. Ga naar **Gegevens** > **Harmoniseren** > **Afstemming** en selecteer **Bewerken**.

1. Selecteer in het deelvenster **Regel bewerken** het besturingselement **Omhoog/omlaag** of gebruik slepen en neerzetten voor entiteiten om de volgorde te wijzigen.

   :::image type="content" source="media/reorder-match-rules.png" alt-text="Opties om te wijzigen in welke volgorde entiteiten worden verwerkt in de matchfase.":::

1. Selecteer **Gereed** om de regel op te slaan.

## <a name="define-deduplication-on-a-match-entity"></a>Ontdubbeling definiëren op een match-entiteit

Naast [regels voor matchen tussen entiteiten](#define-rules-for-match-pairs) kunt u ook ontdubbelingsregels opgeven. *Ontdubbeling* is een ander proces bij het matchen van records. Het identificeert dubbele records en voegt ze samen in één record. Bronrecords worden met alternatieve id's aan de samengevoegde record gekoppeld.

Ontdubbelde records worden gebruikt in het matchingproces tussen verschillende entiteiten. Ontdubbeling vindt plaats op individuele entiteiten en kan worden geconfigureerd voor elke entiteit die in vergelijkingsparen wordt gebruikt.

Het specificeren van ontdubbelingsregels is niet verplicht. Als dergelijke regels niet zijn geconfigureerd, worden de door het systeem gedefinieerde regels toegepast. Ze combineren alle records in één record voordat de entiteitsgegevens worden doorgegeven aan matching tussen entiteiten voor betere prestaties.

### <a name="add-deduplication-rules"></a>Ontdubbelingsregels toevoegen

1. Ga naar **Gegevens** > **Verenigen** > **Afstemming**.

1. Selecteer in de sectie **Samengevoegde duplicaten** de optie **Entiteiten instellen**. Als er al ontdubbelingsregels zijn gemaakt, selecteert u **Bewerken**​.

1. Kies in het deelvenster **Voorkeuren samenvoegen** de entiteiten waarvoor u ontdubbeling wilt uitvoeren.

1. Geef op hoe u de dubbele records wilt combineren en kies een van de drie opties:
   - **Meest gevuld**: identificeert de record met de meeste gevulde kenmerkvelden als de winnende record. Dit is de standaard samenvoegingsoptie.
   - **Meest recent**: identificeert het winnende record op basis van recentheid. Vereist een datum of een numeriek veld om de recentheid te definiëren.
   - **Minst recent**: identificeert het winnende record op basis van minst recent zijn. Vereist een datum of een numeriek veld om de recentheid te definiëren.
 
   > [!div class="mx-imgBorder"]
   > ![Ontdubbelingsregels stap 1.](media/match-selfconflation.png "Ontdubbelingsregels stap 1")
 
1. Zodra de entiteiten zijn geselecteerd en de voorkeur voor samenvoegen is ingesteld, selecteert u **Regel toevoegen** om de ontdubbelingsregels op entiteitsniveau te definiëren.
   - Met **Veld selecteren** worden alle beschikbare velden uit die entiteit weergegeven. Kies het veld dat u op duplicaten wilt controleren. Kies velden die waarschijnlijk uniek zijn voor elke afzonderlijke klant, bijvoorbeeld een e-mailadres of de combinatie van naam, plaats en telefoonnummer.
   - Geef de normalisatie- en precisie-instellingen op.
   - Geef meer voorwaarden op door **Voorwaarde toevoegen** te selecteren.
 
   > [!div class="mx-imgBorder"]
   > ![Ontdubbelingsregels stap 2.](media/match-selfconflation-rules.png "Ontdubbelingsregels stap 2")

  U kunt meerdere ontdubbelingsregels voor een entiteit maken. 

1. Door het matchproces uit te voeren, worden de records nu gegroepeerd op basis van de voorwaarden die zijn gedefinieerd in de ontdubbelingsregels. Nadat de records zijn gegroepeerd, wordt het samenvoegingsbeleid toegepast om het winnende record te identificeren.

1. Deze winnende record wordt vervolgens doorgegeven aan de overeenkomsten zoeken tussen entiteiten, samen met de niet-winnende records (bijvoorbeeld alternatieve id's) om de kwaliteit van de overeenkomst te verbeteren.

1. Alle aangepaste gedefinieerde overeenkomstregels overschrijven ontdubbelingsregels. Als een ontdubbelingsregel overeenkomende records identificeert, en een aangepaste matchregel is ingesteld om nooit te matchen met die records, dan matchen deze twee records niet.

1. Nadat u het [matchproces hebt uitgevoerd](#run-the-match-process), ziet u de ontdubbelingsstatistieken in de tegels met de belangrijkste statistieken.

### <a name="deduplication-output-as-an-entity"></a>Uitvoer van ontdubbeling als een entiteit

Het ontdubbelingsproces maakt een nieuwe entiteit voor elke entiteit uit de vergelijkingsparen om de ontdubbelde records te identificeren. Deze entiteiten zijn te vinden samen met de **ConflationMatchPairs:CustomerInsights** in de sectie **Systeem** op de pagina **Entiteiten**, met de naam **Deduplication_DataSource_Entity**.

Een entiteit voor ontdubbelingsuitvoer bevat de volgende informatie:
- Id's/sleutels
  - Het veld Primaire sleutel en het bijbehorende veld Alternatieve id's. Het veld Alternatieve id's bestaat uit alle alternatieve id's die voor een record zijn geïdentificeerd.
  - Het veld Deduplication_GroupId toont de groep of cluster die is geïdentificeerd binnen een entiteit die alle vergelijkbare records groepeert op basis van de opgegeven ontdubbelingsvelden. Dit wordt gebruikt voor systeemverwerkingsdoeleinden. Als er geen handmatige ontdubbelingsregels zijn opgegeven en door het systeem gedefinieerde ontdubbelingsregels van toepassing zijn, is het mogelijk dat u dit veld niet in de uitvoerentiteit voor ontdubbeling vindt.
  - Deduplication_WinnerId: dit veld bevat de winnende id van de geïdentificeerde groepen of clusters. Als de Deduplication_WinnerId hetzelfde is als de primaire sleutelwaarde voor een record, betekent dit dat de record de winnende record is.
- Velden die worden gebruikt om de ontdubbelingsregels te definiëren.
- Regel- en scorevelden om aan te geven welke van de ontdubbelingsregels zijn toegepast en welke score is geretourneerd door het matching-algoritme.
   
## <a name="run-the-match-process"></a>Het vergelijkingsproces uitvoeren

Met geconfigureerde overeenkomstregels, inclusief tussen entiteiten en ontdubbelingsregels, kunt u het vergelijkingsproces uitvoeren. 

Ga naar **Gegevens** > **Verenigen** > **Afstemmen** en selecteer **Uitvoeren** om het proces te starten. Het vergelijkingsalgoritme heeft enige tijd nodig om te voltooien en u kunt de configuratie pas wijzigen als deze is voltooid. U kunt de uitvoering annuleren als u wijzigingen wilt aanbrengen. Selecteer de status van de taak en selecteer **Taak annuleren** in het deelvenster **Details van voortgang**.

U vindt het resultaat van een geslaagde uitvoering, de geharmoniseerde klantprofielentiteit, op de pagina **Entiteiten**. Uw geharmoniseerde klantentiteit heeft de naam **Klanten** in de sectie **Profielen**. Bij de eerste geslaagde vergelijkingsuitvoering wordt de geharmoniseerde entiteit *Klant* gemaakt. Bij elke volgende vergelijking wordt die entiteit uitgebreid.

> [!TIP]
> Nadat u het vergelijkingsproces hebt uitgevoerd, selecteert u de processtatus om het deelvenster **Taakdetails** te openen. Het geeft een overzicht van de verwerkingstijd, de laatste verwerkingsdatum, en alle fouten en waarschuwingen in verband met de taak. Selecteer **Details bekijken** om te zien welke entiteiten hebben deelgenomen aan het vergelijkingsproces, welke regels erop zijn toegepast en of de updates met succes zijn gepubliceerd.  
> Er zijn [zes soorten status](system.md#status-types) voor taken/processen. Bovendien zijn de meeste processen [afhankelijk van andere stroomafwaartse processen](system.md#refresh-policies).  
> :::image type="content" source="media/process-detail-path.png" alt-text="Inzoompad om naar procesdetails te gaan vanuit de taakstatuskoppeling.":::

## <a name="review-and-validate-your-matches"></a>Uw afstemmingen controleren en valideren

Ga naar **Gegevens** > **Verenigen** > **Afstemmen** om de kwaliteit van uw vergelijkingsparen te evalueren en deze zo nodig te verfijnen.

De tegels boven aan de pagina tonen de belangrijkste statistieken en bieden een overzicht van het aantal vergeleken records en duplicaten.

:::image type="content" source="media/match-KPIs.png" alt-text="Bijgesneden schermopname van de belangrijkste statistieken op de pagina Afstemming met cijfers en details.":::

- **Unieke bronrecords** toont het aantal individuele bronrecords dat is verwerkt tijdens de laatste vergelijkingsuitvoering.
- **Overeenkomende en niet-overeenkomende records** geeft aan hoeveel unieke records er overblijven na verwerking van de overeenkomstregels.
- **Alleen overeenkomende records** toont het aantal overeenkomsten voor al uw vergelijkingsparen.

U kunt de resultaten van elk vergelijkingspaar en de regels ervan beoordelen in de tabel **Details van afgestemde records**. Vergelijk het aantal records dat afkomstig is van een vergelijkingspaar met het percentage succesvol vergeleken records.

Bekijk de regels van een vergelijkingspaar om het percentage succesvol vergeleken records op regelniveau te zien. Selecteer het beletselteken (...) en selecteer vervolgens **Voorbeeldweergave van afstemming** om al deze records op regelniveau te bekijken. We raden u aan enkele records te bekijken om te controleren of ze correct zijn afgestemd.

Probeer verschillende precisiedrempels voor voorwaarden om de optimale waarde te vinden.

  1. Selecteer het beletselteken (...) voor de regel waarmee u wilt experimenteren en selecteer **Bewerken**.

  2. Wijzig de precisiewaarden in de voorwaarden die u wilt reviseren.

  3. Selecteer **Voorbeeld** om het aantal overeenkomende en niet-overeenkomende records voor de geselecteerde voorwaarde te bekijken.

## <a name="manage-match-rules"></a>Overeenkomstregels beheren

U kunt de meeste vergelijkingsparameters opnieuw configureren en verfijnen.

:::image type="content" source="media/match-rules-management.png" alt-text="Schermopname van het vervolgkeuzemenu met opties voor afstemmingsregels.":::

- **Wijzig de volgorde van uw regels** als u meerdere regels hebt gedefinieerd. U kunt de wedstrijdregels opnieuw rangschikken door **Omhoog** en **Omlaag** te selecteren of door te slepen en neer te zetten.

- **Wijzig regelvoorwaarden** door **Bewerken** te selecteren en verschillende velden te kiezen.

- **Een regel deactiveren** om een overeenkomstregel te behouden en deze uit te sluiten van het vergelijkingsproces.

- **Dupliceer uw regels** als u een overeenkomstregel hebt gedefinieerd en u een sportgelijke regel met aanpassingen wilt maken. Selecteer vervolgens **Dupliceren**​.

- **Verwijder een regel** door het symbool voor **Verwijderen** te selecteren.

## <a name="specify-custom-match-conditions"></a>Aangepaste overeenkomstvoorwaarden opgeven

U kunt voorwaarden opgeven die bepaalde records altijd moeten overeenkomen of nooit moeten overeenkomen. Deze regels kunnen worden geüpload om het standaardproces voor overeenkomsten te overschrijven. Als in onze administratie bijvoorbeeld een Jan Pieters I en Jan Pieters II voorkomen, kan het systeem ze als één persoon matchen. Met aangepaste matchregels kunt u opgeven dat hun profielen naar verschillende mensen verwijzen. 

1. Ga naar **Gegevens** > **Verenigen** > **Afstemmen** en selecteer **Aangepaste overeenkomst** in de sectie **Details van afgestemde records**.

  :::image type="content" source="media/custom-match-create.png" alt-text="Schermopname van de sectie voor overeenkomstregels met het gemarkeerde besturingselement Aangepaste overeenkomst.":::

1. Als u geen aangepaste overeenkomstregels hebt ingesteld, wordt een nieuw deelvenster **Aangepaste overeenkomst** met meer details weergegeven.

1. Selecteer **De sjabloon invullen** om een sjabloonbestand te krijgen dat kan specificeren welke records uit welke entiteiten altijd of nooit moeten overeenkomen. U moet de 'altijd overeenkomende' records en 'nooit overeenkomende' records afzonderlijk invullen in twee verschillende bestanden.

1. De sjabloon bevat velden om de entiteit en de primaire sleutelwaarden van de entiteit op te geven die in de aangepaste overeenkomst moeten worden gebruikt. Als u bijvoorbeeld wilt dat de primaire sleutel *12345* uit de entiteit *Verkoop* altijd wordt afgestemd met de primaire sleutel *34567* van de entiteit *Contactpersoon*, vult u de sjabloon in:
    - Entiteit1: Verkoop
    - Entity1Key: 12345
    - Entiteit2: Contactpersoon
    - Entity2Key: 34567

   Hetzelfde sjabloonbestand kan aangepaste afstemmingsrecords van meerdere entiteiten specificeren.
   
   Als u aangepaste overeenkomsten voor ontdubbeling op een entiteit wilt opgeven, geeft u dezelfde entiteit op als Entity1 en Entity2 en stelt u de verschillende primaire sleutelwaarden in.

1. Na het toevoegen van alle overschrijvingen die u wilt toepassen, slaat u het sjabloonbestand op.

1. Ga naar **Gegevens** > **Gegevensbronnen** en neem de sjabloonbestanden op als nieuwe entiteiten. Na inname kunt u ze gebruiken om de afstemmingsconfiguratie op te geven.

1. Na het uploaden zijn de bestanden en entiteiten beschikbaar. Selecteer vervolgens de optie **Aangepaste overeenkomst** opnieuw. U ziet opties om de entiteiten op te geven die u wilt opnemen. Selecteer de vereiste entiteiten in het vervolgkeuzemenu.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Schermopname van het dialoogvenster om overschrijvingen te kiezen voor een aangepast afstemmingsscenario.":::

1. Selecteer de entiteiten die u wilt gebruiken voor **Altijd overeenkomen** en **Nooit overeenkomen** en selecteer vervolgens **Gereed**.

1. Selecteer **Opslaan** op de pagina **Afstemming** om de aangepaste afstemmingsconfiguratie toe te passen.

1. Selecteer **Uitvoeren** op de pagina **Afstemming** om het afstemmingsproces te starten. Andere opgegeven overeenkomstregels worden overschreven door de aangepaste overeenkomstconfiguratie.

> [!TIP]
> Ga naar **Gegevens** > **Entiteiten** en bekijk de entiteit **ConflationMatchPair** om te bevestigen dat de overschrijvingen zijn toegepast.

## <a name="next-step"></a>Volgende stap

Na het voltooien van het afstemmingsproces voor ten minste één afstemmingspaar, kunt u mogelijke tegenstrijdigheden in uw gegevens oplossen door het onderwerp [**Samenvoegen**](merge-entities.md) door te nemen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
