---
title: Gegevens opnemen via een Power Query-connector
description: Connectors voor databronnen op basis van Power Query.
ms.date: 11/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 5d54d33c235e646644e8874e5b0c28898dcff11a
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732212"
---
# <a name="connect-to-a-power-query-data-source"></a>Verbinden met een Power Query-gegevensbron

Power Query biedt een brede set connectors om gegevens op te nemen. De meeste van deze connectors worden ondersteund door Dynamics 365 Customer Insights. Bij het toevoegen van gegevensbronnen op basis van Power Query-connectors worden gewoonlijk de stappen gevolgd die in de volgende sectie worden beschreven. Afhankelijk van de connector die u gebruikt, kan echter andere informatie vereist zijn. Zie voor meer informatie de documentatie over afzonderlijke connectors in [Referentie voor Power Query-connectors](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Een nieuwe gegevensbron maken

1. Ga in doelgroepinzichten naar **Gegevens** > **Gegevensbronnen**.

1. Selecteer **Gegevensbron toevoegen**.

1. Kies de methode **Gegevens importeren** en selecteer **Volgende**.

1. Geef een **Naam** op voor de gegevensbron en selecteer **Volgende** om de gegevensbron te maken. Naamrichtlijnen: 
   - Begin met een letter.
   - Gebruik alleen letters en cijfers. Speciale tekens en spaties zijn niet toegestaan.
   - Gebruik minimaal 3 en maximaal 64 tekens.

1. Kies een van de [beschikbare connectors](#available-power-query-data-sources). Voor dit voorbeeld selecteren we de connector **Tekst/CSV**.

1. Voer de vereiste gegevens in voor de **Verbindingsinstellingen** voor de geselecteerde connector en selecteer **Volgende** om een voorbeeld van de gegevens te zien.

1. Selecteer **Gegevens transformeren**. In deze stap voegt u entiteiten toe aan uw gegevensbron. Entiteiten zijn gegevenssets. Als u een database hebt die meerdere gegevenssets bevat, is elke gegevensset zijn eigen entiteit.

1. In het dialoogvenster **Power Query - Query's bewerken** kunt u de gegevens bekijken en verfijnen. De entiteiten die de systemen in uw geselecteerde gegevensbron hebben geïdentificeerd, verschijnen in het linkerdeelvenster.

   > [!div class="mx-imgBorder"]
   > ![Dialoogvenster Query's bewerken.](media/data-manager-configure-edit-queries.png "Dialoogvenster Query's bewerken")

1. U kunt uw gegevens ook transformeren. Selecteer een entiteit om te bewerken of transformeren. Gebruik de opties in het venster Power Query om transformaties toe te passen. Elke transformatie wordt vermeld onder **Toegepaste stappen**. Power Query biedt tal van vooraf gebouwde transformatie-opties. Zie [Power Query-transformaties](/power-query/power-query-what-is-power-query#transformations) voor meer informatie.

1. U kunt extra entiteiten toevoegen aan uw gegevensbron door **Gegevens ophalen** te selecteren in het dialoogvenster **Query's bewerken**.

   Deze transformaties worden sterk aanbevolen:

   - Als u gegevens opneemt uit een CSV-bestand, bevat de eerste rij vaak kopteksten. Ga naar **Tabel transformeren** en selecteer **Gebruik kopteksten als eerste rij**.
   - Zorg ervoor dat het gegevenstype correct is ingesteld.

1. Selecteer **Opslaan** onderin het venster Power Query om de transformaties op te slaan. Nadat u hebt opgeslagen, ziet u gegevensbron onder **Gegevens** > **Gegevensbronnen**.

1. Op de pagina **Gegevensbronen** ziet u dat de nieuwe gegevensbron de status **Vernieuwen** heeft.

## <a name="available-power-query-data-sources"></a>Beschikbare Power Query-gegevensbronnen

Zie [Referentie voor Power Query-connectors](/power-query/connectors/) voor een up-to-date lijst met connectors die u kunt selecteren om gegevens te importeren in Customer Insights. 

Connectors met een vinkje in de kolom **Customer Insights (gegevensstromen)** zijn beschikbaar om nieuwe gegevensbronnen te maken op basis van Power Query. Bekijk de documentatie van een specifieke connector voor meer informatie over de vereisten, beperkingen en andere details.

## <a name="edit-power-query-data-sources"></a>Power Query-gegevensbronnen bewerken

> [!NOTE]
> Het is misschien niet mogelijk om wijzigingen aan te brengen in gegevensbronnen die momenteel worden gebruikt in een van de processen van de app (bijvoorbeeld *segmentatie*, *afstemming* of *samenvoeging*). 
>
> Met de pagina **Instellingen** kunt u de voortgang van elk van de actieve processen volgen. Wanneer een proces is voltooid, kunt u terugkeren naar de pagina **Gegevensbronnen** en uw wijzigingen aanbrengen.

1. Ga in doelgroepinzichten naar **Gegevens** > **Gegevensbronnen**.

2. Selecteer het verticale weglatingsteken naast de gegevensbron die u wilt wijzigen en selecteer **Bewerken** uit het vervolgkeuzemenu.

   > [!div class="mx-imgBorder"]
   > ![Optie bewerken.](media/edit-option-data-sources.png "Optie bewerken")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. Pas uw wijzigingen en transformaties toe in het dialoogvenster **Power Query - Query's bewerken** zoals beschreven in de sectie [Een nieuwe gegevensbron maken](#create-a-new-data-source).

4. Selecteer **Opslaan** in Power Query na het voltooien van uw bewerkingen om uw wijzigingen op te slaan.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
