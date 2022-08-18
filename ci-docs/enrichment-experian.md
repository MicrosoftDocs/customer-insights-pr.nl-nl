---
title: Klantprofielen verrijken met demografische gegevens van Experian (preview)
description: Algemene informatie over de verrijking van derden Experian.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: fccb37cde3f05a70009c18b6c52db01a5ede094d
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237990"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Klantprofielen verrijken met demografische gegevens van Experian (preview)

Experian is een wereldleider op het gebied van kredietrapportage en marketingdiensten voor consumenten en bedrijven. Met de dataverrijkingsdiensten van Experian kunt u een dieper inzicht in uw klanten opbouwen door uw klantprofielen te verrijken met demografische gegevens zoals de grootte van het huishouden, inkomen en meer.

## <a name="supported-countriesregions"></a>Ondersteunde landen/regio's

We ondersteunen momenteel alleen het verrijken van klantprofielen in de Verenigde Staten.

## <a name="prerequisites"></a>Vereisten

- Een actief Experian-abonnement. U kunt een abonnement nemen door rechtstreeks [contact op te nemen met Experian](https://www.experian.com/marketing-services/contact). [Kom meer te weten over gegevensverrijking met Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Een Experian-[verbinding](connections.md) wordt [geconfigureerd](#configure-the-connection-for-experian) door een beheerder.

- Experian gebruikers-id, partij-id en modelnummer voor uw SSH-enabled Secure Transport (ST)-account dat Experian voor u heeft gemaakt.

## <a name="configure-the-connection-for-experian"></a>De verbinding configureren voor Experian

Je moet een [beheerder](permissions.md#admin) in Customer Insights zijn en een Experian gebruikers-id, partij-id en modelnummer hebben.

1. Selecteer **Verbinding toevoegen** bij het configureren van een verrijking of ga naar **Beheer** > **Verbindingen** en selecteer **Instellen** op de Experian-tegel.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian-verbindingsconfiguratievenster.":::

1. Voer een naam in voor de verbinding en een geldige gebruikers-id, partij-id en modelnummer voor uw Experian Secure Transport-account.

1. Bekijk [Gegevensprivacy en naleving](connections.md#data-privacy-and-compliance) en selecteer **Ik ga akkoord**.

1. Selecteer **Verifiëren** om de configuratie te valideren en selecteer **Opslaan**.

## <a name="configure-the-enrichment"></a>De verrijking configureren

1. Ga naar **Gegevens** > **Verrijking** en selecteer het tabblad **Detecteren**.

1. Selecteer **Mijn gegevens verrijken** op de tegel **Demografische gegevens** van Experian.

   :::image type="content" source="media/experian-tile.png" alt-text="Experian-tegel op de overzichtspagina voor verrijking. ":::

1. Bekijk het overzicht en selecteer **Volgende**.

1. Selecteer de verbinding. Neem contact op met een beheerder als er geen verbinding beschikbaar is.

1. Selecteer **Volgende**.

1. Selecteer de **Klantgegevensset** en kies het profiel of segment dat u wilt verrijken met demografische gegevens van Experian. De entiteit *Klant* verrijkt al uw klantprofielen, terwijl een segment alleen klantprofielen in dat segment verrijkt.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Schermopname bij het kiezen van de klantgegevensset.":::

1. Definieer welk type velden uit uw geharmoniseerde profielen moeten worden gebruikt voor overeenkomende demografische gegevens van Experian. Ten minste één van de velden **Naam en adres**, **Telefoon** of **E-mail** is vereist. Voeg meer velden toe voor een hogere matchnauwkeurigheid. Selecteer **Volgende**.

1. Wijs uw velden toe aan de demografische gegevens van Experian.

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
