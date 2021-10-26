---
title: Customer Insights-gegevens naar een Azure Blob Storage exporteren
description: Leer hoe u de verbinding configureert en exporteert naar Blob-opslag.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d02c09a1869d0099db4861b65ac8ff006914873e
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/06/2021
ms.locfileid: "7605832"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Segmentlijst en andere gegevens exporteren naar Azure Blob Storage (preview)

Sla uw Customer Insights-gegevens op in een Blob-opslag of gebruik deze om uw gegevens over te brengen naar andere toepassingen.

## <a name="known-limitations"></a>Bekende beperkingen

1. Voor Azure Blob Storage kunt u kiezen tussen [Standaardprestaties en Premium prestatielaag](/azure/storage/blobs/storage-blob-performance-tiers). Als u de Premium prestatielaag kiest, selecteert u de premium [blok-blobs als accounttype](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-blob-storage"></a>De verbinding met Blob Storage instellen

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Azure Blob Storage** om de verbinding te configureren.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Voer **Gebruikersnaam**, **Accountsleutel** en **Container** in voor uw Blob-opslagaccount.
    - Zie [De instellingen van het opslagaccount in de Azure Portal beheren](/azure/storage/common/storage-account-manage) voor meer informatie over het vinden van de Blob Storage-accountnaam en -accountsleutel.
    - Zie voor meer informatie over het maken van een container [Een container maken](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Selecteer **Opslaan** om de verbinding te voltooien. 

## <a name="configure-an-export"></a>Een export configureren

U kunt deze export configureren als u toegang hebt tot een verbinding van dit type. Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.

> [!IMPORTANT]
> Als u de instelling voor voorlopig verwijderen in het Azure Blob-opslagaccount hebt ingeschakeld, mislukt het exporteren. Schakel voorlopig verwijderen uit om gegevens naar blobs te exporteren. Zie [Voorlopig verwijderen voor blobs inschakelen](/azure/storage/blobs/soft-delete-blob-enable.md) voor meer informatie

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Bestemming toevoegen** om een nieuwe export te maken.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie Azure Blob Storage. Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.

1. Selecteer het vakje naast elk van de entiteiten die u naar deze bestemming wilt exporteren.

1. Selecteer **Opslaan**.

Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.

De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab).     

U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand). 

Geëxporteerde gegevens worden opgeslagen in de Blob Storage-container die u hebt geconfigureerd. De volgende mappaden worden automatisch in uw container gemaakt:

- Voor bronentiteiten en entiteiten die door het systeem zijn gegenereerd:   
  `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`  
  - Voorbeeld: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
 
- Het model.json voor de geëxporteerde entiteiten bevindt zich op het %ExportDestinationName%-niveau.  
  - Voorbeeld: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE[footer-include](../includes/footer-banner.md)]
