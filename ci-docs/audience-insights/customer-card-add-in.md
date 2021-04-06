---
title: De invoegtoepassing Klantkaart installeren en configureren
description: Installeer en configureer de invoegtoepassing Klantkaart voor Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f3c4a01f9ce7749eeee72f7901620dae7cb9b8d3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597321"
---
# <a name="customer-card-add-in-preview"></a>Invoegtoepassing Klantkaart (preview)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Krijg een compleet overzicht van uw klanten rechtstreeks in Dynamics 365-apps. Bekijk demografische gegevens, inzichten en tijdlijnen van activiteiten met de invoegtoepassing Klantkaart.

## <a name="prerequisites"></a>Vereisten

- Dynamics 365-app (zoals Verkoophub of Klantenservicehub), versie 9.0 en hoger met Unified Interface ingeschakeld.
- Klantprofielen [opgenomen uit de Dynamics 365-app met Common Data Service](connect-power-query.md).
- Gebruikers van de invoegtoepassing Klantenkaart moeten [toegevoegd zijn als gebruikers](permissions.md) in doelgroepinzichten.
- [Geconfigureerde zoek- en filtermogelijkheden](search-filter-index.md).
- Demografische controle: demografische velden, zoals leeftijd of gender, zijn beschikbaar in het geharmoniseerde klantprofiel.
- Besturingselement voor verrijking: vereist dat actieve [verrijkingen](enrichment-hub.md) worden toegepast op klantprofielen.
- Informatiecontrole: vereist gegevens die zijn gegenereerd met Azure Machine Learning ([Voorspellingen](predictions.md) of [Aangepaste modellen](custom-models.md))
- Metingencontrole: vereist [geconfigureerde metingen](measures.md).
- Tijdlijncontrole: vereist [geconfigureerde activiteiten](activities.md).

## <a name="install-the-customer-card-add-in"></a>De invoegtoepassing Klantkaart installeren

De invoegtoepassing Klantkaart is een oplossing voor apps voor klantbetrokkenheid in Dynamics 365. Als u de oplossing wilt installeren, gaat u naar AppSource en zoekt u naar **Dynamics-klantkaart**. Selecteer de [invoegtoepassing Klantkaart in AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) en selecteer **Nu downloaden**.

Mogelijk moet u zich aanmelden met uw beheerdersreferenties voor de Dynamics 365-app om de oplossing te kunnen installeren.

Het kan enige tijd duren voordat de oplossing in uw omgeving is geïnstalleerd.

## <a name="configure-the-customer-card-add-in"></a>De invoegtoepassing Klantkaarten configureren

1. Ga als beheerder naar de sectie **Instellingen** in Dynamics 365 en selecteer **Oplossingen**.

1. Selecteer de koppeling **Weergavenaam** voor de oplossing **Dynamics 365 Customer Insights-invoegtoepassing KIantkaart (preview)**.

   > [!div class="mx-imgBorder"]
   > ![Weergavenaam selecteren](media/select-display-name.png "Weergavenaam selecteren")

1. Selecteer **Aanmelden** en voer de referenties in voor het beheerdersaccount dat u gebruikt om Customer Insights te configureren.

   > [!NOTE]
   > Controleer of de pop-upblokkering van de browser het verificatievenster niet blokkeert wanneer u de knop **Aanmelden** selecteert.

1. Selecteer de omgeving waaruit u gegevens wilt ophalen.

1. Definieer welke velden worden toegewezen aan records in de Dynamics 365-app.
   - Om toe te wijzen aan een contactpersoon, selecteert u het veld in de entiteit Klant die overeenkomt met de id van uw contactpersoon.
   - Om toe te wijzen aan een account, selecteert u het veld in de entiteit Klant die overeenkomt met de id van uw account-entiteit.

   > [!div class="mx-imgBorder"]
   > ![Veld Contactpersoon-id](media/contact-id-field.png "Veld Contactpersoon-id")

1. Selecteer **Configuratie opslaan** om de instellingen op te slaan.

1. Vervolgens moet u beveiligingsrollen toewijzen in Dynamics 365, zodat gebruikers de klantkaart kunnen aanpassen en zien. Ga in Dynamics 365 naar **Instellingen** > **Beveiliging** > **Gebruikers**. Selecteer de gebruikers om gebruikersrollen te bewerken en selecteer **Rollen beheren**.

1. Wijs de rol **'Aanpasser van Customer Insights-kaarten** toe aan gebruikers die de inhoud die op de kaart wordt weergegeven voor de hele organisatie aanpassen.

## <a name="add-customer-card-controls-to-forms"></a>Besturingselementen van Klantenkaart aan formulieren toevoegen
  
1. Als u de besturingselementen voor Klantkaart aan uw formulier Contactpersoon wilt toevoegen, gaat u naar **Instellingen** > **Aanpassingen** in Dynamics 365.

1. Selecteer **Het systeem aanpassen**.

1. Blader naar de entiteit **Contactpersoon**, vouw deze uit en selecteer vervolgens **Formulieren**.

1. Selecteer het contactpersoonformulier waaraan u de besturingselementen voor Klantkaart wilt toevoegen.

    > [!div class="mx-imgBorder"]
    > ![Contactpersoonformulier selecteren](media/contact-active-forms.png "Contactpersoonformulier selecteren")

1. Als u het demografische besturingselement wilt toevoegen, sleept u in de formuliereneditor een willekeurig veld vanuit de **Veldverkenner** naar de locatie waar u het demografische besturingselement wilt weergeven.

1. Selecteer het veld op het formulier dat u zojuist hebt toegevoegd en selecteer vervolgens **Eigenschappen wijzigen**.

1. Ga naar het tabblad **Besturingselementen** en selecteer **Besturingselement toevoegen**. Kies een van de beschikbare aangepaste bedieningselementen en selecteer **Toevoegen**.

1. Schakel in het dialoogvenster **Veldeigenschappen** het selectievakje **Label in het formulier weergeven** uit.

1. Selecteer de optie **Web** voor het besturingselement. Selecteer voor het besturingselement voor verrijking welk verrijkingstype u wilt weergeven door het veld **enrichmentType** te configureren. Voeg een afzonderlijk verrijkingsbesturingselement toe voor elk verrijkingstype.

1. Selecteer **Opslaan** en **Publiceren** om het bijgewerkte contactpersoonformulier te publiceren.

1. Ga naar het gepubliceerde contactpersoonformulier. U ziet nu het nieuw toegevoegde besturingselement. Mogelijk moet u zich aanmelden bij het eerste gebruik.

1. Als u wilt aanpassen wat u wilt weergeven op het aangepaste besturingselement, selecteert u de knop Bewerken in de rechterbovenhoek.

## <a name="upgrade-customer-card-add-in"></a>Invoegtoepassing Klantkaart upgraden
De invoegtoepassing Klantkaart wordt niet automatisch geüpgraded. Om te upgraden naar de nieuwste versie, volgt u deze procedure in de Dynamics 365-app waarop de invoegtoepassing is geïnstalleerd.

1. Ga in de Dynamics 365-app naar **Instellingen** > **Aanpassing** en selecteer **Oplossingen**.

1. Zoek in de tabel met invoegtoepassingen naar **CustomerInsightsCustomerCard** en selecteer de rij.

1. Selecteer **Oplossingsupgrade toepassen** op de actiebalk.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Upgrade de oplossing in het aanpassingsgebied van Dynamics 365-apps":::

1. Nadat u het upgradeproces hebt gestart, ziet u een laadindicator totdat de upgrade is voltooid. Als er geen nieuwere versie is, geeft de upgrade een foutmelding weer.


[!INCLUDE[footer-include](../includes/footer-banner.md)]