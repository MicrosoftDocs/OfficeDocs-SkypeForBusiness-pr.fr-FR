---
title: Créer une application de portail intranet Teams à partir d’un site ou d’une page SharePoint Online
author: cichur
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
description: Prenez un site ou une page SharePoint Online et créez un onglet personnel autonome pouvant être utilisé comme portail intranet pour votre organisation.
localization_priority: Priority
ms.openlocfilehash: 7989478bf7fb81abdbd6ad9e553845302953c8cd
ms.sourcegitcommit: 5473b9fcd2bfe8adeb05a4a8d23e4350c7970fb6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49937506"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a><span data-ttu-id="ddca7-103">Créer une application de portail intranet Teams à partir d’un site ou d’une page SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ddca7-103">Create a Teams 'Intranet Portal app' from a SharePoint Online site or page</span></span>

<span data-ttu-id="ddca7-104">Suivez les étapes décrites dans cet article pour créer une application autonome et statique à l’intérieur de Teams qui crée un lien vers le site intranet de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="ddca7-104">Use the steps in this article to create a standalone and static app inside of Teams that links to the intranet site for your org.</span></span>

<span data-ttu-id="ddca7-105">Une *application personnelle Teams* de votre site intranet SharePoint est créée et apparaît sous forme d’onglet dans Teams.</span><span class="sxs-lookup"><span data-stu-id="ddca7-105">A *Teams Personal App* of your SharePoint intranet site is created, and will appear as a tab inside of Teams.</span></span> <span data-ttu-id="ddca7-106">Cet onglet peut contenir des informations importantes pour les utilisateurs de tous les membres de votre Teams.</span><span class="sxs-lookup"><span data-stu-id="ddca7-106">This tab can contain information important to all your Teams users.</span></span> <span data-ttu-id="ddca7-107">Il s’agit d’un moyen rapide et commode pour les utilisateurs de Teams d'accéder aux mises à jour en un seul clic.</span><span class="sxs-lookup"><span data-stu-id="ddca7-107">It is a quick and convenient way for Teams users to access updates just a tab click away.</span></span>

<span data-ttu-id="ddca7-108">N’oubliez pas que le processus présenté **doit utiliser** un site ou page *Moderne* SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ddca7-108">Be aware that the process shown **must use** a *modern* SharePoint site or page to work.</span></span> <span data-ttu-id="ddca7-109">Ce processus n’est pas disponible pour les *sites ou pages* classiques.</span><span class="sxs-lookup"><span data-stu-id="ddca7-109">This process is not available for *classical* sites or pages.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ddca7-110">Assurez-vous que le chargement latéral des applications Teams est activé pour votre locataire.</span><span class="sxs-lookup"><span data-stu-id="ddca7-110">Make certain that side-loading of Teams apps is enabled for your tenant.</span></span> <span data-ttu-id="ddca7-111">Selon l’endroit où vous vous trouvez dans le processus de migration du portail d’administration Teams, vous devrez peut-être l’activer soit sous Teams > Administrateur, soit sous Paramètres > Administration > Services et compléments > Microsoft Teams > Applications > Applications externes, dans la version précédente du portail.</span><span class="sxs-lookup"><span data-stu-id="ddca7-111">Depending on where you are in the migration process of the Teams Admin portal, you might need to enable it either under Teams > Admin, or under Admin > Settings > Services and Add-ins > Microsoft Teams > Apps > External Apps, in the previous version of the portal!</span></span>

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a><span data-ttu-id="ddca7-112">Utilisez l’application Studio pour créer votre application SharePoint Online autonome</span><span class="sxs-lookup"><span data-stu-id="ddca7-112">Use App Studio to create your standalone SharePoint Online app</span></span>

<span data-ttu-id="ddca7-113">Avant de commencer :</span><span class="sxs-lookup"><span data-stu-id="ddca7-113">Before you begin:</span></span>

1. <span data-ttu-id="ddca7-114">Vous devez connaître l'URL d'un site ou d'une page de communication ou d'équipe moderne SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="ddca7-114">You'll need to know the URL of a SharePoint Online modern Communication or Team site, or page.</span></span>

   <span data-ttu-id="ddca7-115">Les chemins d’accès de ces sites sont toujours */teams/* ou */sites/*.</span><span class="sxs-lookup"><span data-stu-id="ddca7-115">These sites will always have either */teams/* or */sites/* in their paths.</span></span>

2. <span data-ttu-id="ddca7-116">Vous devez connaître le sous-domaine de votre client, lequel sera utilisé dans l’espace réservé **{{subdomain}}**.</span><span class="sxs-lookup"><span data-stu-id="ddca7-116">You'll need to know your tenant's subdomain, which will be used in the placeholder **{{subdomain}}**.</span></span>

3. <span data-ttu-id="ddca7-117">Cet article utilise l’espace réservé **{{siteUrl}}** pour l’*URL* du site ou de la page que vous avez choisi.</span><span class="sxs-lookup"><span data-stu-id="ddca7-117">This article will use **{{siteUrl}}** as a placeholder for the *URL* of the site or page you chose.</span></span>

   <span data-ttu-id="ddca7-118">Exemple *URL* :</span><span class="sxs-lookup"><span data-stu-id="ddca7-118">Example *URLs*:</span></span>
   
   - `https://contoso.sharepoint.com/teams/Contoso`
      <br/><span data-ttu-id="ddca7-119">*ou*</span><span class="sxs-lookup"><span data-stu-id="ddca7-119">*or*</span></span>
   - `https://contoso.sharepoint.com/sites/Contoso`
        
4. <span data-ttu-id="ddca7-120">De plus, **{{sitePath}}** sera utilisé pour indiquer le *chemin d’accès* de l’URL (par exemple : /teams/Contoso).</span><span class="sxs-lookup"><span data-stu-id="ddca7-120">Also, **{{sitePath}}** will be used to denote the *path* of the URL (ex: /teams/Contoso).</span></span>

   <span data-ttu-id="ddca7-121">Exemple *trajectoires* :</span><span class="sxs-lookup"><span data-stu-id="ddca7-121">Example *paths*:</span></span>
   
   - <span data-ttu-id="ddca7-122">/teams/Contoso</span><span class="sxs-lookup"><span data-stu-id="ddca7-122">/teams/Contoso</span></span>
     <br/><span data-ttu-id="ddca7-123">*ou*</span><span class="sxs-lookup"><span data-stu-id="ddca7-123">*or*</span></span>
   - <span data-ttu-id="ddca7-124">/sites/Contoso</span><span class="sxs-lookup"><span data-stu-id="ddca7-124">/sites/Contoso</span></span>

<span data-ttu-id="ddca7-125">Commencez par suivre les étapes ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="ddca7-125">Begin by following the steps below:</span></span>

1. <span data-ttu-id="ddca7-126">Accédez au Store Teams.</span><span class="sxs-lookup"><span data-stu-id="ddca7-126">Go to the Teams Store.</span></span>

2. <span data-ttu-id="ddca7-127">Installez ou ouvrez App Studio.</span><span class="sxs-lookup"><span data-stu-id="ddca7-127">Install or open App Studio.</span></span>

3. <span data-ttu-id="ddca7-128">Cliquez sur **Ouvrir**, en regard de l’option App.</span><span class="sxs-lookup"><span data-stu-id="ddca7-128">Click **Open**, next to the App option.</span></span>

4. <span data-ttu-id="ddca7-129">Avec App studio ouvert, cliquez sur **Éditeur de manifeste**.</span><span class="sxs-lookup"><span data-stu-id="ddca7-129">With App Studio open, click on **Manifest Editor**.</span></span>

5. <span data-ttu-id="ddca7-130">**Créer une nouvelle application**.</span><span class="sxs-lookup"><span data-stu-id="ddca7-130">**Create a new app**.</span></span>

6. <span data-ttu-id="ddca7-131">Renseignez tous les **Détails de l’application**.</span><span class="sxs-lookup"><span data-stu-id="ddca7-131">Fill in all **App Details**.</span></span>

7. <span data-ttu-id="ddca7-132">Cliquez sur **Onglets** sous Fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="ddca7-132">Click on **Tabs** under Capabilities.</span></span>

8. <span data-ttu-id="ddca7-133">Cliquez sur **Ajouter** sous l’onglet Personnel.</span><span class="sxs-lookup"><span data-stu-id="ddca7-133">Click **Add** under Personal Tab.</span></span>

9. <span data-ttu-id="ddca7-134">Entrez le **Nom** puis sélectionnez **une nouvelle ID d’entité unique**.</span><span class="sxs-lookup"><span data-stu-id="ddca7-134">Fill in the **Name** and choose **a new unique Entity ID**.</span></span>

10. <span data-ttu-id="ddca7-135">Renseignez les **contentURL et URL du site web**.</span><span class="sxs-lookup"><span data-stu-id="ddca7-135">Fill in the **contentURL and Website URL**.</span></span>

    - <span data-ttu-id="ddca7-136">**contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}</span><span class="sxs-lookup"><span data-stu-id="ddca7-136">**contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}</span></span>  
    
    - <span data-ttu-id="ddca7-137">**websiteUrl**: {{siteUrl}}</span><span class="sxs-lookup"><span data-stu-id="ddca7-137">**websiteUrl**: {{siteUrl}}</span></span>

      <span data-ttu-id="ddca7-138">Exemple **contentURL** :</span><span class="sxs-lookup"><span data-stu-id="ddca7-138">Example **contentURL**:</span></span>
      
      `https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub`

11. <span data-ttu-id="ddca7-139">Accédez à la page **Domaines et autorisations**.</span><span class="sxs-lookup"><span data-stu-id="ddca7-139">Navigate to **Domains and Permissions**.</span></span> <span data-ttu-id="ddca7-140">Assurez-vous que la section domaines valides contient votre nom de domaine SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="ddca7-140">Make sure the valid domains section contains your SharePoint online domain name.</span></span>

    <span data-ttu-id="ddca7-141">Exemple : `contoso.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="ddca7-141">Example: `contoso.sharepoint.com`</span></span>

12. <span data-ttu-id="ddca7-142">Ajoutez les propriétés **Authentification unique** de l’application web suivante :</span><span class="sxs-lookup"><span data-stu-id="ddca7-142">Add the following web app **single sign-on** properties:</span></span>

    <span data-ttu-id="ddca7-143">Exemple :</span><span class="sxs-lookup"><span data-stu-id="ddca7-143">Example:</span></span>
    
    - <span data-ttu-id="ddca7-144">**ID de l’application AAD** : 00000003-0000-0ff1-ce00-000000000000</span><span class="sxs-lookup"><span data-stu-id="ddca7-144">**AAD application ID**: 00000003-0000-0ff1-ce00-000000000000</span></span>
    
    - <span data-ttu-id="ddca7-145">**Url de ressource** : {{subdomain}}.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="ddca7-145">**Resource Url**: {{subdomain}}.sharepoint.com</span></span>

      ![Authentification unique de l’application web avec ID et URL.](media/personal-app.png)

13. <span data-ttu-id="ddca7-147">**Enregistrez** ces propriétés, puis accédez à **Tester et distribuer**.</span><span class="sxs-lookup"><span data-stu-id="ddca7-147">**Save** these properties and then navigate to **Test and distribute**.</span></span>

14. <span data-ttu-id="ddca7-148">Installez l’application pour tester l’application personnellement.</span><span class="sxs-lookup"><span data-stu-id="ddca7-148">Install the app to test the application personally.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ddca7-149">Si vous n'utilisez pas Teams App Studio, vous devrez compresser le fichier manifest.JSON que vous venez de créer, accédez à l’App Store dans Teams, puis cliquez sur le lien **télécharger l’application personnalisée** (en bas à droite de l’App Store).</span><span class="sxs-lookup"><span data-stu-id="ddca7-149">If you aren't using Teams App Studio, you will have to .zip the manifest.JSON file you just created, navigate to the App Store in Teams, and click  **upload custom app** link (at the bottom right of the App Store).</span></span> <span data-ttu-id="ddca7-150">L’application est alors disponible.</span><span class="sxs-lookup"><span data-stu-id="ddca7-150">This will make the app available to you.</span></span>

15. <span data-ttu-id="ddca7-151">L’application est désormais disponible sous la forme d’un onglet personnel que vous pouvez charger et afficher dans Teams.</span><span class="sxs-lookup"><span data-stu-id="ddca7-151">Now the app is available as a personal tab for you to load and view in Teams.</span></span>

## <a name="test-and-view-your-new-personal-tab"></a><span data-ttu-id="ddca7-152">Tester et afficher votre nouvel onglet personnel</span><span class="sxs-lookup"><span data-stu-id="ddca7-152">Test and view your new personal tab</span></span>

<span data-ttu-id="ddca7-153">Pour afficher l’onglet nouveau sur le bureau Teams, accédez aux points de suspension (**...**) sur le côté gauche de la barre de l’application.</span><span class="sxs-lookup"><span data-stu-id="ddca7-153">To view the new tab on the Teams desktop, navigate to the ellipses (**…**) in the left-hand side of your app bar.</span></span> <span data-ttu-id="ddca7-154">Trouvez votre nouvelle application, chargez-la et testez-la dans Teams.</span><span class="sxs-lookup"><span data-stu-id="ddca7-154">Find your new app, load it, and test your standalone application in Teams.</span></span>

<span data-ttu-id="ddca7-155">Si vous souhaitez que la nouvelle application soit disponible dans le menu de gauche à une position supérieure, vous devez utiliser un paramètre de stratégie d’application.</span><span class="sxs-lookup"><span data-stu-id="ddca7-155">If you want to make the new app available in the left menu at a higher position, you must use an app policy setting for this.</span></span> <span data-ttu-id="ddca7-156">Ce paramètre se trouve dans la section administrateur Teams > stratégie d’application > Ajouter une application épinglée.</span><span class="sxs-lookup"><span data-stu-id="ddca7-156">This setting can be found under the Team admin section > app policy > add a pinned application.</span></span> <span data-ttu-id="ddca7-157">Lorsque vous attribuez la politique à un utilisateur pour le test, le changement apparaîtra quelques heures plus tard.</span><span class="sxs-lookup"><span data-stu-id="ddca7-157">When you assign the policy to a user for testing, the change will appear a few hours later.</span></span> <span data-ttu-id="ddca7-158">À cet esprit, n’hésitez pas à choisir l’emplacement dans lequel l’application doit apparaître à votre guise pour éviter les retards.</span><span class="sxs-lookup"><span data-stu-id="ddca7-158">With this in mind, please decide where the app should appear at your earliest convenience to help avoid delays.</span></span>

<span data-ttu-id="ddca7-159">Pour afficher et tester la nouvelle application sur un appareil mobile, ouvrez le tiroir de l’application en appuyant sur le chevron (**^**) au-dessus de la barre d’onglets située en bas de l’écran.</span><span class="sxs-lookup"><span data-stu-id="ddca7-159">To view and test the new app on a mobile device, open the app drawer by tapping on the chevron (**^**) above the tab bar near the bottom of your screen.</span></span> <span data-ttu-id="ddca7-160">Recherchez votre application et accédez-y sur votre appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="ddca7-160">Find your app and navigate to it on your mobile device.</span></span>

## <a name="a-sample-manifestjson-file"></a><span data-ttu-id="ddca7-161">Exemple de fichier Manifest.JSON</span><span class="sxs-lookup"><span data-stu-id="ddca7-161">A Sample Manifest.JSON file</span></span>

<span data-ttu-id="ddca7-162">Le fichier JSON que vous avez généré ressemble à celui ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="ddca7-162">The JSON file you generate will look something like the one below.</span></span>

```json
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
