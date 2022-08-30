---
title: Bronvelden selecteren voor gegevensharmonisatie
description: De eerste stap in het harmonisatieproces is het selecteren van entiteiten, kenmerken, primaire sleutels en semantische typen om gegevens toe te wijzen aan het geharmoniseerde klantprofiel.
recommendations: false
ms.date: 08/12/2022
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
ms.openlocfilehash: bc120aa7a3713e1184ff278edf0942925faafa12
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304559"
---
# <a name="select-source-fields-for-data-unification"></a>Bronvelden selecteren voor gegevensharmonisatie

De eerste stap bij harmonisatie is het selecteren van de entiteiten en velden binnen uw gegevenssets die u wilt harmoniseren. Selecteer entiteiten die klantgerelateerde details bevatten, zoals naam, adres, telefoonnummer en e-mailadres. U kunt een of meerdere entiteiten selecteren.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="select-entities-and-fields"></a>Entiteiten en velden selecteren

1. Ga naar **Gegevens** > **Harmoniseren**.

   Voor individuele klanten (B2C) wordt op de landingspagina **Harmoniseren** de optie **Aan de slag** weergegeven bij de eerste stap, **Bronvelden**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Schermopname van landingspagina Harmoniseren voor ervaring bij eerste uitvoering voor individuele klanten.":::

   Voor zakelijke accounts (B2B) wordt op de landingspagina **Harmoniseren** de optie **Accounts samenvoegen** weergegeven met **Aan de slag** bij de eerste stap, **Bronvelden**. De stappen voor **Contactpersonen samenvoegen (preview)** zijn optioneel en in afwachting van voltooiing van de accountharmonisatie.

   :::image type="content" source="media/b2b_unify_land.png" alt-text="Schermopname van landingspagina Harmoniseren voor ervaring bij eerste uitvoering voor zakelijke.":::

1. Selecteer **Aan de slag**.

1. Op de pagina **Bronvelden** selecteert u **Entiteiten en velden selecteren**. Het deelvenster **Entiteiten en velden selecteren** wordt weergegeven.

1. Selecteer ten minste één entiteit.

1. Identificeer voor elke geselecteerde entiteit de velden die u wilt gebruiken om klantenrecords en velden te matchen die u in het geharmoniseerde profiel wilt opnemen. Deze velden heten *Kenmerken*. U kunt de vereiste kenmerken van een entiteit één voor één selecteren of alle kenmerken van een entiteit opnemen door het selectievakje op entiteitsniveau in te schakelen. U kunt zoeken op trefwoorden in alle kenmerken en entiteiten om de vereiste kenmerken te selecteren die u wilt toewijzen.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Schermopname van geselecteerde entiteiten en kenmerken.":::

   In dit voorbeeld voegen we de entiteiten **eCommerceContacts** en **loyCustomer** toe. Door deze entiteiten te kiezen, kunt u inzicht krijgen in welke van de online zakelijke klanten leden van het loyaliteitsprogramma zijn.

1. Selecteer **Toepassen** om uw selecties te bevestigen. De geselecteerde entiteiten en kenmerken worden weergegeven.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>De primaire sleutel en het semantische type voor kenmerken selecteren

   :::image type="content" source="media/m3_select_primary.png" alt-text="Schermopname van geselecteerde entiteiten met primaire sleutel nog niet geselecteerd." lightbox="media/m3_select_primary.png":::

Voer voor elke entiteit de volgende stappen uit.

1. Kies de **primaire sleutel**. De primaire sleutel is een kenmerk dat uniek is voor de entiteit. Als een kenmerk een geldige primaire sleutel is, mag het geen dubbele waarden, ontbrekende waarden of null-waarden bevatten. Kenmerken van het gegevenstype string, integer en GUID worden ondersteund als primaire sleutels.

1. Om AI-modellen voor slimme voorspelling van semantiek te gebruiken waarmee tijd wordt bespaard en de nauwkeurigheid wordt verbeterd, is **Intelligente toewijzing** ingeschakeld. Intelligente toewijzing biedt op AI gebaseerde semantische aanbevelingen in het veld **Type**.

1. Kies voor elk kenmerk een semantisch **type** dat het kenmerk het beste beschrijft, zoals naam, plaats of e-mailadres.

   > [!NOTE]
   > Bij B2C moet één veld worden toegewezen aan het semantische type *Person.FullName* om de naam van de klant op de klantenkaart in te vullen. In B2B moet de accountnaam worden toegewezen aan *Organization.Name*. Anders verschijnen de klantenkaarten zonder naam.

   1. U kunt ook een andere optie selecteren om het kenmerktype negeren te dat door het systeem is geïdentificeerd. Als het type niet bestaat, maakt u een aangepast semantisch type door het veld **Type** te selecteren voor het kenmerk en een naam voor uw eigen semantische type in te voeren.

   1. Als u een kenmerk met een URL wilt toevoegen aan openbaar beschikbare profielafbeeldingen of logo's, selecteert u de entiteit en het veld dat de URL bevat. Voer het volgende in het veld **Type** in:
      - Voor een persoon: Person.ProfileImage
      - Voor een organisatie: Organization.LogoImage

1. Bekijk de kenmerken waar een semantisch type automatisch wordt geïdentificeerd. Deze kenmerken staan vermeld onder **Toegewezen velden bekijken**. Alleen kenmerken van hetzelfde type kunnen worden gecombineerd in de stap **Klantvelden harmoniseren**. Semantische typen worden gebruikt om automatisch inzichten voor te stellen. Zorg ervoor dat de typen die u kiest overeenkomen in alle geselecteerde entiteiten.

1. Voor kenmerken die niet automatisch worden toegewezen aan een semantisch type, selecteert u een veld voor het semantische type, voert u de naam van uw aangepaste kenmerktype in of laat u ze zonder toewijzing. Deze kenmerken staan vermeld onder **De gegevens in de niet-toegewezen velden definiëren**.

1. Nadat u de stappen voor elke entiteit hebt uitgevoerd, selecteert u **Bronvelden opslaan**.

1. Selecteer **Volgende**.

> [!div class="nextstepaction"]
> [Volgende stap: Duplicaten verwijderen](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
