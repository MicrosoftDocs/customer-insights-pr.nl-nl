---
title: Verrijking met de verrijking door derden van Experian
description: Algemene informatie over de verrijking door derden van Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896367"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Klantprofielen verrijken met demografische gegevens van Experian (preview)

Experian is een wereldleider in kredietrapportage en marketingdiensten voor consumenten en bedrijven. Met de Experian-services voor gegevensverrijking kunt u een dieper inzicht in uw klanten opbouwen door uw klantprofielen te verrijken met demografische gegevens zoals de grootte van het huishouden, het inkomen en meer.

## <a name="prerequisites"></a>Vereisten

Als u Experian wilt configureren, moet aan de volgende vereisten worden voldaan:

- U hebt een actief Experian-abonnement. Als u een abonnement wilt nemen, [neemt u rechtstreeks contact op met Experian](https://www.experian.com/marketing-services/contact). [Meer informatie over gegevensverrijking met Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Er is al een Experian-verbinding geconfigureerd door een beheerder *of* u hebt [beheerdersmachtigingen](permissions.md#administrator). U hebt ook de gebruikers-id, de partij-id en het modelnummer nodig voor uw ST-account (Secure Transport)-account met SSH-ondersteuning dat Experian voor u heeft gemaakt.

## <a name="configure-the-enrichment"></a>De verrijking configureren

1. Ga naar **Gegevens** > **Verrijking** en selecteer het tabblad **Detecteren**.

1. Selecteer **Mijn gegevens verrijken** op de Experian-tegel.

   > [!div class="mx-imgBorder"]
   > ![Experian-tegel](media/experian-tile.png "Experian-tegel")
   > 

1. Selecteer een [verbinding](connections.md) in de vervolgkeuzelijst. Neem contact op met een beheerder als er geen verbinding beschikbaar is. Als u een beheerder bent, kunt u een verbinding maken door **Verbinding toevoegen** te selecteren en Experian te kiezen in de vervolgkeuzelijst. 

1. Selecteer **Verbinding maken met Experian** om de verbindingsselectie te bevestigen.

1.  Selecteer **Volgende** en kies de **klantgegevensset** die u wilt verrijken met demografische gegevens van Experian. U kunt de entiteit **Klant** selecteren om al uw klantprofielen te verrijken of een segmententiteit selecteren om alleen klantprofielen in dat segment te verrijken.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Schermopname bij het kiezen van de klantgegevensset.":::

1. Selecteer **Volgende** en bepaal welk type velden uit uw geharmoniseerde profielen moeten worden gebruikt om overeenkomende demografische gegevens van Experian te zoeken. Ten minste één van de velden **Naam en adres**, **Telefoon** of **E-mail** is vereist. Voor een hogere nauwkeurigheid bij de afstemming kunnen maximaal twee andere velden worden toegevoegd. Deze selectie heeft invloed op de toewijzingsvelden waartoe u in de volgende stap toegang hebt.

    > [!TIP]
    > Als u meer belangrijke id-kenmerken naar Experian verzendt, levert dat waarschijnlijk een hogere overeenkomst op.

1. Selecteer **Volgende** om de veldtoewijzing te starten.

1. Definieer welke velden uit uw geharmoniseerde profielen moeten worden gebruikt om overeenkomende demografische gegevens van Experian te zoeken. Vereiste velden zijn gemarkeerd.

1. Geef een naam op voor de verrijking en een naam voor de uitvoerentiteit.

1. Selecteer **Verrijking opslaan** na het bekijken van uw keuzes.

## <a name="configure-the-connection-for-experian"></a>De verbinding configureren voor Experian 

U moet een beheerder zijn om verbindingen te kunnen configureren. Selecteer **Verbinding toevoegen** bij het configureren van een verrijking *of* ga naar **Beheerder** > **Verbindingen** en selecteer **Instellen** op de Experian-tegel.

1. Selecteer **Aan de slag**.

1. Voer een naam in voor de verbinding in het vak **Weergavenaam**.

1. Voer een geldige gebruikers-id, partij-id en modelnummer in voor uw Experian Secure Transport-account.

1. **Gegevensprivacy en naleving** bekijken en toestemming geven door het selectievakje **Ik ga akkoord** in te schakelen

1. Selecteer **Verifiëren** om de configuratie te valideren.

1. Voltooi de verificatie en selecteer **Opslaan**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Configuratievenster voor Experian-verbinding.":::

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
