---
title: Customer Insights-gegevens exporteren naar Facebook Ads Manager (video)
description: Leer hoe u de verbinding configureert en exporteert naar Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4b2dc2ff8e5286209bd2ec94df42e82f0944715c
ms.sourcegitcommit: 12910882ca990ec0e890ed4deaf3dac7e01621e5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/10/2021
ms.locfileid: "7904158"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>Segmentenlijst exporteren naar Facebook Ads Manager (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar Facebook Ads Manager om campagnes te maken op Facebook en Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites-for-connection"></a>Vereisten voor verbinding

- U hebt een [**Facebook Ad-account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) nodig dat een [zakelijk **Facebook-account**](https://business.facebook.com/) bevat.
- U moet een beheerder zijn voor het [**Facebook Ads-account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Bekende beperkingen

- Tot 10 miljoen klantprofielen per export naar Facebook Ads Manager.
- Exporteren naar Facebook Ads Manager is beperkt tot segmenten.
- Maak of update in Facebook alleen aangepaste doelgroepen van het type *klantenlijst*.
- Het exporteren van segmenten met in totaal 10 miljoen klantprofielen kan tot 90 minuten duren.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Verbinding instellen met Facebook Ads Manager

Voordat gebruikers een export kunnen maken, moet een beheerder de verbinding met de service configureren en inzenders toestaan de verbinding te gebruiken.

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Facebook Ads Manager** om de verbinding te configureren.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Verifiëren met Facebook Ads: 

   1. Selecteer **Doorgaan met Facebook** om u aan te melden bij uw Facebook Ads-account.

   1. Geef **ads_management** een machtiging na verificatie met Facebook.

   1. Selecteer het **Facebook Ads-account** waarmee u wilt werken.

   1. Selecteer een **Bestaande aangepaste doelgroep** uit de vervolgkeuzelijst of maak een **Nieuwe aangepaste doelgroep**. Zie [**Doelgroepen in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494) voor meer informatie.
      > [!NOTE]
      > U kunt op Facebook alleen aangepaste doelgroepen maken of bijwerken van het type *klantenlijst* met deze export. In sommige gevallen ziet u aangepaste doelgroepen van verschillende typen in de vervolgkeuzelijst. Als een ander type dan *klantenlijst* wordt geselecteerd, resulteert dit in een mislukte export. 

1. Bekijk **Gegevensprivacy en naleving** en selecteer **Ik ga akkoord**.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

U kunt deze export configureren als u toegang hebt tot een verbinding van dit type. Zie [Machtigingen die nodig zijn om een export te configureren](export-destinations.md#set-up-a-new-export) voor meer informatie.

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Bestemming toevoegen** om een nieuwe export te maken. 

1. Kies in **Verbinding voor export** een verbinding uit de sectie **Facebook Ads Manager**. Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.

1. Selecteer in het veld **Uw sleutel-id kiezen** de optie **E-mail**, **Naam en adres** of **Telefoon** om naar Facebook Ads Manager te verzenden. 

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**.

1. Wijs de corresponderende kenmerken van uw geharmoniseerde klantentiteit toe aan de geselecteerde sleutel-id.
   > [!TIP]
   > U hebt de beste kans op een overeenkomst als u **E-mail** als sleutel-id selecteert. De matching kan verbeteren door toevoeging van extra id's.

1. Selecteer **Kenmerk toevoegen** om meer kenmerken toe te wijzen om naar Facebook Ads Manager te verzenden. Kenmerken van Facebook Ads Manager komen overeen met de volgende gebruikersvriendelijke namen: **FN** = **Voornaam**, **LN** = **Achternaam**, **FI** = **Eerste initiaal**, **PHONE** = **Telefoon**, **GEN** = **Geslacht**, **DOB** = **Geboortedatum**, **ST** = **Staat**, **CT** = **Plaats**, **ZIP** = **Postcode**, **COUNTRY** = **Land/regio**

1. Selecteer de segmenten die u wilt exporteren.

1. Selecteer **Opslaan**.

Als u een export opslaat, wordt de export niet onmiddellijk uitgevoerd.

De export wordt uitgevoerd met elke [geplande vernieuwing](system.md#schedule-tab). 

U kunt ook [gegevens op aanvraag exporteren](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens naar Facebook Ads Manager te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens op uw instructie overdragen, maar u bent ervoor verantwoordelijk dat Facebook Ads voldoet aan uw privacy- of beveiligingsverplichtingen. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.
Uw Dynamics 365 Customer Insights-beheerder kan deze exportbestemming op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
