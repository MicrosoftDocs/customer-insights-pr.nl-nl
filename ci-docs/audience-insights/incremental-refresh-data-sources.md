---
title: Incrementeel vernieuwen voor Power Query-gegevensbronnen
description: Vernieuw nieuwe en bijgewerkte gegevens voor grote gegevensbronnen op basis van Power Query.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d4b01be75d25fa0e120904924a193171eefec579
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268542"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Incrementeel vernieuwen voor op Power Query gebaseerde gegevensbronnen

Incrementeel vernieuwen voor gegevensbronnen biedt de volgende voordelen:

- **Sneller vernieuwingen**: alleen gewijzigde gegevens worden vernieuwd. U kunt bijvoorbeeld alleen de gegevens van de afgelopen vijf dagen van een historische gegevensset vernieuwen.
- **Verhoogde betrouwbaarheid**: met kleinere vernieuwingen hoeft u niet zo lang verbindingen met vluchtige bronsystemen te onderhouden, waardoor het risico op verbindingsproblemen afneemt.
- **Verminderd verbruik van resources**: door slechts een subset van uw totale gegevens te vernieuwen, worden uw computerresources efficiënter gebruikt en wordt de ecologische voetafdruk kleiner.

## <a name="configure-incremental-refresh"></a>Incrementele vernieuwing configureren

Doelgroepinzichten maakt incrementele vernieuwing mogelijk voor gegevensbronnen die zijn geïmporteerd via Power Query die incrementele opname ondersteunen. Bijvoorbeeld Azure SQL-databases met datum- en tijdvelden, die aangeven wanneer gegevensrecords voor het laatst zijn bijgewerkt.

1. [Een nieuwe gegevensbron maken op basis van Power Query](connect-power-query.md).

1. Geef een naam op voor de gegevensbron.

1. Selecteer een gegevensbron die incrementeel vernieuwen ondersteunt, zoals Azure SQL-database.

1. Selecteer de entiteiten of tabellen die u wilt opnemen.

1. Voltooi de transformatiestappen en selecteer **Volgende**.

1. In het dialoogvenster **Incrementeel vernieuwen instellen** selecteert u **Instellen** om de **Instellingen voor incrementeel vernieuwen** te openen. Als u selecteert **Overslaan** selecteert, zal de gegevensbron de volledige dataset vernieuwen.
   > [!TIP]
   > U kunt incrementeel vernieuwen ook later toepassen door een bestaande gegevensbron te bewerken.

1. In **Instellingen voor incrementeel vernieuwen** configureert u de incrementele vernieuwing voor alle entiteiten die u hebt geselecteerd bij het maken van de gegevensbron.

   > [!div class="mx-imgBorder"]
   > ![Entiteiten configureren in een gegevensbron voor incrementeel vernieuwen](media/incremental-refresh-settings.png "Entiteiten configureren in een gegevensbron voor incrementeel vernieuwen")

1. Selecteer een entiteit en geef de volgende details op:

   - **De primaire sleutel definiëren**: selecteer een primaire sleutel voor de entiteit of tabel.
   - **Het veld 'Laatst bijgewerkt' definiëren**: in dit veld worden alleen kenmerken van het type datum of tijd weergegeven. Selecteer een kenmerk dat aangeeft wanneer de records voor het laatst zijn bijgewerkt. Het wordt gebruikt om de records te identificeren die binnen het tijdsbestek voor incrementele verversing vallen.
   - **Controleer op updates elke**: geef op hoe lang het tijdsbestek voor de incrementele vernieuwing moet duren.

1. Selecteer **Opslaan** om het maken van de gegevensbron te voltooien. De eerste gegevensvernieuwing is een volledige vernieuwing. Daarna vindt de incrementele gegevensvernieuwing plaats zoals geconfigureerd in de vorige stap.


[!INCLUDE[footer-include](../includes/footer-banner.md)]