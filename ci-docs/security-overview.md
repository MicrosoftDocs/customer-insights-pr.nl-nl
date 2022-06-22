---
title: Beveiligingsinstellingen in Customer Insights
description: Meer informatie over beveiligingsinstellingen in Dynamics 365 Customer Insights.
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947409"
---
# <a name="security-settings-in-customer-insights"></a>Beveiligingsinstellingen in Customer Insights

De pagina **Beveiliging** geeft opties weer om gebruikersmachtigingen en functies te configureren die bijdragen aan een veiliger Dynamics 365 Customer Insights. Alleen beheerders hebben toegang tot deze pagina.

Ga naar **Beheerder** > **Beveiliging** om de instellingen te configureren.

De pagina **Beveiliging** bevat de volgende tabbladen:

- [Gebruikers](#users-tab)
- [API's](#apis-tab)
- [Privékoppelingen](#private-links-tab)
- [Key Vault](#key-vault-tab)
- [Veilig toegang krijgen tot klantgegevens met Klanten-Lockbox (preview)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>Tabblad Gebruikers

Toegang tot Customer Insights is beperkt tot gebruikers in uw organisatie die door een beheerder aan de toepassing zijn toegevoegd. Met het tabblad **Gebruikers** kunt u de gebruikerstoegang en hun machtigingen beheren. Zie [Gebruikersmachtigingen](permissions.md) voor meer informatie.

## <a name="apis-tab"></a>Tabblad API's

Bekijk en beheer de sleutels om de [Customer Insights-API's](apis.md) te gebruiken met de gegevens van uw omgeving.

U kunt nieuwe primaire en secundaire sleutels maken door te **Primaire opnieuw genereren** of **Secundaire opnieuw genereren** te selecteren. 

Om API-toegang tot de omgeving te blokkeren, selecteert u **Uitschakelen**. Als API's zijn uitgeschakeld, kunt u **Inschakelen** selecteren om opnieuw toegang te verlenen.

## <a name="private-links-tab"></a>Tabblad Privékoppelingen

Met [Azure Private Link](/azure/private-link/private-link-overview) maakt Customer Insights verbinding met uw Azure Data Lake Storage-account over een privé-eindpunt in uw virtuele netwerk. Voor gegevens in een opslagaccount, dat niet is blootgesteld aan het openbare internet, maakt Private Link de verbinding met dat beperkte netwerk mogelijk.

> [!IMPORTANT]
> Minimale rolvereiste voor het opzetten van een Private Link-verbinding:
>
> - Customer Insights: Beheerder
> - Ingebouwde Azure-rol: [Bijdrager aan opslagaccount](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Machtigingen voor aangepaste Azure-rol: [Microsoft.Storage/storageAccounts/read en Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

Het instellen van Private Link in Customer Insights is een proces in twee stappen. Start het maken van een privékoppeling vanuit **Beheer** > **Beveiliging** > **Privékoppelingen** in Customer Insights. Op het deelvenster **Privékoppeling toevoegen** worden opslagaccounts van uw tenant vermeld die u mag zien. Selecteer het opslagaccount en geef toestemming om de privékoppeling te maken.

Vervolgens moet u de privékoppeling goedkeuren aan de kant van het Data Lake Storage-account. Open de koppeling die op het scherm wordt weergegeven om de nieuwe privékoppeling goed te keuren.

## <a name="key-vault-tab"></a>Tabblad Sleutelkluis

Via het tabblad **Sleutelkluis** kunt u uw eigen [Azure-sleutelkluis](/azure/key-vault/general/basic-concepts) voor de omgeving koppelen en beheren.
De speciale sleutelkluis kan worden gebruikt om geheimen in de nalevingsgrens van een organisatie op te zetten en te gebruiken. Customer Insights kan de geheimen in Azure Key Vault gebruiken om [verbindingen in te stellen](connections.md) naar systemen van derden.

Zie [Bring your own Azure Key Vault](use-azure-key-vault.md) voor meer informatie.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Veilig toegang krijgen tot klantgegevens met Klanten-Lockbox (preview)

Customer Insights gebruikt de Power Platform-mogelijkheid Klanten-Lockbox. Klanten-Lockbox biedt een interface om verzoeken om gegevenstoegang te beoordelen en goed te keuren (of af te wijzen). Deze verzoeken doen zich voor wanneer gegevenstoegang tot klantgegevens nodig is om een ondersteuningscase op te lossen. Om deze functie te gebruiken, moet Customer Insights een bestaande verbinding hebben met een Microsoft Dataverse-omgeving in uw tenant.

Zie het [overzicht](/power-platform/admin/about-lockbox#summary) van Power Platform Klanten-Lockbox voor meer informatie over Klanten-Lockbox. Het artikel beschrijft ook de [werkstroom](/power-platform/admin/about-lockbox#workflow) en de vereiste [instellingen](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) om Klanten-Lockbox in te schakelen.

> [!IMPORTANT]
> Algemeen beheerders voor Power Platform of Power Platform-beheerders kunnen Klanten-Lockbox-verzoeken goedkeuren die zijn uitgegeven voor Customer Insights.

[!INCLUDE [footer-include](includes/footer-banner.md)]
