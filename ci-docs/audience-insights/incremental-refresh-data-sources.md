---
title: Incrementeel vernieuwen voor Power Query-gegevensbronnen
description: Vernieuw nieuwe en bijgewerkte gegevens voor grote gegevensbronnen op basis van Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 62632efda3c0c7e53fcdd8864b053ba93e2918bc
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353675"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Incrementeel vernieuwen voor gegevensbronnen die zijn gebaseerd op Power Query

In dit artikel wordt beschreven hoe u incrementele vernieuwing voor gegevensbronnen configureert op basis van Power Query.

Incrementeel vernieuwen voor gegevensbronnen biedt de volgende voordelen:

- **Sneller vernieuwingen**: alleen gewijzigde gegevens worden vernieuwd. U kunt bijvoorbeeld alleen de gegevens van de afgelopen vijf dagen van een historische gegevensset vernieuwen.
- **Verhoogde betrouwbaarheid**: met kleinere vernieuwingen hoeft u niet zo lang verbindingen met vluchtige bronsystemen te onderhouden, waardoor het risico op verbindingsproblemen afneemt.
- **Verminderd verbruik van resources**: door slechts een subset van uw totale gegevens te vernieuwen, worden uw computerresources efficiënter gebruikt en wordt de ecologische voetafdruk kleiner.

## <a name="configure-incremental-refresh"></a>Incrementele vernieuwing configureren

Doelgroepinzichten maken incrementele vernieuwing mogelijk voor gegevensbronnen die zijn geïmporteerd via Power Query die incrementele opname ondersteunen. Bijvoorbeeld Azure SQL-databases met datum- en tijdvelden, die aangeven wanneer gegevensrecords voor het laatst zijn bijgewerkt.

1. [Maak een nieuwe gegevensbron op basis van Power Query](connect-power-query.md).

1. Geef een **naam** op voor de gegevensbron.

1. Selecteer een gegevensbron die incrementeel vernieuwen ondersteunt, zoals [Azure SQL-database](/power-query/connectors/azuresqldatabase).

1. Selecteer de entiteiten of tabellen die u wilt opnemen.

1. Voltooi de transformatiestappen en selecteer **Volgende**.

1. In het dialoogvenster **Incrementeel vernieuwen instellen** selecteert u **Instellen** om de **Instellingen voor incrementeel vernieuwen** te openen. Als u selecteert **Overslaan** selecteert, zal de gegevensbron de volledige dataset vernieuwen.
   > [!TIP]
   > U kunt incrementeel vernieuwen ook later toepassen door een bestaande gegevensbron te bewerken.

1. In **Instellingen voor incrementeel vernieuwen** configureert u de incrementele vernieuwing voor alle entiteiten die u hebt geselecteerd bij het maken van de gegevensbron.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Entiteiten configureren in een gegevensbron voor incrementeel vernieuwen.":::

1. Selecteer een entiteit en geef de volgende details op:

   - **De primaire sleutel definiëren**: selecteer een primaire sleutel voor de entiteit of tabel.
   - **Het veld 'Laatst bijgewerkt' definiëren**: in dit veld worden alleen kenmerken van het type datum of tijd weergegeven. Selecteer een kenmerk dat aangeeft wanneer de records voor het laatst zijn bijgewerkt. Het wordt gebruikt om de records te identificeren die binnen het tijdsbestek voor incrementele verversing vallen.
   - **Controleer op updates elke**: geef op hoe lang het tijdsbestek voor de incrementele vernieuwing moet duren.

1. Selecteer **Opslaan** om het maken van de gegevensbron te voltooien. De eerste gegevensvernieuwing is een volledige vernieuwing. Daarna vindt de incrementele gegevensvernieuwing plaats zoals geconfigureerd in de vorige stap.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
