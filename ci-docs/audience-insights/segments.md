---
title: Segmenten maken en beheren
description: Maak segmenten van klanten om deze te groeperen op basis van verschillende kenmerken.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597045"
---
# <a name="create-and-manage-segments"></a>Segmenten maken en beheren

Met segmenten kunt u uw klanten groeperen op basis van demografische, transactionele of gedragskenmerken. U kunt segmenten gebruiken om promotiecampagnes, verkoopactiviteiten en acties voor klantenondersteuning te targeten om uw zakelijke doelstellingen te bereiken.

U kunt complexe filters definiëren rondom de entiteit Klantprofiel en de bijbehorende entiteiten. Elk segment maakt na verwerking een set klantrecords die u kunt exporteren en waarop u actie kunt ondernemen. Er zijn enkele [servicelimieten](service-limits.md) van toepassing.

Tenzij anders vermeld, zijn alle segmenten **Dynamische segmenten**, die worden vernieuwd volgens een terugkerend schema.

Het volgende voorbeeld illustreert de segmentatiemogelijkheid. We hebben een segment gedefinieerd voor klanten die in de afgelopen 90 dagen voor ten minste $ 500 aan goederen hebben besteld *en* die betrokken waren bij een klantenserviceoproep die werd geëscaleerd.

> [!div class="mx-imgBorder"]
> ![Meerdere groepen](media/segmentation-group1-2.png "Meerdere groepen")

## <a name="create-a-new-segment"></a>Een nieuw segment maken

Segmenten worden beheerd op de pagina **Segmenten**.

1. Ga in doelgroepinzichten naar de pagina **Segmenten**.

1. Selecteer **Nieuw** > **Leeg segment**.

1. Kies in het deelvenster **Nieuw segment** een segmenttype en geef een **Naam** op.

   Geef optioneel een weergavenaam op en een beschrijving die helpt bij het identificeren van het segment.

1. Selecteer **Volgende** om naar de pagina **Segmentbouwer** te gaan waar u een groep definieert. Een groep is een set klanten.

1. Kies de entiteit die het kenmerk bevat waarop u wilt segmenteren.

1. Kies het kenmerk waarop u wilt segmenteren. Dit kenmerk kan een van de volgende vier waardetypen hebben: numeriek, tekenreeks, datum of booleaans.

1. Kies een operator en een waarde voor het geselecteerde kenmerk.

   > [!div class="mx-imgBorder"]
   > ![Aangepast groepsfilter](media/customer-group-numbers.png "Klantgroepsfilter")

   |Getal |Definitie  |
   |---------|---------|
   |1     |Entity          |
   |2     |Kenmerk          |
   |3    |Operator         |
   |4    |waarde         |

8. Als de entiteit via [relaties](relationships.md) met de geharmoniseerde klantentiteit is verbonden, moet u het relatiepad definiëren om een geldig segment te maken. Voeg de entiteiten uit het relatiepad toe totdat u de entiteit **Klant : CustomerInsights** in de vervolgkeuzelijst kunt selecteren. Kies vervolgens **Alle records** voor elke conditie.

   > [!div class="mx-imgBorder"]
   > ![Relatiepad tijdens het maken van segmenten](media/segments-multiple-relationships.png "Relatiepad tijdens het maken van segmenten")

1. Segmenten genereren standaard een uitvoerentiteit die alle kenmerken van klantprofielen bevat die overeenkomen met de gedefinieerde filters. Als een segment is gebaseerd op andere entiteiten dan de entiteit *Klant*, kunt u meer attributen van deze entiteiten aan de uitvoerentiteit toevoegen. Selecteer **Projectkernmerken** om de kenmerken te kiezen die aan de uitvoerentiteit worden toegevoegd.  

   
   Voorbeeld: een segment is gebaseerd op een entiteit die gegevens over klantactiviteit bevat die gerelateerd zijn aan de entiteit *Klant*. Het segment zoekt naar alle klanten die de helpdesk de afgelopen 60 dagen hebben gebeld. U kunt ervoor kiezen om de gespreksduur en het aantal gesprekken toe te voegen aan alle overeenkomende klantrecords in de uitvoerentiteit. Deze gegevens kunnen handig zijn om een e-mail met handige koppelingen naar Help-artikelen en FAQ's te sturen naar klanten die vaak hebben gebeld.

1. Selecteer **Opslaan** om uw segment op te slaan. Uw segment wordt opgeslagen en verwerkt als alle vereisten zijn gevalideerd. Anders wordt het opgeslagen als concept.

1. Selecteer **Terug naar segmenten** om terug te gaan naar de pagina **Segmenten**.

## <a name="manage-existing-segments"></a>Bestaande segmenten beheren

Op de pagina **Segmenten** kunt u al uw opgeslagen segmenten bekijken en beheren.

Elk segment wordt weergegeven door een rij met aanvullende informatie over het segment.

U kunt de segmenten in een kolom sorteren door de kolomkop te selecteren.

Gebruik het vak **Zoeken** in de rechterbovenhoek om de segmenten te filteren.

> [!div class="mx-imgBorder"]
> ![Opties voor het beheren van een bestaand segment](media/segments-selected-segment.png "Opties voor het beheren van een bestaand segment")

De volgende actie is beschikbaar wanneer u een segment selecteert:

- **Bekijk** de segmentdetails, inclusief trend van ledentelling en voorbeeld van segmentleden.
- **Bewerk** het segment om de eigenschappen te wijzigen.
- **Maak een duplicaat** van een segment. U kunt ervoor kiezen om de eigenschappen meteen te bewerken of gewoon het duplicaat op te slaan.
- **Vernieuw** het segment om de nieuwste gegevens op te nemen.
- **Activeer** of **Deactiveer** het segment. Segmenten hebben twee mogelijke statussen: actief of inactief. Deze statussen zijn handig bij het bewerken van een segment. Voor inactieve segmenten bestaat de segmentdefinitie, maar bevat deze nog geen klanten. Wanneer u een segment activeert, verandert de status van 'inactief' in 'actief' en wordt gezocht naar klanten die voldoen aan de segmentdefinitie. Als een [geplande vernieuwing](system.md#schedule-tab) is geconfigureerd, hebben inactieve segmenten de **Status** **Overgeslagen**, wat aangeeft dat er niet eens is geprobeerd te vernieuwen. Wanneer een inactief segment wordt geactiveerd, wordt het vernieuwd en opgenomen in geplande vernieuwingen.
  U kunt ook de functionaliteit **Later plannen** in de vervolgkeuzelisjt **Activeren/Deactiveren** gebruiken om een toekomstige datum en tijd op te geven voor activering en deactivering van een bepaald segment.
- **Wijzig de naam** van het segment.
- **Download** de lijst van leden als .CSV-bestand.
- **Toevoegen aan** verzendt de lijst met klant-id's in het segment voor verwerking in een andere applicatie.
- **Verwijder** het segment.

## <a name="refresh-segments"></a>Segmenten vernieuwen

U kunt alle segmenten tegelijk vernieuwen door **Alles vernieuwen** te selecteren op de pagina **Segmenten** of u kunt een of meerdere segmenten vernieuwen wanneer u deze selecteert en **Vernieuwen** uit de opties kiezen. U kunt ook een terugkerende vernieuwing configureren via **Beheerder** > **Systeem** > **Schema**.

> [!TIP]
> Er zijn [zes soorten status](system.md#status-types) voor taken/processen. Bovendien zijn de meeste processen [afhankelijk van andere stroomafwaartse processen](system.md#refresh-policies). U kunt de status van een proces selecteren om voortgangsdetails te zien van de volledige taak. Na het selecteren van **Details bekijken** voor een van de taken vindt u aanvullende informatie: verwerkingstijd, de laatste verwerkingsdatum en alle fouten en waarschuwingen die bij de taak horen.

## <a name="download-and-export-segments"></a>Segmenten downloaden en exporteren

U kunt uw segmenten downloaden naar een CSV-bestand of ze exporteren naar Dynamics 365 Sales.

### <a name="download-segments-to-a-csv-file"></a>Segmenten downloaden naar een CSV-bestand

1. Ga in doelgroepinzichten naar de pagina **Segmenten**.

2. Selecteer het beletselteken in de tegel van een specifiek segment.

3. Selecteer **Downloaden als CSV** in de vervolgkeuzelijst Acties.

### <a name="export-segments-to-dynamics-365-sales"></a>Segmenten exporteren naar Dynamics 365 Sales

Voordat een beheerder segmenten gaat exporteren naar Dynamics 365 Sales, moet deze [de exportbestemming maken](export-destinations.md) voor Dynamics 365 Sales.

1. Ga in doelgroepinzichten naar de pagina **Segmenten**.

2. Selecteer het beletselteken in de tegel van een specifiek segment.

3. Selecteer **Toevoegen aan** in de vervolgkeuzelijst met acties en selecteer de exportbestemming waarnaar u de gegevens wilt verzenden.

## <a name="draft-mode-for-segments"></a>Conceptmodus voor segmenten

Als niet aan alle vereisten voor het verwerken van een segment is voldaan, kunt u het segment als concept opslaan en openen vanaf de pagina **Segmenten**.

Het wordt opgeslagen als een inactief segment en kan niet worden geactiveerd totdat het geldig is.

## <a name="add-more-conditions-to-a-group"></a>Meer voorwaarden toevoegen aan een groep

Als u meer voorwaarden aan een groep wilt toevoegen, kunt u twee logische operators gebruiken:

- **EN**-operator: er moet aan beide voorwaarden worden voldaan als onderdeel van het segmentatieproces. Deze optie is vooral handig wanneer u voorwaarden definieert voor verschillende entiteiten.

- **OF**-operator: er moet aan een van beide voorwaarden worden voldaan als onderdeel van het segmentatieproces. Deze optie is vooral handig wanneer u meerdere voorwaarden definieert voor dezelfde entiteit.

   > [!div class="mx-imgBorder"]
   > ![OF-operator waarbij aan een van beide voorwaarden moet worden voldaan](media/segmentation-either-condition.png "OF-operator waarbij aan een van beide voorwaarden moet worden voldaan")

Het is momenteel mogelijk om een **OF**-operator te nesten onder een **EN**-operator, maar niet andersom.

## <a name="combine-multiple-groups"></a>Meerdere groepen combineren

Elke groep produceert een specifieke set klanten. U kunt deze groepen combineren om de klanten op te nemen die nodig zijn voor uw bedrijfsscenario.

1. Ga in doelgroepinzichten naar de pagina **Segmenten** en selecteer een segment.

2. Selecteer **Groep toevoegen**.

   > [!div class="mx-imgBorder"]
   > ![Klantengroep - Groep toevoegen](media/customer-group-add-group.png "Klantengroep - Groep toevoegen")

3. Selecteer een van de volgende set-operators: **Verbinding**, **Overlappen** of **Behalve**.

   > [!div class="mx-imgBorder"]
   > ![Klantengroep - Verbinding toevoegen](media/customer-group-union.png "Klantengroep - Verbinding toevoegen")

   Selecteer een setoperator om een nieuwe groep te definiëren. Sla verschillende groepen op om te bepalen welke gegevens moeten worden behouden:

   - **Verbinding** verbindt de twee groepen.

   - **Overlappen** overlapt de twee groepen. Alleen gegevens die *gemeenschappelijk* zijn voor beide groepen, worden behouden in de geharmoniseerde groep.

   - **Behalve** combineert de twee groepen. Alleen gegevens in groep A die *niet gemeenschappelijk* zijn voor gegevens in groep B, worden behouden.

## <a name="view-processing-history-and-segment-members"></a>Verwerkingsgeschiedenis en segmentleden weergeven

U kunt geconsolideerde gegevens over een segment bekijken door de details te controleren.

Selecteer op de pagina **Segmenten** het segment dat u wilt controleren.

Het bovenste deel van de pagina bevat een trendgrafiek waarin wijzigingen in het aantal leden worden gevisualiseerd. Beweeg over gegevenspunten om het aantal leden op een specifieke datum te bekijken.

U kunt het tijdsbereik van de visualisatie bijwerken.

> [!div class="mx-imgBorder"]
> ![Tijdsbereik van segment](media/segment-time-range.png "Tijdsbereik van segment")

Het onderste gedeelte bevat een lijst met de segmentleden.

> [!NOTE]
> Velden die in deze lijst worden weergegeven, zijn gebaseerd op de kenmerken van de entiteiten van uw segment.
>
>De lijst is een voorbeeld van de overeenkomende segmentleden en toont de eerste 100 records van uw segment, zodat u het snel kunt evalueren en indien nodig de definities kunt bekijken. Als u alle overeenkomende records wilt bekijken, moet u [het segment exporteren](export-destinations.md).

## <a name="quick-segments"></a>Snelle segmenten

Naast de segment-builder is er nog een ander pad om segmenten te maken. Met snelle segmenten kunt u snel met een enkele operator en met directe inzichten eenvoudige segmenten bouwen.

1. Selecteer op de pagina **Segmenten** de optie **Nieuw** > **Snel maken van**.

   - Selecteer de optie **Profielen** om een segment te bouwen dat is gebaseerd op de geharmoniseerde entiteit Klant.
   - Selecteer de optie **Meetcriteria** om een segment te bouwen rond elk van de typen meetcriteria voor klantkenmerken die u eerder hebt gemaakt op de pagina **Meetcriteria**.
   - Selecteer de optie **Intelligentie** om een segment op te bouwen rond een van de uitvoerentiteiten die u hebt gegenereerd met behulp van de mogelijkheden **Voorspellingen** of **Aangepaste modellen**.

2. Selecteer in het dialoogvenster **Nieuw snel segment** een kenmerk uit de vervolgkeuzelijst **Veld**.

3. Het systeem biedt enkele aanvullende inzichten waarmee u betere segmenten van uw klanten kunt maken.
   - Voor categorievelden geven we tien topposities van klanten weer. Kies een **Waarde** en selecteer **Evalueren**.

   - Voor een numeriek kenmerk laat het systeem zien welke kenmerkwaarde onder het percentiel van elke klant valt. Kies een **Operator** en een **Waarde** en selecteer vervolgens **Evalueren**.

4. Het systeem zal u van een **Geschatte segmentgrootte** voorzien. U kunt kiezen of u het door u gedefinieerde segment wilt genereren of het eerst opnieuw wilt bezoeken om een andere segmentgrootte te krijgen.

    > [!div class="mx-imgBorder"]
    > ![Naam en schatting voor een snel segment](media/quick-segment-name.png "Naam en schatting voor een snel segment")

5. Geef een **Naam** op voor uw segment. Voer desgewenst een **Weergavenaam** in.

6. Selecteer **Opslaan** om uw segment te maken.

7. Nadat de verwerking van segment is voltooid, kunt u het bekijken zoals elk ander segment dat u hebt gemaakt.

Voor de volgende scenario's adviseren wij het gebruik van de segmentbouwer in plaats van de mogelijkheid voor aanbevolen segmenten:

- Segmenten maken met filters voor categorievelden waarbij de operator anders is dan de **Is**-operator
- Segmenten maken met filters voor numerieke velden waarvan de operator anders is dan de operators **Tussen**, **Groter dan** en **Kleiner dan**
- Segmenten maken met filters op datumtypevelden

## <a name="next-steps"></a>Volgende stappen

[Exporteer een segment](export-destinations.md) en verken de [klantenkaart](customer-card-add-in.md) en [connectors](export-power-bi.md) om inzichten op klantniveau te verkrijgen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]