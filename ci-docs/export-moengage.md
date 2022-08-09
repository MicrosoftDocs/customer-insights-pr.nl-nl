---
title: Segmenten exporteren naar MoEngage
description: Ontdek hoe u de verbinding met MoEngage configureert en exporteert.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ffc591c01a5a9434cde41f2da25fa930a515b8c1
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9199086"
---
# <a name="export-segments-to-moengage-preview"></a>Segmenten exporteren naar MoEngage (preview)

Exporteer segmenten van geharmoniseerde klantprofielen naar MoEngage en gebruik ze voor e-mailmarketing in MoEngage.

## <a name="prerequisites-for-a-connection"></a>Vereisten voor een verbinding

- [MoEngage-account](https://www.moengage.com/) en bijbehorende beheerdersreferenties.
- API-sleutel van MoEngage van Instellingen > API in MoEngage.
- [Segmenten geconfigureerd](segments.md) in Customer Insights.

## <a name="known-limitations"></a>Bekende beperkingen

- Maximaal 100.000 klantprofielen per export naar MoEngage en dit kan tot 15 minuten duren. Het aantal klantprofielen dat u kunt exporteren naar MoEngage, is afhankelijk van uw contract met MoEngage.
- Alleen segmenten.

## <a name="set-up-connection-to-moengage"></a>Verbinding instellen met MoEngage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Ga naar **Beheerder** > **Verbindingen**.

1. Selecteer **Verbinding toevoegen** en kies **MoEngage** om de verbinding te configureren.

1. Geef uw verbinding een herkenbare naam in het veld **Weergavenaam**. De naam en het type verbinding beschrijven deze verbinding. We raden u aan een naam te kiezen die het doel en het doel van de verbinding uitlegt.

1. Kies wie deze verbinding kan gebruiken. Als u geen actie onderneemt, wordt Beheerders gebruikt als standaardinstelling. Zie [Inzenders toestaan om een verbinding te gebruiken voor exports](connections.md#allow-contributors-to-use-a-connection-for-exports) voor meer informatie.

1. Voer uw [API-id en API-sleutel voor MoEngage-gegevens](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY) in.

1. Bekijk [Gegevensprivacy en naleving](connections.md#data-privacy-and-compliance) en selecteer **Ik ga akkoord**.

1. Selecteer **Verbinden** om de verbinding met MoEngage te initialiseren.

1. Selecteer **Uzelf toevoegen als exportgebruiker** en geef uw Customer Insights-referenties op.

1. Selecteer **Opslaan** om de verbinding te voltooien.

## <a name="configure-an-export"></a>Een export configureren

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Ga naar **Gegevens** > **Exports**.

1. Selecteer **Export toevoegen** om een nieuwe export te maken.

1. Kies in het veld **Verbinding voor export** een verbinding uit de sectie MoEngage. Als u deze sectienaam niet ziet, zijn er geen verbindingen van dit type voor u beschikbaar.

1. In de sectie **Gegevensvergelijking** selecteert u in het veld **E-mail** het veld dat het e-mailadres van een klant vertegenwoordigt. Herhaal dezelfde stappen voor andere optionele velden.

1. Selecteer de segmenten die u wilt exporteren. We maken een of meer segmenten met dezelfde naam als de geselecteerde segmenten in MoEngage onder **Segmenten** > **Aangepaste segmenten**.

1. Selecteer **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
