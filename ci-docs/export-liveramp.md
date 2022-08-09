---
title: Segmenten exporteren naar LiveRamp (preview)
description: Leer hoe u de verbinding configureert en exporteert naar LiveRamp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 55eacea3af83f46583a3a43797d625479f56586b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196710"
---
# <a name="export-segments-to-liverampreg-preview"></a>Segmenten exporteren naar LiveRamp&reg; (preview)

Activeer uw gegevens in LiveRamp om verbinding te maken met meer dan 500 platforms op digitaal, sociaal en tv. Werk met uw gegevens in LiveRamp om advertentiecampagnes te targeten, onderdrukken en personaliseren.

## <a name="prerequisites"></a>Vereisten

- Een LiveRamp-abonnement om deze connector te kunnen gebruiken. U kunt een abonnement nemen door rechtstreeks [contact op te nemen met LiveRamp](https://liveramp.com/contact/). [Meer informatie over LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="known-limitations"></a>Bekende beperkingen

- Bij de LiveRamp-export wordt een SFTP-export gebruikt. SFTP-bestemmingen achter firewalls worden momenteel niet ondersteund.
- Als u een SSH-sleutel gebruikt voor verificatie, zorg er dan voor dat u [uw privésleutel maakt](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) als PEM- of SSH.COM-indeling. Als u Putty gebruikt, converteert u uw privésleutel door deze te exporteren als Open SSH. De volgende indelingen van privésleutels worden ondersteund:
  - RSA in OpenSSL PEM- en ssh.com-indeling
  - DSA in OpenSSL PEM- en ssh.com-indeling
  - ECDSA 256/384/521 in OpenSSL PEM-indeling
  - ED25519 en RSA in OpenSSH-sleutelindeling
- Hoe lang een export duurt, is afhankelijk van uw systeemprestaties. We raden twee CPU-cores en 1 Gb geheugen aan als minimale configuratie van uw server.
- Het exporteren van entiteiten met maximaal 100 miljoen klantprofielen kan 90 minuten duren bij gebruik van de aanbevolen minimale configuratie van twee CPU-cores en 1 Gb geheugen.
- Het werkelijke aantal profielen (of gegevens) dat u kunt exporteren naar LiveRamp, is afhankelijk van uw abonnement bij LiveRamp.

## <a name="set-up-connection-to-liveramp"></a>Verbinding instellen met LiveRamp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **LiveRamp**.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Standaard zijn dit alleen beheerders. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Kies of u zich wilt verifiëren via SSH of gebruikersnaam/wachtwoord voor uw verbinding en geef de nodige details op.

1. Selecteer **Verifiëren** om de verbinding met LiveRamp te testen.

1. Bekijk na een succesvolle verificatie [gegevensprivacy en naleving](connections.md#data-privacy-and-compliance) en selecteer **Ik ga akkoord**.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen**.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie LiveRamp. Neem contact op met een beheerder als er geen verbinding beschikbaar is.

1. Voer de naam in voor de export.

1. Selecteer in het veld **Gegevens verbinden** de optie **E-mail**, **Naam en adres** of **Telefoon** om naar LiveRamp te sturen voor identiteitsresolutie.

   :::image type="content" source="media/export-liveramp-segments.png" alt-text="LiveRamp-connector met kenmerktoewijzing.":::

1. Wijs de bijbehorende kenmerken toe van uw entiteit *Klant* voor de geselecteerde sleutel-id.

1. Selecteer **Kenmerk toevoegen** om meer kenmerken toe te wijzen om naar LiveRamp te verzenden.

   > [!TIP]
   > Als u meer kenmerken voor sleutel-id's naar LiveRamp verzendt, krijgt u waarschijnlijk een hoger overeenkomstpercentage.

1. Selecteer de segmenten die u wilt exporteren.

1. Selecteer **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
