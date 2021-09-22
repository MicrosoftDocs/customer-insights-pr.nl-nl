---
title: Werkruimten en omgevingen beheren
description: Werkruimten en omgevingen maken, hernoemen en verwijderen.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 07/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: bf310b1a50ba7baac5d11d5f22ff42003fbba516efd7d165c00b59adc958da2e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034036"
---
# <a name="manage-environments-and-workspaces"></a>Omgevingen en werkruimten beheren

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Overzicht

Een werkruimte is een ruimte om gebeurtenissen en rapporten op te slaan en te beheren. Hier kunt u de gebruikersactiviteit in realtime bekijken. Wanneer u een werkruimte maakt, selecteert u het type gegevens dat u naar de werkruimte wilt verzenden. Momenteel worden webgegevens en mobiele apps ondersteund.

Een omgeving is een ruimte waarin u uw werkruimten en verbindingen beheert. Hoe u omgevingen gebruikt, is afhankelijk van uw organisatie en uw gebruiksscenario. U kunt bijvoorbeeld het volgende maken:

-   Een enkele omgeving.
-   Afzonderlijke omgevingen voor test- en productieomgevingen.
-   Afzonderlijke omgevingen voor specifieke teams of afdelingen in uw organisatie die relevante evenementen bevatten voor elke doelgroep.
-   Afzonderlijke omgevingen voor verschillende internationale vestigingen van uw bedrijf.
-   Verbindingsmogelijkheden met Customer Insights doelgroepinzichten.

## <a name="choose-an-environment-and-create-a-workspace"></a>Een omgeving kiezen en een werkruimte maken 

Elke werkruimte moet zich in een omgeving bevinden. U kunt een reeds bestaande omgeving selecteren of een nieuwe maken wanneer u een werkruimte maakt. Vervolgens kunt u ervoor kiezen werkruimteleden toe te voegen en beginnen gegevens te verzamelen.

**Uw eerste werkruimte maken**

1. Selecteer in betrokkenheidsinzichten **Nieuw** vanuit de werkruimteschakelaar. 

   :::image type="content" source="media/New-workspace.png" alt-text="Werkruimtekiezer voor Customer Insights-pagina.":::

1. Kies een omgeving in de lijst of selecteer **Nieuwe omgeving maken**.

1. Voer een naam in bij **Naam werkruimte**. 

1. Selecteer het type omgeving dat u wilt maken, afhankelijk van of u wilt meten wat er op een website of in een mobiele app gebeurt. 

1. U kunt leden toevoegen en hun machtigingsniveau toewijzen vanuit de lijst **Rol**. Selecteer **Voltooien** om de werkruimte te maken of **Volgende** om code te installeren. 

1. Installeer het codefragment om gegevens te ontvangen en selecteer **Gereed**. 

## <a name="manage-a-workspace"></a>Een werkruimte beheren

U kunt meerdere werkruimten tegelijkertijd in een omgeving onderhouden. Uw [rol](user-roles.md) bepaalt hoe u erin kunt werken. 

 - U moet een omgevingsbeheerder of een werkruimtebeheerder zijn om de werkruimte te kunnen beheren.
 - Als werkruimtebeheerder kunt u bestaande werkruimten een andere naam geven of verwijderen. 

### <a name="edit-a-workspace-name"></a>De naam van een werkruimte bewerken

1. Ga naar **Beheer** > **Werkruimte** en selecteer **Instellingen**.

1. Voer een nieuwe naam in het vak **Naam van werkruimte** in.

1. Selecteer **Opslaan** om uw wijzigingen toe te passen.

### <a name="delete-a-workspace"></a>Een werkruimte verwijderen

Als u een werkruimte verwijdert, worden alle inhoud, gegevens, instellingen en machtigingen permanent verwijderd. Dit kan niet ongedaan worden gemaakt.

1. Ga naar **Beheer** > **Werkruimte** en selecteer **Instellingen**.

1. Selecteer **Werkruimte verwijderen**. 

1. Voer in het dialoogvenster **Werkruimte verwijderen** **VERWIJDEREN BEVESTIGEN** in. 

1. Selecteer **Verwijderen** om de werkruimte permanent te verwijderen.

### <a name="manage-workspace-members"></a>Werkruimteleden beheren

1. Ga naar **Beheer** > **Werkruimte** en selecteer **Leden**.

1. Selecteer **Leden toevoegen** om toegang te geven en [rollen toe te wijzen](user-roles.md). Op dit moment is alleen **Werkruimtebeheer** beschikbaar.

1. Als u een [verbinding met doelgroepinzichten](configure-connections.md) instelt, kunt u **Toegang tot profielgegevens toestaan** selecteren om het lid toe te staan rapporten te zien op basis van [gebruikersprofielen](profile-reports.md).

1. Selecteer **Leden toevoegen** om deze toe te voegen aan uw werkruimte.

## <a name="manage-an-environment"></a>Een omgeving beheren

Als omgevingsbeheerder hebt u toegang tot een omgeving via het linkernavigatiedeelvenster. U kunt omgevingsinstellingen, andere omgevingsbeheerders, werkruimten en [verbindingen met doelgroepinzichten](configure-connections.md) configureren. Selecteer tabbladen om tussen verschillende gebieden in het beheercentrum te wisselen.

:::image type="content" source="media/New-environment.png" alt-text="Omgevingsbeheercentrum.":::

### <a name="create-an-environment"></a>Een omgeving maken

1. Selecteer **+Nieuw** in de werkruimtekiezer.

1. Open het vervolgkeuzemenu **Omgeving** in de begeleide ervaring en selecteer **Nieuwe omgeving maken**. 

1. Geef een **Omgevingsnaam** op.

   :::image type="content" source="media/create-environment.png" alt-text="Stap in de begeleide ervaring om de omgevingsdetails op te geven.":::

1. Kies de **Regio** en selecteer **Volgende**. 

1. Geef een werkruimtenaam op en kies welk type werkruimte u wilt maken. 

1.  Voeg desgewenst leden toe en kopieer het codefragment om het maken te voltooien.

### <a name="rename-an-environment"></a>De naam van een omgeving wijzigen

1. Ga naar **Beheer** > **Omgeving** en selecteer **Instellingen**.

1. Werk de **Omgevingsnaam** bij en selecteer **Opslaan** om uw wijzigingen toe te passen.

### <a name="manage-environment-members"></a>Omgevingsleden beheren

1. Ga naar **Beheer** > **Omgeving** en selecteer **Leden**.

1. Selecteer **Leden toevoegen** om leden bij te werken en [rollen toe te wijzen](user-roles.md). Op dit moment is alleen **Omgevingsbeheer** beschikbaar.

1. Als u een [verbinding met doelgroepinzichten](configure-connections.md) instelt, kunt u **Toegang tot profielgegevens toestaan** selecteren om het lid toe te staan rapporten te zien op basis van [gebruikersprofielen](profile-reports.md).

1. Selecteer **Leden toevoegen** om deze toe te voegen aan uw omgeving.

### <a name="delete-an-environment"></a>Een omgeving verwijderen

Omgevingsbeheerders kunnen omgevingen verwijderen. Voordat u een omgeving kunt verwijderen, moet u alle werkruimten eronder verwijderen.

1. Ga naar **Beheer** > **Omgeving** en selecteer **Instellingen**.

1. Selecteer **Omgeving verwijderen**. 

1. Voer in het dialoogvenster **Werkruimte verwijderen** **VERWIJDEREN BEVESTIGEN** in. 

1. Selecteer **Verwijderen** om de omgeving permanent te verwijderen.

## <a name="manage-connections"></a>Verbindingen beheren

Door verbindingen tot stand te brengen met doelgroepinzichten, kunt u rapporten in betrokkenheidsinzichten bekijken op basis van geharmoniseerde klantprofielen. 

Zie [Verbindingen configureren](configure-connections.md) voor meer informatie.

## <a name="manage-personal-data"></a>Persoonlijke gegevens beheren

Om de persoonlijke gegevens van uw klant te beschermen, kunt u identificeerbare gegevens van de eindgebruiker verwijderen of exporteren.

Zie [Gebeurtenisgegevens met persoonlijke informatie verwijderen en exporteren](delete-export-personal-data.md) voor meer informatie.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
