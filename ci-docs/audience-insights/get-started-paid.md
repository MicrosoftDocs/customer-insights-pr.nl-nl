---
title: Een betaalde licentie van Customer Insights maken en configureren
description: Stappen om een licentieabonnement te krijgen voor Dynamics 365 Customer Insights en deze te configureren.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: b5f76f4c468b88aaf7037dbd2ee3bed449fbeaa5f645d52278eee05b36b4e328
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034446"
---
# <a name="get-started-with-a-paid-subscription"></a>Aan de slag met een betaald abonnement

In dit artikel wordt uitgelegd hoe u een nieuwe omgeving kunt maken nadat uw organisatie een Dynamics 365 Customer Insights-abonnement heeft aangeschaft. Als u Customer Insights wilt kopen, vindt u onze contactmogelijkheden op de [Dynamics 365 Customer Insights-website](https://dynamics.microsoft.com/ai/customer-insights/). 

Zie [Een proefomgeving instellen](get-started-trial.md) als u de service en de functies wilt uitproberen.

## <a name="create-an-environment-in-an-existing-organization"></a>Een omgeving maken in een bestaande organisatie

Na aanschaf van een abonnementslicentie voor Customer Insights, ontvangt de algemene beheerder van de Microsoft 365-tenant een e-mail met een uitnodiging om de omgeving te maken. Ga naar [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start) om aan de slag te gaan. 

Customer Insights wordt niet per gebruiker gelicentieerd, dus het wordt niet weergegeven in het gedeelte Licenties. Als u de licentie zoekt in het Microsoft 365-beheercentrum, gaat u naar **Uw producten**. 

> [!NOTE]
> Organisaties kunnen *twee* omgevingen maken voor elke Customer Insights-licentie. Als uw organisatie meer dan één licentie aanschaft, [neemt u contact op met ons ondersteuningsteam](https://go.microsoft.com/fwlink/?linkid=2079641) om het aantal beschikbare omgevingen te vergroten. Download de [Dynamics 365-licentiegids](https://go.microsoft.com/fwlink/?LinkId=866544) voor meer informatie over capaciteit en de uitbreidingsmogelijkheden.

Een omgeving maken:

1. Selecteer in het dialoogvenster **Een omgeving maken** de optie **Nieuwe omgeving**.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialoogvenster om een nieuwe Customer Insights-omgeving te maken.":::

   We raden aan helemaal opnieuw te beginnen met het opzetten van een omgeving. Als u echter beheerder bent of lid bent van een proefomgeving, kunt u [gegevens kopiëren uit een andere omgeving](manage-environments.md#copy-the-environment-configuration), door **Kopiëren uit bestaande omgeving** te kiezen. U ziet een lijst met alle beschikbare omgevingen in uw organisatie waaruit u gegevens kunt kopiëren.

1. Geef de volgende details op:
   - **Naam**: de naam voor deze omgeving. Dit veld is al ingevuld als u hebt gekopieerd vanuit een bestaande omgeving, maar u kunt dit wijzigen.
   - **Regio**: de regio waarin de service wordt geïmplementeerd en gehost.
   - **Type**: selecteer of u een productie- of sandbox-omgeving wilt maken. Sandbox-omgevingen staan geen geplande gegevensvernieuwing toe en zijn bedoeld voor pre-implementatie en testen.
   
1. U kunt desgewenst het **Geavanceerde instellingen** inschakelen:

   - **Alle gegevens opslaan naar**: geeft aan waar u de uitvoergegevens wilt opslaan die zijn gegenereerd vanuit Customer Insights. U hebt twee opties: **Customer Insights-opslag** (een Azure Data Lake beheerd door het Customer Insights-team) en **Azure Data Lake Storage** (uw eigen Azure Data Lake Storage). Standaard is de opslagoptie Customer Insights geselecteerd.

     > [!NOTE]
     > Door gegevens op te slaan in Azure Data Lake Storage stemt u ermee in dat gegevens worden overgebracht naar en opgeslagen in de juiste geografische locatie voor dat Azure Storage-account, die kan afwijken van waar gegevens zijn opgeslagen in Dynamics 365 Customer Insights. [Meer informatie op het Microsoft Trust Center.](https://www.microsoft.com/trust-center)
     >
     > Momenteel worden entiteiten uit Power BI-gegevensstromen opgeslagen in het door Microsoft Dataverse beheerde Data Lake. 
     > 
     > Wij ondersteunen alleen Azure Data Lake Storage-accounts uit dezelfde Azure-regio die u hebt geselecteerd bij het maken van de omgeving. 
     > 
     > Wij ondersteunen alleen Azure Data Lake Storage-accounts waarvoor hiërarchische naamruimte is ingeschakeld.


   - Voor de optie Azure Data Lake Storage kunt u kiezen tussen een op resources gebaseerde optie en een op abonnementen gebaseerde optie voor verificatie. Zie [Doelgroepinzichten verbinden met een Azure Data Lake Storage Gen2-account met een Azure Service Principal](connect-service-principal.md) voor meer informatie. De naam van **Container** kan niet worden gewijzigd en luidt `customerinsights`.
   
   - Als u [kant-en-klare modellen](predictions-overview.md#out-of-box-models) wilt gebruiken, configureert u gegevens delen met Microsoft Dataverse of schakelt u gegevensopname uit on-premise gegevensbronnen in, en geeft u de URL voor de Microsoft Dataverse-omgeving op onder **Gegevens delen met Microsoft Dataverse configureren en aanvullende functionaliteit inschakelen**. Selecteer **Gegevens delen inschakelen** om Customer Insights-uitvoergegevens te delen met een Microsoft Dataverse beheerde data lake.

     > [!NOTE]
     > - Gegevens delen met Microsoft Dataverse beheerde data lake wordt momenteel niet ondersteund wanneer u alle gegevens in uw eigen Azure Data Lake Storage opslaat.
     > - [Voorspelling van ontbrekende waarden in een entiteit](predictions.md) wordt momenteel niet ondersteund wanneer u gegevens delen met een Microsoft Dataverse beheerde data lake inschakelt.

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="Configuratieopties om het delen van gegevens met Microsoft Dataverse mogelijk te maken.":::

   Wanneer systeemprocessen als gegevensopname zijn voltooid, maakt het systeem overeenkomstige mappen in het opslagaccount dat u hebt opgegeven. Gegevensbestanden en model.json-bestanden worden gemaakt en toegevoegd aan mappen op basis van de procesnaam.

   Als u meerdere omgevingen van Customer Insights maakt en ervoor kiest de uitvoerentiteiten van die omgevingen op te slaan in uw opslagaccount, worden voor elke omgeving aparte mappen gemaakt met ci_<environmentid> in de container.

1. Selecteer **Maken** om de omgeving in te stellen. 

## <a name="configure-an-environment"></a>Een omgeving configureren

Bekijk de volgende artikelen om u op weg te helpen met het configureren van Customer Insights. 

- [Voeg meer gebruikers toe en wijs machtigingen toe](permissions.md).
- [Uw gegevensbronnen opnemen](data-sources.md) en deze het [proces voor gegevensharmonisatie](data-unification.md) laten doorlopen om [uniforme klantprofielen](customer-profiles.md) te krijgen.
- [Verrijk de uniforme klantprofielen](enrichment-hub.md) of [voer voorspellende modellen uit](predictions-overview.md).
- Maak [segmenten](segments.md) om klanten te groeperen en [meetcriteria](measures.md) KPI's te bekijken.
- Stel [verbindingen](connections.md) en [exports](export-destinations.md) in om subsets van uw gegevens in andere toepassingen te verwerken.
