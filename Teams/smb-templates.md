---
title: Modèles Teams pour petites et moyennes entreprises créés avec Microsoft Graph
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.reviewer: lavenkat
description: Utilisez les modèles prédéfinés de Microsoft Teams créés dans Microsoft Graph pour créer rapidement et facilement des équipes pour les petites et moyennes entreprises.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7196dd93fc1245102a333c150715c4b4570986c7
ms.sourcegitcommit: 340c2f432b78af4e78b21056af56c6421627045d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294550"
---
# <a name="teams-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a><span data-ttu-id="01269-103">Modèles Teams créés dans Microsoft Graph pour les petites et moyennes entreprises</span><span class="sxs-lookup"><span data-stu-id="01269-103">Teams templates built in Microsoft Graph for Small and Medium Businesses</span></span>

<span data-ttu-id="01269-104">Les modèles Microsoft Teams vous permettent de créer rapidement et facilement des équipes en fournissant un modèle prédéféré de paramètres, de canaux et d’applications préinstallées.</span><span class="sxs-lookup"><span data-stu-id="01269-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="01269-105">Pour les petites et moyennes entreprises, les modèles peuvent être particulièrement puissants, car ils aident les administrateurs à déployer rapidement Teams au sein de leur organisation.</span><span class="sxs-lookup"><span data-stu-id="01269-105">For small and medium businesses, templates can be especially powerful, as they help administrators to quickly deploy Teams across their organization.</span></span> <span data-ttu-id="01269-106">Les modèles aident également les utilisateurs à s’orienter et à commencer à utiliser Teams efficacement.</span><span class="sxs-lookup"><span data-stu-id="01269-106">Templates also help orient users and get started with using Teams effectively.</span></span> <span data-ttu-id="01269-107">Cet article est pour vous si vous êtes responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="01269-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your organization.</span></span>

<span data-ttu-id="01269-108">Nous proposons actuellement trois modèles de pme tierces que vous pouvez utiliser dans différentes situations.</span><span class="sxs-lookup"><span data-stu-id="01269-108">We currently offer three first-party SMB templates that you can leverage for a variety of situations.</span></span> <span data-ttu-id="01269-109">Tous les modèles créent *des équipes* privées.</span><span class="sxs-lookup"><span data-stu-id="01269-109">All templates will create *Private* Teams.</span></span> <span data-ttu-id="01269-110">Une fois que vous avez créé les équipes et que vous  êtes prêt à déployer dans votre organisation, vous pouvez définir la confidentialité sur Échelle de l’organisation ou *Publique,* le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="01269-110">Once you have created the Teams and are ready to roll out to your organization, you can set the privacy to *Org-Wide* or *Public*, as appropriate.</span></span> <span data-ttu-id="01269-111">Pour en savoir plus sur les modèles d’équipe en général, voir [Commencer à utiliser les modèles Teams.](get-started-with-teams-templates.md)</span><span class="sxs-lookup"><span data-stu-id="01269-111">To learn more about team templates in general, see [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="company-wide-template"></a><span data-ttu-id="01269-112">Company-Wide modèle</span><span class="sxs-lookup"><span data-stu-id="01269-112">Company-Wide template</span></span>
<span data-ttu-id="01269-113">Le Company-Wide modèle est destiné aux communications et à la collaboration pertinentes pour l’ensemble de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="01269-113">The Company-Wide template is meant for communication and collaboration that are relevant for the entire company.</span></span> <span data-ttu-id="01269-114">Vous pouvez utiliser le canal Général pour les annonces à l’échelle de l’entreprise, les actualités du secteur ou les billets de la direction.</span><span class="sxs-lookup"><span data-stu-id="01269-114">You can use the General channel for company-wide announcements, industry news or executive posts.</span></span> <span data-ttu-id="01269-115">Le canal Ressources humaines est l’endroit idéal pour consolider toutes les activités RH, telles que les publications de poste, l’intégration des nouveaux employés, la formation et le développement.</span><span class="sxs-lookup"><span data-stu-id="01269-115">The Human Resources channel is a great place to consolidate all HR-related activities like job posts, new employee onboarding, training, and development.</span></span> <span data-ttu-id="01269-116">Le canal Outils amusants fournit une plateforme sociale pour toutes les publications aléatoires et amusantes.</span><span class="sxs-lookup"><span data-stu-id="01269-116">The Fun Stuff channel provides a social platform for all random and fun posts.</span></span>

| <span data-ttu-id="01269-117">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="01269-117">Base template type</span></span>  | <span data-ttu-id="01269-118">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="01269-118">baseTemplateId</span></span> | <span data-ttu-id="01269-119">Propriétés de ce modèle de base</span><span class="sxs-lookup"><span data-stu-id="01269-119">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="01269-120">PME -</span><span class="sxs-lookup"><span data-stu-id="01269-120">SMB -</span></span> <br><span data-ttu-id="01269-121">À l’échelle de l’entreprise</span><span class="sxs-lookup"><span data-stu-id="01269-121">Company-wide</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| <span data-ttu-id="01269-122">Canaux</span><span class="sxs-lookup"><span data-stu-id="01269-122">Channels</span></span> <ul><li><span data-ttu-id="01269-123">Général\*</span><span class="sxs-lookup"><span data-stu-id="01269-123">General\*</span></span></li><li><span data-ttu-id="01269-124">Ressources humaines\*</span><span class="sxs-lookup"><span data-stu-id="01269-124">Human Resources\*</span></span></li><li><span data-ttu-id="01269-125">Amusant\*</span><span class="sxs-lookup"><span data-stu-id="01269-125">Fun Stuff\*</span></span></li></ul><br> <span data-ttu-id="01269-126">Applications</span><span class="sxs-lookup"><span data-stu-id="01269-126">Apps</span></span><ul><li><span data-ttu-id="01269-127">Portail d’entreprise (site web épinglé au **canal des ressources** humaines)</span><span class="sxs-lookup"><span data-stu-id="01269-127">Company Portal (Website pinned to the **Human Resources** channel)</span></span> </li> </UL><br><span data-ttu-id="01269-128">Propriétés de l’équipe</span><span class="sxs-lookup"><span data-stu-id="01269-128">Team properties</span></span> <ul><li><span data-ttu-id="01269-129">Visibilité de l’équipe définie sur Privé</span><span class="sxs-lookup"><span data-stu-id="01269-129">Team visibility set to Private</span></span></li></ul> |

<span data-ttu-id="01269-130">\*Canaux favoris automatiquement</span><span class="sxs-lookup"><span data-stu-id="01269-130">\*Auto-favorited channels</span></span> 

<span data-ttu-id="01269-131">Pour créer l'Company-Wide en prenant les valeurs par défaut du modèle prédéfiny, fournissez la représentation JSON de l’objet d’équipe dans le corps de la demande.</span><span class="sxs-lookup"><span data-stu-id="01269-131">To create the Company-Wide team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="01269-132">Pour en savoir plus sur le déploiement des modèles Teams, consultez l’article Microsoft Graph [sur la création d’une équipe.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="01269-132">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="01269-133">Demande</span><span class="sxs-lookup"><span data-stu-id="01269-133">Request</span></span> 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessOrgWide')",
    "displayName": "Org-wide",
    "description": "All posts that are relevant for entire company (e.g. Company-wide announcements, Exec posts, employee poll/feedback).",
    "visibility": "Private"
}
```

## <a name="executive-team-template"></a><span data-ttu-id="01269-134">Modèle d’équipe de direction</span><span class="sxs-lookup"><span data-stu-id="01269-134">Executive Team template</span></span>

<span data-ttu-id="01269-135">Le modèle d’équipe de direction est idéal pour créer une équipe pour que les cadres d’une entreprise communiquent et collaborent sur des initiatives d’entreprise telles que les priorités annuelles, les budgets budgétaires, les initiatives stratégiques et les principaux clients.</span><span class="sxs-lookup"><span data-stu-id="01269-135">The Executive Team template is ideal for creating a team for company executives to communicate and collaborate on company initiatives like annual priorities, fiscal budgets, strategic initiatives, and top clients.</span></span> <span data-ttu-id="01269-136">Ce modèle est livré avec un *canal privé* pour inviter des utilisateurs spécifiques à des sujets spécifiques.</span><span class="sxs-lookup"><span data-stu-id="01269-136">This template comes with a *Private* channel to invite select users for specific topics.</span></span>

| <span data-ttu-id="01269-137">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="01269-137">Base template type</span></span>  | <span data-ttu-id="01269-138">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="01269-138">baseTemplateId</span></span> | <span data-ttu-id="01269-139">Propriétés de ce modèle de base</span><span class="sxs-lookup"><span data-stu-id="01269-139">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="01269-140">PME -</span><span class="sxs-lookup"><span data-stu-id="01269-140">SMB -</span></span> <br><span data-ttu-id="01269-141">Équipe cadres</span><span class="sxs-lookup"><span data-stu-id="01269-141">Executives Team</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | <span data-ttu-id="01269-142">Canaux</span><span class="sxs-lookup"><span data-stu-id="01269-142">Channels</span></span> <ul><li><span data-ttu-id="01269-143">Général\*</span><span class="sxs-lookup"><span data-stu-id="01269-143">General\*</span></span></li><li><span data-ttu-id="01269-144">Privé \*</span><span class="sxs-lookup"><span data-stu-id="01269-144">Private \*</span></span></li></ul> <span data-ttu-id="01269-145">Applications</span><span class="sxs-lookup"><span data-stu-id="01269-145">Apps</span></span><ul><li><span data-ttu-id="01269-146">OneNote (épinglé au **canal** privé)</span><span class="sxs-lookup"><span data-stu-id="01269-146">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="01269-147">Planificateur (épinglé au **canal** privé)</span><span class="sxs-lookup"><span data-stu-id="01269-147">Planner (pinned to the **Private** channel)</span></span> </li></ul><br><span data-ttu-id="01269-148">Propriétés de l’équipe</span><span class="sxs-lookup"><span data-stu-id="01269-148">Team properties</span></span> <ul><li><span data-ttu-id="01269-149">Visibilité de l’équipe définie sur Privé</span><span class="sxs-lookup"><span data-stu-id="01269-149">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="01269-150">\*Canaux favoris automatiquement</span><span class="sxs-lookup"><span data-stu-id="01269-150">\*Auto-favorited channels</span></span><br>

<span data-ttu-id="01269-151">Pour créer l’équipe Cadres en prenant les valeurs par défaut du modèle prédéfiny, fournissez la représentation JSON de l’objet d’équipe dans le corps de la demande.</span><span class="sxs-lookup"><span data-stu-id="01269-151">To create the Executives team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="01269-152">Pour en savoir plus sur le déploiement des modèles Teams, consultez l’article Microsoft Graph [sur la création d’une équipe.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="01269-152">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="01269-153">Demande</span><span class="sxs-lookup"><span data-stu-id="01269-153">Request</span></span> 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessExecutive')",
    "displayName": "Executive",
    "description": "All posts, announcements and daily collaboration and communication for the company's leadership team.",
    "visibility": "Private"
}
```

## <a name="departmental-team-template"></a><span data-ttu-id="01269-154">Modèle d’équipe par département</span><span class="sxs-lookup"><span data-stu-id="01269-154">Departmental Team template</span></span>

<span data-ttu-id="01269-155">Le modèle d’équipe par département peut être utilisé pour créer une équipe pour des services individuels ou pour des projets.</span><span class="sxs-lookup"><span data-stu-id="01269-155">The Departmental team template can be used for creating a team for individual departments or for projects.</span></span> <span data-ttu-id="01269-156">Le modèle d’équipe Finances est idéal pour tous les billets, les annonces et la collaboration et la communication quotidiennes au sein des membres de l’équipe Finances et des membres de l’équipe de direction, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="01269-156">The Finance team template is ideal for all posts, announcements, and daily collaboration and communication within the Finance team members and executive team members as appropriate.</span></span> <span data-ttu-id="01269-157">Le modèle est livré avec un *canal privé* pour inviter des utilisateurs spécifiques à des sujets spécifiques.</span><span class="sxs-lookup"><span data-stu-id="01269-157">The template comes with a *Private* channel to invite select users for specific topics.</span></span> <span data-ttu-id="01269-158">Nous fournissons également le script ci-dessous à l’équipe Finances, qui peut être utilisé pour étendre le modèle à d’autres départements ou projets spécifiques en l’ajoutant, en le supprimant ou en le modifiez comme bon vous semble.</span><span class="sxs-lookup"><span data-stu-id="01269-158">We also provide the script below for the Finance team that can be used to extend the template to additional departments or specific projects by adding, deleting from, or editing to your liking.</span></span> <span data-ttu-id="01269-159">Par exemple, si vous avez un service marketing, le script peut  être  adapté en renommant l’équipe du service financier au service marketing pour créer une équipe marketing. </span><span class="sxs-lookup"><span data-stu-id="01269-159">For example, if you have a *Marketing* department, then the script can be adapted by renaming the team from *Finance* to *Marketing* to create a new Marketing team</span></span>

| <span data-ttu-id="01269-160">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="01269-160">Base template type</span></span> | <span data-ttu-id="01269-161">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="01269-161">baseTemplateId</span></span> | <span data-ttu-id="01269-162">Propriétés de ce modèle de base</span><span class="sxs-lookup"><span data-stu-id="01269-162">Properties that come with this base template</span></span> |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="01269-163">PME -</span><span class="sxs-lookup"><span data-stu-id="01269-163">SMB -</span></span> <br><span data-ttu-id="01269-164">Finances</span><span class="sxs-lookup"><span data-stu-id="01269-164">Finance</span></span>  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| <span data-ttu-id="01269-165">Canaux</span><span class="sxs-lookup"><span data-stu-id="01269-165">Channels</span></span> <ul><li><span data-ttu-id="01269-166">Général\*</span><span class="sxs-lookup"><span data-stu-id="01269-166">General\*</span></span></li><li><span data-ttu-id="01269-167">Privé \*</span><span class="sxs-lookup"><span data-stu-id="01269-167">Private \*</span></span></li></ul><br> <span data-ttu-id="01269-168">Applications</span><span class="sxs-lookup"><span data-stu-id="01269-168">Apps</span></span><ul><li><span data-ttu-id="01269-169">OneNote (épinglé au **canal** privé)</span><span class="sxs-lookup"><span data-stu-id="01269-169">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="01269-170">Planificateur (épinglé au **canal** privé)</span><span class="sxs-lookup"><span data-stu-id="01269-170">Planner (pinned to the **Private** channel)</span></span> </li> </ul><br><span data-ttu-id="01269-171">Propriétés de l’équipe</span><span class="sxs-lookup"><span data-stu-id="01269-171">Team properties</span></span> <ul><li><span data-ttu-id="01269-172">Visibilité de l’équipe définie sur Privé</span><span class="sxs-lookup"><span data-stu-id="01269-172">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="01269-173">\*Canaux favoris automatiquement</span><span class="sxs-lookup"><span data-stu-id="01269-173">\*Auto-favorited channels</span></span>

<span data-ttu-id="01269-174">Pour créer l’équipe Finances en prenant les valeurs par défaut du modèle prédéfiny, fournissez la représentation JSON de l’objet d’équipe dans le corps de la demande.</span><span class="sxs-lookup"><span data-stu-id="01269-174">To create the Finance team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="01269-175">Pour en savoir plus sur le déploiement des modèles Teams, consultez l’article Microsoft Graph [sur la création d’une équipe.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="01269-175">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="01269-176">Demande</span><span class="sxs-lookup"><span data-stu-id="01269-176">Request</span></span> 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessFinance')",
    "displayName": "Finance",
    "description": "All posts, announcements and daily collaboration and communication within the Finance team members (and exec team members as appropriate).",
    "visibility": "Private"
}
```

### <a name="example-finance-team-template-extension-script"></a><span data-ttu-id="01269-177">Exemple : Script d’extension de modèle Équipe Finance</span><span class="sxs-lookup"><span data-stu-id="01269-177">Example: Finance Team template extension script</span></span>

```powershell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('standard')",
  "displayName": "Finance",
  "description": "Finance Team",
  "channels": 
   [
        {
            "displayName": "Private",
            "isFavoriteByDefault": true,
            "description": "Invite a more select audience for specific topics.",
             "tabs": 
             [
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')",
                    "name": "OneNote"
                },
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')",
                    "name": "Planner"
                }
            ]
        }
    ],
    "memberSettings": 
    {
        "allowCreateUpdateChannels": true,
        "allowDeleteChannels": true,
       "allowAddRemoveApps": true,
        "allowCreateUpdateRemoveTabs": true,
        "allowCreateUpdateRemoveConnectors": true
    },
    "guestSettings": 
    {
        "allowCreateUpdateChannels": false,
        "allowDeleteChannels": false
    },
    "funSettings": 
    {
        "allowGiphy": true,
        "giphyContentRating": "Moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
    },
    "messagingSettings": 
    {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
    },
    "discoverySettings": 
    {
        "showInTeamsSearchAndSuggestions": true
    },
    "installedApps": 
    [
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')"
        },
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')"
        }
    ]
}

```

## <a name="related-topics"></a><span data-ttu-id="01269-178">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="01269-178">Related topics</span></span>

- [<span data-ttu-id="01269-179">Commencer à utiliser les modèles Teams dans la console d’administration</span><span class="sxs-lookup"><span data-stu-id="01269-179">Get started with Teams templates in the admin console</span></span>](get-started-with-teams-templates-in-the-admin-console.md)
- [<span data-ttu-id="01269-180">Prise en main des modèles Teams</span><span class="sxs-lookup"><span data-stu-id="01269-180">Get started with Teams templates</span></span>](get-started-with-teams-templates.md)
- <span data-ttu-id="01269-181">[Créer une équipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (en prévisualisation)</span><span class="sxs-lookup"><span data-stu-id="01269-181">[Create team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (in preview)</span></span>

