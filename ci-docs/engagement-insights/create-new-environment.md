---
title: Een nieuwe omgeving maken
description: Het doel van een omgeving en hoe een nieuwe te creëren.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/04/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 8ff04a6b2ffbd513a77f7f8a33358f3d8f559c7e
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673636"
---
# <a name="create-a-new-environment"></a>Een nieuwe omgeving maken 

## <a name="overview"></a>Overzicht

Een omgeving is een ruimte waarin u uw werkruimten en verbindingen beheert. Hoe u omgevingen gebruikt, is afhankelijk van uw organisatie en uw gebruiksscenario. U kunt bijvoorbeeld het volgende maken:

- Een enkele omgeving.
- Afzonderlijke omgevingen voor test- en productieomgevingen.
- Afzonderlijke omgevingen voor specifieke teams of afdelingen in uw organisatie die relevante evenementen bevatten voor elke doelgroep.
- Afzonderlijke omgevingen voor verschillende internationale vestigingen van uw bedrijf.
- Verbindingsmogelijkheden met Customer Insights doelgroepinzichten.

## <a name="create-a-new-environment"></a>Een nieuwe omgeving maken

1. Selecteer aan de rechterkant van de hoofdbanner de omgevingskiezer en dan **+Nieuw**.

   :::image type="content" source="media/environment-picker.png" alt-text="Selecteer de omgevingskiezer.":::

1. Typ in het deelvenster **Instellingen** een **Omgevingsnaam**.

1. Kies het **Type** account, afhankelijk van uw type abonnement.

1. Kies de **Regio** en selecteer **Volgende**. 

1. Typ een **werkruimtenaam** waarmee u gegevens kunt verzamelen voor specifieke websites of apps. Zie [Een werkruimte maken](create-workspace.md) voor meer informatie.

1. Kies het **werkruimtetype** (web of mobiel) dat u wilt maken. 

1. Selecteer **Geavanceerde instellingen weergeven** om deze optionele instellingen in of uit te schakelen:

   - Schakel **Onbekend tot bekend** in op "ingeschakeld" om webgebeurtenissen te koppelen aan gebruikers die zich eerder hebben geverifieerd. Zie voor meer informatie [Webgebeurtenissen herkennen van eerder geverifieerde bezoekers](unknown-to-known.md).
   - Schakel **Filteren op botverkeer** in op "ingeschakeld" om webverkeer door bots voor deze werkruimte te verwijderen. 

1. Selecteer **Voltooien** als u klaar bent. 

1. Installeer het codefragment om te beginnen met gegevens ontvangen en selecteer vervolgens **Voltooien** om de werkruimte te creëren. Zie [Overzicht van resources voor ontwikkelaars](developer-resources.md) voor meer informatie.

> [!NOTE]
> U kunt nu leden toevoegen en hun machtigingsniveau toewijzen vanuit de lijst **Rol**. Zie [Rollen en machtigingen](user-roles.md) voor meer informatie. 

Zie [Omgevingen en werkruimten beheren](manage-environments-workspaces.md) voor meer informatie.

## <a name="work-with-your-new-environment"></a>Werken met uw nieuwe omgeving

- [Maak een werkruimte](../engagement-insights/create-workspace.md) en voeg leden toe.
- [Voeg code toe aan uw website](../engagement-insights/instrument-website.md) of [mobiele app](../engagement-insights/developer-resources.md#capture-events-from-mobile-apps).
- Bekijk een [realtime rapport](../engagement-insights/view-reports.md) of creëer [aangepaste rapporten](../engagement-insights/custom-reports.md).
- [Maak verfijnde gebeurtenissen](../engagement-insights/refined-events.md) voor export.
- [Exporteer de gegevens](../engagement-insights/export-events.md) naar Data Lake Storage.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
