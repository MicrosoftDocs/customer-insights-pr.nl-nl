---
title: Klantprofielen verrijken met HERE Technologies (preview)
description: Algemene informatie over de verrijking door derden van HERE Technologies.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 86a070342193dd7afda38823d90f4bd28c8b862e
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237852"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Klantprofielen verrijken met HERE Technologies (preview)

HERE Technologies is een locatieplatformbedrijf dat locatiegerichte gegevens en services levert. De gegevensverrijkingsservices van HERE Technologies verbeteren de nauwkeurigheid van locatie-informatie over uw klanten. Het biedt adresnormalisatie, breedte- en lengtegraadextractie en meer.

## <a name="prerequisites"></a>Vereisten

- Een actief HERE Technologies-abonnement. Als u een abonnement wilt nemen, [meldt u zich hier aan](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic). U kunt ook rechtstreeks [contact opnemen met HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Meer informatie over locatieverrijking door HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Een HERE-[verbinding](connections.md) wordt [geconfigureerd](#configure-the-connection-for-here-technologies) door een beheerder.

## <a name="configure-the-connection-for-here-technologies"></a>De verbinding configureren voor HERE Technologies

U moet een [beheerder](permissions.md#admin) in Customer Insights zijn en een actieve HERE Technologies API-sleutel hebben.

1. Selecteer **Verbinding toevoegen** bij het configureren van een verrijking of ga naar **Beheer** > **Verbindingen** en selecteer **Instellen** op de HERE Technologies-tegel.

1. Voer een naam in voor de verbinding en een geldige HERE Technologies API-sleutel.

1. Bekijk [Gegevensprivacy en naleving](connections.md#data-privacy-and-compliance) en selecteer **Ik ga akkoord**.

1. Selecteer **Verifiëren** om de configuratie te valideren en selecteer **Opslaan**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="Configuratiepagina voor HERE technologies-verbinding.":::

## <a name="configure-the-enrichment"></a>De verrijking configureren

1. Ga naar **Gegevens** > **Verrijking** en selecteer het tabblad **Detecteren**.

1. Selecteer **Mijn gegevens verrijken** op de tegel **Locatie** van HERE Technologies.

   :::image type="content" source="media/HERE-tile.png" alt-text="HERE Technologies-tegel.":::

1. Bekijk het overzicht en selecteer **Volgende**.

1. Selecteer de verbinding. Neem contact op met een beheerder als er geen verbinding beschikbaar is.

1. Selecteer **Volgende**.

1. Selecteer de **Klantgegevensset** en kies het profiel of segment dat u wilt verrijken met gegevens van HERE Technologies. De entiteit *Klant* verrijkt al uw klantprofielen, terwijl een segment alleen klantprofielen in dat segment verrijkt.

1. Definieer welk type velden uit uw geharmoniseerde profielen u wilt gebruiken voor het matchen: het primaire en/of secundaire adres. U kunt voor beide adressen een veldtoewijzing specificeren en de profielen voor beide adressen afzonderlijk verrijken. Bijvoorbeeld voor een woonadres en een zakelijk adres. Selecteer **Volgende**.

1. Wijs uw velden toe aan de gegevens van HERE Technologies. De velden **Straat 1** en **Postcode** zijn vereist voor het geselecteerde primaire en/of secundaire adres. Voeg meer velden toe voor een hogere matchnauwkeurigheid.

1. Selecteer **Volgende** om de veldtoewijzing te voltooien.

1. Geef een **Naam** op voor de verrijking en de **Naam van uitvoerentiteit**.

1. Selecteer **Verrijking opslaan** na het bekijken van uw keuzes.

1. Selecteer **Uitvoeren** om het verrijkingsproces te starten of sluit om terug te keren naar de pagina **Verrijkingen**.

## <a name="view-enrichment-results"></a>Verrijkingsresultaten bekijken

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Het **Aantal klanten dat wordt verrijkt per veld** biedt een gedetailleerde beschrijving van de dekking van elk verrijkt veld.

## <a name="next-steps"></a>Volgende stappen

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
