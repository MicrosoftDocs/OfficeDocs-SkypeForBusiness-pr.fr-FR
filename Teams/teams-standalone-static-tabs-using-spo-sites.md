---
title: Créer une application de portail intranet Teams à partir d’un site ou d’une page SharePoint Online
author: LanaChin
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
ms.reviewer: vinbel
search.appverid: MET150
description: Prenez un site ou une page SharePoint Online et créez un onglet statique autonome pouvant être utilisé comme portail intranet pour votre organisation.
localization_priority: Priority
ms.openlocfilehash: 09ff3fd57eee23c5eec9dfac118b68938c1c9f36
ms.sourcegitcommit: a22a7b7e4bf556ee3e5e2e51c6f9f1c865a0724a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083164"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a><span data-ttu-id="f0ebb-103">Créer une application de portail intranet Teams à partir d’un site ou d’une page SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f0ebb-103">Create a Teams 'Intranet Portal app' from a SharePoint Online site or page</span></span>

<span data-ttu-id="f0ebb-104">Suivez les étapes décrites dans cet article pour créer une application autonome et statique à l’intérieur de Teams qui crée un lien vers le site intranet de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-104">Use the steps in this article to create a standalone and static app inside of Teams that links to the intranet site for your org.</span></span>

<span data-ttu-id="f0ebb-105">Une *application personnelle Teams* de votre site intranet SharePoint est créée et apparaît sous forme d’onglet dans Teams.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-105">A *Teams Personal App* of your SharePoint intranet site is created, and will appear as a tab inside of Teams.</span></span> <span data-ttu-id="f0ebb-106">Cet onglet peut contenir des informations importantes pour les utilisateurs de tous les membres de votre Teams.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-106">This tab can contain information important to all your Teams users.</span></span> <span data-ttu-id="f0ebb-107">Il s’agit d’un moyen rapide et commode pour les utilisateurs de Teams d'accéder aux mises à jour en un seul clic.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-107">It is a quick and convenient way for Teams users to access updates just a tab click away.</span></span>

<span data-ttu-id="f0ebb-108">N’oubliez pas que le processus présenté **doit utiliser** un site ou page *Moderne* SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-108">Be aware that the process shown **must use** a *modern* SharePoint site or page to work.</span></span> <span data-ttu-id="f0ebb-109">Ce processus n’est pas disponible pour les *sites ou pages* classiques.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-109">This process is not available for *classical* sites or pages.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f0ebb-110">Assurez-vous que le chargement latéral des applications Teams est activé pour votre locataire.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-110">Make certain that side-loading of Teams apps is enabled for your tenant.</span></span> <span data-ttu-id="f0ebb-111">Selon l’endroit où vous vous trouvez dans le processus de migration du portail d’administration Teams, vous devrez peut-être l’activer soit sous Teams > Administrateur, soit sous Paramètres > Administration > Services et compléments > Microsoft Teams > Applications > Applications externes, dans la version précédente du portail.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-111">Depending on where you are in the migration process of the Teams Admin portal, you might need to enable it either under Teams > Admin, or under Admin > Settings > Services and Add-ins > Microsoft Teams > Apps > External Apps, in the previous version of the portal!</span></span>

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a><span data-ttu-id="f0ebb-112">Utilisez l’application Studio pour créer votre application SharePoint Online autonome</span><span class="sxs-lookup"><span data-stu-id="f0ebb-112">Use App Studio to create your standalone SharePoint Online app</span></span>

<span data-ttu-id="f0ebb-113">Avant de commencer :</span><span class="sxs-lookup"><span data-stu-id="f0ebb-113">Before you begin:</span></span>

1. <span data-ttu-id="f0ebb-114">Vous devez connaître l'URL d'un site ou d'une page de communication ou d'équipe moderne SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-114">You'll need to know the URL of a SharePoint Online modern Communication or Team site, or page.</span></span>
    - <span data-ttu-id="f0ebb-115">Les chemins d’accès de ces sites sont toujours */teams/* ou */sites/*.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-115">These sites will always have either */teams/* or */sites/* in their paths.</span></span>

2. <span data-ttu-id="f0ebb-116">Vous devez connaître le sous-domaine de votre client, lequel sera utilisé dans l’espace réservé **{{subdomain}}**.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-116">You'll need to know your tenant's subdomain, which will be used in the placeholder **{{subdomain}}**.</span></span>

3. <span data-ttu-id="f0ebb-117">Cet article utilise l’espace réservé **{{siteUrl}}** pour l’*URL* du site ou de la page que vous avez choisi.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-117">This article will use **{{siteUrl}}** as a placeholder for the *URL* of the site or page you chose.</span></span>
    - <span data-ttu-id="f0ebb-118">Exemple *URL* : https://contoso.sharepoint.com/teams/Contoso   *ou* https://contoso.sharepoint.com/sites/Contoso</span><span class="sxs-lookup"><span data-stu-id="f0ebb-118">Example *URLs*:   https://contoso.sharepoint.com/teams/Contoso   *or* https://contoso.sharepoint.com/sites/Contoso</span></span>
4. <span data-ttu-id="f0ebb-119">De plus, **{{sitePath}}** sera utilisé pour indiquer le *chemin d’accès* de l’URL (par exemple : /teams/Contoso).</span><span class="sxs-lookup"><span data-stu-id="f0ebb-119">Also, **{{sitePath}}** will be used to denote the *path* of the URL (ex: /teams/Contoso).</span></span>
    - <span data-ttu-id="f0ebb-120">Exemples de *chemins d’accès* :  /teams/Contoso   *ou* /sites/Contoso</span><span class="sxs-lookup"><span data-stu-id="f0ebb-120">Example *paths*:   /teams/Contoso   *or* /sites/Contoso</span></span>

<span data-ttu-id="f0ebb-121">Commencez par suivre les étapes ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="f0ebb-121">Begin by following the steps below:</span></span>

1. <span data-ttu-id="f0ebb-122">Accédez au Store Teams.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-122">Go to the Teams Store.</span></span>

2. <span data-ttu-id="f0ebb-123">Installez ou ouvrez App Studio.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-123">Install or open App Studio.</span></span>

3. <span data-ttu-id="f0ebb-124">Cliquez sur **Ouvrir**, en regard de l’option App.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-124">Click **Open**, next to the App option.</span></span>

4. <span data-ttu-id="f0ebb-125">Avec App studio ouvert, cliquez sur **Éditeur de manifeste**.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-125">With App Studio open, click on **Manifest Editor**.</span></span>

5. <span data-ttu-id="f0ebb-126">**Créer une nouvelle application**.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-126">**Create a new app**.</span></span>

6. <span data-ttu-id="f0ebb-127">Renseignez tous les **Détails de l’application**.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-127">Fill in all **App Details**.</span></span>

7. <span data-ttu-id="f0ebb-128">Cliquez sur **Onglets** sous Fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-128">Click on **Tabs** under Capabilities.</span></span>

8. <span data-ttu-id="f0ebb-129">Cliquez sur **Ajouter** sous l’onglet Personnel.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-129">Click **Add** under Personal Tab.</span></span>

9. <span data-ttu-id="f0ebb-130">Entrez le **Nom** puis sélectionnez **une nouvelle ID d’entité unique**.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-130">Fill in the **Name** and choose **a new unique Entity ID**.</span></span>

10. <span data-ttu-id="f0ebb-131">Renseignez les**contentURL et URL du site web**.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-131">Fill in the **contentURL and Website URL**.</span></span>

- <span data-ttu-id="f0ebb-132">**contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}</span><span class="sxs-lookup"><span data-stu-id="f0ebb-132">**contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}</span></span>  
- <span data-ttu-id="f0ebb-133">**websiteUrl**: {{siteUrl}}</span><span class="sxs-lookup"><span data-stu-id="f0ebb-133">**websiteUrl**: {{siteUrl}}</span></span>

    <span data-ttu-id="f0ebb-134">Exemple **contentURL**: https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub</span><span class="sxs-lookup"><span data-stu-id="f0ebb-134">Example **contentURL**: https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub</span></span>

11. <span data-ttu-id="f0ebb-135">Accédez à la page **Domaines et autorisations**.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-135">Navigate to **Domains and Permissions**.</span></span> <span data-ttu-id="f0ebb-136">Assurez-vous que la section domaines valides contient votre nom de domaine SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-136">Make sure the valid domains section contains your SharePoint online domain name.</span></span>

    <span data-ttu-id="f0ebb-137">Exemple: contoso.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="f0ebb-137">Example: contoso.sharepoint.com</span></span>

12. <span data-ttu-id="f0ebb-138">Ajoutez les propriétés **Authentification unique** de l’application web suivante :</span><span class="sxs-lookup"><span data-stu-id="f0ebb-138">Add the following web app **single sign-on** properties:</span></span>

     <span data-ttu-id="f0ebb-139">Exemple :  **ID application AAD** : 00000003-0000-0ff1-ce00-000000000000  **URL de ressource** : {{subdomain}}.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="f0ebb-139">Example:  **AAD application ID**: 00000003-0000-0ff1-ce00-000000000000  **Resource Url**: {{subdomain}}.sharepoint.com</span></span>

    ![Authentification unique de l’application web avec ID et URL.](media/personal-app.png)

13. <span data-ttu-id="f0ebb-141">**Enregistrez** ces propriétés, puis accédez à **Tester et distribuer**.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-141">**Save** these properties and then navigate to **Test and distribute**.</span></span>

14. <span data-ttu-id="f0ebb-142">Installez l’application pour tester l’application personnellement.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-142">Install the app to test the application personally.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f0ebb-143">Si vous n'utilisez pas Teams App Studio, vous devrez compresser le fichier manifest.JSON que vous venez de créer, accédez à l’App Store dans Teams, puis cliquez sur le lien **télécharger l’application personnalisée** (en bas à droite de l’App Store).</span><span class="sxs-lookup"><span data-stu-id="f0ebb-143">If you aren't using Teams App Studio, you will have to .zip the manifest.JSON file you just created, navigate to the App Store in Teams, and click  **upload custom app** link (at the bottom right of the App Store).</span></span> <span data-ttu-id="f0ebb-144">L’application est alors disponible.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-144">This will make the app available to you.</span></span>

15. <span data-ttu-id="f0ebb-145">L’application est désormais disponible sous la forme d’un onglet statique que vous pouvez charger et afficher dans Teams.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-145">Now the app is available as a static tab for you to load and view in Teams.</span></span>

## <a name="test-and-view-your-new-static-tab"></a><span data-ttu-id="f0ebb-146">Tester et afficher votre nouvel onglet statique</span><span class="sxs-lookup"><span data-stu-id="f0ebb-146">Test and view your new static tab</span></span>

<span data-ttu-id="f0ebb-147">Pour afficher l’onglet nouveau sur le bureau Teams, accédez aux points de suspension (**...**) sur le côté gauche de la barre de l’application.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-147">To view the new tab on the Teams desktop, navigate to the ellipses (**…**) in the left-hand side of your app bar.</span></span> <span data-ttu-id="f0ebb-148">Trouvez votre nouvelle application, chargez-la et testez-la dans Teams.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-148">Find your new app, load it, and test your standalone application in Teams.</span></span>

<span data-ttu-id="f0ebb-149">Si vous souhaitez que la nouvelle application soit disponible dans le menu de gauche à une position supérieure, vous devez utiliser un paramètre de stratégie d’application.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-149">If you want to make the new app available in the left menu at a higher position, you must use an app policy setting for this.</span></span> <span data-ttu-id="f0ebb-150">Ce paramètre se trouve dans la section administrateur Teams > stratégie d’application > Ajouter une application épinglée.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-150">This setting can be found under the Team admin section > app policy > add a pinned application.</span></span> <span data-ttu-id="f0ebb-151">Lorsque vous attribuez la politique à un utilisateur pour le test, le changement apparaîtra quelques heures plus tard.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-151">When you assign the policy to a user for testing, the change will appear a few hours later.</span></span> <span data-ttu-id="f0ebb-152">À cet esprit, n’hésitez pas à choisir l’emplacement dans lequel l’application doit apparaître à votre guise pour éviter les retards.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-152">With this in mind, please decide where the app should appear at your earliest convenience to help avoid delays.</span></span>

<span data-ttu-id="f0ebb-153">Pour afficher et tester la nouvelle application sur un appareil mobile, ouvrez le tiroir de l’application en appuyant sur le chevron (**^**) au-dessus de la barre d’onglets située en bas de l’écran.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-153">To view and test the new app on a mobile device, open the app drawer by tapping on the chevron (**^**) above the tab bar near the bottom of your screen.</span></span> <span data-ttu-id="f0ebb-154">Recherchez votre application et accédez-y sur votre appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-154">Find your app and navigate to it on your mobile device.</span></span>

> [!CAUTION]
> <span data-ttu-id="f0ebb-155">La prise en charge des appareils mobiles est actuellement disponible dans Aperçu pour les développeurs.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-155">Mobile support is currently in Developer Preview.</span></span> <span data-ttu-id="f0ebb-156">Pour activer l’Aperçu pour les développeurs, accédez à Paramètres > À propos, puis activez le mode Aperçu pour les développeurs.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-156">To enable Developer Preview, navigate to Settings > About and then enable Developer Preview mode.</span></span>

## <a name="a-sample-manifestjson-file"></a><span data-ttu-id="f0ebb-157">Exemple de fichier Manifest.JSON</span><span class="sxs-lookup"><span data-stu-id="f0ebb-157">A Sample Manifest.JSON file</span></span>

<span data-ttu-id="f0ebb-158">Le fichier JSON que vous avez généré ressemble à celui ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="f0ebb-158">The JSON file you generate will look something like the one below.</span></span>

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
