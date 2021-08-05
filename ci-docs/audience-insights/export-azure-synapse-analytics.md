---
title: Customer Insights-gegevens exporteren naar Azure Synapse Analytics
description: Meer informatie over het configureren van de verbinding met Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7ee57aa9e86ebf9bd1989d88750642f0b01bd4bf
ms.sourcegitcommit: f18635c29bb25d9e424a3f5825dc2696278450cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "6327358"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Gegevens exporteren naar Azure Synapse Analytics (preview)

Azure Synapse is een analyseservice waarmee de tijd tot inzicht in datawarehouses en big data-systemen wordt versneld. U kunt uw Customer Insights-gegevens opnemen en gebruiken in [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Vereisten

Er moet aan de volgende vereisten zijn voldaan om de verbinding van Customer Insights met Azure Synapse te configureren.

> [!NOTE]
> Zorg ervoor dat u alle **roltoewijzingen** instelt zoals beschreven.  

## <a name="prerequisites-in-customer-insights"></a>Vereisten in Customer Insights

* U hebt de rol van **Beheerder** in doelgroepinzichten. Meer informatie over [het instellen van gebruikersmachtigingen in doelgroepinzichten](permissions.md#assign-roles-and-permissions)

In Azure: 

- Een actief Azure-abonnement.

- Als u een nieuwe Azure Data Lake Storage Gen2-account gebruikt, zijn voor de *service-principal voor doelgroepinzichten* machtigingen van **Bijdrager van opslagblobgegevens** vereist. Meer informatie over het [maken van verbinding met een Azure Data Lake Storage Gen2-account met de service-principal van Azure voor doelgroepinzichten](connect-service-principal.md). Voor Data Lake Storage Gen2 **moet een** [hiërarchische naamruimte](/azure/storage/blobs/data-lake-storage-namespace) zijn ingeschakeld.

- In de resourcegroep waar de Azure Synapse-werkruimte zich bevindt, moeten aan de *service-principal* en de *gebruiker voor doelgroepinzichten* minimaal **Lezer**-machtigingen zijn toegewezen. Zie voor meer informatie [Azure-rollen toewijzen met behulp van de Azure-portal](/azure/role-based-access-control/role-assignments-portal).

- De *gebruiker* heeft machtigingen van **Bijdrager van opslagblobgegevens** in de Azure Data Lake Storage Gen2-account nodig waar de gegevens zich bevinden en zijn gekoppeld aan de Azure Synapse-werkruimte. Meer informatie over [het gebruik van de Azure-portal om een Azure-rol toe te wijzen voor toegang tot blob- en wachtrijgegevens](/azure/storage/common/storage-auth-aad-rbac-portal) en [machtigingen van Bijdrager van opslagblobgegevens](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Voor de in de *[Azure Synapse-werkruimte beheerde identiteit](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* zijn machtigingen van **Bijdrager van opslagblobgegevens** in de Azure Data Lake Storage Gen2-account vereist waarin de gegevens zich bevinden en zijn gekoppeld aan de Azure Synapse-werkruimte. Meer informatie over [het gebruik van de Azure-portal om een Azure-rol toe te wijzen voor toegang tot blob- en wachtrijgegevens](/azure/storage/common/storage-auth-aad-rbac-portal) en [machtigingen van Bijdrager van opslagblobgegevens](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- In de Azure Synapse-werkruimte moet voor de *service-principal voor doelgroepinzichten* de rol **Synapse-beheerder** zijn toegewezen. Zie voor meer informatie [Toegangsbeheer instellen voor uw Synapse-werkruimte](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>De verbinding instellen en exporteren naar Azure Synapse

### <a name="configure-a-connection"></a>Een verbinding configureren

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Azure Synapse Analytics** of selecteer **Instellen** op de tegel **Azure Synapse Analytics** om de verbinding te configureren.

1. Geef uw verbinding een herkenbare naam in het veld Weergavenaam. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Selecteer of zoek naar het abonnement waarin u de Customer Insights-gegevens wilt gebruiken. Zodra een abonnement is geselecteerd, kunt u ook **Werkruimte**, **Opslagaccount** en **Container** selecteren.

1. Selecteer **Opslaan** om de verbinding op te slaan.

### <a name="configure-an-export"></a>Een export configureren

U kunt deze export configureren als u toegang hebt tot een verbinding van dit type. Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen** om een nieuwe export te maken.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie **Azure Synapse Analytics**. Als u deze sectienaam niet ziet, zijn er geen [verbindingen](connections.md) van dit type voor u beschikbaar.

1. Zorg voor een herkenbare **weergavenaam** voor uw export en een **databasenaam**.

1. Geef aan welke entiteiten u wilt exporteren naar Azure Synapse Analytics.
   > [!NOTE]
   > Gegevensbronnen die zijn gebaseerd op een [Common Data Model-map](connect-common-data-model.md), worden niet ondersteund.

2. Selecteer **Opslaan**.

Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.

De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab). U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand).

### <a name="update-an-export"></a>Een export bijwerken

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Bewerken** in de export die u wilt bijwerken.

   - Kies **Toevoegen** of **Verwijderen** om entiteiten toe te voegen aan of te verwijderen uit de selectie. Als entiteiten uit de selectie worden verwijderd, worden ze niet verwijderd uit de Synapse Analytics-database. Bij toekomstige gegevensvernieuwingen worden de verwijderde entiteiten in die database echter niet bijgewerkt.

   - Met **De databasenaam wijzigen** wordt een nieuwe Synapse Analytics-database gemaakt. De database met de naam die eerder is geconfigureerd, ontvangt bij toekomstige vernieuwingen geen updates.
