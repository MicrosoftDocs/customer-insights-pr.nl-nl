---
title: Gegevens opnemen uit Azure Synapse Analytics
description: Gebruik een database in Azure Synapse als een gegevensbron in Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7c758dccf7ea34dd7b8f80d05eff1ed12030526f
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646174"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Een Azure Synapse-gegevensbron verbinden (preview)

Azure Synapse Analytics is een enterprise analytics-service die sneller inzichten verkrijgt in datawarehouses en big data-systemen. Azure Synapse Analytics combineert het beste van SQL-technologieën die worden gebruikt in enterprise datawarehousing, Spark-technologieën die worden gebruikt voor big data, Data Explorer voor log- en tijdreeksanalyses, Pipelines voor gegevensintegratie en ETL/ELT, en diepe integratie met andere Azure-services zoals Power BI, Cosmos DB en AzureML.

Zie voor meer informatie [Azure Synapse-overzicht](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Vereisten

Er moet aan de volgende vereisten worden voldaan om de verbinding van Dynamics 365 Customer Insights naar Azure Synapse te configureren.

> [!IMPORTANT]
> Zorg ervoor dat u alle **roltoewijzingen** instelt zoals beschreven.  

## <a name="prerequisites-in-customer-insights"></a>Vereisten in Customer Insights

* U hebt de rol van **Beheerder** in Customer Insights. Meer informatie over [gebruikersmachtigingen in Customer Insights](permissions.md#assign-roles-and-permissions).

In Azure: 

- Een actief Azure-abonnement.

- Bij gebruik van een nieuw Azure Data Lake Storage Gen2-account heeft de *service-principal voor Customer Insights* de machtigingen voor **Bijdrager van Storage Blob-gegevens** nodig. Hier vindt u meer informatie over [verbinding maken met een Azure Data Lake Storage met een service-principal voor Customer Insights](connect-service-principal.md). Voor Data Lake Storage Gen2 **moet een** [hiërarchische naamruimte](/azure/storage/blobs/data-lake-storage-namespace) zijn ingeschakeld.

- In de resourcegroep waarin de Azure Synapse workspace zich bevindt, moeten aan de *service-principal* en de *gebruiker voor Customer Insights* minimaal machtigingen **Lezer**-machtigingen worden toegewezen. Zie voor meer informatie [Azure-rollen toewijzen met behulp van de Azure-portal](/azure/role-based-access-control/role-assignments-portal).

- De *gebruiker* heeft machtigingen van **Bijdrager van opslagblobgegevens** in de Azure Data Lake Storage Gen2-account nodig waar de gegevens zich bevinden en zijn gekoppeld aan de Azure Synapse-werkruimte. Meer informatie over [het gebruik van de Azure-portal om een Azure-rol toe te wijzen voor toegang tot blob- en wachtrijgegevens](/azure/storage/common/storage-auth-aad-rbac-portal) en [machtigingen van Bijdrager van opslagblobgegevens](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Voor de in de *[Azure Synapse workspace beheerde identiteit](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* zijn machtigingen van **Bijdrager van opslagblobgegevens** in de Azure Data Lake Storage Gen2-account vereist waarin de gegevens zich bevinden en zijn gekoppeld aan de Azure Synapse-werkruimte. Meer informatie over [het gebruik van de Azure-portal om een Azure-rol toe te wijzen voor toegang tot blob- en wachtrijgegevens](/azure/storage/common/storage-auth-aad-rbac-portal) en [machtigingen van Bijdrager van opslagblobgegevens](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- In de Azure Synapse workspace moet aan de *service-principal voor Customer Insights* de rol van **Synapse-beheerder** worden toegewezen. Zie voor meer informatie [Toegangsbeheer instellen voor uw Synapse-werkruimte](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Verbinding maken met data lake-databases in Azure Synapse Analytics

1. Ga naar **Gegevens** > **Gegevensbronnen**.

1. Selecteer **Gegevensbron toevoegen**.

1. Kies de **Azure Synapse Analytics (preview)**-methode.

1. Geef een **Naam** op voor de gegevensbron en selecteer **Volgende** om de gegevensbron te maken. 

1. Kies een [beschikbare verbinding](connections.md) met Azure Synapse Analytics of maak een nieuwe.

1. Kies een **Lake-database** vanuit de werkruimte die is verbonden in de geselecteerde Azure Synapse Analytics-verbinding en selecteer **Volgende**.

1. Selecteer de entiteiten die u wilt opnemen uit de verbonden database. 

1. Kies optioneel de gegevensentiteiten waarvoor gegevensprofilering is toegestaan. 

1. Selecteer **Opslaan** om uw selectie toe te passen en de opname te starten van de gegevens van uw nieuw gemaakte gegevensbron gekoppeld aan de Lake-databasetabellen in Azure Synapse Analytics.
