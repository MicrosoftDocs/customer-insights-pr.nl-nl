---
title: Customer Insights-gegevens exporteren naar Dynamics 365 Sales
description: Leer hoe u de verbinding met Dynamics 365 Sales configureert.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643812"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Connector voor Dynamics 365 Sales (preview)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Uw klantgegevens gebruiken om marketinglijsten te maken, werkstromen op te volgen en aanbiedingen te verzenden met Dynamics 365 Sales.

## <a name="prerequisite"></a>Vereisten

Contactpersoonrecords [van Dynamics 365 Sales opgenomen met Common Data Service](connect-power-query.md).

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
