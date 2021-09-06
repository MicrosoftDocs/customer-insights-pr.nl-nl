---
title: Segmenten maken en beheren
description: Maak segmenten van klanten om deze te groeperen op basis van verschillende kenmerken.
ms.date: 07/18/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e759872643cc7387cf732d73c7a320ae8901e5a9
ms.sourcegitcommit: 42692a815695b9fdc93b9358eae09f2c3e97293c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/13/2021
ms.locfileid: "7377782"
---
# <a name="create-and-manage-segments"></a>Segmenten maken en beheren

> [!IMPORTANT]
> Er worden in september 2021 verschillende veranderingen doorgevoerd in de ervaring met het maken van segmenten: 
> - De opbouwfunctie voor segmenten ziet er anders uit met opnieuw vormgegeven elementen en een verbeterde gebruikersstroom.
> - Nieuwe datum-/tijdoperators en een verbeterde datumkiezen zijn ingeschakeld in de opbouwfunctie voor segmenten.
> - U kunt voorwaarden en regels toevoegen of verwijderen uit segmenten. 
> - Geneste regels die beginnen met een OR-voorwaarde worden beschikbaar. U hebt geen AND-voorwaarde meer nodig bij de bovenste laag.
> - Er is continue een zijpaneel beschikbaar om kenmerken te selecteren.
> - Een optie om entiteitsrelatiepaden te selecteren.
> Als u de nieuwe segmenten-bouwer wilt uitproberen, stuurt u een e-mail met als onderwerp "Verzoek om de nieuwe segmenten-bouwer in te schakelen" naar cihelp [at] microsoft.com. Vermeld de naam van uw organisatie en de id van uw sandbox-omgeving.
> :::image type="content" source="media/segment-builder-overview.png" alt-text="Elementen van de segmentbouwer." lightbox="media/segment-builder-overview.png":::
>
> 1 - Organiseer uw segment met regels en subregels. Elke regel of subregel bestaat uit voorwaarden. Combineer de voorwaarden met logische operators
>
> 2 - Kies het [relatiepad](relationships.md) tussen entiteiten die van toepassing zijn op een regel. Het relatiepad bepaalt welke kenmerken in een voorwaarde kunnen worden gebruikt.
>
> 3 - Beheer regels en subregels. Wijzig de positie van een regel of verwijder deze.
>
> 4 - Voeg voorwaarden toe en bouw het juiste niveau van nesting met behulp van subregels.
>
> 5 - Pas setbewerkingen toe op verbonden regels.
>
> 6 - Gebruik het kenmerkdeelvenster om beschikbare entiteitskenmerken toe te voegen of om voorwaarden te creëren op basis van kenmerken. Het deelvenster toont de lijst met entiteiten en kenmerken, gebaseerd op het geselecteerde relatiepad, die beschikbaar zijn voor de geselecteerde regel.
>
> 7 - Voeg voorwaarden toe aan bestaande regels en subregels op basis van kenmerken of voeg deze toe aan een nieuwe regel.
>
> 8 - Maak wijzigingen ongedaan en voer ze opnieuw uit tijdens het bouwen van het segment.

Definieer complexe filters rond de uniforme klantentiteit en de bijhorende gerelateerde entiteiten. Elk segment maakt na verwerking een set klantrecords die u kunt exporteren en waarop u actie kunt ondernemen. Segmenten worden beheerd op de pagina **Segmenten**. 

Het volgende voorbeeld illustreert de segmentatiemogelijkheid. We hebben een segment gedefinieerd voor klanten die in de afgelopen 90 dagen voor ten minste $ 500 aan goederen hebben besteld *en* die betrokken waren bij een klantenserviceoproep die werd geëscaleerd.

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Schermopname van de gebruikersinterface van de segmentbouwer met twee groepen waarmee een klantsegment wordt opgegeven.":::

## <a name="create-a-new-segment"></a>Een nieuw segment maken

Er zijn meerdere manieren om een nieuw segment te maken. In dit gedeelte wordt beschreven hoe u een geheel *leeg segment* maakt. U kunt ook een *snel segment* maken op basis van bestaande entiteiten of gebruikmaken van Machine Learning-modellen om *voorgestelde segmenten* te krijgen. Meer informatie: [Overzicht segmenten](segments.md)

Terwijl u een segment maakt, kunt u een concept opslaan. Het wordt opgeslagen als een inactief segment en kan niet worden geactiveerd als het is voltooid met een geldige configuratie.

1. Ga naar de pagina **Segmenten**.

1. Selecteer **Nieuw** > **Leeg segment**.

1. Kies een segmenttype in het deelvenster **Nieuw segment**:

   - **Dynamische segmenten** [vernieuwen](segments.md#refresh-segments) in een terugkerende planning.
   - **Statische segmenten** eenmaal uitvoeren wanneer u ze maakt.

1. Geef een **Naam van uitvoerentiteit** voor het segment op. Geef optioneel een weergavenaam op en een beschrijving die helpt bij het identificeren van het segment.

1. Selecteer **Volgende** om naar de pagina **Segmentbouwer** te gaan waar u een groep definieert. Een groep is een set klanten.

1. Kies de entiteit die het kenmerk bevat waarop u wilt segmenteren.

1. Kies het kenmerk waarop u wilt segmenteren. Dit kenmerk kan een van de volgende vier waardetypen hebben: numeriek, tekenreeks, datum of booleaans.

1. Kies een operator en een waarde voor het geselecteerde kenmerk.

   > [!div class="mx-imgBorder"]
   > ![Aangepast groepsfilter.](media/customer-group-numbers.png "Klantgroepsfilter")

   |Aantal |Definitie  |
   |---------|---------|
   |1     |Entity          |
   |2     |Kenmerk          |
   |3    |Operator         |
   |4    |Weergegeven als         |

   1. Als u meer voorwaarden aan een groep wilt toevoegen, kunt u twee logische operators gebruiken:

      - **EN**-operator: er moet aan beide voorwaarden worden voldaan als onderdeel van het segmentatieproces. Deze optie is vooral handig wanneer u voorwaarden definieert voor verschillende entiteiten.

      - **OF**-operator: er moet aan een van beide voorwaarden worden voldaan als onderdeel van het segmentatieproces. Deze optie is vooral handig wanneer u meerdere voorwaarden definieert voor dezelfde entiteit.

      > [!div class="mx-imgBorder"]
      > ![OF-operator waarbij aan een van beide voorwaarden moet worden voldaan.](media/segmentation-either-condition.png "OF-operator waarbij aan een van beide voorwaarden moet worden voldaan")

      Het is momenteel mogelijk om een **OF**-operator te nesten onder een **EN**-operator, maar niet andersom.

   1. Elke groep komt overeen met een reeks klanten. U kunt groepen combineren om de klanten op te nemen die nodig zijn voor uw businesscase.    
   Selecteer **Groep toevoegen**.

      > [!div class="mx-imgBorder"]
      > ![Klantengroep - Groep toevoegen.](media/customer-group-add-group.png "Klantengroep - Groep toevoegen")

   1. Selecteer een van de set-operators: **Samenvoegen**, **Doorsnede** of **Uitsluiten**.

   > [!div class="mx-imgBorder"]
   > ![Klantengroep - Verbinding toevoegen.](media/customer-group-union.png "Klantengroep - Verbinding toevoegen")

   - **Verbinding** verbindt de twee groepen.

   - **Overlappen** overlapt de twee groepen. Alleen gegevens die *gemeenschappelijk* zijn voor beide groepen, worden behouden in de geharmoniseerde groep.

   - **Behalve** combineert de twee groepen. Alleen gegevens in groep A die *niet gemeenschappelijk* zijn voor gegevens in groep B, worden behouden.

1. Als de entiteit via [relaties](relationships.md) met de geharmoniseerde klantentiteit is verbonden, moet u het relatiepad definiëren om een geldig segment te maken. Voeg de entiteiten uit het relatiepad toe totdat u de entiteit **Klant : CustomerInsights** in de vervolgkeuzelijst kunt selecteren. Kies dan **Alle records** voor elke stap.

   > [!div class="mx-imgBorder"]
   > ![Relatiepad tijdens het maken van segmenten.](media/segments-multiple-relationships.png "Relatiepad tijdens het maken van segmenten")

1. Segmenten genereren standaard een uitvoerentiteit die alle kenmerken van klantprofielen bevat die overeenkomen met de gedefinieerde filters. Als een segment is gebaseerd op andere entiteiten dan de entiteit *Klant*, kunt u meer attributen van deze entiteiten aan de uitvoerentiteit toevoegen. Selecteer **Projectkernmerken** om de kenmerken te kiezen die aan de uitvoerentiteit worden toegevoegd.  
  
   Voorbeeld: een segment is gebaseerd op een entiteit die gegevens over klantactiviteit bevat die gerelateerd zijn aan de entiteit *Klant*. Het segment zoekt naar alle klanten die de helpdesk de afgelopen 60 dagen hebben gebeld. U kunt ervoor kiezen om de gespreksduur en het aantal gesprekken toe te voegen aan alle overeenkomende klantrecords in de uitvoerentiteit. Deze gegevens kunnen handig zijn om een e-mail met handige koppelingen naar Help-artikelen en FAQ's te sturen naar klanten die vaak hebben gebeld.

   > [!NOTE]
   > - Geprojecteerde kenmerken werken alleen voor entiteiten die een een-op-veel-relatie hebben met de klantentiteit. Eén klant kan bijvoorbeeld meerdere abonnementen hebben.
   > - U kunt alleen kenmerken projecteren van een entiteit die wordt gebruikt in elke groep segmentquery's die u aan het bouwen bent.
   > - Bij het gebruik van set-operators wordt rekening gehouden met geprojecteerde kenmerken.

1. Selecteer **Opslaan** om uw segment op te slaan. Uw segment wordt opgeslagen en verwerkt als alle vereisten zijn gevalideerd. Anders wordt het opgeslagen als concept.

1. Selecteer **Terug naar segmenten** om terug te gaan naar de pagina **Segmenten**.



## <a name="quick-segments"></a>Snelle segmenten

Met snelle segmenten kunt u snel eenvoudige segmenten bouwen met één operator voor snellere inzichten.

1. Selecteer op de pagina **Segmenten** de optie **Nieuw** > **Maken van**.

   - Selecteer de optie **Profielen** om een segment te bouwen dat is gebaseerd op de entiteit *geharmoniseerde klant*.
   - Selecteer de optie **Meetcriteria** om een segment te bouwen rond meetcriteria die u eerder hebt gemaakt.
   - Selecteer de optie **Intelligentie** om een segment op te bouwen rond een van de uitvoerentiteiten die u hebt gegenereerd met behulp van de mogelijkheden **Voorspellingen** of **Aangepaste modellen**.

2. Selecteer in het dialoogvenster **Nieuw snel segment** een kenmerk uit de vervolgkeuzelijst **Veld**.

3. Het systeem biedt enkele aanvullende inzichten waarmee u betere segmenten van uw klanten kunt maken.
   - Voor categorievelden geven we tien topposities van klanten weer. Kies een **Waarde** en selecteer **Evalueren**.

   - Voor een numeriek kenmerk laat het systeem zien welke kenmerkwaarde onder het percentiel van elke klant valt. Kies een **Operator** en een **Waarde** en selecteer vervolgens **Evalueren**.

4. Het systeem zal u van een **Geschatte segmentgrootte** voorzien. U kunt kiezen of u het door u gedefinieerde segment wilt genereren of het eerst opnieuw wilt bezoeken om een andere segmentgrootte te krijgen.

    > [!div class="mx-imgBorder"]
    > ![Naam en schatting voor een snel segment.](media/quick-segment-name.png "Naam en schatting voor een snel segment")

5. Geef een **Naam** op voor uw segment. Voer desgewenst een **Weergavenaam** in.

6. Selecteer **Opslaan** om uw segment te maken.

7. Nadat de verwerking van segment is voltooid, kunt u het bekijken zoals elk ander segment dat u hebt gemaakt.

## <a name="next-steps"></a>Volgende stappen

[Exporteer een segment](export-destinations.md) en verken de [Klantenkaartintegratie](customer-card-add-in.md) om segmenten in andere toepassingen te gebruiken.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
