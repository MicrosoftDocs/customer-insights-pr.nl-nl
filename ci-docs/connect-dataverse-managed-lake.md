---
title: Verbinding maken met gegevens in een beheerd Microsoft Dataverse data lake
description: Gegevens importeren uit een door Microsoft Dataverse beheerd data lake.
ms.date: 08/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 0d9612525344c8ac99b6e3edfe33a426dc0a474b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609789"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Verbinding maken met gegevens in een beheerd Microsoft Dataverse data lake

Microsoft Dataverse-gebruikers kunnen snel verbinding maken met analytische entiteiten in een door Microsoft Dataverse beheerde lake. Slechts één gegevensbron van een omgeving kan tegelijkertijd dezelfde Dataverse beheerde lake gebruiken.

> [!NOTE]
> U moet een beheerder zijn in de Dataverse-organisatie om door te kunnen gaan en de lijst te kunnen bekijken van entiteiten die beschikbaar zijn in het beheerde lake.

## <a name="prerequisites"></a>Vereisten

- Gegevens die worden opgeslagen in online services, zoals Azure Data Lake Storage, kunnen worden opgeslagen op een andere locatie dan waar gegevens worden verwerkt of opgeslagen in Dynamics 365 Customer Insights. Door gegevens te importeren die zijn opgeslagen in online services, gaat u ermee akkoord dat gegevens kunnen worden overgedragen naar en opgeslagen met Dynamics 365 Customer Insights. [Meer informatie in het Microsoft Trust Centerr](https://www.microsoft.com/trust-center).

- Alleen Dataverse-entiteiten waarvoor [wijzigingen bijhouden](/power-platform/admin/enable-change-tracking-control-data-synchronization) is ingeschakeld zijn zichtbaar. Deze entiteiten kunnen worden geëxporteerd naar de door Dataverse beheerde data lake en gebruikt in Customer Insights. Standaard Dataverse-tabellen hebben standaard het bijhouden van wijzigingen ingeschakeld. U moet het bijhouden van wijzigingen inschakelen voor aangepaste tabellen. Als u wilt controleren of een Dataverse-tabel is ingeschakeld voor het bijhouden van wijzigingen, gaat u naar [Power Apps](https://make.powerapps.com) > **Gegevens** > **Tabellen**. Zoek de tabel waarin u bent geïnteresseerd en selecteer deze. Ga naar **Instellingen** > **Geavanceerde opties** en bekijk de instelling **Wijzigingen bijhouden**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Verbinding maken met een door Dataverse beheerd lake

1. Ga naar **Gegevens** > **Gegevensbronnen**.

1. Selecteer **Gegevensbron toevoegen**.

1. Selecteer **Microsoft Dataverse**.

1. Voer een **Naam** voor de gegevensbron en een optionele **Beschrijving** in.

1. Geef het **Serveradres** voor de Dataverse-organisatie op en selecteer **Aanmelden**.

1. Selecteer in de beschikbare lijst de tabellen die u als entiteiten in Customer Insights wilt opnemen.

   > [!NOTE]
   > Als er al tabellen zijn geselecteerd, worden deze mogelijk gebruikt door andere Dynamics 365-toepassingen (zoals Dynamics 365 Sales Insights of Customer Service Insights). U kunt de selectie niet wijzigen. Deze tabellen zijn als entiteiten beschikbaar zodra de gegevensbron is gemaakt.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dialoogvenster met een lijst entiteiten in de Dataverse-omgeving.":::

1. Sla uw selectie op om te beginnen met de synchronisatie van de geselecteerde tabellen van Dataverse. U vindt de nieuw toegevoegde verbinding op de pagina **Gegevensbronnen**. Deze wordt in de wachtrij geplaatst voor vernieuwing en toont het aantal entiteiten als 0, totdat alle geselecteerde tabellen gesynchroniseerd zijn.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Het laden van gegevens kan enige tijd vergen. Na een succesvolle vernieuwing kunnen de opgenomen gegevens worden bekeken vanaf de pagina [**Entiteiten**](entities.md).

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Een gegevensbron van een door Dataverse beheerde lake bewerken

U kunt de entiteitsselectie pas bewerken nadat u de gegevensbron hebt gemaakt. Als er bijvoorbeeld extra entiteiten zijn toegevoegd aan Dataverse en u ze ook wilt importeren.
Om verbinding te maken met een ander Dataverse-data lake, [moet u een nieuwe gegevensbron maken](#connect-to-a-dataverse-managed-lake).

1. Ga naar **Gegevens** > **Gegevensbronnen**.

1. Selecteer **Bewerken** naast de gegevensbron die u wilt bijwerken.

1. Selecteer extra entiteiten in de beschikbare lijst met entiteiten.

1. Klik op **Opslaan** om uw wijzigingen toe te passen en terug te keren naar de pagina **Gegevensbronnen**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupted-data"></a>Veelvoorkomende redenen voor opnamefouten of beschadigde gegevens

De volgende controles worden uitgevoerd op de opgenomen gegevens om beschadigde records te onthullen:

- De waarde van een veld komt niet overeen met het gegevenstype van de kolom.
- Velden bevatten tekens waardoor de kolommen niet overeenkomen met het verwachte schema. Bijvoorbeeld: onjuist opgemaakte aanhalingstekens, aanhalingstekens zonder escape of tekens voor nieuwe regels.
- Als er kolommen voor datetime/date/datetimeoffset zijn, moet hun indeling in het model worden gespecificeerd als niet de standaard ISO-indeling wordt gevolgd.

### <a name="schema-or-data-type-mismatch"></a>Schema of gegevenstype komt niet overeen

Als de gegevens niet voldoen aan het schema, worden de records geclassificeerd als beschadigd. Corrigeer de brongegevens of het schema en neem de gegevens opnieuw op.

### <a name="datetime-fields-in-the-wrong-format"></a>Datum- en tijdvelden hebben een onjuiste indeling

De datum- en tijdvelden in de entiteit hebben geen ISO- of en-US-indeling. De standaardindeling voor datum/tijd in Customer Insights is de en-US-indeling. Alle datum- en tijdvelden in een entiteit moeten dezelfde indeling hebben. Customer Insights ondersteunt andere indelingen, op voorwaarde dat annotaties of kenmerken worden gemaakt op bron- of entiteitsniveau in het model of manifest.json. Bijvoorbeeld: 

**Model.json**

   ```json
      "annotations": [
        {
          "name": "ci:CustomTimestampFormat",
          "value": "yyyy-MM-dd'T'HH:mm:ss:SSS"
        },
        {
          "name": "ci:CustomDateFormat",
          "value": "yyyy-MM-dd"
        }
      ]   
   ```

  In een manifest.json kan de datum-/tijdindeling worden opgegeven op entiteitsniveau of op kenmerkniveau. Gebruik op entiteitsniveau 'exhibitsTraits' in de entiteit in de *.manifest.cdm.json om de datum-/tijdindeling te definiëren. Gebruik op kenmerkniveau 'appliedTraits' in het kenmerk in entityname.cdm.json.

**Manifest.json op entiteitsniveau**

```json
"exhibitsTraits": [
    {
        "traitReference": "is.formatted.dateTime",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd'T'HH:mm:ss"
            }
        ]
    },
    {
        "traitReference": "is.formatted.date",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd"
            }
        ]
    }
]
```

**Entity.json op kenmerkniveau**

```json
   {
      "name": "PurchasedOn",
      "appliedTraits": [
        {
          "traitReference": "is.formatted.date",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-dd"
            }
          ]
        },
        {
          "traitReference": "is.formatted.dateTime",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-ddTHH:mm:ss"
            }
          ]
        }
      ],
      "attributeContext": "POSPurchases/attributeContext/POSPurchases/PurchasedOn",
      "dataFormat": "DateTime"
    }
```

[!INCLUDE [footer-include](includes/footer-banner.md)]
