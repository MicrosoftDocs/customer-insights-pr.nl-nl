---
title: Power BI-connector
description: De Dynamics 365 Customer Insights-connector leren gebruiken in Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405470"
---
# <a name="connector-for-power-bi-preview"></a>Connector voor Power BI (preview)

Maak visualisaties voor uw gegevens met de Power BI Desktop. Genereer aanvullende inzichten en stel rapporten op met uw geharmoniseerde klantgegevens.

## <a name="prerequisites"></a>Vereisten

- U hebt geharmoniseerde klantprofielen.
- De meest recente versie van [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is op uw computer geïnstalleerd. [Meer informatie over Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>De connector voor Power BI configureren

1. Selecteer in Power BI Desktop de optie **Bestand** > **Gegevens ophalen**.

1. Selecteer **Meer weergeven** en zoek naar **Dynamics 365 Customer Insights**

1. Selecteer het resultaat en selecteer **Verbinden**.

1. **Meld u aan** met hetzelfde organisatieaccount dat u gebruikt voor Customer Insights en selecteer **Verbinden**.
   > [!NOTE]
   > Het account dat u in deze stap opgeeft, wordt gebruikt om gegevens op te halen uit Customer Insights en hoeft niet hetzelfde account te zijn waarmee u bent ingelogd bij Power BI. Om het account dat wordt gebruikt voor het ophalen van gegevens opnieuw in te stellen, opent u Power BI en gaat u naar **Bestand** > **Opties** > **Instellingen** > **Instellingen voor gegevensbron**. Selecteer in de lijst met gegevensbronnen **Aanmelden bij Dynamics 365 Customer Insights** en selecteer **Machtigingen wissen**.  

1. In het dialoogvenster **Navigator**. ziet u de lijst met alle omgevingen waartoe u toegang hebt. Vouw een omgeving uit en open een van de mappen (entiteiten, metingen, segmenten, verrijkingen). Open bijvoorbeeld de map **Entiteiten** om alle entiteiten te bekijken die u kunt importeren.

   ![Navigator voor Power BI-connector](media/power-bi-navigator.png "Navigator voor Power BI-connector")

1. Schakel de selectievakjes in naast de entiteiten die u wilt opnemen en selecteer **Laden**. U kunt meerdere entiteiten selecteren uit meerdere omgevingen.

1. U ziet een dialoogvenster voor laden terwijl uw entiteiten worden geladen. Zodra al uw geselecteerde entiteiten zijn geladen, kunt u de mogelijkheden van Power BI gebruiken om de gegevens te visualiseren.

## <a name="large-data-sets"></a>Grote gegevenssets

De Customer Insights-connector voor Power BI is ontworpen om te werken voor gegevenssets die tot 1 miljoen klantprofielen bevatten. Het importeren van grotere gegevenssets kan werken, maar het duurt lang. Bovendien kan bij het proces een time-out optreden vanwege Power BI-beperkingen. Zie [Power BI: aanbevelingen voor grote gegevenssets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets) voor meer informatie. 

### <a name="work-with-a-subset-of-data"></a>Werken met een subset van gegevens

Overweeg om met een subset van uw gegevens te werken. U kunt bijvoorbeeld [segmenten](segments.md) maken in plaats van alle klantrecords te exporteren naar Power BI.
