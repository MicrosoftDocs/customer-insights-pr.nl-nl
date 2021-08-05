---
title: Customer Insights-gegevens exporteren naar Dynamics 365 Sales
description: Leer hoe u de verbinding configureert en exporteert naar Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f11ab189117da5bcc1aee843b73962ec6615e82
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692337"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a>Segmenten gebruiken in Dynamics 365 Sales (preview)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Gebruik uw klantgegevens om marketinglijsten te maken, werkstromen op te volgen en aanbiedingen te verzenden met Dynamics 365 Sales.

## <a name="prerequisite-for-connection"></a>Vereiste voor verbinding

1. Contactpersoonrecords moeten aanwezig zijn in Dynamics 365 Sales voordat u een segment van Customer Insights naar Sales kunt exporteren. Lees meer over het opnemen van contactpersonen in [Dynamics 365 Sales met Microsoft Dataverse](connect-power-query.md)​.

   > [!NOTE]
   > Als u segmenten van doelgroepinzichten naar Sales exporteert, worden er geen nieuwe contactpersoonrecords gemaakt in de Sales-exemplaren. De contactpersoonrecords van Sales moeten worden opgenomen in doelgroepinzichten en worden gebruikt als een gegevensbron. Ze moeten ook worden opgenomen in de geharmoniseerde klantentiteit om klant-id's toe te wijzen aan contactpersoon-id's voordat segmenten kunnen worden geëxporteerd.

## <a name="set-up-the-connection-to-sales"></a>De verbinding instellen met Sales

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Dynamics 365 Sales** om de verbinding te configureren.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Voer de Sales-URL van uw organisatie in het veld **Serveradres** in.

1. Selecteer in de sectie **Account van serverbeheerder** de optie **Aanmelden** en kies een Dynamics 365 Sales-account.

1. Wijs een klant-id-veld toe aan de Dynamics 365-contactpersoon-id.

1. Selecteer **Opslaan** om de verbinding te voltooien. 

## <a name="configure-an-export"></a>Een export configureren

U kunt deze export configureren als u toegang hebt tot een verbinding van dit type. Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Bestemming toevoegen** om een nieuwe export te maken.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie Dynamics 365 Sales. Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.

1. Kies een of meer segmenten.

1. Selecteer **Opslaan**

Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.

De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab). U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand). 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
