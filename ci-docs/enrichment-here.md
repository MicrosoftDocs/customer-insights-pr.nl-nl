---
title: Verrijking met de verrijking van derden van HERE Technologies
description: Algemene informatie over de verrijking door derden van HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c131ffb230a62b76e123334ff3c6776c8f9aa06e
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646147"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Verrijking van klantprofielen met HERE Technologies (preview)

HERE Technologies is een locatieplatformbedrijf dat locatiegerichte gegevens en services levert. Met de gegevensverrijkingsservices van HERE Technologies kunt u een nauwkeuriger locatie-inzicht van uw klanten opbouwen met adresnormalisatie, extractie van breedtegraad en lengtegraad en meer.

## <a name="prerequisites"></a>Vereisten

Om HERE Technologies-verrijkingen te configureren, moet aan de volgende voorwaarden worden voldaan:

- U moet een actief abonnement hebben voor HERE Technologies. U kunt een abonnement nemen door zich [hier te registreren](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) of rechtstreeks [contact op te nemen met HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Meer informatie over locatieverrijking door HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Er is een HERE-[verbinding](connections.md) beschikbaar *of* u hebt [beheerdersmachtigingen](permissions.md#admin) en de HERE Technologies API-sleutel.

## <a name="configure-the-enrichment"></a>De verrijking configureren

1. Ga naar **Gegevens** > **Verrijking**. 

1. Selecteer **Mijn gegevens verrijken** op de tegel van HERE Technologies en selecteer vervolgens **Aan de slag**.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies-tegel.](media/HERE-tile.png "HERE Technologies-tegel")

1. Selecteer een [verbinding](connections.md) in de vervolgkeuzelijst. Neem contact op met een beheerder als er geen verbinding beschikbaar is. Als u een beheerder bent, kunt u een verbinding maken door **Verbinding toevoegen** te selecteren. Kies **HERE Technologies** uit de vervolgkeuzelijst. 

1. Selecteer **Verbinding maken met HERE Technologies** om de selectie te bevestigen.

1.  Selecteer **Volgende** en kies de **klantgegevensset** die u wilt verrijken met locatie gegevens van HERE Technologies. U kunt de entiteit **Klant** selecteren om al uw klantprofielen te verrijken of een segmententiteit selecteren om alleen klantprofielen in dat segment te verrijken.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Schermopname bij het kiezen van de klantgegevensset.":::

1. Kies of u velden aan het primaire en/of secundaire adres wilt toewijzen. U kunt voor beide adressen een veldtoewijzing specificeren en de profielen voor beide adressen afzonderlijk verrijken. Als er bijvoorbeeld een huisadres en een zakelijk adres is. Selecteer **Volgende**.

1. Definieer welke velden van uw geharmoniseerde profielen moeten worden gebruikt om te zoeken naar overeenkomende locatiegegevens van HERE Technologies. De velden **Straat 1** en **Postcode** zijn vereist voor het geselecteerde primaire en/of secundaire adres. Voor een hogere matchnauwkeurigheid kunnen meer velden worden toegevoegd.

   > [!div class="mx-imgBorder"]
   > ![Configuratiepagina voor verrijking van HERE Technologies.](media/enrichment-HERE-configuration.png "Configuratiepagina voor verrijking van HERE Technologies")

1. Selecteer **Volgende** om de veldtoewijzing te voltooien.

1. Geef een naam op voor de verrijking. 

1. Selecteer **Verrijking opslaan** na het bekijken van uw keuzes.

## <a name="configure-the-connection-for-here-technologies"></a>De verbinding configureren voor HERE Technologies 

U moet een beheerder zijn om verbindingen te kunnen configureren. Selecteer **Verbinding toevoegen** bij het configureren van een verrijking *of* ga naar **Beheerder** > **Verbindingen** en selecteer **Instellen** op de HERE technologies-tegel.

1. Voer een naam in voor de verbinding in het vak **Weergavenaam**.

1. Geef een geldige API-sleutel van HERE Technologies op.

1. Bekijk en geef uw toestemming voor **Gegevensprivacy en naleving** door **Ik ga akkoord** te selecteren.

1. Selecteer **Verifiëren** om de configuratie te valideren.

1. Voltooi de verificatie en selecteer **Opslaan**.

   > [!div class="mx-imgBorder"]
   > ![Configuratiepagina voor HERE technologies-verbinding.](media/enrichment-HERE-connection.png "Configuratiepagina voor HERE technologies-verbinding")

## <a name="enrichment-results"></a>Verrijkingsresultaten

Selecteer **Uitvoeren** vanaf de opdrachtbalk om het verrijkingsproces te starten. U kunt de verrijking ook automatisch laten uitvoeren als onderdeel van een [geplande vernieuwing](system.md#schedule-tab). De verwerkingstijd is afhankelijk van de grootte van uw klantgegevens en de API-responstijden van HERE Technologies.

Nadat het verrijkingsproces is voltooid, kunt u de nieuwe verrijkte klantprofielgegevens bekijken onder **Mijn verrijkingen**. Ook vindt u daar het tijdstip van de laatste update en het aantal verrijkte profielen.

U kunt een gedetailleerd overzicht van elk verrijkt profiel openen door **Verrijkte gegevens weergeven** te selecteren.

## <a name="next-steps"></a>Volgende stappen

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar HERE Technologies te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat HERE Technologies voldoet aan uw privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.
Uw Dynamics 365 Customer Insights-beheerder kan deze verrijking op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.


[!INCLUDE [footer-include](includes/footer-banner.md)]
