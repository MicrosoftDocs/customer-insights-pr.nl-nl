---
title: Rollen en machtigingen
description: Overzicht van beschikbare rollen en machtigingen voor werkruimteleden.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ccc6a1b87b4cc28701e276b6e35432356e7647c4
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227533"
---
# <a name="roles-and-permissions"></a>Rollen en machtigingen

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Een werkruimte is waar u gebeurtenissen en rapporten opslaat en beheert. Zie voor meer informatie [Een werkruimte maken en leden toevoegen](create-workspace.md). 

Een werkruimte kan de volgende rollen en machtigingen bevatten:

- Gebruikers met de rol *Lid* hebben toegang tot een werkruimte. U kunt leden aan uw werkruimte toewijzen en hun rollen en machtigingen definiëren. 
- *Beheerdersrollen* beheren werkruimten en omgevingen en configureren betrokkenheidsinzichten voor andere gebruikers. 
- De rol *Inzender* is voor analisten die geen betrokkenheidsinzichten hoeven te configureren, maar wel hun eigen rapporten, trechters of segmenten willen maken.

## <a name="permissions"></a>Bevoegdheden
  
In de volgende tabel worden de machtigingen voor elke rol aangegeven. 

| Machtiging | Omgevingsbeheerder | Werkruimtebeheerder | Medewerker van omgeving | Medewerker van werkruimte | 
|--|--|--|--|--|
| Omgevingen maken (maker wordt automatisch omgevingsbeheerder) | X* | X* | X* | X* |  
| Omgeving configureren (omgevingsleden, omgeving verwijderen) | X |  |  |  |  
| Werkruimten maken | X |  |  |  |  
| Werkruimten configureren (werkruimteleden, werkruimte verwijderen) | X | X |  |  |  
| Gebeurtenissen en verfijnde gebeurtenissen configureren | X | X | |  |  
| Werkruimtegebeurtenissen en verfijnde gebeurtenissen weergeven | X | X | |  |  
| Werkruimtebronnen weergeven (rapporten, segmenten en metrische gegevens)| X | X | X | X |  
| Aangepaste rapporten en trechters maken | X | X | X | X |  
| Basisstatistieken en dimensies maken| X | X |  |  |  
| Segmenten maken| X | X | X | X |  

*Kan alleen proefomgevingen maken in preview. 

## <a name="add-members"></a>Leden toevoegen

U kunt leden toevoegen aan en verwijderen uit werkruimten en omgevingen. Zie [Omgevingen en werkruimten](manage-environments-workspaces.md) voor meer informatie.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
