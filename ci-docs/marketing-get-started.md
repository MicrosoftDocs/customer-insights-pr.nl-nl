---
title: Geharmoniseerde gebruiken in Dynamics 365 Marketing
description: Leer hoe u geharmoniseerde profielen en segmenten kunt integreren met Dynamics 365 Marketing.
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 45c59465771e4ad25ed36d5da1568e67b94cf994
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653716"
---
# <a name="work-with-unified-customer-profiles-in-dynamics-365-marketing"></a>Werken met geharmoniseerde klantprofielen in Dynamics 365 Marketing

[Dynamics 365 Marketing](/dynamics365/marketing/overview) verbetert klantervaringen, zodat u gepersonaliseerde reizen op alle contactpunten kunt organiseren om relaties te versterken en loyaliteit te verdienen. De Dynamics 365 Marketing-app werkt naadloos samen met Dynamics 365 Sales, Dynamics 365 Customer Insights, Microsoft Teams en andere producten, en stelt u in staat om snellere en betere beslissingen te nemen met behulp van de kracht van gegevens en AI.

Door Customer Insights-gegevens te koppelen aan Marketing, kunt u het volgende doen:

- U richten op geharmoniseerde klantprofielen en segmenten. Zo kunt u contact maken met iedere klant, ongeacht de locatie van de gegevens van de klant.
- Dynamische inhoud (zoals gepersonaliseerde tokens) in e-mails, sms- en pushmeldingen baseren op factoren zoals de loyaliteitsstatus, verlengingsdatum van het abonnement, bovenliggend account of een andere factor die u hebt vastgelegd in het geharmoniseerde Customer Insights-profiel.
- Gegevens vanuit Marketing in Customer Insights laden en combineren met klantgegevens uit andere bronnen.
- Customer Insights-gegevens opschonen en verrijken, en tools voor fuzzy overeenkomst toepassen.


## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>Uitgebreide klantprofielen in realtime marketing gebruiken

Met realtime marketing kunt u [aangepaste triggers](/dynamics365/marketing/real-time-marketing-custom-triggers) maken die klantreizen starten op basis van een klantactie. Hoe persoonlijker uw gegevens, hoe relevanter en persoonlijker uw reizen worden. Dit maakt de combinatie van Marketing en Customer Insights zo krachtig. U kunt uit elke bron [gegevens harmoniseren](data-unification.md) en vervolgens gebruiken om zeer gepersonaliseerde klantreizen te stimuleren.

Meer informatie: [Customer Insights-profielen en -segmenten gebruiken in realtime marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>Geharmoniseerde segmenten met uitgaande klantreizen gebruiken

Met Customer Insights kunt u gegevens uit vele bronnen verfijnen en combineren tot geaggregeerde klantsegmenten. Wanneer [Customer Insights wordt verbonden met uitgaande marketing](export-dynamics365-marketing.md), worden deze segmenten automatisch weergegeven *en* vernieuwd in de klantreisontwerper.

Meer informatie: [Segmenten uit Dynamics 365 Customer Insights gebruiken met Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>Gegevens ophalen uit uw eigen Azure Data Lake Storage

U bent niet beperkt tot cloudopslag als u Customer Insights-gegevens wilt gebruiken met Marketing. Als u al een eigen Azure Data Lake Storage hebt ingesteld, kunt u verbinding maken met Customer Insights en de gegevens delen met de Marketing-app (zoals u ook zou doen met een cloudgebaseerde installatie).

Meer informatie: [Het delen van gegevens met Dataverse vanuit uw eigen Azure Data Lake Storage inschakelen](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)