---
title: Incrementeel vernieuwen voor Power Query en Azure Data Lake-gegevensbronnen
description: Vernieuw nieuwe en bijgewerkte gegevens voor grote gegevensbronnen op basis van Power Query of Azure data lake-gegevensbronnen.
ms.date: 05/30/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: bff27bf7fec2bcb741846ae76bb1f616f459136c
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2022
ms.locfileid: "9012019"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Incrementeel vernieuwen voor Power Query en Azure Data Lake-gegevensbronnen

In dit artikel wordt beschreven hoe u incrementele vernieuwing voor gegevensbronnen configureert op basis van Power Query of Azure Data Lake.

Incrementeel vernieuwen voor gegevensbronnen biedt de volgende voordelen:

- **Sneller vernieuwingen**: alleen gewijzigde gegevens worden vernieuwd. U kunt bijvoorbeeld alleen de gegevens van de afgelopen vijf dagen van een historische gegevensset vernieuwen.
- **Verhoogde betrouwbaarheid**: met kleinere vernieuwingen hoeft u niet zo lang verbindingen met vluchtige bronsystemen te onderhouden, waardoor het risico op verbindingsproblemen afneemt.
- **Verminderd verbruik van resources**: door slechts een subset van uw totale gegevens te vernieuwen, worden uw computerresources efficiënter gebruikt en wordt de ecologische voetafdruk kleiner.

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>Incrementeel vernieuwen voor gegevensbronnen configureren die zijn gebaseerd op Power Query

Customer Insights maken incrementele vernieuwing mogelijk voor gegevensbronnen die zijn geïmporteerd via Power Query die incrementele opname ondersteunen. Bijvoorbeeld Azure SQL-databases met datum- en tijdvelden, die aangeven wanneer gegevensrecords voor het laatst zijn bijgewerkt.

1. [Maak een nieuwe gegevensbron op basis van Power Query](connect-power-query.md).

1. Selecteer een gegevensbron die incrementeel vernieuwen ondersteunt, zoals [Azure SQL-database](/power-query/connectors/azuresqldatabase).

1. Selecteer de entiteiten of tabellen die u wilt opnemen.

1. Voltooi de transformatiestappen en selecteer **Volgende**.

1. In het dialoogvenster **Incrementeel vernieuwen instellen** selecteert u **Instellen** om de **Instellingen voor incrementeel vernieuwen** te openen. Als u selecteert **Overslaan** selecteert, zal de gegevensbron de volledige dataset vernieuwen.
   > [!TIP]
   > U kunt incrementeel vernieuwen ook later toepassen door een bestaande gegevensbron te bewerken.

1. In **Instellingen voor incrementeel vernieuwen** configureert u de incrementele vernieuwing voor alle entiteiten die u hebt geselecteerd bij het maken van de gegevensbron.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Instellingen voor incrementele vernieuwing configureren.":::

1. Selecteer een entiteit en geef de volgende details op:

   - **De primaire sleutel definiëren**: selecteer een primaire sleutel voor de entiteit of tabel.
   - **Het veld 'Laatst bijgewerkt' definiëren**: in dit veld worden alleen kenmerken van het type datum of tijd weergegeven. Selecteer een kenmerk dat aangeeft wanneer de records voor het laatst zijn bijgewerkt. Het wordt gebruikt om de records te identificeren die binnen het tijdsbestek voor incrementele verversing vallen.
   - **Controleer op updates elke**: geef op hoe lang het tijdsbestek voor de incrementele vernieuwing moet duren.

1. Selecteer **Opslaan** om het maken van de gegevensbron te voltooien. De eerste gegevensvernieuwing is een volledige vernieuwing. Daarna vindt de incrementele gegevensvernieuwing plaats zoals geconfigureerd in de vorige stap.

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>Incrementeel vernieuwen configureren voor Azure Data Lake-gegevensbronnen

Customer Insights maakt incrementele vernieuwing mogelijk voor gegevensbronnen die zijn verbonden met Azure Data Lake Storage. Als u incrementele opname en vernieuwing voor een entiteit wilt gebruiken, configureert u die entiteit bij het toevoegen van de Azure Data Lake-gegevensbron of later bij het bewerken van de gegevensbron. De entiteitsgegevensmap moet de volgende mappen bevatten:

- **FullData**: map met gegevensbestanden die initiële records bevatten
- **IncrementalData**: map met datum/tijd-hiërarchiemappen in de indeling **jjjj/mm/dd/uu** die de incrementele updates bevat. **uu** staat voor het uur (UTC) van de updates en bevat de mappen **Upserts** en **Verwijderde items**. **Upserts** bevat gegevensbestanden met updates van bestaande records of nieuwe records. **Verwijderde items** bevat gegevensbestanden met records die moeten worden verwijderd.

1. Wanneer u een gegevensbron toevoegt of bewerkt, navigeert u naar het deelvenster **Kenmerken** voor de entiteit.

1. Bekijk de kenmerken. Zorg ervoor dat een gemaakt of laatst bijgewerkt datumkenmerk is ingesteld met een *dateTime* **Gegevensindeling** en een *Calendar.Date* **Semantisch type**. Bewerk het kenmerke indien nodig en selecteer **Gereed**.

1. Bewerk de entiteit in het deelvenster **Entiteiten selecteren**. Het selectievakje **Incremente opname** is ingeschakeld.

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="Entiteiten configureren in een gegevensbron voor incrementeel vernieuwen.":::

   1. Blader naar de hoofdmap die de .csv- of .parquet-bestanden bevat voor volledige gegevens, incrementele gegevensupserts en incrementele gegevensverwijderingen.
   1. Voer de extensie in voor de volledige gegevens en beide incrementele bestanden (\.csv of \.parquet).
   1. Selecteer **Save**.

1. Selecteer het datum-tijdstempelkenmerk bij **Laatst bijgewerkt**.

1. Als de **Primaire sleutel** niet is geselecteerd, selecteert u de primaire sleutel. De primaire sleutel is een kenmerk dat uniek is voor de entiteit. Als een kenmerk een geldige primaire sleutel is, mag het geen dubbele waarden, ontbrekende waarden of null-waarden bevatten. Kenmerken van het gegevenstype string, integer en GUID worden ondersteund als primaire sleutels.

1. Selecteer **Sluiten** om het deelvenster op te slaan en te sluiten.

1. Ga verder met het toevoegen of bewerken van de gegevensbron.

[!INCLUDE [footer-include](includes/footer-banner.md)]
