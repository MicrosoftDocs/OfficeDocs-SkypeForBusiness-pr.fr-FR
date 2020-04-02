---
title: Créer une application de portail intranet d’équipe à partir d’une page ou d’un site SharePoint Online
author: LanaChin
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: Prenez un site ou une page SharePoint Online existant et créez un onglet statique autonome qui peut être utilisé comme portail intranet pour votre organisation.
localization_priority: Normal
ms.openlocfilehash: 0215a2e1f79627f55bc14c00a099b25d2859b6f9
ms.sourcegitcommit: f0f2fa999c1ca4a1118377c7938a247f79217609
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "43106631"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a><span data-ttu-id="13ad6-103">Créer une application de portail intranet d’équipe à partir d’une page ou d’un site SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="13ad6-103">Create a Teams 'Intranet Portal app' from a SharePoint Online site or page</span></span>

<span data-ttu-id="13ad6-104">Suivez les étapes décrites dans cet article pour créer une application autonome et statique dans une équipe qui pointe vers le site intranet de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="13ad6-104">Use the steps in this article to create a standalone and static app inside of Teams that links to the intranet site for your org.</span></span>

<span data-ttu-id="13ad6-105">Une *application personnelle teams* de votre site intranet SharePoint est créée et s’affiche sous la forme d’un onglet à l’intérieur de teams.</span><span class="sxs-lookup"><span data-stu-id="13ad6-105">A *Teams Personal App* of your SharePoint intranet site is created, and will appear as a tab inside of Teams.</span></span> <span data-ttu-id="13ad6-106">Cet onglet peut contenir des informations importantes pour tous les utilisateurs de votre équipe.</span><span class="sxs-lookup"><span data-stu-id="13ad6-106">This tab can contain information important to all your Teams users.</span></span> <span data-ttu-id="13ad6-107">C’est un moyen rapide et pratique pour les utilisateurs de teams d’accéder aux mises à jour, cliquez sur un onglet.</span><span class="sxs-lookup"><span data-stu-id="13ad6-107">It is a quick and convenient way for Teams users to access updates just a tab click away.</span></span>

<span data-ttu-id="13ad6-108">Sachez que le processus présenté **doit utiliser** un site ou une page SharePoint *moderne* pour fonctionner.</span><span class="sxs-lookup"><span data-stu-id="13ad6-108">Be aware that the process shown **must use** a *modern* SharePoint site or page to work.</span></span> <span data-ttu-id="13ad6-109">Ce processus n’est pas disponible pour les pages ou sites *classiques* .</span><span class="sxs-lookup"><span data-stu-id="13ad6-109">This process is not available for *classical* sites or pages.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="13ad6-110">Assurez-vous que le chargement hors Windows Store des applications teams est activé pour votre client.</span><span class="sxs-lookup"><span data-stu-id="13ad6-110">Make certain that side-loading of Teams apps is enabled for your tenant.</span></span> <span data-ttu-id="13ad6-111">En fonction de l’endroit où vous vous trouvez dans le processus de migration du portail d’administration Teams, vous devrez peut-être l’activer sous équipes > administrateur, ou sous paramètres de > d’administration > services et compléments > les applications Microsoft teams > applications > applications externes, dans la version précédente du portail.</span><span class="sxs-lookup"><span data-stu-id="13ad6-111">Depending on where you are in the migration process of the Teams Admin portal, you might need to enable it either under Teams > Admin, or under Admin > Settings > Services and Add-ins > Microsoft Teams > Apps > External Apps, in the previous version of the portal!</span></span> 

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a><span data-ttu-id="13ad6-112">Utiliser app Studio pour créer votre application SharePoint Online autonome</span><span class="sxs-lookup"><span data-stu-id="13ad6-112">Use App Studio to create your standalone SharePoint Online app</span></span>
<span data-ttu-id="13ad6-113">Avant de commencer :</span><span class="sxs-lookup"><span data-stu-id="13ad6-113">''' Before you begin:</span></span>
1. <span data-ttu-id="13ad6-114">Vous devez connaître l’URL d’une communication moderne SharePoint Online ou d’un site d’équipe ou d’une page.</span><span class="sxs-lookup"><span data-stu-id="13ad6-114">You'll need to know the URL of a SharePoint Online modern Communication or Team site, or page.</span></span>
    - <span data-ttu-id="13ad6-115">Les chemins d’accès de ces sites seront toujours */équipes* ou */sites/* .</span><span class="sxs-lookup"><span data-stu-id="13ad6-115">These sites will always have either */teams/* or */sites/* in their paths.</span></span>

2. <span data-ttu-id="13ad6-116">Vous devez connaître le sous-domaine de votre client, qui sera utilisé dans l’espace réservé **{{subdomain}}**.</span><span class="sxs-lookup"><span data-stu-id="13ad6-116">You'll need to know your tenant's subdomain, which will be used in the placeholder **{{subdomain}}**.</span></span>

3. <span data-ttu-id="13ad6-117">Cet article utilise l’espace réservé **{{SiteUrl}}** pour vous en êtes l' *URL* du site ou de la page que vous avez choisi.</span><span class="sxs-lookup"><span data-stu-id="13ad6-117">This article will use **{{siteUrl}}** placeholder for your the *URL* of the site or page you chose.</span></span>
    - <span data-ttu-id="13ad6-118">Exemples d' *URL*: https://contoso.sharepoint.com/teams/Contoso *ou*   https://contoso.sharepoint.com/sites/Contoso</span><span class="sxs-lookup"><span data-stu-id="13ad6-118">Example *URLs*:   https://contoso.sharepoint.com/teams/Contoso   *or* https://contoso.sharepoint.com/sites/Contoso</span></span> 
4. <span data-ttu-id="13ad6-119">Par ailleurs, **{{sitePath}}** sera utilisé pour indiquer le *chemin d’accès* de l’URL (par exemple:/teams/Contoso).</span><span class="sxs-lookup"><span data-stu-id="13ad6-119">Also, **{{sitePath}}** will be used to denote the *path* of the URL (ex: /teams/Contoso).</span></span>
    - <span data-ttu-id="13ad6-120">Exemples de *chemins*:/teams/Contoso *ou* /sites/contoso</span><span class="sxs-lookup"><span data-stu-id="13ad6-120">Example *paths*:   /teams/Contoso   *or* /sites/Contoso</span></span> 

<span data-ttu-id="13ad6-121">Commencez par suivre les étapes ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="13ad6-121">Begin by following the steps below:</span></span>

1. <span data-ttu-id="13ad6-122">Accédez au magasin d’équipes.</span><span class="sxs-lookup"><span data-stu-id="13ad6-122">Go to the Teams Store.</span></span>

2. <span data-ttu-id="13ad6-123">Installez ou ouvrez App Studio.</span><span class="sxs-lookup"><span data-stu-id="13ad6-123">Install or open App Studio.</span></span>

3. <span data-ttu-id="13ad6-124">Cliquez sur **ouvrir**, en regard de l’option application.</span><span class="sxs-lookup"><span data-stu-id="13ad6-124">Click **Open**, next to the App option.</span></span>

4. <span data-ttu-id="13ad6-125">Avec App studio ouvert, cliquez sur **éditeur de manifeste**.</span><span class="sxs-lookup"><span data-stu-id="13ad6-125">With App Studio open, click on **Manifest Editor**.</span></span>

5. <span data-ttu-id="13ad6-126">**Créer une nouvelle application**.</span><span class="sxs-lookup"><span data-stu-id="13ad6-126">**Create a new app**.</span></span>

6. <span data-ttu-id="13ad6-127">Renseignez les **Détails**de l’application.</span><span class="sxs-lookup"><span data-stu-id="13ad6-127">Fill in all **App Details**.</span></span>

7. <span data-ttu-id="13ad6-128">Cliquez sur les **onglets** sous capacités.</span><span class="sxs-lookup"><span data-stu-id="13ad6-128">Click on **Tabs** under Capabilities.</span></span>

8. <span data-ttu-id="13ad6-129">Dans l’onglet personnel, cliquez sur **Ajouter** .</span><span class="sxs-lookup"><span data-stu-id="13ad6-129">Click **Add** under Personal Tab.</span></span>

9. <span data-ttu-id="13ad6-130">Entrez le **nom** et choisissez **un nouvel ID d’entité unique**.</span><span class="sxs-lookup"><span data-stu-id="13ad6-130">Fill in the **Name** and choose **a new unique Entity ID**.</span></span>

10. <span data-ttu-id="13ad6-131">Entrez l' **URL du site Web contentURL et**.</span><span class="sxs-lookup"><span data-stu-id="13ad6-131">Fill in the **contentURL and Website URL**.</span></span> 

- <span data-ttu-id="13ad6-132">**contentUrl**: {{SiteUrl}}/_layouts/15/teamslogon.aspx ? SPFX = true&dest = {{sitePath}}</span><span class="sxs-lookup"><span data-stu-id="13ad6-132">**contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}</span></span>  
- <span data-ttu-id="13ad6-133">**web’iteUrl**: {{SiteUrl}} ' 'exemple **contentURL**:https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub</span><span class="sxs-lookup"><span data-stu-id="13ad6-133">**web'iteUrl**: {{siteUrl}} ''   Example **contentURL**: https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub</span></span> 

11. <span data-ttu-id="13ad6-134">Accédez à **Domains et Permissi’ns**.</span><span class="sxs-lookup"><span data-stu-id="13ad6-134">Navigate to **Domains and Permissi'ns**.</span></span> <span data-ttu-id="13ad6-135">Assurez-vous que la section domaines valides contient votre nom de domaine SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="13ad6-135">Make sure the valid domains section contains your SharePoint online domain name.</span></span>
<span data-ttu-id="13ad6-136">' 'Exemple : contoso.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="13ad6-136">'' Example: contoso.sharepoint.com</span></span>

12. <span data-ttu-id="13ad6-137">Ajoutez les propriétés **d’authentification unique suivantes de** l’application Web à l’aide de' 'exemple : ' ' ' 'ID de l' **application AAD**: URL de la **ressource**00000003-0000-0ff1-CE00-000000000000 : {{subdomain} ![}. SharePoint. com' ' 'Web App unique, avec ID et URL](media/personal-app.png)</span><span class="sxs-lookup"><span data-stu-id="13ad6-137">Add the following web app **single sign-on** properties:  ''  Example:''''  **AAD application ID**: 00000003-0000-0ff1-ce00-000000000000  **Resource Url**: {{subdomain}}.sharepoint.com' '' ![Web app single sign-on, with ID and URL.](media/personal-app.png)</span></span>

13. <span data-ttu-id="13ad6-138">**Enregistrez** ces propriétés, puis naviguez vers le **test et la distribution**.</span><span class="sxs-lookup"><span data-stu-id="13ad6-138">**Save** these properties and then navigate to **Test and distribute**.</span></span> 

14. <span data-ttu-id="13ad6-139">Installez l’application pour tester l’application personnellement.</span><span class="sxs-lookup"><span data-stu-id="13ad6-139">Install the app to test the application personally.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="13ad6-140">Si vous n’utilisez pas le logiciel teams Studio, vous devez. zip du manifeste. Fichier JSON que vous venez de créer, accédez au magasin d’applications dans Microsoft Teams, puis cliquez sur Télécharger un lien vers une **application personnalisée** (en bas à droite de l’App Store).</span><span class="sxs-lookup"><span data-stu-id="13ad6-140">If you aren't using Teams App Studio, you will have to .zip the manifest.JSON file you just created, navigate to the App Store in Teams, and click  **upload custom app** link (at the bottom right of the App Store).</span></span> <span data-ttu-id="13ad6-141">Cela vous permettra d’accéder à l’application.</span><span class="sxs-lookup"><span data-stu-id="13ad6-141">This will make the app available to you.</span></span>

15. <span data-ttu-id="13ad6-142">L’application est désormais disponible sous la forme d’un onglet statique que vous pouvez charger et afficher dans Teams.</span><span class="sxs-lookup"><span data-stu-id="13ad6-142">Now the app is available as a static tab for you to load and view in Teams.</span></span>

## <a name="test-and-view-your-new-static-tab"></a><span data-ttu-id="13ad6-143">Tester et afficher votre nouvel onglet statique</span><span class="sxs-lookup"><span data-stu-id="13ad6-143">Test and view your new static tab</span></span>

<span data-ttu-id="13ad6-144">Pour afficher l’onglet nouveau sur le bureau Teams, accédez aux points de suspension (**...**) sur le côté gauche de la barre de l’application.</span><span class="sxs-lookup"><span data-stu-id="13ad6-144">To view the new tab on the Teams desktop, navigate to the ellipses (**…**) in the left-hand side of your app bar.</span></span> <span data-ttu-id="13ad6-145">Recherchez votre nouvelle application, chargez-la et testez-la dans Teams.</span><span class="sxs-lookup"><span data-stu-id="13ad6-145">Find your new app, load it, and test your standalone application in Teams.</span></span>

<span data-ttu-id="13ad6-146">Si vous souhaitez que la nouvelle application soit disponible dans le menu de gauche, vous devez utiliser un paramètre de stratégie d’application pour cela.</span><span class="sxs-lookup"><span data-stu-id="13ad6-146">If you want to make the new app available in the left menu at a higher position, you must use an app policy setting for this.</span></span> <span data-ttu-id="13ad6-147">Ce paramètre est disponible dans la section Administration de l’équipe > stratégie de l’application > ajouter une application épinglée.</span><span class="sxs-lookup"><span data-stu-id="13ad6-147">This setting can be found under the Team admin section > app policy > add a pinned application.</span></span> <span data-ttu-id="13ad6-148">Lorsque vous affectez la stratégie à un utilisateur à des fins de test, cette modification est affichée plus de 24 heures.</span><span class="sxs-lookup"><span data-stu-id="13ad6-148">When you assign the policy to a user for testing, the change will appear 24 hours later.</span></span> <span data-ttu-id="13ad6-149">Dans cet esprit, nous vous conseillons de décider de l’endroit où l’application doit apparaître pour vous permettre d’éviter des retards.</span><span class="sxs-lookup"><span data-stu-id="13ad6-149">With this in mind, please decide where the app should appear at your earliest convenience to help avoid delays.</span></span>

<span data-ttu-id="13ad6-150">Pour afficher et tester la nouvelle application sur un appareil mobile, ouvrez le tiroir de l’application en appuyant sur**^** le Chevron () situé au-dessus de la barre d’onglets en bas de votre écran.</span><span class="sxs-lookup"><span data-stu-id="13ad6-150">To view and test the new app on a mobile device, open the app drawer by tapping on the chevron (**^**) above the tab bar near the bottom of your screen.</span></span> <span data-ttu-id="13ad6-151">Recherchez votre application et accédez-y sur votre appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="13ad6-151">Find your app and navigate to it on your mobile device.</span></span>
        
> [!CAUTION]
> <span data-ttu-id="13ad6-152">La prise en charge des appareils mobiles est actuellement dans la version préliminaire du développeur.</span><span class="sxs-lookup"><span data-stu-id="13ad6-152">Mobile support is currently in Developer Preview.</span></span> <span data-ttu-id="13ad6-153">Pour activer l’aperçu des développeurs, accédez à paramètres > à propos de et activez le mode aperçu des développeurs.</span><span class="sxs-lookup"><span data-stu-id="13ad6-153">To enable Developer Preview, navigate to Settings > About and then enable Developer Preview mode.</span></span>

## <a name="a-sample-manifestjson-file"></a><span data-ttu-id="13ad6-154">Exemple de fichier manifest. JSON</span><span class="sxs-lookup"><span data-stu-id="13ad6-154">A Sample Manifest.JSON file</span></span>

<span data-ttu-id="13ad6-155">Le fichier JSO que vous générez ressemble à ce qui suit.</span><span class="sxs-lookup"><span data-stu-id="13ad6-155">The JSO        file you generate will look something like the one below.</span></span>

```JSON'
{ 

    "$schema": "https://developer.microsoft.com/en-us/json-schemas/teams/v1.5/MicrosoftTeams.schema.json", 

    "manifestVersion": "1.5", 

    "version": "1.0.0", 

    "id": "33ebded3-931c-4333-b0c5-b51dd8738873", 

    "packageName": "com.contoso.teams.devapp", 

    "developer": { 

        "name": "Contoso", ''

        "websiteUrl": "https://www.contoso.com", 

        "privacyUrl": "https://www.contoso.com/privacy", 

        "termsOfUseUrl": "https://www.contoso.com/terms" 

    }, 

    "icons": { 

        "color": "color.png", 

        "outline": "outline.png" 

    }, 

    "name": { 

        "short": "Contoso Intranet", '

        "full": "Intranet Portal for Contoso" 

    },                     
                        
    "des    ription": {                 

        "short": "Intranet portal for Contoso", 

        "full": "This app is to demonstrate the capabilities of hosting a SharePoint communication and team site as a standalone app in Teams" 

    }, 

    "accentColor": "#FFFFFF", 
''
    "staticTabs": [ 

        { 
                                       
                     "       nti        Id":       "com    unicat    onSi    eTab", 
                                       
            "name": "Contoso Net", 

            "contentUrl": "https://contoso.sharepoint.com/sites/ContosoNet/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoNet/", 

            "websiteUrl": "https://contoso.sharepoint.com/sites/ContosoNet", 

            "scopes": [ 

                "personal" 

            ] 

        }, 

        { 

            "entityId": "teamSiteTab", 

            "name": "Team Contoso", 

            "contentUrl": "https://contoso.sharepoint.com/teams/TeamContoso/_layouts/15/teamslogon.aspx?SPFX=true&dest=/teams/TeamContoso/", 

            "websiteUrl": "https://contoso.sharepoint.com/teams/TeamContoso", 

            "scopes": [ 

                "personal" 

            ] 

        } 

    ], 

    "permissions": [ 

        "identity", 

        "messageTeamMembers" 

    ], 

    "validDomains": [ 

        "contoso.sharepoint.com" 

    ], 

    "webApplicationInfo": { 

        "id": "00000003-0000-0ff1-ce00-000000000000", 

        "resource": "https://contoso.sharepoint.com" 

    } 

}
```