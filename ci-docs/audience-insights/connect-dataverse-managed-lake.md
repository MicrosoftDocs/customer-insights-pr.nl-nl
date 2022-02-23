---
title: Verbinding maken met tabellen in Microsoft Dataverse
description: Gegevens importeren uit een door Microsoft Dataverse beheerd data lake.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: 436345d8932820eb4c517a9e9164b1377c1f62d3
ms.sourcegitcommit: 3807202283dd116a30f900a163d8141db621e5a8
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/28/2022
ms.locfileid: "8046419"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Verbinding maken met gegevens in een beheerd Microsoft Dataverse data lake



Dit artikel geeft informatie over hoe Dataverse-gebruikers snel verbinding kunnen maken met analytische entiteiten in een beheerd lake in Microsoft Dataverse. 

> [!NOTE]
> U moet een beheerder zijn in de Dataverse-organisatie om door te kunnen gaan en de lijst te kunnen bekijken van entiteiten die beschikbaar zijn in het beheerde lake.

## <a name="important-considerations"></a>Belangrijke aandachtspunten

Gegevens die worden opgeslagen in online services, zoals Azure Data Lake Storage, kunnen worden opgeslagen op een andere locatie dan waar gegevens worden verwerkt of opgeslagen in Dynamics 365 Customer Insights. Door gegevens te importeren die zijn opgeslagen in online services, gaat u ermee akkoord dat gegevens kunnen worden overgedragen naar en opgeslagen met Dynamics 365 Customer Insights. [Meer informatie in het Microsoft Trust Centerr](https://www.microsoft.com/trust-center).

## <a name="connect-to-a-dataverse-managed-lake"></a>Verbinding maken met een door Dataverse beheerd lake

1. Ga in doelgroepinzichten naar **Gegevens** > **Gegevensbronnen**.

2. Selecteer **Gegevensbron toevoegen**.

3. Selecteer **Microsoft Dataverse** en selecteer daarna **Volgende**.

4. Voer een **naam** in voor de gegevensbron en selecteer **Volgende**. 

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
