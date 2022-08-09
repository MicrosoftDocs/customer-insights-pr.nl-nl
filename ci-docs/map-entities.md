---
title: Bronvelden selecteren voor gegevensharmonisatie
description: De eerste stap in het harmonisatieproces is het selecteren van entiteiten, kenmerken, primaire sleutels en semantische typen om gegevens toe te wijzen aan het geharmoniseerde klantprofiel.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: a75218c996b277e00924f2b7b38ea686a1f4dc38
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139776"
---
# <a name="select-source-fields-for-data-unification"></a>Bronvelden selecteren voor gegevensharmonisatie

De eerste stap bij harmonisatie is het selecteren van de entiteiten en velden binnen uw gegevenssets die u wilt harmoniseren. Selecteer entiteiten die klantgerelateerde details bevatten, zoals naam, adres, telefoonnummer en e-mailadres. U kunt een of meerdere entiteiten selecteren.

## <a name="select-entities-and-fields"></a>Entiteiten en velden selecteren

1. Ga naar **Gegevens** > **Harmoniseren**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Schermopname van Unify-landingspagina voor ervaring van eerste uitvoering met Aan de slag gemarkeerd.":::

1. Selecteer **Aan de slag**.

1. Op de pagina **Bronvelden** selecteert u **Entiteiten en velden selecteren**. Het deelvenster **Entiteiten en velden selecteren** wordt weergegeven.

1. Selecteer ten minste één entiteit.

1. Identificeer voor elke geselecteerde entiteit de velden die u wilt gebruiken om klantenrecords en velden te matchen die u in het geharmoniseerde profiel wilt opnemen. Deze velden heten *Kenmerken*. U kunt de vereiste kenmerken van een entiteit één voor één selecteren of alle kenmerken van een entiteit opnemen door het selectievakje op entiteitsniveau in te schakelen. U kunt zoeken op trefwoorden in alle kenmerken en entiteiten om de vereiste kenmerken te selecteren die u wilt toewijzen.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Schermopname van geselecteerde entiteiten en kenmerken.":::

   In dit voorbeeld voegen we de entiteiten **Contacts** en **CustomerLoyalty** toe. Door deze entiteiten te kiezen, kunt u inzicht krijgen in welke van de online zakelijke klanten leden van het loyaliteitsprogramma zijn.

1. Selecteer **Toepassen** om uw selecties te bevestigen. De geselecteerde entiteiten en kenmerken worden weergegeven.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>De primaire sleutel en het semantische type voor kenmerken selecteren

   :::image type="content" source="media/m3_select_primary.png" alt-text="Schermopname van geselecteerde entiteiten met primaire sleutel niet geselecteerd." lightbox="media/m3_select_primary.png":::

Voer voor elke entiteit de volgende stappen uit.

1. Kies de **primaire sleutel**. De primaire sleutel is een kenmerk dat uniek is voor de entiteit. Als een kenmerk een geldige primaire sleutel is, mag het geen dubbele waarden, ontbrekende waarden of null-waarden bevatten. Kenmerken van het gegevenstype string, integer en GUID worden ondersteund als primaire sleutels.

1. Om AI-modellen voor slimme voorspelling van semantiek te gebruiken, tijd te besparen en de nauwkeurigheid te verbeteren, is **Intelligente toewijzing** ingeschakeld. Met Intelligente toewijzing markeert u op AI gebaseerde semantische aanbevelingen in het veld **Type**. U kunt de voorgestelde selectie overschrijven door een semantisch type te kiezen uit de beschikbare lijst met opties.

1. Kies voor elk kenmerk een semantisch **type** dat het kenmerk het beste beschrijft, zoals naam, plaats of e-mailadres.

   > [!NOTE]
   > Eén veld moet worden toegewezen aan het semantische type *Person.FullName* om de naam van de klant in de klantenkaart in te vullen. Anders verschijnen de klantenkaarten zonder naam.

   1. U kunt ook een ander type selecteren om een kenmerktype te wijzigen dat automatisch door het systeem is geïdentificeerd. Als het type niet bestaat, maak dan een aangepast semantisch type door het veld **Type** te selecteren voor het kenmerk en een naam voor uw eigen semantische type in te voeren.

   1. Als u een kenmerk met een URL wilt toevoegen aan openbaar beschikbare profielafbeeldingen of logo's, selecteert u de entiteit en het veld dat de URL bevat. Voer het volgende in het veld **Type** in:
      - Voor een persoon: Person.ProfileImage
      - Voor een organisatie: Organization.LogoImage

   1. Voer voor een accountnaamkenmerk "Organization.Name" in het veld **Type** in.

1. Bekijk de kenmerken waar een semantisch type automatisch wordt geïdentificeerd. Deze kenmerken staan vermeld onder **Toegewezen velden bekijken**. Alleen kenmerken van hetzelfde type kunnen worden gecombineerd in de stap **Geharmoniseerde klantvelden**. Semantische typen worden gebruikt om automatisch inzichten voor te stellen. Zorg ervoor dat de typen die u kiest overeenkomen in alle geselecteerde entiteiten.

1. Voor kenmerken die niet automatisch worden toegewezen aan een semantisch type, selecteert u een veld voor het semantische type, voert u de naam van uw aangepaste kenmerktype in of laat u ze niet toegewezen. Deze kenmerken staan vermeld onder **De gegevens in de niet-toegewezen velden definiëren**.

1. Nadat u de stappen voor elke entiteit hebt uitgevoerd, selecteert u **Bronvelden opslaan**.

1. Selecteer **Volgende**.

> [!div class="nextstepaction"]
> [Volgende stap: Duplicaten verwijderen](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
