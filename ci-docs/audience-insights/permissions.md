---
title: Gebruikersrechten beheren
description: Meer informatie over machtigingen en gebruikersrollen.
ms.date: 10/27/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7de78c0ef71ec5b83870d396de36a7dcabbd14e5
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689214"
---
# <a name="user-permissions"></a>Gebruikersmachtigingen

Op de pagina **Machtigingen** stelt u rollen en machtigingen in voor het gebruik van doelgroepinzichten.

U hebt beheerdermachtigingen nodig om de pagina te zien. Ga naar **Beheer** > **Machtigingen** om toegang te krijgen tot de pagina met machtigingen in doelgroepinzichten.

Er zijn drie soorten rollen:

## <a name="viewer"></a>Kijker

- Ontdek inzichten en segmenten op de pagina's **Start** en **Segmenten**.
- Zoek en filter klantprofielen met behulp van de pagina **Klanten**. Velden moeten doorzoekbaar zijn.
- Bekijk en verken de pagina **Verrijking**.
- Verken en exporteer entiteiten met behulp van de pagina **Entiteiten**.
- Bekijk de status van systeemprocessen met behulp van de pagina **Systeem**.
- Exporteer segmenten van de pagina **Segmenten**.
- Installeer en gebruik het **Power BI Customer Insights**-dashboard.

## <a name="contributor"></a>Inzender

- Alle machtingen beschikbaar voor de kijker.
- Laad en transformeer gegevens met de pagina **Gegevensbronnen**.
- Voltooi de secties *Gegevensharmonisatie* (**Toewijzen**, **Afstemmen** en **Samenvoegen**) die resulteren in de geharmoniseerde klantprofielentiteit.
- Definieer **relaties** en **activiteiten**.
- Maak segmenten met behulp van de pagina **Segmenten**.
- Maak meetcriteria met behulp van de pagina **Meetcriteria**.
- Beheer configuratie en verrijk klantprofielen vanaf de pagina **Verrijking** (alleen voor eigen verrijkingen).

## <a name="administrator"></a>Beheerder

- Alle machtingen beschikbaar voor de inzender.
- Wijzig de instellingen op de pagina **Systeem**, inclusief de werktaal en vernieuwingsschema's voor uw systeemprocessen.
- Bekijk en voeg machtigingen toe met behulp van de pagina **Machtigingen**.
- Stel zoek- en filterdefinities in voor de pagina Klanten met behulp van de pagina **Index voor zoeken en filteren** (toegankelijk via de pagina **Klanten**).
- Definieer Dynamics 365 Sales-segmentbestemmingen met behulp van de pagina **Bestemmingen exporteren**.
- Beheer configuratie en verrijk klantprofielen vanaf de pagina **Verrijking** (voor alle verrijkingen).
- Installeer en gebruik de **invoegtoepassing Klantkaart**.
- Voeg de **Power Apps-connector** toe en gebruik deze.
- Gebruik van [Customer Insights-API's](apis.md) inschakelen.

## <a name="assign-roles-and-permissions"></a>Rollen en machtigingen toewijzen

1. Ga in doelgroepinzichten naar **Beheer** > **Machtigingen**.

1. Selecteer **Gebruikers toevoegen** om het deelvenster **Machtigingen toevoegen/bewerken** te openen.

1. Gebruik het veld **Zoeken** om de Azure Active Directory-gebruiker of -groep te vinden waarvan u de machtigingen wilt aanpassen. Selecteer een **rol** die u wilt toewijzen aan die gebruiker of groep.

1. Selecteer **Opslaan**. De huidige omgeving wordt automatisch gedeeld met de gebruiker of leden van de groep waarvan u de machtigingen hebt gewijzigd. Gebruikers hebben toegang tot de Customer Insights-app en werken volgens hun specifieke rol.

## <a name="view-current-permissions"></a>Huidige machtigingen weergeven

Ga in doelgroepinzichten naar **Beheer** > **Machtigingen** om te zien welke roltoewijzingen momenteel actief zijn.

- De kolom **Type** geeft een enkele gebruiker, groep of toepassing aan. Het systeem ondersteunt individuele gebruikers en groepen.
- Rollen worden gespecificeerd onder de kolom **Rol**.
- Selecteer een willekeurige kolomtitel om de resultaten op die kolomwaarde te sorteren.
- Gebruik het veld **Zoeken** boven aan de pagina om specifieke gebruikers te vinden.
