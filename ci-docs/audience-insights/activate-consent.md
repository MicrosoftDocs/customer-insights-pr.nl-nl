---
title: Toestemmingsregels voor segmenten activeren
description: Volg deze stappen om toestemmingsgegevens te koppelen en toestemmingscontroles te activeren in doelgroepinzichten. Een beheerder kan toestemmingscontroles ook uitschakelen.
ms.date: 11/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 552cb0739c4d17266dd028638df067f3384b738a
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/03/2021
ms.locfileid: "7884068"
---
# <a name="activate-consent-rules"></a>Toestemmingsregels activeren

Het [Toestemmingscentrum (preview)](../consent-management/overview.md) helpt u toestemmingsgegevens uit verschillende bronnen op elkaar af te stemmen. Gebruik de verenigde entiteit *Toestemming* om standaard toestemmingscontroles toe te passen. Na het importeren van toestemmingsgegevens in het Toestemmingscentrum en het configureren van de regels voor de gegevens, wordt de entiteit *Toestemming* automatisch gesynchroniseerd met doelgroepinzichten.

## <a name="enable-consent-checks"></a>Toestemmingscontroles inschakelen

Als toestemmingsgegevens zijn geïmporteerd in het Toestemmingscentrum (preview) en de regels zijn ingesteld, kunt u toestemmingscontroles inschakelen. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Het tabblad Toestemming in de instellingen voor doelgroepinzichten met geactiveerde toestemmingsgegevens.":::

1. Ga in doelgroepinzichten naar **Beheer** > **Systeem**.

1. Selecteer het tabblad **Toestemming (preview)**.

1. Stel in de sectie **Toestemmingscontroles inschakelen** de schakeloptie voor alle gebieden die u wilt inschakelen in op **Aan**.

1. Schakel het selectievakje **Het vervangen van standaard toestemmingsregels toestaan** in om de standaard toestemmingscontroles te verwijderen die voor een bepaald segment worden afgedwongen. 

1. Geef in het vervolgkeuzemenu aan waar u overschrijvingen wilt toestaan.     

1. Kies in de sectie **Toestemming aan klantprofielen koppelen** het kenmerk dat wordt gebruikt als id om toestemmingsgegevens te koppelen aan klantgegevens. Het is waarschijnlijk een telefoonnummer of e-mailadres. 

1. Selecteer **Opslaan** om uw instellingen toe te passen.

## <a name="disable-consent-checks"></a>Toestemmingscontroles uitschakelen

Als u wilt stoppen met het gebruik van toestemmingsgegevens in doelgroepinzichten, moet een beheerder de systeeminstellingen dienovereenkomstig bijwerken.

1. Ga in doelgroepinzichten naar **Beheer** > **Systeem**.

1. Selecteer het tabblad **Toestemming (preview)**.

1. Schakel in de sectie **Toestemmingscontroles inschakelen** de schakeloptie in op **Uit**.

> [!TIP]
> Zie [Systeeminstellingen in Toestemmingscentrum (preview)](../consent-management/system-settings.md) als u wilt stoppen met het gebruiken van de toestemmingsbeheerfunctie.
