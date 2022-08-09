---
title: Klantprofielen verrijken met aangepast importeren via SFTP (preview)
description: Algemene informatie over de aangepaste SFTP-importverrijking.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 81ef6c62240e26cb5c9475e6306e08edc7e5eb31
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195790"
---
# <a name="enrich-customer-profiles-with-sftp-custom-import-preview"></a>Klantprofielen verrijken met aangepast importeren via SFTP (preview)

Dankzij de aangepaste import van Secure File Transfer Protocol (SFTP) kunt u gegevens importeren die niet door het proces van gegevensharmonisatie hoeven te gaan. Het is een flexibele, veilige en gemakkelijke manier om uw gegevens binnen te halen. Aangepaste SFTP-import kan worden gebruikt in combinatie met [SFTP-export](export-sftp.md), waarmee u de klantprofielgegevens kunt exporteren die nodig zijn voor verrijking. De gegevens kunnen vervolgens worden verwerkt en verrijkt en aangepast importeren via SFTP kan worden gebruikt om de verrijkte gegevens terug te brengen naar Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Vereisten

- Bestandsnaam en locatie (pad) van het te importeren bestand op de SFTP-host is bekend.

- Een *model.json*-bestand dat het Common Data Model-schema specificeert voor de te importeren gegevens is beschikbaar. Dit bestand moet in dezelfde map staan als het te importeren bestand.

- Een SFTP-[verbinding](connections.md) is [geconfigureerd](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>Voorbeeld van bestandsschema

De directory die het bestand bevat dat op de SFTP-server moet worden geïmporteerd, moet ook een *model.json*-bestand bevatten. Dit bestand definieert het schema dat moet worden gebruikt voor het importeren van de gegevens. Het schema moet [Common Data Model](/common-data-model/) gebruiken om de veldtoewijzing te specificeren. Een eenvoudig voorbeeld van een model.json-bestand ziet er als volgt uit:

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
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
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

## <a name="configure-the-connection-for-sftp-custom-import"></a>De verbinding voor aangepaste SFTP-import configureren

U moet een [beheerder](permissions.md#admin) in Customer Insights zijn en de gebruikersreferenties, URL en poortnummer hebben voor de SFTP-locatie waarvandaan u gegevens wilt importeren.

1. Selecteer **Verbinding toevoegen** bij het configureren van een verrijking of ga naar **Beheer** > **Verbindingen** en selecteer **Instellen** op de tegel Aangepaste import.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Configuratiepagina voor aangepaste importverbinding.":::

1. Geef een naam op voor de verbinding.

1. Voer een geldige gebruikersnaam, wachtwoord en host-URL in voor de SFTP-server waarop de te importeren gegevens zich bevinden.

1. Bekijk en geef uw toestemming voor [Gegevensprivacy en naleving](#data-privacy-and-compliance) door **Ik ga akkoord** te selecteren.

1. Selecteer **Verifiëren** om de configuratie te valideren en selecteer **Opslaan**.

### <a name="data-privacy-and-compliance"></a>Gegevensprivacy en naleving

Wanneer u Dynamics 365 Customer Insights instelt om gegevens met Aangepaste import te verzenden, staat u overdracht van gegevens toe buiten de nalevingsgrens voor Dynamics 365 Customer Insights, waaronder mogelijk gevoelige gegevens, zoals persoonsgegevens. Microsoft zal dergelijke gegevens in uw opdracht overdragen, maar het is uw verantwoordelijkheid ervoor te zorgen dat de gegevens voldoen aan eventuele privacy- of beveiligingsverplichtingen die u hebt. Zie [Microsoft Dynamics CRM Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=396732) voor meer informatie.
Uw Dynamics 365 Customer Insights-beheerder kan deze verrijking op elk moment verwijderen om het gebruik van deze functionaliteit te stoppen.

## <a name="configure-the-import"></a>De import configureren

1. Ga naar **Gegevens** > **Verrijking** en selecteer het tabblad **Detecteren**.

1. Selecteer **Mijn gegevens verrijken** op de tegel **Aangepaste import via SFTP**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Tegel Aangepaste SFTP-import.":::

1. Bekijk het overzicht en selecteer **Volgende**.

1. Selecteer de verbinding. Neem contact op met een beheerder als er geen verbinding beschikbaar is.

1. Selecteer de **Klantgegevensset** en kies het profiel of segment dat u wilt verrijken. De entiteit *Klant* verrijkt al uw klantprofielen, terwijl een segment alleen klantprofielen in dat segment verrijkt.

1. Selecteer **Volgende**.

1. Voer het **Pad** en de **Bestandsnaam** in van het gegevensbestand dat u wilt importeren.

1. Selecteer **Volgende**.

1. Geef een **Naam** op voor de verrijking en de **Naam van uitvoerentiteit**.

1. Selecteer **Verrijking opslaan** na het bekijken van uw keuzes.

1. Selecteer **Uitvoeren** om het verrijkingsproces te starten of sluit om terug te keren naar de pagina **Verrijkingen**.

## <a name="view-enrichment-results"></a>Verrijkingsresultaten bekijken

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Volgende stappen

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
