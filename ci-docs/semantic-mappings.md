---
title: Semantische toewijzingen (preview)
description: Overzicht van semantische toewijzingen en hoe ze te gebruiken.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 8780c11c8b091717349f0fd75a36b99c3a63ab49
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303870"
---
# <a name="semantic-mappings-preview"></a>Semantische toewijzingen (preview)

> [!NOTE]
> De pagina **Semantische toewijzingen** is alleen beschikbaar voor zakelijke omgevingen (B2B) waarin al contactpersoonprofielen zijn gemaakt met behulp van deze pagina. U kunt doorgaan met het maken en beheren van de individuele contactpersoonprofielen met behulp van de pagina **Semantische toewijzingen**. U kunt ook [uw contactpersoongegevens harmoniseren](data-unification-contacts.md) om duplicaten te verwijderen, overeenkomsten tussen entiteiten te identificeren en een enkel geharmoniseerd contactpersoonprofiel te maken. U kunt vervolgens het geharmoniseerde contactpersoonprofiel gebruiken om activiteiten op contactpersoonniveau te maken.

Met semantische toewijzingen kunt u uw niet-activiteitsgegevens toewijzen aan vooraf gedefinieerde schema's. Deze schema's helpen Customer Insights om uw gegevenskenmerken beter te begrijpen. Semantische toewijzing en de verstrekte gegevens maken nieuwe inzichten en functies mogelijk in Customer Insights. Voor informatie over het koppelen van uw activiteitsgegevens aan de schema's raadpleegt u de documentatie bij [activiteiten](activities.md).

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

[!INCLUDE [footer-include](includes/footer-banner.md)]
