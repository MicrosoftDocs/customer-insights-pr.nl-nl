---
title: Verrijking van gegevensbronnen
description: Verrijk gegevensbronnen voordat u het proces voor gegevensharmonisatie doorloopt.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: b34b83d7a73dbdf21984f626174524188f0f1dc1
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011467"
---
# <a name="enrichment-for-data-sources-preview"></a>Verrijking voor gegevensbronnen (preview)

Gebruik gegevens uit bronnen zoals Microsoft en andere partners om uw klantgegevens te verrijken voordat gegevens worden geharmoniseerd. Gegevensbronverrijkingen zorgen ervoor dat gegevens vollediger zijn en een hogere kwaliteit hebben waardoor betere resultaten kunnen worden behaald nadat u uw gegevens hebt geharmoniseerd. Het gebruik van een genormaliseerde en gestandaardiseerde notatie voor adressen verhoogt bijvoorbeeld de kwaliteit van de vergelijkingsresultaten. Zie [ondersteunde verrijkingsopties voor gegevensbronnen](#supported-data-source-enrichments) voor een lijst met ondersteunde verrijkingen.

## <a name="enrich-a-data-source"></a>Een gegevensbron verrijken

U moet de inzenders- of beheerdersrechten hebben om verrijkingen te kunnen maken of bewerken. Zie [Machtigingen](permissions.md) voor meer informatie.  

1. Ga naar **Gegevens** > **Harmoniseren**. Selecteer de entiteit die u wilt verrijken en selecteer één kenmerk als primaire sleutel voor de entiteit. Zie [Primaire sleutel selecteren](map-entities.md#select-primary-key-and-semantic-type-for-attributes) voor meer informatie.

1. Ga naar **Gegevens** > **Gegevensbronnen**.

1. Selecteer het verticale weglatingsteken (&vellip;) naast de gegevensbron die u wilt verrijken en selecteer **Verrijken**.

   :::image type="content" source="media/data_sources_enrich.png" alt-text="Gegevensbronnenpagina met Verrijken gemarkeerd":::

   Op het tabblad **Detecteren** worden de [ondersteunde verrijkingsopties voor gegevensbronnen](#supported-data-source-enrichments) weergegeven.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Pagina voor verrijking van gegevensbronnen.":::

1. Selecteer **Mijn gegevens verrijken** om een gegevensbronverrijking te configureren. De naam van de uitvoerentiteit wordt automatisch ingevuld.

## <a name="supported-data-source-enrichments"></a>Ondersteund verrijkingen voor gegevensbronnen

De volgende verrijkingen zijn momenteel beschikbaar voor gegevensbronnen. Bekijk de gedetailleerde stappen voor de verrijking om te leren hoe u deze kunt configureren.

- [Uitgebreide adressen](enrichment-enhanced-addresses.md)
- [Uitgebreide bedrijfsgegevens](enrichment-enhanced-company-data.md)
- [Identiteitsgegevens van LiveRamp](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Bestaande gegevensbronverrijkingen beheren

Ga naar het tabblad **Mijn verrijkingen** om alle geconfigureerde verrijkingen te zien.

Selecteer de verrijking om de beschikbare opties te zien. U kunt ook het verticale weglatingsteken (&vellip;) selecteren op een lijstitem om de opties te zien. Als u verschillende verrijkingen hebt geconfigureerd, kunt u het zoekvak gebruiken om ze snel te vinden.

U kunt een gegevensbronverrijking bekijken, bewerken, uitvoeren of verwijderen. Zie [Bestaande verrijkingen beheren](enrichment-hub.md) voor meer informatie.
