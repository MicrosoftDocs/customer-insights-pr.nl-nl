---
title: Gegevens exporteren naar Azure Synapse Analytics (preview)
description: Ontdek hoe u de verbinding met Azure Synapse Analytics configureert.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f9c9ee55f2874ae1dcaf82f2ff17ed0fbbb7804d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196388"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Gegevens exporteren naar Azure Synapse Analytics (preview)

Azure Synapse is een analyseservice waarmee de tijd tot inzicht in datawarehouses en big data-systemen wordt versneld. U kunt uw Customer Insights-gegevens opnemen en gebruiken in [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Vereisten

> [!NOTE]
> Zorg ervoor dat u alle **roltoewijzingen** instelt zoals beschreven.

- Uw Azure Active Directory-gebruikersaccount (AD) moet de rol van [Beheerder](permissions.md#assign-roles-and-permissions) hebben in Customer Insights.

In Azure:

- Een actief Azure-abonnement.

- Bij gebruik van een nieuw Azure Data Lake Storage Gen2-account heeft de [service-principal voor Customer Insights](connect-service-principal.md) machtigingen voor **Inzender van opslagblobgegevens**. Voor Data Lake Storage Gen2 **moet een** [hiërarchische naamruimte](/azure/storage/blobs/data-lake-storage-namespace) zijn ingeschakeld.

- In de resourcegroep waarin de Azure Synapse workspace zich bevindt, moeten aan de *service-principal* en de *Azure AD-gebruiker met beheerdersmachtigingen in Customer Insights* minimaal [machtigingen](/azure/role-based-access-control/role-assignments-portal) van **Lezer** worden toegewezen.

- De *Azure AD-gebruiker met beheerdersmachtigingen in Customer Insights* heeft machtigingen van **Inzender van opslagblobgegevens** in het Azure Data Lake Storage Gen2-account waar de gegevens zich bevinden en is gekoppeld aan de Azure Synapse workspace. Meer informatie over [het gebruik van de Azure-portal om een Azure-rol toe te wijzen voor toegang tot blob- en wachtrijgegevens](/azure/storage/common/storage-auth-aad-rbac-portal) en [machtigingen van Bijdrager van opslagblobgegevens](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- De in de *[Azure Synapse workspace beheerde identiteit](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* heeft machtigingen van **Inzender van opslagblobgegevens** in de Azure Data Lake Storage Gen2-account waarin de gegevens zich bevinden en is gekoppeld aan de Azure Synapse workspace. Meer informatie over [het gebruik van de Azure-portal om een Azure-rol toe te wijzen voor toegang tot blob- en wachtrijgegevens](/azure/storage/common/storage-auth-aad-rbac-portal) en [machtigingen van Bijdrager van opslagblobgegevens](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- In de Azure Synapse workspace is de *service-principal voor Customer Insights* [toegewezen aan de rol](/azure/synapse-analytics/security/how-to-set-up-access-control) van **Synapse-beheerder**.

## <a name="set-up-connection-to-azure-synapse"></a>Verbinding instellen Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Azure Synapse Analytics**.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Standaard zijn dit alleen beheerders. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Selecteer of zoek naar het abonnement waarin u de Customer Insights-gegevens wilt gebruiken. Zodra een abonnement is geselecteerd, kunt u ook **Werkruimte**, **Opslagaccount** en **Container** selecteren.

1. Bekijk [Gegevensprivacy en naleving](connections.md#data-privacy-and-compliance) en selecteer **Ik ga akkoord**.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

[!INCLUDE [export-permission-include](includes/export-permission.md)]Om de export met een gedeelde verbinding te configureren, hebt u minimaal **Inzender**-machtigingen in Customer Insights nodig.

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen**.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie Azure Synapse Analytics. Neem contact op met een beheerder als er geen verbinding beschikbaar is.

1. Zorg voor een herkenbare **weergavenaam** voor uw export en een **databasenaam**. De export maakt een nieuwe [Azure Synapse-lake-database](/azure/synapse-analytics/database-designer/concepts-lake-database) in de werkruimte die is gedefinieerd in de verbinding.

1. Selecteer naar welke entiteiten u wilt exporteren naar Azure Synapse Analytics.
   > [!NOTE]
   > Gegevensbronnen die zijn gebaseerd op een [Common Data Model-map](connect-common-data-model.md), worden niet ondersteund.

1. Selecteer **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Om gegevens op te vragen die naar Synapse Analytics zijn geëxporteerd, hebt u toegang als **Lezer van gegevens in opslagblob** nodig tot de doelopslag op de werkruimte van exports.

## <a name="update-an-export"></a>Een export bijwerken

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Bewerken** in de export die u wilt bijwerken.

   - Kies **Toevoegen** of **Verwijderen** om entiteiten toe te voegen aan of te verwijderen uit de selectie. Als entiteiten uit de selectie worden verwijderd, worden ze niet verwijderd uit de Synapse Analytics-database. Bij toekomstige gegevensvernieuwingen worden de verwijderde entiteiten in die database echter niet bijgewerkt.

   - Met **De databasenaam wijzigen** wordt een nieuwe Synapse Analytics-database gemaakt. De database met de naam die eerder is geconfigureerd, ontvangt bij toekomstige vernieuwingen geen updates.

[!INCLUDE [footer-include](includes/footer-banner.md)]
