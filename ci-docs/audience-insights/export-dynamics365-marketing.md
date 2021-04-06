---
title: Customer Insights-gegevens exporteren naar Dynamics 365 Marketing
description: Leer hoe u de verbinding met Dynamics 365 Marketing configureert.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597597"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Connector voor Dynamics 365 Marketing (preview)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Gebruik de [segmenten](segments.md) om campagnes te genereren en contact op te nemen met specifieke groepen klanten met Dynamics 365 Marketing. Zie [Segmenten van Dynamics 365 Customer Insights gebruiken met Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments) voor meer informatie.

## <a name="prerequisite"></a>Vereiste

- Contactpersoonsrecords moeten aanwezig zijn in Dynamics 365 Marketing voordat u een segment van Customer Insights naar Marketing kunt exporteren. Lees meer over het opnemen van contactpersonen in [Dynamics 365 Marketing met Common Data Services](connect-power-query.md)​.

  > [!NOTE]
  > Als u segmenten van doelgroepinzichten naar Marketing exporteert, worden er geen nieuwe contactpersoonrecords gemaakt in de Marketing-exemplaren. De contactpersoonrecords van Marketing moeten worden opgenomen in doelgroepinzichten en worden gebruikt als een gegevensbron. Ze moeten ook worden opgenomen in de geharmoniseerde klantentiteit om klant-id's toe te wijzen aan contactpersoon-id's voordat segmenten kunnen worden geëxporteerd.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]