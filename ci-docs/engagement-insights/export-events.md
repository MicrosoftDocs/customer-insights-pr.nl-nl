---
title: Verfijnde gebeurtenissen exporteren
description: Procedure om verfijnde gebeurtenissen en basisgebeurtenissen te exporteren.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: faa0c3afb08d1c0282b2164ed914637ce9aad88117af37ba44fdb81e7610e574
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032379"
---
# <a name="export-events"></a>Gebeurtenissen exporteren

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Een gebeurtenis staat voor gebruikersgedrag. Deze registreert wanneer een gebruiker een pagina weergeeft (weergavegebeurtenis) of interactie heeft met inhoud (actiegebeurtenis). Wanneer u kunt beslissen welke eigenschappen van de gegevens u in een rapport wilt weergeven, wordt deze virtuele weergave van de gegevens een *verfijnde gebeurtenis* genoemd. 

- U kunt gebeurtenissen en verfijnde gebeurtenissen exporteren naar externe opslag. 
- De export is een voorwaartse datastroom. U kunt de stroom niet bijvullen. 
- Exports hebben vaste schema's. Als u aangepaste eigenschappen aan een gebeurtenis toevoegt, worden deze niet meegenomen. Dan moet u een nieuwe export maken.

## <a name="prerequisites"></a>Vereisten

Voordat u een export instelt, moet u toegang hebben tot en een actief abonnement hebben op de Azure-portal. U hebt de opslagaccountgegevens nodig tijdens het exportproces. 

### <a name="create-an-azure-data-lake-storage-gen-2-accounts"></a>Een Azure Data Lake Storage Gen2-account maken

1. Meld u aan op de Azure-portal en [maak een nieuw opslagaccount](/azure/storage/common/storage-account-create). 

1. Zorg ervoor dat u **Hiërarchische naamruimte** op het tabblad **Geavanceerd** inschakelt. 

   :::image type="content" source="media/enable-hierarchical-namespace.png" alt-text="Hiërarchische naamruimte op het tabblad Geavanceerd inschakelen.":::

1. Nadat het is geïmplementeerd, gaat u naar het nieuwe opslagaccount. Selecteer **Instellingen** > **Toegangssleutels** in het navigatiedeelvenster. 

1. Kopieer de **Accountnaam** en **Sleutel** om ze te gebruiken bij het maken van een nieuwe export.
   :::image type="content" source="media/storage-account-access-keys.png" alt-text="Toegangssleutels in een opslagaccount.":::

## <a name="export-events"></a>Gebeurtenissen exporteren

U kunt gebeurtenissen op twee manieren exporteren: 
- Ga naar **Gegevens** > **Exports** en selecteer **Nieuwe export**.
- Ga naar **Gegevens** > **Gebeurtenissen**, selecteer **Meer [...]** naast de gebeurtenis die je wilt exporteren en selecteer **Exporteren** uit het vervolgkeuzemenu. 

U wordt door de stappen geleid om een export te maken:

1. Geef een **Exportnaam** op.

1. Kies in de vervolgkeuzelijst **Gebeurtenissenselectie** de basisgebeurtenissen en verfijnde gebeurtenissen die u in de export wilt opnemen. 

1. Selecteer onder **Bestandsstructuur** de cadans om nieuwe bestanden in de doelopslag te maken. Gebeurtenissen worden continu geëxporteerd zodra ze binnenkomen.

1. Selecteer de indeling van uw export. U kunt kiezen uit **Common Data Model**, **CSV** en **JSON**. Om de export met andere Dynamics 365-toepassingen te gebruiken, raden we aan de Common Data Model-indeling te gebruiken.

1. In de stap **Bestemming kiezen** geeft u de Azure Data Lake Storage Gen 2-locatie op.
    1. **ADLS Gen 2-accountnaam** is de naam van het opslagaccount waar u de export wilt opslaan. 
    1. **Mappad** definieert waar de export moet worden opgeslagen in het bestandssysteem en de directorystructuur van het opslagaccount.
    1. **Gedeelde sleutel** is beschikbaar via de Azure-portal voor het opslagaccount.

1. Controleer en bevestig uw selecties.

## <a name="view-and-manage-exports"></a>Exports weergeven en beheren

Als u eenmaal een export hebt ingesteld, gaat u naar **Gegevens** > **Exports** om deze te bekijken. Selecteer **Meer [...]** voor een bestaande export om deze te bewerken of te verwijderen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]