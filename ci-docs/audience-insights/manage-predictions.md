---
title: Gedeelde taken voor voorspellingsscenario's
description: Leer hoe u voorspellingen beheert, problemen oplost en verfijnt.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8ff8d70ffb8489def072e5d8a6e43d062594141a
ms.sourcegitcommit: 696ad9ab6e10046c00f1ac86a7e8fc37386e6fe7
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/08/2022
ms.locfileid: "8555307"
---
# <a name="manage-predictions"></a>Voorspellingen beheren

In dit artikel worden enkele taken besproken die de meeste voorspellingsscenario's gemeenschappelijk hebben.

## <a name="troubleshoot-a-failed-prediction"></a>Probleem van een mislukte voorspelling oplossen

1. Ga naar **Intelligence** > **Voorspellingen** en selecteer het tabblad **Mijn voorspellingen**.

1. Selecteer het verticale beletselteken naast de voorspelling waarvoor u foutenlogbestanden wilt bekijken.

1. Selecteer **Logbestanden**.

1. Bekijk alle fouten. Er zijn verschillende typen fouten die kunnen optreden en deze beschrijven welke toestand de fout heeft veroorzaakt. Een fout waarbij er niet genoeg gegevens beschikbaar zijn om een nauwkeurige voorspelling te maken wordt bijvoorbeeld doorgaans hersteld door extra gegevens in Customer Insights te laden.

## <a name="input-data-usability-report"></a>Bruikbaarheidsrapport voor gegevensinvoer

Het bruikbaarheidsrapport voor invoergegevens biedt een geconsolideerd overzicht van de fouten en waarschuwingen die uw kant-en-klare voorspellingen mogelijk genereren. Het geeft ook aanbevelingen om de prestaties van het model te verbeteren.

Het rapport is beschikbaar nadat een model zijn trainingsproces heeft voltooid. Het wordt voor elk model afzonderlijk gemaakt, ongeacht of dit met succes is voltooid of niet.

### <a name="view-the-input-data-usability-report"></a>Het bruikbaarheidsrapport voor gegevensinvoer bekijken

Nadat een kant-en-klaar model de trainingsstap heeft voltooid, bekijkt u het rapport:
- Selecteer de weglatingstekens naast de modelnaam en kies **Bruikbaarheidsrapport voor gegevensinvoer**.
- Selecteer de status van een model en selecteer **Bruikbaarheidsrapport voor gegevensinvoer bekijken** in het zijpaneel.
- Selecteer een van de modellen in de lijst en selecteer **Bruikbaarheidsrapport voor gegevensinvoer** op de opdrachtbalk.
- Open de pagina met modelresultaten en selecteer **Bruikbaarheidsrapport voor gegevensinvoer** op de opdrachtbalk.

### <a name="information-in-the-input-data-usability-report"></a>Informatie in het bruikbaarheidsrapport voor gegevensinvoer

De volgende kolommen in het rapport bevatten nuttige informatie om de gegevens voor het model te verbeteren.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Voorbeeld van een bruikbaarheidsrapport voor invoergegevens met een tabel met fouten, waarschuwingen en aanbevelingen.":::

- **Naam**: beschrijvende naam van de fout, waarschuwing of aanbeveling.
- **Stap**: modelfase, trainen of scoren, waarnaar de informatie verwijst.
- **Status**: ernst van de informatie (fout, waarschuwing, aanbeveling).
- **Kolomnaam**: kolom in een entiteit die moet worden gewijzigd om de modelprestaties te verbeteren.
- **Entiteitsnaam**: naam van de entiteit die moet worden gewijzigd om de modelprestaties te verbeteren.
- **Details**: details van de fout, waarschuwing of aanbeveling.

## <a name="refresh-a-prediction"></a>Een voorspelling vernieuwen

Voorspellingen worden automatisch vernieuwd volgens hetzelfde [schema van gegevensvernieuwingen](system.md#schedule-tab) zoals geconfigureerd in de instellingen. U kunt ze ook handmatig vernieuwen.

1. Ga naar **Intelligence** > **Voorspellingen** en selecteer het tabblad **Mijn voorspellingen**.

1. Selecteer de verticale puntjes naast de voorspelling die u wilt vernieuwen.

1. Selecteer **Vernieuwen**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="delete-a-prediction"></a>Een voorspelling verwijderen

Als u een voorspelling verwijdert, wordt ook de uitvoerentiteit ervan verwijderd.

1. Ga naar **Intelligence** > **Voorspellingen** en selecteer het tabblad **Mijn voorspellingen**.

1. Selecteer de verticale puntjes naast de voorspelling die u wilt verwijderen.

1. Selecteer **Verwijderen**.
