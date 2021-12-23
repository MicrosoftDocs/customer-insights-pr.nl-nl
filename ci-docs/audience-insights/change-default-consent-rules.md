---
title: Standaard toestemmingsregels voor segmenten beheren
description: Met de functie voor toestemmingsbeheer kunt u de standaardtoestemmingsregels uitschakelen of wijzigen als overschrijvingen zijn ingeschakeld.
ms.date: 12/01/2021
ms.service: customer-insights
mms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 28c9ea49b1f3aebd3abd7d4de58fe61e6474158b
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/03/2021
ms.locfileid: "7884164"
---
# <a name="disable-or-change-default-consent-rules"></a>Standaard toestemmingsregels uitschakelen of wijzigen

Als uw organisatie de [functie voor toestemmingsbeheer](../consent-management/overview.md) in combinatie met doelgroepinzichten gebruikt, [kunnen beheerders toestemmingsregels afdwingen](activate-consent.md) voor segmenten. 

Met regels voor afgedwongen toestemming in het segmentgebied informeert elk segment over de status van toestemmingscontrole en -regels. Als overschrijvingen zijn toegestaan, worden standaard toestemmingsregels uitgeschakeld voor specifieke segmenten. Elke maker van een segment kan meer toestemmingsregels toevoegen naast de standaardregels voor een segment. 

## <a name="for-administrators"></a>Voor beheerders

:::image type="content" source="../consent-management/media/consent-rules-segment.png" alt-text="Opbouwfunctie voor segmenten met opties voor toestemmingsregels.":::

**Standaardtoestemmingsregels deactiveren:**

1. Selecteer in de melding **Toestemmingsregels** de optie **Zie details**. 

1. Stel de schakeloptie **Standaard toestemmingsregels** in op **Uit**.

**Meer toestemmingsregels toevoegen:**

1. Selecteer in de melding **Toestemmingsregels** de optie **Zie details**. 

1. Selecteer **Toestemmingsregels toevoegen** en kies een toestemmingsregel in de vervolgkeuzelijst **Gegevenstype voor toestemming selecteren**.

1. Selecteer **Opslaan** om de nieuwe regel op het segment toe te passen.

## <a name="for-contributors"></a>Voor inzenders

Als u een segment wilt maken zonder afgedwongen toestemmingsregels, moet u uw beheerder vragen deze uit te schakelen voor uw segment. U kunt echter uw eigen toestemmingsregels toevoegen aan segmenten die u bezit en beheert.

Het is een proces met drie stappen: 
1. [Maak het segment](segments.md) in doelgroepinzichten en sla het op. 

1. Deel de segmentnaam met uw beheerder en vraag hen om [overschrijvingen voor uw segment in te schakelen](activate-consent.md). 

1. Open uw segmenten opnieuw. Selecteer in de melding **Toestemmingsregels** de optie **Details bekijken** en voeg de toestemmingsregels toe die u wilt toepassen. **Sla** vervolgens uw segment op en **voer het uit**.



[!INCLUDE[footer-include](../includes/footer-banner.md)] 
