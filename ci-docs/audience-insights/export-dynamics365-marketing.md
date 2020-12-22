---
title: Customer Insights-gegevens exporteren naar Dynamics 365 Marketing
description: Leer hoe u de verbinding met Dynamics 365 Marketing configureert.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643767"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Connector voor Dynamics 365 Marketing (preview)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Gebruik de [segmenten](segments.md) om campagnes te genereren en contact op te nemen met specifieke groepen klanten met Dynamics 365 Marketing. Zie [Segmenten van Dynamics 365 Customer Insights gebruiken met Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments) voor meer informatie.

## <a name="prerequisite"></a>Vereisten

Contactpersoonrecords [van Dynamics 365 Marketing opgenomen door Common Data Service](connect-power-query.md).

## <a name="configure-the-connector-for-marketing"></a>De connector voor Marketing configureren

1. Ga in doelgroepinzichten naar **Beheer** > **Exportbestemmingen**.

1. Ga naar **Dynamics 365 Marketing** en selecteer **Instellen**.

1. Geef uw exportbestemming een herkenbare naam in het veld **Weergavenaam**.

1. Voer de Marketing-URL van uw organisatie in het veld **Serveradres** in.

1. Selecteer in de sectie **Account van serverbeheerder** de optie **Aanmelden** en kies een Dynamics 365 Marketing-account.

1. Wijs een klant-id-veld toe aan de Dynamics 365-contactpersoon-id.

1. Selecteer **Volgende**.

1. Kies een of meer segmenten.

1. Selecteer **Opslaan**.

## <a name="export-the-data"></a>De gegevens exporteren

U kunt [gegevens op aanvraag exporteren](export-destinations.md). De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab).
