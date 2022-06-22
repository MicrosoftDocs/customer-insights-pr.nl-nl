---
title: Verrijking van LiveRamp-identificatiegegevens
description: Verrijk klantprofielen met LiveRamp-gegevens.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e8a130865267b57c89157b44be3d4bba3dc2fb4e
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953989"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Klantprofielen verrijken met identiteitsgegevens uit LiveRamp (preview)

LiveRamp biedt deterministische offline identiteitsresolutie en consolidatie van klantgegevens. U kunt persoonlijke identificatiegegevens in uw klantgegevens toewijzen aan de AbiliTec-identiteitsgrafiek en AbiliTec-id's ontvangen. U kunt deze id's vervolgens gebruiken voor een betere harmonisatie van uw klantgegevens.

## <a name="supported-countriesregions"></a>Ondersteunde landen/regio's

We ondersteunen momenteel alleen in de Verenigde Staten het verrijken van klantprofielen met LiveRamp-gegevens.

## <a name="prerequisites"></a>Vereisten

- Een actief LiveRamp-abonnement. Neem voor een abonnement contact op met uw LiveRamp-accountteam of met [dynamics@liveramp.com](mailto:dynamics@liveramp.com) voor meer informatie.

- Een actief AbiliTec-abonnement met een klant-id en geheim om toegang te krijgen tot de API. Zie [AbiliTec API Developer Hub](https://developers.liveramp.com/abilitec-api/) voor meer informatie.

- Een LiveRamp-[verbinding](connections.md) wordt [geconfigureerd](#configure-the-connection-for-liveramp) door een beheerder.

## <a name="configure-the-connection-for-liveramp"></a>De verbinding voor LiveRamp configureren

Je moet een [beheerder](permissions.md#admin) in Customer Insights zijn en een actieve LiveRamp client-id en -geheim hebben.

1. Selecteer **Verbinding toevoegen** bij het configureren van een verrijking of ga naar **Beheer** > **Verbindingen** en selecteer **Instellen** op de LiveRamp-tegel.

   :::image type="content" source="media/liveramp-connection.png" alt-text="Configuratievenster om de verbinding met de LiveRamp AbiliTec-service in te stellen. ":::

1. Voer een naam in voor de verbinding en een geldige LiveRamp-client-id en een geheim.

1. Bekijk en geef uw toestemming voor [Gegevensprivacy en naleving](#data-privacy-and-compliance) door **Ik ga akkoord** te selecteren.

1. Selecteer **Verifiëren** om de configuratie te valideren en selecteer **Opslaan**.

### <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar LiveRamp te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens in uw opdracht overdragen, maar het is uw verantwoordelijkheid ervoor te zorgen dat LiveRamp voldoet aan eventuele privacy- of beveiligingsverplichtingen die u hebt. Neem de [privacyverklaring van Microsoft](https://go.microsoft.com/fwlink/?linkid=396732) door voor meer informatie. Uw Dynamics 365 Customer Insights-beheerder kan deze verrijking op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.

## <a name="configure-the-enrichment"></a>De verrijking configureren

1. Ga naar **Gegevens** > **Verrijking** en selecteer het tabblad **Detecteren**.

1. Selecteer **Mijn gegevens verrijken** op de tegel **Identiteit** van de LiveRamp-tegel.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Identiteitstegel op de overzichtspagina voor verrijking. ":::

1. Bekijk het overzicht en selecteer **Volgende**.

1. Selecteer de verbinding. Neem contact op met een beheerder als er geen verbinding beschikbaar is.

1. Selecteer **Volgende**.

1. Selecteer de **Klantgegevensset** en kies het profiel of segment dat u wilt verrijken met identiteitsgegevens van LiveRamp. De entiteit *Klant* verrijkt al uw klantprofielen, terwijl een segment alleen klantprofielen in dat segment verrijkt.

1. Definieer welk type velden uit uw geharmoniseerde profielen moeten worden gebruikt voor overeenkomende identiteitsgegevens van LiveRamp. Ten minste één van de velden **Naam en adres**, **E-mail** of **Telefoon** is vereist. Voeg meer velden toe voor een hogere matchnauwkeurigheid. Selecteer **Volgende**.

1. Wijs uw velden toe aan de identificatiegegevens van LiveRamp.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Opties voor gegevenstoewijzing voor de LiveRamp-verrijking.":::

1. Selecteer **Volgende** om de veldtoewijzing te voltooien.

1. Geef een **Naam** op voor de verrijking en de **Naam van uitvoerentiteit**.

1. Selecteer **Verrijking opslaan** na het bekijken van uw keuzes.

1. Selecteer **Uitvoeren** om het verrijkingsproces te starten of sluit om terug te keren naar de pagina **Verrijkingen**.

## <a name="enrichment-results"></a>Verrijkingsresultaten

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Het **Aantal klanten dat wordt verrijkt per veld** biedt een gedetailleerde beschrijving van de dekking van elk verrijkt veld.

## <a name="next-steps"></a>Volgende stappen

Bouw voort op uw verrijkte klantgegevens. Gebruik de AbiliTec-id's om klantprofielen te consolideren in een persoonsgericht overzicht.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
