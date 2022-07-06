---
title: Klantprofielen verrijken met locatiegegevens uit Azure Maps (preview)
description: Algemene informatie over de eigen verrijking van Azure Maps.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: dfadc08f67beac3fded1a97e557ee9e1880664e0
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052601"
---
# <a name="enrich-customer-profiles-with-location-data-from-azure-maps-preview"></a>Klantprofielen verrijken met locatiegegevens uit Azure Maps (preview)

Azure Maps biedt locatiegerichte gegevens en services om ervaringen te leveren op basis van georuimtelijke gegevens met ingebouwde locatie-intelligentie. Met de services voor gegevensverrijking van Azure Maps wordt de nauwkeurigheid van locatiegegevens over uw klanten verbeterd. Met de services zijn bijvoorbeeld adresnormalisatie en breedte- en lengtegraadextractie naar Dynamics 365 Customer Insights mogelijk.

## <a name="prerequisites"></a>Vereisten

- Een actief Azure Maps-abonnement. Als u een abonnement wilt nemen, [meldt u zich aan of neemt u een gratis proefversie](https://azure.microsoft.com/services/azure-maps/).

- Een Azure Maps-[verbinding](connections.md) wordt [geconfigureerd](#configure-the-connection-for-azure-maps) door een beheerder.

## <a name="configure-the-connection-for-azure-maps"></a>De verbinding configureren voor Azure Maps

U moet een [Beheerder](permissions.md#admin) in Customer Insights zijn en een actieve Azure Maps API-sleutel hebben.

1. Selecteer **Verbinding toevoegen** bij het configureren van een verrijking of ga naar **Beheerder** > **Verbindingen** en selecteer **Instellen** op de tegel Azure Maps.

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Configuratiepagina voor Azure Maps-verbinding.":::

1. Voer een naam in voor de verbinding en een geldige Azure Maps API-sleutel.

1. Bekijk en geef uw toestemming voor [Gegevensprivacy en naleving](#data-privacy-and-compliance) door **Ik ga akkoord** te selecteren.

1. Selecteer **Verifiëren** om de configuratie te valideren en selecteer **Opslaan**.

### <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights inschakelt om gegevens te verzenden naar Azure Maps, staat u de overdracht van gegevens buiten de nalevingsgrens toe voor Dynamics 365 Customer Insights, inclusief de overdracht van mogelijk gevoelige gegevens zoals persoonsgegevens. Microsoft zal dergelijke gegevens in uw opdracht overdragen, maar het is uw verantwoordelijkheid ervoor te zorgen dat Azure Maps voldoen aan eventuele privacy- of beveiligingsverplichtingen die u hebt. Ga voor meer informatie naar [Privacyverklaring van Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Uw Dynamics 365 Customer Insights-beheerder kan deze verrijking op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.

## <a name="configure-the-enrichment"></a>De verrijking configureren

1. Ga naar **Gegevens** > **Verrijking** en selecteer het tabblad **Detecteren**.

1. Selecteer **Mijn gegevens verrijken** op de tegel **Locatie** van Microsoft Azure Maps.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Azure Maps-tegel.":::

1. Bekijk het overzicht en selecteer **Volgende**.

1. Selecteer de verbinding. Neem contact op met een beheerder als er geen verbinding beschikbaar is.

1. Selecteer **Volgende**.

1. Selecteer de **Klantgegevensset** en kies het profiel of segment dat u wilt verrijken met gegevens van Microsoft. De entiteit *Klant* verrijkt al uw klantprofielen, terwijl een segment alleen klantprofielen in dat segment verrijkt.

1. Definieer welk type velden uit uw geharmoniseerde profielen u wilt gebruiken voor het matchen: het primaire en/of secundaire adres. U kunt voor beide adressen een veldtoewijzing specificeren en de profielen voor beide adressen afzonderlijk verrijken. Bijvoorbeeld voor een woonadres en een zakelijk adres. Selecteer **Volgende**.

1. Wijs uw velden toe aan de locatiegegevens van Azure Maps. De velden **Straat 1** en **Postcode** zijn vereist voor het geselecteerde primaire en/of secundaire adres. Voeg meer velden toe voor een hogere matchnauwkeurigheid.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Azure Maps-kenmerktoewijzing.":::

1. Selecteer **Volgende** om de veldtoewijzing te voltooien.

1. Bekijk **Geavanceerde instellingen**, waar u maximale flexibiliteit hebt om geavanceerde gebruiksscenario's aan te kunnen. De volgende standaardwaarden hoeven echter meestal niet te worden gewijzigd.

   - **Type adressen**: de beste adresovereenkomst wordt geretourneerd, zelfs als deze onvolledig is. Als u alleen volledige adressen wilt krijgen, bijvoorbeeld adressen met het huisnummer, wist u alle selectievakjes behalve **Adressen van punten**.
   - **Taal**: adressen worden geretourneerd in de taal van de regio van het adres. Als u een gestandaardiseerde adrestaal wilt toepassen, selecteert u de taal in het vervolgkeuzemenu. Als u bijvoorbeeld **Nederlands** selecteert, wordt **Kopenhagen, Denemarken** geretourneerd in plaats van **København, Danmark**.
   - **Maximaal aantal resultaten**: aantal resultaten per adres.

1. Selecteer **Volgende**.

1. Geef een **Naam** op voor de verrijking en de **Naam van uitvoerentiteit**.

1. Selecteer **Verrijking opslaan** na het bekijken van uw keuzes.

1. Selecteer **Uitvoeren** om het verrijkingsproces te starten of sluit om terug te keren naar de pagina **Verrijkingen**.

## <a name="view-enrichment-results"></a>Verrijkingsresultaten bekijken

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Het **Aantal klanten dat wordt verrijkt per veld** biedt een gedetailleerde beschrijving van de dekking van elk verrijkt veld.

## <a name="next-steps"></a>Volgende stappen

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
