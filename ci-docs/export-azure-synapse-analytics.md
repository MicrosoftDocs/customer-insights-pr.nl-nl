---
title: Gegevens exporteren naar Azure Synapse Analytics (preview)
description: Ontdek hoe u de verbinding met Azure Synapse Analytics configureert.
ms.date: 06/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 60bacb313e0426564310f3c1339bf3b732e17489
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081144"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Gegevens exporteren naar Azure Synapse Analytics (preview)

Azure Synapse is een analyseservice waarmee de tijd tot inzicht in datawarehouses en big data-systemen wordt versneld. U kunt uw Customer Insights-gegevens opnemen en gebruiken in [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Vereisten

Er moet aan de volgende vereisten zijn voldaan om de verbinding van Customer Insights met Azure Synapse te configureren.

> [!NOTE]
> Zorg ervoor dat u alle **roltoewijzingen** instelt zoals beschreven.  

## <a name="prerequisites-in-customer-insights"></a>Vereisten in Customer Insights

* Uw Azure Active Directory (AD)-gebruikersaccount heeft een rol **Beheerder** in Customer Insights. Meer informatie over [het instellen van machtigingen](permissions.md#assign-roles-and-permissions).

In Azure: 

- Een actief Azure-abonnement.

- Bij gebruik van een nieuw Azure Data Lake Storage Gen2-account heeft de *service-principal voor Customer Insights* de machtigingen voor **Bijdrager van Storage Blob-gegevens** nodig. Hier vindt u meer informatie over [verbinding maken met een Azure Data Lake Storage-Gen2-account met een Azure-service-principal voor Customer Insights](connect-service-principal.md). Voor Data Lake Storage Gen2 **moet een** [hiërarchische naamruimte](/azure/storage/blobs/data-lake-storage-namespace) zijn ingeschakeld.

- In de resourcegroep waarin de Azure Synapse workspace zich bevindt, moeten aan de *service-principal* en de *Azure AD-gebruiker met beheerdersmachtigingen in Customer Insights* minimaal machtigingen **Lezer** worden toegewezen. Zie voor meer informatie [Azure-rollen toewijzen met behulp van de Azure-portal](/azure/role-based-access-control/role-assignments-portal).

- De *Azure AD-gebruiker met beheerdersmachtigingen in Customer Insights* heeft machtigingen **Bijdrager van Storage Blob-gegevens** nodig in het Azure Data Lake Storage Gen2-account waar de gegevens zich bevinden en moet zijn gekoppeld aan de Azure Synapse workspace. Meer informatie over [het gebruik van de Azure-portal om een Azure-rol toe te wijzen voor toegang tot blob- en wachtrijgegevens](/azure/storage/common/storage-auth-aad-rbac-portal) en [machtigingen van Bijdrager van opslagblobgegevens](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Voor de in de *[Azure Synapse workspace beheerde identiteit](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* zijn machtigingen van **Bijdrager van opslagblobgegevens** in de Azure Data Lake Storage Gen2-account vereist waarin de gegevens zich bevinden en zijn gekoppeld aan de Azure Synapse-werkruimte. Meer informatie over [het gebruik van de Azure-portal om een Azure-rol toe te wijzen voor toegang tot blob- en wachtrijgegevens](/azure/storage/common/storage-auth-aad-rbac-portal) en [machtigingen van Bijdrager van opslagblobgegevens](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- In de Azure Synapse workspace moet aan de *service-principal voor Customer Insights* de rol van **Synapse-beheerder** worden toegewezen. Zie voor meer informatie [Toegangsbeheer instellen voor uw Synapse-werkruimte](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>De verbinding instellen en exporteren naar Azure Synapse

### <a name="configure-a-connection"></a>Een verbinding configureren

Om een verbinding tot stand te brengen, hebben de service-principal en het gebruikersaccount in Customer Insights **Lezer**-machtigingen nodig op de *resourcegroep* waar de Synapse Analytics-werkruimte zich bevindt. Bovendien hebben de service-principal en de gebruiker op de Synapse Analytics-werkruimte **Synaps-beheerder**-machtigingen nodig. 

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Azure Synapse Analytics** of selecteer **Instellen** op de **Azure Synapse Analytics**-tegel om de verbinding te configureren.

1. Geef uw verbinding een herkenbare naam in het veld Weergavenaam. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Selecteer of zoek naar het abonnement waarin u de Customer Insights-gegevens wilt gebruiken. Zodra een abonnement is geselecteerd, kunt u ook **Werkruimte**, **Opslagaccount** en **Container** selecteren.

1. Selecteer **Opslaan** om de verbinding op te slaan.

### <a name="configure-an-export"></a>Een export configureren

U kunt deze export configureren als u toegang hebt tot een verbinding van dit type. Om de export met een gedeelde verbinding te configureren, hebt u minimaal **Inzender**-machtigingen in Customer Insights. Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen** om een nieuwe export te maken.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie **Azure Synapse Analytics**. Als u deze sectienaam niet ziet, zijn er geen [verbindingen](connections.md) van dit type voor u beschikbaar.

1. Zorg voor een herkenbare **weergavenaam** voor uw export en een **databasenaam**. De export maakt een nieuwe [Azure Synapse-lake-database](/azure/synapse-analytics/database-designer/concepts-lake-database) in de werkruimte die is gedefinieerd in de verbinding.

1. Selecteer naar welke entiteiten u wilt exporteren naar Azure Synapse Analytics.
   > [!NOTE]
   > Gegevensbronnen die zijn gebaseerd op een [Common Data Model-map](connect-common-data-model.md), worden niet ondersteund.

1. Selecteer **Opslaan**.

Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.

De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab). U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand).

Om gegevens op te vragen die naar Synapse Analytics zijn geëxporteerd, hebt u toegang als **Lezer van gegevens in opslagblob** nodig tot de doelopslag op de werkruimte van exports. 

### <a name="update-an-export"></a>Een export bijwerken

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Bewerken** in de export die u wilt bijwerken.

   - Kies **Toevoegen** of **Verwijderen** om entiteiten toe te voegen aan of te verwijderen uit de selectie. Als entiteiten uit de selectie worden verwijderd, worden ze niet verwijderd uit de Synapse Analytics-database. Bij toekomstige gegevensvernieuwingen worden de verwijderde entiteiten in die database echter niet bijgewerkt.

   - Met **De databasenaam wijzigen** wordt een nieuwe Synapse Analytics-database gemaakt. De database met de naam die eerder is geconfigureerd, ontvangt bij toekomstige vernieuwingen geen updates.
