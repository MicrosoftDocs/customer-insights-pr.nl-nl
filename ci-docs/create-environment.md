---
title: 'Procedure: Een nieuwe omgeving maken'
description: Stappen om omgevingen te maken in Dynamics 365 Customer Insights.
ms.date: 05/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 875cbbd095dfd239ab83c1c80db28ea7c0a04ed0
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245551"
---
# <a name="how-to-create-a-new-environment"></a>Procedure: Een nieuwe omgeving maken

Na [aanschaf van een abonnementslicentie voor Dynamics 365 Customer Insights](paid-license.md), ontvangt de globale beheerder van de Microsoft 365-tenant een e-mail die hem of haar uitnodigt om de omgeving te maken. Ga naar [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) om aan de slag te gaan. In dit scenario kunt u direct naar [Stap 1: Geef basisinformatie op](#step-1-provide-basic-information) gaan.

Nadat de eerste omgeving is gemaakt, kan de globale beheerder van de Microsoft 365-tenant [gebruikers uit hun organisatie toevoegen als beheerders](permissions.md). In de toekomst zullen deze beheerders gebruikers en omgevingen kunnen beheren. Als uw organisatie meer dan één licentie aanschaft voor Customer Insights, [neemt u contact op met ons ondersteuningsteam](https://go.microsoft.com/fwlink/?linkid=2079641) om het aantal beschikbare omgevingen te vergroten. Raadpleeg voor meer informatie over capaciteit en uitbreidingscapaciteit de [Dynamics 365-licentiegids](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!TIP]
> Als u de service wilt uitproberen, zie [Een proefomgeving instellen](trial-signup.md).

## <a name="prerequisites"></a>Vereisten

U hebt [beheerdermachtigingen](permissions.md) in Customer Insights nodig om omgevingen te creëren of te beheren.

## <a name="start-the-environment-creation-process"></a>Het proces voor het maken van de omgeving starten

1. Open de omgevingskiezer en selecteer **+ Nieuw**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Selecteer de omgevingskiezer.":::

1. Volg de begeleide ervaring die in de volgende secties wordt beschreven om alle vereiste informatie voor een nieuwe omgeving te verstrekken. Als u eerder een omgeving hebt geconfigureerd, kunt u ook [de configuratie kopiëren](#copy-the-environment-configuration).

## <a name="step-1-provide-basic-information"></a>Stap 1: Geef basisinformatie op

In de stap **Basisgegevens** kiest u of u een geheel nieuwe omgeving wilt maken of [gegevens wilt kopiëren uit een andere omgeving](#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialoogvenster om een nieuwe Customer Insights-omgeving te maken.":::

Geef de volgende details op:

- **Naam**: de naam voor deze omgeving. Dit veld is al ingevuld als u hebt gekopieerd vanuit een bestaande omgeving, maar u kunt dit wijzigen. Als u meer dan één werkomgeving hebt, geeft u ze allemaal een gemakkelijk identificeerbare naam.
- **Uw bedrijf kiezen**: kies de primaire doelgroep voor de nieuwe omgeving. Je kunt werken met individuele consumenten (B2C) of [zakelijke accounts](work-with-business-accounts.md) (B2B). Als uw organisatie voornamelijk zaken doet met individuen, zoals een retailer of een coffeeshop, kies dan voor individuele consumenten. Als uw belangrijkste doelgroep uit andere bedrijven bestaat, zoals een auto- of papierfabriek, kiest u zakelijke accounts.
- **Type**: selecteer of u een productie- of sandbox-omgeving wilt maken. Sandbox-omgevingen staan geen geplande gegevensvernieuwing toe en zijn bedoeld voor pre-implementatie en testen. Sandbox-omgevingen gebruiken dezelfde primaire doelgroep als de productieomgeving die momenteel is geselecteerd.
- **Regio**: de regio waarin de service wordt geïmplementeerd en gehost. Als u [uw eigen Azure Data Lake Storage-account wilt gebruiken](own-data-lake-storage.md) of [verbinding wilt maken met een bestaande Microsoft Dataverse-organisatie](customer-insights-dataverse.md), moet de Customer Insights-omgeving zich in dezelfde regio bevinden.

## <a name="step-2-configure-data-storage"></a>Stap 2: gegevensopslag configureren

In de stap **Gegevensopslag** kiest u waar u de gegevens van Customer Insights wilt opslaan.

U kunt uit twee opties kiezen:

- **Customer Insights-opslag**: gegevensopslag wordt beheerd door het Customer Insights-team. Dit is de standaardoptie en tenzij er specifieke vereisten zijn om gegevens in uw eigen opslagaccount op te slaan, raden we u aan deze optie te gebruiken.
- **Azure Data Lake Storage**: geef uw eigen Azure Data Lake Storage-account om de gegevens op te slaan, zodat u volledige controle hebt over waar de gegevens worden opgeslagen. Zie [Uw eigen Azure Data Lake Storage-account gebruiken](own-data-lake-storage.md) voor meer informatie.

:::image type="content" source="media/data-storage-environment.png" alt-text="Kies de voorkeursoptie om uw gegevens op te slaan.":::

## <a name="step-3-connect-to-microsoft-dataverse"></a>Stap 3: verbinden met Microsoft Dataverse

In de stap **Microsoft Dataverse** kunt u Customer Insights verbinden met uw Dataverse-omgeving. Deel gegevens met Dataverse om deze te gebruiken met zakelijke toepassingen op basis van Dataverse, zoals Dynamics 365 Marketing of modelgestuurde toepassingen in Power Apps.

Laat dit veld leeg als u geen eigen Dataverse-omgeving hebt. Wij maken deze dan voor u.

Zie [Werken met Customer Insights-gegevens in Microsoft Dataverse](customer-insights-dataverse.md) voor meer informatie.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="gegevens delen met Microsoft Dataverse automatisch ingeschakeld voor netto nieuwe omgevingen.":::

### <a name="step-4-finalize-the-settings"></a>Stap 4: de instellingen voltooien

In de stap **Beoordeling** doorloopt u alle opgegeven instellingen. Als alles er compleet uitziet, selecteert u **Maken** om de omgeving in te richten.

U kunt een aantal instellingen later wijzigen. Zie [Omgevingen beheren](manage-environments.md) voor meer informatie.

## <a name="work-with-your-new-environment"></a>Werken met uw nieuwe omgeving

Bekijk de volgende artikelen om u op weg te helpen met het configureren van Customer Insights:

- [Voeg meer gebruikers toe en wijs machtigingen toe](permissions.md).
- [Uw gegevensbronnen opnemen](data-sources.md) en deze het [proces voor gegevensharmonisatie](data-unification.md) laten doorlopen om [uniforme klantprofielen](customer-profiles.md) te krijgen.
- [Verrijk de uniforme klantprofielen](enrichment-hub.md) of [voer voorspellende modellen uit](predictions-overview.md).
- [Segmenten maken](segments.md) om klanten en [meetcriteria](measures.md) te groeperen om KPI's te beoordelen.
- [Stel verbindingen](connections.md) en [exports](export-destinations.md) in om subsets van uw gegevens in andere toepassingen te verwerken.

## <a name="copy-the-environment-configuration"></a>De configuratie van de omgeving kopiëren

Als beheerder kunt u ervoor kiezen om de configuratie uit een bestaande omgeving te kopiëren wanneer u een nieuwe maakt.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Schermafbeelding van de opties in de omgevingsinstellingen.":::

U ziet een lijst met alle beschikbare omgevingen in uw organisatie waaruit u gegevens kunt kopiëren.

De volgende configuratie-instellingen worden gekopieerd:

- Gegevensbronnen die worden geïmporteerd via Power Query
- Configuratie van gegevensharmonisatie
- Segments
- Meetcriteria
- Relaties
- Activiteiten
- Index voor zoeken en filteren
- Exports
- Planning vernieuwen
- Verrijkingen
- Voorspellingsmodellen
- Roltoewijzingen

## <a name="set-up-a-copied-environment"></a>Een gekopieerde omgeving instellen

Wanneer u de omgevingsconfiguratie kopieert, moet u enkele extra stappen doorlopen om de referenties te bevestigen:

- Klantprofielen. Verifieer eerst uw gegevensbronnen en neem deze op en voer de gegevensharmonisatie uit om de klantprofielen opnieuw te maken.
- Referenties voor gegevensbron. U moet de referenties opgeven voor elke gegevensbron om de gegevensbronnen handmatig te verifiëren en te vernieuwen.
- Gegevensbronnen uit de Common Data Model-map en Dataverse. U moet deze gegevensbronnen handmatig maken met dezelfde naam als in de bronomgeving.
- Verbindingsgeheimen die worden gebruikt voor exports en verrijkingen. U moet de verbindingen opnieuw verifiëren en vervolgens verrijkingen en exports opnieuw activeren.

U krijgt een bevestigingsbericht te zien wanneer de gekopieerde omgeving is gemaakt. Selecteer **Ga naar gegevensbronnen** om de lijst met gegevensbronnen te zien.

Alle gegevensbronnen hebben de status **Referenties vereist**. Bewerk de gegevensbronnen en voer de referenties in om ze te vernieuwen.

:::image type="content" source="media/data-sources-copied.png" alt-text="Lijst met gegevensbronnen die zijn gekopieerd en waarvoor verificatie is vereist.":::

Ga na het vernieuwen van de gegevensbronnen naar **Gegevens** > **Harmoniseren**. Hier vindt u instellingen uit de bronomgeving. Bewerk deze indien nodig of selecteer **Uitvoeren** om het proces voor gegevensharmonisering te starten en de geharmoniseerde klantentiteit te maken.

Ga wanneer de gegevensharmonisering is voltooid naar **Meetcriteria** en **Segmenten** om deze eveneens te vernieuwen.

Voordat u exports en verrijkingen opnieuw activeert, gaat u naar **Beheerder** > **Verbindingen** om de verbindingen in uw nieuwe omgeving opnieuw te verifiëren.

[!INCLUDE [footer-include](includes/footer-banner.md)]
