---
title: FAQ proefversie - Dynamics 365 Customer Insights
description: Oplossingen voor veelgestelde vragen over de installatie en het beheer van de proefversie van Customer Insights. Meer informatie over het oplossen van platform- en app-specifieke problemen.
author: m-hartmann
ms.author: mhart
ms.date: 02/10/2022
ms.topic: get-started
ms.custom: template-trial-faq
ms.reviewer: jeffhar
manager: shellyha
ms.openlocfilehash: 9badd8370358b9f5745ba6347e8db42e89c5f3d3
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229489"
---
# <a name="dynamics-365-customer-insights-trial-faq"></a>Veelgestelde vragen over de proefversie van Dynamics 365 Customer Insights

## <a name="sign-up"></a>Registreren

### <a name="what-are-the-system-requirements-for-the-trial"></a>Wat zijn de systeemvereisten voor de proefversie?

Deze app is een cloudservice waarvoor geen andere software op de computers van gebruikers hoeft te zijn geïnstalleerd dan een bijgewerkte webbrowser, hoewel er enkele beperkingen gelden. Voor de beste ervaring met de proefversie raden we af de proefsite te benaderen in de incognitomodus en kiest u het best de proeflocatie die het dichtst bij u in de buurt is. [Meer informatie over vereisten voor webtoepassingen.](/power-platform/admin/web-application-requirements)

### <a name="how-do-i-sign-up-for-the-trial-without-a-microsoft-365-tenant"></a>Hoe meld ik me aan voor de proefversie zonder een Microsoft 365-tenant?

U kunt een niet-zakelijk e-mailadres invoeren en wij maken een account en tenant voor u aan.

### <a name="can-i-sign-up-for-multiple-dynamics-365-apps-such-as-sales-marketing-and-customer-service"></a>Kan ik me registreren voor meerdere Dynamics 365-apps, zoals Sales, Marketing en Customer Service?

Ja, dat kan. Als u alle beschikbare proefversies wilt bekijken, [gaat u naar de hubpagina voor proefversies](https://dynamics.microsoft.com/dynamics-365-free-trial). U kunt hetzelfde e-mailaccount gebruiken om u te registreren voor verschillende proefversies. Het is echter niet mogelijk om meerdere apps op dezelfde proefsite te hebben. Elke proefversie heeft een andere organisatie en URL. De proefgegevens worden niet gedeeld tussen apps.

## <a name="trial-app"></a>Proef-app

### <a name="i-didnt-receive-the-trial-details-email-after-signing-up-what-should-i-do"></a>Ik heb de e-mail met de proefgegevens niet ontvangen nadat ik me heb aangemeld, wat moet ik doen?

Wanneer u zich registreert voor de proefversie, ontvangt u een e-mail met de details van de proefversie. Als u de e-mail niet in uw Postvak IN ziet, controleert u uw spammap. U kunt ook de volgende stappen gebruiken om toegang te krijgen tot uw app:

1. Ga naar de proefsite en selecteer **Probeer het gratis uit**.
1. Voer de e-mail-id in die u hebt gebruikt om u te registreren voor de proefversie. U wordt omgeleid naar uw proef-app.

### <a name="how-do-i-add-more-users-to-a-trial"></a>Hoe voeg ik meer gebruikers toe aan een proefversie?

Als u gebruikers wilt toevoegen, gaat u naar het [Microsoft 365-beheercentrum](https://admin.microsoft.com) met het proefbeheeraccount. Volg de [richtlijnen van het beheercentrum](/microsoft-365/admin/add-users/add-users) om gebruikers toe te voegen tot de limiet voor proeflicenties. Als de gebruiker die u toevoegt al een Microsoft 365-account heeft, wijst u aan hem of haar een geschikte beveiligingsrol toe in de proeforganisatie. Zie [Een beveiligingsrol toewijzen aan een gebruiker](/power-platform/admin/create-users-assign-online-security-roles#assign-a-security-role-to-a-user) voor meer informatie.

### <a name="how-many-users-can-i-add-to-my-trial-environment"></a>Hoeveel gebruikers kan ik toevoegen aan mijn proefomgeving?

U kunt een onbeperkt aantal gebruikers aan de proefomgeving toevoegen.

### <a name="how-do-i-reset-the-trial-environment"></a>Hoe stel ik de proefomgeving opnieuw in?

U kunt de proefomgeving niet opnieuw instellen. U kunt wel wachten tot de proefperiode is verstreken en u vervolgens opnieuw registeren voor een nieuwe proefversie.

## <a name="trial-expiration-and-extension"></a>Verloop en verlenging van proefversie

### <a name="how-do-i-extend-the-trial"></a>Hoe verleng ik de proefversie?

U kunt de proefperiode direct in de app verlengen. U kunt uw proefperiode één keer verlengen.

### <a name="can-i-convert-the-trial-to-a-paid-license"></a>Kan ik de proefversie omzetten in een betaalde licentie?

Over het algemeen raden we aan opnieuw te beginnen met uw eigen gegevens bij het upgraden naar de betaalde versie van Customer Insights. 

Optioneel, als u alleen doelgroepinzichten gebruikt, kunt u uw gegevens vanuit een proefomgeving kopiëren als u Customer Insights aanschaft. U moet de beheerder van de Customer Insights-proefversie en de globale beheerder van uw Microsoft 365-tenant zijn, of de Dynamics 365-beheerder in uw organisatie, om de instellingen van een proefomgeving naar een betaalde omgeving te kunnen migreren. 

Nadat u voor de eerste keer bent ingelogd op uw betaalde exemplaar van Customer Insights, wordt u gevraagd een nieuwe omgeving te maken. In dit proces kunt u ervoor kiezen de configuratie uit een bestaande omgeving te kopiëren en de meeste instellingen te migreren. Als u de hierboven genoemde machtigingen hebt, wordt de proefomgeving in deze lijst weergegeven. Zie [De omgevingsconfiguratie kopiëren](audience-insights/manage-environments.md#copy-the-environment-configuration) voor meer informatie.

### <a name="what-are-the-trial-limits-and-quotas"></a>Wat zijn de limieten en targets voor de proefversie?

- U kunt uw eigen Azure Data Lake Storage-account niet gebruiken om uitvoergegevens op te slaan tijdens de proef van doelgroepinzichten. U kunt echter gegevens van een Data Lake-opslagaccount opnemen.
- U kunt maximaal 3 GB aan gegevens opslaan in de Dataverse-omgeving die automatisch wordt ingericht wanneer u een proefversie van Customer Insights start.

## <a name="customer-insights-specific-questions"></a>Specifieke vragen over Customer Insights

### <a name="how-do-i-start-using-the-trial"></a>Hoe ga ik aan de slag met de proefversie?

Nadat u zich hebt geregistreerd voor de proefversie, komt u terecht in het hoofdscherm van de app. Het hoofdscherm bevat koppelingen naar gebruikershandleidingen en zelfstudies. Volg voor meer informatie de koppelingen in het gedeelte [Aanvullende bronnen](trial-signup.md#additional-resources) op de registratiepagina voor de proefversie.

### <a name="what-features-are-available-in-the-trial"></a>Welke functies zijn beschikbaar in de proefversie?

De meeste functies van Customer Insights zijn beschikbaar in de proefversie.

De volgende functies zijn **niet beschikbaar**: 
- U kunt geen nieuwe omgevingen maken die uw eigen Azure Data Lake Storage-account gebruiken.
- U kunt de proefomgeving niet verwijderen. 

### <a name="how-long-does-the-trial-last"></a>Hoe lang duurt de proefversie?

De proefperiode van Customer Insights duurt 30 dagen. U kunt de proefperiode na 23 dagen eenmalig verlengen wanneer u inlogt op uw proefomgeving.

### <a name="how-do-i-remove-sample-data-from-the-trial"></a>Hoe verwijder ik voorbeeldgegevens uit de proefversie?

U kunt de voorbeeldgegevens niet verwijderen uit de proefversie.
