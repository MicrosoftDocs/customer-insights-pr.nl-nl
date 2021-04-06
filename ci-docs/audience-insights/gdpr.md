---
title: Rechten van betrokkenen (DSR) onder AVG | Microsoft Docs
description: Reageren op verzoeken van betrokkenen om de mogelijkheden van Dynamics 365 Customer Insights doelgroepinzichten.
ms.date: 05/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9c453c9b416bff0e6362a8ccf7ff534f4efa1e00
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597505"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="2d01c-103">Rechten van betrokkenen (DSR) onder AVG</span><span class="sxs-lookup"><span data-stu-id="2d01c-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="2d01c-104">Reageren op AVG-verwijderingsverzoeken voor gebruikersgegevens van betrokkenen voor Dynamics 365 Customer Insights doelgroepinzichten</span><span class="sxs-lookup"><span data-stu-id="2d01c-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="2d01c-105">Het 'recht op verwijdering' van persoonsgegevens uit de klantgegevens van een organisatie is een belangrijke bescherming in de Algemene verordening gegevensbescherming (AVG).</span><span class="sxs-lookup"><span data-stu-id="2d01c-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="2d01c-106">Het verwijderen van persoonlijke gegevens omvat het verwijderen van alle persoonlijke gegevens en door het systeem gegenereerde logboeken, behalve auditlogboekinformatie.</span><span class="sxs-lookup"><span data-stu-id="2d01c-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="2d01c-107">Verwijderingsverzoeken van betrokkenen beheren</span><span class="sxs-lookup"><span data-stu-id="2d01c-107">Manage data subject delete requests</span></span>

<span data-ttu-id="2d01c-108">Doelgroepinzichten bieden de volgende mogelijkheden binnen het product om persoonlijke gegevens voor een specifieke klant of gebruiker te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="2d01c-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="2d01c-109">**Verwijderingsverzoeken voor klantgegevens beheren**: klantgegevens in Customer Insights worden opgenomen vanuit originele gegevensbronnen buiten Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2d01c-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="2d01c-110">Alle verwijderingsverzoeken in het kader van de AVG moeten worden uitgevoerd in de originele gegevensbron.</span><span class="sxs-lookup"><span data-stu-id="2d01c-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="2d01c-111">**Beheer verwijderingsverzoeken voor gebruikersgegevens van Customer Insights**: gegevens voor gebruikers worden gemaakt door Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2d01c-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="2d01c-112">Alle verwijderingsverzoeken in het kader van de AVG moeten worden uitgevoerd in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2d01c-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="2d01c-113">Verwijderingsverzoeken voor klantgegevens beheren</span><span class="sxs-lookup"><span data-stu-id="2d01c-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="2d01c-114">Een Customer Insights-beheerder kan deze stappen volgen om klantgegevens te verwijderen die in de gegevensbron zijn verwijderd:</span><span class="sxs-lookup"><span data-stu-id="2d01c-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="2d01c-115">Aanmelden bij Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2d01c-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="2d01c-116">Ga in doelgroepinzichten naar **Gegevens** > **Gegevensbronnen**</span><span class="sxs-lookup"><span data-stu-id="2d01c-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="2d01c-117">Voor elke gegevensbron in de lijst met verwijderde klantgegevens:</span><span class="sxs-lookup"><span data-stu-id="2d01c-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="2d01c-118">Selecteer (...) en selecteer vervolgens **Vernieuwen**.</span><span class="sxs-lookup"><span data-stu-id="2d01c-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="2d01c-119">Controleer de status van de gegevensbron onder **Status**.</span><span class="sxs-lookup"><span data-stu-id="2d01c-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="2d01c-120">Een vinkje betekent dat de vernieuwing is geslaagd.</span><span class="sxs-lookup"><span data-stu-id="2d01c-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="2d01c-121">Een gevarendriehoek betekent dat er iets mis is gegaan.</span><span class="sxs-lookup"><span data-stu-id="2d01c-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="2d01c-122">Neem bij een gevarendriehoek contact op met D365CI@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="2d01c-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2d01c-123">![Verwijderingsverzoeken voor klantgegevens in het kader van de AVG afhandelen](media/gdpr-data-sources.png "Verwijderingsverzoeken voor klantgegevens in het kader van de AVG afhandelen")</span><span class="sxs-lookup"><span data-stu-id="2d01c-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="2d01c-124">Verwijderingsverzoeken voor gebruikersgegevens beheren</span><span class="sxs-lookup"><span data-stu-id="2d01c-124">Manage delete requests for user data</span></span>

<span data-ttu-id="2d01c-125">Een Customer Insights-beheerder kan deze stappen volgen om gegevens van Customer Insights-gebruikers te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="2d01c-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="2d01c-126">Aanmelden bij Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2d01c-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="2d01c-127">Ga in doelgroepinzichten naar **Beheer** > **Machtigingen**.</span><span class="sxs-lookup"><span data-stu-id="2d01c-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="2d01c-128">Schakel het selectievakje in voor de gebruiker die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="2d01c-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="2d01c-129">Selecteer **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="2d01c-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2d01c-130">![AVG-verwijderingsverzoeken voor gebruikersgegevens beheren](media/gdpr-permissions.png "AVG-verwijderingsverzoeken voor gebruikersgegevens afhandelen")</span><span class="sxs-lookup"><span data-stu-id="2d01c-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="2d01c-131">Reageren op exportverzoeken door betrokkenen in het kader van de AVG</span><span class="sxs-lookup"><span data-stu-id="2d01c-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="2d01c-132">Als onderdeel van ons streven om met u samen te werken op uw reis naar naleving van de Algemene verordening gegevensbescherming (AVG), hebben we documentatie ontwikkeld om u te helpen voorbereiden.</span><span class="sxs-lookup"><span data-stu-id="2d01c-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="2d01c-133">Deze documentatie beschrijft de stappen die u vandaag kunt nemen om AVG-naleving te ondersteunen wanneer u doelgroepinzichten gebruikt.</span><span class="sxs-lookup"><span data-stu-id="2d01c-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="2d01c-134">Export- en weergaveverzoeken beheren</span><span class="sxs-lookup"><span data-stu-id="2d01c-134">Manage export and view requests</span></span>

<span data-ttu-id="2d01c-135">Door het recht op gegevensoverdraagbaarheid mogen betrokkenen een kopie van hun persoonlijke gegevens in elektronische indeling (een "gestructureerde, algemeen gebruikte, machineleesbare en interoperabele indeling") aanvragen die naar een andere gegevensbeheerder kan worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="2d01c-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="2d01c-136">Klantgegevens exporteren (tenantbeheerder)</span><span class="sxs-lookup"><span data-stu-id="2d01c-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="2d01c-137">Een tenantbeheerder kan deze stappen volgen om gegevens te exporteren:</span><span class="sxs-lookup"><span data-stu-id="2d01c-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="2d01c-138">Verzend een e-mail naar D365CI@microsoft.com met het e-mailadres van de klant in de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="2d01c-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="2d01c-139">Het Customer Insights-team verzendt een e-mail naar het geregistreerde e-mailadres van de tenantbeheerder waarin wordt gevraagd om bevestiging voor het exporteren van gegevens.</span><span class="sxs-lookup"><span data-stu-id="2d01c-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="2d01c-140">Erken de bevestiging om de gegevens voor de gevraagde klant te exporteren.</span><span class="sxs-lookup"><span data-stu-id="2d01c-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="2d01c-141">Ontvang de geëxporteerde gegevens via het e-mailadres van de tenantbeheerder.</span><span class="sxs-lookup"><span data-stu-id="2d01c-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="2d01c-142">Gebruikersgegevens exporteren (tenantbeheerder)</span><span class="sxs-lookup"><span data-stu-id="2d01c-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="2d01c-143">Verzend een e-mail naar D365CI@microsoft.com met het e-mailadres van de gebruiker in de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="2d01c-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="2d01c-144">Het Customer Insights-team verzendt een e-mail naar het geregistreerde e-mailadres van de tenantbeheerder waarin wordt gevraagd om bevestiging voor het exporteren van gegevens.</span><span class="sxs-lookup"><span data-stu-id="2d01c-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="2d01c-145">Erken de bevestiging om de gegevens voor de gevraagde gebruiker te exporteren.</span><span class="sxs-lookup"><span data-stu-id="2d01c-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="2d01c-146">Ontvang de geëxporteerde gegevens via het e-mailadres van de tenantbeheerder.</span><span class="sxs-lookup"><span data-stu-id="2d01c-146">Receive the exported data through the tenant admin email address.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]