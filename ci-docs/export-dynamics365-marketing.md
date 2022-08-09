---
title: Segmenten exporteren naar Dynamics 365 Marketing (preview)
description: Leer hoe u de verbinding configureert en exporteert naar Dynamics 365 Marketing.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196618"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Segmenten exporteren naar Dynamics 365 Marketing (preview)

Gebruik [segmenten](segments.md) om campagnes te genereren en contact op te nemen met specifieke groepen klanten met [Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Als u de nieuwe mogelijkheden van Dynamics 365 Marketing gebruikt voor realtime orkestratie van klantreizen in een Dataverse-organisatie, hoeft u geen standaardexport naar Dynamics 365 Marketing uit te voeren. Contactpersonen en segmenten uit Customer Insights zijn direct beschikbaar in Dynamics 365 Marketing nadat Marketing en Customer Insights zijn gekoppeld. Voordat u bestaande exports verwijdert, raadpleegt u de documentatie over [hoe u klantenreisarrangementen van Customer Insights en Dynamics 365 Marketing verbindt](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite"></a>Vereiste

Contactpersoonsrecords moeten aanwezig zijn in Dynamics 365 Marketing voordat u een segment van Customer Insights naar Marketing kunt exporteren. Lees meer over het opnemen van contactpersonen in [Dynamics 365 Marketing met Microsoft Dataverse](connect-dataverse-managed-lake.md)​.

> [!NOTE]
> Als u segmenten exporteert van Customer Insights naar Marketing, worden er geen nieuwe contactpersoonrecords gemaakt in de Marketing-exemplaren. De contactpersoonrecords van Marketing moeten worden opgenomen in Customer Insights en worden gebruikt als een gegevensbron. Ze moeten ook worden opgenomen in de geharmoniseerde klantentiteit om klant-id's toe te wijzen aan contactpersoon-id's voordat segmenten kunnen worden geëxporteerd.

## <a name="set-up-connection-to-marketing"></a>Verbinding met Marketing instellen

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Dynamics 365 Marketing**.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Standaard zijn dit alleen beheerders. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Voer de Marketing-URL van uw organisatie in het veld **Serveradres** in.

1. Selecteer in de sectie **Account van serverbeheerder** de optie **Aanmelden** en kies een Dynamics 365 Marketing-account.

1. Wijs het veld Contact-id in de entiteit Klant toe aan de contactpersoon-id van Dynamics 365.

1. Bekijk [Gegevensprivacy en naleving](connections.md#data-privacy-and-compliance) en selecteer **Ik ga akkoord**.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen**.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie Dynamics 365 Marketing. Neem contact op met een beheerder als er geen verbinding beschikbaar is.

1. Voer de naam in voor de export.

1. Selecteer het veld Contact-id in de entiteit Klant toe overeenkomend met de contactpersoon-id van Dynamics 365.

1. Selecteer de segmenten die u wilt exporteren.

1. Selecteer **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
