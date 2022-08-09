---
title: Bedrijfsprofielen verrijken met Leadspace (preview)
description: Algemene informatie over de verrijking door derden van Leadspace.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 3f23fe7177f931db3e3179970915d0cd3c736f87
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196204"
---
# <a name="enrich-company-profiles-with-leadspace-preview"></a>Bedrijfsprofielen verrijken met Leadspace (preview)

Leadspace is een data science-bedrijf dat B2B-platform voor klantgegevens biedt. Het stelt omgevingen met geharmoniseerde klantprofielen op basis van accounts in staat om hun gegevens te verrijken. Verrijk *Klantprofielen* met kenmerken zoals bedrijfsgrootte, locatie of branche. Verrijk *Contactprofielen* met kenmerken zoals functie, persona of e-mailverificatie.

## <a name="prerequisites"></a>Vereisten

- Een actieve Leadspace-licentie.
- [Geharmoniseerde klantprofielen](customer-profiles.md) gebaseerd op accounts.
- Een Leadspace-[verbinding](connections.md) wordt [geconfigureerd](#configure-the-connection-for-leadspace) door een beheerder. Neem rechtstreeks contact op met [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) voor details over hun product.

## <a name="configure-the-connection-for-leadspace"></a>De verbinding configureren voor Leadspace

U moet een [beheerder](permissions.md#admin) in Customer Insights zijn en de 'permanente sleutel' hebben (aangeduid als **Leadspace-token**).

1. Selecteer **Verbinding toevoegen** bij het configureren van een verrijking of ga naar **Beheer** > **Verbindingen** en selecteer **Instellen** op de Leadspace-tegel.

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Configuratiepagina voor Leadspace-verbinding.":::

1. Voer een naam in voor de verbinding en een geldig Leadspace-token.

1. Bekijk en geef uw toestemming voor [Gegevensprivacy en naleving](#data-privacy-and-compliance) door **Ik ga akkoord** te selecteren.

1. Selecteer **Verifiëren** om de configuratie te valideren en selecteer **Opslaan**.

### <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar Leadspace te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat Leadspace voldoet aan uw privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.
Uw Dynamics 365 Customer Insights-beheerder kan deze verrijking op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.

## <a name="configure-the-enrichment"></a>De verrijking configureren

1. Ga naar **Gegevens** > **Verrijking** en selecteer het tabblad **Detecteren**.

1. Selecteer **Mijn gegevens verrijken** op de tegel **Bedrijfsgegevens** van Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Schermopname van de Leadspace-tegel.":::

1. Bekijk het overzicht en selecteer **Volgende**.

1. Selecteer de verbinding. Neem contact op met een beheerder als er geen verbinding beschikbaar is.

1. Selecteer **Volgende**.

1. Selecteer de **Klantgegevensset** en kies het profiel of segment dat u wilt verrijken met bedrijfsgegevens van Leadspace. De entiteit *Klant* verrijkt al uw klantprofielen, terwijl een segment alleen klantprofielen in dat segment verrijkt.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Schermopname bij het kiezen van de klantgegevensset.":::

1. Definieer welk type velden uit uw geharmoniseerde profielen u wilt gebruiken voor het matchen: het primaire en/of secundaire adres. U kunt voor beide adressen een veldtoewijzing specificeren en de profielen voor beide adressen afzonderlijk verrijken. Bijvoorbeeld voor een woonadres en een zakelijk adres. Selecteer **Volgende**.

1. Wijs uw velden toe aan de bedrijfsgegevens van Leadspace. Het veld **Naam van bedrijf** is verplicht. Voor een hogere matchnauwkeurigheid kunt u maximaal twee andere velden, **Bedrijfswebsite** en **Bedrijfslocatie** toevoegen.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Deelvenster Leadspace-veldtoewijzing.":::

1. Selecteer **Volgende** om de veldtoewijzing te voltooien.

1. Vink het selectievakje aan als u *Contactprofielen* hebt die u zou willen verrijken. Customer Insights koppelt automatisch de vereiste velden.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Verrijking van Leadspace-contactpersoonrecords.":::

1. Selecteer **Volgende**.

1. Geef een **Naam** op voor de verrijking en de **Naam van uitvoerentiteit**.

1. Selecteer **Verrijking opslaan** na het bekijken van uw keuzes.

1. Selecteer **Uitvoeren** om het verrijkingsproces te starten of sluit om terug te keren naar de pagina **Verrijkingen**.

## <a name="view-enrichment-results"></a>Verrijkingsresultaten bekijken

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Zie [De API's van Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API) voor meer informatie.

## <a name="next-steps"></a>Volgende stappen

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
