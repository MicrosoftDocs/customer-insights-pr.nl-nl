---
title: Segmenten exporteren naar Dynamics 365 Sales (preview)
description: Leer hoe u de verbinding configureert en exporteert naar Dynamics 365 Sales.
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
ms.openlocfilehash: c3497f4625cada49ae33c6987e58994a15536f9b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195975"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Segmenten exporteren naar Dynamics 365 Sales (preview)

Gebruik uw klantgegevens om marketinglijsten te maken, werkstromen op te volgen en aanbiedingen te verzenden met Dynamics 365 Sales.

## <a name="prerequisites"></a>Vereisten

Contactpersoonrecords moeten aanwezig zijn in Dynamics 365 Sales voordat u een segment van Customer Insights naar Sales kunt exporteren. Lees meer over het opnemen van contactpersonen uit [Dynamics 365 Sales met behulp van Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > Als u segmenten exporteert van Customer Insights naar Sales, worden er geen nieuwe contactpersoonrecords gemaakt in de Sales-exemplaren. De contactpersoonrecords van Sales moeten worden opgenomen in Customer Insights en worden gebruikt als een gegevensbron. Ze moeten ook worden opgenomen in de geharmoniseerde klantentiteit om klant-id's toe te wijzen aan contactpersoon-id's voordat segmenten kunnen worden geëxporteerd.

## <a name="known-limitations"></a>Bekende beperkingen

Exports naar Dynamics 365 Sales zijn beperkt tot 100.000 segmenten en dit kan tot 3 uur in beslag nemen.

## <a name="set-up-connection-to-sales"></a>De verbinding instellen met Sales

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Dynamics 365 Sales**.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Standaard zijn dit alleen beheerders. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Voer de Sales-URL van uw organisatie in het veld **Serveradres** in.

1. Selecteer in de sectie **Account van serverbeheerder** de optie **Aanmelden** en kies een Dynamics 365 Sales-account.

1. Wijs een klant-id-veld toe aan de Dynamics 365-contactpersoon-id.

1. Bekijk [Gegevensprivacy en naleving](connections.md#data-privacy-and-compliance) en selecteer **Ik ga akkoord**.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen**.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie Dynamics 365 Sales. Neem contact op met een beheerder als er geen verbinding beschikbaar is.

1. Voer de naam in voor de export.

1. Selecteer het veld Contact-id in de entiteit Klant toe overeenkomend met de contactpersoon-id van Dynamics 365.

1. Selecteer de segmenten die u wilt exporteren.

1. Selecteer **Opslaan**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
