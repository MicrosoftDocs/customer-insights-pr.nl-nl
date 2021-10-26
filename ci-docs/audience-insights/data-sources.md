---
title: Gegevensbronnen gebruiken om gegevens op te nemen
description: Meer informatie over hoe u gegevens uit verschillende bronnen kunt importeren.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: de31e1f25c08d0bcb5341c5f465b1999de48acf3
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645349"
---
# <a name="data-sources-overview"></a>Overzicht van gegevensbronnen

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

De doelgroepinzichten-mogelijkheid in Dynamics 365 Customer Insights maakt verbinding met gegevens uit uiteenlopende bronnen. Verbinden met een gegevensbron wordt vaak *gegevensopname* genoemd. Na het opnemen van de gegevens kunt u ze [samenvoegen](data-unification.md) en actie ondernemen.

## <a name="add-a-data-source"></a>Een gegevensbron toevoegen

Raadpleeg de gedetailleerde artikelen over het toevoegen van een gegevensbron, afhankelijk van de optie die u kiest.

U kunt een gegevensbron op drie manieren toevoegen:

- [Via tientallen Power Query-connectors](connect-power-query.md)
- [Via een Common Data Model-map](connect-common-data-model.md)
- [Via uw eigen Microsoft Dataverse-lake](connect-dataverse-managed-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>Gegevens toevoegen vanuit on-premises gegevensbronnen

Het opnemen van gegevens uit on-premises gegevensbronnen in doelgroepinzichten wordt ondersteund op basis van Microsoft Power Platform-gegevensstromen. Gegevensstromen kunnen worden ingeschakeld in Customer Insights door [het verstrekken van de URL van de Microsoft Dataverse-omgeving](create-environment.md) bij het opzetten van de omgeving.

Gegevensbronnen die worden gemaakt na het koppelen van een Dataverse-omgeving met Customer Insights maken standaard gebruik van [Power Platform-gegevensstromen](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Gegevensstromen ondersteunen on-premises connectiviteit met behulp van de gegevensgateway. Verwijder gegevensbronnen die al bestonden vóór een Dataverse-omgeving werd gekoppeld en maak deze opnieuw om [de on-premises gegevensgateways te gebruiken](/data-integration/gateway/service-gateway-app).

Gegevensgateways van een bestaande Power BI- of Power Apps-omgeving worden zichtbaar en u kunt deze opnieuw gebruiken in Customer Insights. De pagina met gegevensbronnen toont koppelingen om naar de Microsoft Power Platform-omgeving te gaan waar u on-premises gegevensgateways kunt bekijken en configureren.

## <a name="review-ingested-data"></a>Opgenomen gegevens bekijken

U ziet de naam van elke opgenomen gegevensbron, de status en de laatste keer dat de gegevens voor die bron zijn vernieuwd. U kunt de lijst met gegevensbronnen op elke kolom sorteren.

> [!div class="mx-imgBorder"]
> ![Gegevensbron toegevoegd.](media/configure-data-datasource-added.png "Gegevensbron toegevoegd")

|-Status  |Beschrijving  |
|---------|---------|
|Geslaagd   |Gegevensbron is opgenomen als een tijd wordt vermeld in de kolom **Vernieuwd**.
|Niet gestart   |De gegevensbron heeft nog geen gegevens opgenomen of bevindt zich nog in de conceptmodus.         |
|Vernieuwen    |De opname van gegevens wordt uitgevoerd. U kunt deze bewerking annuleren door **Stoppen met vernieuwen** te selecteren in de kolom **Acties**. Als u het vernieuwen van een gegevensbron stopt, keert het terug naar de laatste vernieuwingsstatus.       |
|Mislukt     |Er zijn fouten opgetreden bij de gegevensopname.         |

Selecteer de waarde in de kolom **Status** van een willekeurige gegevensbron voor meer details. Vouw in het deelvenster **Voortgangsgegevens** de optie **Gegevensbronnen** uit. Selecteer **Details weergeven** voor meer informatie over de vernieuwingsstatus, inclusief foutdetails en downstream procesupdates.

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
