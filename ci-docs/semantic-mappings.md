---
title: Semantische toewijzingen (preview)
description: Overzicht van semantische toewijzingen en hoe ze te gebruiken.
ms.date: 12/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 7c9588ac7a132ca6f43cf26ea3a744109a0dd2b8
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183625"
---
# <a name="semantic-mappings-preview"></a>Semantische toewijzingen (preview)

Met semantische toewijzingen kunt u uw niet-activiteitsgegevens toewijzen aan vooraf gedefinieerde schema's. Deze schema's helpen Customer Insights om uw gegevenskenmerken beter te begrijpen. Semantische toewijzing en de verstrekte gegevens maken nieuwe inzichten en functies mogelijk in Customer Insights. Voor informatie over het koppelen van uw activiteitsgegevens aan de schema's raadpleegt u de documentatie bij [activiteiten](activities.md).

**Semantische toewijzingen zijn momenteel ingeschakeld voor omgevingen op basis van zakelijke accounts**. *ContactProfile* is het enige type semantische toewijzing dat momenteel beschikbaar is in Customer Insights.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Een toewijzing aan semantische entiteit ContactProfile definiëren

1. Ga naar **Gegevens** > **Semantische toewijzingen (preview)**.

1. Selecteer **Semantische toewijzing toevoegen** om de begeleide ervaring te starten.

1. In de stap **Entiteitsgegevens** stelt u de waarden in voor de volgende velden:

   - **Naam van toewijzing van semantische entiteit**: geef een naam op voor uw semantische entiteitstoewijzing.
   - **Bronentiteit**: een entiteit die contactgegevens bevat.
   - **Primaire sleutel**: veld met een unieke identificatie van een contactpersoonrecord. Het mag geen dubbele waarden, lege waarden of ontbrekende waarden bevatten.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Stel de semantische entiteitstoewijzing in met naam, bronentiteit en primaire sleutel.":::

1. Selecteer **Volgende**.

1. Configureer in de stap **Relaties** de details om uw contactpersoongegevens te koppelen aan de bijbehorende accountgegevens. Deze stap visualiseert de verbinding tussen entiteiten.  

   Er zijn twee soorten relatiepaden die kunnen worden geïmplementeerd: **Directe relaties** en **Indirecte relaties**. Ga voor meer informatie naar [directe en indirecte relatiepaden](relationships.md#relationship-paths).

   1. Selecteer **Relatie toevoegen** om de relatie te configureren.
   1. Kies het kenmerk van uw bronentiteit dat uw contactpersoonentiteit verbindt met een andere entiteit.
   1. Kies de entiteit waarmee u uw contactpersoonentiteit wilt verbinden. Kies een entiteit in de sectie **Accountentiteiten** of **Tussenliggende entiteit**. Als u een tussenliggende entiteit selecteert, moet u een tweede relatie definiëren om verbinding te maken met uw doelaccountentiteit.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Selecteer een accountentiteit of een tussenliggende entiteit.":::

   1. Geef een **Relatienaam** op. Als er al een relatie tussen uw entiteiten bestaat, is de relatienaam alleen-lezen. Als er geen relatie bestaat, wordt er een nieuwe relatie gemaakt met de naam die u opgeeft.
   1. Selecteer **Toepassen** om de configuratie van de relatie te voltooien.

   > [!NOTE]
   > U kunt meer relaties configureren tussen de contactpersoonentiteit en andere accountentiteiten met tussenliggende entiteiten.
   
     :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Visualisatie van verschillende relaties die contactpersoonentiteiten verbinden met accountentiteiten.":::

1. Selecteer **Volgende**.

1. In de stap **Semantisch type instellen** kiest u een **Semantisch type**. Momenteel is er één **Semantisch type** met de naam *ContactProfile*.

1. Wijs uw contactpersoon-id toe aan het semantische *ContactProfile*-type **Contactpersoon-id**. Wijs desgewenst andere velden toe, zoals Voornaam, Achternaam, Geslacht of E-mailadres.

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Wijs de kenmerken van uw contactgegevens toe aan de opgegeven verplichte en optionele velden.":::

1. Selecteer **Volgende**.

1. Bekijk in de stap **Beoordelen** de configuratie van de semantische toewijzing. Selecteer **Bewerken** voor de betreffende sectie om wijzigingen aan te brengen.

1. Selecteer **Save**.

1. Selecteer **Uitvoeren** om de semantische toewijzing te verwerken. Of selecteer **Sluiten** om uw semantische toewijzing op te slaan zonder deze te verwerken. Om een semantische toewijzing op een later tijdstip uit te voeren, selecteert u de semantische toewijzing en selecteert u **Vernieuwen**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Bestaande semantische toewijzingen beheren

Ga naar **Gegevens** > **Semantische toewijzingen (preview)** om uw opgeslagen semantische toewijzingen, hun bronentiteit, semantisch type, toewijzingstype en status te bekijken.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Opties om semantische toewijzingen te beheren.":::

Selecteer de semantische toewijzing om beschikbare acties te bekijken.
- **Bewerk** de huidige configuratie. Selecteer **Opslaan** en **Uitvoeren** om de wijzigingen te verwerken.
- **Vernieuw** de semantische toewijzing om de nieuwste gegevens op te nemen. Als u een bepaalde semantische toewijzing vernieuwt, worden alle semantische toewijzingen van hetzelfde type vernieuwd.
- **Wijzig de naam** van de semantische toewijzing. Selecteer **Save**.
- **Verwijder** de semantische toewijzing. Als u meerdere semantische toewijzingen tegelijk wilt verwijderen, selecteert u de semantische toewijzingen en het verwijderpictogram. Selecteer **Verwijderen** om het verwijderen te bevestigen.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Een semantische entiteitstoewijzing ContactProfile gebruiken om activiteiten op contactniveau te maken

Na het maken van een semantische entiteitstoewijzing *ContactProfile*, kunt u activiteiten van contactpersonen vastleggen. Hiermee kunt u in de activiteitentijdlijn voor een account zien welke contactpersoon verantwoordelijk was voor elke activiteit. De meeste stappen volgen de typische configuratie van activiteitentoewijzing.

   > [!NOTE]
   > Als u activiteiten op contactpersoonniveau wilt laten werken, moet u zowel het kenmerk **AccountID** als het kenmerk **ContactID** hebben voor elke record binnen uw activiteitsgegevens.

1. [Definieer de semantische entiteitstoewijzing *ContactProfile* ](#define-a-contactprofile-semantic-entity-mapping) en voer de semantische toewijzing uit.

1. Ga naar **Gegevens** > **Activiteiten**.

1. Selectee **Activiteit toevoegen** om een nieuwe activiteit te maken.

1. Geef de activiteit een naam, selecteer de bronactiviteitsentiteit en selecteer de primaire sleutel van de activiteitsentiteit.

1. Maak in de stap **Relaties** een indirecte relatie tussen uw activiteitsbrongegevens en accounts, waarbij u uw contactgegevens als tussenpersoon gebruikt. Zie [directe en indirecte relatiepaden](relationships.md#relationship-paths) voor meer informatie.
   - Voorbeeldrelatie voor een activiteit met de naam *Aankopen*:
      - **Bronactiviteitsgegevens voor aankopen** > **Contactgegevens** in het kenmerk **ContactID**
      - **Contactgegevens** > **Accountgegevens** in het kenmerk **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Voorbeeld van het instellen van relaties.":::

1. Selecteer na het instellen van de relatie(s) de optie **Volgende** en voltooi uw activiteitstoewijzingsconfiguratie. Zie [een activiteit definiëren](activities.md) voor gedetailleerde stappen voor het maken van activiteiten.

1. Voer uw activiteitstoewijzingen uit.

1. Nadat een activiteitstoewijzing op contactpersoonniveau is uitgevoerd, selecteert u **Klanten**. Activiteiten op niveau van contactpersoon worden op uw klanttijdlijn weergegeven.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Eindresultaat na configureren van contactpersoonactiviteiten":::

### <a name="contact-level-activity-timeline-filtering"></a>Tijdlijnfiltering voor activiteiten op contactpersoonniveau

De tijdlijn voor uw klanten bevat hun id's of namen, afhankelijk van uw configuratie van *ContactProfile*, voor hun activiteiten. Filter activiteiten op contactpersonen in de tijdlijn om specifieke contactpersonen te zien waarin u geïnteresseerd bent. Als u alle activiteiten wilt bekijken die niet aan een specifieke contactpersoon zijn toegewezen, selecteert u **Activiteiten die niet aan een contactpersoon zijn toegewezen**.

:::image type="content" source="media/Contact_Activities3.png" alt-text="Filteropties beschikbaar voor activiteiten op contactpersoonniveau.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
