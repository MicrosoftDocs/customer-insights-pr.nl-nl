---
title: Omgevingen maken en beheren
description: Ontdek hoe u zich aanmeldt voor de service en hoe u omgevingen beheert.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 309b2a900e50727ffa655fc6b5fe728ea55ba5bf
ms.sourcegitcommit: 626d485dae1e001e63e4d4bf78f6770766822ba0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/06/2021
ms.locfileid: "7892378"
---
# <a name="manage-environments"></a>Omgevingen beheren

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Omgevingen omschakelen

Selecteer het besturingselement **Omgeving** in de rechterbovenhoek van de pagina om van omgeving te veranderen.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Schermafbeelding van het besturingselement om van omgeving te wisselen.":::

Beheerders kunnen omgevingen [maken](create-environment.md) en beheren.

## <a name="edit-an-existing-environment"></a>Een bestaande omgeving bewerken

U kunt enkele details van bestaande omgevingen bewerken.

1.  Selecteer de picker **Omgeving** in de koptekst van de app.

2.  Selecteer het pictogram **Bewerken**.

3. In het vak **Omgeving bewerken** kunt u de omgevingsinstellingen bijwerken.

Zie voor meer informatie over omgevingsinstellingen [Een nieuwe omgeving maken](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Verbinding maken met Microsoft Dataverse
   
In de stap **Microsoft Dataverse** kunt u Customer Insights verbinden met uw Dataverse-omgeving.

Als u [kant-en-klare voorspellingsmodellen](predictions-overview.md#out-of-box-models) wilt gebruiken, configureert u delen van gegevens met Dataverse. Of u kunt gegevensopname van on-premises-gegevensbronnen inschakelen door de Microsoft Dataverse omgevings-URL op te geven die uw organisatie beheert. Selecteer **Gegevens delen inschakelen** om Customer Insights-uitvoergegevens te delen met een door Dataverse beheerd data lake.

> [!IMPORTANT]
> Customer Insights en Dataverse moeten zich in dezelfde regio bevinden om het delen van gegevens mogelijk te maken.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Configuratieopties om het delen van gegevens met Microsoft Dataverse mogelijk te maken.":::

> [!NOTE]
> Customer Insights biedt geen ondersteuning voor de volgende scenario's voor het delen van gegevens:
> - Als u alle gegevens opslaat naar uw eigen Azure Data Lake Storage, kunt u het delen van gegevens met een door Dataverse beheerd data lake niet inschakelen.
> - Als u het delen van gegevens met een door Dataverse beheerd data lake inschakelt, is het niet mogelijk om [voorspelde of ontbrekende waarden te maken in een entiteit](predictions.md).

## <a name="copy-the-environment-configuration"></a>De configuratie van de omgeving kopiëren

Wanneer u een nieuwe omgeving maakt, kunt u ervoor kiezen de configuratie uit een bestaande omgeving te kopiëren. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Schermafbeelding van de opties in de omgevingsinstellingen.":::

U ziet een lijst met alle beschikbare omgevingen in uw organisatie waaruit u gegevens kunt kopiëren.

De volgende configuratie-instellingen worden gekopieerd:

- Opgenomen/geïmporteerde gegevensbronnen
- Configuratie van gegevensharmonisatie (Toewijzing, Overeenkomst, Samenvoeging)
- Segmenten
- Metingen
- Relaties
- Activiteiten
- Index voor zoeken en filteren
- Exportbestemmingen
- Geplande vernieuwing
- Verrijkingen
- Modelbeheer
- Roltoewijzingen

De volgende gegevens worden *niet* gekopieerd:

- Klantprofielen.
- Referenties voor gegevensbron. U moet de referenties voor elke gegevensbron opgeven en de gegevensbronnen handmatig vernieuwen.

- Gegevensbronnen uit de Common Data Model-map en het door Dataverse beheerde data lake. U moet die gegevensbronnen handmatig maken met dezelfde naam als in de bronomgeving.

Wanneer u een omgeving kopieert, ziet u een bevestigingsbericht dat de nieuwe omgeving is gemaakt. Selecteer **Ga naar gegevensbronnen** om de lijst met gegevensbronnen te zien.

Alle gegevensbronnen hebben de status **Referenties vereist**. Bewerk de gegevensbronnen en voer de referenties in om ze te vernieuwen.

:::image type="content" source="media/data-sources-copied.png" alt-text="Lijst met gegevensbronnen die zijn gekopieerd en waarvoor verificatie is vereist.":::

Ga na het vernieuwen van de gegevensbronnen naar **Gegevens** > **Harmoniseren**. Hier vindt u instellingen uit de bronomgeving. Bewerk deze indien nodig of selecteer **Uitvoeren** om het proces voor gegevensharmonisering te starten en de geharmoniseerde klantentiteit te maken.

Ga wanneer de gegevensharmonisering is voltooid naar **Meetcriteria** en **Segmenten** om deze eveneens te vernieuwen.

## <a name="reset-an-existing-environment"></a>Een bestaande omgeving opnieuw instellen

Als beheerder kunt u een omgeving terugzetten naar een lege staat als u alle configuraties wilt verwijderen en de opgenomen gegevens wilt verwijderen.

1.  Selecteer de picker **Omgeving** in de koptekst van de app. 

2.  Selecteer de omgeving die u opnieuw wilt instellen en selecteer het beletselteken (**...**). 

3. Kies de optie **Opnieuw instellen**. 

4.  Om het verwijderen te bevestigen, voert u de omgevingsnaam in en selecteert u **Opnieuw instellen**.

## <a name="delete-an-existing-environment"></a>Een bestaande omgeving verwijderen

Als beheerder kunt u een door u beheerde omgeving verwijderen.

1.  Selecteer de picker **Omgeving** in de koptekst van de app.

2.  Selecteer de omgeving die u opnieuw wilt instellen en selecteer het beletselteken (**...**). 

3. Kies de optie **Verwijderen**. 

4.  Om de verwijdering te bevestigen, voert u de omgevingsnaam in en selecteert u **Verwijderen**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
