---
title: Overzicht van voorspellingen
description: Voorspellingsscenario's en opties die worden gedekt door de Dynamics 365 Customer Insights-toepassing.
ms.date: 09/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f8c61d7530126890d26ce482a27a0f97a39e836c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610184"
---
# <a name="predictions-overview"></a>Overzicht van voorspellingen

Dynamics 365 Customer Insights wordt geleverd met een verscheidenheid aan opties die gebruikmaken van AI en Machine Learning om gegevens te voorspellen.

## <a name="out-of-box-models"></a>Kant-en-klare modellen

De eenvoudigste manier om te beginnen met het voorspellen van gegevens zijn vooraf gedefinieerde modellen, vaak kant-en-klare modellen genoemd. Deze hebben alleen bepaalde gegevens en structuur nodig om snel inzichten te genereren. De volgende modellen zijn beschikbaar:

# <a name="individual-consumers-b-to-c"></a>[Individuele consumenten (B-to-C)](#tab/b2c)

- [Levensduurwaarde van klant](predict-customer-lifetime-value.md): voorspelt de potentiële omzet van een klant gedurende de gehele interactie met een bedrijf.
- [Productaanbeveling](predict-product-recommendation.md): stelt sets met voorspellende productaanbevelingen voor op basis van aankoopgedrag en klanten met vergelijkbare aankooppatronen.
- [Verloop van abonnement](predict-subscription-churn.md): voorspelt of het risico bestaat dat een klant niet langer gebruik zal maken van de abonnementsproducten of -services van uw bedrijf.
- [Transactioneel verloop](predict-transactional-churn.md) : voorspelt of een individuele klant niet langer uw producten of services zal kopen in een bepaald tijdsbestek.
- [Gevoelsanalyse](sentiment-analysis.md): analyseert het gevoel van klantfeedback en identificeert bedrijfsaspecten die vaak worden genoemd.

# <a name="business-accounts-b-to-b"></a>[Zakelijke accounts (B-to-B)](#tab/b2b)

- [Transactioneel verloop](predict-transactional-churn.md) : voorspelt of een klantaccount niet langer uw producten of services zal kopen in een bepaald tijdsbestek.

---

> [!TIP]
> We raden u aan om kant-en-klare modellen regelmatig te vernieuwen met bijgewerkte gegevens om ervoor te zorgen dat ze uw zakelijke gebruiksscenario nauwkeurig van informatie voorzien. Gegevens worden ad hoc vernieuwd wanneer het systeem nieuwe of bijgewerkte gegevensbronnen opneemt. Modellen zullen echter alleen in dit geval opnieuw een score bepalen en de bestaande trainingsgegevens blijven gebruiken.
>
> Configureer een **updateschema** door het schema voor hertraining voor het model in te stellen tijdens de configuratie. Het model wordt opnieuw getraind en bepaalt opnieuw een score volgens dit schema, dat u op elk moment kunt wijzigen.

## <a name="azure-machine-learning-integration"></a>Azure Machine Learning-integratie

Als een organisatie al gebruikmaakt van Machine Learning-scenario's op basis van Azure Machine Learning-experimenten, helpt de functie voor aangepaste modellen in Customer Insights om de stippen met elkaar te verbinden. Maak werkstromen die u helpen bij het kiezen van de gegevens waaruit u inzichten wilt genereren en koppel de resultaten aan uw geharmoniseerde klantprofielen. Zie [Aangepaste Machine Learning-modellen](custom-models.md) voor meer informatie.

## <a name="manage-existing-predictions"></a>Bestaande voorspellingen beheren

Ga naar de pagina **Intelligentie** > **Voorspellingen**. Bekijk op het tabblad **Mijn voorspellingen** de voorspellingen die u hebt gemaakt, hun voorspellingstype, de naam van de uitvoerentiteit, de status, de laatste keer dat de voorspelling is bewerkt en de laatste keer dat de gegevens zijn vernieuwd. U kunt de lijst met voorspellingen op elke gewenste kolom sorteren.

Selecteer een voorspelling om beschikbare acties te bekijken.

:::image type="content" source="media/predictions.png" alt-text="Pagina Mijn voorspellingen.":::

- **Bewerken** de voorspelling om de eigenschappen te wijzigen.
- [**Vernieuw**](#refresh-a-prediction) de voorspelling om de meest recente gegevens op te nemen.
- **Bekijk** de voorspellingsdetails.
- [**Bruikbaarheidsrapport voor gegevensinvoer**](#view-the-input-data-usability-report) om fouten, waarschuwingen en aanbevelingen te bekijken.
- **Verwijder** de voorspelling.

### <a name="refresh-a-prediction"></a>Een voorspelling vernieuwen

Voorspellingen kunnen automatisch worden vernieuwd of op aanvraag handmatig worden vernieuwd. Als u alle voorspellingen handmatig wilt vernieuwen, selecteert u **Alles vernieuwen**. Als u handmatig een voorspelling wilt vernieuwen, selecteert u deze en selecteert u vervolgens **Vernieuwen**. Om [een automatische vernieuwing te plannen](schedule-refresh.md), gaat u naar **Beheerder** > **Systeem** > **Planning**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

### <a name="view-the-input-data-usability-report"></a>Het bruikbaarheidsrapport voor gegevensinvoer bekijken

Het bruikbaarheidsrapport voor invoergegevens biedt een geconsolideerd overzicht van de fouten en waarschuwingen die uw kant-en-klare voorspellingen mogelijk genereren. Het geeft ook aanbevelingen om de prestaties van het model te verbeteren.

Het rapport is beschikbaar nadat een model zijn trainingsproces heeft voltooid. Het wordt voor elk model afzonderlijk gemaakt, ongeacht of dit met succes de training heeft voltooid of niet.

Selecteer op het tabblad **Mijn voorspellingen** de voorspelling en kies **Bruikbaarheidsrapport voor gegevensinvoer**. Of selecteer in de detailweergave voor de voorspelling de optie **Bruikbaarheidsrapport voor gegevensinvoer**.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Voorbeeld van een bruikbaarheidsrapport voor invoergegevens met een tabel met fouten, waarschuwingen en aanbevelingen.":::

Het rapport bevat:

- **Naam**: beschrijvende naam van de fout, waarschuwing of aanbeveling.
- **Stap**: modelfase, trainen of scoren, waarnaar de informatie verwijst.
- **Status**: ernst van de informatie (fout, waarschuwing, aanbeveling).
- **Kolomnaam**: kolom in een entiteit die moet worden gewijzigd om de modelprestaties te verbeteren.
- **Entiteitsnaam**: naam van de entiteit die moet worden gewijzigd om de modelprestaties te verbeteren.
- **Details**: details van de fout, waarschuwing of aanbeveling.

[!INCLUDE [footer-include](includes/footer-banner.md)]
