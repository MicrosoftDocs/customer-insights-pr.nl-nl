---
title: Customer Insights-gegevens exporteren naar Azure Data Lake Storage Gen2
description: Ontdek hoe u de verbinding met Azure Data Lake Storage Gen2 configureert.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: c4408e52550b6648e2a001041dc0acdb5063d6a6ef1b8e4bba3321bf25fefcfc
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031973"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a>De verbinding instellen met Azure Data Lake Storage Gen2 (preview)

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
