---
title: Verbinding maken met tabellen in Microsoft Dataverse
description: Gegevens importeren uit een door Microsoft Dataverse beheerd data lake.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: ffeccffd0e353cb5490b537552d585c184ad672f9c806e673bd04743214ad068
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033074"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Verbinding maken met gegevens in een beheerd Microsoft Dataverse data lake

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Dit artikel geeft informatie over hoe Dataverse-gebruikers snel verbinding kunnen maken met hun analytische entiteiten in een door Dataverse beheerde lake. U moet een beheerder zijn in de Dataverse-organisatie om verder te gaan en de lijst met entiteiten te bekijken die beschikbaar zijn in het beheerde lake.

## <a name="important-considerations"></a>Belangrijke aandachtspunten

Gegevens die worden opgeslagen in online services, zoals Azure Data Lake Storage, kunnen worden opgeslagen op een andere locatie dan waar gegevens worden verwerkt of opgeslagen in Dynamics 365 Customer Insights. Door gegevens te importeren die zijn opgeslagen in online services, gaat u ermee akkoord dat gegevens kunnen worden overgedragen naar en opgeslagen met Dynamics 365 Customer Insights.  [Meer informatie in het Microsoft Trust Center.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-dataverse-managed-lake"></a>Verbinding maken met een door Dataverse beheerd lake

1. Ga in doelgroepinzichten naar **Gegevens** > **Gegevensbronnen**.

2. Selecteer **Gegevensbron toevoegen**.

3. Selecteer **Verbinden met door Microsoft Dataverse beheerde lake** en selecteer **Volgende**.

4. Voer een **naam** in voor de gegevensbron en selecteer **Volgende**. Naamrichtlijnen: 
   - Begin met een letter.
   - Gebruik alleen letters en cijfers. Speciale tekens en spaties zijn niet toegestaan.
   - Gebruik minimaal 3 en maximaal 64 tekens.

5. Geef het **Serveradres** voor de Dataverse-organisatie op en selecteer **Aanmelden**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Scherm in stap voor gegevensopname waarin een gebruiker de URL van de Dataverse-omgeving kan invoeren.":::

6. Selecteer de tabellen die u wilt opnemen als entiteiten voor doelgroepinzichten in de lijst met beschikbare tabellen.    

   > [!NOTE]
   > Als er al tabellen zijn geselecteerd, worden deze mogelijk gebruikt door andere Dynamics 365-toepassingen (zoals Dynamics 365 Sales Insights of Customer Service Insights). U kunt de selectie niet wijzigen. Deze tabellen zijn als entiteiten beschikbaar zodra de gegevensbron is gemaakt.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dialoogvenster met een lijst entiteiten in de Dataverse-omgeving.":::

7. Sla uw selectie op om te beginnen met de synchronisatie van de geselecteerde tabellen van Dataverse. U vindt de nieuw toegevoegde verbinding op de pagina **Gegevensbronnen**. Deze wordt in de wachtrij geplaatst voor vernieuwing en toont het aantal entiteiten als 0, totdat alle geselecteerde tabellen gesynchroniseerd zijn.

Slechts één gegevensbron van een omgeving kan tegelijkertijd dezelfde Dataverse beheerde lake gebruiken.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Een gegevensbron van een door Dataverse beheerde lake bewerken

U kunt de entiteitsselectie pas bewerken nadat u de gegevensbron hebt gemaakt. Als er bijvoorbeeld extra entiteiten zijn toegevoegd aan Dataverse en u ze ook wilt importeren.    
Om verbinding te maken met een ander Dataverse-data lake, [moet u een nieuwe gegevensbron maken](#connect-to-a-dataverse-managed-lake).

1. Ga in doelgroepinzichten naar **Gegevens** > **Gegevensbronnen**.

2. Selecteer het weglatingsteken naast de gegevensbron die u wilt bijwerken.

3. Selecteer de optie **Bewerken** in de lijst.

4. Selecteer extra entiteiten in de beschikbare lijst met entiteiten en selecteer vervolgens **Opslaan**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]