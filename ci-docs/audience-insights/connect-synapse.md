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
ms.openlocfilehash: 163bef897880f0497bf00e90fd095621a2d14378
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/25/2022
ms.locfileid: "8356018"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Een Azure Synapse-gegevensbron verbinden (preview)

Azure Synapse Analytics is een enterprise analytics-service die sneller inzichten verkrijgt in datawarehouses en big data-systemen. Azure Synapse Analytics combineert het beste van SQL-technologieën die worden gebruikt in enterprise datawarehousing, Spark-technologieën die worden gebruikt voor big data, Data Explorer voor log- en tijdreeksanalyses, Pipelines voor gegevensintegratie en ETL/ELT, en diepe integratie met andere Azure-services zoals Power BI, Cosmos DB en AzureML.

Zie voor meer informatie [Azure Synapse-overzicht](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Vereisten

Er moet aan de volgende vereisten zijn voldaan om de verbinding van Customer Insights met Azure Synapse te configureren.

> [!IMPORTANT]
> Zorg ervoor dat u alle **roltoewijzingen** instelt zoals beschreven.  

## <a name="prerequisites-in-customer-insights"></a>Vereisten in Customer Insights

* U hebt de rol van **Beheerder** in Customer Insights. Meer informatie over [gebruikersmachtigingen in doelgroepinzichten](permissions.md#assign-roles-and-permissions).

In Azure: 

- Een actief Azure-abonnement.

- Als u een nieuwe Azure Data Lake Storage Gen2-account gebruikt, zijn voor de *service-principal voor doelgroepinzichten* machtigingen van **Bijdrager van opslagblobgegevens** vereist. Hier vindt u meer informatie over [verbinding maken met een Azure Data Lake Storage met een service-principal voor doelgroep-inzichten](connect-service-principal.md). Voor Data Lake Storage Gen2 **moet een** [hiërarchische naamruimte](/azure/storage/blobs/data-lake-storage-namespace) zijn ingeschakeld.

- In de resourcegroep waar de Azure Synapse-werkruimte zich bevindt, moeten aan de *service-principal* en de *gebruiker voor doelgroepinzichten* minimaal **Lezer**-machtigingen zijn toegewezen. Zie voor meer informatie [Azure-rollen toewijzen met behulp van de Azure-portal](/azure/role-based-access-control/role-assignments-portal).

- De *gebruiker* heeft machtigingen van **Bijdrager van opslagblobgegevens** in de Azure Data Lake Storage Gen2-account nodig waar de gegevens zich bevinden en zijn gekoppeld aan de Azure Synapse-werkruimte. Meer informatie over [het gebruik van de Azure-portal om een Azure-rol toe te wijzen voor toegang tot blob- en wachtrijgegevens](/azure/storage/common/storage-auth-aad-rbac-portal) en [machtigingen van Bijdrager van opslagblobgegevens](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Voor de in de *[Azure Synapse-werkruimte beheerde identiteit](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* zijn machtigingen van **Bijdrager van opslagblobgegevens** in de Azure Data Lake Storage Gen2-account vereist waarin de gegevens zich bevinden en zijn gekoppeld aan de Azure Synapse-werkruimte. Meer informatie over [het gebruik van de Azure-portal om een Azure-rol toe te wijzen voor toegang tot blob- en wachtrijgegevens](/azure/storage/common/storage-auth-aad-rbac-portal) en [machtigingen van Bijdrager van opslagblobgegevens](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- In de Azure Synapse-werkruimte moet voor de *service-principal voor doelgroepinzichten* de rol **Synapse-beheerder** zijn toegewezen. Zie voor meer informatie [Toegangsbeheer instellen voor uw Synapse-werkruimte](/azure/synapse-analytics/security/how-to-set-up-access-control).

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
