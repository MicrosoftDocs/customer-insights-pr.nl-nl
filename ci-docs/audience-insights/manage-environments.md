---
title: Omgevingen maken en beheren
description: Ontdek hoe u zich aanmeldt voor de service en hoe u omgevingen beheert.
ms.date: 03/28/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
  - ci-system-about
  - customerInsights
---

# <a name="manage-environments"></a>Omgevingen beheren

## <a name="switch-environments"></a>Omgevingen omschakelen

Selecteer het besturingselement **Omgeving** in de rechterbovenhoek van de pagina om van omgeving te veranderen.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Schermafbeelding van het besturingselement om van omgeving te wisselen.":::

Beheerders kunnen omgevingen [maken](create-environment.md) en beheren.

## <a name="edit-an-existing-environment"></a>Een bestaande omgeving bewerken

U kunt enkele details van bestaande omgevingen bewerken.

1.  Selecteer de picker **Omgeving** in de koptekst van de app.

2.  Selecteer het pictogram **Bewerken**.

3. In het vak **Omgeving bewerken** kunt u de omgevingsinstellingen bijwerken.

Zie voor meer informatie over omgevingsinstellingen [Een nieuwe omgeving maken](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Verbinding maken met Microsoft Dataverse
   
In de stap **Microsoft Dataverse** kunt u Customer Insights verbinden met uw Dataverse-omgeving. 

Bied uw eigen Microsoft Dataverse-omgeving om gegevens (profielen en inzichten) te delen met zakelijke toepassingen op basis van Dataverse, zoals Dynamics 365 Marketing of modelgestuurde toepassingen in Power Apps.

Als u [kant-en-klare voorspellingsmodellen](predictions-overview.md#out-of-box-models) wilt gebruiken, configureert u delen van gegevens met Dataverse. Of u kunt gegevensopname van on-premises-gegevensbronnen inschakelen door de Microsoft Dataverse omgevings-URL op te geven die uw organisatie beheert.

Als het delen van gegevens met Microsoft Dataverse wordt geactiveerd door het selectievakje voor het delen van gegevens in te schakelen, wordt een eenmalige volledige vernieuwing van uw gegevensbronnen en alle andere processen geactiveerd.

> [!IMPORTANT]
> 1. Customer Insights en Dataverse moeten zich in dezelfde regio bevinden om het delen van gegevens mogelijk te maken.
> 1. U moet de rol van algemene beheerder hebben in de Dataverse-omgeving. Controleer of deze [Dataverse-omgeving is gekoppeld](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) aan bepaalde beveiligingsgroepen en zorg ervoor dat u aan die beveiligingsgroepen wordt toegevoegd.
> 1. Er is nog geen bestaande Customer Insights-omgeving aan die Dataverse-omgeving gekoppeld. Leren hoe u [een bestaande verbinding met een Dataverse omgeving kunt verwijderen](#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="Configuratieopties om het delen van gegevens met Microsoft Dataverse mogelijk te maken.":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Gegevens delen met Dataverse inschakelen vanuit uw eigen Azure Data Lake Storage (preview)

Als uw omgeving is geconfigureerd om uw eigen Azure Data Lake Storage-omgeving te gebruiken voor het opslaan van Customer Insights-gegevens, is er wat extra configuratie nodig om het delen van gegevens met Microsoft Dataverse mogelijk te maken.

1. Maak twee beveiligingsgroepen op uw Azure-abonnement - één beveiligingsgroep **Lezer** en één beveiligingsgroep **Inzender** en stel de Microsoft Dataverse-service in als eigenaar voor beide beveiligingsgroepen.
2. Beheer de Access Control List (ACL) voor de Customer Insights-container in uw opslagaccount via deze beveiligingsgroepen. Voeg de Microsoft Dataverse-service en eventuele op Dataverse gebaseerde bedrijfstoepassingen zoals Dynamics 365 Marketing toe aan de beveiligingsgroep **Lezer** met **alleen lezen**-machtigingen. Voeg *alleen* de Customers Insights-toepassing toe aan de beveiligingsgroep **Inzender** om **zowel lees- als schrijfmachtigingen** te verlenen voor het wegschrijven van profielen en inzichten.
   
#### <a name="prerequisites"></a>Vereisten

Als u de PowerShell-scripts wilt uitvoeren, moet u de volgende drie modules hebben geïmporteerd. 

1. Installeer de meest recente versie van [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).
   1. Selecteer op uw pc de Windows-toets op uw toetsenbord en zoek naar **Windows PowerShell**. Selecteer vervolgens **Uitvoeren als beheerder**.
   1. Voer `Install-Module AzureAD` in het PowerShell-venster dat wordt geopend in.
2. Importeer drie modules.
    1. Voer `Install-Module -Name Az.Accounts` in het PowerShell-venster in en volg de stappen. 
    1. Herhaal dit voor `Install-Module -Name Az.Resources` en `Install-Module -Name Az.Storage`.

#### <a name="configuration-steps"></a>Configuratiestappen

1. Download de twee PowerShell-scripts die u moet uitvoeren vanuit onze [GitHub-opslagplaats](https://github.com/trin-msft/byol) voor technici.
    1. `CreateSecurityGroups.ps1`
       - U hebt machtigingen voor *tenantbeheer* nodig om dit PowerShell-script te kunnen uitvoeren. 
       - Dit PowerShell-script maakt twee beveiligingsgroepen in uw Azure-abonnement. Eén voor de groep Lezer en een andere voor de groep Inzender, met de Microsoft Dataverse-service als eigenaar voor beide beveiligingsgroepen.
       - Voer dit PowerShell-script uit in Windows PowerShell door de Azure-abonnements-id op te geven die uw Azure Data Lake Storage bevat. Open het PowerShell-script in een editor om aanvullende informatie en de geïmplementeerde logica te bekijken.
       - Bewaar beide beveiligingsgroep-id-waarden die door dit script zijn gegenereerd omdat we deze zullen gebruiken in het script `ByolSetup.ps1`.
       
        > [!NOTE]
        > Het maken van beveiligingsgroepen kan worden uitgeschakeld op uw tenant. In dat geval is een handmatige configuratie nodig en moet uw Azure AD-beheerder [het maken van beveiligingsgroepen inschakelen](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - U hebt machtigingen *Eigenaar van Storage Blob-gegevens* op opslagaccount-/containerniveau nodig om dit script te kunnen uitvoeren, anders maakt dit script er een voor u. Uw roltoewijzing kan handmatig worden verwijderd nadat het script met succes is uitgevoerd.
        - Dit PowerShell-script voegt de vereiste op rollen gebaseerd toegangsbeheer (RBAC) toe voor de Microsoft Dataverse-service en eventuele op Dataverse gebaseerde bedrijfstoepassingen. Het werkt ook de Access Control List (ACL) in de CustomerInsights-container bij voor de beveiligingsgroepen die zijn gemaakt met het script `CreateSecurityGroups.ps1`. De groep Inzender zal *rwx*-machtiging hebben en de groep Lezer zal alleen *rx*-machtiging hebben.
        - Voer dit PowerShell-script uit in Windows PowerShell door de Azure-abonnements-id op te geven met uw Azure Data Lake Storage, opslagaccountnaam, resourcegroepnaam en de waarden voor de beveiligingsgroep-id voor Lezer en Inzender. Open het PowerShell-script in een editor om aanvullende informatie en de geïmplementeerde logica te bekijken.
        - Kopieer de uitvoertekenreeks nadat het script is uitgevoerd. De uitvoertekenreeks ziet er als volgt uit: `https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. Voer de uitvoertekenreeks die hierboven is gekopieerd in het veld **Id van machtigingen** van de stap voor omgevingsconfiguratie voor Microsoft Dataverse in.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Configuratieopties om het delen van gegevens van uw eigen Azure Data Lake Storage met Microsoft Dataverse in te schakelen.":::

Customer Insights biedt geen ondersteuning voor de volgende scenario's voor het delen van gegevens:
- Als u het delen van gegevens met een door Dataverse beheerd data lake inschakelt, is het niet mogelijk om [voorspelde of ontbrekende waarden te maken in een entiteit](predictions.md).
- Als u het delen van gegevens inschakelt met Dataverse, kunt u geen optionele PowerBI Embedded-rapporten bekijken in uw Customer Insights-omgeving.

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Een bestaande verbinding met een Dataverse-omgeving verwijderen

Bij een verbinding met een Dataverse-omgeving betekent de foutmelding **Deze CDS-organisatie is al aan een ander Customer Insights-exemplaar gekoppeld** dat de Dataverse-omgeving al wordt gebruikt in een Customer Insights-omgeving. U kunt de bestaande verbinding verwijderen als een algemene beheerder in de Dataverse-omgeving. Het kan een paar uur duren voordat de wijzigingen worden doorgevoerd.

1. Ga naar [Power Apps](https://make.powerapps.com).
1. Selecteer de omgeving met de omgevingskiezer.
1. Ga naar **Oplossingen**
1. Verwijder de oplossing met de naam **Invoegtoepassing Klantkaart voor Dynamics 365 Customer Insights (preview)**.

OF 

1. Open uw Dataverse-omgeving.
1. Ga naar **Geavanceerde instellingen** > **Oplossingen**.
1. Verwijder de oplossing **CustomerInsightsCustomerCard**.

## <a name="copy-the-environment-configuration"></a>De configuratie van de omgeving kopiëren

Als beheerder kunt u ervoor kiezen om de configuratie uit een bestaande omgeving te kopiëren wanneer u een nieuwe maakt. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Schermafbeelding van de opties in de omgevingsinstellingen.":::

U ziet een lijst met alle beschikbare omgevingen in uw organisatie waaruit u gegevens kunt kopiëren.

De volgende configuratie-instellingen worden gekopieerd:

- Opgenomen/geïmporteerde gegevensbronnen
- Configuratie van gegevensharmonisatie (Toewijzing, Overeenkomst, Samenvoeging)
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

## <a name="set-up-a-copied-environment"></a>Een gekopieerde omgeving instellen

Wanneer u de omgevingsconfiguratie kopieert, worden de volgende gegevens *niet* gekopieerd:

- Klantprofielen.
- Referenties voor gegevensbron. U moet de referenties voor elke gegevensbron opgeven en de gegevensbronnen handmatig vernieuwen.
- Gegevensbronnen uit de Common Data Model-map en het door Dataverse beheerde data lake. U moet die gegevensbronnen handmatig maken met dezelfde naam als in de bronomgeving.
- Verbindingsgeheimen die worden gebruikt voor exports en verrijkingen. U moet de verbindingen opnieuw verifiëren en vervolgens verrijkingen en exports opnieuw activeren. 

Wanneer u een omgeving kopieert, ziet u een bevestigingsbericht dat de nieuwe omgeving is gemaakt. Selecteer **Ga naar gegevensbronnen** om de lijst met gegevensbronnen te zien.

Alle gegevensbronnen hebben de status **Referenties vereist**. Bewerk de gegevensbronnen en voer de referenties in om ze te vernieuwen.

:::image type="content" source="media/data-sources-copied.png" alt-text="Lijst met gegevensbronnen die zijn gekopieerd en waarvoor verificatie is vereist.":::

Ga na het vernieuwen van de gegevensbronnen naar **Gegevens** > **Harmoniseren**. Hier vindt u instellingen uit de bronomgeving. Bewerk deze indien nodig of selecteer **Uitvoeren** om het proces voor gegevensharmonisering te starten en de geharmoniseerde klantentiteit te maken.

Ga wanneer de gegevensharmonisering is voltooid naar **Meetcriteria** en **Segmenten** om deze eveneens te vernieuwen.

Voordat u exports en verrijkingen opnieuw activeert, gaat u naar **Beheerder** > **Verbindingen** om de verbindingen in uw nieuwe omgeving opnieuw te verifiëren.

## <a name="change-the-owner-of-an-environment"></a>De eigenaar van een omgeving wijzigen

Hoewel meerdere gebruikers beheerdersmachtigingen kunnen hebben in Customer Insights, is slechts één gebruiker de eigenaar van een omgeving. Standaard is het de beheerder die in eerste instantie een omgeving maakt. Als beheerder van een omgeving kunt u het eigendom toewijzen aan een andere gebruiker met beheerdersrechten.

1. Selecteer de picker **Omgeving** in de koptekst van de app.

1. Selecteer het pictogram **Bewerken**.

1. Ga in het vak **Omgeving bewerken** naar de stap **Basisinformatie**.

1. Kies in het veld **Eigenaar van omgeving wijzigen** de nieuwe eigenaar van de omgeving.  

1. Selecteer **Controleren en voltooien** en vervolgens **Bijwerken** om de wijzigingen toe te passen. 

## <a name="claim-ownership-of-an-environment"></a>Eigendom van een omgeving claimen

Als de eigenaar van een omgeving de organisatie verlaat of als zijn of haar gebruikersaccount wordt verwijderd, heeft de omgeving geen eigenaar. Een gebruiker met beheerdersmachtigingen kan het eigendom claimen en de nieuwe eigenaar worden. Ze kunnen eigenaar blijven van de omgeving of [het eigendom wijzigen naar een andere beheerder](#change-the-owner-of-an-environment). 

U kunt het eigendom claimen door de knop **Eigenaar worden** te selecteren die boven aan elke pagina in Customer Insights wordt weergegeven wanneer de oorspronkelijke eigenaar de organisatie heeft verlaten.

## <a name="reset-an-existing-environment"></a>Een bestaande omgeving opnieuw instellen

Als eigenaar van een omgeving kunt u een omgeving opnieuw instellen op een lege status als u alle configuraties wilt verwijderen en de opgenomen gegevens wilt verwijderen.

1.  Selecteer de picker **Omgeving** in de koptekst van de app. 

2.  Selecteer de omgeving die u opnieuw wilt instellen en selecteer het beletselteken (**...**). 

3. Kies de optie **Opnieuw instellen**. 

4.  Om het verwijderen te bevestigen, voert u de omgevingsnaam in en selecteert u **Opnieuw instellen**.

## <a name="delete-an-existing-environment"></a>Een bestaande omgeving verwijderen

Als eigenaar van een omgeving kunt u een door u beheerde omgeving verwijderen.

1.  Selecteer de picker **Omgeving** in de koptekst van de app.

2.  Selecteer de omgeving die u opnieuw wilt instellen en selecteer het beletselteken (**...**). 

3. Kies de optie **Verwijderen**. 

4.  Om de verwijdering te bevestigen, voert u de omgevingsnaam in en selecteert u **Verwijderen**.

> [!NOTE]
> Als u een omgeving verwijdert, wordt de koppeling naar een Dataverse-omgeving niet verwijderd. Leer hoe u [een bestaande verbinding met een Dataverse-omgeving kunt verwijderen](#remove-an-existing-connection-to-a-dataverse-environment).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
