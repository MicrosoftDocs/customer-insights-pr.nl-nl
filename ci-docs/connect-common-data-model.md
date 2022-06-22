---
title: Common Data Model-gegevens met een Azure Data Lake-account verbinden
description: Werken met Common Data Model-gegevens met Azure Data Lake Storage.
ms.date: 05/30/2022
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: 2ab7ec77252be33f1203959c2a596ddec20425f2
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011551"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Verbinding maken met gegevens in Azure Data Lake Storage

Gegevens opnemen in Dynamics 365 Customer Insights via uw Azure Data Lake Storage Gen2-account. Gegevensopname kan volledig of incrementeel zijn.

## <a name="prerequisites"></a>Vereisten

- Uitsluitend ondersteuning voor gegevensopname via Azure Data Lake Storage *Gen2*-accounts. U kunt geen Data Lake Storage Gen1-opslagaccounts gebruiken om gegevens op te nemen.

- Op het Azure Data Lake Storage-account moet [hiërarchische naamruimte ingeschakeld](/azure/storage/blobs/data-lake-storage-namespace) zijn. De gegevens moeten worden opgeslagen in een hiërarchische mapindeling die de hoofdmap definieert en submappen heeft voor elke entiteit. De submappen kunnen volledige gegevens of incrementele gegevensmappen hebben.

- Om te verifiëren met een Azure Service Principal, moet u ervoor zorgen dat deze in uw tenant is geconfigureerd. Zie voor meer informatie [Verbinding met een Azure Data Lake Storage Gen2-account maken met een Azure-service-principal](connect-service-principal.md).

- De Azure Data Lake Storage waarmee u verbinding wilt maken en waaruit u gegevens wilt opnemen, moet zich in dezelfde Azure-regio bevinden als de Dynamics 365 Customer Insights omgeving. Verbindingen met een Common Data Model-map vanuit een data lake in een andere Azure-regio worden niet ondersteund. Als u de Azure-regio van de omgeving wilt weten, gaat u naar **Beheerder** > **Systeem** > **Over** in Customer Insights.

- Gegevens die zijn opgeslagen in online services, kunnen op een andere locatie worden opgeslagen dan waar gegevens worden verwerkt of opgeslagen in Dynamics 365 Customer Insights. Door gegevens te importeren die zijn opgeslagen in online services, gaat u ermee akkoord dat gegevens kunnen worden overgedragen naar en opgeslagen met Dynamics 365 Customer Insights. [Meer informatie in het Microsoft Trust Centerr](https://www.microsoft.com/trust-center).

- De Customer Insights-service-principal moet een van de volgende rollen hebben om toegang te krijgen tot het opslagaccount. Voor meer informatie, zie [Machtigingen verlenen aan de service-principal voor toegang tot het opslagaccount](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account).
  - Opslag-blobgegevens lezer
  - Opslag-blobgegevens eigenaar
  - Inzender van opslag-blobgegevens

- Gegevens in uw Data Lake Storage moeten de Common Data Model-standaard volgen voor de opslag van uw gegevens en het gemeenschappelijke gegevensmodelmanifest hebben om het schema van de gegevensbestanden (*.csv of *.parquet) weer te geven. Het manifest moet de details van de entiteiten bevatten, zoals entiteitskolommen en gegevenstypen, evenals de locatie van het gegevensbestand en het bestandstype. Zie voor meer informatie [Het Common Data Model-manifest](/common-data-model/sdk/manifest). Als het manifest niet aanwezig is, kunnen beheerders met Storage Blob Data eigenaar- of Storage Blob Data inzender-toegang het schema definiëren bij het opnemen van de gegevens.

## <a name="connect-to-azure-data-lake-storage"></a>Verbinding maken met Azure Data Lake Storage

1. Ga naar **Gegevens** > **Gegevensbronnen**.

1. Selecteer **Gegevensbron toevoegen**.

1. Selecteer **Azure Data Lake Storage**.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Dialoogvenster om verbindingsdetails voor Azure Data Lake in te voeren." lightbox="media/data_sources_ADLS.png":::

1. Voer een **Naam** voor de gegevensbron en een optionele **Beschrijving** in. De naam identificeert op unieke wijze de gegevensbron en er wordt naar verwezen in downstreamprocessen en kan niet worden gewijzigd.

1. Kies een van de volgende opties voor **Uw opslag verbinden met**. Zie voor meer informatie [Customer Insights verbinden met een Azure Data Lake Storage Gen2-account maken met een Azure-service-principal](connect-service-principal.md).

   - **Azure-resource**: voer de **Resource-id** in. Optioneel, als u gegevens van een opslagaccount wilt opnemen via een Azure Private Link, selecteert u **Private Link inschakelen**. Zie voor meer informatie [Privékoppelingen](security-overview.md#private-links-tab).
   - **Azure-abonnement**: selecteer het **Abonnement** en dan de **Resourcegroep** en het **Opslagaccount**. Optioneel, als u gegevens van een opslagaccount wilt opnemen via een Azure Private Link, selecteert u **Private Link inschakelen**. Zie voor meer informatie [Privékoppelingen](security-overview.md#private-links-tab).
  
   > [!NOTE]
   > U hebt een van de volgende rollen nodig voor de container of het opslagaccount om de gegevensbron te maken:
   >
   >  - Storage Blob-gegevenslezer is voldoende om van een opslagaccount te lezen en de gegevens op te nemen in Customer Insights. 
   >  - Bijdrager van Storage Blob-gegevens of Eigenaar van Storage Blob-gegevens is vereist als u de manifestbestanden rechtstreeks in Customer Insights wilt bewerken.  
  
1. Kies de naam van de **Container** die de gegevens en het schema bevat (model.json- of manifest.json-bestand) om gegevens uit te importeren, en selecteer **Volgende**.
   > [!NOTE]
   > Elk model.json- of manifest.json-bestand dat aan een andere gegevensbron in de omgeving is gekoppeld, wordt niet in de lijst weergegeven. Hetzelfde model.json- of manifest.json-bestand kan echter worden gebruikt voor gegevensbronnen in meerdere omgevingen.

1. Als u een nieuw schema wilt maken, gaat u naar [Een nieuw schemabestand maken](#create-a-new-schema-file).

1. Als u een bestaand schema wilt gebruiken, navigeert u naar de map met het model.json- of manifest.cdm.json-bestand. U kunt in een map zoeken om het bestand te vinden.

1. Selecteer het json-bestand en selecteer **Volgende**. Een lijst met beschikbare entiteiten wordt weergegeven.

   :::image type="content" source="media/review-entities.png" alt-text="Dialoogvenster van een lijst met te selecteren entiteiten":::

1. Selecteer de entiteiten die u wilt opnemen.

   :::image type="content" source="media/ADLS_required.png" alt-text="Dialoogvenster met Vereist voor primaire sleutel":::

   > [!TIP]
   > Als u de entiteiten in een JSON-bewerkingsinterface wilt bewerken, selecteert u **Meer weergeven** > **Schemabestand bewerken**. Breng uw wijzigingen aan selecteer **Opslaan**.

1. Voor geselecteerde entiteiten die incrementele opname vereisen, wordt **Vereist** weergegeven onder **Incrementeel vernieuwen**. Voor elk van deze entiteiten, zie [Een incrementele vernieuwing configureren voor Azure Data Lake-gegevensbronnen](incremental-refresh-data-sources.md).

1. Voor geselecteerde entiteiten waarvoor geen primaire sleutel is gedefinieerd, wordt **Vereist** weergegeven onder **Primaire sleutel**. Voor elk van deze entiteiten:
   1. Selecteer **Vereist**. Het deelvenster **Entiteit bewerken** wordt weergegeven.
   1. Kies de **primaire sleutel**. De primaire sleutel is een kenmerk dat uniek is voor de entiteit. Als een kenmerk een geldige primaire sleutel is, mag het geen dubbele waarden, ontbrekende waarden of null-waarden bevatten. Kenmerken van het gegevenstype string, integer en GUID worden ondersteund als primaire sleutels.
   1. Wijzig eventueel het partitiepatroon.
   1. Selecteer **Sluiten** om het deelvenster op te slaan en te sluiten.

1. Selecteer het aantal **Kenmerken** voor elke opgenomen entiteit. De pagina **Kernmerken beheren** wordt weergegeven.

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="Dialoogvenster om gegevensprofilering te selecteren.":::

   1. Maak nieuwe kenmerken, bewerk of verwijder bestaande kenmerken. U kunt de naam, de gegevensindeling wijzigen of een semantisch type toevoegen.
   1. Als u analyses en andere mogelijkheden wilt inschakelen, selecteert u **Gegevensprofilering** voor de hele entiteit of voor specifieke kenmerken. Standaard is geen entiteit ingeschakeld voor gegevensprofilering.
   1. Selecteer **Gereed**.

1. Selecteer **Save**. De pagina **Gegevensbronnen** wordt geopend met de nieuwe gegevensbron met de status **Vernieuwen**.

### <a name="create-a-new-schema-file"></a>Een nieuw schemabestand maken

1. Selecteer **Nieuw schemabestand**.

1. Voer een naam in voor het bestand en selecteer **Opslaan**.

1. Selecteer **Nieuwe entiteit**. Het deelvenster **Nieuwe entiteit** wordt weergegeven.

1. Voer de naam van de entiteit in en kies de **Locatie van gegevensbestanden**.
   - **Meerdere .csv- of .parquet-bestanden**: blader naar de hoofdmap, selecteer het patroontype en voer de uitdrukking in.
   - **Enkele .csv- of .parquet-bestanden**: blader naar het .csv- of .parquet-bestand en selecteer het.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="Dialoogvenster om een nieuwe entiteit te maken met de locatie van de gegevensbestanden gemarkeerd.":::

1. Selecteer **Save**.

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="Dialoogvenster om kenmerken te definiëren of automatisch te genereren.":::

1. Selecteer **de kenmerken definiëren** om de kenmerken handmatig toe te voegen, of selecteer **automatisch genereren**. Als u de kenmerken wilt definiëren, voert u een naam in, selecteert u de gegevensindeling en het optionele semantische type. Voor automatisch gegenereerde kenmerken:

   1. Nadat de kenmerken automatisch zijn gegenereerd, selecteert u **Kenmerken beoordelen**. De pagina **Kernmerken beheren** wordt weergegeven.

   1. Zorg ervoor dat de gegevensindeling voor elk kenmerk correct is.

   1. Als u analyses en andere mogelijkheden wilt inschakelen, selecteert u **Gegevensprofilering** voor de hele entiteit of voor specifieke kenmerken. Standaard is geen entiteit ingeschakeld voor gegevensprofilering.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="Dialoogvenster om gegevensprofilering te selecteren.":::

   1. Selecteer **Gereed**. De pagina **Entiteiten selecteren** wordt weergegeven.

1. Ga door met het toevoegen van entiteiten en kenmerken, indien van toepassing.

1. Nadat alle entiteiten zijn toegevoegd, selecteert u **Opnemen** om de entiteiten op te nemen bij de gegevensbronopname.

   :::image type="content" source="media/ADLS_required.png" alt-text="Dialoogvenster met Vereist voor primaire sleutel":::

1. Voor geselecteerde entiteiten die incrementele opname vereisen, wordt **Vereist** weergegeven onder **Incrementeel vernieuwen**. Voor elk van deze entiteiten, zie [Een incrementele vernieuwing configureren voor Azure Data Lake-gegevensbronnen](incremental-refresh-data-sources.md).

1. Voor geselecteerde entiteiten waarvoor geen primaire sleutel is gedefinieerd, wordt **Vereist** weergegeven onder **Primaire sleutel**. Voor elk van deze entiteiten:
   1. Selecteer **Vereist**. Het deelvenster **Entiteit bewerken** wordt weergegeven.
   1. Kies de **primaire sleutel**. De primaire sleutel is een kenmerk dat uniek is voor de entiteit. Als een kenmerk een geldige primaire sleutel is, mag het geen dubbele waarden, ontbrekende waarden of null-waarden bevatten. Kenmerken van het gegevenstype string, integer en GUID worden ondersteund als primaire sleutels.
   1. Wijzig eventueel het partitiepatroon.
   1. Selecteer **Sluiten** om het deelvenster op te slaan en te sluiten.

1. Selecteer **Save**. De pagina **Gegevensbronnen** wordt geopend met de nieuwe gegevensbron met de status **Vernieuwen**.


## <a name="edit-an-azure-data-lake-storage-data-source"></a>Een Azure Data Lake Storage-gegevensbron bewerken

U kunt de optie *Verbinding maken met een opslagaccount met* bijwerken. Zie voor meer informatie [Customer Insights verbinden met een Azure Data Lake Storage Gen2-account maken met een Azure-service-principal](connect-service-principal.md). Als u verbinding wilt maken met een andere container dan uw opslagaccount, of de accountnaam wilt wijzigen, moet u [een nieuwe gegevensbronverbinding maken](#connect-to-azure-data-lake-storage).

1. Ga naar **Gegevens** > **Gegevensbronnen**.

1. Selecteer **Bewerken** naast de gegevensbron die u wilt bijwerken.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Dialoogvenster om Azure Data Lake-gegevensbron te bewerken.":::

1. Wijzig (een van) de volgende gegevens:

   - **Omschrijving**
   - **Uw opslag verbinden met** en verbindingsgegevens. U kunt geen informatie over **Container** wijzigen bij het bijwerken van de verbinding.
      > [!NOTE]
      > Een van de volgende rollen moet worden toegewezen aan het opslagaccount of de container:
        > - Opslag-blobgegevens lezer
        > - Opslag-blobgegevens eigenaar
        > - Inzender van opslag-blobgegevens

   - **Private Link inschakelen** als u gegevens van een opslagaccount wilt opnemen via een Azure Private Link. Zie voor meer informatie [Privékoppelingen](security-overview.md#private-links-tab).

1. Selecteer **Volgende**.
1. Wijzig (een van) de volgende:
   - Navigeer naar een ander model.json- of manifest.json-bestand met een andere set entiteiten uit de container.
   - Als u extra entiteiten wilt toevoegen om op te nemen, selecteert u **Nieuwe entiteit**.
   - Als u reeds geselecteerde entiteiten wilt verwijderen als er geen afhankelijkheden zijn, selecteert u de entiteit en **Verwijderen**.
      > [!IMPORTANT]
      > Als er afhankelijkheden zijn in het bestaande model.json- of manifest.json-bestand en de set entiteiten, ziet u een foutbericht en kunt u geen ander model.json- of manifest.json-bestand selecteren. Verwijder die afhankelijkheden voordat u het model.json- of manifest.json-bestand wijzigt, of maak een nieuw gegevensbron met model.json of manifest.json dat u wilt gebruiken om te voorkomen dat u de afhankelijkheden verwijdert.
   - Als u de locatie van het gegevensbestand of de primaire sleutel wilt wijzigen, selecteert u **Bewerken**.
   - Zie [Een incrementele vernieuwing configureren voor Azure Data Lake-gegevensbronnen](incremental-refresh-data-sources.md) als u de incrementele opnamegegevens wilt wijzigen

1. Selecteer **Kenmerken** om kenmerken toe te voegen of te wijzigen, of om gegevensprofilering in te schakelen. Selecteer **Gereed**.

1. Klik op **Opslaan** om uw wijzigingen toe te passen en terug te keren naar de pagina **Gegevensbronnen**.
