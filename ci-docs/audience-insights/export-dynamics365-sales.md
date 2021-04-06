---
title: Customer Insights-gegevens exporteren naar Dynamics 365 Sales
description: Leer hoe u de verbinding met Dynamics 365 Sales configureert.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598103"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Connector voor Dynamics 365 Sales (preview)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Gebruik uw klantgegevens om marketinglijsten te maken, werkstromen op te volgen en aanbiedingen te verzenden met Dynamics 365 Sales.

## <a name="prerequisite"></a>Vereiste

1. Contactpersoonrecords moeten aanwezig zijn in Dynamics 365 Sales voordat u een segment van Customer Insights naar Sales kunt exporteren. Lees meer over het opnemen van contactpersonen in [Dynamics 365 Sales met Common Data Services](connect-power-query.md)​.

   > [!NOTE]
   > Als u segmenten van doelgroepinzichten naar Sales exporteert, worden er geen nieuwe contactpersoonrecords gemaakt in de Sales-exemplaren. De contactpersoonrecords van Sales moeten worden opgenomen in doelgroepinzichten en worden gebruikt als een gegevensbron. Ze moeten ook worden opgenomen in de geharmoniseerde klantentiteit om klant-id's toe te wijzen aan contactpersoon-id's voordat segmenten kunnen worden geëxporteerd.

## <a name="configure-the-connector-for-sales"></a>De connector voor Sales configureren

1. Ga in doelgroepinzichten naar **Beheer** > **Exportbestemmingen**.

1. Ga naar **Dynamics 365 Sales** en selecteer **Instellen**.

1. Geef uw exportbestemming een herkenbare naam in het veld **Weergavenaam**.

1. Voer de Sales-URL van uw organisatie in het veld **Serveradres** in.

1. Selecteer in de sectie **Account van serverbeheerder** de optie **Aanmelden** en kies een Dynamics 365 Sales-account.

1. Wijs een klant-id-veld toe aan de Dynamics 365-contactpersoon-id.

1. Selecteer **Volgende**.

1. Kies een of meer segmenten.

1. Selecteer **Opslaan**.

## <a name="export-the-data"></a>De gegevens exporteren

U kunt [gegevens op aanvraag exporteren](export-destinations.md). De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]