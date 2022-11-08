---
title: Segmenten exporteren naar Facebook Ads Manager (preview) (bevat video)
description: Leer hoe u de verbinding configureert en exporteert naar Facebook Ads Manager.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c7a4b1be1c959d70fad929b56452169b40e5b592
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724582"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Segmenten exporteren naar Facebook Ads Manager (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar Facebook Ads Manager om campagnes te maken op Facebook en Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>Vereisten

- Een [account voor Facebook Ads](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) dat een [zakelijk Facebook-account](https://business.facebook.com/) bevat.
- Beheerdersbevoegdheden voor het account voor [Facebook Ads](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).
- Aangepaste publieksvoorwaarden moeten worden geaccepteerd door de gebruiker die de verbinding instelt in Customer Insights.

## <a name="known-limitations"></a>Bekende beperkingen

- Maximaal 10 miljoen klantprofielen per export naar Facebook Ads Manager en dit kan tot 90 minuten duren.
- Alleen segmenten.
- Facebook Ads-integratie ondersteunt geen gebruikers met meer dan 25 advertentieaccounts.
- Alleen type Facebook-*klantenlijst* in [aangepaste doelgroepen](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
  > [!NOTE]
  > In sommige gevallen ziet u mogelijk aangepaste doelgroepen van verschillende typen in de vervolgkeuzelijst. Als u een ander type dan *klantenlijst* selecteert, mislukt de export.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Verbinding instellen met Facebook Ads Manager

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **Facebook Ads Manager**.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. [Inzenders toestaan om de verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Verifiëren met Facebook Ads:

   1. Selecteer **Doorgaan met Facebook** om u aan te melden bij uw Facebook Ads-account.

   1. Geef **ads_management** een machtiging na verificatie met Facebook.

   1. Selecteer het **Facebook Ads-account** waarmee u wilt werken.

   1. Selecteer een **Bestaande aangepaste doelgroep** uit de vervolgkeuzelijst of maak een **Nieuwe aangepaste doelgroep**.

1. Bekijk [Gegevensprivacy en naleving](connections.md#data-privacy-and-compliance) en selecteer **Ik ga akkoord**.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen**.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie Facebook Ads Manager. Neem contact op met een beheerder als er geen verbinding beschikbaar is.

1. Voer de naam in voor de export.

1. Selecteer in het veld **Gegevens verbinden** de optie **E-mail**, **Naam en adres** of **Telefoon** om naar Facebook Ads Manager te verzenden.

1. Wijs de corresponderende kenmerken van uw geharmoniseerde klantentiteit toe aan de geselecteerde sleutel-id.
   > [!TIP]
   > U hebt de beste kans op een overeenkomst als u **E-mail** als sleutel-id selecteert. De matching kan verbeteren door toevoeging van extra id's.

1. Selecteer **Kenmerk toevoegen** om meer kenmerken toe te wijzen om naar Facebook Ads Manager te verzenden. Kenmerken van Facebook Ads Manager komen overeen met de volgende gebruikersvriendelijke namen: **FN** = **Voornaam**, **LN** = **Achternaam**, **FI** = **Eerste initiaal**, **PHONE** = **Telefoon**, **GEN** = **Geslacht**, **DOB** = **Geboortedatum**, **ST** = **Staat**, **CT** = **Plaats**, **ZIP** = **Postcode**, **COUNTRY** = **Land/regio**

1. Selecteer de segmenten die u wilt exporteren.

1. Selecteer **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
