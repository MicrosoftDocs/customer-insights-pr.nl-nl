---
title: Verrijking van bedrijfsprofielen met Dun & Bradstreet
description: Algemene informatie over de verrijking door derden met Dun & Bradstreet.
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c738c2657d4cda213342629156ddc8104366bd8a
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755394"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Verrijking van bedrijfsprofielen met Dun & Bradstreet (preview)

Dun & Bradstreet biedt commerciële gegevens, analyses en inzichten voor bedrijven. Het stelt klanten met geharmoniseerde klantprofielen voor bedrijven in staat hun gegevens te verrijken. Verrijkingen omvatten kenmerken, waaronder DUNS-nummer, bedrijfsgrootte, locatie, branche en meer.

## <a name="prerequisites"></a>Vereisten

Als u een Dun & Bradstreet-verrijking wilt configureren, moet aan de volgende vereisten worden voldaan:

- U hebt een actieve [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights)-licentie.
- U hebt [geharmoniseerde klantprofielen](customer-profiles.md) voor bedrijven.
- Een Dun & Bradstreet-[verbinding](connections.md) wordt geconfigureerd door een beheerder. U kunt het maken als u machtigingen als [beheerder](permissions.md#admin) hebt en de referenties voor Dun & Bradstreet Connect om u aan te melden.

## <a name="setting-up-your-dun--bradstreet-project"></a>Uw Dun & Bradstreet-project instellen

Als gelicentieerde gebruiker van Dun & Bradstreet kunt u een project instellen in [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).


1. Meld u aan bij [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights) Om referenties op te halen [herstelt u uw wachtwoord](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Download [ons csv-sjabloonbestand](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) dat zal worden gebruikt om de Customer Insights-velden toe te wijzen aan de overeenkomstige Dun & Bradstreet-velden.

1. Upload het bestand in de stap **Gegevens uploaden** van de Dun & Bradstreet-projectcreatie-ervaring.

1. Selecteer de horizontale stippen onder de relevante **bron** in het nieuw gecreëerde Dun & Bradstreet-project om de beschikbare opties te zien.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Schermopname van stippen in een Dun & Bradstreet-project.":::

1. Kies **S3-details ophalen**. Bewaar deze informatie op een veilige plaats. U hebt dit nodig om [de verbinding voor de verrijking in te stellen](#configure-a-connection-for-dun--bradstreet) in Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Schermopname van selectie van s3-informatie in een Dun & Bradstreet-project.":::

## <a name="configure-the-enrichment"></a>De verrijking configureren

1. Ga naar **Gegevens** > **Verrijking**.

1. Selecteer **Mijn gegevens verrijken** op de Dun & Bradstreet-tegel en selecteer **Aan de slag**.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Schermopname van de Dun & Bradstreet-tegel.":::

1. Selecteer een [verbinding](connections.md) in de vervolgkeuzelijst. Neem contact op met een beheerder als er geen verbinding beschikbaar is. Als u beheerder bent, kunt u een verbinding maken. Selecteer **Verbinding toevoegen** en kies **Dun & Bradstreet**.

1. Selecteer **Verbinding maken met Dun & Bradstreet** om de verbinding te bevestigen.

1. Selecteer **Volgende** en kies de **klantgegevensset** die u wilt verrijken met bedrijfsgegevens van Dun & Bradstreet. U kunt de entiteit **Klant** selecteren om al uw klantprofielen te verrijken of een segmententiteit selecteren om alleen geharmoniseerde klantprofielen in dat segment te verrijken.

1. Selecteer **Volgende** en definieer welk type velden uit uw geharmoniseerde profielen worden gebruikt om te zoeken naar overeenkomende bedrijfsgegevens van Dun & Bradstreet. Verplicht: het veld **DUNS-nummer** of de velden **Naam van het bedrijf** en **Land** . Het landveld mag [landcodes van twee of drie letters](https://www.iso.org/iso-3166-country-codes.html), bevatten, de landnaam in het Engels, landnaam in moedertaal en telefoonvoorvoegsel. Enkele veelvoorkomende landvarianten zijn:

- VS: Verenigde Staten van Amerika, Verenigde Staten, VS, Amerika.
- CA: Canada.
- GB: Verenigd Koninkrijk, VK, Groot-Brittannië, GB, Verenigd Koninkrijk van Groot-Brittannië en Noord-Ierland, Verenigd Koninkrijk van Groot-Brittannië.
- AU: Australië, Gemenebest van Australië.
- FR: Frankrijk, Franse Republiek.
- DE: Duitsland, Duits, Deutschland, Allemagne, Bondsrepubliek Duitsland, Republiek Duitsland.

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Dun & Bradstreet veldtoewijzingsvenster.":::

1. Selecteer **Volgende** om de veldtoewijzing te voltooien.

1. Geef een naam op voor de verrijking en selecteer **Verrijking opslaan** na het bekijken van uw keuzes.

## <a name="configure-a-connection-for-dun--bradstreet"></a>Een verbinding configureren voor Dun & Bradstreet

U moet een beheerder zijn om verbindingen te kunnen configureren. Selecteer **Verbinding toevoegen** bij het configureren van een verrijking *of* ga naar **Beheerder** > **Verbindingen** en selecteer **Instellen** op de Dun & Bradstreet-tegel.

1. Selecteer **Aan de slag**.

1. Voer een naam in voor de verbinding in het vak **Weergavenaam**.

1. Geef geldige Dun & Bradstreet-referenties en Dun & Bradstreet-projectdetails *Regio, Doelmappad en Doelmapnaam*. U [krijgt deze informatie](#setting-up-your-dun--bradstreet-project) van het Dun & Bradstreet-project.

1. Bekijk en geef uw toestemming voor **Gegevensprivacy en naleving** door **Ik ga akkoord** te selecteren.

1. Selecteer **Verifiëren** om de configuratie te valideren.

1. Voltooi de verificatie en selecteer **Opslaan**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Configuratiepagina voor verbinding met Dun & Bradstreet":::

## <a name="enrichment-results"></a>Verrijkingsresultaten

Nadat u de verrijking hebt vernieuwd, kunt u de nieuw verrijkte bedrijfsgegevens bekijken onder [Mijn verrijkingen](enrichment-hub.md). U kunt het tijdstip van de laatste update en het aantal verrijkte profielen terugvinden.

U kunt een gedetailleerd overzicht van elk verrijkt profiel openen door **Verrijkte gegevens weergeven** te selecteren.

## <a name="next-steps"></a>Volgende stappen

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar Dun & Bradstreet te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens in uw opdracht overdragen, maar het is uw verantwoordelijkheid ervoor te zorgen dat Dun & Bradstreet voldoet aan eventuele privacy- of beveiligingsverplichtingen die u hebt. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.
Uw Dynamics 365 Customer Insights-beheerder kan deze verrijking op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.

[!INCLUDE[footer-include](includes/footer-banner.md)]
