---
title: Omgevingen maken in Customer Insights
description: Stappen om omgevingen te creëren met een gelicentieerd abonnement voor Dynamics 365 Customer Insights.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 4f26220f6ba7f5b5ae00c11216129f9ad814b77d
ms.sourcegitcommit: 626d485dae1e001e63e4d4bf78f6770766822ba0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/06/2021
ms.locfileid: "7892332"
---
# <a name="create-an-environment-in-audience-insights"></a>Een omgeving maken in doelgroepinzichten

In dit artikel wordt uitgelegd hoe u een nieuwe omgeving kunt maken nadat uw organisatie een Dynamics 365 Customer Insights-abonnement heeft aangeschaft. 

Organisaties kunnen *twee* omgevingen maken voor elke Customer Insights-licentie. Als uw organisatie meer dan één licentie aanschaft, [neemt u contact op met ons ondersteuningsteam](https://go.microsoft.com/fwlink/?linkid=2079641) om het aantal beschikbare omgevingen te vergroten. Download de [Dynamics 365-licentiegids](https://go.microsoft.com/fwlink/?LinkId=866544) voor meer informatie over capaciteit en de uitbreidingsmogelijkheden.

> [!NOTE]
> Als u de service wilt uitproberen, zie [Een proefomgeving instellen](../trial-signup.md).

## <a name="create-a-new-environment"></a>Een nieuwe omgeving maken

Na aanschaf van een abonnementslicentie voor Customer Insights, ontvangt de algemene beheerder van de Microsoft 365-tenant een e-mail met een uitnodiging om de omgeving te maken. Ga naar [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) om aan de slag te gaan. 

Een begeleide ervaring helpt u bij de stappen om alle benodigde informatie voor een nieuwe omgeving te verzamelen. U hebt [beheerdermachtigingen](permissions.md) in doelgroepinzichten nodig om omgevingen te creëren of te beheren.

1. Open in doelgroepinzichten de omgevingskiezer en selecteer **+ Nieuw**.
  
   :::image type="content" source="../engagement-insights/media/environment-picker.png" alt-text="Selecteer de omgevingskiezer.":::

1. Volg de begeleide ervaring die in de volgende secties wordt beschreven.

### <a name="step-1-provide-environment-information"></a>Stap 1: omgevingsinformatie opgeven

In de stap **Basisgegevens** kiest u of u een geheel nieuwe omgeving wilt maken of [gegevens wilt kopiëren uit een andere omgeving](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialoogvenster om een nieuwe Customer Insights-omgeving te maken.":::

Geef de volgende details op:
   - **Naam**: de naam voor deze omgeving. Dit veld is al ingevuld als u hebt gekopieerd vanuit een bestaande omgeving, maar u kunt dit wijzigen.
   - **Uw bedrijf kiezen**: kies de primaire doelgroep voor de nieuwe omgeving. Je kunt werken met individuele consumenten (B2C) of [zakelijke accounts](work-with-business-accounts.md) (B2B).
   - **Type**: selecteer of u een productie- of sandbox-omgeving wilt maken. Sandbox-omgevingen staan geen geplande gegevensvernieuwing toe en zijn bedoeld voor pre-implementatie en testen. Sandbox-omgevingen gebruiken dezelfde primaire doelgroep als de productieomgeving die momenteel is geselecteerd.
   - **Regio**: de regio waarin de service wordt geïmplementeerd en gehost.

### <a name="step-2-configure-data-storage"></a>Stap 2: gegevensopslag configureren

In de stap **Gegevensopslag** kiest u waar u de gegevens van doelgroepinzichten wilt opslaan.

U hebt twee opties: **Customer Insights-opslag** (een Azure data lake beheerd door het Customer Insights-team) en **Azure Data Lake Storage** (uw eigen Azure Data Lake Storage). Standaard is de opslagoptie Customer Insights geselecteerd.

:::image type="content" source="media/data-storage-environment.png" alt-text="Kies de Azure Data Lake Storage om de gegevens van uw doelgroepinzichten in op te slaan.":::

Door gegevens op te slaan in Azure Data Lake Storage, gaat u ermee akkoord dat gegevens worden overgedragen naar en opgeslagen op de juiste geografische locatie voor die Azure-opslagaccount. Deze locatie kan verschillen van waar de gegevens worden opgeslagen in Dynamics 365 Customer Insights. Ga voor meer informatie naar het [Microsoft Trust Center](https://www.microsoft.com/trust-center).

> [!NOTE]
> Customer Insights ondersteunt momenteel het volgende:
> - Opgenomen entiteiten van Power BI-gegevensstromen die zijn opgeslagen in een door Microsoft Dataverse beheerde Data Lake.  
> - Azure Data Lake Storage-accounts uit dezelfde Azure-regio die u hebt geselecteerd bij het maken van de omgeving.
> - Azure Data Lake Storage-accounts waarvoor *hiërarchische naamruimte* is ingeschakeld.

Voor de optie Azure Data Lake Storage kunt u kiezen tussen een op resources gebaseerde optie en een op abonnementen gebaseerde optie voor verificatie. Zie voor meer informatie [Verbinding met een Azure Data Lake Storage-account maken via een Azure-service-principal](connect-service-principal.md). De naam van de **Container** is `customerinsights`. Dit kan niet worden gewijzigd.

Wanneer systeemprocessen zoals gegevensopname zijn voltooid, maakt het systeem overeenkomstige mappen in de opslagaccount die u hebt opgegeven. Gegevensbestanden en *model.json*-bestanden worden gemaakt en toegevoegd aan mappen op basis van de procesnaam.

Als u meerdere omgevingen van Customer Insights maakt en ervoor kiest om de uitvoerentiteiten van die omgevingen op te slaan in uw opslagaccount, maakt Customer Insights afzonderlijke mappen voor elke omgeving met `ci_environmentID` in de container.

### <a name="step-3-connect-to-microsoft-dataverse"></a>Stap 3: verbinden met Microsoft Dataverse
   
In de stap **Microsoft Dataverse** kunt u Customer Insights verbinden met uw Dataverse-omgeving.

Als u [kant-en-klare voorspellingsmodellen](predictions-overview.md#out-of-box-models) wilt gebruiken, configureert u delen van gegevens met Dataverse. Of u kunt gegevensopname van on-premises-gegevensbronnen inschakelen door de Microsoft Dataverse omgevings-URL op te geven die uw organisatie beheert. Selecteer **Gegevens delen inschakelen** om Customer Insights-uitvoergegevens te delen met een door Dataverse beheerd data lake.

> [!IMPORTANT]
> Customer Insights en Dataverse moeten zich in dezelfde regio bevinden om het delen van gegevens mogelijk te maken.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Configuratieopties om het delen van gegevens met Microsoft Dataverse mogelijk te maken.":::

> [!NOTE]
> Customer Insights biedt geen ondersteuning voor de volgende scenario's voor het delen van gegevens:
> - Als u alle gegevens opslaat naar uw eigen Azure Data Lake Storage, kunt u het delen van gegevens met een door Dataverse beheerd data lake niet inschakelen.
> - Als u het delen van gegevens met een door Dataverse beheerd data lake inschakelt, is het niet mogelijk om [voorspelde of ontbrekende waarden te maken in een entiteit](predictions.md).

### <a name="step-4-finalize-the-settings"></a>Stap 4: de instellingen voltooien

In de stap **Beoordeling** doorloopt u alle opgegeven instellingen. Als alles er compleet uitziet, selecteert u **Maken** om de omgeving in te richten. 

U kunt de meeste instellingen ook later wijzigen. Zie [Omgevingen beheren](manage-environments.md) voor meer informatie.

## <a name="work-with-your-new-environment"></a>Werken met uw nieuwe omgeving

Bekijk de volgende artikelen om u op weg te helpen met het configureren van Customer Insights: 

- [Voeg meer gebruikers toe en wijs machtigingen toe](permissions.md).
- [Uw gegevensbronnen opnemen](data-sources.md) en deze het [proces voor gegevensharmonisatie](data-unification.md) laten doorlopen om [uniforme klantprofielen](customer-profiles.md) te krijgen.
- [Verrijk de uniforme klantprofielen](enrichment-hub.md) of [voer voorspellende modellen uit](predictions-overview.md).
- [Segmenten maken](segments.md) om klanten en [meetcriteria](measures.md) te groeperen om KPI's te beoordelen.
- [Stel verbindingen](connections.md) en [exports](export-destinations.md) in om subsets van uw gegevens in andere toepassingen te verwerken.
