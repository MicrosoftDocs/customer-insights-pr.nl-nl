---
title: Power BI-connector (preview)
description: De Dynamics 365 Customer Insights-connector leren gebruiken in Power BI.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 656a695b8b3f1ec2b5fbaad69feba7f1f0b73dee
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196664"
---
# <a name="power-bi-connector-preview"></a>Power BI-connector (preview)

Visualisaties maken voor uw gegevens met de Microsoft Power BI Desktop. Genereer aanvullende inzichten en stel rapporten op met uw geharmoniseerde klantgegevens.

## <a name="prerequisites"></a>Vereisten

- Geharmoniseerde klantprofielen.
- De nieuwste versie van [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is op uw computer geïnstalleerd. [Meer informatie over Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>De connector voor Power BI configureren

1. Selecteer in Power BI Desktop de optie **Bestand** > **Gegevens ophalen**.

1. Selecteer **Meer weergeven** en zoek naar **Dynamics 365 Customer Insights**

1. Selecteer **Verbinding maken**.

1. **Meld u aan** met hetzelfde organisatieaccount dat u gebruikt voor Customer Insights en selecteer **Verbinden**.
   > [!NOTE]
   > Het account dat u in deze stap opgeeft, wordt gebruikt om gegevens op te halen uit Customer Insights en hoeft niet hetzelfde account te zijn waarmee u bent ingelogd bij Power BI. Om het account dat wordt gebruikt voor het ophalen van gegevens opnieuw in te stellen, opent u Power BI en gaat u naar **Bestand** > **Opties** > **Instellingen** > **Instellingen voor gegevensbron**. Selecteer in de lijst met gegevensbronnen **Aanmelden bij Dynamics 365 Customer Insights** en selecteer **Machtigingen wissen**.  

1. Bekijk in het dialoogvenster **Navigator** de lijst met alle omgevingen waartoe u toegang hebt. Vouw een omgeving uit en open een van de mappen (entiteiten, metingen, segmenten, verrijkingen). Open bijvoorbeeld de map **Entiteiten** om alle entiteiten te bekijken die u kunt importeren.

   :::image type="content" source="media/power-bi-navigator.png" alt-text="Navigator voor Power BI-connector.":::

1. Schakel de selectievakjes in naast de entiteiten die u wilt opnemen en selecteer **Laden**. U kunt meerdere entiteiten selecteren uit meerdere omgevingen.

   Er wordt een dialoogvenster voor laden weergegeven terwijl uw entiteiten worden geladen. Zodra al uw geselecteerde entiteiten zijn geladen, kunt u de mogelijkheden van Power BI gebruiken om de gegevens te visualiseren.

## <a name="large-data-sets"></a>Grote gegevenssets

De Customer Insights-connector voor Power BI is ontworpen om te werken voor gegevenssets die tot 1 miljoen klantprofielen bevatten. Het importeren van grotere gegevenssets kan werken, maar duurt lang en kan een time-out veroorzaken vanwege Power BI-beperkingen. Zie [Power BI: aanbevelingen voor grote gegevenssets](/power-bi/admin/service-premium-what-is#large-datasets) voor meer informatie.

### <a name="work-with-a-subset-of-data"></a>Werken met een subset van gegevens

Overweeg om met een subset van uw gegevens te werken. U kunt bijvoorbeeld [segmenten](segments.md) maken in plaats van alle klantrecords te exporteren naar Power BI.

## <a name="troubleshooting"></a>Probleemoplossing

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Customer Insights-omgeving wordt niet weergegeven Power BI

Omgevingen met meer dan één [relatie](relationships.md) gedefinieerd tussen twee identieke entiteiten in Customer Insights zijn niet beschikbaar in de Power BI-connector.

Identificeer en verwijder de gedupliceerde relaties.

1. Ga naar **Gegevens** > **Relaties** in de omgeving die u mist in Power BI.
1. Identificeer gedupliceerde relaties:
   - Controleer of er meer dan één relatie is gedefinieerd tussen dezelfde twee entiteiten.
   - Controleer of er een relatie tot stand is gebracht tussen twee entiteiten die beide zijn opgenomen in het harmonisatieproces. Er is een impliciete relatie gedefinieerd tussen alle entiteiten die in het harmonisatieproces zijn opgenomen.
1. Verwijder eventuele dubbele relaties die u hebt gevonden.

Na verwijdering van de gedupliceerde relaties, probeert u de Power BI-connector opnieuw te configureren.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Fouten op datumvelden bij het laden van entiteiten in Power BI Desktop

Bij het laden van entiteiten die velden bevatten met een datumnotatie zoals MM/DD/YYYY, kunt u fouten tegenkomen als gevolg van niet-overeenkomende landinstellingen. Deze discrepantie treedt op wanneer uw Power BI Desktop-bestand is ingesteld op een andere taal dan Engels (Verenigde Staten), omdat datumvelden in Customer Insights worden opgeslagen in Amerikaanse indeling.

Het Power BI Desktop-bestand heeft een enkele landinstelling, die wordt toegepast bij het ophalen van gegevens. Om deze datumfouten op te lossen, [stelt u de landinstelling van het .BPI-bestand](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop) in op Engels (Verenigde Staten).

[!INCLUDE [footer-include](includes/footer-banner.md)]
