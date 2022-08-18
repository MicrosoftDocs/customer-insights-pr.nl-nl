---
title: Gebruikersmachtigingen toewijzen
description: Meer informatie over machtigingen en gebruikersrollen.
ms.date: 08/08/2022
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
ms.openlocfilehash: a59a672b6f7e1e67c2162ea14bb9860df0d551aa
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245413"
---
# <a name="assign-user-permissions"></a>Gebruikersmachtigingen toewijzen

Toegang tot Customer Insights is beperkt tot gebruikers in uw organisatie die door een beheerder aan de toepassing zijn toegevoegd. Een beheerder kan gebruikers toevoegen, bewerken of verwijderen. Een gebruiker kan een enkele gebruiker, groep of toepassing zijn. Er zijn drie typen rollen die een gebruiker kan hebben:

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
- Voltooi **Gegevensharmonisatie**, dat resulteert in de entiteit geharmoniseerd klantprofiel.
- Definieer **relaties** en **activiteiten**.
- Maak segmenten met behulp van de pagina **Segmenten**.
- Maak meetcriteria met behulp van de pagina **Meetcriteria**.
- Beheer configuratie en verrijk klantprofielen vanaf de pagina **Verrijking** (alleen voor eigen verrijkingen).
- Beheer en maak exports op basis van [verbindingen die worden gedeeld met inzenders](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Beheerder

- Alle machtingen beschikbaar voor de inzender.
- Wijzig de instellingen op de pagina **Systeem**, inclusief de werktaal en vernieuwingsschema's voor uw systeemprocessen, en exporteer diagnoselogboeken.
- Wijzig instellingen op de pagina **Beveiliging**, inclusief gebruikers, API-sleutels, privékoppelingen en sleutelkluis.
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
- De omgeving [opnieuw instellen en verwijderen](manage-environments.md#reset-an-existing-environment-preview).

## <a name="add-users"></a>Gebruikers toevoegen

1. Ga naar **Beheer** > **Beveiliging** en selecteer het tabblad **Gebruikers**.

1. Selecteer **Gebruikers toevoegen** om het deelvenster **Machtigingen toevoegen/bewerken** te openen.

1. Gebruik het veld **Zoeken** om de Azure Active Directory-gebruiker of -groep te vinden die u wilt toevoegen. Selecteer een **rol** die u wilt toewijzen aan die gebruiker of groep.

1. Selecteer **Save**. De huidige omgeving wordt automatisch gedeeld met de gebruiker of leden van de groep. Gebruikers hebben toegang tot de Customer Insights-app en werken volgens hun specifieke rol.

## <a name="view-current-permissions"></a>Huidige machtigingen weergeven

Ga naar **Beheer** > **Beveiliging** en selecteer het tabblad **Gebruikers** om de lijst met actieve gebruikers en hun roltoewijzingen te bekijken. U kunt de lijst met gebruikers sorteren op elke kolom of het zoekvak gebruiken om een specifieke gebruiker te vinden.

## <a name="manage-current-users"></a>Huidige gebruikers beheren

Ga naar **Beheer** > **Beveiliging** en selecteer het tabblad **Gebruikers**. U kunt de lijst met gebruikers sorteren op elke kolom of het zoekvak gebruiken om de gebruiker te vinden die u wilt beheren.

Selecteer een gebruiker om beschikbare acties te bekijken.

- **Bewerken** om de rol van de gebruiker in Customer Insights te bewerken. Selecteer **Opslaan** om de wijziging te bevestigen.
- **Verwijderen** om de gebruiker de toegang tot Customer Insights te ontzeggen. Selecteer **Verwijderen** om het verwijderen te bevestigen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
