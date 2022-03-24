---
title: Verrijking met de verrijking van derden Experian
description: Algemene informatie over de verrijking van derden Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: efa26fa82a950063e074a4ab930ed95383c55334
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376686"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Klantprofielen verrijken met demografische gegevens van Experian (preview)

Experian is een wereldleider op het gebied van kredietrapportage en marketingdiensten voor consumenten en bedrijven. Met de dataverrijkingsdiensten van Experian kunt u een dieper inzicht in uw klanten opbouwen door uw klantprofielen te verrijken met demografische gegevens zoals de grootte van het huishouden, inkomen en meer.

## <a name="prerequisites"></a>Vereisten

Als u Experian wilt configureren, moet aan de volgende vereisten worden voldaan:

- U moet een actief abonnement hebben voor Experian. U kunt een abonnement nemen door rechtstreeks [contact op te nemen met Experian](https://www.experian.com/marketing-services/contact). [Kom meer te weten over gegevensverrijking met Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Er is al een Experian-verbinding geconfigureerd door een beheerder *of* u hebt [beheerdersmachtigingen](permissions.md#admin). U hebt ook de gebruikers-id, de partij-id en het modelnummer nodig voor uw ST-account (Secure Transport) met SSH-ondersteuning dat Experian voor u heeft gemaakt.

## <a name="supported-countriesregions"></a>Ondersteunde landen/regio's

We ondersteunen momenteel alleen het verrijken van klantprofielen in de Verenigde Staten.

## <a name="configure-the-enrichment"></a>De verrijking configureren

1. Ga naar **Gegevens** > **Verrijking** en selecteer het tabblad **Detecteren**.

1. Selecteer **Mijn gegevens verrijken** op de Experian-tegel.

   > [!div class="mx-imgBorder"]
   > ![Experian-tegel.](media/experian-tile.png "Experian tile")
   > 

1. Selecteer een [verbinding](connections.md) in de vervolgkeuzelijst. Neem contact op met een beheerder als er geen verbinding beschikbaar is. Als u een beheerder bent, kunt u een verbinding maken door **Verbinding toevoegen** te selecteren en Experian te kiezen in de vervolgkeuzelijst. 

1. Selecteer **Verbinden met Experian** om de verbindingsselectie te bevestigen.

1.  Selecteer **Volgende** en kies de **klantgegevensset** die u wilt verrijken met demografische gegevens van Experian. U kunt de entiteit **Klant** selecteren om al uw klantprofielen te verrijken of een segmententiteit selecteren om alleen klantprofielen in dat segment te verrijken.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Schermopname bij het kiezen van de klantgegevensset.":::

1. Selecteer **Volgende** en definieer welk type velden uit uw geharmoniseerde profielen moeten worden gebruikt om te zoeken naar overeenkomende demografische gegevens van Experian. Ten minste één van de velden **Naam en adres**, **Telefoon** of **E-mail** is vereist. Voor een hogere nauwkeurigheid bij de afstemming kunnen maximaal twee andere velden worden toegevoegd. Deze selectie heeft invloed op de toewijzingsvelden waartoe u in de volgende stap toegang hebt.

    > [!TIP]
    > Als meer sleutel-id-kenmerken naar Experian worden verzonden, levert dit waarschijnlijk een hoger matchpercentage op.

1. Selecteer **Volgende** om de veldtoewijzing te starten.

1. Definieer welke velden uit uw geharmoniseerde profielen moeten worden gebruikt om te zoeken naar overeenkomende demografische gegevens van Experian. Vereiste velden zijn gemarkeerd.

1. Geef een naam op voor de verrijking en een naam voor de uitvoerentiteit.

1. Selecteer **Verrijking opslaan** na het bekijken van uw keuzes.

## <a name="configure-the-connection-for-experian"></a>De verbinding configureren voor Experian 

U moet een beheerder zijn om verbindingen te kunnen configureren. Selecteer **Verbinding toevoegen** bij het configureren van een verrijking *of* ga naar **Beheerder** > **Verbindingen** en selecteer **Instellen** op de Experian-tegel.

1. Selecteer **Aan de slag**.

1. Voer een naam in voor de verbinding in het vak **Weergavenaam**.

1. Voer een geldige gebruikers-id, partij-id en modelnummer in voor uw Experian Secure Transport-account.

1. Bekijk en geef uw toestemming voor **Gegevensprivacy en naleving** door **Ik ga akkoord** te selecteren.

1. Selecteer **Verifiëren** om de configuratie te valideren.

1. Voltooi de verificatie en selecteer **Opslaan**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian-verbindingsconfiguratievenster.":::

## <a name="enrichment-results"></a>Verrijkingsresultaten

Selecteer **Uitvoeren** vanaf de opdrachtbalk om het verrijkingsproces te starten. U kunt de verrijking ook automatisch laten uitvoeren als onderdeel van een [geplande vernieuwing](system.md#schedule-tab). De verwerkingstijd is afhankelijk van de omvang van uw klantgegevens en de verrijkingsprocessen die voor uw account zijn ingesteld door Experian.

Nadat het verrijkingsproces is voltooid, kunt u de nieuwe verrijkte klantprofielgegevens bekijken onder **Mijn verrijkingen**. Ook vindt u daar het tijdstip van de laatste update en het aantal verrijkte profielen.

U kunt een gedetailleerd overzicht van elk verrijkt profiel openen door **Verrijkte gegevens weergeven** te selecteren.

## <a name="next-steps"></a>Volgende stappen

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights inschakelt om gegevens te verzenden naar Experian, staat u de overdracht van gegevens buiten de nalevingsgrens toe voor Dynamics 365 Customer Insights, inclusief mogelijk gevoelige gegevens zoals persoonsgegevens. Microsoft zal dergelijke gegevens in uw opdracht overdragen, maar u bent er zelf verantwoordelijk voor dat Experian voldoet aan alle privacy- of beveiligingsverplichtingen die u hebt. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.
Uw Dynamics 365 Customer Insights-beheerder kan deze verrijking op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
