---
title: Entiteiten matchen voor gegevensharmonisatie
description: Match entiteiten om geharmoniseerde klantprofielen te maken.
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 05afd17b7f1b34f7f24a8fa8cb2dc32c1649d40f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267472"
---
# <a name="match-entities"></a>Entiteiten toewijzen

Na het voltooien van de toewijzingsfase bent u klaar om uw entiteiten te gaan afstemmen. De afstemmingsfase geeft aan hoe u uw datasets kunt combineren in een geharmoniseerde klantprofielgegevensset. De afstemmingsfase vereist minimaal [twee toegewezen entiteiten](map-entities.md).

## <a name="specify-the-match-order"></a>De afstemmingsvolgorde opgeven

Ga naar **Gegevens** > **Harmoniseren** > **Afstemming** en selecteer **Volgorde instellen** om de afstemmingsfase te starten.

Elke afstemming harmoniseert twee of meer entiteiten tot een enkele , terwijl elke unieke klantrecord wordt behouden. In het volgende voorbeeld hebben we drie entiteiten geselecteerd: **ContactCSV: TestData** als **primaire** entiteit, **WebAccountCSV: TestData** als **Entiteit 2** en **CallRecordSmall: TestData** als **Entiteit 3**. Het diagram boven de selecties illustreert in welke volgorde de afstemming zal plaatsvinden.

> [!div class="mx-imgBorder"]
> ![De volgorde van gegevensafstemming bewerken](media/configure-data-match-order-edit-page.png "De volgorde van gegevensafstemming bewerken")
  
De **primaire** entiteit wordt afgestemd met **Entiteit 2**. De gegevensset die het resultaat is van de eerste afstemming wordt afgestemd met **Entiteit 3**.
In dit voorbeeld hebben we slechts twee afstemmingen geselecteerd, maar het systeem kan er meer ondersteunen.

> [!IMPORTANT]
> De entiteit die u kiest als uw **primaire** entiteit dient als basis voor uw geharmoniseerde hoofdgegevensset. Extra entiteiten die tijdens de afstemmingsfase worden geselecteerd, worden aan deze entiteit toegevoegd. Tegelijkertijd betekent dit niet dat de geharmoniseerde entiteit *alle* gegevens zal bevatten die zijn opgenomen in deze entiteit.
>
> Er zijn twee overwegingen die u kunnen helpen bij het kiezen van de hiërarchie van uw entiteiten:
>
> - Welke entiteit bevat naar uw mening de meest complete en betrouwbare gegevens over uw klanten?
> - Heeft de entiteit die u zojuist hebt geïdentificeerd kenmerken die ook worden gedeeld door andere entiteiten (bijvoorbeeld naam, telefoonnummer of e-mailadres)? Zo niet, kies dan uw op één na meest betrouwbare entiteit.

Selecteer **Gereed** om uw afstemmingsvolgorde op te slaan.

## <a name="define-rules-for-your-first-match-pair"></a>Regels definiëren voor uw eerste afstemmingspaar

Nadat u de afstemmingsvolgorde hebt opgegeven, ziet u de gedefinieerde afstemmingen op de pagina **Afstemming**. De tegels boven aan het scherm zijn leeg totdat u uw afstemmingsvolgorde uitvoert.

> [!div class="mx-imgBorder"]
> ![Regels definiëren](media/configure-data-match-need-rules.png "Regels definiëren")

De waarschuwing **Heeft regels nodig** suggereert dat er geen afstemmingsregel is gedefinieerd voor een afstemmingspaar. Afstemmingsregels specificeren de logica waarmee een specifiek paar entiteiten zal worden afgestemd.

1. U definieert uw eerste regel door het deelvenster **Regeldefinitie** te openen door de overeenkomstige afstemmingsrij in de afstemmingstabel (1) te selecteren en vervolgens **Nieuwe regel maken** (2) te selecteren.

   > [!div class="mx-imgBorder"]
   > ![Nieuwe regel maken](media/configure-data-match-new-rule2.png "Nieuwe regel maken")

2. Configureer in het deelvenster **Regel bewerken** de voorwaarden voor die regel. Elke voorwaarde wordt voorgesteld door twee rijen met verplichte selecties.

   > [!div class="mx-imgBorder"]
   > ![Deelvenster voor nieuwe regel](media/configure-data-match-new-rule-condition.png "Deelvenster voor nieuwe regel")

   Entiteit/veld (eerste) - Een kenmerk dat wordt gebruikt voor het afstemmen van de entiteit van het eerste afstemmingspaar. Voorbeelden hiervan kunnen een telefoonnummer of e-mailadres zijn. Kies een kenmerk dat waarschijnlijk uniek is voor de klant.

   > [!TIP]
   > Vermijd afstemming op basis van kenmerken van het activiteitstype. Met andere woorden, als een kenmerk een activiteit lijkt te zijn, is het mogelijk een slecht criterium voor afstemming.  

   Entiteit/veld (tweede) - Een kenmerk dat wordt gebruikt voor het afstemmen van de entiteit van het tweede afstemmingspaar.

   Normaliseren - **Normalisatiemethode**: er zijn verschillende normalisatieopties beschikbaar voor de geselecteerde kenmerken. Bijvoorbeeld het verwijderen van interpunctie of het verwijderen van spaties

   Voor normalisatie van organisatienaam (preview) kunt u ook **Type (telefoon, naam, organisatie)** selecteren

   > [!div class="mx-imgBorder"]
   > ![Normalisatie-B2B](media/match-normalization-b2b.png "Normalisatie-B2B")

   Precisieniveau - Het precisieniveau dat zal worden gebruikt voor deze voorwaarde. Bij het instellen van een afstemmingsvoorwaarde kunnen er twee typen precisieniveau zijn: **Basis** en **Aangepast**.  
   - Basis: biedt u vier opties om uit te kiezen: Laag, Gemiddeld, Hoog en Exact. Selecteer **Exact** als u alleen records wilt afstemmen die 100 procent overeenkomen. Selecteer een van de andere niveaus om records af te stemmen die niet 100 procent identiek zijn.
   - Aangepast: gebruik de schuifregelaar om het aanpassingspercentage te definiëren dat records moeten afstemmen of typ een waarde in het veld **Aangepast**. Het systeem stemt alleen records af die deze drempel overschrijden als samengevoegde afstemmingsparen. De waarden op de schuifregelaar liggen tussen 0 en 1. Dus 0,64 komt overeen met 64 procent.

3. Selecteer **Gereed** om de regel op te slaan.

### <a name="add-multiple-conditions"></a>Meerdere voorwaarden toevoegen

Als u uw entiteiten alleen wilt afstemmen als aan meerdere voorwaarden is voldaan, voegt u meer voorwaarden toe die zijn gekoppeld via een EN-operator.

1. Selecteer in het deelvenster **Regel bewerken** de optie **Voorwaarde toevoegen**. U kunt voorwaarden ook verwijderen door de verwijderknop naast een bestaande voorwaarde te selecteren.

2. Selecteer **Gereed** om de regel op te slaan.

## <a name="add-multiple-rules"></a>Meerdere regels toevoegen

Elke voorwaarde is van toepassing op een enkel paar kenmerken, terwijl regels reeksen van voorwaarden vertegenwoordigen. Als u uw entiteiten wilt afstemmen via verschillende reeksen kenmerken, kunt u meer regels toevoegen.

1. Ga in doelgroepinzichten naar **Gegevens** > **Unify** > **Matchen**.

2. Selecteer de entiteit die u wilt bijwerken en selecteer **Regels toevoegen**.

3. Volg de procedure zoals beschreven in [Regels voor uw eerste afstemmingspaar definiëren](#define-rules-for-your-first-match-pair).

> [!NOTE]
> De volgorde van de regels is van belang. Het afstemmingsalgoritme probeert af te stemmen op basis van uw eerste regel en gaat pas door naar de tweede regel als er geen overeenkomsten zijn geïdentificeerd volgens de eerste regel.

## <a name="define-deduplication-on-a-match-entity"></a>Ontdubbeling definiëren op een match-entiteit

Naast het specificeren van match-regels voor meerdere entiteiten, zoals beschreven in de bovenstaande secties, kunt u ook ontdubbelingsregels specificeren. *Ontdubbeling* is een proces. Het identificeert dubbele records, voegt ze samen tot één record en koppelt alle bronrecords aan dit samengevoegde record met alternatieve id's aan het samengevoegde record.

Nadat een gededupliceerde record is geïdentificeerd, wordt het gebruikt in het matchingproces in verschillende entiteiten. Ontdubbeling wordt geïmplementeerd op entiteitsniveau en kan worden toegepast op elke entiteit die in het matchproces wordt gebruikt.

### <a name="add-deduplication-rules"></a>Ontdubbelingsregels toevoegen

1. Ga in doelgroepinzichten naar **Gegevens** > **Unify** > **Matchen**.

1. Selecteer in de sectie **Samengevoegde duplicaten** de optie **Entiteiten instellen**.

1. Selecteer in de sectie **Voorkeuren samenvoegen** de entiteiten waarop u ontdubbeling wilt toepassen.

1. Geef aan hoe u de dubbele records wilt samenvoegen en kies een van de drie samenvoegopties:
   - *Meest gevuld*: identificeert het record met de meeste gevulde kenmerken als het winnende record. Dit is de standaard samenvoegingsoptie.
   - *Meest recent*: identificeert het winnende record op basis van recentheid. Vereist een datum of een numeriek veld om de recentheid te definiëren.
   - *Minst recent*: identificeert het winnende record op basis van minst recent zijn. Vereist een datum of een numeriek veld om de recentheid te definiëren.
 
   > [!div class="mx-imgBorder"]
   > ![Ontdubbelingsregels stap 1](media/match-selfconflation.png "Ontdubbelingsregels stap 1")
 
1. Zodra de entiteiten zijn geselecteerd en de voorkeur voor samenvoegen is ingesteld, selecteert u **Nieuwe regel maken** om de ontdubbelingsregels op entiteitsniveau te definiëren.
   - **Veld selecteren** vermeldt alle beschikbare velden van die entiteit waarvan u brongegevens wilt ontdubbelen.
   - Specificeer de normalisatie- en precisie-instellingen op dezelfde manier als in de matching voor meerdere entiteiten.
   - U kunt aanvullende voorwaarden definiëren door **Voorwaarde toevoegen** te selecteren.
 
   > [!div class="mx-imgBorder"]
   > ![Ontdubbelingsregels stap 2](media/match-selfconflation-rules.png "Ontdubbelingsregels stap 2")

  U kunt meerdere ontdubbelingsregels voor een entiteit maken. 

1. Door het matchproces uit te voeren, worden de records nu gegroepeerd op basis van de voorwaarden die zijn gedefinieerd in de ontdubbelingsregels. Nadat de records zijn gegroepeerd, wordt het samenvoegingsbeleid toegepast om het winnende record te identificeren.

1. Deze winnende record wordt vervolgens doorgegeven aan de overeenkomsten zoeken tussen entiteiten, samen met de niet-winnende records (bijvoorbeeld alternatieve id's) om de kwaliteit van de overeenkomst te verbeteren.

1. Alle aangepaste matchregels die zijn gedefinieerd voor 'matchen altijd' en 'matchen nooit' overschrijven ontdubbelingsregels. Als een ontdubbelingsregel overeenkomende records identificeert, en een aangepaste matchregel is ingesteld om nooit te matchen met die records, dan matchen deze twee records niet.

1. Nadat u het matchproces hebt uitgevoerd, ziet u de ontdubbelingsstatistieken.
   
> [!NOTE]
> Het specificeren van ontdubbelingsregels is niet verplicht. Als dergelijke regels niet zijn geconfigureerd, worden de door het systeem gedefinieerde regels toegepast. Ze vouwen alle records die dezelfde waardecombinatie (exacte overeenkomst) hebben vanuit de primaire sleutel en de velden in de matchregels in één record samen voordat ze de entiteitsgegevens doorgeven aan matchen tussen de entiteiten voor verbeterde prestaties en een gezonde systeemstatus.

## <a name="run-your-match-order"></a>Uw afstemmingsvolgorde uitvoeren

Nadat u de matchregels hebt gedefinieerd, inclusief matchen tussen entiteiten en ontdubbelingsregels, kunt u de matchvolgorde uitvoeren. Selecteer op de pagina **Afstemming** de optie **Uitvoeren** om het proces te starten. Het kan enige tijd duren voordat het afstemmingsalgoritme is voltooid. U kunt de eigenschappen op de pagina **Afstemming** pas wijzigen nadat het afstemmingsproces is voltooid. De geharmoniseerde klantprofielentiteit die is gemaakt is te vinden op de pagina **Entiteiten**. Uw geharmoniseerde klantentiteit wordt **ConflationMatchPairs : CustomerInsights** genoemd.

Om aanvullende wijzigingen aan te brengen en de stap opnieuw uit te voeren, kunt u een lopende afstemming annuleren. Selecteer de tekst **Vernieuwen...** en selecteer **Taak annuleren** onder aan het zijvenster dat wordt weergegeven.

Wanneer het afstemmingsproces is voltooid, wordt de tekst **Vernieuwen...** gewijzigd in **Geslaagd** en kunt u alle functionaliteit van de pagina opnieuw gebruiken.

Het eerste afstemmingsproces resulteert in de aanmaak van een geharmoniseerde hoofdentiteit. Alle daaropvolgende afstemmingsruns resulteren in de uitbreiding van die entiteit.

> [!TIP]
> Er zijn [zes soorten status](system.md#status-types) voor taken/processen. Bovendien zijn de meeste processen [afhankelijk van andere stroomafwaartse processen](system.md#refresh-policies). U kunt de status van een proces selecteren om voortgangsdetails te zien van de volledige taak. Na het selecteren van **Details bekijken** voor een van de taken vindt u aanvullende informatie: verwerkingstijd, de laatste verwerkingsdatum en alle fouten en waarschuwingen die bij de taak horen.

## <a name="deduplication-output-as-an-entity"></a>Uitvoer van ontdubbeling als een entiteit
Naast de geharmoniseerde hoofdentiteit die als onderdeel van de vergelijking tussen entiteiten wordt gemaakt, genereert het ontdubbelingsproces ook een nieuwe entiteit voor elke entiteit uit de afgestemde volgorde om de ontdubbelde records te identificeren. Deze entiteiten zijn te vinden samen met de **ConflationMatchPairs:CustomerInsights** in de sectie **Systeem** op de pagina **Entiteiten**, met de naam **Deduplication_Datasource_Entity**.

Een entiteit voor ontdubbelingsuitvoer bevat de volgende informatie:
- Id's/sleutels
  - Het veld Primaire sleutel en het bijbehorende veld Alternatieve id's. Het veld Alternatieve id's bestaat uit alle alternatieve id's die voor een record zijn geïdentificeerd.
  - Het veld Deduplication_GroupId toont de groep of cluster die is geïdentificeerd binnen een entiteit die alle vergelijkbare records groepeert op basis van de opgegeven ontdubbelingsvelden. Dit wordt gebruikt voor systeemverwerkingsdoeleinden. Als er geen handmatige ontdubbelingsregels zijn opgegeven en door het systeem gedefinieerde ontdubbelingsregels van toepassing zijn, is het mogelijk dat u dit veld niet in de uitvoerentiteit voor ontdubbeling vindt.
  - Deduplication_WinnerId: dit veld bevat de winnende id van de geïdentificeerde groepen of clusters. Als de Deduplication_WinnerId hetzelfde is als de primaire sleutelwaarde voor een record, betekent dit dat de record de winnende record is.
- Velden die worden gebruikt om de ontdubbelingsregels te definiëren.
- Regel- en scorevelden om aan te geven welke van de ontdubbelingsregels zijn toegepast en welke score is geretourneerd door het matching-algoritme.

## <a name="review-and-validate-your-matches"></a>Uw afstemmingen controleren en valideren

Evalueer de kwaliteit van uw afstemmingsparen en verfijn deze:

- Op de pagina **Afstemming** vindt u twee tegels met eerste inzichten over uw gegevens.

  - **Unieke klanten**: toont het aantal unieke profielen dat het systeem heeft geïdentificeerd.
  - **Afgestemde records**: toont het aantal afstemmingen voor al uw afstemmingsparen.

- In de tabel **Afstemmingsvolgorde** kunt u de resultaten van elk afstemmingspaar beoordelen door het aantal records dat afkomstig is van deze afstemmingspaarentiteit te vergelijken met het percentage met succes afgestemde records.

- In de sectie **Regels** van een entiteit in de tabel **Afstemmingsvolgorde** vindt u het percentage met succes afgestemde records op regelniveau. Door het tabelsymbool naast een regel te selecteren, kunt u al deze records op regelniveau bekijken. We raden u aan een subset van de records te bekijken om te bepalen of deze correct zijn afgestemd.

- Experimenteer met verschillende precisiedrempels afhankelijk van uw omstandigheden om de optimale waarde te identificeren.

  1. Selecteer de ellips (...) voor de afstemmingspaarregel waarmee u wilt experimenteren en selecteer vervolgens **Bewerken**.

  2. Selecteer de voorwaarde waarmee u wilt experimenteren. Elk criterium wordt weergegeven door één rij in het deelvenster **Afstemmingsregel**.

  3. Wat u zult zien op de pagina **Voorbeeldweergave van criteria** hangt af van het precisieniveau dat u voor een voorwaarde hebt geselecteerd. Zoek het aantal afgestemde en niet-afgestemde records voor de geselecteerde voorwaarde.

     Krijg een rijk inzicht in de effecten van verschillende drempelniveaus. U kunt vergelijken hoeveel records worden afgestemd onder elk van de drempelniveaus en de records bekijken onder elke optie. Selecteer elk van de tegels en bekijk de gegevens in de tabelsectie.

## <a name="optimize-your-matches"></a>Uw afstemmingen optimaliseren

Verhoog de kwaliteit door enkele van uw afstemmingsparameters opnieuw te configureren:

- **Wijzig de afstemmingsvolgorde** door **Bewerken** te selecteren en de velden voor de afstemmingsvolgorde te wijzigen.

  > [!div class="mx-imgBorder"]
  > ![Volgorde van gegevensafstemming bewerken](media/configure-data-match-order-edit.png "Volgorde van gegevensafstemming bewerken")

- **Wijzig de volgorde van uw regels** als u meerdere regels hebt gedefinieerd. U kunt de afstemmingsregels opnieuw rangschikken door de opties **Omhoog** en **Omlaag** te selecteren in het raster voor afstemmingsregels.

  > [!div class="mx-imgBorder"]
  > ![Regelvolgorde wijzigen](media/configure-data-change-rule-order.png "Regelvolgorde wijzigen")

- **Dupliceer uw regels** als u een afstemmingsregel hebt gedefinieerd en een soortgelijke regel met wijzigingen wilt maken. Doe dit door **Dupliceren** te selecteren.

  > [!div class="mx-imgBorder"]
  > ![Een regel dupliceren](media/configure-data-duplicate-rule.png "Een regel dupliceren")

- **Een regel deactiveren** om een overeenkomstregel te behouden en deze uit te sluiten van het vergelijkingsproces.

  > [!div class="mx-imgBorder"]
  > ![Een regel deactiveren](media/configure-data-deactivate-rule.png "Een regel deactiveren")

- **Bewerk uw regels** door het symbool **Bewerken** te selecteren. U kunt de volgende wijzigingen aanbrengen:

  - Kenmerken wijzigen voor een voorwaarde: selecteer nieuwe kenmerken in de specifieke voorwaarderij.
  - De drempel voor een voorwaarde wijzigen: pas de schuifregelaar voor precisie aan.
  - De normalisatiemethode voor een voorwaarde wijzigen: werk de normalisatiemethode bij.

## <a name="specify-your-custom-match-records"></a>Uw aangepaste afstemmingsrecords opgeven

U kunt voorwaarden opgeven die bepaalde records altijd moeten overeenkomen of nooit moeten overeenkomen. Deze regels kunnen in bulk worden geüpload naar het afstemmingsproces.

1. Selecteer de optie **Aangepaste overeenkomst** op het scherm **Afstemmingsvolgorde**.

   > [!div class="mx-imgBorder"]
   > ![Een aangepaste afstemming maken](media/custom-match-create.png "Een aangepaste afstemming maken")

2. Als u geen geüploade entiteiten hebt, ziet u een nieuw dialoogvenster **Aangepaste overeenkomst** waarin u enkele details moet invullen. Als u deze gegevens eerder hebt opgegeven, gaat u verder met stap 8.

   > [!div class="mx-imgBorder"]
   > ![Nieuw dialoogvenster voor aangepaste overeenkomsten](media/custom-match-new-dialog-box.png "Nieuw dialoogvenster voor aangepaste overeenkomsten")

3. Selecteer **De sjabloon invullen** om een sjabloonbestand te krijgen dat kan specificeren welke records uit welke entiteiten altijd of nooit moeten overeenkomen. U moet de 'altijd overeenkomende' records en 'nooit overeenkomende' records afzonderlijk invullen in twee verschillende bestanden.

4. De sjabloon bevat velden om de entiteit en de primaire sleutelwaarden van de entiteit op te geven die in de aangepaste overeenkomst moeten worden gebruikt. Als u bijvoorbeeld wilt dat de primaire sleutel 12345 van de entiteit Verkoop altijd overeenkomt met de primaire sleutel 34567 van de entiteit Contactpersoon, moet u het volgende opgeven:
    - Entiteit1: Verkoop
    - Entity1Key: 12345
    - Entiteit2: Contactpersoon
    - Entity2Key: 34567

   Hetzelfde sjabloonbestand kan aangepaste afstemmingsrecords van meerdere entiteiten specificeren.
   
   Als u aangepaste overeenkomsten voor ontdubbeling op een entiteit wilt opgeven, geeft u dezelfde entiteit op als Entity1 en Entity2 en stelt u de verschillende primaire sleutelwaarden in.

5. Na het toevoegen van alle overschrijvingen die u wilt toepassen, slaat u het sjabloonbestand op.

6. Ga naar **Gegevens** > **Gegevensbronnen** en neem de sjabloonbestanden op als nieuwe entiteiten. Na inname kunt u ze gebruiken om de afstemmingsconfiguratie op te geven.

7. Na het uploaden zijn de bestanden en entiteiten beschikbaar. Selecteer vervolgens de optie **Aangepaste overeenkomst** opnieuw. U ziet opties om de entiteiten op te geven die u wilt opnemen. Selecteer de vereiste entiteiten uit de vervolgkeuzelijst.

   > [!div class="mx-imgBorder"]
   > ![Overschrijvingen van aangepaste overeenkomsten](media/custom-match-overrides.png "Overschrijvingen van aangepaste overeenkomsten")

8. Selecteer de entiteiten die u wilt gebruiken voor **Altijd overeenkomen** en **Nooit overeenkomen** en selecteer vervolgens **Gereed**.

9. Selecteer **Opslaan** op de pagina **Afstemming** voor de aangepaste afstemmingsconfiguratie die u zojuist hebt ingesteld.

10. Selecteer **Uitvoeren** op de pagina **Afstemming** om het afstemmingsproces te starten en de aangepaste afstemmingsconfiguratie van kracht te laten worden. Regels die door het systeem zijn afgestemd worden overschreven door de configuratieset.

11. Zodra het afstemmen is voltooid, kunt u de entiteit **ConflationMatchPair** verifiëren om te bevestigen dat de overschrijvingen worden toegepast in de samenvoegingsovereenkomsten.

## <a name="next-step"></a>Volgende stap

Na het voltooien van het afstemmingsproces voor ten minste één afstemmingspaar, kunt u mogelijke tegenstrijdigheden in uw gegevens oplossen door het onderwerp [**Samenvoegen**](merge-entities.md) door te nemen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]