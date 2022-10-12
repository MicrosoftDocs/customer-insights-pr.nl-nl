---
title: Overzicht van gegevensbronnen
description: Informatie over hoe u gegevens uit verschillende bronnen kunt importeren of opnemen.
ms.date: 09/29/2022
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
ms.openlocfilehash: f89da3cf5b56e367bd673740f80cd82ec0907b28
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610046"
---
# <a name="data-sources-overview"></a>Overzicht van gegevensbronnen

Dynamics 365 Customer Insights biedt verbindingen om gegevens uit een uitgebreide set reeks bronnen aan te leveren. Verbinden met een gegevensbron wordt vaak *gegevensopname* genoemd. Na het opnemen van de gegevens, kunt u [harmoniseren](data-unification.md), inzichten genereren en de gegevens activeren voor het bouwen van gepersonaliseerde ervaringen.

## <a name="add-or-edit-data-sources"></a>Gegevensbronnen toevoegen of bewerken

U kunt gegevensbronnen bijvoegen of importeren in Customer Insights. De onderstaande koppelingen bevatten instructies voor het toevoegen en bewerken van gegevensbronnen.

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

## <a name="manage-existing-data-sources"></a>Bestaande gegevensbronnen beheren

Ga naar **Gegevens** > **Gegevensbronnen** om de naam van elke opgenomen gegevensbron, de bijbehorende status en de laatste keer dat de gegevens voor die bron zijn vernieuwd te bekijken. U kunt de lijst met gegevensbronnen sorteren op elke kolom of het zoekvak gebruiken om de gegevensbron te vinden die u wilt beheren.

Selecteer een gegevensbron om beschikbare acties te bekijken.

:::image type="content" source="media/data_sources_showmore.png" alt-text="Gegevensbron toegevoegd.":::

- [**Bewerk**](#add-or-edit-data-sources) de gegevensbron om de eigenschappen ervan te wijzigen.
- [**Vernieuw**](#refresh-data-sources) de gegevensbron om de nieuwste gegevens op te nemen.
- [**Verrijk**](data-sources-enrichment.md) de gegevensbron vóór harmonisatie.
- **Verwijder** de gegevensbron. Een gegevensbron kan alleen worden verwijderd als de gegevens niet worden gebruikt voor verwerking zoals harmonisatie, inzichten, activeringen of exportbewerkingen.

## <a name="refresh-data-sources"></a>Gegevensbronnen vernieuwen

Gegevensbronnen kunnen automatisch worden vernieuwd of op aanvraag handmatig worden vernieuwd. [On-premises gegevensbronnen](connect-power-query.md#add-data-from-on-premises-data-sources) vernieuwen volgens eigen planning, ingesteld tijdens gegevensopname. Voor tips voor het oplossen van problemen, zie [Vernieuwingsproblemen met op PPDF Power Query gebaseerde gegevensbron oplossen](connect-power-query.md#troubleshoot-ppdf-power-query-based-data-source-refresh-issues).

Voor gekoppelde gegevensbronnen verbruikt gegevensopname de nieuwste gegevens die beschikbaar zijn van die gegevensbron.

Ga naar **Beheer** > **Systeem** > [**Plannen**](schedule-refresh.md) om door het systeem geplande vernieuwingen van uw opgenomen gegevensbronnen te configureren.

Een gegevensbron op aanvraag vernieuwen:

1. Ga naar **Gegevens** > **Gegevensbronnen**.

1. Selecteer de gegevensbron die u wilt vernieuwen en selecteer **Vernieuwen**. De gegevensbron wordt nu geactiveerd voor een handmatige vernieuwing. Als u een gegevensbron vernieuwt, worden zowel het entiteitsschema als de gegevens bijgewerkt voor alle entiteiten die zijn opgegeven in de gegevensbron.

1. Selecteer de status om het deelvenster **Details van voortgang** te openen en de voortgang te bekijken. Als u de taak wilt annuleren, selecteert u **Taak annuleren** onder aan het deelvenster.

## <a name="corrupt-data-sources"></a>Beschadigde gegevensbronnen

Gegevens die worden opgenomen, kunnen beschadigde records bevatten waardoor het gegevensopnameproces kan worden voltooid met fouten of waarschuwingen.

> [!NOTE]
> Als de gegevensopname wordt voltooid met fouten, wordt de daaropvolgende verwerking (zoals harmonisatie of het maken van activiteiten) die gebruikmaakt van deze gegevensbron overgeslagen. Als de opname is voltooid met waarschuwingen, gaat de daaropvolgende verwerking door, maar worden sommige records mogelijk niet opgenomen.

Deze fouten zijn te zien in de taakdetails.

:::image type="content" source="media/corrupt-task-error.png" alt-text="Taakdetail met fout door beschadigde gegevens.":::

Beschadigde records worden weergegeven in door het systeem gemaakte entiteiten.

### <a name="fix-corrupt-data"></a>Beschadigde gegevens herstellen

1. U kunt de beschadigde gegevens weergeven door naar **Gegevens** > **Entiteiten** te gaan en naar de beschadigde entiteiten te zoeken in de sectie **Systeem**. Het naamgevingsschema van beschadigde entiteiten: 'DataSourceName_EntityName_corrupt'.

1. Selecteer het beschadigde entiteit en vervolgens het tabblad **Gegevens**.

1. Identificeer de beschadigde velden in een record en de reden.

   :::image type="content" source="media/corruption-reason.png" alt-text="Reden van beschadiging." lightbox="media/corruption-reason.png":::

   > [!NOTE]
   > **Gegevens** > **Entiteiten** laat slechts een deel van de beschadigde records zien. Als u alle beschadigde records wilt bekijken, exporteert u de bestanden naar een container in het opslagaccount met behulp van het [exportproces van Customer Insights](export-destinations.md). Als u uw eigen opslagaccount hebt gebruikt, kunt u ook de map Customer Insights in uw opslagaccount bekijken.

1. Herstel de beschadigde gegevens. Voor Azure Data Lake-gegevensbronnen kunt u bijvoorbeeld [de gegevens in de Data Lake Storage herstellen of de gegevenstypen in het bestand manifest/model.json bijwerken](connect-common-data-model.md#common-reasons-for-ingestion-errors-or-corrupt-data). Voor Power Query-gegevensbronnen herstelt u de gegevens in het bronbestand en [corrigeert u het gegevenstype in de transformatiestap](connect-power-query.md#data-type-does-not-match-data) op de pagina **Power Query - Query's bewerken**.

Na de volgende vernieuwing van de gegevensbron worden de gecorrigeerde records opgenomen in Customer Insights en doorgegeven aan downstream processen.

In een kolom 'verjaardag' bijvoorbeeld is het gegevenstype ingesteld op 'datum'. Voor een klantrecord is de verjaardag ingevoerd als '01/01/19777'. Het systeem markeert deze record als beschadigd. WIjzig in het bronsysteem de geboortedatum in '1977'. Na een automatische vernieuwing van gegevensbronnen heeft het veld nu een geldige indeling en wordt de record uit de beschadigde entiteit verwijderd.

[!INCLUDE [footer-include](includes/footer-banner.md)]
