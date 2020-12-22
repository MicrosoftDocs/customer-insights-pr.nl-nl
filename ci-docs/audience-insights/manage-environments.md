---
title: Omgevingen maken en beheren
description: Ontdek hoe u zich aanmeldt voor de service en hoe u omgevingen beheert.
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644127"
---
# <a name="manage-environments"></a>Omgevingen beheren

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

In dit artikel wordt uitgelegd hoe u een nieuwe organisatie maakt en hoe u een omgeving inricht.

## <a name="sign-up-and-create-an-organization"></a>Aanmelden en een organisatie maken

1. Ga naar de website [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).

2. Selecteer **Aan de slag**.

3. Kies het gewenste aanmeldingsscenario en selecteer de bijbehorende koppeling.

4. Accepteer de algemene voorwaarden en selecteer **Doorgaan** om te beginnen met het maken van de organisatie.

5. Nadat de omgeving is gemaakt, wordt u doorgestuurd naar [Customer Insights](https://home.ci.ai.dynamics.com).

6. Gebruik de demo-omgeving om de app te verkennen of maak een nieuwe omgeving door de stappen in de volgende sectie te volgen.

7. Nadat u de omgevingsinstellingen hebt opgegeven, selecteert u **Maken**.

8. Nadat de omgeving is gemaakt, wordt u aangemeld.

## <a name="create-an-environment-in-an-existing-organization"></a>Een omgeving maken in een bestaande organisatie

U kunt op twee manieren een nieuwe omgeving maken. U kunt een geheel nieuwe configuratie opgeven of u kunt enkele configuratie-instellingen uit een bestaande omgeving kopiëren.

Een omgeving maken:

1. Selecteer het symbool **instellingen** in de kop van de app.

1. Selecteer **Nieuwe omgeving**.

   > [!div class="mx-imgBorder"]
   > ![Omgevingsinstellingen](media/environment-settings-dialog.png)

1. Selecteer **Nieuwe omgeving** in het dialoogvenster **Nieuwe omgeving maken**.

   Als u [gegevens wilt kopiëren uit de huidige omgeving](#additional-considerations-for-copy-configuration-preview), selecteert u **Kopiëren uit bestaande omgeving**. U ziet een lijst met alle beschikbare omgevingen in uw organisatie waaruit u gegevens kunt kopiëren.

1. Geef de volgende details op:
   - **Naam**: de naam voor deze omgeving. Dit veld is al ingevuld als u hebt gekopieerd vanuit een bestaande omgeving, maar u kunt dit wijzigen.
   - **Regio**: de regio waarin de service wordt geïmplementeerd en gehost.
   - **Type**: selecteer of u een productie- of sandbox-omgeving wilt maken.

2. U kunt desgewenst het **Geavanceerde instellingen** inschakelen:

   - **Alle gegevens opslaan naar**: geeft aan waar u de uitvoergegevens wilt opslaan die zijn gegenereerd vanuit Customer Insights. U hebt twee opties: **Opslag Customer Insights** (een Azure Data Lake beheerd door het Customer Insights-team) en **Azure Data Lake Storage Gen2** (uw eigen Azure Data Lake Storage). Standaard is de opslagoptie Customer Insights geselecteerd.

   > [!NOTE]
   > Door gegevens op te slaan in Azure Data Lake Storage stemt u ermee in dat gegevens worden overgebracht naar en opgeslagen in de juiste geografische locatie voor dat Azure Storage-account, die kan afwijken van waar gegevens zijn opgeslagen in Dynamics 365 Customer Insights. Meer informatie vindt u in het Dynamics 365 Customer Insights. [Meer informatie op het Microsoft Trust Center.](https://www.microsoft.com/trust-center)
   >
   > Momenteel worden opgenomen entiteiten altijd opgeslagen in het beheerde data lake van Customer Insights.
   > We ondersteunen alleen Azure Data Lake Gen2-opslagaccounts uit dezelfde Azure-regio die u hebt geselecteerd bij het maken van de omgeving.
   > We ondersteunen alleen opslagaccounts waarvoor Azure Data Lake Gen2 Hierarchical Name Space (HNS) is ingeschakeld.

   - Voor de Azure Data Lake Storage Gen2-oplossing kunt u kiezen tussen een resource-optie en een abonnementsoptie voor verificatie. Zie [Doelgroepinzichten verbinden met een Azure Data Lake Storage Gen2-account met een Azure Service Principal](connect-service-principal.md) voor meer informatie. De naam van de **Container** kan niet worden gewijzigd en is "customerinsights".
   
   - Als u [voorspellingen](predictions.md) wilt gebruiken, voert u de URL van het Common Data Service-exemplaar in het veld **Serveradres** in onder **Voorspellingen gebruiken**.

   Wanneer u processen uitvoert, zoals het opnemen van gegevens of het maken van segmenten, worden overeenkomstige mappen gemaakt in het opslagaccount dat u hierboven hebt opgegeven. Gegevensbestanden en model.json-bestanden worden op basis van het proces dat u uitvoert gemaakt en toegevoegd aan de respectievelijke submappen.

   Als u meerdere omgevingen van Customer Insights maakt en ervoor kiest de uitvoerentiteiten van die omgevingen op te slaan in uw opslagaccount, worden voor elke omgeving aparte mappen gemaakt met ci_<environmentid> in de container.

### <a name="additional-considerations-for-copy-configuration-preview"></a>Aanvullende overwegingen voor kopieerconfiguratie (preview)

De volgende configuratie-instellingen worden gekopieerd:

- Functieconfiguraties
- Opgenomen/geïmporteerde gegevensbronnen
- Configuratie van gegevensunificatie (Toewijzing, Overeenkomst, Samenvoeging)
- Segmenten
- Metingen
- Relaties
- Activiteiten
- Index voor zoeken en filteren
- Exportbestemmingen
- Geplande vernieuwing
- Verrijkingen
- Modelbeheer
- Roltoewijzingen

De volgende instellingen worden *niet* gekopieerd:

- Klantprofielen.
- Referenties voor gegevensbron. U moet de referenties voor elke gegevensbron opgeven en de gegevensbronnen handmatig vernieuwen.
- Gegevensbronnen uit Common Data Model-map en beheerd lake voor Common Data Service. U moet die gegevensbronnen handmatig maken met dezelfde naam als in de bronomgeving.

Wanneer u een omgeving kopieert, ziet u een bevestigingsbericht dat de nieuwe omgeving is gemaakt. Selecteer **Ga naar gegevensbronnen** om de lijst met gegevensbronnen te zien.

Alle gegevensbronnen hebben de status **Referenties vereist**. Bewerk de gegevensbronnen en voer de referenties in om ze te vernieuwen.

> [!div class="mx-imgBorder"]
> ![Gekopieerde gegevensbronnen](media/data-sources-copied.png)

Ga na het vernieuwen van de gegevensbronnen naar **Gegevens** > **Harmoniseren**. Hier vindt u instellingen uit de bronomgeving. Bewerk deze indien nodig of selecteer **Uitvoeren** om het proces voor gegevensharmonisering te starten en de geharmoniseerde klantentiteit te maken.

Ga wanneer de gegevensharmonisering is voltooid naar **Meetcriteria** en **Segmenten** om deze eveneens te vernieuwen.

## <a name="edit-an-existing-environment"></a>Een bestaande omgeving bewerken

U kunt enkele details van bestaande omgevingen bewerken.

1. Ga naar **Beheer** > **Systeem** > **Info**.

2. Selecteer **Bewerken**.

3. U kunt de **weergavenaam** van de omgeving bijwerken, maar u kunt de **regio** of het **type** niet wijzigen.

4. Als een omgeving is geconfigureerd om gegevens in op te slaan Azure Data Lake Storage Gen2, kunt u **Accountsleutel** bijwerken. U kunt de **accountnaam** of naam van de **container** echter niet wijzigen.

5. Optioneel kunt u bijwerken vanaf een accountsleutelverbinding naar een resource- of een abonnementsverbinding. Na het upgraden kunt u na de update geen accountsleutel meer gebruiken. Zie [Doelgroepinzichten verbinden met een Azure Data Lake Storage Gen2-account met een Azure Service Principal](connect-service-principal.md) voor meer informatie. U kunt geen informatie over **Container** wijzigen bij het bijwerken van de verbinding.

## <a name="reset-an-existing-environment"></a>Een bestaande omgeving opnieuw instellen

U kunt een omgeving terugzetten naar een lege staat als u alle configuraties wilt verwijderen en de opgenomen gegevens wilt verwijderen.

1.  Ga naar **Beheer** > **Systeem** > **Info**.

2.  Selecteer **Opnieuw instellen**. 

3.  Om het verwijderen te bevestigen, voert u de omgevingsnaam in en selecteert u **Opnieuw instellen**.


## <a name="delete-an-existing-environment"></a>Een bestaande omgeving verwijderen

1. Ga naar **Beheer** > **Systeem** > **Info**.

1. Selecteer **Verwijderen**.

1. Om de verwijdering te bevestigen, voert u de omgevingsnaam in en selecteert u **Verwijderen**.
