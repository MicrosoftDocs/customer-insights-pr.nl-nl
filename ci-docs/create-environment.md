---
title: Een nieuwe omgeving maken
description: Stappen om omgevingen te maken in Dynamics 365 Customer Insights.
ms.date: 08/15/2022
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
ms.openlocfilehash: 0a45e2fd2bdb7b85883a536f8b42ee650e54db7e
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304237"
---
# <a name="create-a-new-environment"></a>Een nieuwe omgeving maken

Na [aanschaf van een abonnementslicentie voor Dynamics 365 Customer Insights](paid-license.md), ontvangt de globale beheerder van de Microsoft 365-tenant een e-mail die hem of haar uitnodigt om de omgeving te maken. Ga naar [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) om aan de slag te gaan. Start in dit scenario met [Stap 1: Geef basisinformatie op](#step-1-provide-basic-information).

Nadat de eerste omgeving is gemaakt, kan de globale beheerder van de Microsoft 365-tenant [gebruikers uit hun organisatie toevoegen als beheerders](permissions.md). Deze beheerders kunnen dan gebruikers en omgevingen beheren. Als uw organisatie meer dan één licentie aanschaft voor Customer Insights, [neemt u contact op met ons ondersteuningsteam](https://go.microsoft.com/fwlink/?linkid=2079641) om het aantal beschikbare omgevingen te vergroten. Raadpleeg voor meer informatie over capaciteit en uitbreidingscapaciteit de [Dynamics 365-licentiegids](https://go.microsoft.com/fwlink/?LinkId=866544). Zodra u de mogelijkheid hebt om extra omgevingen te maken, gaat u naar [Het proces voor het maken van de omgeving starten](#start-the-environment-creation-process).

> [!TIP]
> Als u de service wilt uitproberen, zie [Een proefomgeving instellen](trial-signup.md).

## <a name="prerequisites"></a>Vereisten

[Machtigingen voor beheerders](permissions.md) in Customer Insights

## <a name="start-the-environment-creation-process"></a>Het proces voor het maken van de omgeving starten

1. Open de omgevingskiezer en selecteer **+ Nieuw**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Selecteer de omgevingskiezer.":::

1. Volg de begeleide ervaring die in de volgende secties wordt beschreven om alle vereiste informatie voor een nieuwe omgeving te verstrekken.

## <a name="step-1-provide-basic-information"></a>Stap 1: Geef basisinformatie op

1. Kies of u een geheel nieuwe omgeving wilt maken of gegevens wilt kopiëren uit een andere omgeving. [Gegevens kopiëren uit een andere omgeving](#copy-the-environment-configuration) vereist extra stappen.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialoogvenster om een nieuwe Customer Insights-omgeving te maken.":::

1. Geef de volgende details op:

   - **Naam**: naam voor deze omgeving. Dit veld is al ingevuld als u hebt gekopieerd vanuit een bestaande omgeving, maar u kunt dit wijzigen.
   - **Uw bedrijf kiezen**: primaire doelgroep voor de nieuwe omgeving: individuele consumenten (B2C) of [zakelijke accounts](work-with-business-accounts.md) (B2B). Als uw organisatie voornamelijk zaken doet met individuen, zoals een retailer of een coffeeshop, kies dan voor individuele consumenten. Als uw belangrijkste doelgroep uit andere bedrijven bestaat, zoals een auto- of papierfabriek, kiest u zakelijke accounts.
   - **Type**: type omgeving: productie of sandbox. Sandbox-omgevingen staan geen geplande gegevensvernieuwing toe en zijn bedoeld voor pre-implementatie en testen. Sandbox-omgevingen gebruiken dezelfde primaire doelgroep als de productieomgeving die momenteel is geselecteerd.
   - **Regio**: regio waarin de service wordt geïmplementeerd en gehost. Als u [uw eigen Azure Data Lake Storage-account wilt gebruiken](own-data-lake-storage.md) of [verbinding wilt maken met een bestaande Microsoft Dataverse-organisatie](customer-insights-dataverse.md), moet de Customer Insights-omgeving zich in dezelfde regio bevinden.

1. Selecteer **Volgende**.

## <a name="step-2-configure-data-storage"></a>Stap 2: gegevensopslag configureren

1. Kies waar u de Customer Insights-gegevens wilt opslaan:

   - **Customer Insights-opslag**: gegevensopslag wordt automatisch beheerd. Dit is de standaardoptie en tenzij er specifieke vereisten zijn om gegevens in uw eigen opslagaccount op te slaan, raden we u aan deze optie te gebruiken.
   - **Azure Data Lake Storage**: uw eigen Azure Data Lake Storage-account om de gegevens op te slaan, zodat u volledige controle hebt over waar de gegevens worden opgeslagen. Volg de stappen in [Uw eigen Azure Data Lake Storage-account gebruiken](own-data-lake-storage.md).

   :::image type="content" source="media/data-storage-environment.png" alt-text="Kies de voorkeursoptie om uw gegevens op te slaan.":::

1. Selecteer **Volgende**.

## <a name="step-3-connect-to-microsoft-dataverse"></a>Stap 3: verbinden met Microsoft Dataverse

Als u een Dataverse-omgeving hebt, maakt u verbinding met Customer Insights. Deel gegevens met Dataverse om deze te gebruiken met zakelijke toepassingen op basis van Dataverse, zoals Dynamics 365 Marketing of modelgestuurde toepassingen in Power Apps.

1. Volg de stappen in [Werken met Customer Insights-gegevens in Microsoft Dataverse](customer-insights-dataverse.md).

   :::image type="content" source="media/dataverse-provisioning.png" alt-text="gegevens delen met Microsoft Dataverse automatisch ingeschakeld voor netto nieuwe omgevingen.":::

1. Selecteer **Volgende**.

## <a name="step-4-finalize-the-settings"></a>Stap 4: de instellingen voltooien

De opgegeven instellingen controleren Als alles er compleet uitziet, selecteert u **Maken** om de omgeving in te richten.

Zie [Omgevingen beheren](manage-environments.md) als u sommige instellingen later wilt wijzigen.

## <a name="work-with-your-new-environment"></a>Werken met uw nieuwe omgeving

Bekijk de volgende artikelen om u op weg te helpen met het configureren van Customer Insights:

- [Voeg meer gebruikers toe en wijs machtigingen toe](permissions.md).
- [Uw gegevensbronnen opnemen](data-sources.md) en deze het [proces voor gegevensharmonisatie](data-unification.md) laten doorlopen om [uniforme klantprofielen](customer-profiles.md) te krijgen.
- [Verrijk de uniforme klantprofielen](enrichment-hub.md) of [voer voorspellende modellen uit](predictions-overview.md).
- [Segmenten maken](segments.md) om klanten en [meetcriteria](measures.md) te groeperen om KPI's te beoordelen.
- [Stel verbindingen](connections.md) en [exports](export-destinations.md) in om subsets van uw gegevens in andere toepassingen te verwerken.

## <a name="copy-the-environment-configuration"></a>De configuratie van de omgeving kopiëren

Als u als beheerder ervoor kiest om de configuratie uit een bestaande omgeving te kopiëren, maakt u een keuze uit de lijst met alle beschikbare omgevingen in uw organisatie.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Schermafbeelding van de opties in de omgevingsinstellingen.":::

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

### <a name="set-up-a-copied-environment"></a>Een gekopieerde omgeving instellen

Wanneer u de omgevingsconfiguratie kopieert, wordt een bevestigingsbericht weergegeven als de gekopieerde omgeving is gemaakt. Voer de volgende stappen uit om referenties te bevestigen.

1. Selecteer **Ga naar gegevensbronnen** om de lijst met gegevensbronnen te zien. Alle gegevensbronnen hebben de status **Referenties vereist**.

   :::image type="content" source="media/data-sources-copied.png" alt-text="Lijst met gegevensbronnen die zijn gekopieerd en waarvoor verificatie is vereist.":::

1. Bewerk de gegevensbronnen en voer de referenties in om ze te vernieuwen. Gegevensbronnen uit de map Common Data Model en Dataverse moet handmatig worden gemaakt met dezelfde naam als in de bronomgeving.

1. Ga na het vernieuwen van de gegevensbronnen naar **Gegevens** > **Harmoniseren**. Hier vindt u instellingen uit de bronomgeving. Bewerk deze indien nodig of selecteer **Harmoniseren** > **Klantprofielen en afhankelijkheden harmoniseren** om het proces voor gegevensharmonisering te starten en de geharmoniseerde klantentiteit te maken.

   > [!TIP]
   > Selecteer voor accounts en contactpersonen de optie **Accounts samenvoegen** > **Profielen en afhankelijkheden verenigen**.

1. Ga wanneer de gegevensharmonisering is voltooid naar **Meetcriteria** en **Segmenten** om deze te vernieuwen.

1. Ga naar **Beheerder** > **Verbindingen** om de verbindingen in uw nieuwe omgeving opnieuw te verifiëren.

1. Ga naar **Gegevens** > **Verrijking** en **Gegevens** > **Exports** om deze opnieuw te activeren.

[!INCLUDE [footer-include](includes/footer-banner.md)]
