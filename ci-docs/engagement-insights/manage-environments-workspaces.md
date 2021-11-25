---
title: Werkruimten en omgevingen beheren
description: Werkruimten en omgevingen maken, hernoemen en verwijderen.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 09cb3ddf0f8b4507b7eae6668ea3dad08cfcea29
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673784"
---
# <a name="manage-environments-and-workspaces"></a>Omgevingen en werkruimten beheren

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Overzicht

Dit onderwerp bespreekt hoe werkruimten en omgevingen kunnen worden beheerd nadat ze zijn gemaakt. 

- Een *werkruimte* is een ruimte om gebeurtenissen en rapporten op te slaan en te beheren. Hier kunt u de gebruikersactiviteit in realtime bekijken. Wanneer u een werkruimte maakt, selecteert u het type gegevens dat u naar de werkruimte wilt verzenden. Momenteel worden webgegevens en mobiele apps ondersteund. Zie voor meer informatie [Een nieuwe werkruimte maken en leden toevoegen](create-workspace.md).

- Een *omgeving* is een ruimte waarin u uw werkruimten en verbindingen beheert. Zie [Een nieuwe omgeving maken](create-new-environment.md) voor meer informatie.

## <a name="manage-an-existing-workspace"></a>Een bestaande werkruimte beheren

U kunt meerdere werkruimten tegelijkertijd in een omgeving onderhouden. Uw [rol](user-roles.md) bepaalt hoe u erin kunt werken. 

 - U moet een omgevingsbeheerder of een werkruimtebeheerder zijn om de werkruimte te kunnen beheren.
 - Als werkruimtebeheerder kunt u bestaande werkruimten een andere naam geven of verwijderen. 

:::image type="content" source="media/workspace-edit.png" alt-text="Beheercentrum voor werkruimtes.":::

### <a name="edit-a-workspace-name"></a>De naam van een werkruimte bewerken

1. Ga naar **Beheer** > **Werkruimte** en selecteer **Instellingen**.

1. Voer een nieuwe naam in het vak **Naam van werkruimte** in.

1. Selecteer **Opslaan** om uw wijzigingen toe te passen.

### <a name="delete-a-workspace"></a>Een werkruimte verwijderen

Als u een werkruimte verwijdert, worden alle inhoud, gegevens, instellingen en machtigingen permanent verwijderd. Dit kan niet ongedaan worden gemaakt.

1. Ga naar **Beheer** > **Werkruimte** en selecteer **Instellingen**.

1. Selecteer **Werkruimte verwijderen**. 

1. Voer in het dialoogvenster **Werkruimte verwijderen** in hoofdletters **VERWIJDEREN BEVESTIGEN** in. 

1. Selecteer **Verwijderen** om de werkruimte permanent te verwijderen.

### <a name="manage-workspace-members"></a>Werkruimteleden beheren

1. Ga naar **Beheer** > **Werkruimte** en selecteer **Leden**.

1. Selecteer **Leden toevoegen** om toegang te geven en [rollen toe te wijzen](user-roles.md). Op dit moment is alleen **Werkruimtebeheer** beschikbaar.

1. Selecteer **Leden toevoegen** om deze toe te voegen aan uw werkruimte.

## <a name="manage-an-existing-environment"></a>Een bestaande omgeving beheren

Als omgevingsbeheerder hebt u toegang tot een omgeving via het linkernavigatiedeelvenster. U kunt omgevingsinstellingen, andere omgevingsbeheerders en werkruimten configureren. Selecteer tabbladen om tussen verschillende gebieden in het beheercentrum te wisselen.

:::image type="content" source="media/environment-edit.png" alt-text="Omgevingsbeheercentrum.":::

### <a name="edit-an-environment-name"></a>Een omgevingsnaam bewerken

1. Ga naar **Beheer** > **Omgeving** en selecteer **Instellingen**.

1. Werk de **Omgevingsnaam** bij en selecteer **Opslaan** om uw wijzigingen toe te passen.

### <a name="delete-an-environment"></a>Een omgeving verwijderen

Omgevingsbeheerders kunnen omgevingen verwijderen. Voordat u een omgeving kunt verwijderen, moet u alle werkruimten eronder verwijderen.

1. Ga naar **Beheer** > **Omgeving** en selecteer **Instellingen**.

1. Selecteer **Omgeving verwijderen**. 

1. Voer in het dialoogvenster **Werkruimte verwijderen** in hoofdletters **VERWIJDEREN BEVESTIGEN** in. 

1. Selecteer **Verwijderen** om de omgeving permanent te verwijderen.

### <a name="manage-environment-members"></a>Omgevingsleden beheren

1. Ga naar **Beheer** > **Omgeving** en selecteer **Leden**.

1. Selecteer **Leden toevoegen** om leden bij te werken en [rollen toe te wijzen](user-roles.md). Op dit moment is alleen **Omgevingsbeheer** beschikbaar.

1. Selecteer **Leden toevoegen** om deze toe te voegen aan uw omgeving.

## <a name="manage-connections"></a>Verbindingen beheren

Door verbindingen tot stand te brengen met doelgroepinzichten, kunt u rapporten in betrokkenheidsinzichten bekijken op basis van geharmoniseerde klantprofielen. 

Zie [Een koppeling tot stand brengen tussen doelgroepinzichten en betrokkenheidsinzichten](integrate-audience-insights-engagement-insights.md) voor meer informatie.

## <a name="manage-personal-data"></a>Persoonlijke gegevens beheren

Om de persoonlijke gegevens van uw klant te beschermen, kunt u identificeerbare gegevens van de eindgebruiker verwijderen of exporteren.

Zie [Gebeurtenisgegevens met persoonlijke informatie verwijderen en exporteren](../dsr-rights-requests.md#deleting-and-exporting-event-data-containing-end-user-identifiable-information) voor meer informatie.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
