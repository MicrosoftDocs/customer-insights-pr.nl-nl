---
title: Klantprofielen verrijken met locatiegegevens van Azure Maps
description: Algemene informatie over de eigen verrijking van Azure Maps.
ms.date: 08/31/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 63f241c27ec86f357c83a301d6797f9ff87c2241
ms.sourcegitcommit: 2acda3c5adf40bc3f5bbb4b2b4b6c22f84371da7
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466756"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Verrijking van klantprofielen met Azure Maps (preview)

Azure Maps biedt locatiegerichte gegevens en services om ervaringen te bieden op basis van georuimtelijke gegevens met geïntegreerde locatiegegevens. Met de services voor gegevensverrijking van Azure Maps wordt de nauwkeurigheid van locatiegegevens over uw klanten verbeterd. Met de services zijn bijvoorbeeld adresnormalisatie en breedte- en lengtegraadextractie naar Dynamics 365 Customer Insights mogelijk.

## <a name="prerequisites"></a>Vereisten

Als u gegevensverrijking van Azure Maps wilt configureren, moet aan de volgende vereisten worden voldaan:

- U moet een actief Azure Maps-abonnement hebben. Als u een abonnement wilt nemen, kunt u [zich aanmelden of een gratis proefperiode nemen](https://azure.microsoft.com/services/azure-maps/).

- Er is een Azure Maps-[verbinding](connections.md) beschikbaar *of* u hebt [beheerders](permissions.md#administrator)machtigingen en een actieve Azure Maps API-sleutel.

## <a name="configure-the-enrichment"></a>De verrijking configureren

1. Ga naar **Gegevens** > **Verrijking**. 

1. Selecteer op de tegel **Locatie** de optie **Mijn gegevens verrijken**.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Azure Maps-tegel.":::

1. Selecteer een [verbinding](connections.md) in de vervolgkeuzelijst. Neem contact op met een beheerder als er geen Azure Maps-verbinding beschikbaar is. Als u een beheerder bent, kunt u [de verbinding voor Azure Maps configureren](#configure-the-connection-for-azure-maps). 

1. Selecteer **Volgende** om de selectie te bevestigen.

1. Kies de **klantgegevensset** die u wilt verrijken met locatiegegevens van Azure Maps. U kunt de entiteit **Klant** selecteren om al uw geharmoniseerde klantprofielen te verrijken of een segmententiteit selecteren om alleen klantprofielen in dat segment te verrijken.

    :::image type="content" source="media/enrichment-azure-maps-configuration-customer-data-set.png" alt-text="Schermopname bij het kiezen van de klantgegevensset.":::

1. Kies of u velden wilt toewijzen aan het primaire en/of het secundaire adres. U kunt een veldtoewijzing voor beide adressen opgeven en de profielen voor beide adressen afzonderlijk verrijken, bijvoorbeeld voor een woonadres en een zakelijk adres. Selecteer **Volgende**.

1. Definieer welke velden uit uw geharmoniseerde profielen moeten worden gebruikt om te zoeken naar overeenkomende locatiegegevens van Azure Maps. De velden **Straat 1** en **Postcode** zijn vereist voor het geselecteerde primaire of secundaire adres. Voor een hogere nauwkeurigheid van de overeenkomst kunt u meer velden toevoegen.

   :::image type="content" source="media/enrichment-azure-maps-configuration.png" alt-text="Configuratiepagina voor Azure Maps-verrijking.":::

1. Selecteer **Volgende** om de veldtoewijzing te voltooien.

1. Evalueer of u **Geavanceerde instellingen** wilt wijzigen. Deze instellingen zijn bedoeld om maximale flexibiliteit te bieden bij het verwerken van geavanceerde gebruiksscenario's, maar in de meeste gevallen zijn de standaardwaarden voldoende:
   - **Type adressen** : het standaardgedrag is dat de verrijking de beste adresovereenkomst retourneert, zelfs als deze onvolledig is. Als u alleen volledige adressen wilt krijgen, bijvoorbeeld adressen met het huisnummer, wist u alle selectievakjes behalve **Adressen van punten**. 
   - **Taal** : standaard worden adressen geretourneerd in de taal voor de regio waartoe het adres behoort. Als u een gestandaardiseerde adrestaal wilt toepassen, selecteert u de taal in het vervolgkeuzemenu. Als u bijvoorbeeld **Engels** selecteert, wordt **Kopenhagen, Denemarken** geretourneerd in plaats van **København, Danmark**.

1. Geef een naam op voor de verrijking.

1. Controleer uw keuzen en selecteer vervolgens **Verrijking opslaan**.

## <a name="configure-the-connection-for-azure-maps"></a>De verbinding configureren voor Azure Maps

U moet een beheerder zijn in doelgroepinzichten om verbindingen te configureren. Selecteer **Verbinding toevoegen** bij het configureren van een verrijking of ga naar **Beheerder** > **Verbindingen** en selecteer **Instellen** op de tegel Azure Maps.

1. Voer in het vak **Weergavenaam** een naam in voor de verbinding.

1. Geef een geldige Azure Maps API-sleutel op.

1. **Gegevensprivacy en naleving** bekijken en toestemming geven door het selectievakje **Ik ga akkoord** in te schakelen

1. Selecteer **Verifiëren** om de configuratie te valideren.

1. Voltooi de verificatie en selecteer **Opslaan**.

:::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Configuratiepagina voor Azure Maps-verbinding.":::

## <a name="enrichment-results"></a>Verrijkingsresultaten

Selecteer **Uitvoeren** vanaf de opdrachtbalk om het verrijkingsproces te starten. U kunt de verrijking ook automatisch laten uitvoeren als onderdeel van een [geplande vernieuwing](system.md#schedule-tab). De verwerkingstijd is afhankelijk van de grootte van uw klantgegevens en de API-responstijden.

Nadat het verrijkingsproces is voltooid, kunt u de zojuist verrijkte klantprofielgegevens bekijken onder **Mijn verrijkingen**. Ook vindt u daar het tijdstip van de laatste update en het aantal verrijkte profielen.

U kunt een gedetailleerd overzicht van elk verrijkt profiel openen door **Verrijkte gegevens weergeven** te selecteren.

## <a name="next-steps"></a>Volgende stappen

Bouw voort op uw verrijkte klantgegevens. Maak [segmenten](segments.md), [metingen](measures.md) en [exporteer de gegevens](export-destinations.md) om uw klanten gepersonaliseerde ervaringen te bieden.

## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights inschakelt om gegevens te verzenden naar Azure Maps, staat u de overdracht van gegevens buiten de nalevingsgrens toe voor Dynamics 365 Customer Insights, inclusief de overdracht van mogelijk gevoelige gegevens zoals persoonsgegevens. Microsoft draagt dergelijke gegevens in uw opdracht over, maar u bent er zelf verantwoordelijk voor dat Azure Maps voldoet aan alle privacy- of beveiligingsverplichtingen die u hebt. Ga voor meer informatie naar [Privacyverklaring van Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Uw Dynamics 365 Customer Insights-beheerder kan deze verrijking op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
