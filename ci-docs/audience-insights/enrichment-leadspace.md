---
title: Verrijking van bedrijfsprofielen met de verrijking door derden van Leadspace
description: Algemene informatie over de verrijking door derden van Leadspace.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 0db0c984f6bf9f7ded0704b6fa0caf39c7dace3a
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376778"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Verrijking van bedrijfsprofielen met Leadspace (preview)

Leadspace is een data science-bedrijf dat B2B-platform voor klantgegevens biedt. Het stelt omgevingen met geharmoniseerde klantprofielen op basis van accounts in staat om hun gegevens te verrijken. Verrijk *Klantprofielen* met kenmerken zoals bedrijfsgrootte, locatie of branche. Verrijk *Contactprofielen* met kenmerken zoals functie, persona of e-mailverificatie.

## <a name="prerequisites"></a>Vereisten

Als u Leadspace wilt configureren, moet aan de volgende vereisten worden voldaan:

- U hebt een actieve Leadspace-licentie.
- U hebt [geharmoniseerde klantprofielen](customer-profiles.md) op basis van accounts.
- Een Leadspace-verbinding is al geconfigureerd door een beheerder of u hebt [beheerdersmachtigingen](permissions.md#admin) en de "eeuwigdurende sleutel" (waarnaar wordt verwezen als **Leadspace-token**). Neem rechtstreeks contact op met [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) voor details over hun product.

## <a name="configure-the-enrichment"></a>De verrijking configureren

1. Ga in doelgroepinzichten naar **Gegevens** > **Verrijking**.

1. Selecteer **Mijn gegevens verrijken** op de tegel van Leadspace en selecteer vervolgens **Aan de slag**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Schermopname van de Leadspace-tegel.":::

1. Selecteer een [verbinding](connections.md) in de vervolgkeuzelijst. Neem contact op met een beheerder als er geen verbinding beschikbaar is. Als u een beheerder bent, kunt u een verbinding maken door **Verbinding toevoegen** te selecteren en **Leadspace** te kiezen. 

1. Selecteer **Verbinding maken met Leadspace** om de verbinding te bevestigen.

1. Selecteer **Volgende** en kies de **klantgegevensset** die u wilt verrijken met bedrijfsgegevens van Leadspace. U kunt de entiteit **Klant** selecteren om al uw klantprofielen te verrijken of een segmententiteit selecteren om alleen klantprofielen in dat segment te verrijken.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Schermopname bij het kiezen van de klantgegevensset.":::

1. Selecteer **Volgende** en bepaal welk type velden uit uw geharmoniseerde profielen worden gebruikt om overeenkomende bedrijfsgegevens van Leadspace te zoeken. Het veld **Naam van bedrijf** is verplicht. Voor een hogere matchnauwkeurigheid kunt u maximaal twee andere velden, **Bedrijfswebsite** en **Bedrijfslocatie** toevoegen.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Deelvenster Leadspace-veldtoewijzing.":::

1. Selecteer **Volgende** om de veldtoewijzing te voltooien.

1. Vink het selectievakje aan als u *Contactprofielen* hebt die u zou willen verrijken. Doelgroepinzichten koppelt automatisch de vereiste velden.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Verrijking van Leadspace-contactpersoonrecords.":::
 
1. Geef een naam op voor de verrijking en selecteer **Verrijking opslaan** na het bekijken van uw keuzes.


## <a name="configure-the-connection-for-leadspace"></a>De verbinding configureren voor Leadspace 

U moet een beheerder zijn om verbindingen te kunnen configureren. Selecteer **Verbinding toevoegen** bij het configureren van een verrijking *of* ga naar **Beheerder** > **Verbindingen** en selecteer **Instellen** op de Leadspace-tegel.

1. Selecteer **Aan de slag**. 

1. Voer een naam in voor de verbinding in het vak **Weergavenaam**.

1. Geef een geldig Leadspace-token op.

1. Bekijk en geef uw toestemming voor **Gegevensprivacy en naleving** door **Ik ga akkoord** te selecteren.

1. Selecteer **Verifiëren** om de configuratie te valideren.

1. Voltooi de verificatie en selecteer **Opslaan**.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Configuratiepagina voor Leadspace-verbinding.":::

## <a name="enrichment-results"></a>Verrijkingsresultaten

Nadat u de verrijking hebt vernieuwd, kunt u de nieuw verrijkte bedrijfsgegevens bekijken onder [Mijn verrijkingen](enrichment-hub.md). U kunt het tijdstip van de laatste update en het aantal verrijkte profielen terugvinden.

U kunt een gedetailleerd overzicht van elk verrijkt profiel openen door **Verrijkte gegevens weergeven** te selecteren.

Zie [De API's van Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API) voor meer informatie.

## <a name="next-steps"></a>Volgende stappen


[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar Leadspace te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat Leadspace voldoet aan uw privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.
Uw Dynamics 365 Customer Insights-beheerder kan deze verrijking op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
