---
title: Customer Insights-gegevens exporteren naar InMobi
description: Ontdek hoe u de verbinding met InMobi configureert en exporteert.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9056538"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>Segmentlijst en andere gegevens exporteren naar InMobi (preview)

Exporteer segmentlijsten of andere gegevens van uw Customer Insights-exemplaar naar [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Vereisten

1. U hebt een [InMobi-account](https://www.inmobi.com/) en beheerdersreferenties.
1. U hebt de naam van een Azure Blob Storage-account en de bijbehorende accountsleutel. Zie [Accountinstellingen beheren in de Azure Portal](/azure/storage/common/storage-account-manage) voor meer informatie. Er is een container in het opslagaccount om inMobi-gegevens naartoe te exporteren. Zie [Een container maken](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) voor meer informatie.
1. InMobi maakt een directe verbinding met uw Blob Storage en configureert een automatische import van uw gegevens naar InMobi. Neem contact op met uw InMobi-vertegenwoordiger om het proces te starten.

## <a name="known-limitations"></a>Bekende beperkingen

1. Voor Azure Blob Storage kunt u kiezen tussen [Standaardprestaties en Premium prestatielaag](/azure/storage/blobs/storage-blob-performance-tiers). Als u de Premium prestatielaag kiest, selecteert u de premium [blok-blobs als accounttype](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>De verbinding met Azure Blob Storage instellen en een export configureren

1. Volg de instructies om [een verbinding in te stellen met uw Azure Blob Storage](export-azure-blob-storage.md).
2. Volg de instructies om [een export te configureren](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
