---
title: Gegevensbronnen gebruiken om gegevens op te nemen
description: Meer informatie over hoe u gegevens uit verschillende bronnen kunt importeren.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ca979527c9cb8418e12af4a74513033047e4901c
ms.sourcegitcommit: 3807202283dd116a30f900a163d8141db621e5a8
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/28/2022
ms.locfileid: "8046582"
---
# <a name="data-sources-overview"></a>Overzicht van gegevensbronnen



De doelgroepinzichten-mogelijkheid in Dynamics 365 Customer Insights maakt verbinding met gegevens uit uiteenlopende bronnen. Verbinden met een gegevensbron wordt vaak *gegevensopname* genoemd. Na het opnemen van de gegevens kunt u ze [samenvoegen](data-unification.md) en actie ondernemen.

## <a name="add-a-data-source"></a>Een gegevensbron toevoegen

Raadpleeg de gedetailleerde artikelen voor het toevoegen van een gegevensbron, afhankelijk van de optie die u kiest.

U kunt de volgende gegevensbronnen toevoegen:

- [Power Query-connectors](connect-power-query.md)
- [Common Data Model](connect-common-data-model.md)
- [Microsoft Dataverse lake](connect-dataverse-managed-lake.md)

> [!NOTE]
> Als u de proefversie gebruikt, bevat de sectie met importmethoden een optie **Gegevensbibliotheek voor Customer Insights**. Kies deze optie om een voorbeeldgegevensset te selecteren die beschikbaar is voor verschillende bedrijfstakken. Zie [Proefversie van Dynamics 365 Customer Insights](../trial-signup.md) voor meer informatie.

## <a name="add-data-from-on-premises-data-sources"></a>Gegevens toevoegen vanuit on-premises gegevensbronnen

Het opnemen van gegevens uit on-premises gegevensbronnen in doelgroepinzichten wordt ondersteund op basis van Microsoft Power Platform-gegevensstromen. U kunt gegevensstromen in Customer Insights inschakelen door [de omgevings-URL voor Microsoft Dataverse te verstrekken](create-environment.md) bij het instellen van de omgeving.

Gegevensbronnen die zijn gemaakt na het koppelen van een Dataverse-omgeving met Customer Insights maken standaard gebruik van [Power Platform-gegevensstromen](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Gegevensstromen ondersteunen on-premises connectiviteit met behulp van de gegevensgateway. U kunt gegevensbronnen verwijderen en opnieuw maken die bestonden voordat een Dataverse-omgeving werd gekoppeld [met behulp van on-premises gegevensgateways](/data-integration/gateway/service-gateway-app).

Gegevensgateways van een bestaande Power BI- of Power Apps-omgeving worden zichtbaar en u kunt deze opnieuw gebruiken in Customer Insights. De pagina met gegevensbronnen toont koppelingen om naar de Microsoft Power Platform-omgeving te gaan waar u on-premises gegevensgateways kunt bekijken en configureren.

## <a name="review-ingested-data"></a>Opgenomen gegevens bekijken

U ziet de naam van elke opgenomen gegevensbron, de status en de laatste keer dat de gegevens voor die bron zijn vernieuwd. U kunt de lijst met gegevensbronnen op elke kolom sorteren.

> [!div class="mx-imgBorder"]
> ![Gegevensbron toegevoegd.](media/configure-data-datasource-added.png "Gegevensbron toegevoegd")

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

Het laden van gegevens kan enige tijd vergen. Na een succesvolle vernieuwing kunnen de opgenomen gegevens worden bekeken vanaf de pagina **Entiteiten**. Zie [Entiteiten](entities.md) voor meer informatie.

## <a name="refresh-a-data-source"></a>Een gegevensbron vernieuwen

Gegevensbronnen kunnen automatisch worden vernieuwd of op aanvraag handmatig worden vernieuwd. 

Ga naar **Beheer** > **Systeem** > [**Planning**](system.md#schedule-tab) om geplande vernieuwingen van al uw opgenomen gegevensbronnen te configureren.

Volg deze stappen om een gegevensbron op aanvraag te vernieuwen:

1. Ga in doelgroepinzichten naar **Gegevens** > **Gegevensbronnen**.

2. Selecteer het verticale weglatingsteken naast de gegevensbron die u wilt vernieuwen en selecteer **Vernieuwen** uit de vervolgkeuzelijst.

3. De gegevensbron wordt nu geactiveerd voor een handmatige vernieuwing. Als u een gegevensbron vernieuwt, worden zowel het entiteitsschema als de gegevens bijgewerkt voor alle entiteiten die zijn opgegeven in de gegevensbron.

4. Selecteer **Vernieuwen stoppen** als u een bestaande vernieuwing wilt annuleren, waarna de gegevensbron terugkeert naar de laatste vernieuwingsstatus.

## <a name="delete-a-data-source"></a>Een gegevensbron verwijderen

1. Ga in doelgroepinzichten naar **Gegevens** > **Gegevensbronnen**.

2. Selecteer het verticale weglatingsteken naast de gegevensbron die u wilt verwijderen en selecteer **Verwijderen** uit het vervolgkeuzemenu.

3. Bevestig de verwijdering.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
