---
title: Relaties tussen entiteiten en entiteitspaden
description: Maak en beheer relaties tussen entiteiten uit meerdere gegevensbronnen.
ms.date: 09/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: c639cfca30cf1b57ada7d728311210b7210a37ac
ms.sourcegitcommit: f72d5b86dfdc7282c6c1918b1ab3962d7a1c9852
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/27/2021
ms.locfileid: "7557346"
---
# <a name="relationships-between-entities"></a>Relaties tussen entiteiten

Relaties verbinden entiteiten en definiëren een grafiek van uw gegevens wanneer entiteiten een gemeenschappelijke id, een refererende sleutel, delen. Er kan vanuit de ene entiteit naar de andere worden verwezen met deze refererende sleutel. Verbonden entiteiten maken het definiëren van segmenten en meetcriteria mogelijk op basis van meerdere gegevensbronnen.

Er zijn drie typen relaties: 
- Niet-bewerkbaar systeemrelaties, die door het systeem worden gemaakt als onderdeel van het gegevensharmonisatieproces
- Niet-bewerkbare overgenomen relaties, die automatisch worden gemaakt op basis van het opnemen van gegevensbronnen 
- Bewerkbare aangepaste relaties, die worden gemaakt en geconfigureerd door gebruikers

## <a name="non-editable-system-relationships"></a>Niet-bewerkbare systeemrelaties

Tijdens de gegevensharmonisatie worden systeemrelaties automatisch gemaakt op basis van intelligente afstemming. Deze relaties helpen de klantprofielrecords te relateren aan overeenkomstige records. In het volgende diagram wordt het maken van drie systeemgebaseerde relaties geïllustreerd. De klantentiteit wordt gematcht met andere entiteiten om de geharmoniseerde entiteit *Klant* te maken.

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagram met relatiepaden voor de klantentiteit met drie 1-n-relaties.":::

- De **relatie *CustomerToContact*** is gemaakt tussen de entiteit *Klant* en de entiteit *Contactpersoon*. De entiteit *Klant* krijgt het sleutelveld **Contact_contactID** om een relatie tot stand te brengen met het sleutelveld **contactID** van de entiteit *Contactpersoon*.
- De **relatie *CustomerToAccount*** is gemaakt tussen de entiteit *Klant* en de entiteit *Account*. De entiteit *Klant* krijgt het sleutelveld **Account_accountID** om een relatie tot stand te brengen met het sleutelveld **accountID** van de entiteit *Account*.
- De **relatie *CustomerToWebAccount*** is gemaakt tussen de entiteit *Klant* en de entiteit *WebAccount*. De entiteit *Klant* krijgt het sleutelveld **WebAccount_webaccountID** om een relatie tot stand te brengen met het sleutelveld **webaccountID** van de entiteit *WebAccount*.

## <a name="non-editable-inherited-relationships"></a>Niet-bewerkbare overgenomen relaties

Tijdens het gegevensopnameproces controleert het systeem gegevensbronnen op bestaande relaties. Als er geen relatie bestaat, maakt het systeem deze automatisch aan. Deze relaties worden ook gebruikt in downstreamprocessen.

## <a name="create-a-custom-relationship"></a>Een aangepaste relatie maken

Relatie bestaat uit een *bronentiteit* met de refererende sleutel en een *doelentiteit* waarnaar de refererende sleutel van de bronentiteit verwijst. 

1. Ga in doelgroepinzichten naar **Gegevens** > **Relaties**.

2. Selecteer **Nieuwe relatie**.

3. Geef in het deelvenster **Nieuwe relatie** de volgende informatie op:

   :::image type="content" source="media/relationship-add.png" alt-text="Zijvenster Nieuwe relatie met lege invoervelden.":::

   - **Relatienaam**: naam die het doel van de relatie weergeeft. Voorbeeld: CustomerToSupportCase.
   - **Beschrijving**: de beschrijving van de relatie.
   - **Bronentiteit**: entiteit die wordt gebruikt als bron in de relatie. Voorbeeld: SupportCase.
   - **Doelentiteit**: entiteit die wordt gebruikt als doel in de relatie. Voorbeeld: Customer.
   - **Bronkardinaliteit**: geef de kardinaliteit van de bronentiteit op. Kardinaliteit beschrijft het aantal mogelijke elementen in een set. Het heeft altijd betrekking op de doelkardinaliteit. U kunt kiezen tussen **Een** en **Veel**. Alleen veel-op-één- en één-op-één-relaties worden ondersteund.  
     - Veel-op-één: meerdere bronrecords kunnen betrekking hebben op één doelrecord. Voorbeeld: meerdere ondersteuningsaanvragen van een enkele klant.
     - Eén-op-één: een enkele bronrecord heeft betrekking op één doelrecord. Voorbeeld: één loyaliteits-id voor een enkele klant.

     > [!NOTE]
     > Veel-op-veel-relaties kunnen worden gemaakt met behulp van twee veel-op-één-relaties en een koppelingsentiteit, die de bronentiteit en de doelentiteit verbindt.

   - **Doelkardinaliteit**: selecteer de kardinaliteit van de doelentiteitsrecords. 
   - **Bronsleutelveld**: het veld voor de refererende sleutel in de bronentiteit. Voorbeeld: SupportCase kan CaseID gebruiken als veld voor refererende sleutel.
   - **Doelsleutelveld**: het sleutelveld van de doelentiteit. Voorbeeld: Customer zou het sleutelveld **CustomerID** kunnen gebruiken.

4. Selecteer **Opslaan** om de aangepaste relatie te maken.

## <a name="view-relationships"></a>Relaties weergeven

Op de pagina Relaties worden alle relaties vermeld die zijn gemaakt. Elke rij vertegenwoordigt een relatie, die ook details bevat over de bronentiteit, de doelentiteit en de kardinaliteit. 

:::image type="content" source="media/relationships-list.png" alt-text="Lijst met relaties en opties in de actiebalk van de pagina Relaties.":::

Deze pagina biedt een reeks opties voor bestaande en nieuwe relaties: 
- **Nieuwe relatie:** [maak een aangepaste relatie](#create-a-custom-relationship).
- **Visualizer**: [verken de relatievisualizer](#explore-the-relationship-visualizer) om een netwerkdiagram te zien van de bestaande relaties en hun kardinaliteit.
- **Filteren op**: kies het type relaties om in de lijst weer te geven.
- **Relaties zoeken**: gebruik een op tekst gebaseerde zoekopdracht op eigenschappen van de relaties.

### <a name="explore-the-relationship-visualizer"></a>De relatievisualizer verkennen

De relatievisualizer geeft een netwerkdiagram van de bestaande relaties tussen verbonden entiteiten en hun kardinaliteit weer. Het visualiseert ook het relatiepad.

Om de weergave aan te passen, kunt u de positie van de vakken wijzigen door ze op het canvas te slepen.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Schermopname van het netwerkdiagram van de relatievisualizer met verbindingen tussen gerelateerde entiteiten.":::

Beschikbare opties: 
- **Exporteren als afbeelding**: sla de huidige weergave op als een afbeeldingsbestand.
- **Wijzigen naar horizontale/verticale indeling**: wijzig de uitlijning van de entiteiten en relaties.
- **Bewerken**: werk eigenschappen van aangepaste relaties bij in het bewerkingsvenster en sla de wijzigingen op.

## <a name="relationship-paths"></a>Relatiepaden

Een relatiepad beschrijft de entiteiten die zijn verbonden met relaties tussen een bron- en een doelentiteit. Het wordt gebruikt bij het maken van een segment of een meting die andere entiteiten dan de geharmoniseerde profielentiteit omvat en er zijn meerdere opties om de geharmoniseerde profielentiteit te bereiken. 

Een relatiepad informeert het systeem over welke relaties toegang moeten krijgen tot de uniforme profielentiteit. Verschillende relatiepaden kunnen verschillende resultaten opleveren.

Zo heeft de entiteit *eCommerce_eCommercePurchases* bijvoorbeeld de volgende relaties met de geharmoniseerde profielentiteit *Klant*:

- eCommerce_eCommercePurchases > Klant
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Klant
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Klant 

Een relatiepad bepaalt welke entiteiten u kunt gebruiken bij het maken van regels voor metingen of segmenten. Het kiezen van de optie met het langste relatiepad zal waarschijnlijk minder resultaten opleveren omdat de overeenkomende records deel moeten uitmaken van alle entiteiten. In dit voorbeeld moet een klant goederen hebben gekocht via e-commerce (eCommerce_eCommercePurchases), bij een verkooppunt (POS_posPurchases) en deelnemen aan ons loyaliteitsprogramma (loyaltyScheme_loyCustomers). Als u de eerste optie kiest, krijgt u waarschijnlijk meer resultaten omdat klanten maar in één extra entiteit hoeven te bestaan.

### <a name="direct-relationship"></a>Directe relatie

Een relatie wordt geclassificeerd als een **directe relatie** wanneer een bronentiteit een relatie heeft met een doelentiteit met slechts één relatie.

Als bijvoorbeeld een activiteitsentiteit genaamd *eCommerce_eCommercePurchases* verbinding maakt met een doelentiteit *eCommerce_eCommerceContacts* alleen via *ContactId*, is het een directe relatie.

:::image type="content" source="media/direct_Relationship.png" alt-text="Bronentiteit maakt rechtstreeks verbinding met doelentiteit.":::

#### <a name="multi-path-relationship"></a>Relatie met meerdere paden

Een **relatie met meerdere paden** is een speciaal type directe relatie die een bronentiteit verbindt met meer dan één doelentiteit.

Als bijvoorbeeld een activiteitsentiteit genaamd *eCommerce_eCommercePurchase* een relatie heeft met twee doelentiteiten, zowel *eCommerce_eCommerceContacts* en *loyaltyScheme_loyCustomers*, is het een relatie met meerdere paden.

:::image type="content" source="media/multi-path_relationship.png" alt-text="Bronentiteit maakt rechtstreeks verbinding met meer dan één doelentiteit via een relatie met meerdere hops.":::

### <a name="indirect-relationship"></a>Indirecte relatie

Een relatie wordt geclassificeerd als een **indirecte relatie** wanneer een bronentiteit een relatie heeft met een of meer extra entiteiten voordat het een relatie heeft met een doelentiteit.

#### <a name="multi-hop-relationship"></a>Relatie met meerdere hops

Een *relatie met meerdere hops* is een *indirecte relatie* waarmee u een bronentiteit kunt verbinden met een doelentiteit via een of meer andere intermediaire entiteiten.

Als bijvoorbeeld een activiteitsentiteit genaamd *eCommerce_eCommercePurchasesWest* verbinding maakt met een tussenliggende entiteit genaamd *eCommerce_eCommercePurchasesEast* en vervolgens verbinding maakt met een doelentiteit genaamd *eCommerce_eCommerceContacts*, is het een relatie met meerdere hops.

:::image type="content" source="media/multi-hop_relationship.png" alt-text="Bronentiteit maakt rechtstreeks verbinding met een doelentiteit met een tussenliggende entiteit.":::

### <a name="multi-hop-multi-path-relationship"></a>Relatie met meerdere hops, meerdere paden

Relaties met meerdere hops en meerdere paden kunnen samen worden gebruikt om **relaties met meerdere hops, meerdere paden** te maken. Dit speciale type combineert de functies van **relaties met meerdere hops** en **meerdere paden**. Hiermee kunt u verbinding maken met meer dan één doelentiteit terwijl u tussenliggende entiteiten gebruikt.

Als bijvoorbeeld een activiteitsentiteit genaamd *eCommerce_eCommercePurchasesWest* verbinding maakt met een tussenliggende entiteit genaamd *eCommerce_eCommercePurchasesEast* en vervolgens verbinding maakt met twee doelentiteiten genaamd *eCommerce_eCommerceContacts* en *loyaltyScheme_loyCustomers* is het een relatie met meerdere hops en meerdere paden.

:::image type="content" source="media/multi-hop_multi-path_relationship.png" alt-text="Bronentiteit maakt rechtstreeks verbinding met de één doelentiteit en maakt verbinding met een andere doelentiteit via een tussenliggende entiteit.":::

## <a name="manage-existing-relationships"></a>Bestaande relaties beheren 

Op de pagina Relaties wordt elke relatie weergegeven door een rij. 

Selecteer een relatie en kies een van de volgende opties: 
 
- **Bewerken**: werk eigenschappen van aangepaste relaties bij in het bewerkingsvenster en sla de wijzigingen op.
- **Verwijderen**: aangepaste relaties verwijderen.
- **Weergeven**: door het systeem gemaakte en overgenomen relaties bekijken. 

## <a name="next-step"></a>Volgende stap

Systeem- en aangepaste relaties worden gebruikt om [segmenten](segments.md) en [metingen](measures.md) te maken gebaseerd op meerdere gegevensbronnen die zich niet langer in silo's bevinden.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
