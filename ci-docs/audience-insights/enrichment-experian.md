---
title: Verrijking met de verrijking door derden van Experian
description: Algemene informatie over de verrijking door derden van Experian.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4d4723e8f793ee857c4f5204a42be8338c71d4c3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597781"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Klantprofielen verrijken met demografische gegevens van Experian (preview)

Experian is een wereldleider in kredietrapportage en marketingdiensten voor consumenten en bedrijven. Met de Experian-services voor gegevensverrijking kunt u een dieper inzicht in uw klanten opbouwen door uw klantprofielen te verrijken met demografische gegevens zoals de grootte van het huishouden, het inkomen en meer.

## <a name="prerequisites"></a>Vereisten

Als u Experian wilt configureren, moet aan de volgende vereisten worden voldaan:

- U hebt een actief Experian-abonnement. Als u een abonnement wilt nemen, [neemt u rechtstreeks contact op met Experian](https://www.experian.com/marketing-services/contact). [Meer informatie over gegevensverrijking met Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).
- U hebt de gebruikers-id, partij-id en modelnummer voor uw voor SSH geschikte ST-account (Secure Transport) dat Experian voor u heeft gemaakt.
- U hebt [Beheerder](permissions.md#administrator) machtigingen in doelgroepinzichten.

## <a name="configuration"></a>Configuratie

1. Ga naar **Gegevens** > **Verrijking** en selecteer het tabblad **Detecteren**.

1. Selecteer **Mijn gegevens verrijken** op de Experian-tegel.

   > [!div class="mx-imgBorder"]
   > ![Experian-tegel](media/experian-tile.png "Experian-tegel")

1. Selecteer **Aan de slag** en voer de gebruikers-id, partij-id en modelnummer voor uw Experian Secure Transport-account in. Bekijk en geef toestemming voor **Gegevensprivacy en naleving** door het selectievakje **Ik ga akkoord** in te schakelen. Bevestig alle invoer door **Toepassen** te selecteren.

## <a name="map-your-fields"></a>Uw velden toewijzen

1.  Selecteer **Gegevens toevoegen** en kies de **Klantgegevensset** die u wilt verrijken met demografische gegevens van Experian. U kunt de entiteit **Klant** selecteren om al uw klantprofielen te verrijken of een segmententiteit selecteren om alleen klantprofielen in dat segment te verrijken.

1. Selecteer uw belangrijkste id's uit **Naam en adres**​, **E-mail** of **Telefoon** om naar Experian te sturen voor identiteitsresolutie.

   > [!TIP]
   > Als u meer belangrijke id-kenmerken naar Experian verzendt, levert dat waarschijnlijk een hogere overeenkomst op.

1. Selecteer **Volgende** en wijs de overeenkomstige kenmerken van uw uniforme klantentiteit toe voor de geselecteerde id-velden.

1. Selecteer **Kenmerk toevoegen** om eventuele aanvullende kenmerken die u naar Experian wilt verzenden, toe te wijzen.

1.  Selecteer **Opslaan** om de veldtoewijzing te voltooien.

    > [!div class="mx-imgBorder"]
    > ![Experian-veldtoewijzing](media/experian-field-mapping.png "Experian-veldtoewijzing")

## <a name="enrichment-results"></a>Verrijkingsresultaten

Selecteer **Uitvoeren** vanaf de opdrachtbalk om het verrijkingsproces te starten. U kunt de verrijking ook automatisch laten uitvoeren als onderdeel van een [geplande vernieuwing](system.md#schedule-tab). De verwerkingstijd is afhankelijk van de omvang van uw klantgegevens en de verrijkingsprocessen die Experian voor uw account heeft ingesteld.

Nadat het verrijkingsproces is voltooid, kunt u de nieuwe verrijkte klantprofielgegevens bekijken onder **Mijn verrijkingen**. Ook vindt u daar het tijdstip van de laatste update en het aantal verrijkte profielen.

U kunt een gedetailleerd overzicht van elk verrijkt profiel openen door **Verrijkte gegevens weergeven** te selecteren.

## <a name="next-steps"></a>Volgende stappen

Bouw voort op uw verrijkte klantgegevens. Maak [segmenten](segments.md), [metingen](measures.md) en [exporteer de gegevens](export-destinations.md) om uw klanten gepersonaliseerde ervaringen te bieden.

## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar Experian te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat Experian voldoet aan uw privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.
Uw Dynamics 365 Customer Insights-beheerder kan deze verrijking op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]