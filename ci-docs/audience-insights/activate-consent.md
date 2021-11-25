---
title: Toestemmingsregels activeren voor segmenten in doelgroepinzichten
description: Stappen om toestemmingsgegevens te koppelen en toestemmingscontroles te activeren in doelgroepinzichten.
ms.date: 11/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 33ec3a684c2ca47badb4e5461f069d1b2e4a4f3d
ms.sourcegitcommit: 2a0947cffb52eaf885aa2e50c95b3693f7e4c589
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2021
ms.locfileid: "7753055"
---
# <a name="activate-consent-rules"></a>Toestemmingsregels activeren

[Toestemmingscentrum (preview)](../consent-management/overview.md) helpt u toestemmingsgegevens uit verschillende bronnen op elkaar af te stemmen. Gebruik de verenigde entiteit *Toestemming* om standaard toestemmingscontroles toe te passen. Na het importeren van toestemmingsgegevens in Toestemmingscentrum en het configureren van de regels voor de geïmporteerde toestemmingsgegevens, wordt de entiteit *Toestemming* automatisch gesynchroniseerd met doelgroepinzichten.

## <a name="enable-consent-checks"></a>Toestemmingscontroles inschakelen

Als toestemmingsgegevens zijn geïmporteerd in Toestemmingscentrum (preview) en regels zijn ingesteld, kunt u toestemmingscontroles inschakelen in doelgroepinzichten. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Het tabblad Toestemming in de instellingen voor doelgroepinzichten met geactiveerde toestemmingsgegevens.":::

1. Ga in doelgroepinzichten naar **Beheer** > **Systeem**.

1. Selecteer het tabblad **Toestemming (preview)**.

1. Stel in de sectie **Toestemmingscontroles inschakelen** de schakeloptie voor het gebied dat u wilt inschakelen in op **Aan**.

1. Schakel het selectievakje **Het vervangen van standaard toestemmingsregels toestaan** in om de standaard toestemmingscontroles te verwijderen die voor een bepaald segment worden afgedwongen. 

1. Geef in het vervolgkeuzemenu aan waar u overschrijvingen wilt toestaan.     

1. Kies in de sectie **Toestemming aan klantprofielen koppelen** het kenmerk dat wordt gebruikt als id om toestemmingsgegevens te koppelen aan klantgegevens. Het is waarschijnlijk een telefoonnummer of een e-mailadres. 

1. Selecteer **Opslaan** om uw instellingen toe te passen.

## <a name="disable-consent-checks"></a>Toestemmingscontroles uitschakelen

Als u wilt stoppen met het gebruik van toestemmingsgegevens in doelgroepinzichten, moet een beheerder de systeeminstellingen dienovereenkomstig bijwerken.

1. Ga in doelgroepinzichten naar **Beheer** > **Systeem**.

1. Selecteer het tabblad **Toestemming (preview)**.

1. Schakel in de sectie **Toestemmingscontroles inschakelen** de schakeloptie in op **Uit**.
