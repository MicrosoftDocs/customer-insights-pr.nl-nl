---
title: Omgevingen maken in Customer Insights
description: Stappen om omgevingen te creëren met een gelicentieerd abonnement voor Dynamics 365 Customer Insights.
ms.date: 04/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 0efda9d2997bcfd069b6d2445b69d159d7d3e59b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646037"
---
# <a name="create-an-environment-in-customer-insights"></a>Een omgeving maken in Customer Insights

In dit artikel wordt uitgelegd hoe u een nieuwe omgeving kunt maken nadat uw organisatie een Dynamics 365 Customer Insights-abonnement heeft aangeschaft. 

Organisaties kunnen voor elke Customer Insights-licentie meerdere omgevingen maken. Als uw organisatie meer dan één licentie aanschaft, [neemt u contact op met ons ondersteuningsteam](https://go.microsoft.com/fwlink/?linkid=2079641) om het aantal beschikbare omgevingen te vergroten. Raadpleeg voor meer informatie over capaciteit en uitbreidingscapaciteit de [Dynamics 365-licentiegids](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Als u de service wilt uitproberen, zie [Een proefomgeving instellen](trial-signup.md).

## <a name="create-a-new-environment"></a>Een nieuwe omgeving maken

Na aanschaf van een abonnementslicentie voor Customer Insights, ontvangt de globale beheerder van de Microsoft 365-tenant een e-mail die hen uitnodigt om de omgeving te maken. Ga naar [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) om aan de slag te gaan. 

Een begeleide ervaring helpt u bij de stappen om alle benodigde informatie voor een nieuwe omgeving te verzamelen. U hebt [beheerdermachtigingen](permissions.md) in Customer Insights nodig om omgevingen te creëren of te beheren.

1. Open de omgevingskiezer en selecteer **+ Nieuw**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Selecteer de omgevingskiezer.":::

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

In de stap **Gegevensopslag** kiest u waar u de gegevens van Customer Insights wilt opslaan.

U hebt twee opties: **Customer Insights-opslag** (een Azure data lake beheerd door het Customer Insights-team) en **Azure Data Lake Storage** (uw eigen Azure Data Lake Storage). Standaard is de opslagoptie Customer Insights geselecteerd.

:::image type="content" source="media/data-storage-environment.png" alt-text="Kies de Azure Data Lake Storage om uw gegevens op te slaan.":::

Door gegevens op te slaan in Azure Data Lake Storage, gaat u ermee akkoord dat gegevens worden overgedragen naar en opgeslagen op de juiste geografische locatie voor die Azure-opslagaccount. Deze locatie kan verschillen van waar de gegevens worden opgeslagen in Dynamics 365 Customer Insights. Ga voor meer informatie naar het [Microsoft Trust Center](https://www.microsoft.com/trust-center).

> [!NOTE]
> Customer Insights ondersteunt momenteel het volgende:
> - Opgenomen entiteiten van Power BI-gegevensstromen die zijn opgeslagen in een door Microsoft Dataverse beheerde Data Lake.  
> - Azure Data Lake Storage-accounts uit dezelfde Azure-regio die u hebt geselecteerd bij het maken van de omgeving.
> - Azure Data Lake Storage-accounts die Gen2 zijn en waarvoor *hiërarchische naamruimte* is ingeschakeld. Azure Data Lake Gen1-opslagaccounts worden niet ondersteund.

Voor de optie Azure Data Lake Storage kunt u kiezen tussen een op resources gebaseerde optie en een op abonnementen gebaseerde optie voor verificatie. Zie voor meer informatie [Verbinding met een Azure Data Lake Storage-account maken via een Azure-service-principal](connect-service-principal.md). Een container met de naam `customerinsights` moet aanwezig zijn in het opslagaccount.

Wanneer systeemprocessen zoals gegevensopname zijn voltooid, maakt het systeem overeenkomstige mappen in de opslagaccount die u hebt opgegeven. Gegevensbestanden en *model.json*-bestanden worden gemaakt en toegevoegd aan mappen op basis van de procesnaam.

Als u meerdere omgevingen van Customer Insights maakt en ervoor kiest om de uitvoerentiteiten van die omgevingen op te slaan in uw opslagaccount, maakt Customer Insights afzonderlijke mappen voor elke omgeving met `ci_environmentID` in de container.

### <a name="step-3-connect-to-microsoft-dataverse"></a>Stap 3: verbinden met Microsoft Dataverse
   
In de stap **Microsoft Dataverse** kunt u Customer Insights verbinden met uw Dataverse-omgeving.

Bied uw eigen Microsoft Dataverse-omgeving om gegevens (profielen en inzichten) te delen met zakelijke toepassingen op basis van Dataverse, zoals Dynamics 365 Marketing of modelgestuurde toepassingen in Power Apps. Laat dit veld leeg als u geen eigen Dataverse-omgeving hebt, dan richten wij er een voor u in.

Verbinding maken met uw Dataverse-omgeving stelt u ook in staat om [gegevens op te nemen uit on-premises gegevensbronnen met behulp van Power Platform-gegevensstromen en -gateways](data-sources.md#add-data-from-on-premises-data-sources). U kunt ook [kant-en-klare voorspellingsmodellen](predictions-overview.md?tabs=b2c#out-of-box-models) gebruiken door verbinding te maken met een Dataverse-omgeving.

> [!IMPORTANT]
> 1. Customer Insights en Dataverse moeten zich in dezelfde regio bevinden om het delen van gegevens mogelijk te maken.
> 1. U moet de rol van algemene beheerder hebben in de Dataverse-omgeving. Controleer of deze [Dataverse-omgeving is gekoppeld](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) aan bepaalde beveiligingsgroepen en zorg ervoor dat u aan die beveiligingsgroepen wordt toegevoegd.
> 1. Er is nog geen bestaande Customer Insights-omgeving aan die Dataverse-omgeving gekoppeld. Leren hoe u [een bestaande verbinding met een Dataverse omgeving kunt verwijderen](manage-environments.md#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="gegevens delen met Microsoft Dataverse automatisch ingeschakeld voor netto nieuwe exemplaren.":::

Zie [Verbinden met Microsoft Dataverse](manage-environments.md#connect-to-microsoft-dataverse) voor meer informatie over het inschakelen van het delen van gegevens met Microsoft Dataverse vanuit uw eigen Azure Data Lake Storage.

Customer Insights biedt geen ondersteuning voor de volgende scenario's voor het delen van gegevens:
- Als u het delen van gegevens met een door Dataverse beheerd data lake inschakelt, is het niet mogelijk om [voorspelde of ontbrekende waarden te maken in een entiteit](predictions.md).

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
