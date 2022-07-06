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
ms.openlocfilehash: f6bcdfc45a49c36f22d6ebc6e919f43b27f899d8
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051677"
---
# <a name="create-measures-from-templates"></a>Metingen maken op basis van sjablonen

U kunt vooraf gedefinieerde sjablonen van veelgebruikte [metingen](measures.md) gebruiken om deze te maken. Gedetailleerde beschrijvingen van de sjablonen en een begeleide ervaring helpen u bij het efficiënt maken van meetcriteria. Sjablonen bouwen voort op toegewezen gegevens uit de entiteit *Unified Activity*. Zorg er dus voor dat u [klantactiviteiten](activities.md) hebt geconfigureerd voordat u een meetcriterium maakt op basis van een sjabloon.

Zie [Gebruik de metingenbouwer om helemaal vanaf de grond metingen te maken](measure-builder.md) om aangepaste metingen te maken.

# <a name="individual-consumers-b-to-c"></a>[Individuele consumenten (B-to-C)](#tab/b2c)

Beschikbare sjablonen voor meetcriteria: 
- Gemiddelde transactiewaarde (ATV)
- Totale transactiewaarde
- Gemiddelde dagelijkse omzet
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

1. Definieer in de sectie **Tijdsperiode instellen** het tijdsbestek van de te gebruiken gegevens. Kies of u wilt dat het nieuwe meetcriterium de hele gegevensset omvat door **Altijd** te selecteren of dat u wilt dat het meetcriterium zich concentreert op een **Specifieke tijdsperiode**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Schermopname die de tijdsperiode laat zien bij het configureren van een meetcriterium vanuit een sjabloon.":::

1. Selecteer in de volgende sectie de optie **Gegevens toevoegen** om de activiteiten te kiezen en de bijbehorende gegevens toe te wijzen vanuit uw entiteit *Unified Activity*.

    1. Stap 1 van 2: kies onder **Type activiteit** het type entiteit dat u wilt gebruiken. Selecteer voor **Activiteiten** de entiteiten die u wilt toewijzen.
    1. Stap 2 van 2: kies het kenmerk van de entiteit *Unified Activity* voor het onderdeel dat is vereist door de formule. Voor Gemiddelde transactiewaarde is dit bijvoorbeeld het kenmerk dat de transactiewaarde vertegenwoordigt. Kies voor **Tijdstempel van activiteit** het kenmerk van de entiteit Unified Activity dat de datum en tijd van de activiteit vertegenwoordigt.
   
1. Zodra de gegevenstoewijzing is geslaagd, ziet u de status als **Voltooid** en de naam van de toegewezen activiteiten en kenmerken.

1. U kunt nu **Uitvoeren** selecteren om de resultaten van het meetcriterium te berekenen. Selecteer **Concept opslaan** om het later te verfijnen.

# <a name="business-accounts-b-to-b"></a>[Zakelijke accounts (B-to-B)](#tab/b2b)

Deze functie is alleen beschikbaar voor metingen die zijn gemaakt in omgevingen met individuele klanten als primaire doelgroep.

---
