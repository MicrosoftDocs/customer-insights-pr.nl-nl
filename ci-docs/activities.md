---
title: Klantactiviteiten
description: Definieer klantactiviteiten en geef ze weer in een tijdlijn in klantprofielen.
ms.date: 11/01/2021
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
ms.openlocfilehash: 6c0a1bc5d9a42806b458142804199c733ff530ec
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755492"
---
# <a name="customer-activities"></a>Klantactiviteiten

Combineer klantactiviteiten van [verschillende gegevensbronnen](data-sources.md) in Dynamics 365 Customer Insights. Maak een tijdlijn die de activiteiten chronologisch weergeeft. Neem de tijdlijn op in Dynamics 365-apps met de [invoegtoepassing Klantkaart](customer-card-add-in.md)-oplossing.

## <a name="define-an-activity"></a>Een activiteit definiëren

Uw gegevensbronnen kunnen entiteiten met transactie- en activiteitsgegevens uit meerdere gegevensbronnen bevatten. Identificeer deze entiteiten en selecteer de activiteiten die u op de tijdlijn van de klant wilt bekijken. Kies de entiteit die uw doelactiviteit of -activiteiten omvat.

Een entiteit moet ten minste één kenmerk van het type **Datum** hebben om te worden opgenomen in de tijdlijn van een klant en u kunt geen entiteiten toevoegen zonder velden **Datum**. Het besturingselement **Activiteit toevoegen** is uitgeschakeld als een dergelijke entiteit niet wordt gevonden.

1. Ga naar **Gegevens** > **Activiteiten**.

1. Selecteer **Activiteit toevoegen** om de begeleide ervaring voor het instellingsproces van de activiteit te starten.

1. Stel in de stap **Activiteitsgegevens** stel de waarden in voor de volgende velden:

   - **Activiteitsnaam**: selecteer een naam voor uw activiteit.
   - **Entiteit**: selecteer een entiteit die transactie- of activiteitsgegevens bevat.
   - **Primaire sleutel**: selecteer het veld waarmee een record eenduidig wordt geïdentificeerd. Het mag geen dubbele waarden, lege waarden of ontbrekende waarden bevatten.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Stel de activiteitsgegevens in met naam, entiteit en primaire sleutel.":::

1. Selecteer **Volgende** om naar de volgende stap te gaan.

1. Configureer in de stap **Relatie** de details om uw activiteitsgegevens te koppelen aan het bijbehorende klantrecord. Deze stap visualiseert de verbinding tussen entiteiten.  

   - **Eerste**: vreemd veld in uw activiteitsentiteit dat zal worden gebruikt om een relatie met een andere entiteit tot stand te brengen.
   - **Tweede**: corresponderende bronklantentiteit waarmee uw activiteitsentiteit een relatie heeft. U kunt alleen relaties tot stand brengen met bronklantentiteiten die worden gebruikt in het proces van gegevensharmonisatie.
   - **Derde**: als er al een relatie bestaat tussen deze activiteitsentiteit en de geselecteerde bronklantentiteit, is de relatienaam alleen-lezen. Als een dergelijke relatie niet bestaat, wordt er een nieuwe relatie gemaakt met de naam die u in dit vak opgeeft.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definieer de entiteitsrelatie.":::

   > [!TIP]
   > In B2B-omgevingen kunt u kiezen tussen accountentiteiten en andere entiteiten. Als u een accountentiteit selecteert, wordt het relatiepad automatisch ingesteld. Voor andere entiteiten moet u het relatiepad over een of meer tussenliggende entiteiten definiëren totdat u een accountentiteit bereikt.

1. Selecteer **Volgende** om naar de volgende stap te gaan. 

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

1. Selecteer **Volgende** om naar de volgende stap te gaan. U kunt **Voltooien en controleren** selecteren om de activiteit nu op te slaan met het activiteitstype ingesteld op **Overige**. 

1. Kies in de stap **Type activiteit** het activiteitstype en selecteer optioneel of u enkele van de activiteitstypen semantisch wilt toewijzen voor gebruik in andere gebieden van Customer Insights. Momenteel wordt door activiteitstypen *Feedback*, *Loyalty*, *SalesOrder*, *SalesOrderLine* en *Subscription* semantiek ondersteund nadat akkoord is gegaan met het toewijzen van de velden. Als een activiteitstype niet relevant is voor de nieuwe activiteit, kunt u *Overige* of *Nieuwe maken* kiezen voor een aangepast activiteitstype.

1. Selecteer **Volgende** om naar de volgende stap te gaan. 

1. Verifieer uw selecties in de stap **Controleren**. Ga terug naar een van de voorgaande stappen en werk de informatie indien nodig bij.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Controleer de opgegeven velden voor een activiteit.":::
   
1. Selecteer **Activiteit opslaan** om uw wijzigingen toe te passen en selecteer **Gereed** om terug gaan naar **Gegevens** > **Activiteiten**. Hier ziet ue welke activiteiten zijn ingesteld om in de tijdlijn te worden weergegeven. 

1. Selecteer op de pagina **Activiteiten** de optie **Uitvoeren** om de activiteit te verwerken. 

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-activities"></a>Bestaande activiteiten beheren

In **Gegevens** > **Activiteiten** kunt u al uw opgeslagen activiteiten bekijken en beheren. Elke activiteit wordt vertegenwoordigd door een rij die ook details bevat over de bron, de entiteit en het activiteitstype.

De volgende acties zijn beschikbaar wanneer u een activiteit selecteert. 

- **Bewerken**: opent de activiteitsinstellingen in de controlestap. U kunt vanuit deze stap de huidige configuratie geheel of gedeeltelijk wijzigen. Selecteer na het wijzigen van de configuratie de optie **Activiteit opslaan** en selecteer vervolgens **Uitvoeren** om de wijzigingen te verwerken.

- **Hernoemen**: opent een dialoogvenster waarin u een andere naam voor de geselecteerde activiteit kunt invoeren. Selecteer **Opslaan** om uw wijzigingen toe te passen.

- **Verwijderen**: opent een dialoogvenster om het verwijderen van de geselecteerde activiteit te bevestigen. U kunt ook meer dan één activiteit tegelijk verwijderen door de activiteiten te selecteren en vervolgens het verwijderpictogram te selecteren. Selecteer **Verwijderen** om het verwijderen te bevestigen.

## <a name="view-activity-timelines-on-customer-profiles"></a>Activiteitentijdlijnen op klantprofielen bekijken

Nadat u klantactiviteiten hebt geconfigureerd, selecteert u **Weergeven in activiteitentijdlijn** in de activiteitenconfiguratie om alle activiteiten van uw klant op hun klantprofiel te vinden.

Om de tijdlijn voor een klant te openen, gaat u naar **Klanten** en kiest u het klantprofiel dat u wilt bekijken.

Als een klant heeft deelgenomen aan een geconfigureerde activiteit, vindt u deze in de sectie **Activiteitentijdlijn**.

:::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Bekijk geconfigureerde activiteiten in klantprofielen.":::

Er zijn verschillende manieren om activiteiten in de activiteitentijdlijn te filteren:

- U kunt een of meerdere activiteitenpictogrammen selecteren om uw resultaten te verfijnen en alleen de geselecteerde typen op te nemen.

  :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filter activiteiten op type met behulp van de pictogrammen.":::

- U kunt **Filter** selecteren om een filterpaneel te openen voor de configuratie van uw tijdlijnfilters.

   1. U kunt filteren op *ActivityType* en *Date*
   1. Selecteer **Toepassen** om de filters in de activiteitentijdlijn te gebruiken.

   :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Gebruik het filterpaneel om filtervoorwaarden te configureren.":::

Om een filter te verwijderen, selecteert u de **x** naast het filter dat is toegepast op de tijdlijn, of selecteert u **Filters wissen**.


> [!NOTE]
> Activiteitsfilters worden verwijderd wanneer u een klantprofiel verlaat. U moet ze elke keer dat u een klantprofiel opent, toepassen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
