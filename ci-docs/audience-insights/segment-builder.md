---
title: Segmenten maken met behulp van de opbouwfunctie voor segmenten
description: Maak segmenten van klanten om deze te groeperen op basis van verschillende kenmerken.
ms.date: 09/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e089c475234935742fc42fc3f2bada47711305bf
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/11/2021
ms.locfileid: "7622998"
---
# <a name="create-segments"></a>Segmenten maken

Definieer complexe filters rond de uniforme klantentiteit en de bijhorende gerelateerde entiteiten. Elk segment maakt na verwerking een set klantrecords die u kunt exporteren en waarop u actie kunt ondernemen. Segmenten worden beheerd op de pagina **Segmenten**. U kunt [nieuwe segmenten maken](#create-a-new-segment) met de opbouwfunctie voor segmenten of [snel segmenten maken](#quick-segments) vanuit andere delen van de app. 

> [!TIP]
> - Snelle segmenten worden alleen ondersteund in omgevingen voor **individuele klanten**.    
> - Segmenten op basis van **individuele klanten** nemen automatisch beschikbare contactgegevens voor segmentleden op. In omgevingen voor **zakelijke accounts** zijn segmenten gebaseerd op accounts (bedrijven of dochterondernemingen). Om contactgegevens in een segment op te nemen, gebruikt u de functionaliteit **Projectkenmerken** in de segmentbouwer.

## <a name="segment-builder"></a>Opbouwfunctie voor segmenten

In de volgende afbeelding worden de verschillende aspecten van de opbouwfunctie voor segmenten geïllustreerd. Er wordt een segment weergegeven dat resulteert in een groep klanten. De klanten hebben goederen besteld in een specifieke tijdsbestek en ze hebben beloningspunten verzameld of een bepaald bedrag uitgegeven. 

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elementen van de segmentbouwer." lightbox="media/segment-builder-overview.png":::

1. Organiseer uw segment met regels en subregels. Elke regel of subregel bestaat uit voorwaarden. Combineer de voorwaarden met logische operators

1. Kies het [relatiepad](relationships.md) tussen entiteiten die van toepassing zijn op een regel. Het relatiepad bepaalt welke kenmerken in een voorwaarde kunnen worden gebruikt.

1. Beheer regels en subregels. Wijzig de positie van een regel of verwijder deze.

1. Voeg voorwaarden toe en bouw het juiste niveau van nesting met behulp van subregels.

1. Pas setbewerkingen toe op verbonden regels.

1. Gebruik het kenmerkdeelvenster om beschikbare entiteitskenmerken toe te voegen of om voorwaarden te creëren op basis van kenmerken. Het deelvenster toont de lijst met entiteiten en kenmerken, gebaseerd op het geselecteerde relatiepad, die beschikbaar zijn voor de geselecteerde regel.

1. Voeg voorwaarden toe aan bestaande regels en subregels op basis van kenmerken of voeg deze toe aan een nieuwe regel.

1. Maak wijzigingen ongedaan en voer ze opnieuw uit tijdens het bouwen van het segment.

Het bovenstaande voorbeeld illustreert de segmentatiemogelijkheid. We hebben een segment gedefinieerd voor klanten die ten minste voor $ 500 aan goederen online hebben gekocht *en* interesse hebben in softwareontwikkeling.

## <a name="create-a-new-segment"></a>Een nieuw segment maken

Er zijn meerdere manieren om een nieuw segment te maken. In dit gedeelte wordt beschreven hoe u uw eigen segment helemaal opnieuw kunt opbouwen. U kunt ook een *snel segment* maken op basis van bestaande entiteiten of gebruikmaken van Machine Learning-modellen om *voorgestelde segmenten* te krijgen. Ga voor meer informatie naar [Overzicht van segmenten](segments.md).

Terwijl u een segment maakt, kunt u een concept opslaan. In de conceptfase wordt een segment opgeslagen als inactief segment. Wanneer u de segmentconfiguratie hebt voltooid, voert u deze uit om het segment te activeren. U kunt een segment ook ***Activeren** vanuit de pagina *Alle segmenten**.

1. Ga naar de pagina **Segmenten**.

1. Selecteer **Nieuw** > **Bouw uw eigen segment**.

1. Op de pagina voor het samenstellen van segmenten definieert of stelt u regels op. Een regel bestaat uit een of meer voorwaarden die een set klanten definiëren.

1. In de sectie **Regel 1** kiest u een kenmerk van een entiteit waarop u klanten wilt filteren. U kunt op twee manieren kenmerken kiezen: 
   - Bekijk de lijst met beschikbare entiteiten en kenmerken in het deelvenster **Toevoegen aan regel** en selecteer het pictogram **+** naast het kenmerk dat u wilt toevoegen. Kies of u het kenmerk aan een bestaande regel wilt toevoegen of het wilt gebruiken om een nieuwe regel te maken.
   - Typ de naam van het kenmerk in het regelgedeelte om overeenkomende suggesties weer te geven.

1. Kies de operators om de overeenkomende waarden van de voorwaarde op te geven. Kenmerk kan een van de vier gegevenstypen als waarde hebben: numeriek, tekenreeks, datum of booleaans. Afhankelijk van het gegevenstype van het attribuut zijn er verschillende operators beschikbaar om de voorwaarde op te geven. Voor segmenten met zakelijke accounts zijn er twee speciale operators beschikbaar om mogelijke hiërarchieën tussen de opgenomen accounts op te nemen. Met de operators *kind van* en *ouder van* kunt u gerelateerde accounts opnemen. 

1. Selecteer **Voorwaarde toevoegen** om meer voorwaarden aan een regel toe te voegen. Als u een regel onder de huidige regel wilt maken, selecteert u **Subregel toevoegen**.

1. Als een regel andere entiteiten gebruikt dan de entiteit *Klant*, moet u het relatiepad instellen. Het relatiepad is vereist om het systeem te informeren via welke relaties u toegang wilt hebben tot de geharmoniseerde klantentiteit. Selecteer **Relatiepad instellen** om de geselecteerde entiteit toe te wijzen aan de geharmoniseerde klantentiteit. Als er maar één mogelijk relatiepad is, selecteert het systeem automatisch dit pad. Verschillende relatiepaden kunnen verschillende resultaten opleveren. Elke regel kan zijn eigen relatiepad hebben.

   :::image type="content" source="media/relationship-path.png" alt-text="Potentieel relatiepad bij het maken van een regel op basis van een entiteit die is toegewezen aan de geharmoniseerde klantentiteit.":::

   Zo heeft de entiteit *eCommerce_eCommercePurchases* in de schermopname bijvoorbeeld vier opties om de entiteit *Klant* toe te wijzen: 
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Klant
   - eCommerce_eCommercePurchases > Klant
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Klant
   - eCommerce_eCommerceAankopen > eCommerce_eCommerceContacten > POS_posPurchases > loyaltyScheme_loyCustomers > Klant Bij het kiezen van de laatste optie kunnen we kenmerken van alle vermelde entiteiten opnemen in de regelvoorwaarden. We krijgen waarschijnlijk minder resultaten omdat de overeenkomende klantrecords deel moeten uitmaken van alle entiteiten. In dit voorbeeld hebben ze goederen gekocht via e-commerce (*eCommerce_eCommercePurchases*) bij een verkooppunt (*POS_posPurchases*) en nemen ze deel aan ons loyaliteitsprogramma (*loyaltyScheme_loyCustomers*). Bij het kiezen van de tweede optie kunnen we alleen kenmerken kiezen uit de *eCommerce_eCommercePurchases* en de entiteit *Klant*. Dit resulteert waarschijnlijk in meer klantprofielen.

1. Als u meerdere voorwaarden in een regel hebt opgenomen, kunt u kiezen welke logische operator ze verbindt.  
   - **EN**-operator: er moet aan alle voorwaarden worden voldaan om een record in het segment op te nemen. Deze optie is vooral handig wanneer u voorwaarden definieert voor verschillende entiteiten.
   - **OF**-operator: er moet aan een van de voorwaarden worden voldaan om een record in het segment op te nemen. Deze optie is vooral handig wanneer u meerdere voorwaarden definieert voor dezelfde entiteit.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Regel met twee EN-voorwaarden.":::

   Bij gebruik van de OF-operator moeten alle voorwaarden zijn gebaseerd op entiteiten die in het relatiepad zijn opgenomen.

   - U kunt meerdere regels maken om verschillende sets klantrecords te maken. U kunt groepen combineren om de klanten op te nemen die nodig zijn voor uw businesscase. Selecteer **Regel toevoegen** om een nieuwe regel te maken. Als u een entiteit niet in een regel kunt opnemen vanwege het opgegeven relatiepad, moet u een nieuwe regel maken om er kenmerken uit te kiezen.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Voeg een nieuwe regel toe aan een segment en kies de set-operator.":::

   - Selecteer een van de set-operators: **Samenvoegen**, **Doorsnede** of **Uitsluiten**.

      - **Verbinding** verbindt de twee groepen.
      - **Overlappen** overlapt de twee groepen. Alleen gegevens die *gemeenschappelijk* zijn voor beide groepen, worden behouden in de geharmoniseerde groep.
      - **Behalve** combineert de twee groepen. Alleen gegevens in groep A die *niet gemeenschappelijk* zijn voor gegevens in groep B, worden behouden.

1. Segmenten genereren standaard de entiteit voor uitvoer die alle kenmerken bevat van klantprofielen die overeenkomen met de gedefinieerde filters. Als een segment is gebaseerd op andere entiteiten dan de entiteit *Klant*, kunt u meer attributen van deze entiteiten aan de uitvoerentiteit toevoegen. Selecteer **Projectkernmerken** om de kenmerken te kiezen die aan de uitvoerentiteit worden toegevoegd.  

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Voorbeeld van geprojecteerde kenmerken die in het zijvenster zijn geselecteerd om aan de entiteit voor uitvoer toe te voegen.":::
  
   Bijvoorbeeld: een segment is gebaseerd op een entiteit die inkoopgegevens bevat die verband houden met de entiteit *Klant*. Het segment zoekt naar alle klanten uit Spanje die in het lopende jaar goederen hebben gekocht. U kunt ervoor kiezen om kenmerken zoals de prijs van de goederen of de aankoopdatum toe te voegen aan alle overeenkomende klantrecords in de uitvoerentiteit. Deze informatie kan nuttig zijn om seizoenscorrelaties en de totale uitgaven te analyseren.

   > [!NOTE]
   > - **Projectkenmerken** werkt alleen voor entiteiten die een een-op-veel-relatie hebben met de klantentiteit. Eén klant kan bijvoorbeeld meerdere abonnementen hebben.
   > - Als het kenmerk dat u wilt projecteren meer dan één stap verwijderd is van de entiteit *Klant*, zoals gedefinieerd door de relatie, moet dat kenmerk worden gebruikt in elke regel van de segmentquery die u maakt. 
   > - Als het kenmerk dat u wilt projecteren slechts één stap verwijderd is van de entiteit *Klant*, hoeft dat kenmerk niet aanwezig te zijn in elke regel van de segmentquery die u maakt. 
   > - Bij het gebruik van set-operators wordt rekening gehouden met **geprojecteerde kenmerken**.
   > - Voor segmenten die zijn gebaseerd op zakelijke accounts, moeten details van een of meer contacten van elke account worden opgenomen in het segment om toe te staan dat het segment kan worden geactiveerd of geëxporteerd naar bestemmingen waarvoor contactgegevens nodig zijn.

1. Voordat u het segment opslaat en uitvoert, selecteert u **Details bewerken** naast de naam van het segment. Geef een naam op voor uw segment en werk de voorgestelde **Naam van uitvoerentiteit** voor het segment bij. U kunt ook een beschrijving aan het segment toevoegen.

1. Selecteer **Uitvoeren** om het segment op te slaan, activeer het en begin met het verwerken van uw segment op basis van alle regels en voorwaarden. Anders wordt het opgeslagen als een inactief segment.

1. Selecteer **Terug naar segmenten** om terug te gaan naar de pagina **Segmenten**.

> [!TIP]
> - De opbouwfunctie voor segmenten stelt geen geldige waarden van entiteiten voor bij het instellen van de operators voor de voorwaarden. U kunt naar **Gegevens** > **Entiteiten** gaan en de entiteitsgegevens downloaden om te zien welke waarden er beschikbaar zijn.
> - Met voorwaarden op basis van de datums kunt u schakelen tussen vaste datums en een zwevend datumbereik.
> - Als u meerdere regels voor uw segment heeft, heeft de regel die u aan het bewerken bent, een verticale blauwe lijn ernaast. 
> - U kunt regels en voorwaarden naar andere plaatsen in de segmentdefinitie verplaatsen. Selecteer [...] naast een regel of voorwaarde en kies hoe en waarnaartoe u deze wilt verplaatsen.
> - Met de opties **Ongedaan maken** en **Opnieuw** in de opdrachtbalk kunt u wijzigingen ongedaan maken.

## <a name="quick-segments"></a>Snelle segmenten

Met snelle segmenten kunt u snel eenvoudige segmenten bouwen met één operator voor snellere inzichten.

1. Selecteer op de pagina **Segmenten** de optie **Nieuw** > **Maken van**.
   - Selecteer de optie **Profielen** om een segment te bouwen dat is gebaseerd op de entiteit *geharmoniseerde klant*.
   - Selecteer de optie **Meetcriteria** om een segment te bouwen rond meetcriteria die u eerder hebt gemaakt.
   - Selecteer de optie **Intelligentie** om een segment op te bouwen rond een van de uitvoerentiteiten die u hebt gegenereerd met behulp van de mogelijkheden **Voorspellingen** of **Aangepaste modellen**.

2. Selecteer in het dialoogvenster **Nieuw snel segment** een kenmerk uit de vervolgkeuzelijst **Veld**.

3. Het systeem biedt meer inzichten die u helpen om betere segmenten van uw klanten te maken.
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
