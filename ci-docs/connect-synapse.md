---
title: Een Azure Synapse-gegevensbron verbinden (preview)
description: Gebruik een database in Azure Synapse als een gegevensbron in Dynamics 365 Customer Insights.
ms.date: 03/25/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c4ae65613a02df38a30f907dae72d413bf1a702f
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052693"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Een Azure Synapse Analytics-gegevensbron verbinden (preview)

Azure Synapse Analytics is een enterprise analytics-service die sneller inzichten verkrijgt in datawarehouses en big data-systemen. Azure Synapse Analytics combineert het beste van SQL-technologieën die worden gebruikt in enterprise datawarehousing, Spark-technologieën die worden gebruikt voor big data, Data Explorer voor log- en tijdreeksanalyses, Pipelines voor gegevensintegratie en ETL/ELT, en diepe integratie met andere Azure-services zoals Power BI, Cosmos DB en AzureML.

Zie voor meer informatie [Azure Synapse-overzicht](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Vereisten

> [!IMPORTANT]
> Zorg ervoor dat u alle **roltoewijzingen** instelt zoals beschreven.  

**In Customer Insights**:

* U hebt de rol van **Beheerder** in Customer Insights. Meer informatie over [gebruikersmachtigingen in Customer Insights](permissions.md#assign-roles-and-permissions).

**In Azure**:

- Een actief Azure-abonnement.

- Bij gebruik van een nieuw Azure Data Lake Storage Gen2-account heeft de *service-principal voor Customer Insights* de machtigingen voor **Bijdrager van Storage Blob-gegevens** nodig. Hier vindt u meer informatie over [verbinding maken met een Azure Data Lake Storage met een service-principal voor Customer Insights](connect-service-principal.md). Voor Data Lake Storage Gen2 **moet een** [hiërarchische naamruimte](/azure/storage/blobs/data-lake-storage-namespace) zijn ingeschakeld.

- In de resourcegroep waarin de Azure Synapse workspace zich bevindt, moeten aan de *service-principal* en de *gebruiker voor Customer Insights* minimaal machtigingen **Lezer**-machtigingen worden toegewezen. Zie voor meer informatie [Azure-rollen toewijzen met behulp van de Azure-portal](/azure/role-based-access-control/role-assignments-portal).

- De *gebruiker* heeft machtigingen van **Bijdrager van opslagblobgegevens** in de Azure Data Lake Storage Gen2-account nodig waar de gegevens zich bevinden en zijn gekoppeld aan de Azure Synapse-werkruimte. Meer informatie over [het gebruik van de Azure-portal om een Azure-rol toe te wijzen voor toegang tot blob- en wachtrijgegevens](/azure/storage/common/storage-auth-aad-rbac-portal) en [machtigingen van Bijdrager van opslagblobgegevens](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Voor de in de *[Azure Synapse workspace beheerde identiteit](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* zijn machtigingen van **Bijdrager van opslagblobgegevens** in de Azure Data Lake Storage Gen2-account vereist waarin de gegevens zich bevinden en zijn gekoppeld aan de Azure Synapse-werkruimte. Meer informatie over [het gebruik van de Azure-portal om een Azure-rol toe te wijzen voor toegang tot blob- en wachtrijgegevens](/azure/storage/common/storage-auth-aad-rbac-portal) en [machtigingen van Bijdrager van opslagblobgegevens](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- In de Azure Synapse workspace moet aan de *service-principal voor Customer Insights* de rol van **Synapse-beheerder** worden toegewezen. Zie voor meer informatie [Toegangsbeheer instellen voor uw Synapse-werkruimte](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Verbinding maken met de data lake-database in Azure Synapse Analytics

1. Ga naar **Gegevens** > **Gegevensbronnen**.

1. Selecteer **Gegevensbron toevoegen**.

1. Kies de **Azure Synapse Analytics (preview)**-methode.

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Dialoogvenster om verbinding te maken met Synapse Analytics-gegevens":::
  
1. Voer een **Naam** voor de gegevensbron en een optionele **Beschrijving** in.

1. Kies een [beschikbare verbinding](connections.md) met Azure Synapse Analytics of maak een nieuwe.

1. Kies een **Database** vanuit de werkruimte die is verbonden in de geselecteerde Azure Synapse Analytics-verbinding en selecteer **Volgende**. Momenteel ondersteunen we alleen het databasetype *Lake-database*.

1. Selecteer de entiteiten die u wilt opnemen uit de verbonden database en selecteer **Volgende**.

1. Kies optioneel de gegevensentiteiten waarvoor gegevensprofilering is toegestaan.

1. Selecteer **Opslaan** om uw selectie toe te passen en de opname te starten van de gegevens van uw nieuw gemaakte gegevensbron gekoppeld aan de Lake-databasetabellen in Azure Synapse Analytics. De pagina **Gegevensbronnen** wordt geopend met de nieuwe gegevensbron met de status **Vernieuwen**.
