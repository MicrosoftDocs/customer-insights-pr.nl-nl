---
title: Customer Insights-gegevens exporteren naar InMobi
description: Ontdek hoe u de verbinding met InMobi configureert en exporteert.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195882"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Customer Insights-gegevens exporteren naar InMobi (preview)

Exporteer segmentlijsten of andere gegevens van uw Customer Insights-exemplaar naar [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Vereisten

- Een [InMobi-account](https://www.inmobi.com/) en beheerdersreferenties.
- Een naam en accountsleutel voor een [Azure Blob Storage-account](/azure/storage/blobs/create-data-lake-storage-account). Zie [Instellingen van opslagaccount in de Azure-portal beheren](/azure/storage/common/storage-account-manage) als u de naam en de sleutel wilt vinden.
- Een [Azure Blob Storage-container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) om InMobi-gegevens naar te exporteren.
- InMobi maakt een directe verbinding met uw Blob Storage en configureert een automatische import van uw gegevens naar InMobi. Neem contact op met uw InMobi-vertegenwoordiger om het proces te starten.

## <a name="known-limitations"></a>Bekende beperkingen

- Voor Azure Blob Storage kunt u kiezen tussen [Standaardprestaties en Premium prestatielaag](/azure/storage/blobs/storage-blob-performance-tiers). Als u de Premium prestatielaag kiest, selecteert u de premium [blok-blobs als accounttype](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-blob-storage"></a>De verbinding met Azure Blob Storage instellen

[Een verbinding met uw Azure Blob Storage](export-azure-blob-storage.md) instellen.

## <a name="configure-an-export"></a>Een export configureren

[Een export configureren](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
