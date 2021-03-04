---
title: Exportbestemmingen
description: Gegevens exporteren en exportbestemmingen beheren.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 63caa2ebdd7d637d14ac9c9cc7972095803aee2f
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477127"
---
# <a name="export-destinations-preview-overview"></a>Overzicht exportbestemmingen (preview)

De pagina **Exportbestemmingen** bevat alle locaties die u hebt ingesteld om gegevens naar te exporteren. U kunt ook nieuwe bestemmingen toevoegen voor export. Hierin worden verder de momenteel beschikbare exportopties weergegeven. Krijg een snel overzicht, een beschrijving en ontdek wat u kunt doen met elke uitbreidingsoptie. Exporteer uniforme profielen, meetwaarden en segmenten naar ondersteunde apps die relevant zijn voor uw bedrijf.

Ga naar **Beheer** > **Exportbestemmingen** om de volgende uitbreidingsopties te vinden:

- [Invoegtoepassing Dynamics 365-klantkaart](customer-card-add-in.md)
- [Facebook Ads Manager-connector](export-facebook.md)
- [Power Automate-connector](export-power-automate.md)
- [Power Apps-connector](export-power-apps.md)
- [Power BI-connector](export-power-bi.md)
- [Autopilot](export-autopilot.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Azure Blob-opslag](export-azure-blob-storage.md)
- [Azure Data Lake Storage Gen2](export-azure-data-lake-storage-gen2.md)
- [SendGrid](export-sendgrid.md)
- [LiveRamp&reg;-connector](export-liveramp.md)
- [Bot voor Microsoft Teams](export-teams-bot.md)
- [Mailchimp](export-mailchimp.md)
- [Customer Insights-API](apis.md)

## <a name="add-a-new-export-destination"></a>Een nieuwe exportbestemming toevoegen

Om exportbestemmingen toe te voegen, hebt u [Beheerdersmachtigingen](permissions.md) nodig. Als u exporteert naar Microsoft-services, gaan we ervan uit dat beide services zich in dezelfde organisatie bevinden.

1. Ga naar **Beheer** > **Exportbestemmingen**.

1. Schakel over naar het tabblad **Mijn exportbestemmingen**.

1. Selecteer **Bestemming toevoegen** om een nieuwe exportbestemming te maken.

1. Selecteer in het deelvenster **Bestemming toevoegen** het **Type** exportbestemming in de vervolgkeuzelijst.

1. Geef de vereiste details op en selecteer **Volgende** om de exportbestemming te maken.

U kunt ook **Instellen** selecteren op een tegel op het tabblad **Ontdekken**.

## <a name="view-export-destinations"></a>Exportbestemmingen weergeven

Nadat u exportbestemmingen hebt gemaakt, vindt u deze in een tabel op het tabblad **Mijn exportbestemmingen**. Deze tabel heeft drie kolommen:

- **Weergavenaam**: de naam die u hebt ingevoerd bij het maken van de bestemming.
- **Type**: het type exportbestemming dat u hebt ingesteld bij het maken van de bestemming.
- **Gemaakt**: de datum waarop de bestemming is gemaakt.

## <a name="edit-an-export-destination"></a>Een exportbestemming bewerken

1. Selecteer het verticale weglatingsteken voor de exportbestemming die u wilt bewerken.

   > [!div class="mx-imgBorder"]
   > ![Verticaal weglatingsteken](media/export-destinations-page-ellipsis.png "Verticaal weglatingsteken")

1. Selecteer **Bewerken** in de vervolgkeuzelijst.

1. Wijzig de waarden die moeten worden bijgewerkt en selecteer **Opslaan**.

## <a name="export-data-on-demand"></a>Gegevens op aanvraag exporteren

Na het configureren van een connector voor een exportbestemming, worden exports uitgevoerd bij elke [geplande vernieuwing](system.md#schedule-tab).

Als u gegevens wilt exporteren zonder te wachten op een geplande vernieuwing, gaat u naar het tabblad **Mijn exportbestemmingen** onder **Beheer** > **Exportbestemmingen**.

> [!div class="mx-imgBorder"]
> ![Verticaal weglatingsteken](media/export-destinations-page-ellipsis.png "Verticaal weglatingsteken")

- Selecteer **Exporteren** boven de lijst om de export uit te voeren naar alle exportbestemmingen tegelijk.
- Selecteer het beletselteken (...) na een lijstitem en kies vervolgens de optie **Exporteren** om de export uit te voeren voor een enkele exportbestemming.

## <a name="remove-an-export-destination"></a>Exportbestemming verwijderen

Als u een exportbestemming wilt verwijderen, begint u op de pagina **Exportbestemmingen**.

1. Selecteer het verticale weglatingsteken voor de exportbestemming die u wilt verwijderen.

   > [!div class="mx-imgBorder"]
   > ![Verticaal weglatingsteken](media/export-destinations-page-ellipsis.png "Verticaal weglatingsteken")

2. Selecteer **Verwijderen** in het vervolgkeuzemenu.

3. Bevestig de verwijdering door **Verwijderen** te selecteren op het bevestigingsscherm.


[!INCLUDE[footer-include](../includes/footer-banner.md)]