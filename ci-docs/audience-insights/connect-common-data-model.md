---
title: Common Data Model-gegevens met een Azure Data Lake-account verbinden
description: Werken met Common Data Model-gegevens met Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 247e4d9c47ff2373065ebf3c6d554323e45a120b
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267854"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="98b54-103">Verbinding maken met een Common Data Model-map via een Azure Data Lake-account</span><span class="sxs-lookup"><span data-stu-id="98b54-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="98b54-104">Dit artikel bevat informatie over het opnemen van gegevens uit een Common Data Model-map met uw Azure Data Lake Storage Gen2-account.</span><span class="sxs-lookup"><span data-stu-id="98b54-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="98b54-105">Belangrijke aandachtspunten</span><span class="sxs-lookup"><span data-stu-id="98b54-105">Important considerations</span></span>

- <span data-ttu-id="98b54-106">Gegevens in uw Azure Data Lake moeten de Common Data Model-standaard volgen.</span><span class="sxs-lookup"><span data-stu-id="98b54-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="98b54-107">Andere indelingen worden momenteel niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="98b54-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="98b54-108">Gegevensopname ondersteunt alleen Azure Data Lake *Gen2*-opslagaccounts.</span><span class="sxs-lookup"><span data-stu-id="98b54-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="98b54-109">U kunt geen Azure Data Lake Gen1-opslagaccounts gebruiken om gegevens op te nemen.</span><span class="sxs-lookup"><span data-stu-id="98b54-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="98b54-110">Om te verifiëren met een Azure Service Principal, moet u ervoor zorgen dat deze in uw tenant is geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="98b54-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="98b54-111">Zie [Doelgroepinzichten verbinden met een Azure Data Lake Storage Gen2-account met een Azure Service Principal](connect-service-principal.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="98b54-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="98b54-112">De Azure Data Lake waarmee u verbinding wilt maken en gegevens wilt opnemen, moet zich in dezelfde Azure-regio bevinden als de Dynamics 365 Customer Insights-omgeving.</span><span class="sxs-lookup"><span data-stu-id="98b54-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="98b54-113">Verbindingen met een Common Data Model-map vanuit een data lake in een andere Azure-regio worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="98b54-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="98b54-114">Ga naar **Beheer** > **Systeem** > **Over** in doelgroepinzichten om de Azure-regio van de omgeving te vinden.</span><span class="sxs-lookup"><span data-stu-id="98b54-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="98b54-115">Gegevens die zijn opgeslagen in online services, kunnen op een andere locatie worden opgeslagen dan waar gegevens worden verwerkt of opgeslagen in Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="98b54-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="98b54-116"> Door gegevens te importeren die zijn opgeslagen in online services, gaat u ermee akkoord dat gegevens kunnen worden overgedragen naar en opgeslagen met Dynamics 365 Customer Insights.  [Meer informatie in het Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="98b54-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="98b54-117">Verbinding maken met een Common Data Model-map</span><span class="sxs-lookup"><span data-stu-id="98b54-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="98b54-118">Ga in doelgroepinzichten naar **Gegevens** > **Gegevensbronnen**.</span><span class="sxs-lookup"><span data-stu-id="98b54-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="98b54-119">Selecteer **Gegevensbron toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="98b54-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="98b54-120">Selecteer **Verbinding maken met een Common Data Model-map**, voer een **Naam** in voor de gegevensbron en selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="98b54-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span> <span data-ttu-id="98b54-121">Naamrichtlijnen:</span><span class="sxs-lookup"><span data-stu-id="98b54-121">Name guidelines:</span></span> 
   - <span data-ttu-id="98b54-122">Begin met een letter.</span><span class="sxs-lookup"><span data-stu-id="98b54-122">Start with a letter.</span></span>
   - <span data-ttu-id="98b54-123">Gebruik alleen letters en cijfers.</span><span class="sxs-lookup"><span data-stu-id="98b54-123">Use letters and numbers only.</span></span> <span data-ttu-id="98b54-124">Speciale tekens en spaties zijn niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="98b54-124">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="98b54-125">Gebruik minimaal 3 en maximaal 64 tekens.</span><span class="sxs-lookup"><span data-stu-id="98b54-125">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="98b54-126">U kunt kiezen tussen een resource-optie en een abonnementsoptie voor verificatie.</span><span class="sxs-lookup"><span data-stu-id="98b54-126">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="98b54-127">Zie [Doelgroepinzichten verbinden met een Azure Data Lake Storage Gen2-account met een Azure Service Principal](connect-service-principal.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="98b54-127">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="98b54-128">Voer de informatie van de **Container** in en selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="98b54-128">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="98b54-129">![Dialoogvenster om nieuwe verbindingsdetails in te voeren voor Azure Data Lake](media/enter-new-storage-details.png)
   > </span><span class="sxs-lookup"><span data-stu-id="98b54-129">![Dialog box to enter new connection details for Azure Data Lake](media/enter-new-storage-details.png)
   > </span></span>[!NOTE]
<span data-ttu-id="98b54-130">U hebt een van de volgende rollen nodig voor de container of het opslagaccount waarnaar hierboven wordt verwezen om verbinding te kunnen maken met een gegevensbron en deze te maken:</span><span class="sxs-lookup"><span data-stu-id="98b54-130">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="98b54-131">Opslag-blobgegevens lezer</span><span class="sxs-lookup"><span data-stu-id="98b54-131">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="98b54-132">Opslag-blobgegevens eigenaar</span><span class="sxs-lookup"><span data-stu-id="98b54-132">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="98b54-133">Inzender van opslag-blobgegevens</span><span class="sxs-lookup"><span data-stu-id="98b54-133">Storage Blob Data Contributor</span></span>

1. <span data-ttu-id="98b54-134">Selecteer in het dialoogvenster **Een Common Data Model-map selecteren** het bestand model.json of manifest.json waaruit u gegevens wilt importeren en selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="98b54-134">In the **Select a Common Data Model folder** dialog, select the model.json or manifest.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="98b54-135">Elk model.json- of manifest.json-bestand dat aan een andere gegevensbron in de omgeving is gekoppeld, wordt niet in de lijst weergegeven.</span><span class="sxs-lookup"><span data-stu-id="98b54-135">Any model.json or manifest.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="98b54-136">U krijgt een lijst met beschikbare entiteiten in het geselecteerde model.json- of manifest.json-bestand.</span><span class="sxs-lookup"><span data-stu-id="98b54-136">You'll get a list of available entities in the selected model.json or manifest.json file.</span></span> <span data-ttu-id="98b54-137">U kunt entiteiten bekijken en selecteren in de beschikbare lijst met beschikbare entiteiten en vervolgens **Opslaan** selecteren.</span><span class="sxs-lookup"><span data-stu-id="98b54-137">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="98b54-138">Alle geselecteerde entiteiten worden uit de nieuwe gegevensbron opgenomen.</span><span class="sxs-lookup"><span data-stu-id="98b54-138">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="98b54-139">![Dialoogvenster met een lijst met entiteiten uit een model.json-bestand](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="98b54-139">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="98b54-140">Geef aan voor welke gegevensentiteiten u profilering wilt inschakelen en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="98b54-140">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="98b54-141">Met gegevensprofilering kunnen analyses en andere functies worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="98b54-141">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="98b54-142">U kunt de hele entiteit selecteren, die alle kenmerken uit de entiteit selecteert, of bepaalde kenmerken selecteren.</span><span class="sxs-lookup"><span data-stu-id="98b54-142">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="98b54-143">Standaard is geen entiteit ingeschakeld voor gegevensprofilering.</span><span class="sxs-lookup"><span data-stu-id="98b54-143">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="98b54-144">![Dialoogvenster met gegevensprofilering](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="98b54-144">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="98b54-145">Na het opslaan van uw selecties wordt de pagina **Gegevensbronnen** geopend.</span><span class="sxs-lookup"><span data-stu-id="98b54-145">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="98b54-146">U zou nu de Common Data Model-mapverbinding moeten zien als een gegevensbron.</span><span class="sxs-lookup"><span data-stu-id="98b54-146">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="98b54-147">Een model.json- of manifest.json-bestand kan alleen worden gekoppeld aan één gegevensbron in dezelfde omgeving.</span><span class="sxs-lookup"><span data-stu-id="98b54-147">A model.json file or manifest.json can only associate with one data source in the same environment.</span></span> <span data-ttu-id="98b54-148">Hetzelfde model.json- of manifest.json-bestand kan echter worden gebruikt voor gegevensbronnen in meerdere omgevingen.</span><span class="sxs-lookup"><span data-stu-id="98b54-148">However, the same model.json or manifest.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="98b54-149">Een gegevensbron voor een Common Data Model-map bewerken</span><span class="sxs-lookup"><span data-stu-id="98b54-149">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="98b54-150">U kunt de toegangssleutel bijwerken voor het opslagaccount dat de map Common Data Model bevat.</span><span class="sxs-lookup"><span data-stu-id="98b54-150">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="98b54-151">U kunt ook het model.json- of manifest.json-bestand wijzigen.</span><span class="sxs-lookup"><span data-stu-id="98b54-151">You may also change the model.json or manifest.json file.</span></span> <span data-ttu-id="98b54-152">Als u verbinding wilt maken met een andere container dan uw opslagaccount, of de accountnaam wilt wijzigen, moet u [een nieuwe gegevensbronverbinding maken](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="98b54-152">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="98b54-153">Ga in doelgroepinzichten naar **Gegevens** > **Gegevensbronnen**.</span><span class="sxs-lookup"><span data-stu-id="98b54-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="98b54-154">Selecteer het weglatingsteken naast de gegevensbron die u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="98b54-154">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="98b54-155">Selecteer de optie **Bewerken** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="98b54-155">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="98b54-156">Werk desgewenst de **Toegangssleutel** bij en selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="98b54-156">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Dialoogvenster om een toegangssleutel voor een bestaande gegevensbron te wijzigen en bij te werken](media/edit-access-key.png)

5. <span data-ttu-id="98b54-158">Optioneel kunt u bijwerken vanaf een accountsleutelverbinding naar een resource- of een abonnementsverbinding.</span><span class="sxs-lookup"><span data-stu-id="98b54-158">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="98b54-159">Zie [Doelgroepinzichten verbinden met een Azure Data Lake Storage Gen2-account met een Azure Service Principal](connect-service-principal.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="98b54-159">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="98b54-160">U kunt geen informatie over **Container** wijzigen bij het bijwerken van de verbinding.</span><span class="sxs-lookup"><span data-stu-id="98b54-160">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]

   > ![Dialoogvenster om verbindingsdetails voor Azure Data Lake in te voeren met een bestaand opslagaccount](media/enter-existing-storage-details.png)

   > [!NOTE]
   > <span data-ttu-id="98b54-162">U hebt een van de volgende rollen nodig voor de container of het opslagaccount waarnaar hierboven wordt verwezen om verbinding te kunnen maken met een gegevensbron en deze te maken:</span><span class="sxs-lookup"><span data-stu-id="98b54-162">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="98b54-163">Opslag-blobgegevens lezer</span><span class="sxs-lookup"><span data-stu-id="98b54-163">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="98b54-164">Opslag-blobgegevens eigenaar</span><span class="sxs-lookup"><span data-stu-id="98b54-164">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="98b54-165">Inzender van opslag-blobgegevens</span><span class="sxs-lookup"><span data-stu-id="98b54-165">Storage Blob Data Contributo</span></span>


6. <span data-ttu-id="98b54-166">Kies optioneel een ander model.json- of manifest.json-bestand met een andere set entiteiten uit de container.</span><span class="sxs-lookup"><span data-stu-id="98b54-166">Optionally, choose a different model.json or manifest.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="98b54-167">Optioneel kunt u extra entiteiten selecteren om op te nemen.</span><span class="sxs-lookup"><span data-stu-id="98b54-167">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="98b54-168">U kunt ook reeds geselecteerde entiteiten verwijderen als er geen afhankelijkheden zijn.</span><span class="sxs-lookup"><span data-stu-id="98b54-168">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="98b54-169">Als er afhankelijkheden zijn in het bestaande model.json- of manifest.json-bestand en de set entiteiten, ziet u een foutbericht en kunt u geen ander model.json- of manifest.json-bestand selecteren.</span><span class="sxs-lookup"><span data-stu-id="98b54-169">If there are dependencies on the existing model.json or manifest.json file and the set of entities, you'll see an error message and can't select a different model.json or manifest.json file.</span></span> <span data-ttu-id="98b54-170">Verwijder die afhankelijkheden voordat u het model.json- of manifest.json-bestand wijzigt, of maak een nieuw gegevensbron met model.json of manifest.json dat u wilt gebruiken om te voorkomen dat u de afhankelijkheden verwijdert.</span><span class="sxs-lookup"><span data-stu-id="98b54-170">Remove those dependencies before changing the model.json or manifest.json file or create a new data source with the model.json or manifest.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="98b54-171">Optioneel kunt u extra kenmerken of entiteiten selecteren om gegevensprofilering in te schakelen of reeds geselecteerde uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="98b54-171">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   


[!INCLUDE[footer-include](../includes/footer-banner.md)]