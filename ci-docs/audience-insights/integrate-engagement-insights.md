---
title: Webgegevens uit betrokkenheidsinzichten integreren met doelgroepinzichten
description: Breng webinformatie over klanten van betrokkenheidsinzichten naar doelgroepinzichten.
ms.date: 06/24/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2789a7d1379e0cf56511b272a763c904d8a3d347058ea9e029aaff0f723a028
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033763"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>Webgegevens uit betrokkenheidsinzichten integreren met doelgroepinzichten

Klanten voeren hun dagelijkse transacties vaak online uit via websites. De mogelijkheid voor betrokkenheidsinzichten (preview) in Dynamics 365 Customer Insights is een handige oplossing om webgegevens als bron te integreren. Naast transactionele, demografische of gedragsgegevens kunnen we activiteiten op het internet zien in geharmoniseerde klantprofielen. We kunnen deze profielen gebruiken om aanvullende inzichten te verwerven, zoals segmenten, metingen of voorspellingen voor doelgroepactivering.

In dit artikel worden de stappen beschreven om de webactiviteitsgegevens van uw klanten uit betrokkenheidsinzichten over te brengen naar uw bestaande omgeving voor doelgroepinzichten.

In dit voorbeeld gaan we uit van een omgeving die geharmoniseerde klantprofielen bevat. De profielen zijn geharmoniseerd met bronnen uit enquêtes, winkelverkopen en een ticketsysteem. Het toont ook de gerelateerde activiteiten van de klanten. 

We willen nu weten of een klant onze webeigendommen bezoekt en hun activiteiten begrijpen. Activiteiten omvatten bijvoorbeeld bezochte websites of bekeken productpagina's via een link die in een e-mail is ontvangen.

## <a name="prerequisites"></a>Vereisten

Om gegevens uit betrokkenheidsinzichten te integreren, moet aan een aantal voorwaarden worden voldaan: 

- Integreer de SDK voor betrokkenheidsinzichten met uw website. Zie [Overzicht van resources voor ontwikkelaars](../engagement-insights/developer-resources.md) voor meer informatie.
- Voor het exporteren van webgebeurtenissen uit betrokkenheidsinzichten is toegang tot een Azure Data Lake Storage-account vereist dat zal worden gebruikt om de webgebeurtenisgegevens op te nemen in doelgroepinzichten. Zie [Gebeurtenissen exporteren](../engagement-insights/export-events.md) voor meer informatie.

## <a name="configure-refined-events-in-engagement-insights"></a>Verfijnde gebeurtenissen configureren in betrokkenheidsinzichten

Nadat een beheerder een website heeft geïnstrumenteerd met de SDK voor betrokkenheidsinzichten, worden *basisgebeurtenissen* verzameld wanneer een gebruiker een webpagina bekijkt of ergens op klikt. Basisgebeurtenissen bevatten meestal talloze details. Afhankelijk van uw gebruiksscenario hebt u slechts een subset van de gegevens in een basisgebeurtenis nodig. Met betrokkenheidsinzichten kunt u *verfijnde gebeurtenissen* maken die alleen de eigenschappen bevatten van een basisgebeurtenis die u selecteert.     

Zie [Verfijnde gebeurtenissen maken en wijzigen](../engagement-insights/refined-events.md)​voor meer informatie.

Overwegingen bij het maken van verfijnde evenementen: 

- Geef een betekenisvolle naam voor de verfijnde gebeurtenis. Het wordt gebruikt als een activiteitsnaam in doelgroepinzichten.
- Selecteer ten minste de volgende eigenschappen om een activiteit te maken in doelgroepinzichten: 
    - Signal.Action.Name – geeft de activiteitsdetails aan.
    - Signal.User.Id – gebruikt om toe te wijzen met de klant-id,
    - Signal.View.Uri – wordt gebruikt als een webadres als basis voor segmenten of metingen.
    - Signal.Export.Id – gebruikt als primaire sleutel voor gebeurtenissen.
    - Signal.Timestamp – bepaalt de datum en tijd voor de activiteit.

Selecteer de filters om u te concentreren op de gebeurtenissen en pagina's die voor uw situatie van belang zijn. In dit voorbeeld gebruiken we de actienaam 'e-mailpromotie'.

## <a name="export-the-refined-web-events"></a>De verfijnde webgebeurtenissen exporteren 

Na het definiëren van de verfijnde gebeurtenis, moet u de export van de gebeurtenisgegevens configureren voor Azure Data Lake Storage, dat kan worden ingesteld als een gegevensbron voor opname in doelgroepinzichten. Exporteren vindt constant plaats terwijl de gebeurtenissen uit het webeigendom stromen.

Zie [Gebeurtenissen exporteren](../engagement-insights/export-events.md) voor meer informatie.

## <a name="ingest-event-data-to-audience-insights"></a>Gebeurtenisgegevens opnemen in doelgroepinzichten

Nu u de verfijnde gebeurtenis hebt gedefinieerd en de export ervan hebt geconfigureerd, gaan we de gegevens opnemen in doelgroepinzichten. U moet een nieuwe gegevensbron maken op basis van een Common Data Model-map. Voer de details in voor het opslagaccount waarnaar u de gebeurtenissen exporteert. Selecteer in het bestand *default.cdm.json* de verfijnde gebeurtenis die u wilt opnemen en maak de entiteit in doelgroepinzichten.

Zie [Verbinding maken met een Common Data Model-map met behulp van een Azure Data Lake-account](connect-common-data-model.md) voor meer informatie.


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>Verfijnde gebeurtenisgegevens relateren als een activiteit van een klantprofiel

Nadat de opname van de entiteit is voltooid, kunt u de activiteit voor het klantprofiel configureren.

Zie [Klantactiviteiten](activities.md) voor meer informatie.

:::image type="content" source="media/web-event-activity.png" alt-text="Activiteitenpagina met uitgevouwen activiteitenvenster Bewerken en ingevulde velden.":::

Configureer de nieuwe activiteit met de volgende toewijzingen: 

- **Primaire sleutel**: Signal.Export.Id, een unieke id die beschikbaar is voor elke gebeurtenisrecord in betrokkenheidsinzichten. Deze eigenschap wordt automatisch gegenereerd.

- **Tijdstempel**: Signal.Timestamp in de gebeurteniseigenschap.

- **Gebeurtenis**: Signal.Name, de naam van de gebeurtenis die u wilt volgen.

- **webadres**: Signal.View.Uri verwijst naar de URI van de pagina die de gebeurtenis heeft gemaakt.

- **Details**: Signal.Action.Name om de informatie weer te geven die aan de gebeurtenis moet worden gekoppeld. De geselecteerde eigenschap geeft in dit geval aan dat de gebeurtenis bedoeld is voor e-mailpromotie.

- **Activiteitstype**: in dit voorbeeld kiezen we voor het bestaande activiteitstype WebLog. Deze selectie is een handige filteroptie om voorspellingsmodellen uit te voeren of segmenten te maken op basis van dit activiteitstype.

- **Relatie instellen**: deze belangrijke instelling koppelt de activiteit aan bestaande klantprofielen. **Signal.User.Id** is de id die is geconfigureerd in de te verzamelen SDK en die betrekking heeft op de gebruikers-id in andere gegevensbronnen die zijn geconfigureerd in doelgroepinzichten. In dit voorbeeld configureren we de relatie tussen Signal.User.Id en RetailCustomers:CustomerRetailId, de primaire sleutel die werd geïdentificeerd in de toewijzingsstap van het gegevensharmonisatieproces.

Nadat de activiteiten zijn verwerkt, kunt u klantrecords beoordelen en een klantenkaart openen om activiteiten te zien vanuit betrokkenheidsinzichten in de tijdlijn. 

> [!TIP]
> Als u een klant-id wilt vinden die een activiteit voor betrokkenheidsinzichten heeft, gaat u naar **Entiteiten** en bekijkt u een voorbeeld van de gegevens voor de entiteit UnifiedActivity. ActivityTypeDisplay = WebLog bevat de betrokkenheidsinzichtenactiviteit die in het bovenstaande voorbeeld is geconfigureerd. Kopieer de klant-id voor een van die records en voor de id op de pagina **Klanten**.

## <a name="next-steps"></a>Volgende stappen

U kunt nu [segmenten](segments.md), [metingen](measures.md) en [voorspellingen](predictions.md) maken om een zinvolle verbinding te maken met uw klanten.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
