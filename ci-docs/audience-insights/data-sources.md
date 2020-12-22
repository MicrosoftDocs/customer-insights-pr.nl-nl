---
title: Gegevensbronnen gebruiken om gegevens op te nemen
description: Meer informatie over hoe u gegevens uit verschillende bronnen kunt importeren.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643947"
---
# <a name="overview-about-data-sources"></a>Overzicht van gegevensbronnen

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

De doelgroepinzichten-mogelijkheid in Dynamics 365 Customer Insights maakt verbinding met gegevens uit uiteenlopende bronnen. Verbinden met een gegevensbron wordt vaak *gegevensopname* genoemd. Na het opnemen van de gegevens kunt u ze [samenvoegen](data-unification.md) en actie ondernemen.

## <a name="add-a-data-source"></a>Een gegevensbron toevoegen

Raadpleeg de gedetailleerde artikelen over het toevoegen van een gegevensbron, afhankelijk van de optie die u kiest.

U kunt een gegevensbron op drie manieren toevoegen:

- [Via tientallen Power Query-connectors](connect-power-query.md)
- [Via een Common Data Model-map](connect-common-data-model.md)
- [Via uw eigen Common Data Service-lake](connect-common-data-service-lake.md)

> [!NOTE]
> U kunt nog geen gegevens toevoegen uit on-premises gegevensbronnen.

## <a name="review-ingested-data"></a>Opgenomen gegevens bekijken

U ziet de naam van elke opgenomen gegevensbron, de status en de laatste keer dat de gegevens voor die bron zijn vernieuwd. U kunt de lijst met gegevensbronnen op elke kolom sorteren.

> [!div class="mx-imgBorder"]
> ![Gegevensbron toegevoegd](media/configure-data-datasource-added.png "Gegevensbron toegevoegd")

|Status  |Beschrijving  |
|---------|---------|
|Voltooid   |Gegevensbron is opgenomen als een tijd wordt vermeld in de kolom **Vernieuwd**.
|Niet gestart   |De gegevensbron heeft nog geen gegevens opgenomen of bevindt zich nog in de conceptmodus.         |
|Vernieuwen    |De opname van gegevens wordt uitgevoerd. U kunt deze bewerking annuleren door **Stoppen met vernieuwen** te selecteren in de kolom **Acties**. Als u het vernieuwen van een gegevensbron stopt, keert het terug naar de laatste vernieuwingsstatus.       |
|Mislukt     |Er zijn fouten opgetreden bij de gegevensopname.         |

Selecteer **Status vernieuwen** om meer details over de vernieuwingsstatus te bekijken, inclusief foutdetails en downstream procesupdates.

Het laden van gegevens kan enige tijd in beslag nemen. Na een succesvolle vernieuwing kunnen de opgenomen gegevens worden bekeken vanaf de pagina **Entiteiten**. Zie [Entiteiten](entities.md) voor meer informatie.

## <a name="refresh-a-data-source"></a>Een gegevensbron vernieuwen

Gegevensbronnen kunnen automatisch worden vernieuwd of op aanvraag handmatig worden vernieuwd. 

Ga naar **Beheer** > **Systeem** > [**Planning**](system.md#schedule-tab) om geplande vernieuwingen van al uw opgenomen gegevensbronnen te configureren.

Volg deze stappen om een gegevensbron op aanvraag te vernieuwen:

1. Ga in doelgroepinzichten naar **Gegevens** > **Gegevensbronnen**

2. Selecteer het verticale beletselteken naast de gegevensbron die u wilt vernieuwen en selecteer **Vernieuwen** in de vervolgkeuzelijst.

3. De gegevensbron wordt nu geactiveerd voor een handmatige vernieuwing. Als u een gegevensbron vernieuwt, worden zowel de entiteitsplanning als de gegevens bijgewerkt voor alle entiteiten die zijn gespecificeerd in de gegevensbron.

4. Selecteer **Vernieuwen stoppen** als u een bestaande vernieuwing wilt annuleren, waarna de gegevensbron terugkeert naar de laatste vernieuwingsstatus.

## <a name="delete-a-data-source"></a>Een gegevensbron verwijderen

1. Ga in doelgroepinzichten naar **Gegevens** > **Gegevensbronnen**.

2. Selecteer het verticale weglatingsteken naast de gegevensbron die u wilt verwijderen en selecteer **Verwijderen** uit het vervolgkeuzemenu.

3. Bevestig de verwijdering.
