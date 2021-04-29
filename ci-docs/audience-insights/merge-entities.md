---
title: Entiteiten samenvoegen in gegevensharmonisatie
description: Voeg entiteiten samen om geharmoniseerde klantprofielen te maken.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4ad06a0baf57e612fc0e0214dfd23d28e7d2b6be
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896505"
---
# <a name="merge-entities"></a>Entiteiten samenvoegen

De samenvoegingsfase is de laatste fase in het proces voor gegevensharmonisatie. Het doel is het afstemmen van conflicterende gegevens. Voorbeelden van conflicterende gegevens kunnen een klantnaam zijn die in twee van uw gegevenssets is gevonden, maar in elk een beetje anders verschijnt ("Grant Marshall" versus "Grant Marshal"), of een telefoonnummer met een andere indeling(617-803-091X versus 617803091X). Het samenvoegen van die conflicterende gegevenspunten gebeurt op een kenmerk-per-kenmerkbasis.

Na het voltooien van de [afstemmingsfase](match-entities.md), kunt u de samenvoegingsfase starten door de tegel **Samenvoegen** te selecteren op de pagina **Harmoniseren**.

## <a name="review-system-recommendations"></a>Systeemaanbevelingen bekijken

Op de pagina **Samenvoegen** kunt u kenmerken kiezen en uitsluiten die moeten worden samengevoegd binnen uw geharmoniseerde klantprofielentiteit (het resultaat van het configuratieproces). Sommige kenmerken worden automatisch door het systeem samengevoegd.

### <a name="view-merged-attributes"></a>Samengevoegde kenmerken bekijken

Selecteer het samengevoegde kenmerk om de kenmerken te bekijken die zijn opgenomen in een van uw automatisch samengevoegde kenmerken. De twee kenmerken waaruit dat samengevoegde kenmerk is samengesteld, verschijnen in twee nieuwe rijen onder het samengevoegde kenmerk.

> [!div class="mx-imgBorder"]
> ![Samengevoegd kenmerk selecteren](media/configure-data-merge-profile-attributes.png "Samengevoegd kenmerk selecteren")

### <a name="separate-merged-attributes"></a>Aparte samengevoegde kenmerken

Als u een van de automatisch samengevoegde kenmerken wilt scheiden of de samenvoeging ongedaan wilt maken, zoekt u het kenmerk in de tabel **Profielkenmerken**.

1. Selecteer de knop met de drie puntjes (…).
  
2. Selecteer **Afzonderlijke velden** in de vervolgkeuzelijst.

### <a name="remove-merged-attributes"></a>Samengevoegde kenmerken verwijderen

Als u een kenmerk wilt uitsluiten van de uiteindelijke klantprofielentiteit, kunt u deze vinden in de tabel **Profielkenmerken**.

1. Selecteer de knop met de drie puntjes (…).
  
2. Selecteer **Niet samenvoegen** in de vervolgkeuzelijst.

   Het kenmerk wordt verplaatst naar de sectie **Verwijderd uit klantenrecord**.

## <a name="manually-add-a-merged-attribute"></a>Handmatig een samengevoegd kenmerk toevoegen

Ga naar de pagina **Samenvoegen** om een samengevoegd kenmerk toe te voegen .

1. Selecteer **Samengevoegd kenmerk toevoegen**.

2. Geef een **naam** op om het later te kunnen identificeren op de pagina **Samenvoegen**.

3. Geef desgewenst een **weergavenaam** op die verschijnt in de geharmoniseerde entiteit Klantprofiel.

4. Configureeer **Dubbele kenmerken selecteren** om de kenmerken te selecteren die u wilt samenvoegen uit de afgestemde entiteiten. U kunt ook naar kenmerken zoeken.

5. Stel de optie **Rangschikken op basis van belang** in om het ene kenmerk een hogere prioriteit te geven dan de andere. Als bijvoorbeeld de entiteit *WebAccountCSV* de meest nauwkeurige gegevens over het kenmerk *Volledige namen* bevat, kunt u deze entiteit prioriteit geven boven *ContactCSV* door *WebAccountCSV* te selecteren. Het resultaat is dat *WebAccountCSV* de hoogste prioriteit krijgt, terwijl *ContactCSV* de tweede prioriteit krijgt bij het ophalen van waarden voor het kenmerk *Volledige naam*.

## <a name="run-your-merge"></a>Uw samenvoeging uitvoeren

Of u kenmerken handmatig samenvoegt of deze laat samenvoegen door het systeem, u kunt altijd uw samenvoeging uitvoeren. Selecteer **Uitvoeren** op de pagina **Samenvoegen** om het proces te starten.

> [!div class="mx-imgBorder"]
> ![Samenvoegen van gegevens opslaan en uitvoeren](media/configure-data-merge-save-run.png "Samenvoegen van gegevens opslaan en uitvoeren")

Om aanvullende wijzigingen aan te brengen en de stap opnieuw uit te voeren, kunt u een lopende samenvoeging annuleren. Selecteer **Vernieuwen...** en selecteer **Taak annuleren** in het zijvenster dat wordt weergegeven.

Nadat de tekst **Vernieuwen...** is gewijzigd in **Geslaagd**, is de samenvoeging voltooid en zijn tegenstrijdigheden in uw gegevens opgelost volgens het door u gedefinieerde beleid. Samengevoegde en niet-samengevoegde kenmerken worden opgenomen in de geharmoniseerde profielentiteit. Uitgesloten kenmerken worden niet opgenomen in de geharmoniseerde profielentiteit.

Als het niet de eerste keer was dat u met succes een samenvoeging hebt uitgevoerd, worden alle stroomafwaartse processen, inclusief verrijking, segmentatie en meetcriteria, automatisch opnieuw uitgevoerd. Nadat alle stroomafwaartse processen opnieuw zijn uitgevoerd, weerspiegelen de klantprofielen alle wijzigingen die u hebt aangebracht.

> [!TIP]
> Er zijn [zes soorten status](system.md#status-types) voor taken/processen. Bovendien zijn de meeste processen [afhankelijk van andere stroomafwaartse processen](system.md#refresh-policies). U kunt de status van een proces selecteren om voortgangsdetails te zien van de volledige taak. Na het selecteren van **Details bekijken** voor een van de taken vindt u aanvullende informatie: verwerkingstijd, de laatste verwerkingsdatum en alle fouten en waarschuwingen die bij de taak horen.

## <a name="next-step"></a>Volgende stap

Configureer [activiteiten](activities.md), [verrijking](enrichment-hub.md) of [relaties](relationships.md) voor meer inzichten over uw klanten.

Als u al activiteiten, verrijking of relaties hebt geconfigureerd of segmenten hebt gedefinieerd, worden deze automatisch verwerkt om de nieuwste klantgegevens te gebruiken.




[!INCLUDE[footer-include](../includes/footer-banner.md)]