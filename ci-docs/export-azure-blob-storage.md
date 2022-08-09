---
title: Gegevens exporteren naar een Azure Blob Storage (preview)
description: Leer hoe u de verbinding configureert en exporteert naar Blob-opslag.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195698"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Gegevens exporteren naar een Azure Blob Storage (preview)

Sla uw Customer Insights-gegevens op in een Blob-opslag of gebruik deze om uw gegevens over te brengen naar andere toepassingen.

## <a name="prerequisites"></a>Vereisten

- Een naam en accountsleutel voor een [Azure Blob Storage-account](/azure/storage/blobs/create-data-lake-storage-account). Zie [Instellingen van opslagaccount in de Azure-portal beheren](/azure/storage/common/storage-account-manage) als u de naam en de sleutel wilt vinden.
- Een [Azure Blob Storage-container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Bekende beperkingen

- Voor Azure Blob Storage kunt u kiezen tussen [Standaardprestaties en Premium prestatielaag](/azure/storage/blobs/storage-blob-performance-tiers). Als u de Premium prestatielaag kiest, selecteert u de premium [blok-blobs als accounttype](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-blob-storage"></a>De verbinding met Blob Storage instellen

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Azure Blob Storage**.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Standaard zijn dit alleen beheerders. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Voer **Gebruikersnaam**, **Accountsleutel** en **Container** in voor uw Blob-opslagaccount.

1. Bekijk [Gegevensprivacy en naleving](connections.md#data-privacy-and-compliance) en selecteer **Ik ga akkoord**.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

Als u deze export wilt configureren, moet u [machtiging](export-destinations.md#set-up-a-new-export) voor dit verbindingstype hebben.

> [!IMPORTANT]
> Als u de instelling voor [voorlopig verwijderen](/azure/storage/blobs/soft-delete-blob-enable) in het Azure Blob Storage-account hebt ingeschakeld, mislukt het exporteren. Schakel voorlopig verwijderen uit om gegevens naar blobs te exporteren.

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen**.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie Azure Blob Storage. Neem contact op met een beheerder als er geen verbinding beschikbaar is.

1. Voer de naam in voor de export.

1. Voer de mapnaam in voor de Blob Storage.

1. Selecteer het vakje naast elk van de entiteiten die u naar deze bestemming wilt exporteren.

1. Selecteer **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Geëxporteerde gegevens worden opgeslagen in de Blob Storage-container die u hebt geconfigureerd. De volgende mappaden worden automatisch in uw container gemaakt:

- Voor bronentiteiten en entiteiten die door het systeem zijn gegenereerd:  
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  Voorbeeld: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > Export van entiteiten die een grote hoeveelheid gegevens bevatten, kan leiden tot meerdere CSV-bestanden in dezelfde map voor elke export. Het splitsen van exports gebeurt om prestatieredenen om de tijd die nodig is om een export te voltooien tot een minimum te beperken.

- De model.json voor de geëxporteerde entiteiten bevindt zich op het niveau *%ExportDestinationName%*.  
  
  Voorbeeld: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
