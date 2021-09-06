---
title: Omgevingen maken en beheren
description: Ontdek hoe u zich aanmeldt voor de service en hoe u omgevingen beheert.
ms.date: 07/22/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: e3f99f8f151aea5f120084382babd5e46e109545a4f63aafc51c3ecb1400cc33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034171"
---
# <a name="manage-environments"></a>Omgevingen beheren

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Omgevingen omschakelen

Selecteer het besturingselement **Omgeving** in de rechterbovenhoek van de pagina om van omgeving te veranderen.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Schermafbeelding van het besturingselement om van omgeving te wisselen.":::

Beheerders kunnen omgevingen [maken](get-started-paid.md) en beheren.

## <a name="edit-an-existing-environment"></a>Een bestaande omgeving bewerken

U kunt enkele details van bestaande omgevingen bewerken.

1.  Selecteer de picker **Omgeving** in de koptekst van de app.

2.  Selecteer het pictogram **Bewerken**.

3. In het vak **Omgeving bewerken** kunt u de **Weergavenaam** van de omgeving bijwerken, maar u kunt niet de **Regio** of het **Type** bijwerken.

4. Als een omgeving is geconfigureerd om gegevens op te slaan in Azure Data Lake Storage, kunt u de **accountsleutel** bijwerken. U kunt de **accountnaam** of naam van de **container** echter niet wijzigen.

5. Optioneel kunt u bijwerken vanaf een accountsleutelverbinding naar een resource- of een abonnementsverbinding. Na het upgraden kunt u na de update geen accountsleutel meer gebruiken. Zie [Doelgroepinzichten verbinden met een Azure Data Lake Storage Gen2-account met een Azure Service Principal](connect-service-principal.md) voor meer informatie. U kunt geen informatie over **Container** wijzigen bij het bijwerken van de verbinding.

6. Optioneel kunt u een URL voor een Microsoft Dataverse-omgeving opgeven onder **Het delen van gegevens met Microsoft Dataverse configureren en extra mogelijkheden inschakelen**. Deze mogelijkheden omvatten het delen van gegevens met toepassingen en oplossingen op basis van Microsoft Dataverse, gegevensopname uit on-premises-gegevensbronnen of het gebruik van [voorspellingen](predictions.md). Selecteer **Gegevens delen inschakelen** om Customer Insights-uitvoergegevens te delen met een Microsoft Dataverse beheerde data lake.

   > [!NOTE]
   > - Gegevens delen met Microsoft Dataverse beheerde data lake wordt momenteel niet ondersteund wanneer u alle gegevens in uw eigen Azure Data Lake Storage opslaat.
   > - [Voorspelling van ontbrekende waarden in een entiteit](predictions.md) en PowerBI Embedded-rapporten in doelgroepinzichten (indien ingeschakeld in uw omgeving) worden momenteel niet ondersteund wanneer u gegevens delen met een door Microsoft Dataverse beheerd data lake inschakelt.

   Nadat u het delen van gegevens met Microsoft Dataverse hebt ingeschakeld, wordt een volledige vernieuwing van uw gegevensbronnen en andere processen gestart. Als er momenteel processen actief zijn, ziet u de optie om het delen van gegevens met Microsoft Dataverse in te schakelen niet. Wacht tot die processen zijn voltooid of annuleer ze om het delen van gegevens in te schakelen. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Configuratieopties om het delen van gegevens met Microsoft Dataverse mogelijk te maken.":::
   
   Wanneer u processen uitvoert, zoals het opnemen van gegevens of het maken van segmenten, worden overeenkomstige mappen gemaakt in het opslagaccount dat u hierboven hebt opgegeven. Er worden gegevensbestanden en bestanden model.json gemaakt en toegevoegd aan de respectievelijke submappen, afhankelijk van het proces dat u uitvoert.

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
- Gegevensbronnen uit map Common Data Model en door Dataverse beheerde Data Lake. U moet die gegevensbronnen handmatig maken met dezelfde naam als in de bronomgeving.

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
