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
ms.openlocfilehash: b67aa7477033222b0bc9512a962a1580edd973b4882ce925620ff5ec14f83fe3
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032706"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Klantprofielen verrijken met aangepaste gegevens (preview)

Dankzij de aangepaste import van Secure File Transfer Protocol (SFTP) kunt u gegevens importeren die niet door het proces van gegevensharmonisatie hoeven te gaan. Het is een flexibele, veilige en gemakkelijke manier om uw gegevens binnen te halen. Aangepaste SFTP-import kan worden gebruikt in combinatie met [SFTP-export](export-sftp.md), waarmee u de klantprofielgegevens kunt exporteren die nodig zijn voor verrijking. De gegevens kunnen vervolgens worden verwerkt en verrijkt, en aangepaste SFTP-import kan worden gebruikt om de verrijkte gegevens terug te brengen naar de doelgroepinzichten van Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Vereisten

Om aangepaste SFTP-import te configureren, moet aan de volgende voorwaarden worden voldaan:

- U hebt de bestandsnaam en locatie (pad) van het bestand dat moet worden geïmporteerd op de SFTP-host.
- Er is een bestand *model.json* dat [het Common Data Model-schema](/common-data-model/) specificeert voor de te importeren gegevens. Dit bestand moet in dezelfde map staan als het te importeren bestand.
- Er is al een SFTP-verbinding geconfigureerd door een beheerder *of* u hebt [beheerdersmachtigingen](permissions.md#administrator). U hebt de gebruikersgegevens, de URL en het poortnummer nodig voor de SFTP-locatie waaruit u gegevens wilt importeren.


## <a name="configure-the-import"></a>De import configureren

1. Ga naar **Gegevens** > **Verrijking** en selecteer het tabblad **Detecteren**.

1. Selecteer op de tegel **Aangepaste SFTP-import** de optie **Mijn gegevens verrijken** en selecteer vervolgens **Aan de slag**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Tegel Aangepaste SFTP-import.":::

1. Selecteer een [verbinding](connections.md) in de vervolgkeuzelijst. Neem contact op met een beheerder als er geen verbinding beschikbaar is. Als u een beheerder bent, kunt u een verbinding maken door **Verbinding toevoegen** te selecteren en **Aangepaste SFTP-import** te kiezen in de vervolgkeuzelijst.

1. Selecteer **Verbinding maken met aangepaste import** om de geselecteerde verbinding te bevestigen.

1.  Selecteer **Volgende** en voer het **Pad** en de **Bestandsnaam** in van het gegevensbestand dat u wilt importeren.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Schermopname bij invoeren van gegevenslocatie.":::

1. Selecteer **Volgende** en geef een naam op voor de verrijking en een naam voor de uitvoerentiteit. 

1. Selecteer **Verrijking opslaan** na het bekijken van uw keuzes.

## <a name="configure-the-connection-for-sftp-custom-import"></a>De verbinding voor aangepaste SFTP-import configureren 

U moet een beheerder zijn om verbindingen te kunnen configureren. Selecteer **Verbinding toevoegen** bij het configureren van een verrijking *of* ga naar **Beheerder** > **Verbindingen** en selecteer **Instellen** op de tegel Aangepaste import.

1. Voer een naam in voor de verbinding in het vak **Weergavenaam**.

1. Voer een geldige gebruikersnaam, wachtwoord en host-URL in voor de SFTP-server waarop de te importeren gegevens zich bevinden.

1. Bekijk en geef toestemming voor **Gegevensprivacy en naleving** door het selectievakje **Ik ga akkoord** in te schakelen.

1. Selecteer **Verifiëren** om de configuratie te valideren.

1. Nadat de verificatie is voltooid, kan de verbinding worden opgeslagen door **Opslaan** te selecteren.

   > [!div class="mx-imgBorder"]
   > ![Experian-verbindingsconfiguratiepagina.](media/enrichment-SFTP-connection.png "Experian-verbindingsconfiguratiepagina")


## <a name="defining-field-mappings"></a>Veldtoewijzingen definiëren 

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

Bouw voort op uw verrijkte klantgegevens. Maak [segmenten](segments.md) en [meetcriteria](measures.md), en [exporteer de gegevens](export-destinations.md) om gepersonaliseerde ervaringen aan uw klanten te leveren.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
