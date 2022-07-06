---
title: Verbinding maken met een Power Query-gegevensbron (met video)
description: Neem gegevens op via een Power Query-connector (met video).
ms.date: 06/13/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: matgos
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 6736b253e3a7e652f92f61bc44bfb31ca69be31a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080995"
---
# <a name="connect-to-a-power-query-data-source"></a>Verbinding maken met een Power Query-gegevensbron

Power Query biedt een brede reeks connectors voor het opnemen van gegevens. De meeste van deze connectors worden ondersteund door Dynamics 365 Customer Insights.

Bij het toevoegen van gegevensbronnen op basis van Power Query-connectors worden over het algemeen de stappen gevolgd die in deze sectie worden beschreven. Afhankelijk van de connector die u gebruikt, kan echter andere informatie vereist zijn. Zie de documentatie over afzonderlijke connectors in de [Power Query-connectorreferentie](/power-query/connectors/) voor meer informatie.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Een nieuwe gegevensbron maken

1. Ga naar **Gegevens** > **Gegevensbronnen**.

1. Selecteer **Gegevensbron toevoegen**.

1. Selecteer **Microsoft Power Query**.

1. Voer een **Naam** voor de gegevensbron en een optionele **Beschrijving** in en selecteer **Volgende**.

1. Kies een van de [beschikbare connectors](#available-power-query-data-sources). In dit voorbeeld selecteren we de connector **Tekst/CSV**.

1. Voer de vereiste gegevens in voor de **Verbindingsinstellingen** voor de geselecteerde connector en selecteer **Volgende** om een voorbeeld van de gegevens te zien.

1. Selecteer **Gegevens transformeren**. In deze stap voegt u entiteiten toe aan uw gegevensbron. Entiteiten zijn gegevenssets. Als u een database hebt die meerdere gegevenssets bevat, is elke gegevensset zijn eigen entiteit.

1. Met het dialoogvenster **Power Query - Query's bewerken** kunt u de gegevens bekijken en verfijnen. De entiteiten die de systemen in uw geselecteerde gegevensbron hebben geïdentificeerd, verschijnen in het linkerdeelvenster.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Dialoogvenster Query's bewerken":::

1. U kunt uw gegevens ook transformeren. Selecteer een entiteit om te bewerken of transformeren. Gebruik de opties in het Power Query-venster om transformaties toe te passen. Elke transformatie wordt vermeld onder **Toegepaste stappen**. Power Query biedt tal van vooraf gebouwde transformatieopties. Voor meer informatie raadpleegt u [Power Query-transformaties](/power-query/power-query-what-is-power-query#transformations).

   We raden u aan de volgende transformaties te gebruiken:

   - Als u gegevens opneemt uit een CSV-bestand, bevat de eerste rij vaak kopteksten. Ga naar **Transformeren** en selecteer **De eerste rij als veldnamen gebruiken**.
   - Zorg ervoor dat het gegevenstype correct is ingesteld. Selecteer bijvoorbeeld een datumtype voor datumvelden.

1. Als u extra entiteiten wilt toe te voegen aan uw gegevensbron in het dialoogvenster **Query's bewerken**, ga naar **Start** en selecteer **Gegevens ophalen**. Herhaal stap 6-10 totdat u alle entiteiten voor deze gegevensbron hebt toegevoegd.

1. Selecteer **Save**. De pagina **Gegevensbronnen** wordt geopend met de nieuwe gegevensbron met de status **Vernieuwen**.

### <a name="available-power-query-data-sources"></a>Beschikbare Power Query-gegevensbronnen

Zie de [Power Query-connectorreferentie](/power-query/connectors/) voor een lijst met connectors die u kunt gebruiken om gegevens naar Customer Insights te importeren.

Connectors met een vinkje in de kolom **Customer Insights (gegevensstromen)** zijn beschikbaar om nieuwe gegevensbronnen te maken op basis van Power Query. Bekijk de documentatie van een specifieke connector voor meer informatie over de vereisten, [querybeperkingen](/power-query/power-query-online-limits) en andere informatie.

## <a name="add-data-from-on-premises-data-sources"></a>Gegevens toevoegen vanuit on-premises gegevensbronnen

Het opnemen van gegevens uit on-premises gegevensbronnen wordt ondersteund op basis van Microsoft Power Platform-gegevensstromen (PPDF's). U kunt gegevensstromen in Customer Insights inschakelen door [de omgevings-URL voor Microsoft Dataverse te verstrekken](create-environment.md) bij het instellen van de omgeving.

Gegevensbronnen die zijn gemaakt na het koppelen van een Dataverse-omgeving met Customer Insights maken standaard gebruik van [Power Platform-gegevensstromen](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Gegevensstromen ondersteunen on-premises connectiviteit met behulp van de gegevensgateway. U kunt gegevensbronnen verwijderen en opnieuw maken die bestonden voordat een Dataverse-omgeving werd gekoppeld [met behulp van on-premises gegevensgateways](/data-integration/gateway/service-gateway-app).

Gegevensgateways van een bestaande Power BI- of Power Apps-omgeving worden zichtbaar en u kunt deze opnieuw gebruiken in Customer Insights. De pagina met gegevensbronnen toont koppelingen om naar de Microsoft Power Platform-omgeving te gaan waar u on-premises gegevensgateways kunt bekijken en configureren.

> [!IMPORTANT]
> Zorg ervoor dat uw gateways zijn bijgewerkt naar de nieuwste versie. U kunt een update installeren en een gateway opnieuw configureren vanaf een prompt die direct op het gatewayscherm wordt weergegeven of [de meest recente versie downloaden](https://powerapps.microsoft.com/downloads/). Als u niet de nieuwste gatewayversie gebruikt, mislukt het vernieuwen van de gegevensstroom met foutmeldingen zoals **Het trefwoord wordt niet ondersteund: configuratie-eigenschappen. Parameternaam: trefwoord**.

## <a name="edit-power-query-data-sources"></a>Power Query-gegevensbronnen bewerken

> [!NOTE]
> Het is misschien niet mogelijk om wijzigingen aan te brengen in gegevensbronnen die momenteel worden gebruikt in een van de processen van de app (bijvoorbeeld *segmentatie*, *afstemming* of *samenvoeging*).
>
> Op de pagina **Instellingen** kunt u de voortgang van elk van de actieve processen volgen. Wanneer een proces is voltooid, kunt u terugkeren naar de pagina **Gegevensbronnen** en uw wijzigingen aanbrengen.

1. Ga naar **Gegevens** > **Gegevensbronnen**.

1. Selecteer **Bewerken** naast de gegevensbron die u wilt bijwerken.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

1. Pas uw wijzigingen en transformaties toe in het dialoogvenster **Power Query - Query's bewerken** zoals beschreven in de sectie [Een nieuwe gegevensbron maken](#create-a-new-data-source).

1. Selecteer **Opslaan** in Power Query na het voltooien van uw bewerkingen om uw wijzigingen op te slaan.
