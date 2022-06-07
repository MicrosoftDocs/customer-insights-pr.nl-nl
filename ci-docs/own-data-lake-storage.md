---
title: Uw eigen Azure Data Lake Storage Gen2-account gebruiken
author: mukeshpo
description: Meer informatie over de vereisten om uw eigen Azure Data Lake Storage-account te gebruiken voor het opslaan van Customer Insights-gegevens.
ms.author: mukeshpo
ms.date: 05/30/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 9fcd7645e34bf310ac3a1b98a0dd9a60598b19dc
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833918"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Uw eigen Azure Data Lake Storage Gen2-account gebruiken

Dynamics 365 Customer Insights geeft u de mogelijkheid om al uw gegevens op te slaan in [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction).

Door gegevens op te slaan in Data Lake Storage, gaat u ermee akkoord dat gegevens worden overgedragen naar en opgeslagen op de juiste geografische locatie voor die Azure-opslagaccount. Zie [Microsoft Vertrouwenscentrum](https://www.microsoft.com/trust-center) voor meer informatie.

Beheerders in Customer Insights kunnen [omgevingen maken](create-environment.md) en [de optie voor gegevensopslag opgeven](create-environment.md#step-2-configure-data-storage) in het proces.

## <a name="prerequisites-to-use-your-storage-account"></a>Vereisten voor het gebruik van uw opslagaccount

- Azure Data Lake Storage-accounts moeten zich in dezelfde Azure-regio bevinden die u hebt geselecteerd bij het maken van de Customer Insights-omgeving. U kunt de regio van de Customer Insights-omgeving controleren onder **Beheer** > **Systeem** > **Info**.
- Data Lake Storage moet Gen2 zijn en [hiërarchische naamruimte hebben ingeschakeld](/azure/storage/blobs/create-data-lake-storage-account). Gen1-opslagaccounts worden niet ondersteund.
- Een container met de naam `customerinsights` moet aanwezig zijn in het opslagaccount. U moet deze maken voordat u uw eigen Data Lake Storage in Customer Insights gebruikt. De beheerder die de Customer Insights-omgeving instelt, heeft de rol Bijdrager van Storage Blob-gegevens of Eigenaar van Storage Blob-gegevens nodig voor het opslagaccount of de `customerinsights`-container. Zie [Een opslagaccount maken](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal) voor meer informatie over het toewijzen van machtiging in een opslagaccount.

## <a name="connect-customer-insights-with-your-storage-account"></a>Customer Insights verbinden met uw opslagaccount

Wanneer u een nieuwe omgeving maakt, moet u ervoor zorgen dat het Data Lake Storage-account bestaat en dat aan alle vereisten is voldaan.

1. Stel tijdens het maken van de omgeving in de stap **Gegevensopslag** de optie **Uitvoergegevens opslaan** in op **Azure Data Lake Storage Gen2**.
1. Kies hoe u **uw opslag wilt verbinden**. U kunt kiezen tussen een op resources gebaseerde optie en een op abonnementen gebaseerde optie voor verificatie. Zie [Verbinding met een Azure Data Lake Storage-account maken via een Azure-service-principal](connect-service-principal.md) voor meer informatie.
   - Bij **Azure-abonnement** kiest u de waarden voor **Abonnement**, **Resourcegroep** en **Opslagaccount** die de `customerinsights`-container bevatten.
   - Geef voor **Accountsleutel** de **accountnaam** en **accountsleutel** voor het Data Lake Storage-account op. Het gebruik van deze verificatiemethode houdt in dat u wordt geïnformeerd als uw organisatie de sleutels rouleert. U moet [de omgevingsconfiguratie bijwerken](manage-environments.md#edit-an-existing-environment) met de nieuwe sleutel wanneer deze wordt gerouleerd.

Wanneer systeemprocessen zoals gegevensopname zijn voltooid, maakt het systeem overeenkomstige mappen in het opslagaccount. Gegevensbestanden en *model.json*-bestanden worden gemaakt en toegevoegd aan mappen op basis van de procesnaam.

Als u meerdere omgevingen van Customer Insights maakt en ervoor kiest om de uitvoerentiteiten van die omgevingen op te slaan in uw opslagaccount, maakt Customer Insights afzonderlijke mappen voor elke omgeving met `ci_environmentID` in de container.
