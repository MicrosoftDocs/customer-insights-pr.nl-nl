---
title: Verrijking van LiveRamp-identificatiegegevens
description: Verrijk klantprofielen met LiveRamp-gegevens.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ee65cb49447df61dd5c298a84ad21bc119ead558
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2022
ms.locfileid: "8373010"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Klantprofielen verrijken met identiteitsgegevens uit LiveRamp (preview) 

LiveRamp biedt deterministische offline identiteitsresolutie en consolidatie van klantgegevens. U kunt persoonlijke identificatiegegevens in uw klantgegevens toewijzen aan de AbiliTec-identiteitsgrafiek en AbiliTec-id's ontvangen. U kunt deze id's vervolgens gebruiken voor een betere harmonisatie van uw klantgegevens. 

## <a name="prerequisites"></a>Vereisten 

Als u de verrijking wilt configureren, moet aan de volgende vereisten worden voldaan: 

- U hebt een actief LiveRamp-abonnement. Neem voor een abonnement contact op met uw LiveRamp-accountteam of met [dynamics@liveramp.com](mailto:dynamics@liveramp.com) voor meer informatie.   

- Een actief AbiliTec-abonnement met een klant-id en geheim om toegang te krijgen tot de API. Zie [AbiliTec API Developer Hub](https://developers.liveramp.com/abilitec-api/) voor meer informatie. 

## <a name="supported-countriesregions"></a>Ondersteunde landen/regio's 

We ondersteunen momenteel alleen in de Verenigde Staten het verrijken van klantprofielen met LiveRamp-gegevens. 

## <a name="configure-the-enrichment"></a>De verrijking configureren 

1. Ga naar **Gegevens** > **Verrijking** en selecteer het tabblad **Detecteren**. 

1. Selecteer **Mijn gegevens verrijken** op de tegel **Identiteit**. 

   :::image type="content" source="media/liveramp-tile.png" alt-text="Identiteitstegel op de overzichtspagina voor verrijking. ":::

1. Selecteer een [verbinding](connections.md) in de vervolgkeuzelijst. Neem contact op met een beheerder als er geen verbinding beschikbaar is. Als u beheerder bent, kunt u een verbinding maken door **Verbinding toevoegen** te selecteren. Kies **LiveRamp** in de vervolgkeuzelijst. 

1. Selecteer **Volgende** en kies de **klantgegevensset** die u wilt verrijken met identiteitsgegevens van LiveRamp. U kunt de entiteit *Klant* selecteren om al uw klantprofielen te verrijken of een entiteit *segment* selecteren om alleen klantprofielen in dat segment te verrijken. 

1. Selecteer **Volgende** en definieer welk type velden uit uw geharmoniseerde profielen moeten worden gebruikt om te zoeken naar overeenkomende identiteitsgegevens van LiveRamp. Ten minste één van de velden **Naam en adres**, **Telefoon** of **E-mail** is vereist. 

   > [!TIP]
   > Hoe meer sleutel-id's en velden u toewijst, hoe groter de kans op een hoger matchpercentage 

1. Wijs de velden van uw geharmoniseerde entiteit *Klant* toe die zal worden gebruikt voor afstemming met de AbiliTec-id-grafiek van LiveRamp. 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Opties voor gegevenstoewijzing voor de LiveRamp-verrijking.":::

1. Selecteer **Volgende** om de veldtoewijzing te voltooien. 

1. Geef een **naam** op voor de verrijking en de **uitvoerentiteit**. 

1. Selecteer **Verrijking opslaan** na het bekijken van uw keuzes. 

## <a name="configure-the-connection-for-liveramp"></a>De verbinding voor LiveRamp configureren 

U moet een beheerder zijn om [verbindingen te kunnen configureren](connections.md). Selecteer **Verbinding toevoegen** bij het configureren van de verrijking of ga naar **Beheerder** > **Verbindingen** en selecteer **Instellen** op de **LiveRamp**-tegel. 

:::image type="content" source="media/liveramp-connection.png" alt-text="Configuratievenster om de verbinding met de LiveRamp AbiliTec-service in te stellen. ":::

1. Voer voor **Weergavenaam** de naam van de verbinding in. 

1. Geef een geldige LiveRamp-client-id en een geheim op. 

1. Bekijk en geef toestemming voor **Gegevensprivacy en naleving** door het selectievakje **Ik ga akkoord** in te schakelen. 

1. Selecteer **Verifiëren** om de configuratie te valideren. 

1. Voltooi de verbinding door **Opslaan** te selecteren. 

## <a name="enrichment-results"></a>Verrijkingsresultaten 

Selecteer Uitvoeren vanaf de opdrachtbalk om het verrijkingsproces te starten. U kunt de verrijking ook automatisch laten uitvoeren als onderdeel van een  [geplande vernieuwing](system.md#schedule-tab). De verwerkingstijd is afhankelijk van de grootte van uw klantgegevens. 

Nadat het verrijkingsproces is voltooid, kunt u de nieuw verrijkte klantprofielgegevens bekijken onder  **Mijn verrijkingen**. Ook vindt u daar het tijdstip van de laatste update en het aantal verrijkte profielen. 

U kunt een gedetailleerd overzicht van elk verrijkt profiel openen door  **Verrijkte gegevens weergeven** te selecteren. 

## <a name="next-steps"></a>Volgende stappen

Bouw voort op uw verrijkte klantgegevens. Gebruik de AbiliTec-id's om klantprofielen te consolideren in een persoonsgericht overzicht. 
[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving 

Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar LiveRamp te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens in uw opdracht overdragen, maar het is uw verantwoordelijkheid ervoor te zorgen dat LiveRamp voldoet aan eventuele privacy- of beveiligingsverplichtingen die u hebt. Neem de [privacyverklaring van Microsoft](https://go.microsoft.com/fwlink/?linkid=396732) door voor meer informatie. Uw Dynamics 365 Customer Insights-beheerder kan deze verrijking op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
