---
title: Verrijking met aangepaste SFTP-import
description: Algemene informatie over de aangepaste SFTP-importverrijking.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d9e095ef793cbd25415864f76a541dce68fafe47
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595849"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="be31a-103">Klantprofielen verrijken met aangepaste gegevens (preview)</span><span class="sxs-lookup"><span data-stu-id="be31a-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="be31a-104">Dankzij de aangepaste import van Secure File Transfer Protocol (SFTP) kunt u gegevens importeren die niet door het proces van gegevensharmonisatie hoeven te gaan.</span><span class="sxs-lookup"><span data-stu-id="be31a-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="be31a-105">Het is een flexibele, veilige en gemakkelijke manier om uw gegevens binnen te halen.</span><span class="sxs-lookup"><span data-stu-id="be31a-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="be31a-106">Aangepaste SFTP-import kan worden gebruikt in combinatie met [SFTP-export](export-sftp.md), waarmee u de klantprofielgegevens kunt exporteren die nodig zijn voor verrijking.</span><span class="sxs-lookup"><span data-stu-id="be31a-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="be31a-107">De gegevens kunnen vervolgens worden verwerkt, verrijkt en aangepaste SFTP-import kan worden gebruikt om de verrijkte gegevens terug te brengen naar de doelgroepinzichten van Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="be31a-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="be31a-108">Vereisten</span><span class="sxs-lookup"><span data-stu-id="be31a-108">Prerequisites</span></span>

<span data-ttu-id="be31a-109">Om aangepaste SFTP-import te configureren, moet aan de volgende voorwaarden worden voldaan:</span><span class="sxs-lookup"><span data-stu-id="be31a-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="be31a-110">U hebt gebruikersreferenties (gebruikersnaam en wachtwoord) voor de SFTP-locatie vanwaar de gegevens worden geïmporteerd.</span><span class="sxs-lookup"><span data-stu-id="be31a-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="be31a-111">U hebt de URL en het poortnummer (meestal 22) voor de SFTP-host.</span><span class="sxs-lookup"><span data-stu-id="be31a-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="be31a-112">U hebt de bestandsnaam en locatie van het bestand dat moet worden geïmporteerd op de SFTP-host.</span><span class="sxs-lookup"><span data-stu-id="be31a-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="be31a-113">Er is een *model.json*-bestand dat de planning specificeert voor de gegevens die moeten worden geïmporteerd.</span><span class="sxs-lookup"><span data-stu-id="be31a-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="be31a-114">Dit bestand moet in dezelfde map staan als het te importeren bestand.</span><span class="sxs-lookup"><span data-stu-id="be31a-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="be31a-115">U hebt [Beheerders](permissions.md#administrator)machtiging.</span><span class="sxs-lookup"><span data-stu-id="be31a-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="be31a-116">Configuratie</span><span class="sxs-lookup"><span data-stu-id="be31a-116">Configuration</span></span>

1. <span data-ttu-id="be31a-117">Ga naar **Gegevens** > **Verrijking** en selecteer het tabblad **Detecteren**.</span><span class="sxs-lookup"><span data-stu-id="be31a-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="be31a-118">Selecteer op de **Aangepaste SFTP-importtegel** de optie **Mijn gegevens verrijken**.</span><span class="sxs-lookup"><span data-stu-id="be31a-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="be31a-119">![Aangepaste SFTP-import-tegel](media/SFTP_Custom_Import_tile.png "Aangepaste SFTP-import-tegel")</span><span class="sxs-lookup"><span data-stu-id="be31a-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="be31a-120">Selecteer **Aan de slag** en geef de referenties en het adres voor de SFTP-server op.</span><span class="sxs-lookup"><span data-stu-id="be31a-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="be31a-121">Bijvoorbeeld sftp://mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="be31a-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="be31a-122">Voer de naam in van het bestand dat de gegevens bevat en het pad naar het bestand op de SFTP-server als het niet in de hoofdmap staat.</span><span class="sxs-lookup"><span data-stu-id="be31a-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="be31a-123">Bevestig alle invoer door **Verbinden met aangepaste import** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="be31a-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="be31a-124">![Flyout aangepaste SFTP-importconfiguratie](media/SFTP_Custom_Import_Configuration_flyout.png "Flyout aangepaste SFTP-importconfiguratie")</span><span class="sxs-lookup"><span data-stu-id="be31a-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="be31a-125">Veldtoewijzingen definiëren</span><span class="sxs-lookup"><span data-stu-id="be31a-125">Defining field mappings</span></span> 

<span data-ttu-id="be31a-126">De directory die het bestand bevat dat op de SFTP-server moet worden geïmporteerd, moet ook een *model.json*-bestand bevatten.</span><span class="sxs-lookup"><span data-stu-id="be31a-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="be31a-127">Dit bestand definieert het schema dat moet worden gebruikt voor het importeren van de gegevens.</span><span class="sxs-lookup"><span data-stu-id="be31a-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="be31a-128">Het schema moet [het Common Data Model](/common-data-model/) gebruiken om de veldtoewijzing op te geven.</span><span class="sxs-lookup"><span data-stu-id="be31a-128">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="be31a-129">Een eenvoudig voorbeeld van een model.json-bestand ziet er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="be31a-129">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="be31a-130">Verrijkingsresultaten</span><span class="sxs-lookup"><span data-stu-id="be31a-130">Enrichment results</span></span>

<span data-ttu-id="be31a-131">Selecteer **Uitvoeren** vanaf de opdrachtbalk om het verrijkingsproces te starten.</span><span class="sxs-lookup"><span data-stu-id="be31a-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="be31a-132">U kunt de verrijking ook automatisch laten uitvoeren als onderdeel van een [geplande vernieuwing](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="be31a-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="be31a-133">De verwerkingstijd is afhankelijk van de grootte van de te importeren gegevens en de verbinding met de SFTP-server.</span><span class="sxs-lookup"><span data-stu-id="be31a-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="be31a-134">Nadat het verrijkingsproces is voltooid, kunt u uw net geïmporteerde aangepaste verrijkingsgegevens bekijken onder **Mijn verrijkingen**.</span><span class="sxs-lookup"><span data-stu-id="be31a-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="be31a-135">Ook vindt u daar het tijdstip van de laatste update en het aantal verrijkte profielen.</span><span class="sxs-lookup"><span data-stu-id="be31a-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="be31a-136">U kunt een gedetailleerd overzicht van elk verrijkt profiel openen door **Verrijkte gegevens weergeven** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="be31a-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="be31a-137">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="be31a-137">Next steps</span></span>

<span data-ttu-id="be31a-138">Bouw voort op uw verrijkte klantgegevens.</span><span class="sxs-lookup"><span data-stu-id="be31a-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="be31a-139">Maak [segmenten](segments.md), [metingen](measures.md) en [exporteer de gegevens](export-destinations.md) om uw klanten gepersonaliseerde ervaringen te bieden.</span><span class="sxs-lookup"><span data-stu-id="be31a-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]