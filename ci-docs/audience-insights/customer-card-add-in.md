---
title: Invoegtoepassing Klantkaart voor Dynamics 365-apps
description: Geef gegevens van doelgroepinzichten weer in Dynamics 365-apps met deze invoegtoepassing.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059582"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="6b878-103">Invoegtoepassing Klantkaart (preview)</span><span class="sxs-lookup"><span data-stu-id="6b878-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="6b878-104">Krijg een compleet overzicht van uw klanten rechtstreeks in Dynamics 365-apps.</span><span class="sxs-lookup"><span data-stu-id="6b878-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="6b878-105">Met de invoegtoepassing Klantkaart geïnstalleerd in een ondersteunde Dynamics 365-app kunt u ervoor kiezen om demografische gegevens, inzichten en activiteitstijdlijnen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="6b878-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="6b878-106">Met de invoegtoepassing worden gegevens opgehaald uit Customer Insights zonder dat dit invloed heeft op de gegevens in de verbonden Dynamics 365-app.</span><span class="sxs-lookup"><span data-stu-id="6b878-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="6b878-107">Vereisten</span><span class="sxs-lookup"><span data-stu-id="6b878-107">Prerequisites</span></span>

- <span data-ttu-id="6b878-108">De invoegtoepassing werkt alleen met modelgestuurde Dynamics 365-apps, zoals Sales of Customer Service, versie 9.0 en hoger.</span><span class="sxs-lookup"><span data-stu-id="6b878-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="6b878-109">Voor toewijzing van uw Dynamics 365-gegevens aan de klantprofielen van doelgroepinzichten moeten ze [worden opgenomen vanuit de Dynamics 365-app met behulp van de Common Data Service-connector](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="6b878-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="6b878-110">Alle Dynamics 365-gebruikers van de invoegtoepassing Klantkaart moeten worden [toegevoegd als gebruikers](permissions.md) in doelgroepinzichten om de gegevens te zien.</span><span class="sxs-lookup"><span data-stu-id="6b878-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="6b878-111">[Geconfigureerde zoek- en filtermogelijkheden](search-filter-index.md) in doelgroepinzichten zijn vereist voor het opzoeken van gegevens.</span><span class="sxs-lookup"><span data-stu-id="6b878-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="6b878-112">Elk besturingselement van de invoegtoepassing is afhankelijk van specifieke gegevens in doelgroepinzichten:</span><span class="sxs-lookup"><span data-stu-id="6b878-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="6b878-113">Metingencontrole: vereist [geconfigureerde metingen](measures.md).</span><span class="sxs-lookup"><span data-stu-id="6b878-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="6b878-114">Informatiebeheer: vereist gegevens die zijn gegenereerd met [voorspellingen](predictions.md) of [aangepaste modellen](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="6b878-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="6b878-115">Demografische controle: demografische velden, zoals leeftijd of gender, zijn beschikbaar in het geharmoniseerde klantprofiel.</span><span class="sxs-lookup"><span data-stu-id="6b878-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="6b878-116">Besturingselement voor verrijking: vereist dat actieve [verrijkingen](enrichment-hub.md) worden toegepast op klantprofielen.</span><span class="sxs-lookup"><span data-stu-id="6b878-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="6b878-117">Tijdlijncontrole: vereist [geconfigureerde activiteiten](activities.md).</span><span class="sxs-lookup"><span data-stu-id="6b878-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="6b878-118">De invoegtoepassing Klantkaart installeren</span><span class="sxs-lookup"><span data-stu-id="6b878-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="6b878-119">De invoegtoepassing Klantkaart is een oplossing voor apps voor klantbetrokkenheid in Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="6b878-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="6b878-120">Als u de oplossing wilt installeren, gaat u naar AppSource en zoekt u naar **Dynamics-klantkaart**.</span><span class="sxs-lookup"><span data-stu-id="6b878-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="6b878-121">Selecteer de [invoegtoepassing Klantkaart in AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) en selecteer **Nu downloaden**.</span><span class="sxs-lookup"><span data-stu-id="6b878-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="6b878-122">Mogelijk moet u zich aanmelden met uw beheerdersreferenties voor de Dynamics 365-app om de oplossing te kunnen installeren.</span><span class="sxs-lookup"><span data-stu-id="6b878-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="6b878-123">Het kan enige tijd duren voordat de oplossing in uw omgeving is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="6b878-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="6b878-124">De invoegtoepassing Klantkaarten configureren</span><span class="sxs-lookup"><span data-stu-id="6b878-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="6b878-125">Ga als beheerder naar de sectie **Instellingen** in Dynamics 365 en selecteer **Oplossingen**.</span><span class="sxs-lookup"><span data-stu-id="6b878-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="6b878-126">Selecteer de koppeling **Weergavenaam** voor de oplossing **Dynamics 365 Customer Insights-invoegtoepassing KIantkaart (preview)**.</span><span class="sxs-lookup"><span data-stu-id="6b878-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6b878-127">![Weergavenaam selecteren](media/select-display-name.png "Weergavenaam selecteren")</span><span class="sxs-lookup"><span data-stu-id="6b878-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="6b878-128">Selecteer **Aanmelden** en voer de referenties in voor het beheerdersaccount dat u gebruikt om Customer Insights te configureren.</span><span class="sxs-lookup"><span data-stu-id="6b878-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6b878-129">Controleer of de pop-upblokkering van de browser het verificatievenster niet blokkeert wanneer u de knop **Aanmelden** selecteert.</span><span class="sxs-lookup"><span data-stu-id="6b878-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="6b878-130">Selecteer de Customer Insights-omgeving waaruit u gegevens wilt ophalen.</span><span class="sxs-lookup"><span data-stu-id="6b878-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="6b878-131">Definieer de veldtoewijzing aan records in de Dynamics 365-app.</span><span class="sxs-lookup"><span data-stu-id="6b878-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="6b878-132">Afhankelijk van uw gegevens in Customer Insights kunt u ervoor kiezen om de volgende opties toe te wijzen:</span><span class="sxs-lookup"><span data-stu-id="6b878-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="6b878-133">Om toe te wijzen aan een contactpersoon, selecteert u het veld in de entiteit Klant die overeenkomt met de id van uw contactpersoon.</span><span class="sxs-lookup"><span data-stu-id="6b878-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="6b878-134">Om toe te wijzen aan een account, selecteert u het veld in de entiteit Klant die overeenkomt met de id van uw account-entiteit.</span><span class="sxs-lookup"><span data-stu-id="6b878-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6b878-135">![Veld Contactpersoon-id](media/contact-id-field.png "Veld Contactpersoon-id")</span><span class="sxs-lookup"><span data-stu-id="6b878-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="6b878-136">Selecteer **Configuratie opslaan** om de instellingen op te slaan.</span><span class="sxs-lookup"><span data-stu-id="6b878-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="6b878-137">Vervolgens moet u beveiligingsrollen toewijzen in Dynamics 365, zodat gebruikers de klantkaart kunnen aanpassen en zien.</span><span class="sxs-lookup"><span data-stu-id="6b878-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="6b878-138">Ga in Dynamics 365 naar **Instellingen** > **Beveiliging** > **Gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="6b878-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="6b878-139">Selecteer de gebruikers om gebruikersrollen te bewerken en selecteer **Rollen beheren**.</span><span class="sxs-lookup"><span data-stu-id="6b878-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="6b878-140">Wijs de rol **'Aanpasser van Customer Insights-kaarten** toe aan gebruikers die de inhoud die op de kaart wordt weergegeven voor de hele organisatie aanpassen.</span><span class="sxs-lookup"><span data-stu-id="6b878-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="6b878-141">Besturingselementen van Klantenkaart aan formulieren toevoegen</span><span class="sxs-lookup"><span data-stu-id="6b878-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="6b878-142">Als u de besturingselementen voor Klantkaart aan uw formulier Contactpersoon wilt toevoegen, gaat u naar **Instellingen** > **Aanpassingen** in Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="6b878-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="6b878-143">Selecteer **Het systeem aanpassen**.</span><span class="sxs-lookup"><span data-stu-id="6b878-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="6b878-144">Blader naar de entiteit **Contactpersoon**, vouw deze uit en selecteer vervolgens **Formulieren**.</span><span class="sxs-lookup"><span data-stu-id="6b878-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="6b878-145">Selecteer het contactpersoonformulier waaraan u de besturingselementen voor Klantkaart wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="6b878-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6b878-146">![Contactpersoonformulier selecteren](media/contact-active-forms.png "Contactpersoonformulier selecteren")</span><span class="sxs-lookup"><span data-stu-id="6b878-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="6b878-147">Als u het demografische besturingselement wilt toevoegen, sleept u in de formuliereneditor een willekeurig veld vanuit de **Veldverkenner** naar de locatie waar u het demografische besturingselement wilt weergeven.</span><span class="sxs-lookup"><span data-stu-id="6b878-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="6b878-148">Selecteer het veld op het formulier dat u zojuist hebt toegevoegd en selecteer vervolgens **Eigenschappen wijzigen**.</span><span class="sxs-lookup"><span data-stu-id="6b878-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="6b878-149">Ga naar het tabblad **Besturingselementen** en selecteer **Besturingselement toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="6b878-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="6b878-150">Kies een van de beschikbare aangepaste bedieningselementen en selecteer **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="6b878-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="6b878-151">Schakel in het dialoogvenster **Veldeigenschappen** het selectievakje **Label in het formulier weergeven** uit.</span><span class="sxs-lookup"><span data-stu-id="6b878-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="6b878-152">Selecteer de optie **Web** voor het besturingselement.</span><span class="sxs-lookup"><span data-stu-id="6b878-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="6b878-153">Selecteer voor het besturingselement voor verrijking welk verrijkingstype u wilt weergeven door het veld **enrichmentType** te configureren.</span><span class="sxs-lookup"><span data-stu-id="6b878-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="6b878-154">Voeg een afzonderlijk verrijkingsbesturingselement toe voor elk verrijkingstype.</span><span class="sxs-lookup"><span data-stu-id="6b878-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="6b878-155">Selecteer **Opslaan** en **Publiceren** om het bijgewerkte contactpersoonformulier te publiceren.</span><span class="sxs-lookup"><span data-stu-id="6b878-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="6b878-156">Ga naar het gepubliceerde contactpersoonformulier.</span><span class="sxs-lookup"><span data-stu-id="6b878-156">Go to the published contact form.</span></span> <span data-ttu-id="6b878-157">U ziet nu het nieuw toegevoegde besturingselement.</span><span class="sxs-lookup"><span data-stu-id="6b878-157">You'll see the newly added control.</span></span> <span data-ttu-id="6b878-158">Mogelijk moet u zich aanmelden bij het eerste gebruik.</span><span class="sxs-lookup"><span data-stu-id="6b878-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="6b878-159">Als u wilt aanpassen wat u wilt weergeven op het aangepaste besturingselement, selecteert u de knop Bewerken in de rechterbovenhoek.</span><span class="sxs-lookup"><span data-stu-id="6b878-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="6b878-160">Invoegtoepassing Klantkaart upgraden</span><span class="sxs-lookup"><span data-stu-id="6b878-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="6b878-161">De invoegtoepassing Klantkaart wordt niet automatisch geüpgraded.</span><span class="sxs-lookup"><span data-stu-id="6b878-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="6b878-162">Om te upgraden naar de nieuwste versie, volgt u deze procedure in de Dynamics 365-app waarop de invoegtoepassing is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="6b878-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="6b878-163">Ga in de Dynamics 365-app naar **Instellingen** > **Aanpassing** en selecteer **Oplossingen**.</span><span class="sxs-lookup"><span data-stu-id="6b878-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="6b878-164">Zoek in de tabel met invoegtoepassingen naar **CustomerInsightsCustomerCard** en selecteer de rij.</span><span class="sxs-lookup"><span data-stu-id="6b878-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="6b878-165">Selecteer **Oplossingsupgrade toepassen** op de actiebalk.</span><span class="sxs-lookup"><span data-stu-id="6b878-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Upgrade de oplossing in het aanpassingsgebied van Dynamics 365-apps":::

1. <span data-ttu-id="6b878-167">Nadat u het upgradeproces hebt gestart, ziet u een laadindicator totdat de upgrade is voltooid.</span><span class="sxs-lookup"><span data-stu-id="6b878-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="6b878-168">Als er geen nieuwere versie is, geeft de upgrade een foutmelding weer.</span><span class="sxs-lookup"><span data-stu-id="6b878-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
