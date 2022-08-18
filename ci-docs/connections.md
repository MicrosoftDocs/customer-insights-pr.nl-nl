---
title: Overzicht van Verbindingen (preview)
description: Verbindingen met andere services van Customer Insights.
ms.date: 08/04/2022
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 8580dc7d90c75f66f73efc15f8e38f5e10fbb8a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245505"
---
# <a name="connections-preview-overview"></a>Overzicht van Verbindingen (preview)

Verbindingen zijn de sleutel om het delen van gegevens van en naar Customer Insights mogelijk te maken. Elke verbinding brengt het delen van gegevens tot stand met een specifieke service. Gebruik verbindingen om [verrijkingen van derden te configureren](enrichment-hub.md) en het [exports te configureren](export-destinations.md). Dezelfde verbinding kan meerdere keren worden gebruikt. Eén verbinding met Dynamics 365 Marketing werkt bijvoorbeeld voor meerdere exports en één Leadspace-verbinding kan worden gebruikt voor verschillende verrijkingen.

## <a name="export-connections"></a>Verbindingen exporteren

Alleen beheerders kunnen nieuwe verbindingen configureren, maar ze kunnen [inzenders toegang verlenen](#allow-contributors-to-use-a-connection-for-exports) om bestaande verbindingen te gebruiken. Beheerders bepalen waar gegevens naartoe kunnen, inzenders bepalen de nettolading en de frequentie die aan hun behoeften voldoen.

## <a name="enrichment-connections"></a>Verrijkingsverbindingen

Alleen beheerders kunnen nieuwe verbindingen configureren, maar de gemaakte verbindingen zijn altijd beschikbaar voor zowel beheerders als inzenders. Beheerders beheren referenties en geven toestemming voor gegevensoverdrachten. De verbindingen kunnen vervolgens door zowel beheerders als inzenders worden gebruikt voor verrijkingen.

## <a name="add-a-new-connection"></a>Een nieuwe verbinding toevoegen

### <a name="prerequisites"></a>Vereisten

- [Beheerdersmachtigingen](permissions.md)
- Andere Microsoft-services, indien aanwezig, bevinden zich in dezelfde organisatie

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies het type verbinding dat u wilt maken. U kunt ook naar het tabblad **Ontdekken** gaan en **Instellen** selecteren op een verbindingstegel.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Voer de vereiste gegevens in. De exacte velden zijn afhankelijk van de service waarmee u verbinding maakt. U kunt meer te weten komen over de details van een specifiek verbindingstype in het artikel over de doelservice.

1. Als u uw [eigen Key Vault gebruikt](use-azure-key-vault.md) om geheimen op te slaan, activeert u **Key Vault gebruiken** en kiest u het geheim uit de lijst.

1. Beoordeel de gegevensprivacy en naleving en selecteer **Ik ga akkoord**.

1. Selecteer **Opslaan** om de verbinding te maken.

### <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights inschakelt om gegevens naar derden of andere Microsoft-producten te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, inclusief mogelijk gevoelige gegevens zoals persoonsgegevens. Microsoft zal dergelijke gegevens in uw opdracht overdragen, maar u bent ervoor verantwoordelijk dat de derde partij voldoet aan uw privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.

Uw Dynamics 365 Customer Insights-beheerder kan de verbinding op elk moment verwijderen om het gebruik van de functionaliteit te stoppen.

## <a name="allow-contributors-to-use-a-connection-for-exports"></a>Inzenders toestaan om een verbinding te gebruiken voor exports

Kies, bij het opzetten of bewerken van een exportverbinding, welke gebruikers deze specifieke verbinding mogen gebruiken om [exports](export-destinations.md) te definiëren. Standaard is er een verbinding beschikbaar voor gebruikers met een beheerdersrol. Wijzig de instelling **Kiezen wie deze verbinding kan gebruiken** om gebruikers met de rol van inzender deze verbinding te laten gebruiken.

- Inzenders kunnen de verbinding niet bekijken of bewerken. Ze zien alleen de weergavenaam en het type ervan bij het maken van een export.
- Door een verbinding te delen, staat u inzenders toe een verbinding te gebruiken. Inzenders zien gedeelde verbindingen wanneer ze exports instellen. Zij kunnen elke export beheren die deze specifieke verbinding gebruikt.
- U kunt deze instelling wijzigen terwijl u de export behoudt die al door inzenders is gedefinieerd.

## <a name="manage-existing-connections"></a>Bestaande verbindingen beheren

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer het tabblad **Verrijking** of **Exports** om een lijst met verrijkings- of exportverbindingen, het verbindingstype, wanneer het is gemaakt en wie toegang heeft te bekijken. U kunt de lijst met verbindingen op elke willekeurige kolom sorteren.

1. Selecteer de verbinding om beschikbare acties te bekijken.

   - **Bewerk** de verbinding.
   - [**Verwijder**](#remove-a-connection) een verbinding.

### <a name="remove-a-connection"></a>Een verbinding verwijderen

Als de verbinding die u verwijdert, wordt gebruikt door verrijkingen of exports, koppelt u deze eerst los of verwijdert u deze. Het dialoogvenster voor verwijdering leidt u naar de relevante verrijkingen of exports.

> [!TIP]
> Gedeactiveerde verrijkingen en losgekoppelde exports worden inactief. U activeert deze opnieuw door er een andere verbinding aan toe te voegen op de pagina [Verrijkingen](enrichment-hub.md) of [Exports](export-destinations.md).

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer het tabblad **Verrijking** of **Exports**.

1. Selecteer de verbinding die u wilt verwijderen.

1. Selecteer **Verwijderen** in het vervolgkeuzemenu. Er wordt een bevestigingsvenster weergegeven.

   1. Als er verrijkingen of exports zijn die deze verbinding gebruiken, selecteert u de knop om te zien wat de verbinding gebruikt.
      - **Exports:** Kies ervoor om de export te **verwijderen** of **de verbinding los te koppelen**. Als de verbinding wordt losgekoppeld, blijft de exportconfiguratie behouden, maar wordt deze pas uitgevoerd als er een andere verbinding aan is toegevoegd.
      - **Verrijkingen:** Kies ervoor om de verrijkingen te **verwijderen** of **deactiveren**.
   1. Zodra de verbinding geen afhankelijkheden meer heeft, gaat u terug naar **Beheerder** > **Verbindingen** en probeert u de verbinding opnieuw te verwijderen.

1. Selecteer **Verwijderen** om de verwijdering te bevestigen.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Verbindingen instellen met geheimen die worden beheerd door uw eigen Key Vault

Sommige verbindingen hebben geheimen nodig, zoals API-sleutels of wachtwoorden. Sommige verbindingen ondersteunen geheimen die zijn opgeslagen in uw eigen Key Vault. Meer informatie over ondersteunde verbindingen en hoe u uw [eigen Key Vault kunt instellen voor Customer Insights](use-azure-key-vault.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
