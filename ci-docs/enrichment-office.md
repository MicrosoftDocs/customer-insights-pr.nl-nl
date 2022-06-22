---
title: Klantprofielen verrijken met gegevens vanuit Microsoft Office 365
description: Gebruik gebruikseigen gegevens van Microsoft Office om uw klantprofielen te verrijken met contactgegevens.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 7192b7680e73a581dd603de174c57b20bec996dd
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954127"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Klantprofielen verrijken met contactgegevens (preview)

Gebruik gegevens van Microsoft Office 365 om uw klantaccountprofielen te verrijken met inzichten over contacten via Office 365-apps. De contactgegevens bestaan uit e-mail- en vergaderactiviteiten, die op accountniveau worden geaggregeerd. Bijvoorbeeld het aantal e-mails van een zakelijk account of het aantal vergaderingen met het account. Er worden geen gegevens over individuele gebruikers beschikbaar gesteld.

## <a name="supported-countries-or-regions"></a>Ondersteunde landen of regio's

We ondersteunen momenteel de volgende regio's: VK, Europa, Noord-Amerika.

## <a name="prerequisites"></a>Vereisten

- Een actie Office 365-cloudlicentie.
- [Geharmoniseerde klantprofielen](customer-profiles.md) op basis van [zakelijke accounts](work-with-business-accounts.md).
- Een [Microsoft Dataverse-organisatie toegevoegd](create-environment.md#step-3-connect-to-microsoft-dataverse) in uw Customer Insights-omgeving.
- [Beheerders](permissions.md#admin)machtigingen.
- Toestemming van de beheerder van uw Office 365-tenant, om Office 365-gegevens te gebruiken om **Inzichten voor de organisatie** binnen Dynamics 365-toepassingen te verstrekken.

## <a name="configure-the-enrichment"></a>De verrijking configureren

1. Ga naar **Gegevens** > **Verrijking** en selecteer het tabblad **Detecteren**.

1. Selecteer **Mijn gegevens verrijken** op de tegel **Accountbetrokkenheid**.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Tegel Accountbetrokkenheid.":::

1. Bekijk het overzicht en selecteer **Volgende**.

1. Voer e-mailadressen van uw organisatie in waarvoor Office-gegevens worden gecombineerd. Alleen gegevens van de vermelde e-mailadressen worden verwerkt voor relevante communicatie. Een best practice is om e-mailgroepen te gebruiken, bijvoorbeeld *Amerikaans verkoopteam*, die u kunt beheren in Office 365. Het aantal e-mailadressen in de groepen wordt opgelost en weergegeven. Het totale aantal e-mailadressen moet minimaal 2 bedragen en mag niet groter zijn dan 2500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="E-mailadressen voor accountbetrokkenheid.":::

1. Bekijk en geef uw toestemming voor [Toestemming van Office 365-tenantbeheerder](#office-365-tenant-administrator-consent) door **Ik ga akkoord** te selecteren.

1. Selecteer **Volgende**.

1. Selecteer de **Contactgegevensset** en kies het profiel dat u wilt verrijken. Selecteer **Volgende**.

1. Wijs het veld voor het e-mailadres van de contactpersoon toe en selecteer **Volgende**.

1. Geef een **naam** op voor de verrijking en de **uitvoerentiteit**.

1. Selecteer **Verrijking opslaan** na het bekijken van uw keuzes.

1. Selecteer **Sluiten** om terug te keren naar de pagina **Verrijkingen**.

### <a name="office-365-tenant-administrator-consent"></a>Toestemming van Office 365-tenantbeheerder

Toestemming van een Office 365-tenantbeheerder is vereist om de verrijking te activeren. Er wordt een e-mail naar de Office 365-tenantbeheerders gestuurd wanneer de verrijking is opgeslagen, waarin hen wordt gevraagd om te controleren en toestemming te geven om Dynamics 365-toepassingen toe te staan de Office 365-gegevens van uw onderneming te gebruiken voor het bieden van **Inzichten voor de organisatie**. De Office 365-tenantbeheerder kan ook rechtstreeks toestemming geven in hun Office 365-beheerdersconsole door **Inzichten voor de organisatie** te selecteren.

## <a name="running-the-enrichment-for-the-first-time"></a>De verrijking voor het eerst uitvoeren

Wanneer de verrijking voor het eerst wordt gestart, begint het downloaden van gegevens vanuit Office 365 nadat de Office 365-tenantbeheerder toestemming heeft gegeven. Dit proces neemt enige tijd in beslag. De eerste verrijkingsuitvoering zal plaatsvinden met een vertraging van zes uur. U kunt het aantal dagen zien dat de gegevens beslaan op de overzichtspagina voor accountbetrokkenheid nadat de verrijking is voltooid. Voer bij een groot datavolume de verrijking na een paar dagen opnieuw uit. Dit zorgt ervoor dat de gegevens compleet zijn voor het hele tijdvenster, dat een jaar bedraagt.

Afhankelijk van de grootte van uw Office-gegevens kan het enkele uren duren voordat een verrijkingsuitvoering is voltooid.

Wanneer u een verrijking uitvoert, verwerkt Microsoft de gegevens binnen de Office 365-nalevingsgrens om geaggregeerde inzichten te creëren, die vervolgens worden toegevoegd aan uw Customer Insights-omgeving. Er komen geen gegevens op individueel niveau (bijvoorbeeld de hoofdtekst van een e-mail of agenda-uitnodiging) beschikbaar voor gebruikers van Customer Insights.

Selecteer **Uitvoeren** om het verrijkingsproces te starten.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Verrijkingsresultaten

[!INCLUDE [enrichment-results](includes/enrichment-results.md)] Dit is de *Office*-entiteit. De *Office_UserEntity* bevat de Active Directory-id's voor de e-mailadressen die zijn gekozen tijdens de verrijkingsconfiguratie.

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Voorbeeldweergave van resultaten na het uitvoeren van het verrijkingsproces.":::

Alle gegevens worden geaggregeerd tot op accountniveau. Het systeem berekent voor elk account een betrokkenheidsscore, variërend van 0 tot 100. De betrokkenheidsscore biedt een samengesteld meetcriterium voor de accountbetrokkenheid bij e-mails en vergaderingen ten opzichte van uw andere accounts. De volgende lijst bevat de geaggregeerde gegevens die de verrijking voor accountbetrokkenheid biedt:

| 'Gegevens                                                                              | Kolomnaam                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Contactscore                                                                  |  EngagementScore                         |
| Aantal e-mails naar account                                                       |  NoOfEmails_ToAccount                    |
| Aantal e-mails van account                                                     |  NoOfEmails_FromAccount                  |
| Aantal vergaderingen dat door account is geïnitieerd                                           |  NoOfMeetings_FromAccount                |
| Aantal vergaderingen dat door uw organisatie is geïnitieerd                                 |  NoOfMeetings_ToAccount                  |
| Aantal mensen van uw organisatie in vergaderingen met account                  |  NoOfContactsInvolved_Meetings           |
| Aantal mensen van uw organisatie in e-mailgesprekken met account       |  NoOfContactsInvolved_Emails             |
| Aantal mensen van account in vergaderingen met uw organisatie                  |  NoOfAccountContactsInvolved_Meetings    |
| Aantal mensen van account in e-mailgesprekken met uw organisatie       |  NoOfAccountContactsInvolved_Emails      |
| Begindatum betrokkenheid (eerste e-mail of vergadering in de gegevens)                        |  EngagementStartDate                     |
| Dagen sinds laatste e-mail                                                             |  DaysSinceLastEmail                      |
| Dagen sinds laatste vergadering                                                           |  DaysSinceLastMeeting                    |
| Gemiddelde duur van vergaderingen                                                      |  AverageDuration_Of_Meetings             |
| Gemiddelde duur van e-mailantwoorden van account                                    |  AverageDuration_Of_AccountEmailReplies  |
| Begindatum van aggregatie                                                            |  AggregationStartDate                    |
| Aggregatieniveau (jaar, maand of week)                                          |  AggregationLevel                        |

## <a name="see-enrichment-data-on-the-customer-card"></a>Zie verrijkingsgegevens op de klantenkaart

Accountbetrokkenheid kan ook worden bekeken op individuele klantenkaarten. Ga naar **Klanten** en selecteer een klantprofiel. Op de klantenkaart vindt u de betrokkenheidsscore van het account, het totale aantal e-mails en het totale aantal vergaderingen van het afgelopen jaar. U vindt er ook grafieken die de e-mail- en vergaderingsgeschiedenis weergeven.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Klantenkaart met verrijkte gegevens.":::

## <a name="next-steps"></a>Volgende stappen

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]
Bijvoorbeeld een segment dat alle klanten bevat met een waarde van meer dan 60 voor *dagen sinds laatste e-mail* en *dagen sinds de laatste vergadering*. Dat segment bevat verouderde accounts die u kunt proberen opnieuw te activeren.

[!INCLUDE [footer-include](includes/footer-banner.md)]
