---
title: Klantactiviteiten
description: Definieer klantactiviteiten en bekijk ze op de tijdlijn van de klant.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: dcef8f0547009e1488f1abe91423fa0bf5b061de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267426"
---
# <a name="customer-activities"></a>Klantactiviteiten

Combineer klantactiviteiten van [verschillende gegevensbronnen](data-sources.md) in Dynamics 365 Customer Insights om een klanttijdlijn te maken met de activiteiten in chronologische volgorde. U kunt de tijdlijn opnemen in apps voor klantbetrokkenheid in Dynamics 365 via de [invoegtoepassing Klantenkaart](customer-card-add-in.md) of in een Power BI-dashboard.

## <a name="define-an-activity"></a>Een activiteit definiëren

Uw gegevensbronnen omvatten entiteiten met transactie- en activiteitsgegevens uit meerdere gegevensbronnen. Identificeer deze entiteiten en selecteer de activiteiten die u op de tijdlijn van de klant wilt bekijken. Kies de entiteit die uw doelactiviteit of -activiteiten omvat.

1. Ga in doelgroepinzichten naar **Gegevens** > **Activiteiten**.

1. Selecteer **Activiteit toevoegen**.

   > [!NOTE]
   > Een entiteit moet ten minste één kenmerk van het type **Datum** hebben om te worden opgenomen in de tijdlijn van een klant en u kunt geen entiteiten toevoegen zonder velden **Datum**. Het besturingselement **Activiteit toevoegen** is uitgeschakeld als een dergelijke entiteit niet wordt gevonden.

1. Stel in het deelvenster **Activiteit toevoegen** de waarden in voor de volgende velden:

   - **Entiteit**: selecteer een entiteit die transactie- of activiteitsgegevens bevat.
   - **Primaire sleutel**: selecteer het veld waarmee een record eenduidig wordt geïdentificeerd. Het mag geen dubbele waarden, lege waarden of ontbrekende waarden bevatten.
   - **Tijdstempel**: selecteer het veld dat de starttijd van uw activiteit vertegenwoordigt.
   - **Gebeurtenis**: selecteer het veld dat de gebeurtenis voor de activiteit aangeeft.
   - **webadres**: selecteer het veld dat een URL vertegenwoordigt met aanvullende informatie over deze activiteit. Bijvoorbeeld het transactiesysteem dat de bron van deze activiteit vormt. Deze URL kan elk veld zijn uit de gegevensbron, of het kan worden geconstrueerd als een nieuw veld via een Power Query-transformatie. Deze URL-gegevens worden opgeslagen in de entiteit Geharmoniseerde activiteit, die stroomafwaarts kan worden gebruikt met behulp van API's.
   - **Details**: selecteer optioneel het veld dat wordt toegevoegd voor extra details.
   - **Pictogram**: selecteer optioneel het pictogram dat deze activiteit aangeeft.
   - **Type activiteit**: definieer de verwijzing naar het activiteitstype naar Common Data Model dat het beste de semantische definitie van de activiteit beschrijft.

1. Configureer in de sectie **Relatie instellen** de details om uw activiteitsgegevens te koppelen aan de corresponderende klant.

    - **Activiteitsentiteitsveld**: selecteer het veld in uw activiteitsentiteit dat zal worden gebruikt om een relatie met een andere entiteit tot stand te brengen.
    - **Klantentiteit**: selecteer de corresponderende bronklantentiteit waarmee uw activiteitsentiteit een relatie zal hebben. U kunt alleen relaties tot stand brengen met bronklantenentiteiten die worden gebruikt in het proces van gegevensharmonisering.
    - **Veld Klantentiteit**: dit veld toont de primaire sleutel van de bronklantentiteit zoals geselecteerd in het kaartproces. Dit primaire sleutelveld in de bronklantentiteit wordt gebruikt om een relatie tot stand te brengen met de activiteitsentiteit.
    - **Naam**: als er al een relatie bestaat tussen deze activiteitsentiteit en de geselecteerde bronklantentiteit, staat de relatienaam in de alleen-lezenmodus. Als een dergelijke relatie niet bestaat, wordt er een nieuwe relatie gemaakt met de hier opgegeven naam.
   
   > [!div class="mx-imgBorder"]
   > ![De entiteitsrelatie definiëren](media/activities-entities-define.png "De entiteitsrelatie definiëren")

1. Selecteer **Opslaan** om uw wijzigingen toe te passen.

1. Selecteer **Uitvoeren** op de pagina **Activiteiten**.

> [!TIP]
> Er zijn [zes soorten status](system.md#status-types) voor taken/processen. Bovendien zijn de meeste processen [afhankelijk van andere stroomafwaartse processen](system.md#refresh-policies). U kunt de status van een proces selecteren om voortgangsdetails te zien van de volledige taak. Na het selecteren van **Details bekijken** voor een van de taken vindt u aanvullende informatie: verwerkingstijd, de laatste verwerkingsdatum en alle fouten en waarschuwingen die bij de taak horen.

## <a name="edit-an-activity"></a>Een activiteit bewerken

1. Ga in doelgroepinzichten naar **Gegevens** > **Activiteiten**.

2. Selecteer de activiteitsentiteit die u wilt bewerken en selecteer **Bewerken**. Of u kunt de muisaanwijzer op de rij van de entiteit plaatsen en het pictogram **Bewerken** selecteren.

3. Klik op het pictogram **Bewerken**.

4. Werk in het deelvenster **Activiteit bewerken** de waarden bij en selecteer **Opslaan**.

5. Selecteer **Uitvoeren** op de pagina **Activiteiten**.

## <a name="delete-an-activity"></a>Een activiteit verwijderen

1. Ga in doelgroepinzichten naar **Gegevens** > **Activiteiten**.

2. Selecteer de activiteitsentiteit die u wilt verwijderen en selecteer **Verwijderen**. Of u kunt de muisaanwijzer op de rij van de entiteit plaatsen en het pictogram **Verwijderen** selecteren. Bovendien kunt u meerdere activiteitsentiteiten selecteren om tegelijkertijd te verwijderen.
   > [!div class="mx-imgBorder"]
   > ![De entiteitsrelaties bewerken of verwijderen](media/activities-entities-edit-delete.png "De entiteitsrelaties bewerken of verwijderen")

3. Selecteer het pictogram **Verwijderen**.

4. Bevestig de verwijdering.


[!INCLUDE[footer-include](../includes/footer-banner.md)]