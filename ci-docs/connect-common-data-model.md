---
title: Common Data Model-gegevens met een Azure Data Lake-account verbinden
description: Werken met Common Data Model-gegevens met Azure Data Lake Storage.
ms.date: 01/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: eeb6b9d97be5f9c0b9f6cbd6dbc6985559a1cd9d
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646164"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Verbinding maken met een Common Data Model-map via een Azure Data Lake-account

Dit artikel geeft informatie over het opnemen van gegevens in Dynamics 365 Customer Insights vanuit een Common Data Model-map met behulp van uw Azure Data Lake Storage Gen2-account.

## <a name="important-considerations"></a>Belangrijke aandachtspunten

- Gegevens in uw Azure Data Lake moeten de Common Data Model-standaard volgen. Andere indelingen worden momenteel niet ondersteund.

- Gegevensopname ondersteunt alleen Azure Data Lake *Gen2*-opslagaccounts. U kunt geen Azure Data Lake Gen1-opslagaccounts gebruiken om gegevens op te nemen.

- Voor de Azure Data Lake Storage-account moet [hiërarchische naamruimte zijn ingeschakeld](/azure/storage/blobs/data-lake-storage-namespace).

- Om te verifiëren met een Azure Service Principal, moet u ervoor zorgen dat deze in uw tenant is geconfigureerd. Zie voor meer informatie [Verbinding met een Azure Data Lake Storage Gen2-account maken met een Azure-service-principal](connect-service-principal.md).

- De Azure Data Lake waarmee u verbinding wilt maken en gegevens wilt opnemen, moet zich in dezelfde Azure-regio bevinden als de Dynamics 365 Customer Insights-omgeving. Verbindingen met een Common Data Model-map vanuit een data lake in een andere Azure-regio worden niet ondersteund. Als u de Azure-regio van de omgeving wilt weten, gaat u naar **Beheerder** > **Systeem** > **Over** in Customer Insights.

- Gegevens die zijn opgeslagen in online services, kunnen op een andere locatie worden opgeslagen dan waar gegevens worden verwerkt of opgeslagen in Dynamics 365 Customer Insights. Door gegevens te importeren die zijn opgeslagen in online services, gaat u ermee akkoord dat gegevens kunnen worden overgedragen naar en opgeslagen met Dynamics 365 Customer Insights. [Meer informatie in het Microsoft Trust Centerr](https://www.microsoft.com/trust-center).

## <a name="connect-to-a-common-data-model-folder"></a>Verbinding maken met een Common Data Model-map

1. Ga naar **Gegevens** > **Gegevensbronnen**.

1. Selecteer **Gegevensbron toevoegen**.

1. Selecteer **Azure Data Lake Storage**, voer een **naam** voor de gegevensbron in en selecteer daarna **Volgende**.

   - Selecteer desgevraagd een van de voorbeeldgegevenssets die betrekking hebben op uw branche en selecteer daarna **Volgende**. 

1. U kunt kiezen tussen een resource-optie en een abonnementsoptie voor verificatie. Zie voor meer informatie [Verbinding met een Azure Data Lake Storage Gen2-account maken met een Azure-service-principal](connect-service-principal.md). Voer het **serveradres** in, selecteer **Aanmelden** en selecteer daarna **Volgende**.
   > [!div class="mx-imgBorder"]
   > ![Dialoogvenster om nieuwe verbindingsdetails in te voeren voor Azure Data Lake.](media/enter-new-storage-details.png)
   > [!NOTE]
   > U hebt een van de volgende rollen nodig voor de container of het opslagaccount waarnaar hierboven wordt verwezen om verbinding te kunnen maken met een gegevensbron en deze te maken:
   >  - Opslag-blobgegevens lezer
   >  - Opslag-blobgegevens eigenaar
   >  - Inzender van opslag-blobgegevens

1. Selecteer in het dialoogvenster **Een Common Data Model-map selecteren** het bestand model.json of manifest.json waaruit u gegevens wilt importeren en selecteer **Volgende**.
   > [!NOTE]
   > Elk model.json- of manifest.json-bestand dat aan een andere gegevensbron in de omgeving is gekoppeld, wordt niet in de lijst weergegeven.

1. U ziet een lijst met beschikbare entiteiten in het geselecteerde bestand model.json of manifest.json. Bekijk en maak een keuze in de lijst met beschikbare entiteiten en selecteer vervolgens **Opslaan**. Alle geselecteerde entiteiten worden uit de nieuwe gegevensbron opgenomen.
   > [!div class="mx-imgBorder"]
   > ![Dialoogvenster met een lijst met entiteiten uit een model.json-bestand.](media/review-entities.png)

8. Geef aan voor welke gegevensentiteiten u profilering wilt inschakelen en selecteer vervolgens **Opslaan**. Met gegevensprofilering kunnen analyses en andere functies worden gebruikt. U kunt de hele entiteit selecteren, die alle kenmerken uit de entiteit selecteert, of bepaalde kenmerken selecteren. Standaard is geen entiteit ingeschakeld voor gegevensprofilering.
   > [!div class="mx-imgBorder"]
   > ![Dialoogvenster met gegevensprofilering.](media/dataprofiling-entities.png)

9. Na het opslaan van uw selecties wordt de pagina **Gegevensbronnen** geopend. U zou nu de Common Data Model-mapverbinding moeten zien als een gegevensbron.

> [!NOTE]
> Een model.json- of manifest.json-bestand kan alleen worden gekoppeld aan één gegevensbron in dezelfde omgeving. Hetzelfde model.json- of manifest.json-bestand kan echter worden gebruikt voor gegevensbronnen in meerdere omgevingen.

## <a name="edit-a-common-data-model-folder-data-source"></a>Een gegevensbron voor een Common Data Model-map bewerken

U kunt de toegangssleutel bijwerken voor het opslagaccount dat de map Common Data Model bevat. U kunt ook het model.json- of manifest.json-bestand wijzigen. Als u verbinding wilt maken met een andere container dan uw opslagaccount, of de accountnaam wilt wijzigen, moet u [een nieuwe gegevensbronverbinding maken](#connect-to-a-common-data-model-folder).

1. Ga naar **Gegevens** > **Gegevensbronnen**.

2. Selecteer het weglatingsteken naast de gegevensbron die u wilt bijwerken.

3. Selecteer de optie **Bewerken** in de lijst.

4. Werk desgewenst de **Toegangssleutel** bij en selecteer **Volgende**.

   ![Dialoogvenster om een toegangssleutel voor een bestaande gegevensbron te wijzigen en bij te werken.](media/edit-access-key.png)

5. Optioneel kunt u bijwerken vanaf een accountsleutelverbinding naar een resource- of een abonnementsverbinding. Zie voor meer informatie [Verbinding met een Azure Data Lake Storage Gen2-account maken met een Azure-service-principal](connect-service-principal.md). U kunt geen informatie over **Container** wijzigen bij het bijwerken van de verbinding.
   > [!div class="mx-imgBorder"]

   > ![Dialoogvenster om verbindingsdetails voor Azure Data Lake in te voeren met een bestaand opslagaccount.](media/enter-existing-storage-details.png)

   > [!NOTE]
   > U hebt een van de volgende rollen nodig voor de container of het opslagaccount waarnaar hierboven wordt verwezen om verbinding te kunnen maken met een gegevensbron en deze te maken:
   >  - Opslag-blobgegevens lezer
   >  - Opslag-blobgegevens eigenaar
   >  - Inzender van opslag-blobgegevens


6. Kies optioneel een ander model.json- of manifest.json-bestand met een andere set entiteiten uit de container.

7. Optioneel kunt u extra entiteiten selecteren om op te nemen. U kunt ook reeds geselecteerde entiteiten verwijderen als er geen afhankelijkheden zijn.

   > [!IMPORTANT]
   > Als er afhankelijkheden zijn in het bestaande model.json- of manifest.json-bestand en de set entiteiten, ziet u een foutbericht en kunt u geen ander model.json- of manifest.json-bestand selecteren. Verwijder die afhankelijkheden voordat u het model.json- of manifest.json-bestand wijzigt, of maak een nieuw gegevensbron met model.json of manifest.json dat u wilt gebruiken om te voorkomen dat u de afhankelijkheden verwijdert.

8. Optioneel kunt u extra kenmerken of entiteiten selecteren om gegevensprofilering in te schakelen of reeds geselecteerde uit te schakelen.   


[!INCLUDE [footer-include](includes/footer-banner.md)]
