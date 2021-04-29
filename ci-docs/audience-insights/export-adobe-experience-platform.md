---
title: Customer Insights-gegevens naar Adobe Experience Platform exporteren
description: Ontdek hoe u segmenten voor doelgroepinzichten gebruikt in Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 884f4d30f354bed29909d57be84dce4c8e46965a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760095"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Customer Insights-segmenten gebruiken in Adobe Experience Platform (preview)

Als gebruiker van doelgroepinzichten voor Dynamics 365 Customer Insights hebt u mogelijk segmenten gemaakt om uw marketingcampagnes efficiënter te maken door u op relevante doelgroepen te richten. Als u een segment uit doelgroepinzichten in Adobe Experience Platform en toepassingen zoals Adobe Campaign Standard wilt gebruiken, moet u een paar stappen volgen die in dit artikel worden beschreven.

:::image type="content" source="media/AEP-flow.png" alt-text="Procesdiagram van de stappen die in dit artikel worden beschreven.":::

## <a name="prerequisites"></a>Vereisten

-   Dynamics 365 Customer Insights-licentie
-   Adobe Experience Platform-licentie
-   Adobe Campaign Standard-licentie
-   Azure Blob Storage-account

## <a name="campaign-overview"></a>Campagne-overzicht

Laten we eens kijken naar een fictieve voorbeeldcampagne om beter te begrijpen hoe u segmenten uit doelgroepinzichten in Adobe Experience Platform kunt gebruiken.

Laten we aannemen dat uw bedrijf een maandelijkse, op abonnementen gebaseerde service biedt aan uw klanten in de Verenigde Staten. U wilt klanten identificeren waarvan het abonnement binnen acht dagen moet worden verlengd, maar die hun abonnement nog niet hebben verlengd. Om deze klanten te behouden, wilt u ze een promotieaanbieding sturen via e-mail, met Adobe Experience Platform.

In dit voorbeeld willen we de promotionele e-mailcampagne één keer uitvoeren. In dit artikel wordt niet het gebruiksscenario behandeld waarin de campagne meerdere keer wordt uitgevoerd.

## <a name="identify-your-target-audience"></a>Uw doelgroep identificeren

In ons scenario gaan we ervan uit dat de e-mailadressen van de klanten beschikbaar zijn in doelgroepinzichten en dat hun promotievoorkeuren zijn geanalyseerd om leden van het segment te identificeren.

Het [segment dat u hebt gedefinieerd in doelgroepinzichten](segments.md) wordt **ChurnProneCustomers** genoemd en u bent van plan deze klanten de e-mailpromotie te sturen.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Schermopname van de pagina Segmenten met het gemaakte segment ChurnProneCustomers.":::

De aanbiedings-e-mail die u wilt verzenden, bevat de voornaam, achternaam en einddatum van het abonnement van de klant. Klanten worden geïnformeerd over de korting die ze krijgen als ze hun abonnement verlengen voordat het afloopt.

## <a name="export-your-target-audience"></a>Uw doelgroep exporteren

Nu onze doelgroep is geïdentificeerd, kunnen we de export van doelgroepinzichten naar een Azure Blob Storage-account configureren.

### <a name="configure-a-connection"></a>Een verbinding configureren

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Azure Blob Storage** of selecteer **Instellen** in de **Azure Blob Storage**-tegel:

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Configuratietegel voor Azure Blob Storage."::: om de verbinding te configureren.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Voer een waarde in de velden **Gebruikersnaam**, **Accountsleutel** en **Container** in voor uw Blob-opslagaccount waarnaar u het segment wilt exporteren.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Schermopname van de opslagaccountconfiguratie. "::: 
   
    - Zie [De instellingen van het opslagaccount in de Azure Portal beheren](/azure/storage/common/storage-account-manage) voor meer informatie over het vinden van de Blob-opslagaccountnaam en -accountsleutel.
    - Zie voor meer informatie over het maken van een container [Een container maken](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Selecteer **Opslaan** om de verbinding te voltooien. 

### <a name="configure-an-export"></a>Een export configureren

U kunt deze export configureren als u toegang hebt tot een verbinding van dit type. Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen** om een nieuwe export te maken.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie Azure Blob Storage. Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.

1. Sluit het segment dat u u wilt exporteren. In dit voorbeeld is het **ChurnProneCustomers**​.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Schermopname van de gebruikersinterface voor segmentselectie met het segment ChurnProneCustomers geselecteerd.":::

1. Selecteer **Opslaan**.

Nadat u de exportbestemming hebt opgeslagen, vindt u deze onder **Gegevens** > **Exports**.

U kunt [het segment nu op aanvraag exporteren](export-destinations.md#run-exports-on-demand)​. De export wordt ook uitgevoerd bij elke [geplande vernieuwing](system.md).

> [!NOTE]
> Zorg ervoor dat het aantal records in het geëxporteerde segment binnen de toegestane limiet van uw Adobe Campaign Standard-licentie valt.

Geëxporteerde gegevens worden opgeslagen in de Azure Blob-opslagcontainer die u eerder hebt geconfigureerd. Het volgende mappad wordt automatisch gemaakt in uw container:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Voorbeeld: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

De *model.json* voor de geëxporteerde entiteiten bevindt zich op het niveau *%ExportDestinationName%*.

Voorbeeld: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>XDM (Experience Data Model) definiëren in Adobe Experience Platform

Voordat de geëxporteerde gegevens uit doelgroepinzichten kunnen worden gebruikt in Adobe Experience Platform, moeten we het Experience Data Model-schema definiëren en [de gegevens voor het realtime klantprofiel configureren](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials)​.

Leer [wat XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) en begrijp de [basisprincipes van schemasamenstelling](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Gegevens importeren in Adobe Experience Platform

Nu aan alle voorwaarden is voldaan, moeten we de voorbereide doelgroepgegevens van doelgroepinzichten importeren in Adobe Experience Platform.

Maak eerst [een Azure Blob Storage-bronverbinding](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started)​.    

Na het definiëren van de bronverbinding [configureert u een gegevensstroom](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) voor een batchverbinding met cloudopslag om de segmentuitvoer uit doelgroepinzichten te importeren in Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Een doelgroep maken in Adobe Campaign Standard

We gebruiken Adobe Campaign Standard om de e-mail voor deze campagne te verzenden. Nadat we de gegevens in Adobe Experience Platform hebben geïmporteerd, moeten we [een doelgroep maken](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard met de gegevens in Adobe Experience Platform.

Leer hoe u de [functie voor het maken van segmenten gebruikt](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard om een doelgroep te definiëren op basis van de gegevens in Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>De e-mail maken en verzenden met Adobe Campaign Standard

Maak de e-mailinhoud en [test en verzend](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) vervolgens uw e-mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Voorbeeld van e-mail met verlengingsaanbieding van Adobe Campaign Standard.":::
