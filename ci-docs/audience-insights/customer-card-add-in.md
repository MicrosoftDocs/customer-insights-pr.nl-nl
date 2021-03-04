---
title: De invoegtoepassing Klantkaart installeren en configureren
description: Installeer en configureer de invoegtoepassing Klantkaart voor Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a6d5b49380ed129cf147698a16f5f3f597bf7fbc
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268038"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="1a198-103">Invoegtoepassing Klantkaart (preview)</span><span class="sxs-lookup"><span data-stu-id="1a198-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="1a198-104">Krijg een compleet overzicht van uw klanten rechtstreeks in Dynamics 365-apps.</span><span class="sxs-lookup"><span data-stu-id="1a198-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="1a198-105">Bekijk demografische gegevens, inzichten en tijdlijnen van activiteiten met de invoegtoepassing Klantkaart.</span><span class="sxs-lookup"><span data-stu-id="1a198-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1a198-106">Vereisten</span><span class="sxs-lookup"><span data-stu-id="1a198-106">Prerequisites</span></span>

- <span data-ttu-id="1a198-107">Dynamics 365-app (zoals Verkoophub of Klantenservicehub), versie 9.0 en hoger met Unified Interface ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="1a198-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="1a198-108">Klantprofielen [opgenomen uit de Dynamics 365-app met Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="1a198-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="1a198-109">Gebruikers van de invoegtoepassing Klantenkaart moeten [toegevoegd zijn als gebruikers](permissions.md) in doelgroepinzichten.</span><span class="sxs-lookup"><span data-stu-id="1a198-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="1a198-110">[Geconfigureerde zoek- en filtermogelijkheden](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="1a198-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="1a198-111">Demografische controle: demografische velden, zoals leeftijd of gender, zijn beschikbaar in het geharmoniseerde klantprofiel.</span><span class="sxs-lookup"><span data-stu-id="1a198-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="1a198-112">Besturingselement voor verrijking: vereist dat actieve [verrijkingen](enrichment-hub.md) worden toegepast op klantprofielen.</span><span class="sxs-lookup"><span data-stu-id="1a198-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="1a198-113">Informatiecontrole: vereist gegevens die zijn gegenereerd met Azure Machine Learning ([Voorspellingen](predictions.md) of [Aangepaste modellen](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="1a198-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="1a198-114">Metingencontrole: vereist [geconfigureerde metingen](measures.md).</span><span class="sxs-lookup"><span data-stu-id="1a198-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="1a198-115">Tijdlijncontrole: vereist [geconfigureerde activiteiten](activities.md).</span><span class="sxs-lookup"><span data-stu-id="1a198-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="1a198-116">De invoegtoepassing Klantkaart installeren</span><span class="sxs-lookup"><span data-stu-id="1a198-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="1a198-117">De invoegtoepassing Klantkaart is een oplossing voor apps voor klantbetrokkenheid in Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="1a198-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="1a198-118">Als u de oplossing wilt installeren, gaat u naar AppSource en zoekt u naar **Dynamics-klantkaart**.</span><span class="sxs-lookup"><span data-stu-id="1a198-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="1a198-119">Selecteer de [invoegtoepassing Klantkaart in AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) en selecteer **Nu downloaden**.</span><span class="sxs-lookup"><span data-stu-id="1a198-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="1a198-120">Mogelijk moet u zich aanmelden met uw beheerdersreferenties voor de Dynamics 365-app om de oplossing te kunnen installeren.</span><span class="sxs-lookup"><span data-stu-id="1a198-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="1a198-121">Het kan enige tijd duren voordat de oplossing in uw omgeving is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="1a198-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="1a198-122">De invoegtoepassing Klantkaarten configureren</span><span class="sxs-lookup"><span data-stu-id="1a198-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="1a198-123">Ga als beheerder naar de sectie **Instellingen** in Dynamics 365 en selecteer **Oplossingen**.</span><span class="sxs-lookup"><span data-stu-id="1a198-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="1a198-124">Selecteer de koppeling **Weergavenaam** voor de oplossing **Dynamics 365 Customer Insights-invoegtoepassing KIantkaart (preview)**.</span><span class="sxs-lookup"><span data-stu-id="1a198-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1a198-125">![Weergavenaam selecteren](media/select-display-name.png "Weergavenaam selecteren")</span><span class="sxs-lookup"><span data-stu-id="1a198-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="1a198-126">Selecteer **Aanmelden** en voer de referenties in voor het beheerdersaccount dat u gebruikt om Customer Insights te configureren.</span><span class="sxs-lookup"><span data-stu-id="1a198-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1a198-127">Controleer of de pop-upblokkering van de browser het verificatievenster niet blokkeert wanneer u de knop **Aanmelden** selecteert.</span><span class="sxs-lookup"><span data-stu-id="1a198-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="1a198-128">Selecteer de omgeving waaruit u gegevens wilt ophalen.</span><span class="sxs-lookup"><span data-stu-id="1a198-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="1a198-129">Definieer welke velden worden toegewezen aan records in de Dynamics 365-app.</span><span class="sxs-lookup"><span data-stu-id="1a198-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="1a198-130">Om toe te wijzen aan een contactpersoon, selecteert u het veld in de entiteit Klant die overeenkomt met de id van uw contactpersoon.</span><span class="sxs-lookup"><span data-stu-id="1a198-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="1a198-131">Om toe te wijzen aan een account, selecteert u het veld in de entiteit Klant die overeenkomt met de id van uw account-entiteit.</span><span class="sxs-lookup"><span data-stu-id="1a198-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1a198-132">![Veld Contactpersoon-id](media/contact-id-field.png "Veld Contactpersoon-id")</span><span class="sxs-lookup"><span data-stu-id="1a198-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="1a198-133">Selecteer **Configuratie opslaan** om de instellingen op te slaan.</span><span class="sxs-lookup"><span data-stu-id="1a198-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="1a198-134">Vervolgens moet u beveiligingsrollen toewijzen in Dynamics 365, zodat gebruikers de klantkaart kunnen aanpassen en zien.</span><span class="sxs-lookup"><span data-stu-id="1a198-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="1a198-135">Ga in Dynamics 365 naar **Instellingen** > **Beveiliging** > **Gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="1a198-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="1a198-136">Selecteer de gebruikers om gebruikersrollen te bewerken en selecteer **Rollen beheren**.</span><span class="sxs-lookup"><span data-stu-id="1a198-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="1a198-137">Wijs de rol **'Aanpasser van Customer Insights-kaarten** toe aan gebruikers die de inhoud die op de kaart wordt weergegeven voor de hele organisatie aanpassen.</span><span class="sxs-lookup"><span data-stu-id="1a198-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="1a198-138">Besturingselementen van Klantenkaart aan formulieren toevoegen</span><span class="sxs-lookup"><span data-stu-id="1a198-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="1a198-139">Als u de besturingselementen voor Klantkaart aan uw formulier Contactpersoon wilt toevoegen, gaat u naar **Instellingen** > **Aanpassingen** in Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="1a198-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="1a198-140">Selecteer **Het systeem aanpassen**.</span><span class="sxs-lookup"><span data-stu-id="1a198-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="1a198-141">Blader naar de entiteit **Contactpersoon**, vouw deze uit en selecteer vervolgens **Formulieren**.</span><span class="sxs-lookup"><span data-stu-id="1a198-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="1a198-142">Selecteer het contactpersoonformulier waaraan u de besturingselementen voor Klantkaart wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="1a198-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1a198-143">![Contactpersoonformulier selecteren](media/contact-active-forms.png "Contactpersoonformulier selecteren")</span><span class="sxs-lookup"><span data-stu-id="1a198-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="1a198-144">Als u het demografische besturingselement wilt toevoegen, sleept u in de formuliereneditor een willekeurig veld vanuit de **Veldverkenner** naar de locatie waar u het demografische besturingselement wilt weergeven.</span><span class="sxs-lookup"><span data-stu-id="1a198-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="1a198-145">Selecteer het veld op het formulier dat u zojuist hebt toegevoegd en selecteer vervolgens **Eigenschappen wijzigen**.</span><span class="sxs-lookup"><span data-stu-id="1a198-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="1a198-146">Ga naar het tabblad **Besturingselementen** en selecteer **Besturingselement toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="1a198-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="1a198-147">Kies een van de beschikbare aangepaste bedieningselementen en selecteer **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="1a198-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="1a198-148">Schakel in het dialoogvenster **Veldeigenschappen** het selectievakje **Label in het formulier weergeven** uit.</span><span class="sxs-lookup"><span data-stu-id="1a198-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="1a198-149">Selecteer de optie **Web** voor het besturingselement.</span><span class="sxs-lookup"><span data-stu-id="1a198-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="1a198-150">Selecteer voor het besturingselement voor verrijking welk verrijkingstype u wilt weergeven door het veld **enrichmentType** te configureren.</span><span class="sxs-lookup"><span data-stu-id="1a198-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="1a198-151">Voeg een afzonderlijk verrijkingsbesturingselement toe voor elk verrijkingstype.</span><span class="sxs-lookup"><span data-stu-id="1a198-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="1a198-152">Selecteer **Opslaan** en **Publiceren** om het bijgewerkte contactpersoonformulier te publiceren.</span><span class="sxs-lookup"><span data-stu-id="1a198-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="1a198-153">Ga naar het gepubliceerde contactpersoonformulier.</span><span class="sxs-lookup"><span data-stu-id="1a198-153">Go to the published contact form.</span></span> <span data-ttu-id="1a198-154">U ziet nu het nieuw toegevoegde besturingselement.</span><span class="sxs-lookup"><span data-stu-id="1a198-154">You'll see the newly added control.</span></span> <span data-ttu-id="1a198-155">Mogelijk moet u zich aanmelden bij het eerste gebruik.</span><span class="sxs-lookup"><span data-stu-id="1a198-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="1a198-156">Als u wilt aanpassen wat u wilt weergeven op het aangepaste besturingselement, selecteert u de knop Bewerken in de rechterbovenhoek.</span><span class="sxs-lookup"><span data-stu-id="1a198-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="1a198-157">Invoegtoepassing Klantkaart upgraden</span><span class="sxs-lookup"><span data-stu-id="1a198-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="1a198-158">De invoegtoepassing Klantkaart wordt niet automatisch geüpgraded.</span><span class="sxs-lookup"><span data-stu-id="1a198-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="1a198-159">Om te upgraden naar de nieuwste versie, volgt u deze procedure in de Dynamics 365-app waarop de invoegtoepassing is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="1a198-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="1a198-160">Ga in de Dynamics 365-app naar **Instellingen** > **Aanpassing** en selecteer **Oplossingen**.</span><span class="sxs-lookup"><span data-stu-id="1a198-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="1a198-161">Zoek in de tabel met invoegtoepassingen naar **CustomerInsightsCustomerCard** en selecteer de rij.</span><span class="sxs-lookup"><span data-stu-id="1a198-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="1a198-162">Selecteer **Oplossingsupgrade toepassen** op de actiebalk.</span><span class="sxs-lookup"><span data-stu-id="1a198-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Upgrade de oplossing in het aanpassingsgebied van Dynamics 365-apps":::

1. <span data-ttu-id="1a198-164">Nadat u het upgradeproces hebt gestart, ziet u een laadindicator totdat de upgrade is voltooid.</span><span class="sxs-lookup"><span data-stu-id="1a198-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="1a198-165">Als er geen nieuwere versie is, geeft de upgrade een foutmelding weer.</span><span class="sxs-lookup"><span data-stu-id="1a198-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]