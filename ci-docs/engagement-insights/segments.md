---
title: Segmenten weergeven en maken
description: Procedure voor het maken, bewerken en verwijderen van segmenten en indicatie waar u ze kunt gebruiken.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: e99c04e6c92d8ca16c2d69957e0f5b7dba0ac757
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225370"
---
# <a name="view-and-create-segments"></a>Segmenten weergeven en maken

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Met segmenten kunt u subsets van bezoekers identificeren op basis van kenmerken of website-interacties. Met segmenten kunt u filters toepassen en die subsets analyseren. De analyse kan helpen bij het onderzoeken van en reageren op trends in uw bedrijf. 

:::image type="content" source="media/segments-page.png" alt-text="Schermopname van de toepassing voor betrokkenheidsinzichten die de lijst met bestaande segmenten in een werkruimte weergeeft.":::

## <a name="view-segments"></a>Segmenten weergeven

1. Ga naar **Gegevens** in het linkernavigatievenster. 

1. Selecteer het tabblad **Segmenten** om een lijst met alle segmenten in de werkruimte te zien. 

## <a name="create-a-segment"></a>Een segment maken

Segmenten bestaan uit regels en voorwaarden die verbonden zijn met logische operators. Voorwaarden passen filters toe op een geselecteerde dimensie. Elk segment kan maximaal vijf dimensies gebruiken.

Het volgende voorbeeld toont een segment met twee voorwaarden in één regel. Het filtert alle websitegebeurtenissen waarbij de browser Chrome is en het besturingssysteem iOS of Android.

:::image type="content" source="media/segment-sample.png" alt-text="Voorbeeldsegmenten met twee voorwaarden in een regel om te filteren op websitegebeurtenissen.":::

In dit gedeelte wordt beschreven hoe u een geheel *leeg segment* maakt.

1. Ga naar **Gegevens** > **Segmenten**.

1. Selecteer **Nieuw segment**.

1. Selecteer in de **Resourcebibliotheek** de (+) naast het kenmerk waarop u wilt filteren. Momenteel kunt u alleen segmenten maken op basis van dimensies.

   :::image type="content" source="media/create-new-segment.png" alt-text="Een nieuw segment maken.":::

1. Kies in de sectie **Regel** een operator en een waarde voor het geselecteerde kenmerk. De volgende bewerkingen worden ondersteund.

   :::image type="content" source="media/choose-operator-segment.png" alt-text="Kies een operator voor uw nieuwe segment.":::

   - **is**: vereist een exacte overeenkomst om waarden op te nemen. Gebruikt **is gelijk aan** voor een enkele waarde of **is een van** om meerdere waarden op te nemen.
   - **is niet**: vereist een exacte overeenkomst om waarden uit te sluiten. Gebruikt **is gelijk aan** voor een enkele waarde of **is een van** om meerdere waarden op te nemen.
   - **begint met**: een tekenreeks waarmee de overeenkomende waarden beginnen.
   - **eindigt op**: een tekenreeks waarmee de overeenkomende waarden eindigen.
   - **bevat**: een tekenreeks in overeenkomende waarden.

1. Om meer voorwaarden aan een groep toe te voegen, kunt u logische operators gebruiken. Bij het gebruik van set-operators wordt rekening gehouden met geprojecteerde kenmerken.
   - **EN**-operator: er moet aan beide voorwaarden worden voldaan als onderdeel van het segmentatieproces. Deze optie is vooral handig wanneer u voorwaarden definieert voor verschillende entiteiten.
   - **OF**-operator: er moet aan een van beide voorwaarden worden voldaan als onderdeel van het segmentatieproces. Deze optie is vooral handig wanneer u meerdere voorwaarden definieert voor dezelfde entiteit.

1. Selecteer **Opslaan** en geef het segment een naam. 

Het segment wordt vermeld op de pagina **Segmenten** en u kunt het toepassen op alle rapporten en trechters in de werkruimte.

## <a name="use-a-segment-in-a-report-or-funnel"></a>Een segment gebruiken in een rapport of trechter

U kunt segmenten toepassen op een rapport of trechter om ze te filteren op basis van de voorwaarden in het segment. U kunt echter geen segmenten toepassen op het realtime gebruiksrapport.

:::image type="content" source="media/segment-reports-filter.png" alt-text="Een rapport met paginaweergaven met een uitgebreide vervolgkeuzelijst om te kiezen welke segmenten moeten worden toegepast.":::

Open het rapport of de trechter om een segment toe te passen. Selecteer **+ Voorwaarde toevoegen** en kies **Filteren op segment**. Kies het segment in de lijst die u wilt toepassen. Het segment wordt toegepast op het rapport. Als een diagram het segment niet ondersteunt, wordt er een fout weergegeven. Zie voor meer informatie [Trechterrapporten maken en beheren](funnel-reports.md).
 
U kunt *tot drie segmenten* toepassen aan een rapport of trechter.

## <a name="edit-a-segment"></a>Een segment bewerken

1. Ga naar **Gegevens** > **Segmenten**.
1. Selecteer het segment in de lijst om het te openen. 
1. Wijzig of voeg naar behoefte waarden toe.
1. Selecteer **Opslaan** om uw wijzigingen toe te passen.

## <a name="change-the-name-of-a-segment"></a>De naam van een segment wijzigen

1. Ga naar **Gegevens** > **Segmenten**.
1. Selecteer in de segmentenlijst de optie **Meer [...]**. 
1. Kies **Naam bewerken** uit de vervolgkeuzelijst.
1. Voer de bueywe naam in en selecteer **Naam wijzigen**.

## <a name="delete-a-segment"></a>Een segment verwijderen

1. Ga naar **Gegevens** > **Segmenten**.
1. Selecteer in de segmentenlijst de optie **Meer [...]**. 
1. Kies **Verwijderen** uit de vervolgkeuzelijst.
1. Selecteer **Verwijderen** om te bevestigen.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
