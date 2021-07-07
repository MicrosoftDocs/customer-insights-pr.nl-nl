---
title: Verrijking met aangepaste SFTP-import
description: Algemene informatie over de aangepaste SFTP-importverrijking.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f92b36ac5364ea8586f9cbba7ba03178641555c0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304644"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="152c8-103">Klantprofielen verrijken met aangepaste gegevens (preview)</span><span class="sxs-lookup"><span data-stu-id="152c8-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="152c8-104">Dankzij de aangepaste import van Secure File Transfer Protocol (SFTP) kunt u gegevens importeren die niet door het proces van gegevensharmonisatie hoeven te gaan.</span><span class="sxs-lookup"><span data-stu-id="152c8-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="152c8-105">Het is een flexibele, veilige en gemakkelijke manier om uw gegevens binnen te halen.</span><span class="sxs-lookup"><span data-stu-id="152c8-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="152c8-106">Aangepaste SFTP-import kan worden gebruikt in combinatie met [SFTP-export](export-sftp.md), waarmee u de klantprofielgegevens kunt exporteren die nodig zijn voor verrijking.</span><span class="sxs-lookup"><span data-stu-id="152c8-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="152c8-107">De gegevens kunnen vervolgens worden verwerkt en verrijkt, en aangepaste SFTP-import kan worden gebruikt om de verrijkte gegevens terug te brengen naar de doelgroepinzichten van Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="152c8-107">The data can then be processed and enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="152c8-108">Vereisten</span><span class="sxs-lookup"><span data-stu-id="152c8-108">Prerequisites</span></span>

<span data-ttu-id="152c8-109">Om aangepaste SFTP-import te configureren, moet aan de volgende voorwaarden worden voldaan:</span><span class="sxs-lookup"><span data-stu-id="152c8-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="152c8-110">U hebt de bestandsnaam en locatie (pad) van het bestand dat moet worden geïmporteerd op de SFTP-host.</span><span class="sxs-lookup"><span data-stu-id="152c8-110">You have the file name and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="152c8-111">Er is een bestand *model.json* dat [het Common Data Model-schema](/common-data-model/) specificeert voor de te importeren gegevens.</span><span class="sxs-lookup"><span data-stu-id="152c8-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="152c8-112">Dit bestand moet in dezelfde map staan als het te importeren bestand.</span><span class="sxs-lookup"><span data-stu-id="152c8-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="152c8-113">Er is al een SFTP-verbinding geconfigureerd door een beheerder *of* u hebt [beheerdersmachtigingen](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="152c8-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="152c8-114">U hebt de gebruikersgegevens, de URL en het poortnummer nodig voor de SFTP-locatie waaruit u gegevens wilt importeren.</span><span class="sxs-lookup"><span data-stu-id="152c8-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="152c8-115">De import configureren</span><span class="sxs-lookup"><span data-stu-id="152c8-115">Configure the import</span></span>

1. <span data-ttu-id="152c8-116">Ga naar **Gegevens** > **Verrijking** en selecteer het tabblad **Detecteren**.</span><span class="sxs-lookup"><span data-stu-id="152c8-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="152c8-117">Selecteer op de tegel **Aangepaste SFTP-import** de optie **Mijn gegevens verrijken** en selecteer vervolgens **Aan de slag**.</span><span class="sxs-lookup"><span data-stu-id="152c8-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Tegel Aangepaste SFTP-import.":::

1. <span data-ttu-id="152c8-119">Selecteer een [verbinding](connections.md) in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="152c8-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="152c8-120">Neem contact op met een beheerder als er geen verbinding beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="152c8-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="152c8-121">Als u een beheerder bent, kunt u een verbinding maken door **Verbinding toevoegen** te selecteren en **Aangepaste SFTP-import** te kiezen in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="152c8-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the dropdown list.</span></span>

1. <span data-ttu-id="152c8-122">Selecteer **Verbinding maken met aangepaste import** om de geselecteerde verbinding te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="152c8-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="152c8-123">Selecteer **Volgende** en voer het **Pad** en de **Bestandsnaam** in van het gegevensbestand dat u wilt importeren.</span><span class="sxs-lookup"><span data-stu-id="152c8-123">Select **Next** and enter the **Path** and **Filename** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Schermopname bij invoeren van gegevenslocatie.":::

1. <span data-ttu-id="152c8-125">Selecteer **Volgende** en geef een naam op voor de verrijking en een naam voor de uitvoerentiteit.</span><span class="sxs-lookup"><span data-stu-id="152c8-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="152c8-126">Selecteer **Verrijking opslaan** na het bekijken van uw keuzes.</span><span class="sxs-lookup"><span data-stu-id="152c8-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="152c8-127">De verbinding voor aangepaste SFTP-import configureren</span><span class="sxs-lookup"><span data-stu-id="152c8-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="152c8-128">U moet een beheerder zijn om verbindingen te kunnen configureren.</span><span class="sxs-lookup"><span data-stu-id="152c8-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="152c8-129">Selecteer **Verbinding toevoegen** bij het configureren van een verrijking *of* ga naar **Beheerder** > **Verbindingen** en selecteer **Instellen** op de tegel Aangepaste import.</span><span class="sxs-lookup"><span data-stu-id="152c8-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="152c8-130">Voer een naam in voor de verbinding in het vak **Weergavenaam**.</span><span class="sxs-lookup"><span data-stu-id="152c8-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="152c8-131">Voer een geldige gebruikersnaam, wachtwoord en host-URL in voor de SFTP-server waarop de te importeren gegevens zich bevinden.</span><span class="sxs-lookup"><span data-stu-id="152c8-131">Enter a valid username, password, and host URL for the SFTP server that the data to be imported resides on.</span></span>

1. <span data-ttu-id="152c8-132">Bekijk en geef toestemming voor **Gegevensprivacy en naleving** door het selectievakje **Ik ga akkoord** in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="152c8-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="152c8-133">Selecteer **Verifiëren** om de configuratie te valideren.</span><span class="sxs-lookup"><span data-stu-id="152c8-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="152c8-134">Nadat de verificatie is voltooid, kan de verbinding worden opgeslagen door **Opslaan** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="152c8-134">Once the verification has completed, the connection can be saved by selecting **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="152c8-135">![Experian-verbindingsconfiguratiepagina](media/enrichment-SFTP-connection.png "Experian-verbindingsconfiguratiepagina")</span><span class="sxs-lookup"><span data-stu-id="152c8-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="152c8-136">Veldtoewijzingen definiëren</span><span class="sxs-lookup"><span data-stu-id="152c8-136">Defining field mappings</span></span> 

<span data-ttu-id="152c8-137">De directory die het bestand bevat dat op de SFTP-server moet worden geïmporteerd, moet ook een *model.json*-bestand bevatten.</span><span class="sxs-lookup"><span data-stu-id="152c8-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="152c8-138">Dit bestand definieert het schema dat moet worden gebruikt voor het importeren van de gegevens.</span><span class="sxs-lookup"><span data-stu-id="152c8-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="152c8-139">Het schema moet [Common Data Model](/common-data-model/) gebruiken om de veldtoewijzing te specificeren.</span><span class="sxs-lookup"><span data-stu-id="152c8-139">The schema has to use [Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="152c8-140">Een eenvoudig voorbeeld van een model.json-bestand ziet er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="152c8-140">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="152c8-141">Verrijkingsresultaten</span><span class="sxs-lookup"><span data-stu-id="152c8-141">Enrichment results</span></span>

<span data-ttu-id="152c8-142">Selecteer **Uitvoeren** vanaf de opdrachtbalk om het verrijkingsproces te starten.</span><span class="sxs-lookup"><span data-stu-id="152c8-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="152c8-143">U kunt de verrijking ook automatisch laten uitvoeren als onderdeel van een [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="152c8-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="152c8-144">De verwerkingstijd is afhankelijk van de grootte van de te importeren gegevens en de verbinding met de SFTP-server.</span><span class="sxs-lookup"><span data-stu-id="152c8-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="152c8-145">Nadat het verrijkingsproces is voltooid, kunt u uw net geïmporteerde aangepaste verrijkingsgegevens bekijken onder **Mijn verrijkingen**.</span><span class="sxs-lookup"><span data-stu-id="152c8-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="152c8-146">Ook vindt u daar het tijdstip van de laatste update en het aantal verrijkte profielen.</span><span class="sxs-lookup"><span data-stu-id="152c8-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="152c8-147">U kunt een gedetailleerd overzicht van elk verrijkt profiel openen door **Verrijkte gegevens weergeven** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="152c8-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="152c8-148">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="152c8-148">Next steps</span></span>

<span data-ttu-id="152c8-149">Bouw voort op uw verrijkte klantgegevens.</span><span class="sxs-lookup"><span data-stu-id="152c8-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="152c8-150">Maak [segmenten](segments.md) en [meetcriteria](measures.md), en [exporteer de gegevens](export-destinations.md) om gepersonaliseerde ervaringen aan uw klanten te leveren.</span><span class="sxs-lookup"><span data-stu-id="152c8-150">Create [segments](segments.md) and [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
