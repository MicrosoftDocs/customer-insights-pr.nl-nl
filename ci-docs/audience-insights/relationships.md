---
title: Relaties tussen entiteiten en entiteitspaden
description: Maak en beheer relaties tussen entiteiten uit meerdere gegevensbronnen.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 295c372bb452e7c40aa950506dc494d4a2de1108
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405511"
---
# <a name="relationships-between-entities"></a>Relaties tussen entiteiten

Relaties helpen u bij het verbinden van entiteiten en het genereren van een grafiek van uw gegevens wanneer entiteiten een gemeenschappelijke identificatie (externe sleutel) delen waarnaar van de ene entiteit naar de andere kan worden verwezen. Met verbonden entiteiten kunt u segmenten en meetcriteria definiëren op basis van meerdere gegevensbronnen.

Er zijn twee typen relaties. Niet-bewerkbaar systeemrelaties, die automatisch worden gemaakt, en aangepaste relaties, die worden gemaakt en geconfigureerd door gebruikers.

Tijdens de afstemmings- en samenvoegingsprocessen worden achter de schermen systeemrelaties gemaakt op basis van intelligente afstemming. Deze relaties helpen de klantprofielrecords te relateren aan de records van andere overeenkomstige entiteiten. Het volgende diagram illustreert het maken van drie systeemrelaties wanneer de klantentiteit wordt afgestemd met extra entiteiten om de uiteindelijke entiteit Klantprofiel te produceren.

> [!div class="mx-imgBorder"]
> ![Het maken van relaties](media/relationships-entities-merge.png "Het maken van relaties")

- **De relatie *CustomerToContact*** is gemaakt tussen de entiteit Klant en de entiteit Contactpersoon. De entiteit Klant krijgt het sleutelveld **Contact_contactId** om een relatie tot stand te brengen met het sleutelveld **contactId** van de entiteit Contactpersoon.
- **De relatie _CustomerToAccount_** is gemaakt tussen de entiteit Klant en de entiteit Account. De entiteit Klant krijgt het sleutelveld **Account_accountId** om een relatie tot stand te brengen met het sleutelveld **accountId** van de entiteit Account.
- **De relatie _CustomerToWebAccount_** is gemaakt tussen de entiteit Klant en de entiteit WebAccount. De entiteit Klant krijgt het sleutelveld **WebAccount_webaccountId** om een relatie tot stand te brengen met het sleutelveld **webaccountId** van de entiteit WebAccount.

## <a name="create-a-relationship"></a>Een relatie maken

Definieer aangepaste relaties op de pagina **Relaties**. Elke relatie bestaat uit een bronentiteit (de entiteit die de externe sleutel bevat) en een doelentiteit (de entiteit waarnaar de externe sleutel van de bronentiteit verwijst).

1. Ga in doelgroepinzichten naar **Gegevens** > **Relaties**.

2. Selecteer **Nieuwe relatie**.

3. Geef in het deelvenster **Relatie toevoegen** de volgende informatie op:

   > [!div class="mx-imgBorder"]
   > ![Relatiedetails invoeren](media/relationships-add.png "Relatiedetails invoeren")

   - **Relatienaam**: naam die het doel van de relatie weergeeft (bijvoorbeeld **AccountWebLogs**).
   - **Beschrijving**: de beschrijving van de relatie.
   - **Bronentiteit**: selecteer de entiteit die wordt gebruikt als bron in de relatie (bijvoorbeeld WebLog).
   - **Kardinaliteit**: selecteer de kardinaliteit van de bronentiteitsrecords. "Veel" betekent bijvoorbeeld dat meerdere Weblog-records gerelateerd zijn aan één WebAccount.
   - **Bronsleutelveld**: dit vertegenwoordigt het veld met de externe sleutel in de bronentiteit. WebLog heeft bijvoorbeeld het veld met de externe sleutel **accountId**.
   - **Doelentiteit**: selecteer de entiteit die wordt gebruikt als doel in de relatie (bijvoorbeeld WebAccount).
   - **Doelkardinaliteit**: selecteer de kardinaliteit van de doelentiteitsrecords. "Een" betekent bijvoorbeeld dat meerdere Weblog-records zijn gerelateerd aan één WebAccount.
   - **Doelsleutelveld**: dit veld vertegenwoordigt het sleutelveld van de doelentiteit. WebAccount heeft bijvoorbeeld het sleutelveld **accountId**.

> [!NOTE]
> Alleen veel-op-één- en één-op-één-relaties worden ondersteund. Veel-op-veel-relaties kunnen worden gemaakt met behulp van twee veel-op-één-relaties en een koppelingsentiteit (een entiteit die wordt gebruikt om de bronentiteit en de doelentiteit met elkaar te verbinden).

## <a name="delete-a-relationship"></a>Een relatie verwijderen

1. Ga in doelgroepinzichten naar **Gegevens** > **Relaties**.

2. Schakel selectievakjes in voor de relaties die u wilt verwijderen.

3. Selecteer **Verwijderen** boven aan de tabel **Relaties**.

4. Bevestig de verwijdering.

## <a name="next-step"></a>Volgende stap

Systeem- en aangepaste relaties worden gebruikt om segmenten te maken op basis van meerdere gegevensbronnen die niet langer geïsoleerd zijn. Zie [Segmenten](segments.md) voor meer informatie.
