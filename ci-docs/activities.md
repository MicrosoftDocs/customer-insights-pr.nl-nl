---
title: Activiteiten voor klanten of zakelijke contactpersonen
description: Definieer activiteiten van klanten of zakelijke contactpersonen en geef ze weer in een tijdlijn in klantprofielen.
ms.date: 10/26/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: srivas15
ms.author: shsri
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: d8caa477278f04c3a0a95ced15f4bea2a22aa8cd
ms.sourcegitcommit: da6a2d189edacc8f2c0f2abedcb28245f26fe74c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/27/2022
ms.locfileid: "9723775"
---
# <a name="customer-or-business-contact-activities"></a>Activiteiten voor klanten of zakelijke contactpersonen

Klantactiviteiten zijn acties of gebeurtenissen die worden uitgevoerd door klanten of zakelijke contactpersonen. Voorbeelden zijn transacties, duur van ondersteuningsgesprekken, websitereviews, aankopen of retouren. Deze activiteiten zijn opgenomen in een of meer gegevensbronnen. Met Customers Insights consolideert u uw klantactiviteiten vanuit deze [gegevensbronnen](data-sources.md) en koppelt u ze aan klantprofielen. Deze activiteiten verschijnen chronologisch op een tijdlijn in het klantprofiel. Neem de tijdlijn op in Dynamics 365-apps met de [invoegtoepassing Klantkaart](customer-card-add-in.md)-oplossing.

## <a name="define-a-customer-activity"></a>Een klantactiviteit definiëren

Een entiteit moet ten minste één kenmerk van het type **Datum** hebben om te worden opgenomen op de tijdlijn van een klant. Het besturingselement **Activiteit toevoegen** is uitgeschakeld als een dergelijke entiteit niet wordt gevonden.

1. Ga naar **Gegevens** > **Activiteiten**.

1. Selecteer **Activiteit toevoegen** om de begeleide ervaring te starten.

1. Voer in de stap **Activiteitsgegevens** de volgende gegevens in:

   - **Activiteitsnaam**: selecteer een naam voor uw activiteit.
   - **Activiteitsentiteit**: selecteer een entiteit die transactie- of activiteitsgegevens bevat.
   - **Primaire sleutel**: selecteer het veld waarmee een record eenduidig wordt geïdentificeerd. Het mag geen dubbele waarden, lege waarden of ontbrekende waarden bevatten.

     > [!NOTE]
     > De primaire sleutel voor elke rij moet consistent blijven tijdens gegevensbronvernieuwingen. Als de primaire sleutel voor een rij wordt bijgewerkt in een gegevensbronvernieuwing, worden er duplicaten gemaakt in de uitvoerentiteit Activiteit. 

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Stel de activiteitsgegevens in met naam, entiteit en primaire sleutel.":::

1. Selecteer **Volgende**.

1. Selecteer in de stap **Relatie** de optie **Relatie toevoegen** om uw activiteitsgegevens te koppelen aan de bijbehorende klantrecord. Deze stap visualiseert de verbinding tussen entiteiten.  

   - **Refererende sleutel**: vreemd veld in uw activiteitsentiteit dat zal worden gebruikt om een relatie met een andere entiteit tot stand te brengen.
   - **Naar entiteitsnaam**: bijbehorende bronklantentiteit waarmee uw activiteitsentiteit een relatie heeft. U kunt alleen relaties tot stand brengen met bronklantentiteiten die worden gebruikt in het proces van gegevensharmonisatie.
   - **Relatienaam**: als er al een relatie bestaat tussen deze activiteitsentiteit en de geselecteerde bronklantentiteit, bevindt de relatienaam zich in de alleen-lezenmodus. Als een dergelijke relatie niet bestaat, wordt er een nieuwe relatie gemaakt met de naam die u in dit vak opgeeft.

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

## <a name="manage-existing-customer-activities"></a>Bestaande klantactiviteiten beheren

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

> [!NOTE]
> Activiteitsfilters worden verwijderd wanneer u een klantprofiel verlaat. U moet ze toepassen elke keer dat u een klantprofiel opent.

## <a name="define-a-contact-activity"></a>Een activiteit met contactpersonen definiëren

Gebruik voor zakelijke accounts (B2B) een entiteit *ContactProfile* om activiteiten van contactpersonen vast te leggen. U kunt de activiteitentijdlijn voor een account zien welke contactpersoon verantwoordelijk was voor elke activiteit. De meeste stappen volgen de toewijzingsconfiguratie voor klantactiviteiten.

   > [!NOTE]
   > Als u een activiteit op contactpersoonniveau wilt definiëren, moet een entiteit *ContactProfile* worden gemaakt, als [geharmoniseerd contactpersoonprofiel](data-unification-contacts.md) of via [semantische toewijzing](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).
   >
   > U moet zowel het kenmerk **AccountID** als het kenmerk **ContactID** hebben voor elke record binnen uw activiteitsgegevens.
  
1. Ga naar **Gegevens** > **Activiteiten**.

1. Selecteer **Activiteit toevoegen**.

1. Voer in de stap **Activiteitsgegevens** de volgende gegevens in:

   - **Activiteitsnaam**: selecteer een naam voor uw activiteit.
   - **Activiteitsentiteit**: selecteer een entiteit die transactie- of activiteitsgegevens bevat.
   - **Primaire sleutel**: selecteer het veld waarmee een record eenduidig wordt geïdentificeerd. Het mag geen dubbele waarden, lege waarden of ontbrekende waarden bevatten.

     > [!NOTE]
     > De primaire sleutel voor elke rij moet consistent blijven tijdens gegevensbronvernieuwingen. Als de primaire sleutel voor een rij wordt bijgewerkt in een gegevensbronvernieuwing, worden er duplicaten gemaakt in de uitvoerentiteit Activiteit. 


1. Maak in de stap **Relaties** een indirecte relatie tussen uw activiteitsbrongegevens en accounts, waarbij u uw contactgegevens als tussenpersoon gebruikt. Zie [directe en indirecte relatiepaden](relationships.md#relationship-paths) voor meer informatie.
   - Voorbeeldrelatie voor een activiteit met de naam *Aankopen*:
      - **Bronactiviteitsgegevens voor aankopen** > **Contactgegevens** in het kenmerk **ContactID**
      - **Contactgegevens** > **Accountgegevens** in het kenmerk **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Voorbeeld van het instellen van relaties.":::

1. Selecteer na het instellen van de relatie(s) de optie **Volgende** en voltooi uw activiteitstoewijzingsconfiguratie. Zie [Een klantactiviteit definiëren](#define-a-customer-activity) voor gedetailleerde stappen bij het maken van activiteiten.

1. Voer uw activiteitstoewijzingen uit.

1. Uw activiteiten op contactpersoonniveau zijn nu zichtbaar op uw klanttijdlijn.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Eindresultaat na configureren van contactpersoonactiviteiten":::

## <a name="contact-level-activity-timeline-filtering"></a>Tijdlijnfiltering voor activiteiten op contactpersoonniveau

Nadat u een activiteittoewijzing op contactpersoonniveau hebt geconfigureerd en uitgevoerd, wordt de activiteitentijdlijn voor uw klanten bijgewerkt. Het bevat hun id's of namen, afhankelijk van uw configuratie *ContactProfile*, voor de activiteiten waarop ze hebben gehandeld. U kunt activiteiten filteren op contactpersonen in de tijdlijn om specifieke contactpersonen te zien waarin u geïnteresseerd bent. Bovendien kunt u alle activiteiten zien die niet aan een specifieke contactpersoon zijn toegewezen door **Activiteiten die niet aan een contactpersoon zijn toegewezen** te selecteren.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Filteropties beschikbaar voor activiteiten op contactpersoonniveau.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
