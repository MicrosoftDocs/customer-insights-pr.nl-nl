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
# <a name="manage-environments"></a><span data-ttu-id="51b73-103">Omgevingen beheren</span><span class="sxs-lookup"><span data-stu-id="51b73-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="51b73-104">In dit artikel wordt uitgelegd hoe u een nieuwe organisatie maakt en hoe u een omgeving inricht.</span><span class="sxs-lookup"><span data-stu-id="51b73-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="51b73-105">Aanmelden en een organisatie maken</span><span class="sxs-lookup"><span data-stu-id="51b73-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="51b73-106">Ga naar de website [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="51b73-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="51b73-107">Selecteer **Aan de slag**.</span><span class="sxs-lookup"><span data-stu-id="51b73-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="51b73-108">Kies het gewenste aanmeldingsscenario en selecteer de bijbehorende koppeling.</span><span class="sxs-lookup"><span data-stu-id="51b73-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="51b73-109">Accepteer de algemene voorwaarden en selecteer **Doorgaan** om te beginnen met het maken van de organisatie.</span><span class="sxs-lookup"><span data-stu-id="51b73-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="51b73-110">Nadat de omgeving is gemaakt, wordt u doorgestuurd naar [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="51b73-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="51b73-111">Gebruik de demo-omgeving om de app te verkennen of maak een nieuwe omgeving door de stappen in de volgende sectie te volgen.</span><span class="sxs-lookup"><span data-stu-id="51b73-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="51b73-112">Nadat u de omgevingsinstellingen hebt opgegeven, selecteert u **Maken**.</span><span class="sxs-lookup"><span data-stu-id="51b73-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="51b73-113">Nadat de omgeving is gemaakt, wordt u aangemeld.</span><span class="sxs-lookup"><span data-stu-id="51b73-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="51b73-114">Een omgeving maken in een bestaande organisatie</span><span class="sxs-lookup"><span data-stu-id="51b73-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="51b73-115">U kunt op twee manieren een nieuwe omgeving maken.</span><span class="sxs-lookup"><span data-stu-id="51b73-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="51b73-116">U kunt een geheel nieuwe configuratie opgeven of u kunt enkele configuratie-instellingen uit een bestaande omgeving kopiëren.</span><span class="sxs-lookup"><span data-stu-id="51b73-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="51b73-117">Een omgeving maken:</span><span class="sxs-lookup"><span data-stu-id="51b73-117">To create an environment:</span></span>

1. <span data-ttu-id="51b73-118">Selecteer het symbool **instellingen** in de kop van de app.</span><span class="sxs-lookup"><span data-stu-id="51b73-118">Select the **Settings** symbol in the header of the app.</span></span>

1. <span data-ttu-id="51b73-119">Selecteer **Nieuwe omgeving**.</span><span class="sxs-lookup"><span data-stu-id="51b73-119">Select **New environment**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="51b73-120">![Omgevingsinstellingen](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="51b73-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="51b73-121">Selecteer **Nieuwe omgeving** in het dialoogvenster **Nieuwe omgeving maken**.</span><span class="sxs-lookup"><span data-stu-id="51b73-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="51b73-122">Als u [gegevens wilt kopiëren uit de huidige omgeving](#additional-considerations-for-copy-configuration-preview), selecteert u **Kopiëren uit bestaande omgeving**.</span><span class="sxs-lookup"><span data-stu-id="51b73-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="51b73-123">U ziet een lijst met alle beschikbare omgevingen in uw organisatie waaruit u gegevens kunt kopiëren.</span><span class="sxs-lookup"><span data-stu-id="51b73-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="51b73-124">Geef de volgende details op:</span><span class="sxs-lookup"><span data-stu-id="51b73-124">Provide the following details:</span></span>
   - <span data-ttu-id="51b73-125">**Naam**: de naam voor deze omgeving.</span><span class="sxs-lookup"><span data-stu-id="51b73-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="51b73-126">Dit veld is al ingevuld als u hebt gekopieerd vanuit een bestaande omgeving, maar u kunt dit wijzigen.</span><span class="sxs-lookup"><span data-stu-id="51b73-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="51b73-127">**Regio**: de regio waarin de service wordt geïmplementeerd en gehost.</span><span class="sxs-lookup"><span data-stu-id="51b73-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="51b73-128">**Type**: selecteer of u een productie- of sandbox-omgeving wilt maken.</span><span class="sxs-lookup"><span data-stu-id="51b73-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="51b73-129">U kunt desgewenst het **Geavanceerde instellingen** inschakelen:</span><span class="sxs-lookup"><span data-stu-id="51b73-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="51b73-130">**Alle gegevens opslaan naar**: geeft aan waar u de uitvoergegevens wilt opslaan die zijn gegenereerd vanuit Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="51b73-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="51b73-131">U hebt twee opties: **Opslag Customer Insights** (een Azure Data Lake beheerd door het Customer Insights-team) en **Azure Data Lake Storage Gen2** (uw eigen Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="51b73-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="51b73-132">Standaard is de opslagoptie Customer Insights geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="51b73-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="51b73-133">Door gegevens op te slaan in Azure Data Lake Storage stemt u ermee in dat gegevens worden overgebracht naar en opgeslagen in de juiste geografische locatie voor dat Azure Storage-account, die kan afwijken van waar gegevens zijn opgeslagen in Dynamics 365 Customer Insights. Meer informatie vindt u in het Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="51b73-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="51b73-134">Meer informatie op het Microsoft Trust Center.</span><span class="sxs-lookup"><span data-stu-id="51b73-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="51b73-135">Momenteel worden opgenomen entiteiten altijd opgeslagen in het beheerde data lake van Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="51b73-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="51b73-136">We ondersteunen alleen Azure Data Lake Gen2-opslagaccounts uit dezelfde Azure-regio die u hebt geselecteerd bij het maken van de omgeving.</span><span class="sxs-lookup"><span data-stu-id="51b73-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="51b73-137">We ondersteunen alleen opslagaccounts waarvoor Azure Data Lake Gen2 Hierarchical Name Space (HNS) is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="51b73-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="51b73-138">Voor de Azure Data Lake Storage Gen2-oplossing kunt u kiezen tussen een resource-optie en een abonnementsoptie voor verificatie.</span><span class="sxs-lookup"><span data-stu-id="51b73-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="51b73-139">Zie [Doelgroepinzichten verbinden met een Azure Data Lake Storage Gen2-account met een Azure Service Principal](connect-service-principal.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="51b73-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="51b73-140">De naam van de **Container** kan niet worden gewijzigd en is "customerinsights".</span><span class="sxs-lookup"><span data-stu-id="51b73-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="51b73-141">Als u [voorspellingen](predictions.md) wilt gebruiken, voert u de URL van het Common Data Service-exemplaar in het veld **Serveradres** in onder **Voorspellingen gebruiken**.</span><span class="sxs-lookup"><span data-stu-id="51b73-141">If you want to use [predictions](predictions.md), enter the Common Data Service instance URL in the **Server address** field under **Use predictions**.</span></span>

   <span data-ttu-id="51b73-142">Wanneer u processen uitvoert, zoals het opnemen van gegevens of het maken van segmenten, worden overeenkomstige mappen gemaakt in het opslagaccount dat u hierboven hebt opgegeven.</span><span class="sxs-lookup"><span data-stu-id="51b73-142">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="51b73-143">Gegevensbestanden en model.json-bestanden worden op basis van het proces dat u uitvoert gemaakt en toegevoegd aan de respectievelijke submappen.</span><span class="sxs-lookup"><span data-stu-id="51b73-143">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="51b73-144">Als u meerdere omgevingen van Customer Insights maakt en ervoor kiest de uitvoerentiteiten van die omgevingen op te slaan in uw opslagaccount, worden voor elke omgeving aparte mappen gemaakt met ci_<environmentid> in de container.</span><span class="sxs-lookup"><span data-stu-id="51b73-144">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="51b73-145">Aanvullende overwegingen voor kopieerconfiguratie (preview)</span><span class="sxs-lookup"><span data-stu-id="51b73-145">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="51b73-146">De volgende configuratie-instellingen worden gekopieerd:</span><span class="sxs-lookup"><span data-stu-id="51b73-146">The following configuration settings are copied:</span></span>

- <span data-ttu-id="51b73-147">Functieconfiguraties</span><span class="sxs-lookup"><span data-stu-id="51b73-147">Feature configurations</span></span>
- <span data-ttu-id="51b73-148">Opgenomen/geïmporteerde gegevensbronnen</span><span class="sxs-lookup"><span data-stu-id="51b73-148">Inegsted/imported data sources</span></span>
- <span data-ttu-id="51b73-149">Configuratie van gegevensunificatie (Toewijzing, Overeenkomst, Samenvoeging)</span><span class="sxs-lookup"><span data-stu-id="51b73-149">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="51b73-150">Segmenten</span><span class="sxs-lookup"><span data-stu-id="51b73-150">Segments</span></span>
- <span data-ttu-id="51b73-151">Metingen</span><span class="sxs-lookup"><span data-stu-id="51b73-151">Measures</span></span>
- <span data-ttu-id="51b73-152">Relaties</span><span class="sxs-lookup"><span data-stu-id="51b73-152">Relationships</span></span>
- <span data-ttu-id="51b73-153">Activiteiten</span><span class="sxs-lookup"><span data-stu-id="51b73-153">Activities</span></span>
- <span data-ttu-id="51b73-154">Index voor zoeken en filteren</span><span class="sxs-lookup"><span data-stu-id="51b73-154">Search & filter Index</span></span>
- <span data-ttu-id="51b73-155">Exportbestemmingen</span><span class="sxs-lookup"><span data-stu-id="51b73-155">Export destinations</span></span>
- <span data-ttu-id="51b73-156">Geplande vernieuwing</span><span class="sxs-lookup"><span data-stu-id="51b73-156">Scheduled refresh</span></span>
- <span data-ttu-id="51b73-157">Verrijkingen</span><span class="sxs-lookup"><span data-stu-id="51b73-157">Enrichments</span></span>
- <span data-ttu-id="51b73-158">Modelbeheer</span><span class="sxs-lookup"><span data-stu-id="51b73-158">Model management</span></span>
- <span data-ttu-id="51b73-159">Roltoewijzingen</span><span class="sxs-lookup"><span data-stu-id="51b73-159">Role assignments</span></span>

<span data-ttu-id="51b73-160">De volgende instellingen worden *niet* gekopieerd:</span><span class="sxs-lookup"><span data-stu-id="51b73-160">The following settings are *not* copied:</span></span>

- <span data-ttu-id="51b73-161">Klantprofielen.</span><span class="sxs-lookup"><span data-stu-id="51b73-161">Customer profiles.</span></span>
- <span data-ttu-id="51b73-162">Referenties voor gegevensbron.</span><span class="sxs-lookup"><span data-stu-id="51b73-162">Data source credentials.</span></span> <span data-ttu-id="51b73-163">U moet de referenties voor elke gegevensbron opgeven en de gegevensbronnen handmatig vernieuwen.</span><span class="sxs-lookup"><span data-stu-id="51b73-163">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="51b73-164">Gegevensbronnen uit Common Data Model-map en beheerd lake voor Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="51b73-164">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="51b73-165">U moet die gegevensbronnen handmatig maken met dezelfde naam als in de bronomgeving.</span><span class="sxs-lookup"><span data-stu-id="51b73-165">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="51b73-166">Wanneer u een omgeving kopieert, ziet u een bevestigingsbericht dat de nieuwe omgeving is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="51b73-166">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="51b73-167">Selecteer **Ga naar gegevensbronnen** om de lijst met gegevensbronnen te zien.</span><span class="sxs-lookup"><span data-stu-id="51b73-167">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="51b73-168">Alle gegevensbronnen hebben de status **Referenties vereist**.</span><span class="sxs-lookup"><span data-stu-id="51b73-168">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="51b73-169">Bewerk de gegevensbronnen en voer de referenties in om ze te vernieuwen.</span><span class="sxs-lookup"><span data-stu-id="51b73-169">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="51b73-170">![Gekopieerde gegevensbronnen](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="51b73-170">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="51b73-171">Ga na het vernieuwen van de gegevensbronnen naar **Gegevens** > **Harmoniseren**.</span><span class="sxs-lookup"><span data-stu-id="51b73-171">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="51b73-172">Hier vindt u instellingen uit de bronomgeving.</span><span class="sxs-lookup"><span data-stu-id="51b73-172">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="51b73-173">Bewerk deze indien nodig of selecteer **Uitvoeren** om het proces voor gegevensharmonisering te starten en de geharmoniseerde klantentiteit te maken.</span><span class="sxs-lookup"><span data-stu-id="51b73-173">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="51b73-174">Ga wanneer de gegevensharmonisering is voltooid naar **Meetcriteria** en **Segmenten** om deze eveneens te vernieuwen.</span><span class="sxs-lookup"><span data-stu-id="51b73-174">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="51b73-175">Een bestaande omgeving bewerken</span><span class="sxs-lookup"><span data-stu-id="51b73-175">Edit an existing environment</span></span>

<span data-ttu-id="51b73-176">U kunt enkele details van bestaande omgevingen bewerken.</span><span class="sxs-lookup"><span data-stu-id="51b73-176">You can edit some of the details of existing environments.</span></span>

1. <span data-ttu-id="51b73-177">Ga naar **Beheer** > **Systeem** > **Info**.</span><span class="sxs-lookup"><span data-stu-id="51b73-177">Go to **Admin** > **System** > **About**.</span></span>

2. <span data-ttu-id="51b73-178">Selecteer **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="51b73-178">Select **Edit**.</span></span>

3. <span data-ttu-id="51b73-179">U kunt de **weergavenaam** van de omgeving bijwerken, maar u kunt de **regio** of het **type** niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="51b73-179">You can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="51b73-180">Als een omgeving is geconfigureerd om gegevens in op te slaan Azure Data Lake Storage Gen2, kunt u **Accountsleutel** bijwerken.</span><span class="sxs-lookup"><span data-stu-id="51b73-180">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="51b73-181">U kunt de **accountnaam** of naam van de **container** echter niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="51b73-181">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="51b73-182">Optioneel kunt u bijwerken vanaf een accountsleutelverbinding naar een resource- of een abonnementsverbinding.</span><span class="sxs-lookup"><span data-stu-id="51b73-182">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="51b73-183">Na het upgraden kunt u na de update geen accountsleutel meer gebruiken.</span><span class="sxs-lookup"><span data-stu-id="51b73-183">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="51b73-184">Zie [Doelgroepinzichten verbinden met een Azure Data Lake Storage Gen2-account met een Azure Service Principal](connect-service-principal.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="51b73-184">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="51b73-185">U kunt geen informatie over **Container** wijzigen bij het bijwerken van de verbinding.</span><span class="sxs-lookup"><span data-stu-id="51b73-185">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="51b73-186">Een bestaande omgeving opnieuw instellen</span><span class="sxs-lookup"><span data-stu-id="51b73-186">Reset an existing environment</span></span>

<span data-ttu-id="51b73-187">U kunt een omgeving terugzetten naar een lege staat als u alle configuraties wilt verwijderen en de opgenomen gegevens wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="51b73-187">You can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="51b73-188">Ga naar **Beheer** > **Systeem** > **Info**.</span><span class="sxs-lookup"><span data-stu-id="51b73-188">Go to **Admin** > **System** > **About**.</span></span>

2.  <span data-ttu-id="51b73-189">Selecteer **Opnieuw instellen**.</span><span class="sxs-lookup"><span data-stu-id="51b73-189">Select **Reset**.</span></span> 

3.  <span data-ttu-id="51b73-190">Om het verwijderen te bevestigen, voert u de omgevingsnaam in en selecteert u **Opnieuw instellen**.</span><span class="sxs-lookup"><span data-stu-id="51b73-190">To confirm the deletion, enter the environment name and select **Reset**.</span></span>


## <a name="delete-an-existing-environment"></a><span data-ttu-id="51b73-191">Een bestaande omgeving verwijderen</span><span class="sxs-lookup"><span data-stu-id="51b73-191">Delete an existing environment</span></span>

1. <span data-ttu-id="51b73-192">Ga naar **Beheer** > **Systeem** > **Info**.</span><span class="sxs-lookup"><span data-stu-id="51b73-192">Go to **Admin** > **System** > **About**.</span></span>

1. <span data-ttu-id="51b73-193">Selecteer **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="51b73-193">Select **Delete**.</span></span>

1. <span data-ttu-id="51b73-194">Om de verwijdering te bevestigen, voert u de omgevingsnaam in en selecteert u **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="51b73-194">To confirm the deletion, enter the environment name and select **Delete**.</span></span>
