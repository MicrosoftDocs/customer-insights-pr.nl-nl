---
title: Verrijking van de verrijking door derden van HERE Technologies
description: Algemene informatie over de verrijking door derden van HERE Technologies.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668672"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Verrijking van klantprofielen met HERE Technologies (preview)

HERE Technologies is een locatieplatformbedrijf dat locatiegerichte gegevens en services levert. Met de gegevensverrijkingsservices van HERE Technologies kunt u een nauwkeuriger locatie-inzicht van uw klanten opbouwen met adresnormalisatie, extractie van breedtegraad en lengtegraad en meer.

## <a name="prerequisites"></a>Vereisten

Om HERE Technologies-verrijkingen te configureren, moet aan de volgende voorwaarden worden voldaan:

- U moet een actief abonnement hebben voor HERE Technologies. Om een abonnement te nemen, kunt u [hier registreren](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) of rechtstreeks [contact opnemen met HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Meer informatie over locatieverrijking door HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- U hebt de HERE Technologies API-sleutel.

- U hebt [Beheerders](permissions.md#administrator)machtigingen.

## <a name="configuration"></a>Configuratie

1. Ga naar **Gegevens** > **Verrijking**.

1. Selecteer **Mijn gegevens verrijken** op de HERE Technologies-tegel.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies-tegel](media/HERE-tile.png "HERE Technologies-tegel")

1. Voer een actieve **HERE Technologies API-sleutel** in. Bekijk en geef toestemming voor **Gegevensprivacy en naleving** door het selectievakje **Ik ga akkoord** in te schakelen. 

1. Bevestig de invoer door **Verbinden met HERE** te selecteren.

1. Selecteer **Gegevens toevoegen** en kies of u velden aan het primaire en/of secundaire adres wilt toewijzen. U kunt voor beide adressen een veldtoewijzing specificeren (bijvoorbeeld een privé- en een werkadres) en de profielen voor beide adressen afzonderlijk verrijken. Selecteer **Volgende**.

1. Definieer welke velden van uw geharmoniseerde profielen moeten worden gebruikt om te zoeken naar overeenkomende locatiegegevens van HERE Technologies. De velden **Straat 1** en **Postcode** zijn vereist voor het geselecteerde primaire en/of secundaire adres. Voor een hogere matchnauwkeurigheid kunnen meer velden worden toegevoegd.

   > [!div class="mx-imgBorder"]
   > ![Configuratiepagina voor verrijking van HERE Technologies](media/enrichment-HERE-configuration.png "Configuratiepagina voor verrijking van HERE Technologies")

1. Selecteer **Toepassen** om de veldtoewijzing te voltooien.

## <a name="enrichment-results"></a>Verrijkingsresultaten

Selecteer **Uitvoeren** vanaf de opdrachtbalk om het verrijkingsproces te starten. U kunt de verrijking ook automatisch laten uitvoeren als onderdeel van een [geplande vernieuwing](system.md#schedule-tab). De verwerkingstijd is afhankelijk van de grootte van uw klantgegevens en de API-responstijden van HERE Technologies.

Nadat het verrijkingsproces is voltooid, kunt u de nieuwe verrijkte klantprofielgegevens bekijken onder **Mijn verrijkingen**. Ook vindt u daar het tijdstip van de laatste update en het aantal verrijkte profielen.

U kunt een gedetailleerd overzicht van elk verrijkt profiel openen door **Verrijkte gegevens weergeven** te selecteren.

## <a name="next-steps"></a>Volgende stappen

Bouw voort op uw verrijkte klantgegevens. Maak [segmenten](segments.md), [metingen](measures.md) en [exporteer de gegevens](export-destinations.md) om uw klanten gepersonaliseerde ervaringen te bieden.

## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar HERE Technologies te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat HERE Technologies voldoet aan uw privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.
Uw Dynamics 365 Customer Insights-beheerder kan deze verrijking op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.
