---
title: Customer Insights-gegevens naar een Azure Blob-opslag exporteren
description: Meer informatie over het configureren van de verbinding met Azure Blob-opslag.
ms.date: 09/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0986ee5caf5fa079994ca584fb2c4d9294ddb80b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596171"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Connector voor Azure Blob-opslag (preview)

Sla uw Customer Insights-gegevens op in een Azure Blob-opslag of gebruik deze om uw gegevens over te brengen naar andere toepassingen.

## <a name="configure-the-connector-for-azure-blob-storage"></a>De connector voor Azure Blob-opslag configureren

1. Ga in doelgroepinzichten naar **Beheer** > **Exportbestemmingen**.

1. Selecteer onder **Azure Blob-opslag** de optie **Instellen**.

1. Voer **accountnaam**, **accountsleutel** en **container** in voor uw Azure Blob-opslagaccount.
    - Zie voor meer informatie over het vinden van de naam en de accountsleutel van uw Azure-blobopslagaccount [Opslagaccountinstellingen beheren in de Azure-portal](/azure/storage/common/storage-account-manage).
    - Zie voor meer informatie over het maken van een container [Een container maken](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Geef uw bestemming een herkenbare naam in het veld **Weergavenaam**.

1. Selecteer **Volgende**.

1. Selecteer het vakje naast elk van de entiteiten die u naar deze bestemming wilt exporteren.

1. Selecteer **Opslaan**.

Geëxporteerde gegevens worden opgeslagen in de Azure Blob-opslagcontainer die u hebt geconfigureerd. De volgende mappaden worden automatisch in uw container gemaakt:

- Voor bronentiteiten en entiteiten die door het systeem zijn gegenereerd: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Voorbeeld: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- De model.json voor de geëxporteerde entiteiten bevindt zich op het niveau %ExportDestinationName%
  - Voorbeeld: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>De gegevens exporteren

U kunt [gegevens op aanvraag exporteren](export-destinations.md#export-data-on-demand). De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]