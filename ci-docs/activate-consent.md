---
title: Toestemmingsregels voor segmenten activeren
description: Volg deze stappen om toestemmingsgegevens te koppelen en toestemmingscontroles te activeren in Dynamics 365 Customer Insights. Een beheerder kan toestemmingscontroles ook uitschakelen.
ms.date: 11/12/2021
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: bfa03f4b7b56b300a74ebd04721cd64b893879f1
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646047"
---
# <a name="activate-consent-rules"></a>Toestemmingsregels activeren

Het [Toestemmingscentrum (preview)](consent-management/overview.md) helpt u toestemmingsgegevens uit verschillende bronnen op elkaar af te stemmen. Gebruik de verenigde entiteit *Toestemming* om standaard toestemmingscontroles toe te passen. Na het importeren van toestemmingsgegevens in het Toestemmingscentrum en het configureren van de regels voor de gegevens, wordt de entiteit *Toestemming* automatisch gesynchroniseerd met Dynamics 365 Customer Insights.

## <a name="enable-consent-checks"></a>Toestemmingscontroles inschakelen

Als toestemmingsgegevens zijn geïmporteerd in het Toestemmingscentrum (preview) en de regels zijn ingesteld, kunt u toestemmingscontroles inschakelen. 

:::image type="content" source="consent-management/media/enable-consent-checks.png" alt-text="Het tabblad Toestemming in de instellingen voor Customer Insights met geactiveerde toestemmingsgegevens.":::

1. Ga in Customer Insights naar **Beheer** > **Systeem**.

1. Selecteer het tabblad **Toestemming (preview)**.

1. Stel in de sectie **Toestemmingscontroles inschakelen** de schakeloptie voor alle gebieden die u wilt inschakelen in op **Aan**.

1. Schakel het selectievakje **Het vervangen van standaard toestemmingsregels toestaan** in om de standaard toestemmingscontroles te verwijderen die voor een bepaald segment worden afgedwongen. 

1. Geef in het vervolgkeuzemenu aan waar u overschrijvingen wilt toestaan.     

1. Kies in de sectie **Toestemming aan klantprofielen koppelen** het kenmerk dat wordt gebruikt als id om toestemmingsgegevens te koppelen aan klantgegevens. Het is waarschijnlijk een telefoonnummer of e-mailadres. 

1. Selecteer **Opslaan** om uw instellingen toe te passen.

## <a name="disable-consent-checks"></a>Toestemmingscontroles uitschakelen

Als u wilt stoppen met het gebruik van toestemmingsgegevens in Customer Insights, moet een beheerder de systeeminstellingen dienovereenkomstig bijwerken.

1. Ga in Customer Insights naar **Beheer** > **Systeem**.

1. Selecteer het tabblad **Toestemming (preview)**.

1. Schakel in de sectie **Toestemmingscontroles inschakelen** de schakeloptie in op **Uit**.

> [!TIP]
> Zie [Systeeminstellingen in Toestemmingscentrum (preview)](consent-management/system-settings.md) als u wilt stoppen met het gebruiken van de toestemmingsbeheerfunctie.
