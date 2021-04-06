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
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Klantprofielen verrijken met aangepaste gegevens (preview)

Dankzij de aangepaste import van Secure File Transfer Protocol (SFTP) kunt u gegevens importeren die niet door het proces van gegevensharmonisatie hoeven te gaan. Het is een flexibele, veilige en gemakkelijke manier om uw gegevens binnen te halen. Aangepaste SFTP-import kan worden gebruikt in combinatie met [SFTP-export](export-sftp.md), waarmee u de klantprofielgegevens kunt exporteren die nodig zijn voor verrijking. De gegevens kunnen vervolgens worden verwerkt, verrijkt en aangepaste SFTP-import kan worden gebruikt om de verrijkte gegevens terug te brengen naar de doelgroepinzichten van Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Vereisten

Om aangepaste SFTP-import te configureren, moet aan de volgende voorwaarden worden voldaan:

- U hebt gebruikersreferenties (gebruikersnaam en wachtwoord) voor de SFTP-locatie vanwaar de gegevens worden geïmporteerd.
- U hebt de URL en het poortnummer (meestal 22) voor de SFTP-host.
- U hebt de bestandsnaam en locatie van het bestand dat moet worden geïmporteerd op de SFTP-host.
- Er is een *model.json*-bestand dat de planning specificeert voor de gegevens die moeten worden geïmporteerd. Dit bestand moet in dezelfde map staan als het te importeren bestand.
- U hebt [Beheerders](permissions.md#administrator)machtiging.

## <a name="configuration"></a>Configuratie

1. Ga naar **Gegevens** > **Verrijking** en selecteer het tabblad **Detecteren**.

1. Selecteer op de **Aangepaste SFTP-importtegel** de optie **Mijn gegevens verrijken**.

   > [!div class="mx-imgBorder"]
   > ![Aangepaste SFTP-import-tegel](media/SFTP_Custom_Import_tile.png "Aangepaste SFTP-import-tegel")

1. Selecteer **Aan de slag** en geef de referenties en het adres voor de SFTP-server op. Bijvoorbeeld sftp://mysftpserver.com:22.

1. Voer de naam in van het bestand dat de gegevens bevat en het pad naar het bestand op de SFTP-server als het niet in de hoofdmap staat.

1. Bevestig alle invoer door **Verbinden met aangepaste import** te selecteren.

   > [!div class="mx-imgBorder"]
   > ![Flyout aangepaste SFTP-importconfiguratie](media/SFTP_Custom_Import_Configuration_flyout.png "Flyout aangepaste SFTP-importconfiguratie")

## <a name="defining-field-mappings"></a>Veldtoewijzingen definiëren 

De directory die het bestand bevat dat op de SFTP-server moet worden geïmporteerd, moet ook een *model.json*-bestand bevatten. Dit bestand definieert het schema dat moet worden gebruikt voor het importeren van de gegevens. Het schema moet [het Common Data Model](/common-data-model/) gebruiken om de veldtoewijzing op te geven. Een eenvoudig voorbeeld van een model.json-bestand ziet er als volgt uit:

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

## <a name="enrichment-results"></a>Verrijkingsresultaten

Selecteer **Uitvoeren** vanaf de opdrachtbalk om het verrijkingsproces te starten. U kunt de verrijking ook automatisch laten uitvoeren als onderdeel van een [geplande vernieuwing](system.md#schedule-tab). De verwerkingstijd is afhankelijk van de grootte van de te importeren gegevens en de verbinding met de SFTP-server.

Nadat het verrijkingsproces is voltooid, kunt u uw net geïmporteerde aangepaste verrijkingsgegevens bekijken onder **Mijn verrijkingen**. Ook vindt u daar het tijdstip van de laatste update en het aantal verrijkte profielen.

U kunt een gedetailleerd overzicht van elk verrijkt profiel openen door **Verrijkte gegevens weergeven** te selecteren.

## <a name="next-steps"></a>Volgende stappen

Bouw voort op uw verrijkte klantgegevens. Maak [segmenten](segments.md), [metingen](measures.md) en [exporteer de gegevens](export-destinations.md) om uw klanten gepersonaliseerde ervaringen te bieden.




[!INCLUDE[footer-include](../includes/footer-banner.md)]