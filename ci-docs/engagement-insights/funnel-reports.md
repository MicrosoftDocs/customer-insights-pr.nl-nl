---
title: Trechterrapporten
description: Trechterrapporten gebruiken om te begrijpen hoe de doelgroep beslissingen neemt.
ms.reviewer: mhart
ms.author: kamacdon
author: kamacdon
ms.date: 09/17/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 901e7ec50037d66c7c5ceb635d1c6cda6cfff83b
ms.sourcegitcommit: 3bafa27adae113948636b30c7462e0af060c7131
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2021
ms.locfileid: "7498636"
---
# <a name="create-and-manage-funnel-reports"></a>Trechterrapporten maken en beheren

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Een trechterrapport verzamelt informatie over de stappen die plaatsvinden tijdens een klantreis via uw website of mobiele app. Het helpt u te begrijpen hoe een doelgroep een proces doorloopt en identificeert afhaakpunten. U kunt bijvoorbeeld een trechterrapport gebruiken om paden te identificeren die uw klanten nemen voordat ze een aankoop doen. Een trechterrapport biedt gegevens om beslissingen te nemen en gebieden voor optimalisatie en procesverbeteringen te identificeren.

## <a name="create-a-funnel-report"></a>Een trechterrapport maken

Om het trechterrapport te maken, specificeert u de stappen die u wilt opnemen en de activiteit voor elke stap. Een activiteit is een [gebeurtenis](glossary.md) die staat voor gebruikersgedrag. Het trechterrapport geeft het aantal gebruikers weer dat elke gedefinieerde stap heeft doorlopen. 

1. Ga naar **Trechters** en selecteer **+Nieuwe trechter** om een trechterrapport te starten.

1. Selecteer in de **Trechter-editor**, onder **Stappen** de optie **+Stap toevoegen**. 

1. Voer een naam in bij **Staptitel**.

   :::image type="content" source="media/new-funnel-report.png" alt-text="Nieuw trechterrapport.":::

1. Selecteer een **Activiteit**. Een activiteit registreert wanneer een gebruiker een pagina bekijkt (activiteit **Weergave**) of interactie heeft met inhoud (activiteit **Actie**).

1. Gebruik **Stapcriteria** om de dimensie van de activiteit te specificeren. [Dimensies](dimensions.md) zijn kenmerken die gegevens kunnen beschrijven, filteren of groeperen.

1. Optioneel kunt u trechterstappen met meerdere voorwaarden configureren. Selecteer **Voorwaarde toevoegen** om meer dimensies in een stap op te geven. Aanvullende criteria moeten hetzelfde activiteitstype gebruiken. U kunt kiezen of meerdere voorwaarden worden gekoppeld aan een EN- of een OF-operator.

   :::image type="content" source="media/funnel-add-condition.png" alt-text="Trechtereditor die de stapconfiguratie toont met stappen met meerdere voorwaarden.":::

1. Selecteer **Stap toevoegen** totdat u alle gewenste stappen in het rapport hebt doorlopen.

1. Selecteer **Opslaan**, geef het rapport een naam en selecteer nogmaals **Opslaan**. 

### <a name="example-fourth-coffee-company-funnel-report"></a>Voorbeeld: trechterrapport bedrijf Fourth Coffee

Het volgende scenario laat zien hoe u een trechterrapport kunt gebruiken. Een analist bij het bedrijf Fourth Coffee wil de invloed van een recente promotie op de abonnementstarieven begrijpen. De analist maakt een trechterrapport om klantactiviteit te identificeren. Het begint wanneer klanten op de startpagina van het bedrijf aankomen totdat ze de promotiecode voor het abonnement gebruiken. De analist maakt een trechterrapport met de volgende stappen:

Stap 1: klanten die op de startpagina terechtkomen   
Stap 2: klanten die een aankoop doen   
Stap 3: klanten die de promotiecode gebruiken om korting te krijgen op een abonnement   
Stap 4: aanmelden voor abonnement   

:::image type="content" source="media/funnel-report-example.png" alt-text="voorbeeld van een trechterrapport.":::
  
In deze trechter kunt u het aantal gebruikers zien dat de promotiecode na een eenmalige aankoop heeft gebruikt om zich aan te melden voor het abonnementsprogramma.

### <a name="configure-advanced-settings"></a>Geavanceerde instellingen configureren 

Met trechterrapporten kunt u een limiet definiëren voor de tijd die nodig is om een trechter te voltooien. U kunt de tijd voor het voltooien van de trechter bijvoorbeeld instellen op vier dagen. Deze instelling telt alleen succesvolle aanmeldingen voor abonnementen die hebben plaatsgevonden binnen vier dagen nadat een gebruiker de startpagina heeft bezocht.

1. Ga naar **Trechters** om de **Trechterbibliotheek** te openen.

1. Selecteer een naam om het rapport te openen. 

1. Ga naar het deelvenster **Trechtereditor** en selecteer **Geavanceerde instellingen**. 

1. Stel Limiet voor voltooiingstijd trechter in op **Aan**.

   :::image type="content" source="media/funnel-limit-time.png" alt-text="Trechtereditor met geavanceerde instellingen en opties om de tijd voor het voltooien van een trechter te beperken.":::

1. Kies het tijdstip waarop de trechter moet zijn voltooid in de vervolgkeuzelijst **Limiet instellen op**.

1. Selecteer **Opslaan** om uw wijzigingen toe te passen.


## <a name="cross-channel-funnel-reports"></a>Trechterrapporten voor meerdere kanalen 

Betrokkenheidsinzichten kunnen ook worden gebruikt om gedragsgegevens van klanten te verzamelen in uw mobiele app. Zodra u uw mobiele app hebt geïnstrumenteerd met de [Android-SDK](get-started-android.md) of [iOS-SDK](get-started-ios.md) voor betrokkenheidsinzichten, kunt u trechterrapporten voor meerdere kanalen maken. 

### <a name="create-a-cross-channel-funnel-report"></a>Eeb trechterrapport voor meerdere kanalen maken 

1. Volg de stappen om [een trechterrapport te maken](#create-a-funnel-report).    

1. U kunt bijhouden hoe uw klanten omgaan met uw merk op zowel uw website als mobiele app, of meerdere websites, door de werkruimtewisselaar te gebruiken om trechterstappen te maken met gegevens uit andere werkruimten. Selecteer in de **Trechtereditor**, onder **Stappen**, uit welke werkruimte de gegevens voor uw trechterstap moeten komen.

## <a name="manage-funnel-reports"></a>Trechterrapporten beheren

U kunt trechterrapporten beoordelen om gegevens te analyseren, prestaties bij te houden en inzichten te verzamelen.

> [!NOTE]
> - Betrokkenheidsinzichten-trechterrapporten ondersteunen momenteel scenario's waarin alle gebruikers in de trechter anoniem zijn of alle gebruikers zijn geverifieerd. 
> - Historische gegevens in trechterrapporten zijn beschikbaar voor de afgelopen 30 dagen.

### <a name="view-funnel-reports"></a>Trechterrapporten weergeven

1. Ga naar **Trechters** om de **Trechterbibliotheek** te openen.
1. Selecteer een naam om het rapport te openen.    

### <a name="see-the-data-collected-for-a-report"></a>Bekijk de verzamelde gegevens voor een rapport   

Informatie over een fase zien

- Wijs een stap in het rapport aan.

:::image type="content" source="media/funnel-step-data.png" alt-text="trechtergegevens.":::

### <a name="change-the-date-range-for-the-funnel-report"></a>Het datumbereik voor het trechterrapport wijzigen

1. Ga naar **Trechters** om de **Trechterbibliotheek** te openen.

1. Selecteer een naam om het rapport te openen.

1. Open het **tijdsbereik** en selecteer een nieuwe tijdsperiode in de lijst of **Vast datumbereik** om een datumbereik op te geven.

## <a name="edit-or-delete-funnel-reports"></a>Trechterrapporten bewerken of verwijderen

U kunt de naam van een trechterrapport wijzigen, verwijderen of de stappen in het rapport wijzigen.

### <a name="rename-or-delete-a-funnel-report"></a>De naam van een trechterrapport wijzigen of het rapport verwijderen

1. Ga naar **Trechters** om de **Trechterbibliotheek** te openen. 

1. Selecteer **Meer** naast het rapport dat u wilt wijzigen en kies **Naam bewerken** of **Verwijderen**.

### <a name="edit-a-funnel-step"></a>Een trechterstap bewerken  

1. Ga naar **Trechters** om de **Trechterbibliotheek** te openen. 

1. Selecteer een naam om het rapport te openen.

1. Selecteer de stap die u wilt bewerken.

1. Selecteer **Bewerken**.

1. Werk in de **Trechter-editor** de informatie bij die u wilt wijzigen.  

1. Selecteer **Opslaan**.

### <a name="reorder-a-funnel-step"></a>De volgorde van een trechterstap wijzigen

1. Ga naar **Trechters** om de **Trechterbibliotheek** te openen. 

1. Selecteer een naam om het rapport te openen.

1. Selecteer de stap waarvan u de volgorde wilt wijzigen.

1. Selecteer **Verplaatsen**, daarna **Omhoog**, **Omlaag**, **Naar boven** of **Naar beneden** om de stap te verplaatsen.

### <a name="delete-a-funnel-step"></a>Een trechterstap verwijderen

1. Ga naar **Trechters** om de **Trechterbibliotheek** te openen. 

1. Selecteer een naam om het rapport te openen.

1. Selecteer de stap die u wilt verwijderen en selecteer **Verwijderen**.

## <a name="funnel-insights"></a>Trechterinzichten 

Betrokkenheidsinzichten bieden nu trechterinzichten voor klanten. Gebruik trechterinzichten om meer inzicht te krijgen in het gedrag van klanten over de stappen in uw trechterrapport. Wanneer u een nieuw trechterrapport maakt en opslaat, worden automatisch trechterinzichten gegenereerd voor uw rapport. 

U kunt trechterinzichten uit de volgende categorieën bekijken, zowel op hoofd- als op stapniveau: 

 - Conversiepercentage 
 - Overgangstijd 
 - Voltooiingstijd 

Gebruik deze inzichten om het gedrag van klanten nog beter te leren kennen en meer inzicht te krijgen in afleverpunten en conversies voor uw trechterrapport. 

Trechterinzichten worden elke 24 uur opnieuw berekend, of wanneer u **Opslaan** kiest in uw trechterrapport. 

> [!NOTE]
> Als u inzichten voor uw trechter wilt bekijken, moet u uw rapport elke keer dat u wijzigingen aanbrengt, opslaan. 

