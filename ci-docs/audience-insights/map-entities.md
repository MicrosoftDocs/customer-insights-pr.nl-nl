---
title: Entiteiten en kenmerken toewijzen voor gegevensharmonisering
description: Selecteer entiteiten, kenmerken, primaire sleutels en semantische typen om gegevens toe te wijzen aan het geharmoniseerde klantprofiel.
ms.date: 10/18/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-map
ms.openlocfilehash: 7ee3feea8423f35f32ff471b3ed8eb3447584089
ms.sourcegitcommit: 37182127b93b90846cc91fbeb26dd7a18cf5610a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/18/2021
ms.locfileid: "7648156"
---
# <a name="map-entities-and-attributes"></a>Entiteiten en attributen toewijzen

**Toewijzen** is de eerste fase in het gegevensharmonisatieproces van doelgroepinzichten. Toewijzing bestaat uit drie fasen:

- *Entiteitsselectie*: identificeer de combineerbare entiteiten die leiden tot een gegevensset met meer volledige informatie over uw klanten.
- *Kenmerkselectie:* identificeer voor elke entiteit de kolommen die u wilt combineren en op elkaar afstemmen in de fasen voor *afstemmen* en *samenvoegen*. Deze kolommen worden *Kenmerken* genoemd.
- *Selectie van primaire sleutel en semantisch type*: identificeer voor elke entiteit een kenmerk dat u wilt definiëren als de primaire sleutel voor die entiteit en identificeer voor elk kenmerk een semantisch type dat dit kenmerk het beste beschrijft.

Zie [Harmoniseren](data-unification.md) voor meer informatie over de algemene stroom van gegevensharmonisatie.

## <a name="select-the-first-entities"></a>De eerste entiteiten selecteren

1. Ga in doelgroepinzichten naar **Gegevens** > **Unify** > **Toewijzen**.

2. Start de toewijzingsfase door **Entiteiten selecteren** te selecteren.

3. Selecteer de entiteiten en kenmerken die u wilt gebruiken in de fasen voor *afstemmen* en *samenvoegen*. U kunt de vereiste kenmerken van een entiteit afzonderlijk selecteren of alle kenmerken van een entiteit opnemen door het selectievakje **Alle velden opnemen** in te schakelen op entiteitsniveau. We raden u aan ten minste twee entiteiten te selecteren om te profiteren van het proces voor gegevensharmonisatie.

   > [!div class="mx-imgBorder"]
   > ![Voorbeeld van toevoegen van entiteiten.](media/data-manager-configure-map-add-entities-example.png "Voorbeeld van toevoegen van entiteiten")

   In dit voorbeeld voegen we de entiteiten **eCommerceContacten** en **loyCustomers** toe. Door deze entiteiten te kiezen, kunt u inzicht krijgen in welke van de online zakelijke klanten leden van het loyaliteitsprogramma zijn.
   
   U kunt zoeken op trefwoorden in alle kenmerken en entiteiten om de vereiste kenmerken te selecteren die u wilt toewijzen.
   
     > [!div class="mx-imgBorder"]
   > ![Voorbeeld van zoekvelden.](media/data-manager-configure-map-search-fields-example.png "Voorbeeld van zoekvelden")

4. Selecteer **Toepassen** om uw selecties te bevestigen.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>De primaire sleutel en het semantische type voor kenmerken selecteren

Nadat u uw entiteiten hebt geselecteerd, bevat de pagina **Toewijzen** de geselecteerde entiteiten voor uw beoordeling. Definieer de primaire sleutel voor een entiteit en identificeer het semantische type voor een kenmerk in de entiteit.

- **Primaire sleutel**: selecteer één kenmerk als primaire sleutel voor elk van uw entiteiten. Als een kenmerk een geldige primaire sleutel is, mag het geen dubbele waarden, ontbrekende waarden of null-waarden bevatten. Kenmerken van het gegevenstype tekenreeks, geheel getal en GUID worden ondersteund als primaire sleutels en worden weergegeven in een veld waaruit u kunt kiezen.

- **Semantische type van kenmerk**: categorieën van uw kenmerken, zoals e-mailadres of naam. Als u AI-modellen wilt gebruiken voor slimme voorspelling van semantiek, tijdsbesparing en verbeterde nauwkeurigheid, zet u **Intelligente toewijzing** op **AAN**. Met Intelligente toewijzing markeert u op AI gebaseerde semantische aanbevelingen in het veld **Type**. Als u dit instelt op **UIT**, ziet u onze normale aanbevelingen voor toewijzingen. U kunt elk semantisch type uit de beschikbare lijst met opties selecteren en de voorgestelde selectie negeren.

> [!div class="mx-imgBorder"]
> ![Kenmerktype en semantische voorspelling.](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Kenmerktype en semantische voorspelling")

Het toevoegen van een aangepast semantisch type is eveneens mogelijk. Selecteer het type veld voor een kenmerk en typ de aangepaste naam van het semantische type. Zo kunt u ook de kenmerktypen wijzigen die door het systeem zijn geïdentificeerd.

Alle kenmerken waarvoor een semantisch type automatisch wordt geïdentificeerd, worden gegroepeerd in de sectie **Toegewezen velden beoordelen**. Bekijk deze kenmerken en hun semantische typen, want ze zullen worden gebruikt om uw entiteiten te combineren in de samenvoegstap van gegevensharmonisering.

Kenmerken die niet automatisch worden toegewezen aan een semantisch type, worden gegroepeerd in de sectie **De gegevens in de niet-toegewezen velden definiëren**. Selecteer het semantische typeveld voor de niet-toegewezen kenmerken of voer uw aangepaste naam voor het kenmerktype in.

> [!div class="mx-imgBorder"]
> ![Primaire sleutel en kenmerktype.](media/data-manager-configure-map-add-attributes.png "Primaire sleutel en kenmerktype")

> [!NOTE]
> Eén veld moet worden toegewezen aan het semantische type Person.FullName om de klantnaam in de klantenkaart te vullen. Anders verschijnen de klantenkaarten zonder naam. 

## <a name="add-and-remove-attributes-and-entities"></a>Kenmerken en entiteiten toevoegen en verwijderen

1. Selecteer in **Harmoniseren** > **Toewijzen** de optie **Velden bewerken**.

2. Voeg in het deelvenster **Velden bewerken** kenmerken en entiteiten toe of verwijder deze. Gebruik de zoekopdracht of schuif om de kenmerken en entiteiten waarin u bent interessante te zoeken en te selecteren. U kunt een kenmerk of entiteit niet verwijderen als deze al zijn afgestemd.

   > [!div class="mx-imgBorder"]
   > ![Kenmerken toevoegen of verwijderen.](media/configure-data-map-edit.png "Kenmerken toevoegen of verwijderen")

3. Selecteer **Toepassen**.

## <a name="add-images-to-profiles"></a>Afbeeldingen toevoegen aan profielen

Als een entiteit URL's bevat naar openbaar beschikbare profielafbeeldingen of logo's, kunt u deze toevoegen aan het geharmoniseerde klantprofiel.

Selecteer de entiteit en zoek het veld dat de URL naar de profielafbeelding bevat. Voer in het invoerveld **Type** handmatig de volgende waarde in: 
- Voor een persoon: Person.ProfileImage
- Voor een organisatie: Organization.LogoImage

Ga verder met de harmoniseringsstappen en zorg ervoor dat het kenmerk dat de afbeeldings-URL bevat ook wordt toegevoegd aan de stap [Samenvoegen](merge-entities.md).

## <a name="set-attributes-for-organizations"></a>Kenmerken instellen voor organisaties

Voor organisaties (preview) moet het kenmerktype worden toegewezen aan 'Organization.Name'
> [!div class="mx-imgBorder"]
> ![Primaire sleutel en kenmerktype B2B](media/configure-data-map-edit-b2b.png "Primaire sleutel en kenmerktype B2B")

## <a name="next-step"></a>Volgende stap

Als onderdeel van het proces voor gegevensharmonisatie gaat u naar de pagina **Afstemmen**. Bezoek [**Afstemmen**](match-entities.md) voor meer informatie over deze fase.

> [!TIP]
> Bekijk de volgende video: [Aan de slag: Een geharmoniseerd klantprofiel maken](https://youtu.be/oBfGEhucAxs).


[!INCLUDE[footer-include](../includes/footer-banner.md)]