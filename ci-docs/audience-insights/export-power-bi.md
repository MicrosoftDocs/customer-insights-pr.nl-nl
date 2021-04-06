---
title: Power BI-connector
description: De Dynamics 365 Customer Insights-connector leren gebruiken in Power BI.
ms.date: 09/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e43e2f9dbc84ebfbf2154990a752740f973296cb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596033"
---
# <a name="connector-for-power-bi-preview"></a>Connector voor Power BI (preview)

Maak visualisaties voor uw gegevens met de Power BI Desktop. Genereer aanvullende inzichten en stel rapporten op met uw geharmoniseerde klantgegevens.

## <a name="prerequisites"></a>Vereisten

- U hebt geharmoniseerde klantprofielen.
- De nieuwste versie van [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is op uw computer geïnstalleerd. [Meer informatie over Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>De connector voor Power BI configureren

1. Selecteer in Power BI Desktop de optie **Bestand** > **Gegevens ophalen**.

1. Selecteer **Meer weergeven** en zoek naar **Dynamics 365 Customer Insights**

1. Selecteer **Verbinding maken**.

1. **Meld u aan** met hetzelfde organisatieaccount dat u gebruikt voor Customer Insights en selecteer **Verbinden**.
   > [!NOTE]
   > Het account dat u in deze stap opgeeft, wordt gebruikt om gegevens op te halen uit Customer Insights en hoeft niet hetzelfde account te zijn waarmee u bent ingelogd bij Power BI. Om het account dat wordt gebruikt voor het ophalen van gegevens opnieuw in te stellen, opent u Power BI en gaat u naar **Bestand** > **Opties** > **Instellingen** > **Instellingen voor gegevensbron**. Selecteer in de lijst met gegevensbronnen **Aanmelden bij Dynamics 365 Customer Insights** en selecteer **Machtigingen wissen**.  

1. In het dialoogvenster **Navigator**. ziet u de lijst met alle omgevingen waartoe u toegang hebt. Vouw een omgeving uit en open een van de mappen (entiteiten, metingen, segmenten, verrijkingen). Open bijvoorbeeld de map **Entiteiten** om alle entiteiten te bekijken die u kunt importeren.

   ![Navigator voor Power BI-connector](media/power-bi-navigator.png "Navigator voor Power BI-connector")

1. Schakel de selectievakjes in naast de entiteiten die u wilt opnemen en selecteer **Laden**. U kunt meerdere entiteiten selecteren uit meerdere omgevingen.

1. U ziet een dialoogvenster voor laden terwijl uw entiteiten worden geladen. Zodra al uw geselecteerde entiteiten zijn geladen, kunt u de mogelijkheden van Power BI gebruiken om de gegevens te visualiseren.

## <a name="large-data-sets"></a>Grote gegevenssets

De Customer Insights-connector voor Power BI is ontworpen om te werken voor gegevenssets die tot 1 miljoen klantprofielen bevatten. Het importeren van grotere gegevenssets kan werken, maar het duurt lang. Bovendien kan bij het proces een time-out optreden vanwege Power BI-beperkingen. Zie [Power BI: aanbevelingen voor grote gegevenssets](/power-bi/admin/service-premium-what-is#large-datasets) voor meer informatie. 

### <a name="work-with-a-subset-of-data"></a>Werken met een subset van gegevens

Overweeg om met een subset van uw gegevens te werken. U kunt bijvoorbeeld [segmenten](segments.md) maken in plaats van alle klantrecords te exporteren naar Power BI.

## <a name="troubleshooting"></a>Probleemoplossing

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Customer Insights-omgeving wordt niet weergegeven Power BI

Omgevingen waarvoor meer dan één [relatie](relationships.md) is gedefinieerd tussen twee identieke entiteiten in doelgroepinzichten zijn niet beschikbaar zijn in de Power BI-connector.

U kunt de gedupliceerde relaties identificeren en verwijderen.

1. Ga in doelgroepinzichten naar **Gegevens** > **Relaties** in de omgeving die ontbreekt in Power BI​.
2. Identificeer gedupliceerde relaties:
   - Controleer of er meer dan één relatie is gedefinieerd tussen dezelfde twee entiteiten.
   - Controleer of er een relatie tot stand is gebracht tussen twee entiteiten die beide zijn opgenomen in het harmonisatieproces. Er is een impliciete relatie gedefinieerd tussen alle entiteiten die in het harmonisatieproces zijn opgenomen.
3. Verwijder eventuele dubbele relaties die u hebt gevonden.

Na verwijdering van de gedupliceerde relaties, probeert u de Power BI-connector opnieuw te configureren. De omgeving zou nu beschikbaar moeten zijn.

[!INCLUDE[footer-include](../includes/footer-banner.md)]