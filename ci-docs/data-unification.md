---
title: Een geharmoniseerde weergave maken van uw klanten
description: Doorloop het proces voor gegevensharmonisering met uw gegevens om één hoofdgegevensset van account- of klantprofielen te maken.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: c2a81776eab147c4b5209a6fbf89c0f4c9853d1d
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304421"
---
# <a name="data-unification-overview"></a>Overzicht van gegevensharmonisatie

Na [het opzetten van de gegevensbronnen](data-sources.md) kunt u de gegevens harmoniseren. Met gegevensharmonisatie kunt u gegevensbronnen die ooit ongelijksoortig waren, samenbrengen in één hoofdgegevensset die een geharmoniseerde weergave van die gegevens biedt.

Voor individuele consumenten (B2C) waarbij de gegevens zijn gecentreerd rond individuen, biedt harmonisatie een geharmoniseerde weergave van uw klanten. Voor zakelijke accounts (B2B) waarbij de gegevens zijn gecentreerd rond accounts, biedt harmonisatie een geharmoniseerde weergave van uw accounts. [Harmonisatie van contactpersonen (preview)](data-unification-contacts.md) maakt het mogelijk contactpersonen voor die accounts apart te harmoniseren en aan de accounts te koppelen.

Gegevens kunnen worden geharmoniseerd in een enkele entiteit of in meerdere entiteiten.

# <a name="individual-consumers-b-to-c"></a>[Individuele consumenten (B-to-C)](#tab/b2c)

Het harmonisatieproces wijst klantgegevens uit uw gegevensbronnen toe, verwijdert duplicaten, stemt de gegevens tussen entiteiten af en stel een geharmoniseerd profiel op. Harmonisatie wordt uitgevoerd in deze volgorde:

1. [Bronvelden](map-entities.md) (voorheen Kaart genoemd): selecteer in de stap Bronvelden de entiteiten en velden die u in het harmonisatieproces wilt opnemen. Wijs velden toe aan een algemeen semantisch type dat het doel van het veld beschrijft.

1. [Dubbele records](remove-duplicates.md) (voorheen onderdeel van Afstemmen): definieer in de stap Dubbele records optioneel regels om dubbele klantrecords uit elke entiteit te verwijderen.

1. [Overeenkomende voorwaarden](match-entities.md) (voorheen Afstemmen genoemd): definieer in de stap Overeenkomende voorwaarden regels die klantrecords tussen entiteiten matchen. Wanneer een klant in twee of meer entiteiten wordt gevonden, wordt één geconsolideerde record gemaakt met alle kolommen en gegevens van elke entiteit.

1. [Geharmoniseerde klantvelden](merge-entities.md) (voorheen Samenvoegen genoemd): bepaal in de stap Geharmoniseerde klantvelden welke bronvelden moeten worden opgenomen, uitgesloten of samengevoegd tot een geharmoniseerd klantprofiel.  

1. [Beoordeel](review-unification.md) en maak het geharmoniseerde profiel.

# <a name="business-accounts-b-to-b"></a>[Zakelijke accounts (B-to-B)](#tab/b2b)

Het harmonisatieproces wijst accountgegevens uit uw gegevensbronnen toe, verwijdert duplicaten, stemt de gegevens tussen entiteiten af en stel een geharmoniseerd profiel op. Harmonisatie wordt uitgevoerd in deze volgorde:

1. [Bronvelden](map-entities.md) (voorheen Kaart genoemd): selecteer in de stap Bronvelden de entiteiten en velden die u in het harmonisatieproces voor account wilt opnemen. Wijs velden toe aan een algemeen semantisch type dat het doel van het veld beschrijft.

1. [Dubbele records](remove-duplicates.md) (voorheen onderdeel van Afstemmen): definieer in de stap Dubbele records optioneel regels om dubbele accountrecords uit elke entiteit te verwijderen.

1. [Overeenkomende voorwaarden](match-entities.md) (voorheen Afstemmen genoemd): definieer in de stap Overeenkomende voorwaarden regels die accountrecords tussen entiteiten afstemmen. Wanneer een account in twee of meer entiteiten wordt gevonden, wordt één geconsolideerde record gemaakt met alle kolommen en gegevens van elke entiteit.

1. [Geharmoniseerde klantvelden](merge-entities.md) (voorheen Samenvoegen genoemd): bepaal in de stap Geharmoniseerde klantvelden welke bronvelden moeten worden opgenomen, uitgesloten of samengevoegd tot een geharmoniseerd klantprofiel.  

1. [Beoordeel](review-unification.md) en maak het geharmoniseerde profiel.

Na harmonisatie van accounts kunt u optioneel [contactpersonen voor die accounts harmoniseren (preview)](data-unification-contacts.md) en de geharmoniseerde contactpersonen aan de geharmoniseerde accounts koppelen.

---

Na het voltooien van gegevensharmonisatie kunt u desgewenst:

- [Relaties tussen entiteiten instellen](relationships.md) om geavanceerde segmenten te maken.
- [Uw gegevens verrijken](enrichment-hub.md) om een breder scala aan inzichten over uw klanten te krijgen.
- [Activiteiten definiëren](activities.md) van enkele van de opgenomen kenmerken.
- [Metingen bouwen](measures.md) om het gedrag van klanten en de bedrijfsprestaties beter te begrijpen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
