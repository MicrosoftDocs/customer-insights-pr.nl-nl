---
title: Metingen maken en bewerken
description: Definieer klantgerelateerde meetcriteria om de prestaties van bepaalde bedrijfsgebieden te analyseren en weer te geven.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405508"
---
# <a name="define-and-manage-measures"></a>Meetcriteria definiëren en beheren

**Meetcriteria** vertegenwoordigen key performance indicators (KPI's) die de prestaties en gezondheid van specifieke bedrijfsgebieden weerspiegelen. Doelgroepinzichten bieden een intuïtieve ervaring voor het bouwen van verschillende soorten metingen, met behulp van een querybuilder waarvoor u uw metingen niet handmatig hoeft te coderen of te valideren. U kunt uw zakelijke meetcriteria bijhouden op de pagina **Start**, meetcriteria voor specifieke klanten bekijken op de **Klantkaart** en meetcriteria gebruiken om klantsegmenten op de pagina **Segmenten** te definiëren.

## <a name="create-a-measure"></a>Een meetcriterium maken

In deze sectie wordt u begeleid bij het maken van een geheel nieuw meetcriteria. U kunt meetcriteria samenstellen met gegevens uit meerdere gegevensbronnen die zijn verbonden via de entiteit Klant. Er zijn enkele [servicelimieten](service-limits.md) van toepassing.

1. Ga in doelgroepinzichten naar **Metingen**.

2. Selecteer **Nieuw meetcriterium**.

3. Kies het meetcriteria **Type**:

   - **Klantkenmerk**: een enkel veld per klant dat een score, waarde of status voor de klant aangeeft. Klantkenmerken worden gemaakt als kenmerken in een nieuwe, door het systeem gegenereerde entiteit genaamd **Customer_Measure**.

   - **Meetcriterium klant**: inzichten in klantgedrag met uitsplitsing naar geselecteerde dimensies. Voor elk meetcriterium wordt een nieuwe entiteit gegenereerd, mogelijk met meerdere records per klant.

   - **Zakelijk meetcriterium**: houdt uw bedrijfsprestaties en de gezondheid van het bedrijf bij. Zakelijke meetcriteria kunnen twee verschillende uitvoeren hebben: een numerieke uitvoer die wordt weergegeven op de pagina **Start** of een nieuwe entiteit die u vindt op de pagina **Entiteiten**.

4. Geef een **naam** en een optionele **weergavenaam** op en selecteer daarna **Volgende**.

5. Selecteer in de sectie **Entiteiten** de eerste entiteit in de vervolgkeuzelijst. Op dit punt moet u beslissen of aanvullende entiteiten nodig zijn als onderdeel van de definitie van uw meetcriterium.

   > [!div class="mx-imgBorder"]
   > ![Definitie van meetcriterium](media/measure-definition.png "Definitie van meetcriterium")

   Als u meer entiteiten wilt toevoegen, selecteert u **Entiteit toevoegen** en selecteert u entiteiten die u voor het meetcriterium wilt gebruiken.

   > [!NOTE]
   > U kunt alleen entiteiten selecteren die relaties hebben met uw eerste entiteit. Zie [Relaties](relationships.md) voor meer informatie over het definiëren van relaties.

6. Optioneel kunt u variabelen configureren. Selecteer in de sectie **Variabelen** de optie **Nieuwe variabele**.

   Variabelen zijn berekeningen die worden uitgevoerd op elk van uw geselecteerde records. Bijvoorbeeld het optellen van verkopen via point-of-sale (POS) en online verkopen voor elk van de records van uw klanten.

7. Geef een **naam** op voor de variabele.

8. Kies in het gebied **Expressie** een veld waarmee u uw berekening wilt beginnen.

9. Typ een expressie in het gebied **Expressie** terwijl u meer velden kiest om in uw berekening op te nemen.

   > [!NOTE]
   > Momenteel worden alleen rekenkundige expressies ondersteund. Bovendien wordt variabele berekening niet ondersteund voor entiteiten uit verschillende [entiteitspaden](relationships.md).

10. Selecteer **Gereed**.

11. In de sectie **Definitie van meetcriterium** definieert u hoe uw gekozen entiteiten en berekende variabelen worden geaggregeerd in een nieuwe entiteit Meetcriterium of een nieuw kenmerk Meetcriterium.

12. Selecteer **Nieuwe dimensie**. Een dimensie kan worden beschouwd als een functie *groeperen op*. De gegevensuitvoer van uw entiteit of kenmerk Meetcriterium wordt gegroepeerd op basis van al uw gedefinieerde dimensies.

    > [!div class="mx-imgBorder"]
    > ![Aggregatiecyclus kiezen](media/measures-businessreport-measure-definition2.png "Aggregatiecyclus kiezen")

    Selecteer of voer de volgende informatie in als onderdeel van de definitie van uw dimensie:

    - **Entiteit**: als u een entiteit Meetcriterium definieert, moet dit ten minste één kenmerk bevatten. Als u een kenmerk Meetcriterium definieert, bevat dit standaard slechts één kenmerk. Deze selectie gaat over het kiezen van de entiteit die dat kenmerk bevat.
    - **Veld**: kies het specifieke kenmerk dat u wilt opnemen in uw entiteit of kenmerk Meetcriterium.
    - **Bucket**: kies of u gegevens wilt samenvoegen op dagelijkse, maandelijkse of jaarlijkse basis. Dit is alleen een vereiste selectie als u een kenmerk Datumtype hebt geselecteerd.
    - **Als**: definieert de naam van uw nieuwe veld.
    - **Weergavenaam**: definieert de weergavenaam van uw veld.

    > [!NOTE]
    > Uw zakelijke meetcriterium wordt opgeslagen als een entiteit met één nummer en verschijnt op de pagina **Start** tenzij u meer dimensies toevoegt aan uw meetcriterium. Na het toevoegen van meer dimensies zal het meetcriterium *niet* worden weergegeven op de pagina **Start**.

13. Voeg optioneel aggregatiefuncties toe. Elke aggregatie die u maakt, resulteert in een nieuwe waarde binnen uw entiteit of kenmerk Meetcriterium. Ondersteunde aggregatiefuncties zijn: **Min**, **Max**, **Gemiddelde**, **Mediaan**, **Som**, **Aantal unieke**, **Eerste** (neemt de eerste record van een dimensiewaarde) en **Laatste** (neemt de laatste record die aan een dimensiewaarde is toegevoegd).

14. Selecteer **Opslaan** om uw wijzigingen toe te passen op het meetcriterium.

## <a name="manage-your-measures"></a>Uw meetcriteria beheren

Nadat u ten minste één meting hebt gemaakt, ziet u een lijst met metingen op de pagina **Metingen**.

U vindt informatie over het type meetcriterium, de maker, de aanmaakdatum en -tijd, de datum en tijd van laatste bewerking, de status (of het meetcriterium actief, inactief of mislukt is) en de meest recente vernieuwingsdatum en -tijd. Wanneer u een meetcriterium uit de lijst selecteert, kunt u een voorbeeld van de uitvoer bekijken.

Selecteer om al uw meetcriteria tegelijkertijd te vernieuwen de optie **Alles vernieuwen** zonder een specifiek meetcriterium te selecteren.

> [!div class="mx-imgBorder"]
> ![Acties om afzonderlijke meetcriteria te beheren](media/measure-actions.png "Acties om afzonderlijke meetcriteria te beheren")

U kunt ook een meetcriterium uit de lijst selecteren en een van de volgende acties uitvoeren:

- Selecteer de naam van het meetcriterium om de details te zien.
- **Bewerk** de configuratie van het meetcriterium.
- **Hernoem** het meetcriterium.
- **Verwijder** het meetcriterium.
- Selecteer het beletselteken (...) en vervolgens **Vernieuwen** om het vernieuwingsproces voor het meetcriterium te starten.
- Selecteer het beletselteken (...) en vervolgens **Downloaden** om een .CSV-bestand van het meetcriterium op te halen.

> [!TIP]
> Er zijn [zes soorten status](system.md#status-types) voor taken/processen. Bovendien zijn de meeste processen [afhankelijk van andere stroomafwaartse processen](system.md#refresh-policies). U kunt de status van een proces selecteren om voortgangsdetails te zien van de volledige taak. Na het selecteren van **Details bekijken** voor een van de taken vindt u aanvullende informatie: verwerkingstijd, de laatste verwerkingsdatum en alle fouten en waarschuwingen die bij de taak horen.

## <a name="next-step"></a>Volgende stap

U kunt bestaande meetcriteria gebruiken om uw eerste klantensegment ter maken op de pagina **Segmenten**. Zie [Segmenten](segments.md) voor meer informatie.
