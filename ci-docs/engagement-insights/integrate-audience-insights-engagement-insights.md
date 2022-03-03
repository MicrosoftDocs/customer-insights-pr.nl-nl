---
title: Een koppeling tot stand brengen tussen doelgroepinzichten en betrokkenheidsinzichten
description: Maak een actieve koppeling tussen doelgroepinzichten en betrokkenheidsinzichten om het delen van gegevens in twee richtingen mogelijk te maken.
ms.date: 09/08/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 56adc206d83bc6e34a55f11383393b5ac66da531
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229866"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>Een koppeling tot stand brengen tussen doelgroepinzichten en betrokkenheidsinzichten

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

De integratie tussen betrokkenheidsinzichten en doelgroepinzichten koppelt omgevingen met beide mogelijkheden en maakt het mogelijk om gegevens in beide richtingen tussen hen te delen.

Gebruik uniforme profielen en segmenten uit doelgroepinzichten voor meer analyse-opties in betrokkenheidsinzichten. Exporteer gebeurtenissen met een hoge zakelijke waarde op basis van betrokkenheidsinzichten. Gebruik deze gebeurtenissen om gegevens toe te voegen aan geharmoniseerde profielen in doelgroepinzichten.

## <a name="prerequisites"></a>Vereisten

- Profielen voor doelgroepinzichten moeten worden opgeslagen in een Azure Data Lake Storage-account waarvan u de eigenaar bent of in een door [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro) beheerd data lake. 
- De omgeving van uw doelgroepinzichten moet een gekoppelde Dataverse-omgeving hebben. Als in die omgeving ook Dataverse wordt gebruikt voor gegevensopslag, moet u de optie **Gegevens delen inschakelen** in doelgroepinzichten selecteren. Zie voor meer informatie [Een omgeving in doelgroepeninzichten maken en configureren](../audience-insights/create-environment.md).
- U hebt beheerdersmachtigingen nodig voor zowel de omgeving voor betrokkenheidsinzichten als de omgeving voor doelgroepinzichten.
- Gekoppelde omgevingen moeten zich in dezelfde geografische regio bevinden.

> [!NOTE]
> - Als uw abonnement op doelgroepinzichten een proefversie is die gebruikmaakt van een intern beheerd data lake voor doelgroepinzichten, neemt u contact op met [pirequest@microsoft.com](mailto:pirequest@microsoft.com) voor assistentie. 
> - Als uw omgeving voor doelgroepinzichten uw eigen Azure Data Lake Storage gebruikt om gegevens op te slaan, moet u een Azure-serviceprincipal voor betrokkenheidsinzichten toevoegen aan uw opslagaccount. Ga naar [Verbinding met een Azure Data Lake Storage-account maken met een Azure-serviceprincipal voor doelgroepinzichten](../audience-insights/connect-service-principal.md) voor meer informatie. 


## <a name="create-an-environment-link"></a>Een omgevingskoppeling maken

U kunt een omgevingskoppeling maken door de instellingen voor **Beheerder** > **Omgeving** bij te werken in betrokkenheidsinzichten.

**Een actieve koppeling tot stand brengen tussen doelgroepinzichten en betrokkenheidsinzichten**

1. Selecteer op de pagina **Omgevingsbeheerder** het tabblad **Omgevingen koppelen**.

    :::image type="content" source="media/integrate1.png" alt-text="Een omgeving instellen.":::

1. Selecteer **Omgevingen instellen** in de linkerbovenhoek of onder aan het scherm.

     :::image type="content" source="media/integrate2.png" alt-text="Een omgeving voor doelgroepinzichten selecteren.":::

1. Selecteer een omgeving voor doelgroepinzichten en selecteer daarna **Volgende** om te voltooien. Nu kunt u optionele functies selecteren voor de gekoppelde omgevingen.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>Geharmoniseerde profielkenmerken en segmenten instellen voor doelgroepinzichten

Nadat u omgevingen hebt gekoppeld, kunt u optionele functies selecteren voor de gekoppelde omgevingen. Deze functies maken geharmoniseerde profielkenmerken en segmenten van doelgroepinzichten mogelijk voor interactieve analyse van klantgegevens.

> [!IMPORTANT]
> Als u segmenten van doelgroepinzichten in betrokkenheidsinzichten wilt laten verschijnen, moet u eerst [samenvoeg- en downstreamprocessen uitvoeren](../audience-insights/merge-entities.md). Downstreamprocessen zijn belangrijk omdat ze een unieke tabel genereren die segmenten van doelgroepinzichten voorbereidt om te worden gedeeld met betrokkenheidsinzichten. (Als een systeemvernieuwing is gepland, omvat deze automatisch downstreamprocessen.)

**Webgegevens analyseren in betrokkenheidsinzichten**

1. Schakel op de pagina **Omgevingsbeheerder** de wisseloptie **Gegevens uit doelgroepinzichten delen met betrokkenheidsinzichten** in en selecteer daarna **Volgende**.

    :::image type="content" source="media/integrate4.png" alt-text="Functies selecteren.":::

1. Selecteer de kenmerken van de geharmoniseerde profielen die dimensies worden in betrokkenheidsinzichten. (Niet alle kenmerken zijn bruikbare dimensies. Het is bijvoorbeeld niet waarschijnlijk dat u **Voornaam** of **Achternaam** nodig hebt als kenmerk voor analyse van uw websitegebeurtenissen.)

    :::image type="content" source="media/integrate5.png" alt-text="Samengestelde afmetingen.":::

   >[!NOTE]
   > Alle profielkenmerken voor doelgroepinizhten die id's vertegenwoordigen (zoals **Id** en **Alternatieve id**) worden uit de beschikbare kenmerken gefilterd en worden dimensies in betrokkenheidsinzichten.

1. Als u klaar bent met het selecteren van kenmerken, selecteert u **Volgende**.
1. Voeg gebruikers toe die de profieldimensies en segmenten van doelgroepinzichten kunnen bekijken in betrokkenheidsinzichten.

    :::image type="content" source="media/integrate6.png" alt-text="Toegang tot klantgegevens beheren.":::

   > [!IMPORTANT]
   > Als u in deze stap niet expliciet gebruikers toevoegt, worden de gegevens verborgen voor gebruikers in betrokkenheidsinzichten.
   > Als u segmenten van doelgroepinzichten in betrokkenheidsinzichten wilt laten verschijnen, moet u eerst [samenvoeg- en downstreamprocessen uitvoeren](../audience-insights/merge-entities.md). Downstreamprocessen zijn belangrijk omdat ze een unieke tabel genereren die segmenten van doelgroepinzichten voorbereidt om te worden gedeeld met betrokkenheidsinzichten. (Als een systeemvernieuwing is gepland, omvat deze automatisch downstreamprocessen.)

1. Controleer uw selectie en selecteer vervolgens **Voltooien**.

    :::image type="content" source="media/integrate7.png" alt-text="Instellingen voor klantgegevens controleren.":::

## <a name="export-refined-events-to-audience-insights"></a>Verrijkte gebeurtenissen exporteren naardoelgroepinzichten

Nadat u een koppeling tussen omgevingen tot stand hebt gebracht, kunt u verrijkte gebeurtenissen van betrokkenheidsinzichten exporteren naar doelgroepinzichten en deze opnemen als een nieuwe gegevensbron. 

Ga naar [Webgegevens uit betrokkenheidsinzichten integreren met doelgroepinzichten](../audience-insights/integrate-engagement-insights.md) voor meer informatie.

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
