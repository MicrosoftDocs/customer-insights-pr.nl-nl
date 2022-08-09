---
title: Klantactiviteiten
description: Definieer klantactiviteiten en geef ze weer in een tijdlijn in klantprofielen.
ms.date: 07/22/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsight
ms.openlocfilehash: cc21b0eeb368156437e60d851c2d144f3974c066
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188133"
---
# <a name="customer-activities"></a>Klantactiviteiten

Klantactiviteiten zijn acties of gebeurtenissen die door klanten worden uitgevoerd. Voorbeelden zijn transacties, duur van ondersteuningsgesprekken, websitereviews, aankopen of retouren. Deze activiteiten zijn opgenomen in een of meer gegevensbronnen. Met Customers Insights consolideert u uw klantactiviteiten vanuit deze [gegevensbronnen](data-sources.md) en koppelt u ze aan klantprofielen. Deze activiteiten verschijnen chronologisch op een tijdlijn in het klantprofiel. Neem de tijdlijn op in Dynamics 365-apps met de [invoegtoepassing Klantkaart](customer-card-add-in.md)-oplossing.

## <a name="define-an-activity"></a>Een activiteit definiëren

Een entiteit moet ten minste één kenmerk van het type **Datum** hebben om te worden opgenomen op de tijdlijn van een klant. Het besturingselement **Activiteit toevoegen** is uitgeschakeld als een dergelijke entiteit niet wordt gevonden.

1. Ga naar **Gegevens** > **Activiteiten**.

1. Selecteer **Activiteit toevoegen** om de begeleide ervaring te starten.

1. Voer in de stap **Activiteitsgegevens** de volgende gegevens in:

   - **Activiteitsnaam**: een naam voor uw activiteit.
   - **Activiteitsentiteit**: een entiteit die transactie- of activiteitsgegevens bevat.
   - **Primaire sleutel**: het veld waarmee een record op unieke wijze wordt geïdentificeerd. Het mag geen dubbele waarden, lege waarden of ontbrekende waarden bevatten.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Stel de activiteitsgegevens in met naam, entiteit en primaire sleutel.":::

1. Selecteer **Volgende**.

1. Selecteer in de stap **Relatie** de optie **Relatie toevoegen** om uw activiteitsgegevens te koppelen aan de bijbehorende klantrecord. Deze stap visualiseert de verbinding tussen entiteiten.  

   - **Buitenlandse sleutel uit**: veld in uw activiteitsentiteit waarmee een relatie met een andere entiteit tot stand wordt gebracht.
   - **Naar entiteitsnaam**: bijbehorende bronklantentiteit waarmee uw activiteitsentiteit een relatie heeft. U kunt alleen relaties tot stand brengen met bronklantentiteiten die worden gebruikt in het proces van gegevensharmonisatie.
   - **Naam relatie**: naam waarmee de relatie tussen entiteiten wordt geïdentificeerd. Als er al een relatie bestaat tussen deze activiteitsentiteit en de geselecteerde bronklantentiteit, is de relatienaam alleen-lezen.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definieer de entiteitsrelatie.":::

   > [!TIP]
   > In B2B-omgevingen kunt u kiezen tussen accountentiteiten en andere entiteiten. Als u een accountentiteit selecteert, wordt het relatiepad automatisch ingesteld. Voor andere entiteiten moet u het relatiepad over een of meer tussenliggende entiteiten definiëren totdat u een accountentiteit bereikt.

1. Selecteer **Toepassen** om de relatie te maken.

1. Selecteer **Volgende**.

1. Kies in de stap **Unificatie van activiteit** de activiteitsgebeurtenis en de starttijd van uw activiteit.
   - **Vereiste velden**
      - **Gebeurtenisactiviteit**: veld dat de gebeurtenis aangeeft voor deze activiteit.
      - **Timestamp**: veld dat de starttijd van uw activiteit aangeeft.

   - **Optionele velden**
      - **Aanvullende details**: veld met relevante informatie voor deze activiteit.
      - **Pictogram**: pictogram dat dit type activiteit het beste weergeeft.
      - **webadres**: veld dat een URL bevat met informatie over deze activiteit. Bijvoorbeeld het transactiesysteem dat de bron van deze activiteit vormt. Deze URL kan elk veld uit de gegevensbron zijn, of het kan worden geconstrueerd als een nieuw veld met behulp van een Power Query-transformatie. De URL-gegevens worden opgeslagen in de entiteit *Unified Activity*, die stroomafwaarts kan worden gebruikt met [API's](apis.md).

   - **Weergeven in tijdlijn**
      - Kies of u deze activiteit wilt weergeven in de tijdlijnweergave in uw klantprofielen. Selecteer **Ja** als u de activiteit in de tijdlijn wilt weergeven of **Nee** als u de activiteit wilt verbergen.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Geef de klantactiviteitsgegevens op in een Unified Activity-entiteit.":::

1. Selecteer **Volgende** om het activiteitstype te kiezen of selecteer **Voltooien en controleren** om de activiteit op te slaan met het activiteitstype dat is ingesteld op **Overige**.

1. Kies in de stap **Type activiteit** het activiteitstype en selecteer optioneel of u enkele van de activiteitstypen semantisch wilt toewijzen voor gebruik in andere gebieden van Customer Insights. Momenteel wordt door activiteitstypen *Feedback*, *Loyalty*, *SalesOrder*, *SalesOrderLine* en *Subscription* semantiek ondersteund nadat akkoord is gegaan met het toewijzen van de velden. Als een activiteitstype niet relevant is voor de nieuwe activiteit, kunt u *Overige* of *Nieuwe maken* kiezen voor een aangepast activiteitstype.

1. Selecteer **Volgende**.

1. Verifieer uw selecties in de stap **Controleren**. Ga terug naar een van de voorgaande stappen en werk de informatie indien nodig bij.

1. Selecteer **Activiteit opslaan** om uw wijzigingen toe te passen en selecteer **Gereed** om terug gaan naar **Gegevens** > **Activiteiten**. De gemaakte activiteit wordt weergegeven.

1. Nadat u al uw activiteiten hebt gemaakt, selecteert u **Uitvoeren** om ze te verwerken.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-activities"></a>Bestaande activiteiten beheren

Ga naar **Gegevens** > **Activiteiten** om uw opgeslagen activiteiten, de bijbehorende bronentiteit, het activiteitstype te bekijken en om te zien of ze zijn opgenomen in de tijdlijn van de klant. U kunt de lijst met activiteiten sorteren op elke kolom of het zoekvak gebruiken om de activiteit te vinden die u wilt beheren.

Selecteer een activiteit om beschikbare acties te bekijken.

- **Bewerk** de activiteit om de configuratie ervan te wijzigen. De configuratie wordt geopend in de controlestap. Selecteer na het wijzigen van de configuratie de optie **Activiteit opslaan** en selecteer vervolgens **Uitvoeren** om de wijzigingen te verwerken.
- **Wijzig de naam** van de activiteit. Selecteer **Opslaan** om uw wijzigingen toe te passen.
- **Verwijder** de activiteit. U kunt ook meer dan één activiteit tegelijk verwijderen door de activiteiten te selecteren en vervolgens **Verwijderen** te selecteren. Bevestig de verwijdering.

## <a name="view-activity-timelines-on-customer-profiles"></a>Activiteitentijdlijnen op klantprofielen bekijken

1. Als u **Weergeven in activiteitentijdlijn** hebt geselecteerd in de activiteitenconfiguratie, gaat u naar **Klanten** en selecteert u een klantprofiel om activiteiten van de klant te bekijken in de sectie **Activiteitentijdlijn**.

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Bekijk geconfigureerde activiteiten in klantprofielen.":::

1. Activiteiten op de activiteitentijdlijn filteren:

   - Selecteer een of meerdere activiteitspictogrammen om uw resultaten te verfijnen en alleen de geselecteerde typen op te nemen.

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filter activiteiten op type met behulp van de pictogrammen.":::

   - Selecteer **Filter** om een filterpaneel te openen voor de configuratie van uw tijdlijnfilters. Filter op *ActivityType* en/of *Date*. Selecteer **Toepassen**.

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Gebruik het filterpaneel om filtervoorwaarden te configureren.":::

1. Als u filters wilt verwijderen, selecteert u **Filters wissen** of selecteert u **Filter** en schakelt u het selectievakje Filter uit.

> [!NOTE]
> Activiteitsfilters worden verwijderd wanneer u een klantprofiel verlaat. U moet ze toepassen elke keer dat u een klantprofiel opent.

[!INCLUDE [footer-include](includes/footer-banner.md)]
