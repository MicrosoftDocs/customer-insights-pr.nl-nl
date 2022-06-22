---
title: Verrijking van bedrijfsprofielen met Dun & Bradstreet
description: Algemene informatie over de verrijking door derden met Dun & Bradstreet.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b1038970b6aee3bbdd7f79cc457f79aaf1c38222
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953885"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Verrijking van bedrijfsprofielen met Dun & Bradstreet (preview)

Dun & Bradstreet biedt commerciële gegevens, analyses en inzichten voor bedrijven. Het stelt klanten met geharmoniseerde klantprofielen voor bedrijven in staat hun gegevens te verrijken. Verrijkingen omvatten kenmerken, waaronder DUNS-nummer, bedrijfsgrootte, locatie, branche en meer.

## <a name="prerequisites"></a>Vereisten

- Een actieve [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights)-licentie.
- [Geharmoniseerde klantprofielen](customer-profiles.md) voor bedrijven.
- Een Dun & Bradstreet-[project](#set-up-your-dun--bradstreet-project) wordt ingesteld.
- Een Dun & Bradstreet-[verbinding](connections.md) wordt [geconfigureerd](#configure-a-connection-for-dun--bradstreet) door een beheerder.

## <a name="set-up-your-dun--bradstreet-project"></a>Uw Dun & Bradstreet-project instellen

Als gelicentieerde gebruiker van Dun & Bradstreet kunt u een project instellen in [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. Meld u aan bij [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights) Om referenties op te halen [herstelt u uw wachtwoord](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Download [ons csv-sjabloonbestand](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) dat zal worden gebruikt om de Customer Insights-velden toe te wijzen aan de overeenkomstige Dun & Bradstreet-velden.

1. Upload het bestand in de stap **Gegevens uploaden** van de Dun & Bradstreet-projectcreatie-ervaring.

1. Selecteer de horizontale stippen onder de relevante **bron** in het nieuw gecreëerde Dun & Bradstreet-project om de beschikbare opties te zien.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Schermopname van stippen in een Dun & Bradstreet-project.":::

1. Kies **S3-details ophalen**. Bewaar deze informatie op een veilige plaats. U hebt dit nodig om [de verbinding voor de verrijking in te stellen](#configure-a-connection-for-dun--bradstreet) in Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Schermopname van selectie van s3-informatie in een Dun & Bradstreet-project.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Een verbinding configureren voor Dun & Bradstreet

U moet een [beheerder](permissions.md#admin) in Customer Insights zijn en de referenties voor Dun & Bradstreet Connect hebben.

1. Selecteer **Verbinding toevoegen** bij het configureren van een verrijking of ga naar **Beheer** > **Verbindingen** en selecteer **Instellen** op de Dun & Bradstreet-tegel.

1. Geef een naam op voor de verbinding.

1. Geef geldige Dun & Bradstreet-referenties en Dun & Bradstreet-projectdetails *Regio, Doelmappad en Doelmapnaam*. U [krijgt deze informatie](#set-up-your-dun--bradstreet-project) van het Dun & Bradstreet-project.

1. Bekijk en geef uw toestemming voor [Gegevensprivacy en naleving](#data-privacy-and-compliance) door **Ik ga akkoord** te selecteren.

1. Selecteer **Verifiëren** om de configuratie te valideren en selecteer **Opslaan**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Configuratiepagina voor verbinding met Dun & Bradstreet":::

### <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar Dun & Bradstreet te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens in uw opdracht overdragen, maar het is uw verantwoordelijkheid ervoor te zorgen dat Dun & Bradstreet voldoet aan eventuele privacy- of beveiligingsverplichtingen die u hebt. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.
Uw Dynamics 365 Customer Insights-beheerder kan deze verrijking op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.

## <a name="supported-countries-or-regions"></a>Ondersteunde landen of regio's

We ondersteunen momenteel de volgende land-/regio-opties: Canada (Engels) of Verenigde Staten (Engels).

## <a name="configure-the-enrichment"></a>De verrijking configureren

1. Ga naar **Gegevens** > **Verrijking** en selecteer het tabblad **Detecteren**.

1. Selecteer **Mijn gegevens verrijken** op de tegel **Bedrijfsgegevens** voor Dun & Bradstreet.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Schermopname van de Dun & Bradstreet-tegel.":::

1. Bekijk het overzicht en selecteer **Volgende**.

1. Selecteer de verbinding en bevestig. Neem contact op met een beheerder als er geen verbinding beschikbaar is.

1. Selecteer **Volgende**.

1. Selecteer de **Klantgegevensset** en kies het profiel of segment dat u wilt verrijken met bedrijfsgegevens van Dun & Bradstreet. De entiteit *Klant* verrijkt al uw klantprofielen, terwijl een segment alleen klantprofielen in dat segment verrijkt.

1. Definieer welk type velden uit uw geharmoniseerde profielen moeten worden gebruikt voor overeenkomende bedrijfsgegevens van Dun & Bradstreet. Ten minste één van de velden **Naam en adres**, **Telefoon** of **E-mail** is vereist.

1. Selecteer **Volgende**

1. Wijs uw velden toe aan de bedrijfsgegevens van Dun & Bradstreet. Verplicht: het veld **DUNS-nummer** of de velden **Naam van het bedrijf** en **Land** .

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Dun & Bradstreet veldtoewijzingsvenster.":::

1. Selecteer **Volgende** om de veldtoewijzing te voltooien.

1. Geef een **Naam** op voor de verrijking en de **Naam van uitvoerentiteit**.

1. Selecteer **Verrijking opslaan** na het bekijken van uw keuzes.

1. Selecteer **Uitvoeren** om het verrijkingsproces te starten of sluit om terug te keren naar de pagina **Verrijkingen**.

## <a name="enrichment-results"></a>Verrijkingsresultaten

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Volgende stappen

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
