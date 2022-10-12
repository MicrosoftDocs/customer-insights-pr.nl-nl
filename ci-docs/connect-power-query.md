---
title: Verbinding maken met een Power Query-gegevensbron (met video)
description: Neem gegevens op via een Power Query-connector (met video).
ms.date: 09/29/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 4cc7e57dfb0f8d050e91adc441c24e849882f5d8
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609870"
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

1. Selecteer **Gegevens transformeren**.

1. Controleer en verfijn uw gegevens op de pagina **Power Query - Query's bewerken**. De entiteiten die de systemen in uw geselecteerde gegevensbron hebben geïdentificeerd, verschijnen in het linkerdeelvenster.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Dialoogvenster Query's bewerken":::

1. Transformeer uw gegevens. Selecteer een entiteit om te bewerken of transformeren. Gebruik de opties in het Power Query-venster om transformaties toe te passen. Elke transformatie wordt vermeld onder **Toegepaste stappen**. Power Query biedt tal van [vooraf gebouwde transformatie](/power-query/power-query-what-is-power-query#transformations)opties.

   > [!IMPORTANT]
   > We raden u aan de volgende transformaties te gebruiken:
   >
   > - Als u gegevens opneemt uit een CSV-bestand, bevat de eerste rij vaak kopteksten. Ga naar **Transformeren** en selecteer **De eerste rij als veldnamen gebruiken**.
   > - Zorg ervoor dat het gegevenstype correct is ingesteld en overeenkomt met de gegevens. Selecteer bijvoorbeeld een datumtype voor datumvelden.

1. Als u extra entiteiten wilt toe te voegen aan uw gegevensbron in het dialoogvenster **Query's bewerken**, ga naar **Start** en selecteer **Gegevens ophalen**. Herhaal stap 5-10 totdat u alle entiteiten voor deze gegevensbron hebt toegevoegd. Als u een database hebt die meerdere gegevenssets bevat, is elke gegevensset zijn eigen entiteit.

1. Selecteer **Save**. De pagina **Gegevensbronnen** wordt geopend met de nieuwe gegevensbron met de status **Vernieuwen**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Het laden van gegevens kan enige tijd vergen. Na een succesvolle vernieuwing kunnen de opgenomen gegevens worden bekeken vanaf de pagina [**Entiteiten**](entities.md).

> [!CAUTION]
>
> - Met een op basis van Power Query wordt een [gegevensstroom in Dataverse](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) gemaakt. Wijzig de naam van een gegevensstroom niet in het Power Platform-beheercentrum dat wordt gebruikt in Customer Insights. Het hernoemen van een gegevensstroom veroorzaakt problemen met de verwijzingen tussen de Customer Insights-gegevensbron en de Dataverse-gegevensstroom.
> - Gelijktijdige evaluaties voor Power Query-gegevensbronnen in Customer Insights hebben dezelfde [vernieuwingslimieten als gegevensstromen in PowerBI.com](/power-query/power-query-online-limits#refresh-limits). Als een gegevensvernieuwing mislukt omdat deze de evaluatielimiet heeft bereikt, raden we u aan het vernieuwingsschema voor elke gegevensstroom aan te passen om ervoor te zorgen dat de gegevensbronnen niet tegelijkertijd worden verwerkt.

### <a name="available-power-query-data-sources"></a>Beschikbare Power Query-gegevensbronnen

Zie de [Power Query-connectorreferentie](/power-query/connectors/) voor een lijst met connectors die u kunt gebruiken om gegevens naar Customer Insights te importeren.

Connectors met een vinkje in de kolom **Customer Insights (gegevensstromen)** zijn beschikbaar om nieuwe gegevensbronnen te maken op basis van Power Query. Bekijk de documentatie van een specifieke connector voor meer informatie over de vereisten, [querybeperkingen](/power-query/power-query-online-limits) en andere informatie.

## <a name="add-data-from-on-premises-data-sources"></a>Gegevens toevoegen vanuit on-premises gegevensbronnen

Het opnemen van gegevens uit on-premises gegevensbronnen wordt ondersteund op basis van Microsoft Power Platform-gegevensstromen (PPDF's). U kunt gegevensstromen in Customer Insights inschakelen door [de omgevings-URL voor Microsoft Dataverse te verstrekken](create-environment.md) bij het instellen van de omgeving.

Gegevensbronnen die zijn gemaakt na het koppelen van een Dataverse-omgeving met Customer Insights maken standaard gebruik van [Power Platform-gegevensstromen](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Gegevensstromen ondersteunen on-premises connectiviteit met behulp van de gegevensgateway. U kunt gegevensbronnen verwijderen en opnieuw maken die bestonden voordat een Dataverse-omgeving werd gekoppeld [met behulp van on-premises gegevensgateways](/data-integration/gateway/service-gateway-app).

Gegevensgateways van een bestaande Power BI- of Power Apps-omgeving zijn zichtbaar en u kunt ze opnieuw gebruiken in Customer Insights als de gegevensgateway en de Customer Insights-omgeving zich in dezelfde Azure-regio bevinden. De pagina met gegevensbronnen toont koppelingen om naar de Microsoft Power Platform-omgeving te gaan waar u on-premises gegevensgateways kunt bekijken en configureren.

> [!IMPORTANT]
> Zorg ervoor dat uw gateways zijn bijgewerkt naar de nieuwste versie. U kunt een update installeren en een gateway opnieuw configureren vanaf een prompt die direct op het gatewayscherm wordt weergegeven of [de meest recente versie downloaden](https://powerapps.microsoft.com/downloads/). Als u niet de nieuwste gatewayversie gebruikt, mislukt het vernieuwen van de gegevensstroom met foutmeldingen zoals **Het trefwoord wordt niet ondersteund: configuratie-eigenschappen. Parameternaam: trefwoord**.
>
> Fouten met on-premises-gegevensgateways in Customer Insights worden vaak veroorzaakt door configuratieproblemen. Zie [Problemen met de on-premises gegevensgateway oplossen](/data-integration/gateway/service-gateway-tshoot) voor meer informatie over het oplossen van problemen met gegevensgateways.

## <a name="edit-power-query-data-sources"></a>Power Query-gegevensbronnen bewerken

> [!NOTE]
> Het is misschien niet mogelijk om wijzigingen aan te brengen in gegevensbronnen die momenteel worden gebruikt in een van de processen van de app (bijvoorbeeld segmentatie of gegevensharmonisatie).
>
> Op de pagina **Instellingen** kunt u de voortgang van elk van de actieve processen volgen. Wanneer een proces is voltooid, kunt u terugkeren naar de pagina **Gegevensbronnen** en uw wijzigingen aanbrengen.

1. Ga naar **Gegevens** > **Gegevensbronnen**.

1. Selecteer **Bewerken** naast de gegevensbron die u wilt bijwerken.

1. Pas uw wijzigingen en transformaties toe in het dialoogvenster **Power Query - Query's bewerken** zoals beschreven in de sectie [Een nieuwe gegevensbron maken](#create-a-new-data-source).

1. Selecteer **Opslaan** om uw wijzigingen toe te passen en terug te keren naar de pagina **Gegevensbronnen**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupt-data"></a>Veelvoorkomende redenen voor opnamefouten of beschadigde gegevens

### <a name="data-type-does-not-match-data"></a>Gegevenstype komt niet overeen met gegevens

De meest voorkomende mismatch van het gegevenstype doet zich voor wanneer een datumveld niet is ingesteld op de juiste datumnotatie.

De gegevens kunnen bij de bron worden hersteld en opnieuw worden opgenomen. Of de transformatie kan worden uitgevoerd binnen Customer Insights. De transformatie uitvoeren:

1. Ga naar **Gegevens** > **Gegevensbronnen**.

1. Selecteer **Bewerken** naast de gegevensbron met de beschadigde gegevens.

1. Selecteer **Volgende**.

1. Selecteer elk van de query's en zoek naar transformaties die zijn toegepast in "Toegepaste stappen" die onjuist zijn, of datumkolommen die niet zijn getransformeerd met een datumnotatie.

   :::image type="content" source="media/PQ_corruped_date.png" alt-text="Power Query - Bewerken met onjuiste datumnotatie":::

1. Wijzig het gegevenstype zodat dit overeenkomt met de gegevens.

1. Selecteer **Save**. Die gegevensbron wordt vernieuwd.

## <a name="troubleshoot-ppdf-power-query-based-data-source-refresh-issues"></a>Vernieuwingsproblemen met op PPDF Power Query gebaseerde gegevensbron oplossen

Als de gegevens verouderd zijn of als u fouten ontvangt na een vernieuwing van de gegevensbron, voert u de volgende stappen uit:

1. Navigeer naar [Power Platform](https://make.powerapps.com).

1. Selecteer de **omgeving** voor uw Customer Insights-exemplaar.

1. Navigeer naar **Gegevensstromen**.

1. Selecteer voor de gegevensstroom die overeenkomt met de gegevensbron in Customer Insights het verticale weglatingsteken (&vellip;) en selecteer vervolgens **Vernieuwingsgeschiedenis weergeven**.

1. Als de gegevensstroom **Geslaagd** als **status** heeft, is mogelijk het eigendom van de op Power Query gebaseerde gegevensbron gewijzigd:

   1. Bekijk het vernieuwingsschema vanuit de vernieuwingsgeschiedenis.
   1. Stel het schema van de nieuwe eigenaar in en sla de instellingen op.

1. Als de gegevensstroom een **status** van **Mislukt** heeft:

   1. Download het bestand met de vernieuwingsgeschiedenis.
   1. Bekijk het gedownloade bestand voor de reden voor de fout.
   1. Als de fout niet kan worden opgelost, selecteert u **?** om een ondersteuningsticket te openen. Neem het gedownloade bestand met de vernieuwingsgeschiedenis op.


[!INCLUDE [footer-include](includes/footer-banner.md)]
