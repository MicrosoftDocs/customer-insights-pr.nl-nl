---
title: Bring your own Azure Key Vault (preview)
description: Informatie over hoe u Customer Insights configureert om uw eigen Azure Key Vault te gebruiken om geheimen te beheren.
ms.date: 08/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 229fb5698a02d1d73c30442f61c7b1b5fce918bf
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246149"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Bring your own Azure Key Vault (preview)

Organisaties kunnen aan nalevingsvereisten voldoen door een speciale [Azure-sleutelkluis](/azure/key-vault/general/basic-concepts) aan een Customer Insights-omgeving te koppelen.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>De sleutelkluis koppelen aan de Customer Insights-omgeving

Stel de speciale sleutelkluis is om geheimen op te zetten en te gebruiken in de nalevingsgrens van een organisatie.

### <a name="prerequisites"></a>Vereisten

- Een actief Azure-abonnement.

- Een rol [Beheerder](permissions.md#admin) [toegewezen](permissions.md#add-users) in Customer Insights.

- Rollen [Inzender](/azure/role-based-access-control/built-in-roles#contributor) en [Beheerder gebruikerstoegang](/azure/role-based-access-control/built-in-roles#user-access-administrator) in de sleutelkluis of de resourcegroep waartoe de sleutelkluis behoort. Ga voor meer informatie naar [Azure-roltoewijzingen toevoegen of verwijderen met behulp van de Azure-portal](/azure/role-based-access-control/role-assignments-portal). Als u de rol Beheerder gebruikerstoegang niet hebt in de sleutelkluis, stelt u afzonderlijk op rollen gebaseerde toegangsbeheermachtigingen in voor de Azure-service-principal voor Dynamics 365 Customer Insights. Volg de stappen om [een Azure-service-principal te gebruiken](connect-service-principal.md) voor de sleutelkluis die moet worden gekoppeld.

- De Key Vault-firewall moet zijn **uitgeschakeld** voor de sleutelkluis.

- De sleutelkluis bevindt zich in dezelfde [Azure-locatie](https://azure.microsoft.com/global-infrastructure/geographies/#overview) als de Customer Insights-omgeving. Ga in Customer Insights naar **Beheer** > **Systeem** en het tabblad **Info** om de regio van de omgeving te bekijken.

### <a name="recommendations"></a>Aanbevelingen

- [Gebruik een aparte of speciale sleutelkluis](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults) die alleen de geheimen bevat die nodig zijn voor Customer Insights.

- Volg de [best practices om Key Vault te gebruiken](/azure/key-vault/general/best-practices#turn-on-logging) voor opties voor toegangscontrole, back-up, audit en herstel.

### <a name="link-a-key-vault-to-the-environment"></a>Een sleutelkluis aan de omgeving koppelen

1. Ga naar **Beheer** > **Beveiliging** en selecteer het tabblad **Sleutelkluis**.
1. Op de tegel **Key Vault** selecteer **Instellingen**.
1. Kies een **Abonnement**.
1. Kies een sleutelkluis in de keuzelijst **Key Vault**. Als er te veel sleutelkluizen beschikbaar zijn, selecteert u een resourcegroep om de zoekresultaten te beperken.
1. Bekijk [Gegevensprivacy en naleving](connections.md#data-privacy-and-compliance) en selecteer **Ik ga akkoord**.
1. Selecteer **Save**.

Op de tegel **Key Vault** worden de gekoppelde sleutelkluisnaam, het abonnement en de resourcegroep weergegeven. Deze is klaar om te worden gebruikt in configuratie van de verbinding.
Ga naar [Machtigingen op de sleutelkluis voor doelgroepinzichten](#permissions-granted-on-the-key-vault) voor meer informatie over welke machtigingen op de sleutelkluis worden verleend aan Customer Insights.

## <a name="use-the-key-vault-in-the-connection-setup"></a>De sleutelkluis gebruiken in configuratie van de verbinding

Bij het [instellen van verbindingen](connections.md) naar [ondersteunde systemen van derden](#supported-connection-types), gebruikt u de geheimen in de gekoppelde Key Vault om de verbindingen te configureren.

1. Ga naar **Beheerder** > **Verbindingen**.
1. Selecteer **Verbinding toevoegen**.
1. Voor de ondersteunde verbindingstypen is er een schakeloptie **Key Vault gebruiken** beschikbaar als u een sleutelkluis hebt gekoppeld.
1. In plaats van het geheim handmatig in te voeren, kiest u de geheime naam die verwijst naar de geheime waarde in de sleutelkluis.

   :::image type="content" source="media/use-key-vault-secret.png" alt-text="Verbindingsvenster met een SFTP-verbinding die gebruikmaakt van een geheim in de Key Vault.":::

1. Selecteer **Opslaan** om de verbinding te maken.

## <a name="supported-connection-types"></a>Ondersteunde verbindingstypen

De volgende [export](export-destinations.md)-verbindingen worden ondersteund:

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault"></a>Machtigingen verleend op de sleutelkluis

De volgende machtigingen worden verleend aan Customer Insights op een gekoppelde sleutelkluis als [Toegangsbeleid voor Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) of [Op rollen gebaseerd toegangsbeheer van Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) is ingeschakeld.

### <a name="key-vault-access-policy"></a>Toegangsbeleid voor Key Vault

| Type        | Bevoegdheden          |
| ----------- | -------------------- |
| Toets         | [Sleutels ophalen](/rest/api/keyvault/keys/get-keys/get-keys), [Sleutel ophalen](/rest/api/keyvault/keys/get-key/get-key)                                 |
| Geheim      | [Geheimen ophalen](/rest/api/keyvault/secrets/get-secrets/get-secrets), [Geheim ophalen](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| Certificaat | [Certificaten ophalen](/rest/api/keyvault/certificates/get-certificates/get-certificates), [Certificaat ophalen](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

Minimaal de voorgaande waarden worden opgesomd en gelezen tijdens uitvoering.

### <a name="azure-role-based-access-control"></a>Op rollen gebaseerd toegangsbeheer van Azure

De [gebruikersrollen Key Vault-lezer en Gebruiker van Key Vault-geheimen](/azure/key-vault/general/rbac-guide?tabs=azure-cli) worden toegevoegd voor Customer Insights.

## <a name="frequently-asked-questions"></a>Veelgestelde vragen

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Kan Customer Insights geheimen schrijven of geheimen overschrijven in de sleutelkluis?

Nee Alleen de lees- en lijstmachtigingen die worden beschreven in [toegekende machtigingen](#permissions-granted-on-the-key-vault) worden toegekend aan Customer Insights. Het systeem kan geen geheimen in de sleutelkluis toevoegen, verwijderen of overschrijven. Dat is ook de reden waarom u geen inloggegevens kunt invoeren wanneer een verbinding Key Vault gebruikt.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Kan ik een verbinding wijzigen zodat standaardverificatie wordt gebruikt in plaats van Key Vault-geheimen?

Nee U kunt niet teruggaan naar een standaardverbinding nadat u de verbinding hebt geconfigureerd met behulp van een geheim uit een gekoppelde sleutelkluis. Maak een aparte verbinding en verwijder de oude als u deze niet meer nodig hebt.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Hoe kan ik toegang tot een sleutelkluis voor Customer Insights intrekken?

Als het [toegangsbeleid voor Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) of [op rollen gebaseerd toegangsbeheer van Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) is ingeschakeld, moet u de machtigingen voor de service-principal `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` met de naam `Dynamics 365 AI for Customer Insights` verwijderen. Alle verbindingen die gebruikmaken van de sleutelkluis werken niet meer.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Een geheim dat in een verbinding wordt gebruikt, is verwijderd uit de sleutelkluis. Wat kan ik doen?

Er verschijnt een melding in Customer Insights wanneer een geconfigureerd geheim in de sleutelkluis niet meer toegankelijk is. Schakel [zacht-verwijderen](/azure/key-vault/general/soft-delete-overview) in op de sleutelkluis om geheimen te herstellen als ze per ongeluk werden verwijderd.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Een verbinding werkt niet, maar mijn geheim zit in de sleutelkluis. Wat kan de oorzaak zijn?

Er wordt een melding weergegeven in Customer Insights als er toegang tot de sleutelkluis kan worden gekregen. De oorzaak kan zijn:

- De machtigingen voor de service-principal van Customer Insights werd verwijderd. Ze moeten handmatig worden hersteld.

- De firewall op de sleutelkluis is ingeschakeld. De firewall moet worden uitgeschakeld om de sleutelkluis weer toegankelijk te maken voor Customer Insights.
