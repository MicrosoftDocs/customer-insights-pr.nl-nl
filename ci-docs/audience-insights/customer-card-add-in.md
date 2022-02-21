---
title: Invoegtoepassing Klantkaart voor Dynamics 365-app (met video)
description: Geef gegevens van doelgroepinzichten weer in Dynamics 365-apps met deze invoegtoepassing.
ms.date: 02/02/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: ce6c8fab84fd4c5dfc9f78b91dde3483a1d358c1
ms.sourcegitcommit: 11308ed275b4b25a35576eccfcae9dda9e2c2784
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/02/2022
ms.locfileid: "8085209"
---
# <a name="customer-card-add-in-preview"></a>Invoegtoepassing Klantkaart (preview)



Krijg een compleet overzicht van uw klanten rechtstreeks in Dynamics 365-apps. Als de invoegtoepassing Klantkaart is geïnstalleerd in een ondersteunde Dynamics 365-app, kunt u ervoor kiezen om klantprofielvelden, inzichten en activiteitentijdlijn weer te geven. Met de invoegtoepassing worden gegevens opgehaald uit Customer Insights zonder dat dit invloed heeft op de gegevens in de verbonden Dynamics 365-app.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Vereisten

- De invoegtoepassing werkt alleen met modelgestuurde Dynamics 365-apps, zoals Sales of Customer Service, versie 9.0 en hoger.
- Voor toewijzing van uw Dynamics 365-gegevens aan de klantprofielen van doelgroepinzichten raden we aan ze [op te nemen vanuit de Dynamics 365-app met behulp van de Microsoft Dataverse-connector](connect-power-query.md). Als u een andere methode gebruikt om Dynamics 365-contactpersonen (of -accounts) op te nemen, moet u ervoor zorgen dat het veld `contactid` (of `accountid`) is ingesteld als de [primaire sleutel voor die gegevensbron in de kaartstap van het gegevensharmonisatieproces ](map-entities.md#select-primary-key-and-semantic-type-for-attributes). 
- Alle Dynamics 365-gebruikers van de invoegtoepassing Klantkaart moeten worden [toegevoegd als gebruikers](permissions.md) in doelgroepinzichten om de gegevens te zien.
- [Geconfigureerde zoek- en filtermogelijkheden](search-filter-index.md) in doelgroepinzichten zijn vereist voor het opzoeken van gegevens.
- Elk besturingselement van de invoegtoepassing is afhankelijk van specifieke gegevens in doelgroepinzichten. Sommige gegevens en besturingselementen zijn alleen beschikbaar in omgevingen van specifieke typen. De configuratie van de invoegtoepassing zal u informeren als een besturingselement niet beschikbaar is vanwege het geselecteerde omgevingstype. Meer informatie over [gebruiksscenario's en omgevingen](work-with-business-accounts.md).
  - **Metingcontrole**: hiervoor zijn [geconfigureerde metingen](measures.md) van het type klantkenmerken vereist.
  - **Informatiebeheer**: vereist gegevens die zijn gegenereerd met [voorspellingen of aangepaste modellen](predictions-overview.md).
  - **Controle klantgegevens**: alle velden uit het profiel zijn beschikbaar in het geharmoniseerde klantprofiel.
  - **Besturingselement voor verrijking**: vereist dat actieve [verrijkingen](enrichment-hub.md) worden toegepast op klantprofielen. De kaart invoegtoepassing ondersteunt deze verrijkingen: [Merken](enrichment-microsoft.md) geleverd door Microsoft, [Interesses](enrichment-microsoft.md) geleverd door Microsoft en [Betrokkenheidsgegevens kantoor](enrichment-office.md) geleverd door Microsoft.
  - **Controle contactpersonen**: hiervoor is de definitie van de semantische entiteit van het type contactpersonen vereist.
  - **Tijdlijncontrole**: vereist [geconfigureerde activiteiten](activities.md).

## <a name="install-the-customer-card-add-in"></a>De invoegtoepassing Klantkaart installeren

De invoegtoepassing Klantkaart is een oplossing voor apps voor klantbetrokkenheid in Dynamics 365. Als u de oplossing wilt installeren, gaat u naar AppSource en zoekt u naar **Dynamics-klantkaart**. Selecteer de [invoegtoepassing Klantkaart in AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) en selecteer **Nu downloaden**.

Mogelijk moet u zich aanmelden met uw beheerdersreferenties voor de Dynamics 365-app om de oplossing te kunnen installeren. Het kan enige tijd duren voordat de oplossing in uw omgeving is geïnstalleerd.

## <a name="configure-the-customer-card-add-in"></a>De invoegtoepassing Klantkaarten configureren

1. Ga als beheerder naar de sectie **Instellingen** in Dynamics 365 en selecteer **Oplossingen**.

1. Selecteer de koppeling **Weergavenaam** voor de oplossing **Dynamics 365 Customer Insights-invoegtoepassing KIantkaart (preview)**.

   > [!div class="mx-imgBorder"]
   > ![Weergavenaam selecteren.](media/select-display-name.png "Weergavenaam selecteren.")

1. Selecteer **Aanmelden** en voer de referenties in voor het beheerdersaccount dat u gebruikt om Customer Insights te configureren.

   > [!NOTE]
   > Controleer of de pop-upblokkering van de browser het verificatievenster niet blokkeert wanneer u de knop **Aanmelden** selecteert.

1. Selecteer de Customer Insights-omgeving waaruit u gegevens wilt ophalen.

1. Definieer de veldtoewijzing aan records in de Dynamics 365-app. Afhankelijk van uw gegevens in Customer Insights kunt u ervoor kiezen om de volgende opties toe te wijzen:
   - Om toe te wijzen aan een contactpersoon, selecteert u het veld in de entiteit Klant die overeenkomt met de id van uw contactpersoon.
   - Om toe te wijzen aan een account, selecteert u het veld in de entiteit Klant die overeenkomt met de id van uw account-entiteit.

   > [!div class="mx-imgBorder"]
   > ![Veld Contactpersoon-id.](media/contact-id-field.png "Veld Contactpersoon-id.")

1. Selecteer **Configuratie opslaan** om de instellingen op te slaan.

1. Vervolgens moet u beveiligingsrollen toewijzen in Dynamics 365, zodat gebruikers de klantkaart kunnen aanpassen en zien. Ga in Dynamics 365 naar **Instellingen** > **Beveiliging** > **Gebruikers**. Selecteer de gebruikers om gebruikersrollen te bewerken en selecteer **Rollen beheren**.

1. Wijs de rol **'Aanpasser van Customer Insights-kaarten** toe aan gebruikers die de inhoud die op de kaart wordt weergegeven voor de hele organisatie aanpassen.

## <a name="add-customer-card-controls-to-forms"></a>Besturingselementen van Klantenkaart aan formulieren toevoegen

Afhankelijk van uw scenario kunt u ervoor kiezen om bedieningselementen toe te voegen aan het formulier **Contactpersoon** of **Account**. Als uw omgeving doelgroepinzichten voor zakelijke accounts is, raden we u aan de bedieningselementen toe te voegen aan het formulier Account. Vervang in dat geval "contactpersoon" in de onderstaande stappen door "account".

1. Als u de besturingselementen voor Klantkaart aan uw formulier Contactpersoon wilt toevoegen, gaat u naar **Instellingen** > **Aanpassingen** in Dynamics 365.

1. Selecteer **Het systeem aanpassen**.

1. Blader naar de entiteit **Contactpersoon**, vouw deze uit en selecteer vervolgens **Formulieren**.

1. Selecteer het contactpersoonformulier waaraan u de besturingselementen voor de klantkaart wilt toevoegen.

    > [!div class="mx-imgBorder"]
    > ![Contactpersoonformulier selecteren.](media/contact-active-forms.png "Contactpersoonformulier selecteren.")

1. Als u het demografische besturingselement wilt toevoegen, sleept u in de formuliereneditor een willekeurig veld vanuit de **Veldverkenner** naar de locatie waar u het demografische besturingselement wilt weergeven.

1. Selecteer het veld op het formulier dat u zojuist hebt toegevoegd, en selecteer vervolgens **Eigenschappen wijzigen**.

1. Ga naar het tabblad **Besturingselementen** en selecteer **Besturingselement toevoegen**. Kies een van de beschikbare aangepaste bedieningselementen en selecteer **Toevoegen**.

1. Schakel in het dialoogvenster **Veldeigenschappen** het selectievakje **Label in het formulier weergeven** uit.

1. Selecteer de optie **Web** voor het besturingselement. Selecteer voor het besturingselement voor verrijking welk verrijkingstype u wilt weergeven door het veld **enrichmentType** te configureren. Voeg een afzonderlijk verrijkingsbesturingselement toe voor elk verrijkingstype.

1. Selecteer **Opslaan** en **Publiceren** om het bijgewerkte contactpersoonformulier te publiceren.

1. Ga naar het gepubliceerde contactpersoonformulier. U ziet nu het nieuw toegevoegde besturingselement. Mogelijk moet u zich aanmelden bij het eerste gebruik.

1. Als u wilt aanpassen wat u wilt weergeven op het aangepaste besturingselement, selecteert u de knop Bewerken in de rechterbovenhoek.

## <a name="upgrade-customer-card-add-in"></a>Invoegtoepassing Klantkaart upgraden

De invoegtoepassing Klantkaart wordt niet automatisch geüpgraded. Om te upgraden naar de meest recente versie, volgt u deze stappen in de Dynamics 365-app waarop de invoegtoepassing is geïnstalleerd.

1. Ga in de Dynamics 365-app naar **Instellingen** > **Aanpassing** en selecteer **Oplossingen**.

1. Zoek in de tabel met invoegtoepassingen naar **CustomerInsightsCustomerCard** en selecteer de rij.

1. Selecteer **Oplossingsupgrade toepassen** op de actiebalk.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Upgrade de oplossing in het aanpassingsgebied van Dynamics 365-apps.":::

1. Nadat u het upgradeproces hebt gestart, ziet u een laadindicator totdat de upgrade is voltooid. Als er geen nieuwere versie is, geeft de upgrade een foutmelding weer.

## <a name="troubleshooting"></a>Probleemoplossing

### <a name="controls-from-customer-card-add-in-dont-find-data"></a>Besturingselementen van de invoegtoepassing Klantkaart vinden geen gegevens

**Probleem:**

Zelfs met correct geconfigureerde id-velden kunnen de besturingselementen voor geen enkele klant gegevens vinden.  

**Oplossing:**

1. Zorg ervoor dat u de invoegtoepassing hebt geconfigureerd volgens de instructies: [De invoegtoepassing Klantkaart configureren](#configure-the-customer-card-add-in) 

1. Bekijk de configuratie van de gegevensopname. Bewerk de gegevensbron voor het Dynamics 365-systeem dat de GUID van de contactpersoon-id bevat. Als de GUID van de contactpersoon-id wordt weergegeven in hoofdletters in de Power Query-editor, probeert u het volgende: 
    1. Bewerk de gegevensbron om de gegevensbron te openen in de Power Query-editor.
    1. Selecteer de kolom voor de contactpersoon-id.
    1. Selecteer **Transformeren** in de koptekstbalk om beschikbare acties te zien.
    1. Selecteer **kleine letters**. Valideer of GUID's in de tabel nu in kleine letters zijn.
    1. Sla de gegevensbron op.
    1. Voer gegevensopname, harmonisatie en downstreamprocessen uit om de wijzigingen in de GUID door te voeren. 

Nadat de volledige vernieuwing is voltooid, moeten de besturingselementen van de invoegtoepassing Klantenkaart de verwachte gegevens weergeven. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
