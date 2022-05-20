---
title: Gebruikersrechten beheren
description: Meer informatie over machtigingen en gebruikersrollen.
ms.date: 02/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-permissions
- ci-system-security
- customerInsights
ms.openlocfilehash: 74c7ff7cda8431c04dd34713becefa7e346331b4
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740897"
---
# <a name="user-permissions"></a>Gebruikersmachtigingen

Op de pagina **Machtigingen** stelt u rollen en machtigingen in voor het gebruik van Customer Insights.

U hebt beheerdermachtigingen nodig om de pagina te zien. Om toegang te krijgen tot de pagina met machtigingen, gaat u naar **Beheerder** > **Beveiliging** > **Gebruikers**.

Er zijn drie soorten rollen:

## <a name="viewer"></a>Kijker

- Ontdek inzichten en segmenten op de pagina's **Start** en **Segmenten**.
- Zoek en filter klantprofielen met behulp van de pagina **Klanten**. Velden moeten doorzoekbaar zijn.
- Bekijk en verken de pagina **Verrijking**.
- Verken en exporteer entiteiten met behulp van de pagina **Entiteiten**.
- Bekijk de status van systeemprocessen met behulp van de pagina **Systeem**.
- Exports weergeven op de pagina **Exports**.
- Installeer en gebruik het **Power BI Customer Insights**-dashboard.

## <a name="contributor"></a>Inzender

- Alle machtingen beschikbaar voor de kijker.
- Laad en transformeer gegevens met de pagina **Gegevensbronnen**.
- Voltooi ***Gegevensharmonisatie**, dat resulteert in de entiteit Unified customer profile.
- Definieer **relaties** en **activiteiten**.
- Maak segmenten met behulp van de pagina **Segmenten**.
- Maak meetcriteria met behulp van de pagina **Meetcriteria**.
- Beheer configuratie en verrijk klantprofielen vanaf de pagina **Verrijking** (alleen voor eigen verrijkingen).
- Beheer en maak exports op basis van verbindingen die worden gedeeld met inzenders. [Meer informatie over hoe beheerders inzenders toestaan een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Beheerder

- Alle machtingen beschikbaar voor de inzender.
- Wijzig de instellingen op de pagina **Systeem**, inclusief de werktaal en vernieuwingsschema's voor uw systeemprocessen.
- Bekijk en voeg machtigingen toe met behulp van de pagina **Machtigingen**.
- Stel zoek- en filterdefinities in voor de pagina Klanten met behulp van de pagina **Index voor zoeken en filteren** (toegankelijk via de pagina **Klanten**).
- Beheer verbindingen en sta deze toe voor andere gebruikersrollen op de pagina **Verbindingen**.
- Beheer configuratie en verrijk klantprofielen vanaf de pagina **Verrijking** (voor alle verrijkingen).
- Beheer en maak exports op de pagina **Exports**.
- Installeer en gebruik de **invoegtoepassing Klantkaart**.
- Voeg de **Power Apps-connector** toe en gebruik deze.
- Gebruik van [Customer Insights-API's](apis.md) inschakelen.
- [Eigendom van omgeving toewijzen](manage-environments.md#change-the-owner-of-an-environment) aan een andere beheerder.

## <a name="admin-owner"></a>Beheerder (eigenaar)

- Alle machtigingen beschikbaar voor de beheerder.
- De omgeving [opnieuw instellen en verwijderen](manage-environments.md#reset-an-existing-environment).

## <a name="assign-roles-and-permissions"></a>Rollen en machtigingen toewijzen

1. Ga naar **Beheerder** > **Beveiliging** > **Gebruikers***.

1. Selecteer **Gebruikers toevoegen** om het deelvenster **Machtigingen toevoegen/bewerken** te openen.

1. Gebruik het veld **Zoeken** om de Azure Active Directory-gebruiker of -groep te vinden waarvan u de machtigingen wilt aanpassen. Selecteer een **rol** die u wilt toewijzen aan die gebruiker of groep.

1. Selecteer **Opslaan**. De huidige omgeving wordt automatisch gedeeld met de gebruiker of leden van de groep waarvan u de machtigingen hebt gewijzigd. Gebruikers hebben toegang tot de Customer Insights-app en werken volgens hun specifieke rol.

## <a name="view-current-permissions"></a>Huidige machtigingen weergeven

Ga naar **Beheerder** > **Beveiliging** > **Gebruikers** om te zien welke roltoewijzingen momenteel actief zijn.

- De kolom **Type** geeft een enkele gebruiker, groep of toepassing aan. Het systeem ondersteunt individuele gebruikers en groepen.
- Rollen worden gespecificeerd onder de kolom **Rol**.
- Selecteer een willekeurige kolomtitel om de resultaten op die kolomwaarde te sorteren.
- Gebruik het veld **Zoeken** boven aan de pagina om specifieke gebruikers te vinden.


[!INCLUDE [footer-include](includes/footer-banner.md)]
