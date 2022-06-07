---
title: Procedure - Omgevingen beheren
description: Leer hoe u als beheerder bestaande Customer Insights-omgevingen kunt beheren.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 62a5856edac5e66e5e42c93313d78fa6826469b3
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833486"
---
# <a name="how-to-manage-environments"></a>Procedure: Omgevingen beheren

Beheerders [maken](create-environment.md) en beheren omgevingen. Zij kunnen bepaalde instellingen in bestaande omgevingen wijzigen. Bedrijf, type, regio, opslagoptie en Dataverse-instellingen staan vast na het maken van de omgeving. Als u deze instellingen wilt wijzigen, stelt u de omgeving opnieuw in of maakt u een nieuwe omgeving.

## <a name="edit-an-existing-environment"></a>Een bestaande omgeving bewerken

U kunt enkele details van bestaande omgevingen bewerken.

1. Selecteer de picker **Omgeving** in de koptekst van de app.

1. Selecteer het pictogram **Bewerken**.

   :::image type="content" source="media/edit-environment.png" alt-text="Pictogram voor het bewerken van de omgevingsinstellingen.":::

1. In het vak **Omgeving bewerken** kunt u de omgevingsinstellingen bijwerken.

Zie [Een nieuwe omgeving maken](create-environment.md) als u wilt beginnen met een nieuwe omgeving.

## <a name="change-the-owner-of-an-environment"></a>De eigenaar van een omgeving wijzigen

Meerdere gebruikers kunnen beheerdersmachtigingen hebben, maar slechts één gebruiker is de eigenaar van een omgeving. Standaard is het de beheerder die in eerste instantie een omgeving maakt. Als beheerder van een omgeving kunt u het eigendom toewijzen aan een andere gebruiker met beheerdersrechten.

1. Selecteer de picker **Omgeving** in de koptekst van de app.

1. Selecteer het pictogram **Bewerken**.

1. Ga in het vak **Omgeving bewerken** naar de stap **Basisinformatie**.

1. Kies in het veld **Eigenaar van omgeving wijzigen** de nieuwe eigenaar van de omgeving.  

1. Selecteer **Controleren en voltooien** en vervolgens **Bijwerken** om de wijzigingen toe te passen.

## <a name="claim-ownership-of-an-environment"></a>Eigendom van een omgeving claimen

Als het gebruikersaccount van de eigenaar wordt verwijderd of opgeschort, heeft de omgeving geen eigenaar. Elke gebruiker met beheerdersmachtigingen kan het eigendom claimen en de nieuwe eigenaar worden. Ze kunnen eigenaar blijven van de omgeving of [het eigendom wijzigen naar een andere beheerder](#change-the-owner-of-an-environment).

U kunt het eigendom claimen door de knop **Eigenaar worden** te selecteren die boven aan elke pagina in Customer Insights wordt weergegeven wanneer de oorspronkelijke eigenaar de organisatie heeft verlaten.

## <a name="reset-an-existing-environment-preview"></a>Een bestaande omgeving opnieuw instellen (preview)

Als eigenaar van een omgeving kunt u een omgeving opnieuw instellen op een lege status als u alle configuraties wilt verwijderen en de opgenomen gegevens wilt verwijderen.

1. Selecteer de picker **Omgeving** in de koptekst van de app.

1. Selecteer de omgeving die u opnieuw wilt instellen en selecteer het verticale weglatingsteken (&vellip;).

1. Kies de optie **Opnieuw instellen**.

   :::image type="content" source="media/reset-environment.png" alt-text="Besturingselement om een omgeving opnieuw in te stellen.":::

1. Kies of u de hele omgeving opnieuw wilt instellen, alles behalve de gegevensbronnen of alles dat bovenop het unified customer profile is geconfigureerd.

1. Voer ter bevestiging de naam van de omgeving in en selecteer **Opnieuw instellen**.

## <a name="delete-an-existing-environment"></a>Een bestaande omgeving verwijderen

Als eigenaar van een omgeving kunt u een door u beheerde omgeving verwijderen.

1. Selecteer de picker **Omgeving** in de koptekst van de app.

1. Selecteer de omgeving die u opnieuw wilt instellen en selecteer het verticale weglatingsteken (&vellip;). 

1. Kies de optie **Verwijderen**.

   :::image type="content" source="media/delete-environment.png" alt-text="Besturingselement voor het verwijderen van de omgeving.":::

1. Om de verwijdering te bevestigen, voert u de omgevingsnaam in en selecteert u **Verwijderen**.

> [!IMPORTANT]
> Bij het verwijderen van een omgeving wordt de verbinding met een Dataverse-omgeving niet verwijderd. Als u van plan bent om dezelfde Dataverse-omgeving te verbinden met een nieuwe Customer Insights-omgeving in de toekomst, moet u die verbinding verwijderen. Meer informatie over [het verwijderen van een bestaande verbinding met een Dataverse-omgeving](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

[!INCLUDE [footer-include](includes/footer-banner.md)]
