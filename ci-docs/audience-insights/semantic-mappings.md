---
title: Semantische toewijzingen (preview)
description: Overzicht van semantische toewijzingen en hoe ze te gebruiken.
ms.date: 09/28/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: b0884b8b6a2c5abe4b3967d1b57d11a3a6d65c5b
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/11/2021
ms.locfileid: "7622929"
---
# <a name="semantic-mappings"></a>Semantische toewijzingen

Met semantische toewijzingen kunt u uw niet-activiteitsgegevens toewijzen aan vooraf gedefinieerde schema's. Deze schema's helpen doelgroepinzichten om uw gegevenskenmerken beter te begrijpen. Semantische toewijzing en de verstrekte gegevens maken nieuwe inzichten en functies mogelijk in doelgroepinzichten. Voor informatie over het koppelen van uw activiteitsgegevens aan de schema's raadpleegt u de documentatie bij [activiteiten](activities.md).

**Semantische toewijzingen zijn momenteel ingeschakeld voor omgevingen op basis van zakelijke accounts**. *ContactProfile* is het enige type semantische toewijzing dat momenteel beschikbaar is in doelgroepinzichten.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Een toewijzing aan semantische entiteit ContactProfile definiëren

1. Ga in doelgroepinzichten naar **Gegevens** > **Semantische toewijzingen (preview)**.

1. Selecteer **Semantische toewijzing toevoegen** om de begeleide ervaring te starten.

1. In de stap **Entiteitsgegevens** stelt u de waarden in voor de volgende velden:

   - **Naam van toewijzing van semantische entiteit**: geef een naam op voor uw semantische entiteitstoewijzing.
   - **Bronentiteit**: selecteer een entiteit die contactgegevens bevat.
   - **Primaire sleutel**: selecteer het veld met een unieke identificatie van een contactpersoonrecord. Het mag geen dubbele waarden, lege waarden of ontbrekende waarden bevatten.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Stel de semantische entiteitstoewijzing in met naam, bronentiteit en primaire sleutel.":::

1. Selecteer **Volgende** om door te gaan.

1. Configureer in de stap **Relaties** de details om uw contactpersoongegevens te koppelen aan de bijbehorende accountgegevens. Deze stap visualiseert de verbinding tussen entiteiten.  

   Er zijn twee soorten relatiepaden die kunnen worden geïmplementeerd: **Directe relaties** en **Indirecte relaties**. Ga voor meer informatie naar [directe en indirecte relatiepaden](relationships.md#relationship-paths).

   1. Selecteer **Relatie toevoegen** om de relatie te configureren.
   1. Kies het kenmerk van uw bronentiteit dat uw contactpersoonentiteit verbindt met een andere entiteit.
   1. Kies de entiteit waarmee u uw contactpersoonentiteit wilt verbinden. U kunt een entiteit kiezen in de sectie **Accountentiteiten** of **Tussenliggende entiteit**. Als u een tussenliggende entiteit selecteert, moet u een tweede relatie definiëren om verbinding te maken met uw doelaccountentiteit.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Selecteer een accountentiteit of een tussenliggende entiteit.":::

   1. Geef een **Relatienaam** op. Als er al een relatie tussen uw entiteiten bestaat, is de relatienaam alleen-lezen. Als er geen relatie bestaat, wordt er een nieuwe relatie gemaakt met de naam die u opgeeft.
   1. Selecteer **Toepassen** om de configuratie van de relatie te voltooien.

   > [!NOTE]
   > U kunt meer relaties configureren tussen de contactpersoonentiteit en andere accountentiteiten met tussenliggende entiteiten.
   >  :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Visualisatie van verschillende relaties die contactpersoonentiteiten verbinden met accountentiteiten.":::

1. Selecteer **Volgende** wanneer u klaar bent met de relatieconfiguratie.

1. In de stap **Semantisch type instellen** kiest u een **Semantisch type**. Momenteel is er één **Semantisch type** met de naam *ContactProfile*.

1. Wijs uw gegevens nu toe aan het *Semantisch type* **ContactProfile** voor de weergegeven velden:
   - Vereist veld: Contact-id
   - Optionele velden: Voornaam, Achternaam, Geboortedatum, Geslacht, Primair e-mailadres en Primair telefoonnummer

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Wijs de kenmerken van uw contactgegevens toe aan de opgegeven verplichte en optionele velden.":::

1. Selecteer **Volgende** om door te gaan.

1. In de stap **Beoordelen** stap, bekijkt u de configuratie van de semantische toewijzing. Selecteer **Bewerken** voor de betreffende sectie om wijzigingen aan te brengen.

1. Selecteer **Opslaan** om de nieuwe **Semantische toewijzing** op te slaan.

1. Na het opslaan kunt u **Uitvoeren** selecteren om de semantische toewijzing te verwerken. U kunt ook **Sluiten** selecteren om de semantische toewijzing op te slaan zonder deze te verwerken.

1. Om een semantische toewijzing op een later tijdstip uit te voeren, selecteert u de semantische toewijzing en selecteert u **Vernieuwen**.

> [!TIP]
> Er zijn [zes soorten status](system.md#status-types) voor taken/processen. Bovendien zijn de meeste processen [afhankelijk van andere stroomafwaartse processen](system.md#refresh-policies). U kunt de status van een proces selecteren om voortgangsdetails te zien van de volledige taak. Na het selecteren van **Details bekijken** voor een van de taken vindt u aanvullende informatie: verwerkingstijd, de laatste verwerkingsdatum en alle fouten en waarschuwingen die bij de taak horen.

## <a name="manage-existing-semantic-mappings"></a>Bestaande semantische toewijzingen beheren

Op **Gegevens** > **Semantische toewijzingen (preview)** kunt u al uw opgeslagen semantische toewijzingen bekijken en beheren. Elke semantische toewijzing wordt weergegeven door een afzonderlijke rij. U vindt details over de bronentiteit, het semantische type, het toewijzingstype en de status ervan.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Opties om semantische toewijzingen te beheren.":::

- **Bewerken**: de configuratie van de semantische toewijzing in de stap Beoordelen openen. U kunt de huidige configuratie wijzigen. Selecteer **Opslaan** en **Uitvoeren** om de wijzigingen te verwerken.

- **Vernieuwen**: de geselecteerde semantische toewijzing vernieuwen met de meest actuele gegevens van de entiteiten die deel uitmaken van de configuratie. Als u een bepaalde semantische toewijzing vernieuwt, worden alle semantische toewijzingen van hetzelfde type vernieuwd.

- **Naam wijzigen**: een dialoogvenster openen waarin u een andere naam kunt invoeren voor de geselecteerde semantische toewijzing. Selecteer **Opslaan** om uw wijzigingen toe te passen.

- **Verwijderen**: een dialoogvenster openen om het verwijderen van de geselecteerde semantische toewijzing te bevestigen. U kunt ook meerdere semantische toewijzingen tegelijk verwijderen door de semantische toewijzingen en het verwijderpictogram te selecteren. Selecteer **Verwijderen** om het verwijderen te bevestigen.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
