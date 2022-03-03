---
title: Customer Insights-gegevens exporteren naar Azure Data Lake Storage Gen2
description: Ontdek hoe u de verbinding met Azure Data Lake Storage Gen2 configureert.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: cc0b3aac11a33facc366e9c57071d1fb8be4ecc4
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231668"
---
# <a name="export-segment-list-and-other-data-to-azure-data-lake-storage-gen2-preview"></a>Segmentlijst en andere gegevens exporteren naar Azure Data Lake Storage Gen2 (preview)

Sla uw Customer Insights-gegevens op in een Data Lake Storage Gen2-account of gebruik deze om uw gegevens over te brengen naar andere toepassingen.

## <a name="known-limitations"></a>Bekende beperkingen

1. Voor Azure Data Lake Storage Gen2 kunt u kiezen tussen [Standaardprestaties en Premium prestatielaag](/azure/storage/blobs/create-data-lake-storage-account) wanneer u een opslagaccount maakt voor uw data lake. Als u de Premium prestatielaag kiest, selecteert u de premium blok-blobs als accounttype. 


## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>De verbinding instellen met Azure Data Lake Storage Gen2 


1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Azure Data Lake Gen 2** om de verbinding te configureren.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Voer **Accountnaam**, **Accountsleutel** **Container** voor uw Azure Data Lake Storage Gen2 in.
    - Voor informatie over het maken van een opslagaccount om te gebruiken met Azure Data Lake Storage Gen2, zie [Een opslagaccount maken](/azure/storage/blobs/create-data-lake-storage-account)​. 
    - Zie [De instellingen van het opslagaccount in de Azure-portal beheren](/azure/storage/common/storage-account-manage) voor meer informatie over het vinden van de Azure Data Lake Gen 2-opslagaccountnaam en -accountsleutel.

1. Selecteer **Opslaan** om de verbinding te voltooien. 

## <a name="configure-an-export"></a>Een export configureren

U kunt deze export configureren als u toegang hebt tot een verbinding van dit type. Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen** om een nieuwe export te maken.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie **Azure Data Lake**. Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.

1. Selecteer het vakje naast elk van de entiteiten die u naar deze bestemming wilt exporteren.

1. Selecteer **Opslaan**.

Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.

De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab). U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand). 

Geëxporteerde gegevens worden opgeslagen in de Azure Data Lake Gen 2-opslagcontainer die u hebt geconfigureerd. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
