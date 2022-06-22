---
title: Gegevensbronnen gebruiken om gegevens op te nemen
description: Meer informatie over hoe u gegevens uit verschillende bronnen kunt importeren.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: overview
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: e22977107565a0b28b74f41576a1c7ccc74f6dc1
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011743"
---
# <a name="data-sources-overview"></a>Overzicht van gegevensbronnen

Dynamics 365 Customer Insights biedt verbindingen om gegevens uit een uitgebreide set reeks bronnen aan te leveren. Verbinden met een gegevensbron wordt vaak *gegevensopname* genoemd. Na het opnemen van de gegevens, kunt u [harmoniseren](data-unification.md), inzichten genereren en de gegevens activeren voor het bouwen van gepersonaliseerde ervaringen.

## <a name="add-data-sources"></a>Gegevensbronnen toevoegen

U kunt gegevensbronnen bijvoegen of importeren in Customer Insights. De onderstaande links bevatten instructies voor het toevoegen van gegevensbronnen.

**Een gegevensbron bijvoegen**

Als u gegevens hebt voorbereid in een van de Azure-gegevensservices van Microsoft, kan Customer Insights eenvoudig verbinding maken met de gegevensbron zonder dat u de gegevens opnieuw hoeft op te nemen. Selecteer een van de volgende opties:
- [Azure Data Lake Storage (csv- of parquet-bestanden in een Common Data Model-map)](connect-common-data-model.md)
- [Azure Synapse Analytics (Lake-databases)](connect-synapse.md)
- [Microsoft Dataverse data lake](connect-dataverse-managed-lake.md)

**Importeren en transformeren**

Als u on-premises gegevensbronnen, Microsoft-gegevens of gegevens van derden gebruikt, importeert en transformeert u de gegevens met Power Query-connectors.
- [Power Query-connectors](connect-power-query.md)

## <a name="review-data-sources"></a>Gegevensbronnen beoordelen

Als uw omgeving is geconfigureerd om Customer Insights-opslag te gebruiken en u lokale gegevensbronnen gebruikt, gebruikt u Power Platform-gegevensstromen. Met Power Platform-gegevensstromen kunt u gedeelde gegevensbronnen en gegevensbronnen bekijken die door anderen worden beheerd. Op de pagina **Gegevensbronnen** worden de gegevensbronnen in drie secties vermeld:
- **Gedeeld**: gegevensbronnen die kunnen worden beheerd door alle Customer Insights-beheerders. Power Platform-gegevensstromen, uw eigen opslagaccount en koppelen aan een door Dataverse beheerd data lake zijn voorbeelden van gedeelde gegevensbronnen.
- **Beheerd door mij**: Power Platform-gegevensstromen die alleen door u zijn gemaakt en worden beheerd. Andere Customer Insights-beheerders kunnen deze gegevensstromen alleen bekijken, maar niet bewerken, vernieuwen of verwijderen.
- **Beheerd door anderen**: Power Platform-gegevensstromen die door andere beheerders zijn gemaakt. Je kunt deze alleen bekijken. Er wordt een vermelding weergegeven van de eigenaar van de gegevensstroom waarmee contact kan worden opgenomen voor hulp.
> [!NOTE]
> Alle entiteiten kunnen worden bekeken en gebruikt door andere gebruikers. Hoewel gegevensbronnen eigendom zijn van de gebruiker die ze heeft gemaakt, kunnen de resulterende entiteiten van de gegevensopname door elke gebruiker van Customer Insights worden gebruikt.

Als uw omgeving geen gebruik maakt van Power Platform-gegevensstromen, bevat de pagina **Gegevensbronnen** bevat alleen een lijst met alle gegevensbronnen. Er worden geen secties weergegeven.

Ga naar **Gegevens** > **Gegevensbronnen** om de naam van elke opgenomen gegevensbron, de bijbehorende status en de laatste keer dat de gegevens voor die bron zijn vernieuwd te bekijken. U kunt de lijst met gegevensbronnen op elke kolom sorteren.

:::image type="content" source="media/configure-data-datasource-added.png" alt-text="Gegevensbron toegevoegd.":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Het laden van gegevens kan enige tijd vergen. Na een succesvolle vernieuwing kunnen de opgenomen gegevens worden bekeken vanaf de pagina **Entiteiten**. Zie [Entiteiten](entities.md) voor meer informatie.

## <a name="refresh-data-sources"></a>Gegevensbronnen vernieuwen

Gegevensbronnen kunnen automatisch worden vernieuwd of op aanvraag handmatig worden vernieuwd. [On-premises gegevensbronnen](connect-power-query.md#add-data-from-on-premises-data-sources) vernieuwen volgens eigen planning, ingesteld tijdens gegevensopname. Voor gekoppelde gegevensbronnen verbruikt gegevensopname de nieuwste gegevens die beschikbaar zijn van die gegevensbron.

Ga naar **Beheer** > **Systeem** > [**Plannen**](system.md#schedule-tab) om door het systeem geplande vernieuwingen van uw opgenomen gegevensbronnen te configureren.

Volg deze stappen om een gegevensbron op aanvraag te vernieuwen:

1. Ga naar **Gegevens** > **Gegevensbronnen**.

1. Selecteer het verticale weglatingsteken (&vellip;) naast de gegevensbron die u wilt vernieuwen en selecteer **Vernieuwen** uit de vervolgkeuzelijst. De gegevensbron wordt nu geactiveerd voor een handmatige vernieuwing. Als u een gegevensbron vernieuwt, worden zowel het entiteitsschema als de gegevens bijgewerkt voor alle entiteiten die zijn opgegeven in de gegevensbron.

1. Selecteer **Vernieuwen stoppen** als u een bestaande vernieuwing wilt annuleren, waarna de gegevensbron terugkeert naar de laatste vernieuwingsstatus.

## <a name="delete-a-data-source"></a>Een gegevensbron verwijderen

Een gegevensbron kan alleen worden verwijderd als de gegevens niet worden gebruikt voor verwerking zoals harmonisatie, inzichten, activeringen of exportbewerkingen.

1. Ga naar **Gegevens** > **Gegevensbronnen**.

2. Selecteer het verticale weglatingsteken (&vellip;) naast de gegevensbron die u wilt verwijderen en selecteer **Verwijderen** uit het vervolgkeuzemenu.

3. Bevestig de verwijdering.


[!INCLUDE [footer-include](includes/footer-banner.md)]
