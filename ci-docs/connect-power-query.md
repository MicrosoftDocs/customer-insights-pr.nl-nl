---
title: Gegevens opnemen via een Power Query-connector (met video)
description: Connectors voor gegevensbronnen op basis van Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 50258365c3134c588aa79ec72c66d0de329e0ff1
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646184"
---
# <a name="connect-to-a-power-query-data-source"></a>Verbinding maken met een Power Query-gegevensbron

Power Query biedt een brede reeks connectors voor het opnemen van gegevens. De meeste van deze connectors worden ondersteund door Dynamics 365 Customer Insights. 

Bij het toevoegen van gegevensbronnen op basis van Power Query-connectors worden over het algemeen de stappen gevolgd die in deze sectie worden beschreven. Afhankelijk van de connector die u gebruikt, kan echter andere informatie vereist zijn. Zie de documentatie over afzonderlijke connectors in de [Power Query-connectorreferentie](/power-query/connectors/) voor meer informatie.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Een nieuwe gegevensbron maken

1. Ga naar **Gegevens** > **Gegevensbronnen**.

1. Selecteer **Gegevensbron toevoegen**.

1. Selecteer **Microsoft Power Query**.

1. Geef een **Naam** op voor de gegevensbron en selecteer **Volgende** om de gegevensbron te maken.

1. Kies een van de [beschikbare connectors](#available-power-query-data-sources). In dit voorbeeld selecteren we de connector **Tekst/CSV**.

1. Voer de vereiste gegevens in voor de **Verbindingsinstellingen** voor de geselecteerde connector en selecteer **Volgende** om een voorbeeld van de gegevens te zien.

1. Selecteer **Gegevens transformeren**. In deze stap voegt u entiteiten toe aan uw gegevensbron. Entiteiten zijn gegevenssets. Als u een database hebt die meerdere gegevenssets bevat, is elke gegevensset zijn eigen entiteit.

1. Met het dialoogvenster **Power Query - Query's bewerken** kunt u de gegevens bekijken en verfijnen. De entiteiten die de systemen in uw geselecteerde gegevensbron hebben geïdentificeerd, verschijnen in het linkerdeelvenster.

   > [!div class="mx-imgBorder"]
   > ![Dialoogvenster Query's bewerken.](media/data-manager-configure-edit-queries.png "Dialoogvenster Query's bewerken")

1. U kunt uw gegevens ook transformeren. Selecteer een entiteit om te bewerken of transformeren. Gebruik de opties in het Power Query-venster om transformaties toe te passen. Elke transformatie wordt vermeld onder **Toegepaste stappen**. Power Query biedt tal van vooraf gebouwde transformatieopties. Voor meer informatie raadpleegt u [Power Query-transformaties](/power-query/power-query-what-is-power-query#transformations).

   We raden u aan de volgende transformaties te gebruiken:

   - Als u gegevens opneemt uit een CSV-bestand, bevat de eerste rij vaak kopteksten. Ga naar **Transformeren** en selecteer **De eerste rij als veldnamen gebruiken**.
   - Zorg ervoor dat het gegevenstype correct is ingesteld. Selecteer bijvoorbeeld een datumtype voor datumvelden.

1. Als u extra entiteiten wilt toe te voegen aan uw gegevensbron in het dialoogvenster **Query's bewerken**, ga naar **Start** en selecteer **Gegevens ophalen**.

1. Selecteer **Opslaan** onder aan het Power Query-venster om de transformaties op te slaan. Nadat u hebt opgeslagen, ziet u gegevensbron onder **Gegevens** > **Gegevensbronnen**.

1. Op de pagina **Gegevensbronen** ziet u dat de nieuwe gegevensbron de status **Vernieuwen** heeft.

## <a name="available-power-query-data-sources"></a>Beschikbare Power Query-gegevensbronnen

Zie de [Power Query-connectorreferentie](/power-query/connectors/) voor een lijst met connectors die u kunt gebruiken om gegevens naar Customer Insights te importeren. 

Connectors met een vinkje in de kolom **Customer Insights (gegevensstromen)** zijn beschikbaar om nieuwe gegevensbronnen te maken op basis van Power Query. Bekijk de documentatie van een specifieke connector voor meer informatie over de vereisten, beperkingen en andere details.

## <a name="edit-power-query-data-sources"></a>Power Query-gegevensbronnen bewerken

> [!NOTE]
> Het is misschien niet mogelijk om wijzigingen aan te brengen in gegevensbronnen die momenteel worden gebruikt in een van de processen van de app (bijvoorbeeld *segmentatie*, *afstemming* of *samenvoeging*). 
>
> Op de pagina **Instellingen** kunt u de voortgang van elk van de actieve processen volgen. Wanneer een proces is voltooid, kunt u terugkeren naar de pagina **Gegevensbronnen** en uw wijzigingen aanbrengen.

1. Ga naar **Gegevens** > **Gegevensbronnen**.

2. Selecteer het verticale weglatingsteken naast de gegevensbron die u wilt wijzigen en selecteer **Bewerken** uit het vervolgkeuzemenu.

   > [!div class="mx-imgBorder"]
   > ![Optie bewerken.](media/edit-option-data-sources.png "Optie bewerken")

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]
   
3. Pas uw wijzigingen en transformaties toe in het dialoogvenster **Power Query - Query's bewerken** zoals beschreven in de sectie [Een nieuwe gegevensbron maken](#create-a-new-data-source).

4. Selecteer **Opslaan** in Power Query na het voltooien van uw bewerkingen om uw wijzigingen op te slaan.


[!INCLUDE [footer-include](includes/footer-banner.md)]