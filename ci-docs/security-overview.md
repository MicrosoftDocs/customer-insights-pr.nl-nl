---
title: Beveiligingsinstellingen in Dynamics 365 Customer Insights
description: Meer informatie over beveiligingsinstellingen in Dynamics 365 Customer Insights.
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653713"
---
# <a name="security-overview-page"></a>Overzichtspagina voor beveiliging

De pagina **Beveiliging** geeft opties weer om gebruikersmachtigingen en functies te configureren die bijdragen aan een veiliger Dynamics 365 Customer Insights. Alleen beheerders hebben toegang tot deze pagina. 

Ga naar **Beheerder** > **Beveiliging** om de instellingen te configureren.

De pagina **Beveiliging** bevat de volgende tabbladen:
- [Gebruikers](#users-tab)
- [API's](#apis-tab)
- [Key Vault](#key-vault-tab)

## <a name="users-tab"></a>Tabblad Gebruikers

Toegang tot Customer Insights is beperkt tot gebruikers in uw organisatie die door een beheerder aan de toepassing zijn toegevoegd. Met het tabblad **Gebruikers** kunt u de gebruikerstoegang en hun machtigingen beheren. Zie [Gebruikersmachtigingen](permissions.md) voor meer informatie.

## <a name="apis-tab"></a>Tabblad API's

Bekijk en beheer de sleutels om de [Customer Insights-API's](apis.md) te gebruiken met de gegevens van uw omgeving.

U kunt nieuwe primaire en secundaire sleutels maken door te **Primaire opnieuw genereren** of **Secundaire opnieuw genereren** te selecteren. 

Om API-toegang tot de omgeving te blokkeren, selecteert u **Uitschakelen**. Als API's zijn uitgeschakeld, kunt u **Inschakelen** selecteren om opnieuw toegang te verlenen.

## <a name="key-vault-tab"></a>Tabblad Sleutelkluis

Via het tabblad **Sleutelkluis** kunt u uw eigen [Azure-sleutelkluis](/azure/key-vault/general/basic-concepts) voor de omgeving koppelen en beheren.
De speciale sleutelkluis kan worden gebruikt om geheimen in de nalevingsgrens van een organisatie op te zetten en te gebruiken. Customer Insights kan de geheimen in Azure Key Vault gebruiken om [verbindingen in te stellen](connections.md) naar systemen van derden.

Zie [Bring your own Azure Key Vault](use-azure-key-vault.md) voor meer informatie.


[!INCLUDE [footer-include](includes/footer-banner.md)]
