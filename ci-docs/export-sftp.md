---
title: Gegevens exporteren naar SFTP-hosts (preview) (met video)
description: Leer hoe u de verbinding configureert en exporteert naar een SFTP-locatie.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b12d25ecbd2e5fb31d7d5a6bb775dc3e7c1bf007
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207223"
---
# <a name="export-data-to-sftp-hosts-preview"></a>Gegevens exporteren naar SFTP-hosts (preview)

Gebruik uw klantgegevens in toepassIngen van derden door ze te exporteren naar een SFTP-locatie (Secure File Transfer Protocol).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites"></a>Vereisten

- Beschikbaarheid van een SFTP-host en bijbehorende inloggegevens.

## <a name="known-limitations"></a>Bekende beperkingen

- SFTP-bestemmingen achter firewalls worden momenteel niet ondersteund.
- Hoe lang een export duurt, is afhankelijk van uw systeemprestaties. We raden twee CPU-cores en 1 Gb geheugen aan als minimale configuratie van uw server.
- Maximaal 100 miljoen klantprofielen kunnen worden geëxporteerd en dit kan 90 minuten duren bij gebruik van de aanbevolen minimale configuratie van twee CPU-cores en 1 Gb geheugen.
- Als u een SSH-sleutel gebruikt voor verificatie, zorg er dan voor dat u [uw privésleutel maakt](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) als PEM- of SSH.COM-indeling. Als u Putty gebruikt, converteert u uw privésleutel door deze te exporteren als Open SSH. De volgende indelingen van privésleutels worden ondersteund:
  - RSA in OpenSSL PEM- en ssh.com-indeling
  - DSA in OpenSSL PEM- en ssh.com-indeling
  - ECDSA 256/384/521 in OpenSSL PEM-indeling
  - ED25519 en RSA in OpenSSH-sleutelindeling

## <a name="set-up-connection-to-sftp"></a>Verbinding instellen MET SFTP

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **SFTP**.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Standaard zijn dit alleen beheerders. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Kies of u zich wilt verifiëren via SSH of gebruikersnaam/wachtwoord voor uw verbinding en geef de nodige details op. Als u een SSH-sleutel gebruikt voor verificatie, zorg er dan voor dat u [uw privésleutel maakt](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) als PEM- of SSH.COM-indeling. Als u Putty gebruikt, converteert u uw privésleutel door deze te exporteren als Open SSH. De volgende indelingen van privésleutels worden ondersteund:
   - RSA in OpenSSL PEM- en ssh.com-indeling
   - DSA in OpenSSL PEM- en ssh.com-indeling
   - ECDSA 256/384/521 in OpenSSL PEM-indeling
   - ED25519 en RSA in OpenSSH-sleutelindeling

1. Selecteer **Verifiëren** om de verbinding te testen.

1. Bekijk [Gegevensprivacy en naleving](connections.md#data-privacy-and-compliance) en selecteer **Ik ga akkoord**.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen**.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie SFTP. Neem contact op met een beheerder als er geen verbinding beschikbaar is.

1. Voer de naam in voor de export.

1. Kies of u uw gegevens **Gzipped** of **Uitgepakt** wilt exporteren en geef het **veldscheidingsteken** voor de geëxporteerde bestanden op.

1. Selecteer de entiteiten, bijvoorbeeld segmenten, die u wilt exporteren.

   > [!NOTE]
   > Elke geselecteerde entiteit wordt bij het exporteren opgesplitst in maximaal vijf uitvoerbestanden.

1. Selecteer **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!TIP]
> Export van entiteiten die een grote hoeveelheid gegevens bevatten, kan leiden tot meerdere CSV-bestanden in dezelfde map voor elke export. Het splitsen van exports gebeurt om prestatieredenen om de tijd die nodig is om een export te voltooien tot een minimum te beperken.

[!INCLUDE [footer-include](includes/footer-banner.md)]
