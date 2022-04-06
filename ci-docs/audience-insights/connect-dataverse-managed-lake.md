---
title: Verbinding maken met tabellen in Microsoft Dataverse
description: Gegevens importeren uit een door Microsoft Dataverse beheerd data lake.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
searchScope:
  - ci-dataverse
  - customerInsights
---

# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Verbinding maken met gegevens in een beheerd Microsoft Dataverse data lake

Dit artikel geeft informatie over hoe Dataverse-gebruikers snel verbinding kunnen maken met analytische entiteiten in een beheerd lake in Microsoft Dataverse. 

> [!NOTE]
> U moet een beheerder zijn in de Dataverse-organisatie om door te kunnen gaan en de lijst te kunnen bekijken van entiteiten die beschikbaar zijn in het beheerde lake.

## <a name="important-considerations"></a>Belangrijke aandachtspunten

1. Gegevens die worden opgeslagen in online services, zoals Azure Data Lake Storage, kunnen worden opgeslagen op een andere locatie dan waar gegevens worden verwerkt of opgeslagen in Dynamics 365 Customer Insights. Door gegevens te importeren die zijn opgeslagen in online services, gaat u ermee akkoord dat gegevens kunnen worden overgedragen naar en opgeslagen met Dynamics 365 Customer Insights. [Meer informatie in het Microsoft Trust Centerr](https://www.microsoft.com/trust-center).
2. Alleen Dataverse-entiteiten waarvoor [wijzigingen bijhouden](/power-platform/admin/enable-change-tracking-control-data-synchronization) is ingeschakeld zijn zichtbaar. Deze entiteiten kunnen worden geëxporteerd naar de door Dataverse beheerde data lake en gebruikt in Customer Insights. Standaard Dataverse-tabellen hebben standaard het bijhouden van wijzigingen ingeschakeld. U moet het bijhouden van wijzigingen inschakelen voor aangepaste tabellen. Als u wilt controleren of een Dataverse-tabel is ingeschakeld voor het bijhouden van wijzigingen, gaat u naar [Power Apps](https://make.powerapps.com) > **Gegevens** > **Tabellen**. Zoek de tabel waarin u bent geïnteresseerd en selecteer deze. Ga naar **Instellingen** > **Geavanceerde opties** en bekijk de instelling **Wijzigingen bijhouden**.

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
