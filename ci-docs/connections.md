---
title: Overzicht van Verbindingen (preview)
description: Verbindingen met andere services van Customer Insights.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 4a0bc5dd4100b462a26660a0c51fda1fe92b6bb9
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195168"
---
# <a name="connections-preview-overview"></a>Overzicht van Verbindingen (preview)

Verbindingen zijn de sleutel om het delen van gegevens van en naar Customer Insights mogelijk te maken. Elke verbinding brengt het delen van gegevens tot stand met een specifieke service. Verbindingen vormen de basis voor het [configureren van verrijkingen van derden](enrichment-hub.md) en het [configureren van exports](export-destinations.md). Dezelfde verbinding kan meerdere keren worden gebruikt. Eén verbinding met Dynamics 365 Marketing werkt bijvoorbeeld voor meerdere exports en één Leadspace-verbinding kan worden gebruikt voor verschillende verrijkingen.

Ga naar **Beheerder** > **Verbindingen** om verbindingen te maken en te bekijken.

Het tabblad **Verbindingen** laat u alle actieve verbindingen zien. De lijst toont een rij voor elke verbinding.

Krijg een snel overzicht met beschrijving en ontdek wat u kunt doen met elke uitbreidingsoptie op het tabblad **Ontdekken**.

## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights inschakelt om gegevens naar derden of andere Microsoft-producten te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, inclusief mogelijk gevoelige gegevens zoals persoonsgegevens. Microsoft zal dergelijke gegevens in uw opdracht overdragen, maar u bent ervoor verantwoordelijk dat de derde partij voldoet aan uw privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.

Uw Dynamics 365 Customer Insights-beheerder kan de verbinding op elk moment verwijderen om het gebruik van de functionaliteit te stoppen.

## <a name="exports"></a>Exports

Alleen beheerders kunnen nieuwe verbindingen configureren, maar ze kunnen inzenders toegang verlenen om bestaande verbindingen te gebruiken. Beheerders bepalen waar gegevens naartoe kunnen, inzenders bepalen de nettolading en de frequentie die aan hun behoeften voldoen. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

## <a name="enrichments"></a>Verrijkingen

Alleen beheerders kunnen nieuwe verbindingen configureren, maar de gemaakte verbindingen zijn altijd beschikbaar voor zowel beheerders als inzenders. Beheerders beheren referenties en geven toestemming voor gegevensoverdrachten. De verbindingen kunnen vervolgens door zowel beheerders als inzenders worden gebruikt voor verrijkingen.

## <a name="add-a-new-connection"></a>Een nieuwe verbinding toevoegen

Als u verbindingen wilt toevoegen, moet u over [beheerdersmachtigingen](permissions.md) beschikken. Als u verbinding maakt met andere Microsoft-services, gaan we ervan uit dat beide services zich in dezelfde organisatie bevinden.

1. Ga naar **Beheerder** > **Verbindingen (preview)**.

1. Selecteer **Verbinding toevoegen** om een nieuwe verbinding te maken. Kies in het vervolgkeuzemenu welk type verbinding u wilt maken.

1. Geef in het deelvenster **Verbindingen instellen** de vereiste details op.
   1. De **weergavenaam** en het type verbinding beschrijven een verbinding. We raden u aan een naam te kiezen die het doel en het doel van deze verbinding uitlegt.
   1. De exacte velden zijn afhankelijk van de service waarmee u verbinding maakt. U kunt meer te weten komen over de details van een specifiek verbindingstype in het artikel over de doelservice.
   1. Als u uw [eigen Key Vault gebruikt](use-azure-key-vault.md) om geheimen op te slaan, activeert u **Key Vault gebruiken** en kiest u het geheim uit de lijst.

1. Selecteer **Opslaan** om de verbinding te maken.

U kunt ook **Instellen** selecteren op een tegel op het tabblad **Ontdekken**.

### <a name="allow-contributors-to-use-a-connection-for-exports"></a>Inzenders toestaan om een verbinding te gebruiken voor exports

Bij het opzetten of bewerken van een exportverbinding, kiest u welke gebruikers deze specifieke verbinding mogen gebruiken om [exports](export-destinations.md) te definiëren. Standaard is er een verbinding beschikbaar voor gebruikers met de beheerdersrol. U kunt deze instelling wijzigen onder **Kiezen wie deze verbinding kan gebruiken** en laat gebruikers met de rol van inzender deze verbinding gebruiken.

- Inzenders kunnen de verbinding niet bekijken of bewerken. Ze zien alleen de weergavenaam en het type ervan bij het maken van een export.
- Door een verbinding te delen, staat u inzenders toe een verbinding te gebruiken. Inzenders zien gedeelde verbindingen wanneer ze exports instellen. Zij kunnen elke export beheren die deze specifieke verbinding gebruikt.
- U kunt deze instelling wijzigen terwijl u de export behoudt die al door inzenders is gedefinieerd.

## <a name="edit-a-connection"></a>Een verbinding bewerken

1. Ga naar **Beheerder** > **Verbindingen (preview)**.

1. Ga naar het tabblad **Verbindingen**.

1. Selecteer het verticale weglatingsteken (&vellip;) voor de verbinding die u wilt bewerken.

1. Selecteer **Bewerken**.

1. Wijzig de waarden die u wilt bijwerken en selecteer **Opslaan**.

## <a name="remove-a-connection"></a>Een verbinding verwijderen

Als de verbinding die u verwijdert, wordt gebruikt door verrijkingen of exports, moet u deze eerst loskoppelen of verwijderen. Het dialoogvenster voor verwijdering leidt u naar de relevante verrijkingen of exports.

Losgekoppelde verrijkingen en exports worden inactief. U activeert deze opnieuw door er een andere verbinding aan toe te voegen op de pagina [Verrijkingen](enrichment-hub.md) of [Exports](export-destinations.md).

1. Ga naar **Beheerder** > **Verbindingen (preview)**.

1. Ga naar het tabblad **Verbindingen**.

1. Selecteer het verticale weglatingsteken (&vellip;) voor de verbinding die u wilt verwijderen.

1. Selecteer **Verwijderen** in het vervolgkeuzemenu. Er wordt een bevestigingsvenster weergegeven.

   1. Als er verrijkingen of exports zijn die deze verbinding gebruiken, selecteert u de knop om te zien wat de verbinding gebruikt.
      - **Exports:** u kunt ervoor kiezen om de exports te verwijderen of los te koppelen om de verbinding te kunnen verwijderen. Voor het loskoppelen van een export kunnen beheerders de actie **Verbinding verbreken** gebruiken. Deze actie is beschikbaar voor individuele en meerdere geselecteerde exports. Door de verbinding te verbreken, behoudt u de exportconfiguratie, maar wordt deze pas uitgevoerd als er een andere verbinding aan is toegevoegd.
      - **Verrijkingen:** u kunt ervoor kiezen om de verrijkingen te verwijderen of te deactiveren om de verbinding te kunnen verwijderen.
   1. Zodra de verbinding geen afhankelijkheden meer heeft, gaat u terug naar **Beheerder** > **Verbindingen** en probeert u de verbinding opnieuw te verwijderen.

1. Selecteer **Verwijderen** om de verwijdering te bevestigen.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Verbindingen instellen met geheimen die worden beheerd door uw eigen Key Vault

Sommige verbindingen hebben geheimen nodig, zoals API-sleutels of wachtwoorden. Sommige verbindingen ondersteunen geheimen die zijn opgeslagen in uw eigen Key Vault. Meer informatie over ondersteunde verbindingen en hoe u uw [eigen Key Vault kunt instellen voor Customer Insights](use-azure-key-vault.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
