---
title: Gedeeltelijke gegevens voltooien met behulp van voorspellingen
description: Gebruik voorspellingen om onvolledige klantgegevens in te vullen.
ms.date: 11/01/2021
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-predictions
- ci-custom-models
- customerInsights
ms.openlocfilehash: e2cace3547a0b584dbf26ae5eecf86f3b256649f
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740713"
---
# <a name="complete-your-partial-data-with-predictions-deprecated"></a>Uw gedeeltelijke gegevens aanvullen met voorspellingen (afgeschaft)

> [!IMPORTANT]
> Deze functie wordt op **5 november 2021** **afgeschaft**. Huidige implementaties blijven werken totdat de functie wordt verwijderd, maar u kunt geen nieuwe integraties maken met behulp van de onderstaande instructies.

Met Voorspellingen kunt u eenvoudig voorspelde waarden maken die uw begrip van een klant kunnen verbeteren. Op de pagina **Intelligentie** > **Voorspellingen** kunt u **Mijn voorspellingen** selecteren om voorspellingen te zien die u in andere delen van Customer Insights hebt geconfigureerd en kunt u deze verder aanpassen.

> [!NOTE]
> U kunt deze functie niet gebruiken als uw omgeving Azure Data Lake Gen 2-opslag gebruikt.
>
> De voorspellingsfunctie maakt gebruik van geautomatiseerde middelen om gegevens te evalueren en voorspellingen te doen op basis van die gegevens, en heeft daarom de mogelijkheid om te worden gebruikt als methode voor profilering, zoals die term wordt gedefinieerd door de Algemene verordening gegevensbescherming ("AVG"). Op het gebruik door de klant van deze functie om gegevens te verwerken, zijn mogelijk de AVG of andere wetten of voorschriften van toepassing. U bent ervoor verantwoordelijk dat uw gebruik van Dynamics 365 Customer Insights, inclusief voorspellingen, voldoet aan alle toepasselijke wet- en regelgeving, inclusief wetten met betrekking tot privacy, persoonsgegevens, biometrische gegevens, gegevensbescherming en vertrouwelijkheid van communicatie.

## <a name="prerequisites"></a>Vereisten

Voordat uw organisatie de voorspellingsfunctie kan gebruiken, moet u ervoor zorgen dat aan de volgende voorwaarden is voldaan:

1. Uw organisatie heeft een exemplaar [ingesteld in Microsoft Dataverse](/ai-builder/build-model#prerequisites) en het bevindt zich in dezelfde organisatie als Customer Insights.

2. Uw Customer Insights-omgeving is gekoppeld aan uw exemplaar van Dataverse.

Zie [Een nieuwe omgeving maken](create-environment.md) voor meer informatie.

## <a name="create-a-prediction-in-the-customer-entity"></a>Een voorspelling maken in de entiteit Klant

1. Ga naar **Gegevens** > **Entiteiten**.

2. Selecteer de entiteit **Klant**.

3. Selecteer in de entiteit **Klant: CustomerInsights** op het tabblad **Velden**.

4. Zoek de kenmerknaam waarvoor u waarden wilt voorspellen en selecteer vervolgens het pictogram **Overzicht** in de kolom **Samenvatting**.
   > [!div class="mx-imgBorder"]
   > ![Overzichtspictogram.](media/intelligence-overviewicon.png "Overzichtspictogram")

5. Als er veel waarden ontbreken voor uw kenmerk, selecteert u **Ontbrekende waarden voorspellen** om door te gaan met uw voorspelling.
   > [!div class="mx-imgBorder"]
   > ![Overzichtsstatus met knop Ontbrekende waarden voorspellen weergegeven.](media/intelligence-overviewpredictmissingvalues.png "Overzichtsstatus met knop Ontbrekende waarden voorspellen weergegeven")

6. Geef een **weergavenaam** en een **naam van de uitvoerentiteit** op voor de resultaten van de voorspelling.

7. Een vooraf ingevulde lijst met opties laat zien waar u de waarden kunt toewijzen aan een voorspelde categorie. In dit geval zullen uw enige categorieopties 0 of 1 zijn, omdat deze verwijzen naar de waar/onwaar of binaire aard van de voorspelling. Wijs in de kolom Categorie de veldwaarden die u als '0' wilt classificeren in de uiteindelijke voorspelling toe aan "0" in de kolom Categorie en de items die u als "1" wilt classificeren in de uiteindelijke voorspelling aan "1".
   > [!div class="mx-imgBorder"]
   > ![Voorbeeld van toegewezen veldwaarden aan categorieën.](media/intelligence-categorymapping.png "Voorbeeld van toegewezen veldwaarden aan categorieën")

8. Selecteer **Gereed**. De voorspelling wordt nu verwerkt. De verwerking duurt enige tijd, afhankelijk van de grootte en complexiteit van gegevens. De resultaten zijn beschikbaar in een nieuwe entiteit op basis van de **naam van de uitvoerentiteit** van de voorspelling die u hebt gemaakt.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="create-a-prediction-while-creating-a-segment"></a>Een voorspelling maken terwijl u een segment maakt

Het voorspellen van ontbrekende waarden voor een specifiek kenmerk naar keuze is ook mogelijk bij het maken van een segment. In het bijzonder wanneer u snel een segment maakt op basis van uw geharmoniseerde entiteit Klant en entiteit Meetcriterium voor klant.

Als onderdeel van deze stroom kiest u een specifiek kenmerk om uw segment op te baseren, zoals Klanttevredenheid, Aankoopbedrag of een ander kenmerk van uw keuze. Bij het maken van segmenten zal het systeem een methode voorstellen voor het voorspellen van ontbrekende waarden voor dit kenmerk.

1. Ga naar **Segmenten** en selecteer de tegel **Profielen**.

2. Kies een **veld** om een segment te maken en selecteer een **operator** en selecteer vervolgens **Evalueren**.

3. Geef een **naam** en een **weergavenaam** op voor het segment.

4. Selecteer **Opslaan**.

5. Als het gemaakte segment onvolledige gegevens in het bronveld bevat, kunt u ervoor kiezen om de ontbrekende waarden te voorspellen.
   > [!div class="mx-imgBorder"]
   > ![Voorspellingsknop.](media/segments-predictoption.png "Voorspellingsknop")

6. Geef een **weergavenaam** en een **naam van de uitvoerentiteit** op voor de resultaten van de voorspelling.

7. Selecteer **Gereed**. Uw voorspelling wordt binnenkort gegenereerd in een nieuwe entiteit met de naam die u hebt opgegeven bij **Naam van uitvoerentiteit**.

## <a name="view-a-prediction"></a>Een voorspelling weergeven

1. Ga naar **Informatie** > **Voorspellingen** > **Mijn voorspellingen**.

2. Selecteer de voorspelling die u wilt beoordelen.

3. Selecteer de drie puntjes in de kolom **Acties** en kies **Weergeven**.

4. U ziet een aantal gegevenspunten in de weergave van uw voorspelling.
   > [!div class="mx-imgBorder"]
   > ![Voorspellingspagina.](media/intelligence-predictionsviewpage.png "Voorspellingspagina")

   - **Voorspelde waarden** toont de toewijzing die u tijdens de fase Toewijzing van veldwaarde aan categorie hebt gemaakt. Dit zijn de waarden in uw gegevensset weergegeven die zijn toegewezen aan een specifieke categorie.
   -**Meest populaire beïnvloeders** zijn de factoren in uw gegevensset die waarschijnlijk van invloed zijn op het vertrouwen van de voorspelling van uw veldwaarde die wordt toegewezen aan een specifieke categorie.
   - **Prestatie** geeft aan hoe de voorspellingen het doen. Selecteer de koppeling voor meer informatie.
   - **Voorbeeld** toont voorbeelden van de uitgevoerde gegevensset voor uw voorspelling en de waarschijnlijkheid van, of ons vertrouwen in, de voorspelde waarde, waarbij 0 onzeker is en 1 zeker is.

## <a name="update-a-prediction"></a>Een voorspelling bijwerken

1. Ga naar **Informatie** > **Voorspellingen** > **Mijn voorspellingen**.

2. Selecteer de voorspelling die u wilt bijwerken en selecteer het pictogram **Bijwerken**.

3. De voorspelling wordt gepland voor verwerking. U kunt de tijd zien waarop deze voor het laatst is bijgewerkt in de kolom **Bijgewerkt** van de pagina **Voorspellingen**.

## <a name="edit-a-prediction"></a>Een voorspelling bewerken

Nadat u een voorspelling hebt gemaakt, kunt u het model aanpassen in de AI Builder om de effectiviteit van uw model te vergroten.  

1. Ga naar **Informatie** > **Voorspellingen** > **Mijn voorspellingen**.

2. Selecteer de voorspelling die u wilt bewerken.

3. Selecteer de drie puntjes in de kolom **Acties** en kies **Weergeven**.

4. Selecteer **Aanpassen in AI Builder**.

5. Werk uw model bij in de AI Builder. [Meer informatie over het beheren van modellen in de AI Builder](/ai-builder/manage-model#retrain-and-republish-existing-models).

Bij de volgende uitvoering van uw voorspelling wordt het bijgewerkte model gebruikt dat u hebt gemaakt.

> [!NOTE]
> Nieuwe modellen gemaakt in AI Builder worden niet weergegeven in Customer Insights, tenzij het model is gemaakt op basis van de hierboven genoemde ervaringen.

## <a name="remove-a-prediction"></a>Een voorspelling verwijderen

1. Ga naar **Informatie** > **Voorspellingen** > **Mijn voorspellingen**.

2. Selecteer de voorspelling die u wilt verwijderen.

3. Selecteer de drie puntjes in de kolom **Acties** en kies **Verwijderen**.

4. Bevestig de verwijdering.

## <a name="troubleshooting"></a>Problemen oplossen

Als u het proces voor het bijvoegen van Dataverse niet kunt voltooien als gevolg van een fout, kunt u proberen het proces handmatig te voltooien. Er zijn twee bekende problemen die kunnen optreden tijdens het bijvoegen:

- De invoegtoepassingoplossing Klantenkaart is niet geïnstalleerd.
    1. Voer de instructies uit voor [het installeren en configureren van de oplossing](customer-card-add-in.md).

- App-machtigingen worden niet verleend.
    1. Ga naar [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).
    1. Selecteer **Omgevingen**.
    1. Selecteer het beletselteken naast de omgeving waaraan u de toestemming wilt toevoegen en selecteer **Instellingen**.
    1. Vouw **Gebruikers + machtigingen** uit en selecteer **Gebruikers**.
    1. Selecteer **+ Nieuw** en selecteer **Gebruiker**.
    1. Selecteer **Toepassingsgebruiker** als dit nog niet is geselecteerd en voer de volgende informatie in:
        - **Gebruikersnaam:** cihelp@microsoft.com
        - **Toepassings-id:** 38c77d00-5fcb-4cce-9d93-af4738258e3c
        - **Voornaam:** Customer
        - **Achternaam:** Insights
        - **Primair e-mailadres:** cihelp@microsoft.com
    1. Kies **Opslaan en sluiten**.
    1. Selecteer de gebruiker die u zojuist hebt gemaakt.
    1. Selecteer **Rollen beheren** in de bovenste menubalk.
    1. Selecteer **Systeembeheerder** en selecteer vervolgens **OK**.


[!INCLUDE [footer-include](includes/footer-banner.md)]
