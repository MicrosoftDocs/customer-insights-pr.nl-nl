---
title: Overzicht van gegevensharmonisatie
description: Doorloop het proces voor gegevensharmonisatie met uw gegevens om één gegevensset van geharmoniseerde klantprofielen te maken.
ms.date: 05/10/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: v-wendysmith
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: 766e688cb80c50a0d620943f87b76eb84a2fb89a
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139478"
---
# <a name="data-unification-overview"></a>Overzicht van gegevensharmonisatie

Na [het opzetten van de gegevensbronnen](data-sources.md) kunt u de gegevens harmoniseren. Met gegevensharmonisatie kunt u gegevensbronnen die ooit ongelijksoortig waren, samenbrengen in één hoofdgegevensset die een geharmoniseerde weergave van die gegevens biedt. Voor individuele consumenten (B2C) waarbij de gegevens zijn gecentreerd rond individuen, biedt harmonisatie een geharmoniseerde weergave van uw klanten. Voor zakelijke accounts (B2B) waarbij de gegevens zijn gecentreerd rond accounts, biedt harmonisatie een geharmoniseerde weergave van uw accounts.

Gegevens kunnen worden geharmoniseerd in een enkele entiteit of in meerdere entiteiten. Harmonisatie wordt uitgevoerd in deze volgorde:

1. [Bronvelden](map-entities.md) (voorheen Kaart genoemd): selecteer in de stap Bronvelden de entiteiten en velden die u in het harmonisatieproces wilt opnemen. Wijs velden toe aan een algemeen semantisch type dat het doel van het veld beschrijft.

1. [Dubbele records](remove-duplicates.md) (voorheen onderdeel van Afstemmen): definieer in de stap Dubbele records optioneel regels om dubbele klantrecords uit elke entiteit te verwijderen.

1. [Overeenkomende voorwaarden](match-entities.md) (voorheen Afstemmen genoemd): definieer in de stap Overeenkomende voorwaarden regels die klantrecords tussen entiteiten matchen. Wanneer een klant in twee of meer entiteiten wordt gevonden, wordt één geconsolideerde record gemaakt met alle kolommen en gegevens van elke entiteit.

1. [Geharmoniseerde klantvelden](merge-entities.md) (voorheen Samenvoegen genoemd): bepaal in de stap Geharmoniseerde klantvelden welke bronvelden moeten worden opgenomen, uitgesloten of samengevoegd tot een geharmoniseerd klantprofiel.  

1. [Beoordeel](review-unification.md) en maak het geharmoniseerde profiel.

Na het voltooien van de gegevensharmonisatie kunt u desgewenst:

- [Relaties tussen entiteiten instellen](relationships.md) om geavanceerde segmenten te maken.
- [Uw gegevens verrijken](enrichment-hub.md) om een breder scala aan inzichten over uw klanten te krijgen.
- [Activiteiten definiëren](activities.md) van enkele van de opgenomen kenmerken.
- [Metingen bouwen](measures.md) om het gedrag van klanten en de bedrijfsprestaties beter te begrijpen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
