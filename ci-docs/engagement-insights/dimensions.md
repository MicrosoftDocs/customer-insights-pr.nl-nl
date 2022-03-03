---
title: Dimensies weergeven en maken
description: Procedure voor het maken, bewerken en verwijderen van dimensies.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: d35c72f73d2f3e202ae3c5a5ef26e9db89360084
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226297"
---
# <a name="view-and-create-dimensions"></a>Dimensies weergeven en maken

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Een dimensie is een kenmerk van een gebeurtenis dat gegevens kunnen beschrijven, filteren of groeperen. Als u een marketingactie op uw website uitvoert, kunt u dimensies gebruiken om bezoekers te sorteren op nieuwe en terugkerende gebruikers.  

Betrokkenheidsinzichten omvat kant-en-klare (OOB) dimensies voor gebeurteniseigenschappen. Enkele voorbeelden:

- Browsernaam
- Paginanaam
- Apparaatmodel
- Besturingssysteem
- land/regio

## <a name="view-dimensions"></a>Afmetingen bekijken

Afmetingen zijn gebaseerd op bestaande gebeurteniseigenschappen. Wanneer u de volgcode gebruikt voor betrokkenheidsinzichten, worden automatisch systeemdimensies gemaakt.

1. Ga naar **Gegevens** in het linkernavigatievenster. 
1. Selecteer **Dimensies** om een lijst met alle dimensies in de werkruimte te zien. 
   > [!NOTE]
   > Door het systeem gegenereerde dimensies zijn alleen-lezen. U kunt deze niet bewerken. U kunt alleen aangepaste dimensies maken en bewerken.

## <a name="create-a-dimension"></a>Een dimensie maken

Naast door het systeem gegenereerde dimensies kunnen omgevings- en werkruimtebeheerders aangepaste dimensies maken. Aangepaste dimensies zijn gebaseerd op standaardeigenschappen van basisgebeurtenissen of kunnen [aangepaste eigenschappen van een gebeurtenis](advanced-SDK-implementation.md) gebruiken.

1. Ga naar **Gegevens** > **Dimensies**.
1. Selecteer **Nieuwe dimensie**.

   :::image type="content" source="media/add-dimension.png" alt-text="Een dimensie toevoegen aan een gebeurtenis.":::

1. Selecteer in het deelvenster **Een dimensie maken** een eigenschap waarop u de dimensie wilt baseren. De eigenschappenlijst toont alle eigenschappen in de werkruimte die niet aan een dimensie zijn toegewezen.
   
   :::image type="content" source="media/create-new-dimension.png" alt-text="Een nieuwe dimensie maken.":::
      
3. Voer een naam in het vak **Weergavenaam** in. Optioneel kunt u een **Beschrijving** toevoegen.
4. Selecteer **Maken** om de dimensie op te slaan. Het kan tot een minuut duren voordat u de dimensie kunt gebruiken in een [aangepast rapport](custom-reports.md) of [segment](segments.md). 

## <a name="edit-a-dimension"></a>Een dimensie bewerken

U kunt de naam en beschrijving van een dimensie wijzigen. U kunt alleen door de gebruiker gemaakte dimensies bewerken, maar u kunt geen systeemdimensies bewerken.


1. Ga naar **Gegevens** > **Dimensies**.
1. Selecteer de dimensie die u wilt verwijderen.
1. Werk in het deelvenster **Dimensie bewerken** de dimensie bij.
1. Selecteer **Toepassen** om uw wijzigingen op te slaan.

## <a name="delete-a-dimension"></a>Een dimensie verwijderen

U kunt alleen door de gebruiker gemaakte dimensies verwijderen. Systeemdimensies kunnen niet worden verwijderd.

Het verwijderen van een dimensie is definitief. Rapporten en segmenten die een verwijderde dimensie gebruiken, werken niet meer. 

1. Ga naar **Gegevens** > **Dimensies**.
1. Selecteer de dimensie die u wilt verwijderen.
1. Selecteer in het deelvenster **Dimensie bewerken** de optie **Dimensie verwijderen**.

   :::image type="content" source="media/delete-dimension.png" alt-text="Een dimensie verwijderen uit een gebeurtenis.":::

1. Voer **VERWIJDEREN BEVESTIGEN** (in hoofdletters) in om de verwijdering te bevestigen. 
1. Selecteer **Verwijderen**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
