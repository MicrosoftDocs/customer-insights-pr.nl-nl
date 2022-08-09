---
title: Metingen maken op basis van sjablonen
description: Definieer metingen met behulp van sjablonen voor veelvoorkomende gebruiksscenario's.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 6dc7fce78d10ba91de4b2abf54c6c6ab1c919d3a
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170767"
---
# <a name="create-measures-from-templates"></a>Metingen maken op basis van sjablonen

Gebruik vooraf gedefinieerde sjablonen van veelgebruikte [metingen](measures.md) om deze te maken. Sjablonen bouwen voort op toegewezen gegevens uit de entiteit *Unified Activity*. Zorg er dus voor dat u [klantactiviteiten](activities.md) hebt geconfigureerd voordat u een meetcriterium maakt op basis van een sjabloon.

Metingsjablonen worden alleen ondersteund in omgevingen voor **individuele klanten**. Zie [Metingbouwer gebruiken](measure-builder.md) om aangepaste metingen te maken of om metingen voor B2B te maken.

Beschikbare sjablonen voor meetcriteria:
- Gemiddelde transactiewaarde (ATV)
- Totale transactiewaarde
- Gemiddelde dagelijkse omzet
- Gemiddelde maandomzet
- Gemiddelde jaaromzet
- Aantal transacties
- Verdiende loyaliteitspunten
- Verzilverde loyaliteitspunten
- Saldo loyaliteitspunten
- Actieve levensduur van klant
- Lidmaatschapsduur van loyaliteitsprogramma
- Tijd sinds laatste aankoop

## <a name="build-a-new-measure-using-a-template"></a>Een nieuwe meting maken met behulp van een sjabloon

1. Ga naar **Metingen**.

1. Selecteer **Nieuw** en selecteer **Een sjabloon kiezen**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Schermopname van het vervolgkeuzemenu bij het maken van een nieuw meetcriterium met markering op sjabloon.":::

1. Zoek de sjabloon die bij uw behoeften past en selecteer **Sjabloon kiezen**.

1. Bekijk de vereiste gegevens en selecteer **Aan de slag** als u over alle gegevens beschikt.

1. Selecteer **Details bewerken** naast de naam van het meetcriterium. Geef een naam op voor het meetcriterium. Voeg optioneel [tags](work-with-tags-columns.md#manage-tags) toe aan het meetcriterium.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialoogvenster Details bewerken.":::

1. Selecteer **Gereed**.

1. Definieer in de sectie **Tijdsperiode instellen** het tijdsbestek van de gegevens. Kies of u wilt dat het nieuwe meetcriterium de hele gegevensset omvat door **Altijd** te selecteren of dat u wilt dat het meetcriterium zich concentreert op een **Specifieke tijdsperiode**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Schermopname die de tijdsperiode laat zien bij het configureren van een meetcriterium vanuit een sjabloon.":::

1. Selecteer in de volgende sectie de optie **Gegevens toevoegen** om de activiteiten te kiezen en de bijbehorende gegevens toe te wijzen vanuit uw entiteit *Unified Activity*.

    1. Stap 1 van 2: kies onder **Type activiteit** het type entiteit dat u wilt gebruiken. Selecteer voor **Activiteiten** de entiteiten die u wilt toewijzen en selecteer vervolgens **Volgende**.
    1. Stap 2 van 2: kies het kenmerk van de entiteit *Unified Activity* voor het onderdeel dat is vereist door de formule. Voor Gemiddelde transactiewaarde is dit bijvoorbeeld het kenmerk dat de transactiewaarde vertegenwoordigt. Kies voor **Tijdstempel van activiteit** het kenmerk van de entiteit *Geharmoniseerde activiteit* waarmee de datum en tijd van de activiteit wordt vertegenwoordigd.
    1. Selecteer **Save**.

    Als de gegevenstoewijzing is geslaagd, ziet u als status **Voltooid** en wordt de naam van de toegewezen activiteiten en kenmerken weergegeven.

1. Selecteer **Uitvoeren** om de resultaten van de meting te berekenen. Selecteer **Concept opslaan** als u de huidige configuratie wilt behouden en de meting later wilt uitvoeren. De pagina **Metingen** wordt weergegeven.

## <a name="next-step"></a>Volgende stap

Gebruik bestaande metingen om [een klantsegment](segments.md) te maken.

[!INCLUDE [footer-include](includes/footer-banner.md)]
