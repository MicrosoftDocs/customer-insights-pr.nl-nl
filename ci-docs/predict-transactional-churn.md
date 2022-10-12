---
title: Voorspelling van transactieverloop (met video)
description: Voorspel of het risico bestaat dat een klant de producten of services van uw bedrijf niet meer zal kopen.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: fd8df0f0a168ddfab9e8ad3af9e1f1fc0bc1b7a2
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610506"
---
# <a name="predict-transaction-churn"></a>Transactieverloop voorspellen

Met deze functie kunt u voorspellen of een klant uw producten of services binnen een bepaald tijdsbestek niet meer zal kopen.

U moet over zakelijke kennis beschikken om te begrijpen wat verloop voor uw bedrijf betekent. We ondersteunen op tijd gebaseerde verloopdefinities, wat betekent dat een klant na een periode zonder aankopen wordt beschouwd als verlopen.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Voor omgevingen die zijn gebaseerd op zakelijke accounts, kunnen we het transactieverloop voor een account voorspellen en ook voor een combinatie van account en informatie van een ander niveau, zoals productcategorie. Door een dimensie toe te voegen, kunt u er bijvoorbeeld achter komen hoe waarschijnlijk het is dat het account 'Contoso' stopt met het kopen van de productcategorie 'kantoorbenodigdheden'. Daarnaast kunnen we voor zakelijke accounts ook AI gebruiken om een lijst met mogelijke redenen te genereren waarom een account waarschijnlijk verloop zal vertonen voor een categorie informatie van een secundair niveau.

> [!TIP]
> Probeer de voorspelling van transactieverloop uit met voorbeeldgegevens: [Voorbeeldgids voor voorspelling van transactieverloop](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Vereisten

- Minstens [Inzendermachtigingen](permissions.md).
- Minimaal 10 klantprofielen, bij voorkeur meer dan 1.000 unieke klanten.
- Klant-id. Dit is een unieke id om transacties aan uw klanten te koppelen.
- Transactiegegevens voor ten minste het dubbele van het geselecteerde tijdvenster, zoals twee tot drie jaar transactiegeschiedenis. Idealiter minimaal twee transacties per klant. De transactiegeschiedenis moet het volgende bevatten:
  - **Transactie-id**: unieke identificatie van een aankoop of transactie.
  - **Transactiedatum**: datum van de aankoop of de transactie.
  - **Waarde van de transactie**: valuta of numerieke waarde van de transactie.
  - **Unieke product-id**: id van het gekochte product of de gekochte service als uw gegevens zich op regelitemniveau bevinden.
  - **Of deze transactie een retour was**: een waar/onwaar-veld dat aangeeft of de transactie een retour was of niet. Als de **waarde van de transactie** negatief is, gaan we uit van een retour.
- Activiteitsgegevens van klant:
  - Klant-id. Dit is een unieke id om activiteiten toe te wijzen aan uw klanten.
  - **Primaire sleutel:** unieke id voor een activiteit. Bijvoorbeeld een websitebezoek of een gebruiksrecord waaruit blijkt dat de klant een monster van uw product heeft geprobeerd.
  - **Tijdstempel:** datum en tijd van de gebeurtenis die wordt geïdentificeerd door de primaire sleutel.
  - **Gebeurtenis:** naam van de gebeurtenis die u wilt gebruiken. Een veld met de naam 'UserAction' in een supermarkt kan bijvoorbeeld een kortingsbon zijn die door de klant wordt gebruikt.
  - **Details:** gedetailleerde informatie over de gebeurtenis. Een veld met de naam 'CouponValue' in een supermarkt kan bijvoorbeeld de valutawaarde van de kortingsbon zijn.
- Minder dan 20% ontbrekende waarden in het gegevensveld van de opgegeven entiteit

Voeg voor zakelijke accounts (B-to-B) klantgegevens toe die zijn afgestemd op meer statische kenmerken om ervoor te zorgen dat het model optimaal presteert:
- **Klant-id** unieke id voor een klant.
- **Aanmaakdatum:** datum waarop de klant voor het eerst is toegevoegd.
- **Staat of provincie:** staat of provincie van een klant.
- **Land:** land van een klant.
- **Branche:** branchetype van een klant. Een veld met de naam 'Branche' voor een koffiebrander kan bijvoorbeeld aangeven of de klant retail was.
- **Classificatie:** categorisering van een klant voor uw bedrijf. Een veld met de naam 'Waardesegment' voor een koffiebrander kan bijvoorbeeld het klantniveau aangeven op basis van de klantgrootte.

> [!NOTE]
> Voor een bedrijf met een hoge aankoopfrequentie van klanten (om de paar weken) wordt het aanbevolen om een korter voorspellingsvenster en verloopdefinitie te selecteren. Kies voor een lage aankoopfrequentie (om de paar maanden of eenmaal per jaar) een langer voorspellingsvenster en verloopdefinitie.

## <a name="create-a-transaction-churn-prediction"></a>Een voorspelling van transactieverloop maken

1. Ga naar **Informatie** > **Voorspellingen**.

1. Selecteer op het tabblad **Maken** de optie **Model gebruiken** op de tegel **Klantverloopmodel**.

1. Selecteer **Transactie** voor het type verloop en vervolgens **Aan de slag**.

1. **Geef dit model een naam** en de **Naam van uitvoerentiteit** om ze te onderscheiden van andere modellen of entiteiten.

1. Selecteer **Volgende**.

### <a name="define-customer-churn"></a>Klantverloop definiëren

Selecteer **Concept opslaan** op elk gewenst moment om de voorspelling als concept op te slaan. De conceptvoorspelling wordt weergegeven op het tabblad **Mijn voorspellingen**.

1. Stel het **Voorspellingsvenster** in. Voorspel bijvoorbeeld het verlooprisico voor uw klanten in de komende 90 dagen om deze op uw marketinginspanningen voor klantbehoud af te stemmen. Het voorspellen van het verlooprisico voor een langere of kortere periode kan het moeilijker maken om de factoren in uw verlooprisicoprofiel mee te nemen, maar het hangt af van uw specifieke zakelijke vereisten.

1. Voer het aantal dagen in om verloop te definiëren in het veld **Definitie van verloop**. Als een klant bijvoorbeeld in de afgelopen 30 dagen geen aankoop heeft gedaan, kan deze voor uw bedrijf als verlopen worden beschouwd.

1. Selecteer **Volgende**.

### <a name="add-purchase-history"></a>Aankoopgeschiedenis toevoegen

1. Selecteer **Gegevens toevoegen** bij **Transactiegeschiedenis van de klant**.

1. Selecteer het semantische activiteitstype, **SalesOrder** of **SalesOrderLine**, dat de vereiste transactiegeschiedenisgegevens bevat. Als de activiteit niet is ingesteld, selecteert u **hier** en maakt u deze.

1. Kies onder **Activiteiten**, als de activiteitskenmerken semantisch zijn toegewezen bij het maken van de activiteit, de specifieke kenmerken of entiteit waarop u de berekening wilt richten. Als er geen semantische toewijzing heeft plaatsgevonden, selecteert u **Bewerken** en wijst u uw gegevens toe.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Zijvenster met het kiezen van specifieke activiteiten onder het semantische type.":::

1. Selecteer **Volgende** en bekijk de kenmerken die vereist zijn voor dit model.

1. Selecteer **Save**.

1. Voeg meer activiteiten toe of selecteer **Volgende**.

# <a name="individual-consumers-b-to-c"></a>[Individuele consumenten (B-to-C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Aanvullende gegevens toevoegen (optioneel)

1. Selecteer **Gegevens toevoegen** voor **Klantactiviteiten**.

1. Selecteer het semantische activiteitstype dat de gegevens bevat die u wilt gebruiken. Als de activiteit niet is ingesteld, selecteert u **hier** en maakt u deze.

1. Kies onder **Activiteiten**, als de activiteitskenmerken semantisch zijn toegewezen bij het maken van de activiteit, de specifieke kenmerken of entiteit waarop u de berekening wilt richten. Als er geen semantische toewijzing heeft plaatsgevonden, selecteert u **Bewerken** en wijst u uw gegevens toe.

1. Selecteer **Volgende** en bekijk de kenmerken die vereist zijn voor dit model.

1. Selecteer **Save**.

1. Selecteer **Volgende**

# <a name="business-accounts-b-to-b"></a>[Zakelijke accounts (B-to-B)](#tab/b2b)

### <a name="select-prediction-level"></a>Voorspellingsniveau selecteren

De meeste voorspellingen worden op klantniveau gemaakt. In sommige situaties is dat misschien niet gedetailleerd genoeg om aan uw zakelijke behoeften te voldoen. Gebruik deze functie om het verloop voor een filiaal van een klant te voorspellen, in plaats van voor de klant als geheel.

1. Selecteer **Entiteit voor een secundair niveau selecteren**. Als de optie niet beschikbaar is, controleert u of u het vorige gedeelte hebt voltooid.

1. Vouw de entiteiten uit waarvan u het secundaire niveau wilt kiezen, of gebruik het zoekfiltervak om de geselecteerde opties te filteren.

1. Kies het kenmerk dat u als secundair niveau wilt gebruiken en selecteer vervolgens **Toevoegen**.

1. Selecteer **Volgende**.

> [!NOTE]
> De entiteiten die in deze sectie beschikbaar zijn, worden weergegeven omdat ze een relatie hebben met de entiteit die u in de vorige sectie hebt gekozen. Als u de entiteit niet ziet die u wilt toevoegen, zorg er dan voor dat deze een geldige relatie heeft in **Relaties**. Alleen één-op-één- en veel-op-één-relaties zijn geldig voor deze configuratie.

### <a name="add-additional-data-optional"></a>Aanvullende gegevens toevoegen (optioneel)

1. Selecteer **Gegevens toevoegen** voor **Klantactiviteiten**.

1. Selecteer het semantische activiteitstype dat de gegevens bevat die u wilt gebruiken. Als de activiteit niet is ingesteld, selecteert u **hier** en maakt u deze.

1. Kies onder **Activiteiten**, als de activiteitskenmerken semantisch zijn toegewezen bij het maken van de activiteit, de specifieke kenmerken of entiteit waarop u de berekening wilt richten. Als er geen semantische toewijzing heeft plaatsgevonden, selecteert u **Bewerken** en wijst u uw gegevens toe.

1. Selecteer **Volgende** en bekijk de kenmerken die vereist zijn voor dit model.

1. Selecteer **Save**.

1. Selecteer **Volgende**

1. Optioneel, selecteer **Gegevens toevoegen** voor **Klantengegevens**.

1. Wijs de semantische kenmerken toe aan velden in uw eigen klantgegevens zoals geïdentificeerd. De gegevens in de gebruikte velden mogen niet vaak veranderen om de beste prestaties van het model te garanderen. Als u bijvoorbeeld een veld selecteert voor 'Classificatie' dat elke maand verandert, wordt alleen de laatste waarde gebruikt in de voorspelling, hoewel historisch gezien dezelfde waarde mogelijk niet van toepassing is op de klant bij het bouwen van de voorspellingpatronen.

1. Selecteer **Volgende**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Een optionele lijst met benchmarkaccounts opgeven

Voeg een lijst toe met uw zakelijke klanten en accounts die u als benchmarks wilt gebruiken. De [details voor deze benchmark-accounts](#view-prediction-results) omvatten hun verloopscore en de kenmerken die het meeste invloed hadden op hun verloopvoorspelling.

1. Selecteer **+ Klanten toevoegen**.

1. Kies de klanten die als benchmark fungeren.

1. Selecteer **Volgende**.

---

### <a name="set-update-schedule"></a>Updateplanning instellen

1. Kies voor de stap **Gegevensupdates** een frequentie om uw model opnieuw te trainen. Deze instelling is belangrijk om de nauwkeurigheid van voorspellingen bij te werken wanneer nieuwe gegevens worden opgenomen in Customer Insights. De meeste bedrijven kunnen eenmaal per maand opnieuw trainen en krijgen een goede nauwkeurigheid voor hun voorspelling.

1. Selecteer **Volgende**.

### <a name="review-and-run-the-model-configuration"></a>De modelconfiguratie controleren en uitvoeren

De stap **Controleren en uitvoeren** toont een samenvatting van de configuratie en biedt een kans om wijzigingen aan te brengen voordat u de voorspelling maakt.

1. Selecteer **Bewerken** in een van de stappen om te controleren en eventuele wijzigingen aan te brengen.

1. Als u tevereden bent over uw selecties, selecteert u **Opslaan en uitvoeren** om te beginnen met het uitvoeren van het model. Selecteer **Gereed**. Het tabblad **Mijn voorspellingen** wordt weergegeven terwijl de voorspelling wordt gemaakt. Het proces kan enkele uren in beslag nemen, afhankelijk van de hoeveelheid gegevens die in de voorspelling is gebruikt.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Resultaten van voorspelling weergeven

1. Ga naar **Informatie** > **Voorspellingen**.

1. Selecteer op het tabblad **Mijn voorspellingen** de voorspelling die u wilt weergeven.

# <a name="individual-consumers-b-to-c"></a>[Individuele consumenten (B-to-C)](#tab/b2c)

Er zijn drie primaire gegevenssecties op de resultatenpagina:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

# <a name="business-accounts-b-to-b"></a>[Zakelijke accounts (B-to-B)](#tab/b2b)

Er zijn drie primaire gegevenssecties op de resultatenpagina:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

Een informatiepagina **Invloedrijke functieanalyse** bevat vier secties met gegevens:

- Selecteer in het rechterdeelvenster een item in **Topklanten** of **Benchmarkklanten**. Beide lijsten zijn gerangschikt op afnemende waarde van de verloopscore, of de score nu alleen voor de klant is of een gecombineerde score is voor klanten en een secundair niveau zoals productcategorie. Het item dat is geselecteerd, bepaalt de inhoud op deze pagina.

  - **Topklanten**: lijst van 10 klanten met het hoogste risico op klantverloop en het laagste risico op klantverloop op basis van hun klantverloopscore.
  - **Benchmarklanten**: lijst met maximaal 10 klanten die zijn geselecteerd bij het configureren van het model.

- **Verloopscore:** weergave van de verloopscore voor het geselecteerde item in het rechterdeelvenster.

- **Verdeling van verlooprisico:** weergave van verdeling van verlooprisico over klanten en het percentiel waarin de geselecteerde klant zich bevindt.

- **Belangrijke functies die het risico op verloop verhogen en verlagen:** geeft voor het geselecteerde item in het rechterdeelvenster de top vijf kenmerken weer die het verlooprisico hebben verhoogd en verlaagd. Toont de waarde van de feature voor dat item en de invloed ervan op de verloopscore voor elke invloedrijke functie. De gemiddelde waarde van elk kenmerk in de segmenten met een laag, gemiddeld en hoog klantverloop wordt ook weergegeven. Het helpt om de waarden van de belangrijkste invloedrijke functies voor het geselecteerde item beter te contextualiseren en te vergelijken met klantsegmenten met een laag, gemiddeld en hoog verloop.

  - Laag: accounts of combinaties van account en secundair niveau met een verloopscore tussen 0 en 0,33.
  - Gemiddeld: accounts of combinaties van accounts en secundaire niveaus met een verloopscore tussen 0,33 en 0,66.
  - Hoog: accounts of combinaties van accounts en secundaire niveaus met een verloopscore groter dan 0,66.

  Wanneer u klantverloop op accountniveau voorspelt, worden alle accounts in aanmerking genomen bij het afleiden van de gemiddelde kenmerkwaarden voor klantverloopsegmenten. Voor verloopvoorspellingen op secundair niveau voor elk account, hangt de afleiding van verloopsegmenten af van het secundair niveau van het item dat in het deelvenster is geselecteerd. Als een artikel bijvoorbeeld een secundair niveau van productcategorie (kantoorbenodigdheden) heeft, worden alleen de artikelen met kantoorbenodigdheden als productcategorie in aanmerking genomen bij het bepalen van de gemiddelde kenmerkwaarden voor verloopsegmenten. Deze logica wordt toegepast om te zorgen voor een eerlijke vergelijking van de kenmerkwaarden van het item met de gemiddelde waarden over de segmenten met laag, gemiddeld en hoog verloop.

  In sommige gevallen is de gemiddelde waarde van segmenten met laag, gemiddeld of hoog verloop leeg of niet beschikbaar omdat er geen items zijn die behoren tot de overeenkomstige verloopsegmenten op basis van de bovenstaande definitie.

  De interpretatie van waarden onder de kolommen Laag, Gemiddeld en Hoog is anders voor categorische kenmerken zoals land of bedrijfstak. Omdat het begrip gemiddelde kenmerkwaarde niet van toepassing is op categorische kenmerken, zijn de waarden in deze kolommen het aandeel klanten in segmenten met een laag, gemiddeld of hoog verloop die vergeleken met het item geselecteerd in het zijpaneel dezelfde waarde hebben als het categorische kenmerk.

---

 > [!NOTE]
 > In de uitvoerentiteit voor dit model geeft *ChurnScore* de voorspelde waarschijnlijkheid van verloop aan en is *IsChurn* een binair label op basis van *ChurnScore* met een drempel van 0,5. Als deze standaarddrempel niet werkt voor uw scenario, [maakt u een nieuw segment](segments.md#create-a-segment) met uw geprefereerde drempel. Niet alle klanten hoeven actieve klanten te zijn. Sommigen van hen hebben misschien al een lange tijd geen activiteit gehad en worden al als verlopen beschouwd, op basis van uw verloopdefinitie. Het voorspellen van het verlooprisico voor klanten die al verloop vertonen, is niet nuttig omdat ze geen doelgroep van belang zijn.
>
> Als u de verloopscore wilt bekijken, gaat u naar **Gegevens** > **Entiteiten** en bekijkt u het gegevenstabblad voor de uitvoerentiteit die u voor dit model hebt gedefinieerd.

[!INCLUDE [footer-include](includes/footer-banner.md)]
