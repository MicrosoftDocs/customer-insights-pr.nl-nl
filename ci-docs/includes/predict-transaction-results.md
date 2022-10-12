---
ms.openlocfilehash: a67714de5aae80a0080c0e631ae6f8986eb2a003
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9611098"
---
- **Prestaties trainingsmodel**: beoordelingscijfers A, B of C geven de prestaties van de voorspelling aan en kan u helpen bij het nemen van de beslissing om de resultaten te gebruiken die zijn opgeslagen in de uitvoerentiteit.

  Cijfers worden bepaald op basis van de volgende regels:
  - **A** wanneer het model nauwkeurig ten minste 50% van de totale voorspellingen heeft voorspeld, en wanneer het percentage nauwkeurige voorspellingen voor verlopen klanten met ten minste 10% groter is dan het basislijnpercentage.
  - **B** wanneer het model nauwkeurig ten minste 50% van de totale voorspellingen heeft voorspeld, en wanneer het percentage nauwkeurige voorspellingen voor verlopen klanten tot 10% groter is dan het basislijnpercentage.
  - **C** wanneer het model nauwkeurig minder dan 50% van de totale voorspellingen heeft voorspeld, of wanneer het percentage nauwkeurige voorspellingen voor verlopen klanten minder is dan het basislijnpercentage.
  - **Basislijn** neemt de invoer van het voorspellingstijdvenster voor het model (bijvoorbeeld een jaar), en deelt de tijd in fracties door deze door 2 te delen totdat de tijdsperiode van een maand of minder wordt bereikt. Het gebruikt deze breuken om een bedrijfsregel te maken voor klanten die in dit tijdsbestek niets hebben gekocht. Deze klanten worden als verlopen beschouwd. De op tijd gebaseerde bedrijfsregel met de hoogste kans om te goed voorspellen wie waarschijnlijk zal verlopen, wordt gekozen als het basislijnmodel.

- **Waarschijnlijkheid van verloop (aantal klanten)**: groepen klanten op basis van hun voorspelde verlooprisico. Optioneel kunt u [segmenten van klanten maken](../prediction-based-segment.md) met een hoog verlooprisico. Dergelijke segmenten helpen u te begrijpen waar uw grens voor segmentlidmaatschap moet liggen.

- **Meest invloedrijke factoren**: er zijn veel factoren waarmee rekening wordt gehouden bij het maken van uw voorspelling. Voor elke factor wordt het belang berekend van de gecombineerde voorspellingen die een model maakt. Gebruik deze factoren om uw voorspellingsresultaten te helpen valideren. Of gebruik deze informatie later om [segmenten te maken](../prediction-based-segment.md) die het verlooprisico voor klanten kunnen helpen beïnvloeden.