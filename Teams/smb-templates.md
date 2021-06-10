---
title: Teams modèles pour petites et moyennes entreprises conçus avec Microsoft Graph
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
description: Utilisez Microsoft Teams modèles prédéfinés créés dans Microsoft Graph pour créer rapidement et facilement des équipes pour les petites et moyennes entreprises.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e3d29dca0bbdbd7b3487ac1738b84396a3d41117
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116992"
---
# <a name="teams-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a><span data-ttu-id="c28a8-103">Teams modèles créés dans Microsoft Graph pour les petites et moyennes entreprises</span><span class="sxs-lookup"><span data-stu-id="c28a8-103">Teams templates built in Microsoft Graph for Small and Medium Businesses</span></span>

<span data-ttu-id="c28a8-104">Les modèles Microsoft Teams vous permettent de créer rapidement et facilement des équipes en fournissant un modèle prédéfini de paramètres, de canaux et d'applications préinstallées.</span><span class="sxs-lookup"><span data-stu-id="c28a8-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="c28a8-105">Pour les petites et moyennes entreprises, les modèles peuvent être particulièrement puissants, car ils aident les administrateurs à déployer rapidement des Teams au sein de leur organisation.</span><span class="sxs-lookup"><span data-stu-id="c28a8-105">For small and medium businesses, templates can be especially powerful, as they help administrators to quickly deploy Teams across their organization.</span></span> <span data-ttu-id="c28a8-106">Les modèles aident également à orienter les utilisateurs et à commencer à Teams efficacement.</span><span class="sxs-lookup"><span data-stu-id="c28a8-106">Templates also help orient users and get started with using Teams effectively.</span></span> <span data-ttu-id="c28a8-107">Cet article est pour vous si vous êtes responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c28a8-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your organization.</span></span>

<span data-ttu-id="c28a8-108">Nous proposons actuellement trois modèles de pme tierces que vous pouvez utiliser dans différentes situations.</span><span class="sxs-lookup"><span data-stu-id="c28a8-108">We currently offer three first-party SMB templates that you can leverage for a variety of situations.</span></span> <span data-ttu-id="c28a8-109">Tous les modèles créent *des modèles Teams.*</span><span class="sxs-lookup"><span data-stu-id="c28a8-109">All templates will create *Private* Teams.</span></span> <span data-ttu-id="c28a8-110">Une fois que vous avez créé l’Teams et que vous êtes prêt  à la déployer dans votre organisation, vous pouvez définir la confidentialité sur Échelle de l’organisation ou *Publique,* le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="c28a8-110">Once you have created the Teams and are ready to roll out to your organization, you can set the privacy to *Org-Wide* or *Public*, as appropriate.</span></span> <span data-ttu-id="c28a8-111">Pour en savoir plus sur les modèles d’équipe en général, consultez [Prise en main des modèles Teams](get-started-with-teams-templates.md).</span><span class="sxs-lookup"><span data-stu-id="c28a8-111">To learn more about team templates in general, see [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="company-wide-template"></a><span data-ttu-id="c28a8-112">Company-Wide modèle</span><span class="sxs-lookup"><span data-stu-id="c28a8-112">Company-Wide template</span></span>
<span data-ttu-id="c28a8-113">Le Company-Wide modèle est destiné aux communications et à la collaboration pertinentes pour l’ensemble de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="c28a8-113">The Company-Wide template is meant for communication and collaboration that are relevant for the entire company.</span></span> <span data-ttu-id="c28a8-114">Vous pouvez utiliser le canal Général pour les annonces à l’échelle de l’entreprise, les actualités du secteur ou les publications de la direction.</span><span class="sxs-lookup"><span data-stu-id="c28a8-114">You can use the General channel for company-wide announcements, industry news or executive posts.</span></span> <span data-ttu-id="c28a8-115">Le canal Ressources humaines est l’endroit idéal pour consolider toutes les activités RH, telles que les publications de poste, l’intégration des nouveaux employés, la formation et le développement.</span><span class="sxs-lookup"><span data-stu-id="c28a8-115">The Human Resources channel is a great place to consolidate all HR-related activities like job posts, new employee onboarding, training, and development.</span></span> <span data-ttu-id="c28a8-116">Le canal Outils amusants fournit une plateforme sociale pour toutes les publications aléatoires et amusantes.</span><span class="sxs-lookup"><span data-stu-id="c28a8-116">The Fun Stuff channel provides a social platform for all random and fun posts.</span></span>

| <span data-ttu-id="c28a8-117">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="c28a8-117">Base template type</span></span>  | <span data-ttu-id="c28a8-118">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="c28a8-118">baseTemplateId</span></span> | <span data-ttu-id="c28a8-119">Propriétés fournies avec ce modèle de base</span><span class="sxs-lookup"><span data-stu-id="c28a8-119">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="c28a8-120">PME -</span><span class="sxs-lookup"><span data-stu-id="c28a8-120">SMB -</span></span> <br><span data-ttu-id="c28a8-121">À l’échelle de l’entreprise</span><span class="sxs-lookup"><span data-stu-id="c28a8-121">Company-wide</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| <span data-ttu-id="c28a8-122">Canaux</span><span class="sxs-lookup"><span data-stu-id="c28a8-122">Channels</span></span> <ul><li><span data-ttu-id="c28a8-123">Généralités\*</span><span class="sxs-lookup"><span data-stu-id="c28a8-123">General\*</span></span></li><li><span data-ttu-id="c28a8-124">Ressources humaines\*</span><span class="sxs-lookup"><span data-stu-id="c28a8-124">Human Resources\*</span></span></li><li><span data-ttu-id="c28a8-125">Amusant\*</span><span class="sxs-lookup"><span data-stu-id="c28a8-125">Fun Stuff\*</span></span></li></ul><br> <span data-ttu-id="c28a8-126">Applications</span><span class="sxs-lookup"><span data-stu-id="c28a8-126">Apps</span></span><ul><li><span data-ttu-id="c28a8-127">Portail d’entreprise (site web épinglé au **canal des ressources** humaines)</span><span class="sxs-lookup"><span data-stu-id="c28a8-127">Company Portal (Website pinned to the **Human Resources** channel)</span></span> </li> </UL><br><span data-ttu-id="c28a8-128">Propriétés de l’équipe</span><span class="sxs-lookup"><span data-stu-id="c28a8-128">Team properties</span></span> <ul><li><span data-ttu-id="c28a8-129">Visibilité de l’équipe définie sur Privé</span><span class="sxs-lookup"><span data-stu-id="c28a8-129">Team visibility set to Private</span></span></li></ul> |

<span data-ttu-id="c28a8-130">\*Canaux favoris automatiquement</span><span class="sxs-lookup"><span data-stu-id="c28a8-130">\*Auto-favorited channels</span></span> 

<span data-ttu-id="c28a8-131">Pour créer l'Company-Wide en prenant les valeurs par défaut du modèle prédéfiny, fournissez la représentation JSON de l’objet d’équipe dans le corps de la demande.</span><span class="sxs-lookup"><span data-stu-id="c28a8-131">To create the Company-Wide team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="c28a8-132">Pour en savoir plus sur le déploiement de Teams modèles, consultez l’article microsoft Graph [sur la création d’une équipe.](/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="c28a8-132">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="c28a8-133">Demande</span><span class="sxs-lookup"><span data-stu-id="c28a8-133">Request</span></span> 
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

## <a name="executive-team-template"></a><span data-ttu-id="c28a8-134">Modèle d’équipe de direction</span><span class="sxs-lookup"><span data-stu-id="c28a8-134">Executive Team template</span></span>

<span data-ttu-id="c28a8-135">Le modèle d’équipe de direction est idéal pour créer une équipe pour que les cadres d’une entreprise communiquent et collaborent sur des initiatives d’entreprise telles que les priorités annuelles, les budgets budgétaires, les initiatives stratégiques et les principaux clients.</span><span class="sxs-lookup"><span data-stu-id="c28a8-135">The Executive Team template is ideal for creating a team for company executives to communicate and collaborate on company initiatives like annual priorities, fiscal budgets, strategic initiatives, and top clients.</span></span> <span data-ttu-id="c28a8-136">Ce modèle est livré avec un *canal privé* pour inviter des utilisateurs spécifiques à des sujets spécifiques.</span><span class="sxs-lookup"><span data-stu-id="c28a8-136">This template comes with a *Private* channel to invite select users for specific topics.</span></span>

| <span data-ttu-id="c28a8-137">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="c28a8-137">Base template type</span></span>  | <span data-ttu-id="c28a8-138">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="c28a8-138">baseTemplateId</span></span> | <span data-ttu-id="c28a8-139">Propriétés fournies avec ce modèle de base</span><span class="sxs-lookup"><span data-stu-id="c28a8-139">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="c28a8-140">PME -</span><span class="sxs-lookup"><span data-stu-id="c28a8-140">SMB -</span></span> <br><span data-ttu-id="c28a8-141">Équipe cadres</span><span class="sxs-lookup"><span data-stu-id="c28a8-141">Executives Team</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | <span data-ttu-id="c28a8-142">Canaux</span><span class="sxs-lookup"><span data-stu-id="c28a8-142">Channels</span></span> <ul><li><span data-ttu-id="c28a8-143">Généralités\*</span><span class="sxs-lookup"><span data-stu-id="c28a8-143">General\*</span></span></li><li><span data-ttu-id="c28a8-144">Privé \*</span><span class="sxs-lookup"><span data-stu-id="c28a8-144">Private \*</span></span></li></ul> <span data-ttu-id="c28a8-145">Applications</span><span class="sxs-lookup"><span data-stu-id="c28a8-145">Apps</span></span><ul><li><span data-ttu-id="c28a8-146">OneNote (épinglé au **canal** privé)</span><span class="sxs-lookup"><span data-stu-id="c28a8-146">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="c28a8-147">Planificateur (épinglé au **canal** privé)</span><span class="sxs-lookup"><span data-stu-id="c28a8-147">Planner (pinned to the **Private** channel)</span></span> </li></ul><br><span data-ttu-id="c28a8-148">Propriétés de l’équipe</span><span class="sxs-lookup"><span data-stu-id="c28a8-148">Team properties</span></span> <ul><li><span data-ttu-id="c28a8-149">Visibilité de l’équipe définie sur Privé</span><span class="sxs-lookup"><span data-stu-id="c28a8-149">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="c28a8-150">\*Canaux favoris automatiquement</span><span class="sxs-lookup"><span data-stu-id="c28a8-150">\*Auto-favorited channels</span></span><br>

<span data-ttu-id="c28a8-151">Pour créer l’équipe Cadres en prenant les valeurs par défaut du modèle prédéfiny, fournissez la représentation JSON de l’objet d’équipe dans le corps de la demande.</span><span class="sxs-lookup"><span data-stu-id="c28a8-151">To create the Executives team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="c28a8-152">Pour en savoir plus sur le déploiement de Teams modèles, consultez l’article microsoft Graph [sur la création d’une équipe.](/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="c28a8-152">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="c28a8-153">Demande</span><span class="sxs-lookup"><span data-stu-id="c28a8-153">Request</span></span> 
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

## <a name="departmental-team-template"></a><span data-ttu-id="c28a8-154">Modèle d’équipe par département</span><span class="sxs-lookup"><span data-stu-id="c28a8-154">Departmental Team template</span></span>

<span data-ttu-id="c28a8-155">Le modèle d’équipe par département peut être utilisé pour créer une équipe pour des services individuels ou pour des projets.</span><span class="sxs-lookup"><span data-stu-id="c28a8-155">The Departmental team template can be used for creating a team for individual departments or for projects.</span></span> <span data-ttu-id="c28a8-156">Le modèle d’équipe Finances est idéal pour tous les billets, les annonces et la collaboration et la communication quotidiennes au sein des membres de l’équipe Finances et des membres de l’équipe de direction, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="c28a8-156">The Finance team template is ideal for all posts, announcements, and daily collaboration and communication within the Finance team members and executive team members as appropriate.</span></span> <span data-ttu-id="c28a8-157">Le modèle est livré avec un *canal privé* pour inviter des utilisateurs spécifiques à des sujets spécifiques.</span><span class="sxs-lookup"><span data-stu-id="c28a8-157">The template comes with a *Private* channel to invite select users for specific topics.</span></span> <span data-ttu-id="c28a8-158">Nous fournissons également le script ci-dessous à l’équipe Finances, qui peut être utilisé pour étendre le modèle à d’autres départements ou projets spécifiques en l’ajoutant, en le supprimant ou en le modifiez comme bon vous semble.</span><span class="sxs-lookup"><span data-stu-id="c28a8-158">We also provide the script below for the Finance team that can be used to extend the template to additional departments or specific projects by adding, deleting from, or editing to your liking.</span></span> <span data-ttu-id="c28a8-159">Par exemple, si vous avez un service marketing, le script peut  être  adapté en renommant l’équipe du service financier au service marketing pour créer une équipe marketing. </span><span class="sxs-lookup"><span data-stu-id="c28a8-159">For example, if you have a *Marketing* department, then the script can be adapted by renaming the team from *Finance* to *Marketing* to create a new Marketing team</span></span>

| <span data-ttu-id="c28a8-160">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="c28a8-160">Base template type</span></span> | <span data-ttu-id="c28a8-161">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="c28a8-161">baseTemplateId</span></span> | <span data-ttu-id="c28a8-162">Propriétés fournies avec ce modèle de base</span><span class="sxs-lookup"><span data-stu-id="c28a8-162">Properties that come with this base template</span></span> |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="c28a8-163">PME -</span><span class="sxs-lookup"><span data-stu-id="c28a8-163">SMB -</span></span> <br><span data-ttu-id="c28a8-164">Finances</span><span class="sxs-lookup"><span data-stu-id="c28a8-164">Finance</span></span>  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| <span data-ttu-id="c28a8-165">Canaux</span><span class="sxs-lookup"><span data-stu-id="c28a8-165">Channels</span></span> <ul><li><span data-ttu-id="c28a8-166">Généralités\*</span><span class="sxs-lookup"><span data-stu-id="c28a8-166">General\*</span></span></li><li><span data-ttu-id="c28a8-167">Privé \*</span><span class="sxs-lookup"><span data-stu-id="c28a8-167">Private \*</span></span></li></ul><br> <span data-ttu-id="c28a8-168">Applications</span><span class="sxs-lookup"><span data-stu-id="c28a8-168">Apps</span></span><ul><li><span data-ttu-id="c28a8-169">OneNote (épinglé au **canal** privé)</span><span class="sxs-lookup"><span data-stu-id="c28a8-169">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="c28a8-170">Planificateur (épinglé au **canal** privé)</span><span class="sxs-lookup"><span data-stu-id="c28a8-170">Planner (pinned to the **Private** channel)</span></span> </li> </ul><br><span data-ttu-id="c28a8-171">Propriétés de l’équipe</span><span class="sxs-lookup"><span data-stu-id="c28a8-171">Team properties</span></span> <ul><li><span data-ttu-id="c28a8-172">Visibilité de l’équipe définie sur Privé</span><span class="sxs-lookup"><span data-stu-id="c28a8-172">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="c28a8-173">\*Canaux favoris automatiquement</span><span class="sxs-lookup"><span data-stu-id="c28a8-173">\*Auto-favorited channels</span></span>

<span data-ttu-id="c28a8-174">Pour créer l’équipe Finances en prenant les valeurs par défaut du modèle prédéfiny, fournissez la représentation JSON de l’objet d’équipe dans le corps de la demande.</span><span class="sxs-lookup"><span data-stu-id="c28a8-174">To create the Finance team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="c28a8-175">Pour en savoir plus sur le déploiement de Teams modèles, consultez l’article microsoft Graph [sur la création d’une équipe.](/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="c28a8-175">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="c28a8-176">Demande</span><span class="sxs-lookup"><span data-stu-id="c28a8-176">Request</span></span> 
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

### <a name="example-finance-team-template-extension-script"></a><span data-ttu-id="c28a8-177">Exemple : Script d’extension de modèle Équipe Finance</span><span class="sxs-lookup"><span data-stu-id="c28a8-177">Example: Finance Team template extension script</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="c28a8-178">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="c28a8-178">Related topics</span></span>

- [<span data-ttu-id="c28a8-179">Commencer à utiliser Teams modèles dans la console d’administration</span><span class="sxs-lookup"><span data-stu-id="c28a8-179">Get started with Teams templates in the admin console</span></span>](get-started-with-teams-templates-in-the-admin-console.md)
- [<span data-ttu-id="c28a8-180">Prise en main des modèles Teams</span><span class="sxs-lookup"><span data-stu-id="c28a8-180">Get started with Teams templates</span></span>](get-started-with-teams-templates.md)
- <span data-ttu-id="c28a8-181">[Créer une équipe](/graph/api/team-post?view=graph-rest-beta) (en prévisualisation)</span><span class="sxs-lookup"><span data-stu-id="c28a8-181">[Create team](/graph/api/team-post?view=graph-rest-beta) (in preview)</span></span>