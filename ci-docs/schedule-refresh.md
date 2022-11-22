---
title: Systeemvernieuwing plannen
description: Plan de tijd waarop het systeem moet worden vernieuwd
ms.date: 09/27/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 4aac02b570357d2086f7a9d7340b0e4837157a0b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610322"
---
# <a name="schedule-system-refresh"></a>Systeemvernieuwing plannen

Plan automatische vernieuwingen van al uw [opgenomen gegevensbronnen](data-sources.md). Automatische vernieuwingen zorgen ervoor dat updates van uw gegevensbronnen worden weerspiegeld in uw geharmoniseerde klantprofielen.

> [!NOTE]
> Power Query-gegevensbronnen die door u worden beheerd worden volgens hun eigen schema vernieuwd. Om het vernieuwen van deze Power Query-gegevensbronnen te plannen, configureert u vernieuwingsinstellingen voor die specifieke gegevensbron vanuit de pagina **Gegevensbronnen**. Stem de timing af op het upstream-vernieuwingsschema voor gegevens, zodat vernieuwingen niet allemaal tegelijk plaatsvinden.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Instellingen voor vernieuwen van gegevensstromen.":::

## <a name="set-system-refresh-schedule"></a>Planning voor systeemvernieuwing instellen

1. Ga naar **Beheer** > **Systeem** en selecteer het tabblad **Planning**.

   :::image type="content" source="media/schedule_refresh.png" alt-text="Tabblad Vernieuwing plannen op de pagina Systeem.":::

1. De standaardstatus voor de geplande vernieuwing is **Uit**. Als u geplande vernieuwingen wilt inschakelen, stelt u de schakelaar boven aan het scherm in op **Aan**.

1. Kies tussen **Wekelijks** (standaard) en **Dagelijks** vernieuwen. Als u wekelijkse vernieuwingen wilt plannen, selecteert u een of meer dagen waarop u de vernieuwing wilt uitvoeren.

1. Stel uw **tijdzone** in en gebruik daarna de vervolgkeuzelijst **Tijd** om uw vernieuwingstijd in te stellen. Als u meerdere vernieuwingen op één dag wilt plannen, selecteert u **Een andere tijd toevoegen**. U kunt maximaal vier vernieuwingen toevoegen.

1. Selecteer **Opslaan** om uw wijzigingen toe te passen.

[!INCLUDE [footer-include](includes/footer-banner.md)]