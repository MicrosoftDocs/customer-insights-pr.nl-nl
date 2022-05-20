---
title: Gegevensbronnen gebruiken om gegevens op te nemen
description: Meer informatie over hoe u gegevens uit verschillende bronnen kunt importeren.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 1fe8d6e8098831ecc8ff28e571340c56a654de6d
ms.sourcegitcommit: a50c5e70d2baf4db41a349162fd1b1f84c3e03b6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2022
ms.locfileid: "8739202"
---
# <a name="data-sources-overview"></a>Overzicht van gegevensbronnen



Dynamics 365 Customer Insights maakt verbinding met gegevens uit een uitgebreide set reeks bronnen. Verbinden met een gegevensbron wordt vaak *gegevensopname* genoemd. Na het opnemen van de gegevens kunt u ze [samenvoegen](data-unification.md) en actie ondernemen.

## <a name="add-a-data-source"></a>Een gegevensbron toevoegen

Raadpleeg de gedetailleerde artikelen voor het toevoegen van een gegevensbron, afhankelijk van de optie die u kiest.

U kunt de volgende gegevensbronnen toevoegen:

- [Via tientallen Power Query-connectoren](connect-power-query.md)
- [Via een Common Data Model-map](connect-common-data-model.md)
- [Via uw eigen Microsoft Dataverse-lake](connect-dataverse-managed-lake.md)
- [Vanuit een Azure Synapse Analytics-database](connect-synapse.md)

## <a name="add-data-from-on-premises-data-sources"></a>Gegevens toevoegen vanuit on-premises gegevensbronnen

Het opnemen van gegevens uit on-premises gegevensbronnen wordt ondersteund op basis van Microsoft Power Platform-gegevensstromen. U kunt gegevensstromen in Customer Insights inschakelen door [de omgevings-URL voor Microsoft Dataverse te verstrekken](create-environment.md) bij het instellen van de omgeving.

Gegevensbronnen die zijn gemaakt na het koppelen van een Dataverse-omgeving met Customer Insights maken standaard gebruik van [Power Platform-gegevensstromen](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Gegevensstromen ondersteunen on-premises connectiviteit met behulp van de gegevensgateway. U kunt gegevensbronnen verwijderen en opnieuw maken die bestonden voordat een Dataverse-omgeving werd gekoppeld [met behulp van on-premises gegevensgateways](/data-integration/gateway/service-gateway-app).

Gegevensgateways van een bestaande Power BI- of Power Apps-omgeving worden zichtbaar en u kunt deze opnieuw gebruiken in Customer Insights. De pagina met gegevensbronnen toont koppelingen om naar de Microsoft Power Platform-omgeving te gaan waar u on-premises gegevensgateways kunt bekijken en configureren.

> [!IMPORTANT]
> Zorg ervoor dat uw gateways zijn bijgewerkt naar de nieuwste versie. U kunt een update installeren en een gateway opnieuw configureren vanaf een prompt die direct op het gatewayscherm wordt weergegeven of [de meest recente versie downloaden](https://powerapps.microsoft.com/downloads/). Als u niet de nieuwste gatewayversie gebruikt, mislukt het vernieuwen van de gegevensstroom met foutmeldingen zoals **Het trefwoord wordt niet ondersteund: configuratie-eigenschappen. Parameternaam: trefwoord**.

## <a name="review-ingested-data"></a>Opgenomen gegevens bekijken
Als uw omgeving Power Platform-gegevensstromen bevat, bevat de pagina **Gegevensbronnen** drie secties: 
- **Gedeeld**: gegevensbronnen die kunnen worden beheerd door alle Customer Insights-beheerders. Power BI-gegevensstromen, uw eigen opslagaccount en koppelen aan een door Dataverse beheerd data lake zijn voorbeelden van gedeelde gegevensbronnen.
- **Beheerd door mij**: Power Platform-gegevensstromen die alleen door u zijn gemaakt en kunnen worden beheerd. Andere Customer Insights-beheerders kunnen deze gegevensstromen alleen bekijken, maar niet bewerken, vernieuwen of verwijderen.
- **Beheerd door anderen**: Power Platform-gegevensstromen die door andere beheerders zijn gemaakt. Je kunt deze alleen bekijken. Er wordt een vermelding weergegeven van de eigenaar van de gegevensstroom waarmee contact kan worden opgenomen voor hulp.
> [!NOTE]
> Alle entiteiten kunnen worden bekeken en gebruikt door andere gebruikers. Gebruikerscontextualiteit is alleen van toepassing op de gegevensbronnen en niet op de entiteiten die het resultaat zijn van deze gegevensstromen.

Als geen Power Platform-gegevensstromen worden gebruikt, ziet u geen groepen of secties. De pagina **Gegevensbronnen** bevat alleen een lijst van alle gegevensbronnen.

U ziet de naam van elke opgenomen gegevensbron, de status en de laatste keer dat de gegevens voor die bron zijn vernieuwd. U kunt de lijst met gegevensbronnen op elke kolom sorteren.

> [!div class="mx-imgBorder"]
> ![Gegevensbron toegevoegd.](media/configure-data-datasource-added.png "Gegevensbron toegevoegd")

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Het laden van gegevens kan enige tijd vergen. Na een succesvolle vernieuwing kunnen de opgenomen gegevens worden bekeken vanaf de pagina **Entiteiten**. Zie [Entiteiten](entities.md) voor meer informatie.

## <a name="refresh-a-data-source"></a>Een gegevensbron vernieuwen

Gegevensbronnen kunnen automatisch worden vernieuwd of op aanvraag handmatig worden vernieuwd. 

Ga naar **Beheer** > **Systeem** > [**Planning**](system.md#schedule-tab) om geplande vernieuwingen van al uw opgenomen gegevensbronnen te configureren.

Volg deze stappen om een gegevensbron op aanvraag te vernieuwen:

1. Ga naar **Gegevens** > **Gegevensbronnen**.

2. Selecteer het verticale weglatingsteken naast de gegevensbron die u wilt vernieuwen en selecteer **Vernieuwen** uit de vervolgkeuzelijst.

3. De gegevensbron wordt nu geactiveerd voor een handmatige vernieuwing. Als u een gegevensbron vernieuwt, worden zowel het entiteitsschema als de gegevens bijgewerkt voor alle entiteiten die zijn opgegeven in de gegevensbron.

4. Selecteer **Vernieuwen stoppen** als u een bestaande vernieuwing wilt annuleren, waarna de gegevensbron terugkeert naar de laatste vernieuwingsstatus.

## <a name="delete-a-data-source"></a>Een gegevensbron verwijderen

1. Ga naar **Gegevens** > **Gegevensbronnen**.

2. Selecteer het verticale weglatingsteken naast de gegevensbron die u wilt verwijderen en selecteer **Verwijderen** uit het vervolgkeuzemenu.

3. Bevestig de verwijdering.


[!INCLUDE [footer-include](includes/footer-banner.md)]
