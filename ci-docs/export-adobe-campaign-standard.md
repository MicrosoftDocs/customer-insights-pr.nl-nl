---
title: Gegevens uit Customer Insights exporteren naar Adobe Campaign Standard
description: Meer informatie over hoe u Customer Insights-segmenten kunt gebruiken in Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 2a62d2f889f199222eeb8cc969fce62fa89fa6f0
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646234"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Customer Insights-segmenten gebruiken in Adobe Campaign Standard (preview)

Als gebruiker van Dynamics 365 Customer Insights hebt u mogelijk segmenten gemaakt om uw marketingcampagnes efficiënter te maken door relevante doelgroepen te targeten. Een segment uit Customer Insights gebruiken in Adobe Experience Platform en toepassingen zoals Adobe Campaign Standard, moet u een paar stappen volgen die in dit artikel worden beschreven.

:::image type="content" source="media/ACS-flow.png" alt-text="Procesdiagram van de stappen die in dit artikel worden beschreven.":::

## <a name="prerequisites"></a>Vereisten

-   Dynamics 365 Customer Insights-licentie
-   Licentie voor Adobe Campaign Standard
-   Azure Blob Storage-account

## <a name="campaign-overview"></a>Campagne-overzicht

Laten we eens kijken naar een fictieve voorbeeldcampagne om beter te begrijpen hoe u segmenten uit Customer Insights kunt gebruiken in Adobe Experience Platform.

Laten we aannemen dat uw bedrijf een maandelijkse, op abonnementen gebaseerde service biedt aan uw klanten in de Verenigde Staten. U wilt klanten identificeren waarvan het abonnement binnen acht dagen moet worden verlengd, maar die hun abonnement nog niet hebben verlengd. Om deze klanten te behouden, wilt u ze een promotieaanbieding sturen via e-mail, met behulp van Adobe Campaign Standard.

In dit voorbeeld willen we de promotionele e-mailcampagne één keer uitvoeren. In dit artikel wordt niet het gebruiksscenario behandeld waarin de campagne meerdere keer wordt uitgevoerd. Echter, Customer Insights en Adobe Campaign Standard kunnen ook worden geconfigureerd om geschikt te zijn voor een terugkerend campagnescenario.

## <a name="identify-your-target-audience"></a>Uw doelgroep identificeren

In ons scenario gaan we ervan uit dat de e-mailadressen van de klanten beschikbaar zijn en dat hun promotievoorkeuren zijn geanalyseerd om leden van het segment te identificeren.

Het [segment dat u hebt gedefinieerd in Customer Insights](segments.md) heet **ChurnProneCustomers** en u bent van plan deze klanten de e-mailpromotie te sturen.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Schermopname van de pagina Segmenten met het gemaakte segment ChurnProneCustomers.":::

De aanbiedings-e-mail die u wilt verzenden, bevat de voornaam, achternaam en einddatum van het abonnement van de klant. Klanten worden geïnformeerd over de korting die ze krijgen als ze hun abonnement verlengen voordat het afloopt.

## <a name="export-your-target-audience"></a>Uw doelgroep exporteren

### <a name="configure-a-connection"></a>Een verbinding configureren

Nu we weten wie onze doelgroep is, kunnen we de export van Customer Insights naar een Azure Blob Storage-account configureren.

1. Ga in Customer Insights naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Adobe Campaign** om de verbinding te configureren of selecteer **Instellen** op de tegel **Adobe Campaign**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Configuratietegel voor Adobe Campaign Standard.":::

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling. Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.

1. Voer een waarde in de velden **Accountnaam**, **Accountsleutel** en **Container** in van het Azure Blob Storage-account waarnaar u het segment wilt exporteren.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Schermopname van de opslagaccountconfiguratie."::: 

   - Zie [Opslagaccountinstellingen beheren in de Azure-portal](/azure/storage/common/storage-account-manage) voor meer informatie over het vinden van de Azure Blob Storage-accountnaam en -accountsleutel.

   - Zie voor meer informatie over het maken van een container [Een container maken](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Selecteer **Opslaan** om de verbinding te voltooien.

### <a name="configure-an-export"></a>Een export configureren

U kunt deze export configureren als u toegang hebt tot een verbinding van dit type. Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen** om een nieuwe export te maken.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie Adobe Campaign. Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.

1. Sluit het segment dat u u wilt exporteren. In dit voorbeeld is het **ChurnProneCustomers**​.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Schermopname van de gebruikersinterface voor segmentselectie met het segment ChurnProneCustomers geselecteerd.":::

1. Selecteer **Volgende**.

1. Nu wijzen we de **Bron**-velden van het Customer Insights-segment toe aan de **Doel**-veldnamen in het Adobe Campaign Standard-profielschema.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Veldtoewijzing voor de Adobe Campaign Standard-connector.":::

   Als u meer kenmerken wilt toevoegen, selecteert u **Kenmerk toevoegen**​. De doelnaam kan verschillen van de naam van het bronveld, zodat u toch segmentuitvoer van Customer Insights kunt toewijzen aan Adobe Campaign Standard als de velden niet dezelfde naam hebben in beide systemen.

   > [!NOTE]
   > E-mailadres wordt gebruikt als identiteitsveld, maar u kunt elke andere id uit het klantprofiel gebruiken om gegevens aan toe te wijzen aan Adobe Campaign Standard.

1. Selecteer **Save**.

Nadat u de exportbestemming hebt opgeslagen, vindt u deze onder **Gegevens** > **Exports**.

U kunt [het segment nu op aanvraag exporteren](export-destinations.md#run-exports-on-demand)​. De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md).

> [!NOTE]
> Zorg ervoor dat het aantal records in het geëxporteerde segment binnen de toegestane limiet van uw Adobe Campaign Standard-licentie.

Geëxporteerde gegevens worden opgeslagen in de Azure Blob Storage-container die u eerder hebt geconfigureerd. Het volgende mappad wordt automatisch gemaakt in uw container:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Voorbeeld: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Adobe Campaign Standard configureren

Geëxporteerde segmenten bevatten de kolommen die u hebt geselecteerd tijdens het definiëren van de exportbestemming in de vorige stap. Deze gegevens kunnen worden gebruikt om [profielen in Adobe Campaign Standard te maken](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Als u het segment in Adobe Campaign Standard wilt gebruiken, moeten we het profielschema uitbreiden in Adobe Campaign Standard om twee extra velden op te nemen. Leer hoe u [de profielbron kunt uitbreiden](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) met nieuwe velden in Adobe Campaign Standard.

In ons voorbeeld zijn dit de velden *Segmentnaam en Segmentdatum (optioneel)*.

We zullen deze velden gebruiken om de profielen in Adobe Campaign Standard te identificeren waarop we ons willen richten voor deze campagne.

Als er geen andere records zijn in Adobe Campaign Standard, behalve wat u gaat importeren, kunt u deze stap overslaan.

## <a name="import-data-into-adobe-campaign-standard"></a>Gegevens importeren in Adobe Campaign Standard

Nu alles aanwezig is, moeten we de voorbereide doelgroepgegevens uit Customer Insights importeren in Adobe Campaign Standard om profielen te maken. Leer [profielen importeren in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) met behulp van een werkstroom.

De importwerkstroom in de onderstaande afbeelding is geconfigureerd om elke acht uur te worden uitgevoerd en te zoeken naar geëxporteerde Customer Insights-segmenten (.csv-bestand in Azure Blob Storage). De werkstroom extraheert de inhoud van het CSV-bestand in een opgegeven kolomvolgorde. Deze werkstroom is gebouwd om elementaire foutafhandeling uit te voeren en ervoor te zorgen dat elke record een e-mailadres heeft voordat de gegevens worden overgebracht naar Adobe Campaign Standard. De werkstroom extraheert ook de segmentnaam uit de bestandsnaam voordat deze wordt toegevoegd aan Adobe Campaign Standard-profielgegevens.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Schermopname van een importwerkstroom in de gebruikersinterface van Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>De doelgroep ophalen in Adobe Campaign Standard

Zodra de gegevens zijn geïmporteerd in Adobe Campaign Standard, kunt u [een werkstroom maken](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) en [query's uitvoeren](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) voor de klanten op basis van *Segmentnaam* en *Segmentdatum* om profielen te selecteren die zijn geïdentificeerd voor onze voorbeeldcampagne.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>De e-mail maken en verzenden met Adobe Campaign Standard

Maak de e-mailinhoud en [test en verzend](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) vervolgens uw e-mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Voorbeelde-mail met verlengingsaanbieding van Adobe Campaign Standard.":::