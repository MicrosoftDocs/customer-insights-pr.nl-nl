---
title: Toestemmingsregels voor segmenten activeren
description: Volg deze stappen om toestemmingsgegevens te koppelen en toestemmingscontroles te activeren in Dynamics 365 Customer Insights. Een beheerder kan toestemmingscontroles ook uitschakelen.
ms.date: 04/27/2022
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f82e3a4031fee8bcaa88575cbd68b37385a7fffb
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755164"
---
# <a name="activate-consent-rules"></a>Toestemmingsregels activeren

Het [Toestemmingscentrum (preview)](consent-management/overview.md) helpt u toestemmingsgegevens uit verschillende bronnen op elkaar af te stemmen. Gebruik de verenigde entiteit *Toestemming* om standaard toestemmingscontroles toe te passen. Na het importeren van toestemmingsgegevens en het configureren van de toewijzingsregels, wordt de entiteit *Toestemming* automatisch gesynchroniseerd met Dynamics 365 Customer Insights.

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
