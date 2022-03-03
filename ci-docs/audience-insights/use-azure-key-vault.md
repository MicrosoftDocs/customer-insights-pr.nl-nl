---
title: Bring your own Azure Key Vault om geheimen te beheren
description: Leer hoe u Customer Insights configureert om uw eigen Azure Key Vault te gebruiken.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 5b22c1464b3f089551f485f98d6d93840ff77136
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355885"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Bring your own Azure Key Vault (preview)

Een speciale [Azure Key Vault](/azure/key-vault/general/basic-concepts) koppelen aan een omgeving voor doelgroepinzichten helpt organisaties om te voldoen aan compliancevereisten.
De speciale sleutelkluis kan worden gebruikt om geheimen in de nalevingsgrens van een organisatie op te zetten en te gebruiken. Doelgroepinzichten kunnen de geheimen in Azure Key Vault gebruiken om [verbindingen in te stellen](connections.md) naar systemen van derden.

## <a name="link-the-key-vault-to-the-audience-insights-environment"></a>Koppel de sleutelkluis aan de omgeving voor doelgroepeninzichten

### <a name="prerequisites"></a>Vereisten

Om de sleutelkluis in doelgroepinzichten te configureren, moet aan de volgende vereisten worden voldaan:

- U heeft een actief Azure-abonnement.

- U hebt de rol van [Beheerder](permissions.md#administrator) in doelgroepinzichten. Meer informatie over [gebruikersmachtigingen in doelgroepinzichten](permissions.md#assign-roles-and-permissions).

- Er zijn de rollen [Inzender](/azure/role-based-access-control/built-in-roles#contributor) en [Beheerder gebruikerstoegang](/azure/role-based-access-control/built-in-roles#user-access-administrator) in de sleutelkluis of de resourcegroep waartoe de sleutelkluis behoort. Ga voor meer informatie naar [Azure-roltoewijzingen toevoegen of verwijderen met behulp van de Azure-portal](/azure/role-based-access-control/role-assignments-portal). Als u de rol Beheerder gebruikerstoegang niet hebt in de sleutelkluis, moet u afzonderlijk op rollen gebaseerde toegangsbeheermachtigingen instellen voor de Azure-service-principal voor Dynamics 365 Customer Insights. Volg de stappen om [een Azure-service-principal te gebruiken](connect-service-principal.md) voor de sleutelkluis die moet worden gekoppeld.

- De Key Vault-firewall moet zijn **uitgeschakeld** voor de sleutelkluis.

- De sleutelkluis bevindt zich in dezelfde [Azure-locatie](https://azure.microsoft.com/global-infrastructure/geographies/#overview) als de doelgroepinzichtenomgeving. De regio van de omgeving in doelgroepinzichten wordt vermeld onder **Beheer** > **Systeem** > **Over** > **Regio**.

### <a name="link-a-key-vault-to-the-environment"></a>Een sleutelkluis aan de omgeving koppelen

1. Ga naar **Beheer** > **Systeem**, en selecteer het tabblad **Beveiliging**.
1. Op de tegel **Key Vault** selecteer **Instellingen**.
1. Kies een **Abonnement**.
1. Kies een sleutelkluis in de keuzelijst **Key Vault**. Als er te veel sleutelkluizen worden weergegeven, selecteert u een resourcegroep om de zoekresultaten te beperken.
1. Accepteer de verklaring **Gegevensprivacy en naleving**.
1. Selecteer **Opslaan**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Stappen om een gekoppelde sleutelkluis in te stellen in doelgroepinzichten.":::

Op de tegel **Key Vault** worden nu de gekoppelde sleutelkluisnaam, resourcegroep en abonnement weergegeven. Deze is klaar om te worden gebruikt in configuratie van de verbinding.
Ga voor meer informatie over welke machtigingen op de sleutelkluis worden verleend aan doelgroepinzichten naar [Machtigingen op de sleutelkluis voor doelgroepinzichten](#permissions-granted-on-the-key-vault-to-audience-insights), verderop in dit artikel.

## <a name="use-the-key-vault-in-the-connection-setup"></a>De sleutelkluis gebruiken in configuratie van de verbinding

Bij het [instellen van verbindingen](connections.md) naar systemen van derden, kunnen de geheimen in de gekoppelde Key Vault worden gebruikt om de verbindingen te configureren.

1. Ga naar **Beheerder** > **Verbindingen**.
1. Selecteer **Verbinding toevoegen**.
1. Voor de ondersteunde verbindingstypen is er een schakeloptie **Key Vault gebruiken** beschikbaar als u een sleutelkluis hebt gekoppeld.
1. In plaats van het geheim handmatig in te voeren, kunt u de geheime naam kiezen die verwijst naar de geheime waarde in de sleutelkluis.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="Verbindingsvenster met een SFTP-verbinding die gebruikmaakt van een geheim in de Key Vault.":::

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

## <a name="permissions-granted-on-the-key-vault-to-audience-insights"></a>Machtigingen die in de sleutelkluis worden verleend aan doelgroepinzichten

De volgende machtigingen worden verleend aan doelgroepinzichten op een gekoppelde sleutelkluis als [Toegangsbeleid voor Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) of [Op rollen gebaseerd toegangsbeheer van Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) is ingeschakeld.

### <a name="key-vault-access-policy"></a>Toegangsbeleid voor Key Vault

| Type        | Bevoegdheden          |
| ----------- | -------------------- |
| Toets         | [Sleutels ophalen](/rest/api/keyvault/get-keys), [Sleutel ophalen](/rest/api/keyvault/get-key)                                 |
| Geheim      | [Geheimen ophalen](/rest/api/keyvault/get-secrets), [Geheim ophalen](/rest/api/keyvault/get-secret)                     |
| Certificaat | [Certificaten ophalen](/rest/api/keyvault/get-certificates), [Certificaat ophalen](/rest/api/keyvault/get-certificate) |

Minimaal de voorgaande waarden worden opgesomd en gelezen tijdens uitvoering.

### <a name="azure-role-based-access-control"></a>Op rollen gebaseerd toegangsbeheer van Azure

De gebruikersrollen Key Vault-lezer en Gebruiker van Key Vault-geheimen worden toegevoegd voor doelgroepinzichten. Ga voor meer informatie over deze rollen naar [Ingebouwde Azure-rollen voor Key Vault-gegevensvlakbewerkingen](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Aanbevelingen

- Gebruik een aparte of speciale sleutelkluis die alleen de geheimen bevat die nodig zijn voor doelgroepinzichten. Lees meer over waarom [aparte sleutelkluizen worden aanbevolen](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Volg de [best practices om Key Vault te gebruiken](/azure/key-vault/general/best-practices#turn-on-logging) voor opties voor toegangscontrole, back-up, audit en herstel.

## <a name="frequently-asked-questions"></a>Veelgestelde vragen

### <a name="can-audience-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Kunnen doelgroepinzichten geheimen schrijven of geheimen overschrijven in de sleutelkluis?

Nee Alleen de lees- en lijstmachtigingen die worden beschreven in de sectie over [toegekende machtigingen](#permissions-granted-on-the-key-vault-to-audience-insights) eerder in dit artikel, worden toegekend aan doelgroepinzichten. Het systeem kan geen geheimen in de sleutelkluis toevoegen, verwijderen of overschrijven. Dat is ook de reden waarom u geen inloggegevens kunt invoeren wanneer een verbinding Key Vault gebruikt.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Kan ik een verbinding wijzigen zodat standaardverificatie wordt gebruikt in plaats van Key Vault-geheimen?

Nee U kunt niet teruggaan naar een standaardverbinding nadat u de verbinding hebt geconfigureerd met behulp van een geheim uit een gekoppelde sleutelkluis. Maak een aparte verbinding en verwijder de oude als u deze niet meer nodig hebt.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-audience-insights"></a>Hoe kan ik toegang tot een sleutelkluis voor doelgroepinzichten intrekken?

Afhankelijk van het feit of [Toegangsbeleid voor Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) of [Op rollen gebaseerd toegangsbeheer van Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) is ingeschakeld, moet u de machtigingen verwijderen voor de service-principal `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` met de naam `Dynamics 365 AI for Customer Insights`. Alle verbindingen die gebruikmaken van de sleutelkluis werken niet meer.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Een geheim dat in een verbinding wordt gebruikt, is verwijderd uit de sleutelkluis. Wat kan ik doen?

Er verschijnt een melding in doelgroepinzichten wanneer een geconfigureerd geheim in de sleutelkluis niet meer toegankelijk is. Schakel [zacht-verwijderen](/azure/key-vault/general/soft-delete-overview) in op de sleutelkluis om geheimen te herstellen als ze per ongeluk werden verwijderd.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Een verbinding werkt niet, maar mijn geheim zit in de sleutelkluis. Wat kan de oorzaak zijn?

Er wordt een melding weergegeven in doelgroepinzichten als er geen toegang tot de sleutelkluis kan worden gekregen. De oorzaak kan zijn:

- De machtigingen voor de service-principal van doelgroepinzichten werden verwijderd. Ze moeten handmatig worden hersteld.

- De firewall op de sleutelkluis is ingeschakeld. De firewall moet worden uitgeschakeld om de sleutelkluis weer toegankelijk te maken voor doelgroepinzichten.
