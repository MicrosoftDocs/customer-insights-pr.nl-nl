---
title: Customer Insights-gegevens exporteren naar Azure Data Lake Storage Gen2
description: Ontdek hoe u de verbinding met Azure Data Lake Storage Gen2 configureert.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596631"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Connector voor Azure Data Lake Storage Gen2 (preview)

Sla uw Customer Insights-gegevens op in Azure Data Lake Storage Gen2 of gebruik deze om uw gegevens over te brengen naar andere toepassingen.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>De connector voor Azure Data Lake Storage Gen2 configureren

1. Ga in doelgroepinzichten naar **Beheer** > **Exportbestemmingen**.

1. Selecteer onder **Azure Data Lake Storage Gen2** de optie **Instellen**.

1. Geef uw bestemming een herkenbare naam in het veld **Weergavenaam**.

1. Voer **Accountnaam**, **Accountsleutel** **Container** voor uw Azure Data Lake Storage Gen2 in.
    - Voor informatie over het maken van een opslagaccount om te gebruiken met Azure Data Lake Storage Gen2, zie [Een opslagaccount maken](/azure/storage/blobs/create-data-lake-storage-account)​. 
    - Zie [Instellingen voor opslagaccount beheren in de Azure-portal](/azure/storage/common/storage-account-manage)​voor meer informatie over het vinden van de accountnaam en accountsleutel voor Azure Data Lake Gen2.

1. Selecteer **Volgende**.

1. Selecteer het vakje naast elk van de entiteiten die u naar deze bestemming wilt exporteren.

1. Selecteer **Opslaan**.

## <a name="export-the-data"></a>De gegevens exporteren

U kunt [gegevens op aanvraag exporteren](export-destinations.md#export-data-on-demand). De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab).