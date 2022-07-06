---
title: Segmenten exporteren naar Dynamics 365 Marketing (preview)
description: Leer hoe u de verbinding configureert en exporteert naar Dynamics 365 Marketing.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: fed4ae1b017cca2b6060c4dda155859cd77e0daf
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054610"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Segmenten exporteren naar Dynamics 365 Marketing (preview)

Gebruik de [segmenten](segments.md) om campagnes te genereren en contact op te nemen met specifieke groepen klanten met Dynamics 365 Marketing. Zie [Segmenten van Dynamics 365 Customer Insights gebruiken met Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments) voor meer informatie.

Als u de nieuwe mogelijkheden van Dynamics 365 Marketing gebruikt voor realtime orkestratie van klantreizen in een Dataverse-organisatie, hoeft u geen standaardexport naar Dynamics 365 Marketing uit te voeren. Contactpersonen en segmenten uit Customer Insights zijn direct beschikbaar in Dynamics 365 Marketing nadat Marketing en Customer Insights zijn gekoppeld. Voordat u bestaande exports verwijdert, raadpleegt u de documentatie over [hoe u klantenreisarrangementen van Customer Insights en Dynamics 365 Marketing verbindt](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite-for-a-connection"></a>Vereiste voor een verbinding

- Contactpersoonsrecords moeten aanwezig zijn in Dynamics 365 Marketing voordat u een segment van Customer Insights naar Marketing kunt exporteren. Lees meer over het opnemen van contactpersonen in [Dynamics 365 Marketing met Microsoft Dataverse](connect-dataverse-managed-lake.md)​.

  > [!NOTE]
  > Als u segmenten exporteert van Customer Insights naar Marketing, worden er geen nieuwe contactpersoonrecords gemaakt in de Marketing-exemplaren. De contactpersoonrecords van Marketing moeten worden opgenomen in Customer Insights en worden gebruikt als een gegevensbron. Ze moeten ook worden opgenomen in de geharmoniseerde klantentiteit om klant-id's toe te wijzen aan contactpersoon-id's voordat segmenten kunnen worden geëxporteerd.

## <a name="set-up-connection-to-marketing"></a>Verbinding met Marketing instellen

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Dynamics 365 Marketing** om de verbinding te configureren.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Voer de Marketing-URL van uw organisatie in het veld **Serveradres** in.

1. Selecteer in de sectie **Account van serverbeheerder** de optie **Aanmelden** en kies een Dynamics 365 Marketing-account.

1. Wijs het veld Contact-id in de entiteit Klant toe aan de contactpersoon-id van Dynamics 365.

1. Selecteer **Opslaan** om de verbinding te voltooien. 

## <a name="configure-an-export"></a>Een export configureren

U kunt deze export configureren als u toegang hebt tot een verbinding van dit type. Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Bestemming toevoegen** om een nieuwe export te maken.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie Dynamics 365 Marketing. Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.

1. Kies een of meer segmenten.

1. Selecteer **Opslaan**.

Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.

De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab). U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand). 

[!INCLUDE [footer-include](includes/footer-banner.md)]
