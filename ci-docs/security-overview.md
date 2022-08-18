---
title: Beveiligingsinstellingen configureren
description: Meer informatie over beveiligingsinstellingen in Dynamics 365 Customer Insights.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ea21163d7dd05370de28ca8340ae9583846adb26
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246056"
---
# <a name="configure-security-settings"></a>Beveiligingsinstellingen configureren

Beheer API-sleutels, krijg toegang tot klantgegevens en stel een Azure Private Link in.

## <a name="manage-api-keys"></a>API-sleutels beheren

Bekijk en beheer de sleutels om de [Customer Insights-API's](apis.md) te gebruiken met de gegevens in uw omgeving.

1. Ga naar **Systeem** > **Beveiliging** en selecteer het tabblad **API's**.

1. Als er geen API-toegang tot de omgeving is ingesteld, selecteert u **Inschakelen**. Of blokkeer de API-toegang tot de omgeving door **Uitschakelen** te selecteren en te bevestigen.

1. Beheer de primaire en secundaire API-sleutels:

   1. U kunt de primaire of secundaire API-sleutel weergeven door het symbool **Weergeven** te selecteren.

   1. U kunt de primaire of secundaire API-sleutel kopiëren door het symbool **Kopiëren** te selecteren.

   1. U kunt nieuwe primaire of secundaire API-sleutels maken door **Primaire opnieuw genereren** of **Secundaire opnieuw genereren** te selecteren.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Veilig toegang krijgen tot klantgegevens met Klanten-Lockbox (preview)

Customer Insights gebruikt de mogelijkheid Klanten-lockbox voor Power Platform. Klanten-Lockbox biedt een interface om verzoeken om gegevenstoegang te beoordelen en goed te keuren (of af te wijzen). Deze verzoeken doen zich voor wanneer gegevenstoegang tot klantgegevens nodig is om een ondersteuningscase op te lossen. Om deze functie te gebruiken, moet Customer Insights een bestaande verbinding hebben met een Microsoft Dataverse-omgeving in uw tenant.

Zie het [overzicht](/power-platform/admin/about-lockbox#summary) van Power Platform Klanten-Lockbox voor meer informatie over Klanten-Lockbox. Het artikel beschrijft ook de [werkstroom](/power-platform/admin/about-lockbox#workflow) en de vereiste [instellingen](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) om Klanten-Lockbox in te schakelen.

> [!IMPORTANT]
> Algemeen beheerders voor Power Platform of Power Platform-beheerders kunnen Klanten-Lockbox-verzoeken goedkeuren die zijn uitgegeven voor Customer Insights.

## <a name="set-up-an-azure-private-link"></a>Een Azure Private Link instellen

Met [Azure Private Link](/azure/private-link/private-link-overview) maakt Customer Insights verbinding met uw Azure Data Lake Storage-account over een privé-eindpunt in uw virtuele netwerk. Voor gegevens in een opslagaccount, dat niet is blootgesteld aan het openbare internet, maakt Private Link de verbinding met dat beperkte netwerk mogelijk.

> [!IMPORTANT]
> Minimale rolvereiste voor het opzetten van een Private Link-verbinding:
>
> - Customer Insights: Beheerder
> - Ingebouwde Azure-rol: [Bijdrager aan opslagaccount](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Machtigingen voor aangepaste Azure-rol: [Microsoft.Storage/storageAccounts/read en Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. Ga in Customer Insights naar **Beheer** > **Beveiliging** en selecteer het tabblad **Privékoppelingen**.

1. Selecteer **Privékoppeling toevoegen**.

   Op het deelvenster **Privékoppeling toevoegen** worden opslagaccounts van uw tenant vermeld die u mag zien.

1. Selecteer het abonnement, de resourcegroep en het opslagaccount.

1. Bekijk [Gegevensprivacy en naleving](connections.md#data-privacy-and-compliance) en selecteer **Ik ga akkoord**.

1. Selecteer **Save**.

1. Ga naar uw Data Lake Storage-account en open de koppeling op het scherm.

1. Keur de privékoppeling goed.


[!INCLUDE [footer-include](includes/footer-banner.md)]
