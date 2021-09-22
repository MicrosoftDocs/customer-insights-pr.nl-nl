---
title: Rollen en machtigingen
description: Overzicht van beschikbare rollen en machtigingen voor werkruimteleden.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 07/06/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 6d7f4db4a130fc15a69b380c892538db5492d96d8e13f3c070c6a6b9bd098371
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036687"
---
# <a name="roles-and-permissions"></a>Rollen en machtigingen

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Een werkruimte is de manier waarop u gebeurtenissen en rapporten opslaat en beheert. Een lid is een gebruiker die toegang heeft tot een werkruimte. U kunt leden aan uw werkruimte toewijzen en hun rollen en machtigingen definiëren. Beheerdersrollen beheren werkruimten en omgevingen en configureren betrokkenheidsinzichten voor andere gebruikers. De inzenderrollen zijn gericht op analisten die geen betrokkenheidsinzichten hoeven te configureren, maar hun eigen rapporten, trechters of segmenten willen maken.

## <a name="permissions"></a>Bevoegdheden
  
In het volgende diagram worden de machtigingen voor elke rol aangegeven. 

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
