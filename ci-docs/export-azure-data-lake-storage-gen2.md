---
title: Gegevens exporteren naar Azure Data Lake Storage Gen2 (preview)
description: Ontdek hoe u de verbinding met Azure Data Lake Storage Gen2 configureert.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196434"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Gegevens exporteren naar Azure Data Lake Storage Gen2 (preview)

Sla uw Customer Insights-gegevens op in een Data Lake Storage Gen2-account of gebruik deze om uw gegevens over te brengen naar andere toepassingen.

## <a name="prerequisites"></a>Vereisten

- Een [opslagaccount voor gebruik met Azure Data Lake Gen 2](/azure/storage/blobs/create-data-lake-storage-account). Zie [Instellingen van opslagaccount in de Azure-portal beheren](/azure/storage/common/storage-account-manage) als u de naam en de sleutel van het opslagaccount wilt vinden.
- Een [Azure Blob Storage-container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Bekende beperkingen

- Maak voor Azure Data Lake Storage Gen2 een keuze tussen [Standaardprestaties en Premium prestatielaag](/azure/storage/blobs/create-data-lake-storage-account). Als u de Premium prestatielaag kiest, selecteert u de premium [blok-blobs als accounttype](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Verbinding instellen met Azure Data Lake Storage Gen2

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Azure Data Lake Gen 2**.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Standaard zijn dit alleen beheerders. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Voer **Accountnaam**, **Accountsleutel** **Container** voor uw Azure Data Lake Storage Gen2 in.

1. Bekijk [Gegevensprivacy en naleving](connections.md#data-privacy-and-compliance) en selecteer **Ik ga akkoord**.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen**.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie Azure Data Lake. Neem contact op met een beheerder als er geen verbinding beschikbaar is.

1. Voer de naam in voor de export.

1. Voer de mapnaam in voor de Azure Data Lake Storage Gen2-opslag.

1. Selecteer het vakje naast elk van de entiteiten die u naar deze bestemming wilt exporteren.

1. Selecteer **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Geëxporteerde gegevens worden opgeslagen in de Azure Data Lake Gen 2-opslagcontainer die u hebt geconfigureerd.

> [!TIP]
> Export van entiteiten die een grote hoeveelheid gegevens bevatten, kan leiden tot meerdere CSV-bestanden in dezelfde map voor elke export. Het splitsen van exports gebeurt om prestatieredenen om de tijd die nodig is om een export te voltooien tot een minimum te beperken.

[!INCLUDE [footer-include](includes/footer-banner.md)]
