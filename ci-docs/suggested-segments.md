---
title: Voorgestelde segmenten op basis van metingen (preview)
description: Laat Machine Learning u helpen nieuwe en interessante segmenten te vinden op basis van klantkenmerken.
ms.date: 10/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: e3f504827029afa12c65ec6f065a62606aaa823f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170951"
---
# <a name="suggested-segments-based-on-measures-preview"></a>Voorgestelde segmenten op basis van metingen (preview)

Ontdek interessante segmenten van uw klanten met behulp van een AI-model. Deze door Machine Learning aangedreven functie suggereert segmenten op basis van metingen of klantkenmerken. Het kan u helpen uw KPI's (Key Performance Indicators) te verbeteren of de invloed van kenmerken in de context van andere kenmerken beter te begrijpen.

> [!NOTE]
> De functie voor voorgestelde segmenten gebruikt geautomatiseerde middelen om gegevens te evalueren en voorspellingen te doen op basis van die gegevens. Daarom kan het worden gebruikt als een methode voor profilering, zoals die term is gedefinieerd door de Algemene Verordening Gegevensbescherming ("AVG"). Uw gebruik van deze functie om gegevens te verwerken, kan onderhevig zijn aan de AVG of andere wet- of regelgeving. U bent ervoor verantwoordelijk dat uw gebruik van Dynamics 365 Customer Insights, inclusief deze functie, voldoet aan alle toepasselijke wet- en regelgeving, inclusief wetten met betrekking tot privacy, persoonsgegevens, biometrische gegevens, gegevensbescherming en vertrouwelijkheid van communicatie.

:::image type="content" source="media/suggested-segments.png" alt-text="Pagina met voorgestelde segmenten met details van een suggestie in een zijvenster.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Voorgestelde segmenten om uw KPI's te verbeteren

Als u gebruikmaakt van [metingen die zijn gemaakt](measures.md) om uw KPI's te volgen, maakt u segmenten om de invloeden op de KPI te bekijken. U kunt deze informatie gebruiken om een zeer gerichte campagne te voeren.

U volgt bijvoorbeeld een meting met de naam *TotalSpendPerCustomer*​. Als bedrijf zou u dit aantal graag zien groeien. Door een meting als primair kenmerk te kiezen, kunt u de kenmerken selecteren die u op invloed wilt beoordelen. Laten we zeggen *lidmaatschapsniveau*, *lidmaatschapsperiode* en *bezetting*​. Customer Insights kan dan een segment voorstellen dat u vertelt wie de grootste invloed heeft op die meting. Bijvoorbeeld *Accountants* die *Gouden* leden zijn en die *minstens vijf jaar* klant bij u zijn, hebben de grootste invloed op *TotalSpendPerCustomer*. U krijgt voor elke suggestie een geschatte segmentgrootte. U kunt deze informatie gebruiken om campagnes te maken voor de beoogde doelgroepen.

## <a name="understand-what-influences-a-customer-attribute"></a>Begrijpen wat van invloed is op een klantkenmerk

U kunt een klantkenmerk kiezen in plaats van een meting als het primaire kenmerk. Op basis van uw keuze van beïnvloedende kenmerken, maakt het AI-model een reeks suggesties die laten zien hoe de geselecteerde kenmerken het primaire kenmerk beïnvloeden.

U kiest bijvoorbeeld *Bonuslid (ja/n nee)* als het primaire kenmerk. *Dienstverband*, *Beroep* en *Aantal ondersteuningstickets* zijn ook ingesteld als beïnvloedende kenmerken. Het AI-model zou segmenten kunnen suggereren die aangeven dat voornamelijk IT-professionals met een dienstverband van meer dan twee jaar bonusleden zijn. Een andere suggestie zou kunnen benadrukken dat accountants met een dienstverband van meer dan een jaar en minder dan drie ondersteuningstickets bonusleden zijn.

## <a name="artificial-intelligence-usage"></a>Gebruik van kunstmatige intelligentie

Door gebruik te maken van het primaire kenmerk en de beïnvloedende kenmerken, suggereert een beslisboom-algoritme interessante segmenten. De suggesties zijn gebaseerd op regels of patronen die zijn opgepikt door het AI-algoritme. Alleen segmenten die significant verschillen van de gemiddelde populatie worden als suggestie getoond. De vergelijking met de gemiddelde populatie is gebaseerd op de geselecteerde meting of het primaire kenmerk.

### <a name="responsible-ai"></a>Verantwoordelijke AI

Met voorgestelde segmenten kunt u kenmerken selecteren om nieuwe segmenten te maken en de door u geselecteerde gegevens te verwerken. Bij het kiezen van kenmerken, inclusief gevoelige kenmerken als ras, seksuele geaardheid of gender, moet u ervoor zorgen dat u die gegevens kunt en moet verwerken. U bent verantwoordelijk om alle wetten na te leven die van toepassing zijn op uw organisatie en om u te houden aan de principes en het privacybeleid van uw organisatie.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Verschillende resultaten voor primaire kenmerken met categorische en numerieke waarden

Segmentsuggesties zijn anders als u een numeriek kenmerk of een categorisch kenmerk als primair kenmerk kiest. Waarden in een categorisch kenmerk bevatten twee of meer categorieën of typen. Een numeriek kenmerk bevat kwantitatieve gegevens en er is een gevoel van meting aan verbonden.

Met een numeriek kenmerk als *jaarinkomen* of *lidmaatschapsperiode* als primair kenmerk stelt het systeem segmenten voor die een hogere of lagere gemiddelde waarde van het numerieke kenmerk hebben in vergelijking met alle klanten.

Een categorisch kenmerk als *klanttevredenheid* omdat het primaire kenmerk resulteert in voorgestelde segmenten met een hoger of lager percentage klanten die tot een bepaalde categorie behoren in vergelijking met het percentage van alle klanten die tot dezelfde categorie behoren. Bijvoorbeeld *klanttevredenheid* is gekozen als het primaire kenmerk en bestaat uit drie categorieën (*Laag*, *Gemiddeld* en *Hoog*). Voor elke categorie worden segmenten voorgesteld die een hoger of lager percentage klanten hebben die tot die categorie behoren in vergelijking met het aandeel van alle klanten in dezelfde categorie. Als 22% van alle klanten een *hoge* tevredenheid hebben, worden alleen segmenten met een hoger of lager aandeel van klanten met een *hoge* tevredenheid in vergelijking met 22% voorgesteld voor die categorie. Evenzo worden segmenten voorgesteld voor elk van de andere categorieën (*Laag* en *Gemiddeld*) als ze statistisch significant zijn.

> [!NOTE]
> Momenteel ondersteunen we alleen primaire categorische kenmerken met maximaal 10 categorieën. Als u segmentsuggesties wilt zien op basis van een primair kenmerk met meer dan 10 categorieën, raden we u aan enkele categorieën te groeperen om het aantal categorieën terug te brengen tot 10 of minder. Deze beperking is alleen van toepassing op primaire kenmerken. Voor het beïnvloeden van categorische kenmerken ondersteunen we momenteel maximaal 100 categorieën.

## <a name="generate-suggested-segments"></a>Voorgestelde segmenten genereren

1. Ga naar **Segmenten** en selecteer het tabblad **Suggesties (preview)**.

1. Selecteer **Nieuwe suggesties zoeken** en kies **Een meting/metrisch gegeven verbeteren**. Selecteer **Starten**.

   :::image type="content" source="media/suggested-segments-measure.png" alt-text="Ervoor kiezen een meting te verbeteren voor de voorgestelde segmenten.":::

1. Kies een meting of een klantkenmerk als primair kenmerk en selecteer **Volgende**.

1. Selecteer de beïnvloedende kenmerken en selecteer **Uitvoeren**.

   > [!TIP]
   > Door meerdere beïnvloedende kenmerken te selecteren, vergroot u de kans om te evalueren hoe ze het primaire kenmerk beïnvloeden. Neem geen kenmerken op die geen invloed hebben op het primaire kenmerk. Als al uw klanten bijvoorbeeld uit een bepaald land komen, neemt u het kenmerk *land* niet op, omdat het geen invloed heeft op de uitvoer.

Afhankelijk van het aantal klantprofielen en geselecteerde kenmerken, kan het enkele minuten duren om de geselecteerde kenmerken te verwerken.

## <a name="manage-suggested-segments"></a>Voorgestelde segmenten beheren

Ga naar **Segmenten** en selecteer het tabblad **Suggesties (preview)**. Selecteer in de sectie **Op kenmerken gebaseerde segmentsuggesties** een voorgesteld segment om beschikbare acties te bekijken.

- **Bekijk** de segmentdetails en de kenmerkwaarden of regels die het AI-model heeft geleerd.
- **Sla de suggestie op als een segment** opslaan. Het wordt weergegeven op het tabblad **Alle segmenten** en kan worden [vernieuwd, bewerkt of verwijderd](segments.md).
- **Bewerk kenmerken** en wijzig de geconfigureerde kenmerken die de huidige suggesties vervangen.
- Selecteer **Suggesties vernieuwen** om de suggesties te vernieuwen en tegelijkertijd de geconfigureerde kenmerken te behouden.

## <a name="limitations"></a>Beperkingen

1. Geschatte segmentgrootte komt niet overeen: als u een primair kenmerk kiest dat lege waarden bevat, kan dit van invloed zijn op de geschatte segmentgrootte in de segmentsuggesties. Wanneer een dergelijk segment wordt opgeslagen, kan de werkelijke segmentgrootte verschillen van de oorspronkelijke schatting.

2. Primaire kenmerken van het Booleaanse type werken niet: momenteel ondersteunen we alleen tekenreeksen en numerieke gegevenstypen als het primaire kenmerk.

3. Voorgestelde segmenten zijn niet duidelijk genoeg: houd er rekening mee dat de geselecteerde kenmerken en de verdeling van waarden van die kenmerken de resultaten beïnvloeden. U kunt uw beïnvloedende kenmerken of zelfs uw primaire kenmerk wijzigen om andere resultaten te krijgen.

[!INCLUDE [footer-include](includes/footer-banner.md)]