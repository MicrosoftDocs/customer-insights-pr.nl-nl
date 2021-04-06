---
title: Verbinding maken met entiteiten in de Common Data Service beheerde lake
description: Gegevens importeren uit een door Common Data Service beheerd data lake.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: b1cfab40c1edb32f4a7f359e1195cfb1e879a0d5
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596953"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Verbinding maken met gegevens in een beheerd Common Data Service data lake

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Dit artikel bevat informatie over hoe bestaande Dynamics 365-klanten snel verbinding kunnen maken met hun analytische entiteiten in het door Common Data Service beheerde lake. U moet een beheerder zijn in de Common Data Service-organisatie om verder te gaan en de lijst met entiteiten te bekijken die beschikbaar zijn in het beheerde lake.

## <a name="important-considerations"></a>Belangrijke aandachtspunten

Gegevens die worden opgeslagen in online services, zoals Azure Data Lake Storage, kunnen worden opgeslagen op een andere locatie dan waar gegevens worden verwerkt of opgeslagen in Dynamics 365 Customer Insights. Door gegevens te importeren die zijn opgeslagen in online services, gaat u ermee akkoord dat gegevens kunnen worden overgedragen naar en opgeslagen met Dynamics 365 Customer Insights.  [Meer informatie in het Microsoft Trust Center.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>Verbinding maken met een door Common Data Service beheerd lake

1. Ga in doelgroepinzichten naar **Gegevens** > **Gegevensbronnen**.

2. Selecteer **Gegevensbron toevoegen**.

3. Selecteer **Verbinden met Common Data Service** en selecteer **Volgende**.

4. Voer een **naam** in voor de gegevensbron en selecteer **Volgende**. Naamrichtlijnen: 
   - Begin met een letter.
   - Gebruik alleen letters en cijfers. Speciale tekens en spaties zijn niet toegestaan.
   - Gebruik minimaal 3 en maximaal 64 tekens.

5. Geef het **Serveradres** op voor uw Common Data Service-organisatie en selecteer **Aanmelden**.

   > [!div class="mx-imgBorder"]
   > ![Dialoogvenster om Common Data Service-serveradres in te voeren](media/enter-CDS-org-details.png)

6. Selecteer de entiteiten die u wilt opnemen uit de beschikbare lijst.    

   > [!NOTE]
   > Als sommige entiteiten al zijn geselecteerd, worden ze mogelijk gebruikt door andere Dynamics 365-toepassingen (zoals Dynamics 365 Sales Insights of Customer Service Insights). U kunt de selectie niet wijzigen. Deze entiteiten zijn beschikbaar zodra de gegevensbron is gemaakt.

   > [!div class="mx-imgBorder"]
   > ![Dialoogvenster met een lijst van entiteiten in de Common Data Service-organisatie](media/select-analytical-entities.png)

7. Sla uw selectie op om te beginnen met het synchroniseren van de geselecteerde entiteiten met het door Common Data Service beheerde lake. U vindt de nieuw toegevoegde verbinding op de pagina **Gegevensbronnen**. Deze wordt in de wachtrij geplaatst voor vernieuwing en het aantal entiteiten wordt weergegeven als 0 totdat alle entiteiten zijn gesynchroniseerd.

Slechts één gegevensbron van een omgeving kan tegelijkertijd dezelfde Common Data Service beheerde lake gebruiken.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>Een gegevensbron van een door Common Data Service beheerde lake bewerken

U kunt de entiteitsselectie pas bewerken nadat u de gegevensbron hebt gemaakt. Als er bijvoorbeeld extra entiteiten zijn toegevoegd aan Common Data Service en u ze ook wilt importeren.    
Als u verbinding wilt maken met een andere Common Data Service, [maakt u een nieuwe gegevensbron](#connect-to-a-common-data-service-managed-lake).

1. Ga in doelgroepinzichten naar **Gegevens** > **Gegevensbronnen**.

2. Selecteer het weglatingsteken naast de gegevensbron die u wilt bijwerken.

3. Selecteer de optie **Bewerken** in de lijst.

4. Selecteer extra entiteiten in de beschikbare lijst met entiteiten en selecteer vervolgens **Opslaan**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]