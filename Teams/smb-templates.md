---
title: Modèles d’équipes pour les petites et moyennes entreprises créées avec Microsoft Graph
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
description: Utilisez les modèles prédéfinis de Microsoft teams intégrés dans Microsoft Graph pour créer rapidement et facilement des équipes pour les petites et moyennes entreprises.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9807e7f3694731af398abd83189698420ec36b8a
ms.sourcegitcommit: ded1e92348b6c18aa31f7f67e68ced3db525977d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/28/2020
ms.locfileid: "46506147"
---
# <a name="teams-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a><span data-ttu-id="96489-103">Modèles d’équipes intégrés à Microsoft Graph pour les petites et moyennes entreprises</span><span class="sxs-lookup"><span data-stu-id="96489-103">Teams templates built in Microsoft Graph for Small and Medium Businesses</span></span>

<span data-ttu-id="96489-104">Les modèles Microsoft teams vous permettent de créer rapidement et facilement des équipes en fournissant un modèle prédéfini de paramètres, de canaux et d’applications préinstallées.</span><span class="sxs-lookup"><span data-stu-id="96489-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="96489-105">Pour les petites et moyennes entreprises, les modèles peuvent être particulièrement puissants, car ils permettent aux administrateurs de déployer rapidement des équipes au sein de leur organisation.</span><span class="sxs-lookup"><span data-stu-id="96489-105">For small and medium businesses, templates can be especially powerful, as they help administrators to quickly deploy Teams across their organization.</span></span> <span data-ttu-id="96489-106">Les modèles permettent également d’orienter les utilisateurs et de commencer à utiliser les équipes efficacement.</span><span class="sxs-lookup"><span data-stu-id="96489-106">Templates also help orient users and get started with using Teams effectively.</span></span> <span data-ttu-id="96489-107">Cet article est pour vous si vous êtes responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="96489-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your organization.</span></span>

<span data-ttu-id="96489-108">Pour l’instant, nous proposons trois modèles SMB de première partie que vous pouvez utiliser dans diverses situations.</span><span class="sxs-lookup"><span data-stu-id="96489-108">We currently offer three first-party SMB templates that you can leverage for a variety of situations.</span></span> <span data-ttu-id="96489-109">Tous les modèles créent une équipe *privée* .</span><span class="sxs-lookup"><span data-stu-id="96489-109">All templates will create *Private* Teams.</span></span> <span data-ttu-id="96489-110">Une fois que vous avez créé les équipes et que vous êtes prêt à déployer votre organisation, vous pouvez définir le *niveau* de confidentialité en fonction de l’organisation ou du *public*, selon le cas.</span><span class="sxs-lookup"><span data-stu-id="96489-110">Once you have created the Teams and are ready to roll-out to your organization, you can set the privacy to *Org-Wide* or *Public*, as appropriate.</span></span> <span data-ttu-id="96489-111">Pour en savoir plus sur les modèles d’équipe en général, voir [prendre en main les modèles](get-started-with-teams-templates.md)Teams.</span><span class="sxs-lookup"><span data-stu-id="96489-111">To learn more about team templates in general, please see [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="company-wide-template"></a><span data-ttu-id="96489-112">Modèle à l’échelle de l’entreprise</span><span class="sxs-lookup"><span data-stu-id="96489-112">Company-Wide template</span></span>
<span data-ttu-id="96489-113">Le modèle à l’échelle de l’entreprise est destiné aux communications et à la collaboration pertinentes pour l’ensemble de la société.</span><span class="sxs-lookup"><span data-stu-id="96489-113">The Company-Wide template is meant for communication and collaboration that are relevant for the entire company.</span></span> <span data-ttu-id="96489-114">Vous pouvez utiliser le canal général pour les annonces à l’échelle de l’entreprise, les actualités du secteur ou les billets d’encadrement.</span><span class="sxs-lookup"><span data-stu-id="96489-114">You can use the General channel for company-wide announcements, industry news or executive posts.</span></span> <span data-ttu-id="96489-115">Le canal de ressources humaines est l’endroit idéal pour consolider toutes les activités liées aux ressources humaines, telles que les billets de poste, l’intégration de nouveaux employés, la formation et le développement.</span><span class="sxs-lookup"><span data-stu-id="96489-115">The Human Resources channel is a great place to consolidate all HR-related activities like job posts, new employee onboarding, training and development.</span></span> <span data-ttu-id="96489-116">Le canal amusant est une plate-forme de mise en place pour toutes les publications aléatoires et amusantes.</span><span class="sxs-lookup"><span data-stu-id="96489-116">The Fun Stuff channel provides a social platform for all random and fun posts.</span></span>

| <span data-ttu-id="96489-117">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="96489-117">Base template type</span></span>  | <span data-ttu-id="96489-118">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="96489-118">baseTemplateId</span></span> | <span data-ttu-id="96489-119">Propriétés fournies avec ce modèle de base</span><span class="sxs-lookup"><span data-stu-id="96489-119">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="96489-120">Secteur</span><span class="sxs-lookup"><span data-stu-id="96489-120">SMB -</span></span> <br><span data-ttu-id="96489-121">À l’échelle de l’entreprise</span><span class="sxs-lookup"><span data-stu-id="96489-121">Company-wide</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| <span data-ttu-id="96489-122">Canaux</span><span class="sxs-lookup"><span data-stu-id="96489-122">Channels</span></span> <ul><li><span data-ttu-id="96489-123">Général\*</span><span class="sxs-lookup"><span data-stu-id="96489-123">General\*</span></span></li><li><span data-ttu-id="96489-124">Ressources humaines\*</span><span class="sxs-lookup"><span data-stu-id="96489-124">Human Resources\*</span></span></li><li><span data-ttu-id="96489-125">Outils amusants\*</span><span class="sxs-lookup"><span data-stu-id="96489-125">Fun Stuff\*</span></span></li></ul><br> <span data-ttu-id="96489-126">Applications</span><span class="sxs-lookup"><span data-stu-id="96489-126">Apps</span></span><ul><li><span data-ttu-id="96489-127">Portail d’entreprise (site Web épinglé au canal **ressources humaines** )</span><span class="sxs-lookup"><span data-stu-id="96489-127">Company Portal (Website pinned to the **Human Resources** channel)</span></span> </li> </UL><br><span data-ttu-id="96489-128">Propriétés d’équipe</span><span class="sxs-lookup"><span data-stu-id="96489-128">Team properties</span></span> <ul><li><span data-ttu-id="96489-129">Visibilité de l’équipe définie sur privée</span><span class="sxs-lookup"><span data-stu-id="96489-129">Team visibility set to Private</span></span></li></ul> |

<span data-ttu-id="96489-130">\* Canaux avec favoris automatique</span><span class="sxs-lookup"><span data-stu-id="96489-130">\*Auto-favorited channels</span></span> 

<span data-ttu-id="96489-131">Pour créer une équipe à l’échelle de la société en utilisant les valeurs par défaut du modèle prédéfini, fournissez la représentation JSON de l’objet d’équipe dans le corps de la requête.</span><span class="sxs-lookup"><span data-stu-id="96489-131">To create the Company-Wide team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="96489-132">Pour en savoir plus sur le déploiement de modèles d’équipes, voir l' [article Microsoft Graph sur la création d’une équipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="96489-132">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="96489-133">Demande</span><span class="sxs-lookup"><span data-stu-id="96489-133">Request</span></span> 
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

## <a name="executive-team-template"></a><span data-ttu-id="96489-134">Modèle d’équipe exécutive</span><span class="sxs-lookup"><span data-stu-id="96489-134">Executive Team template</span></span>

<span data-ttu-id="96489-135">Le modèle d’équipe exécutive est idéal pour créer une équipe destinée aux responsables de la société afin de communiquer et de collaborer sur des initiatives de société telles que des priorités annuelles, des budgets fiscaux, des initiatives stratégiques, des clients principaux, etc. Ce modèle est fourni avec un canal *privé* pour inviter des utilisateurs à sélectionner des rubriques spécifiques.</span><span class="sxs-lookup"><span data-stu-id="96489-135">The Executive Team template is ideal for creating a team for company executives to communicate and collaborate on company initiatives like annual priorities, fiscal budgets, strategic initiatives, top clients, etc. This template comes with a *Private* channel to invite select users for specific topics.</span></span>

| <span data-ttu-id="96489-136">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="96489-136">Base template type</span></span>  | <span data-ttu-id="96489-137">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="96489-137">baseTemplateId</span></span> | <span data-ttu-id="96489-138">Propriétés fournies avec ce modèle de base</span><span class="sxs-lookup"><span data-stu-id="96489-138">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="96489-139">Secteur</span><span class="sxs-lookup"><span data-stu-id="96489-139">SMB -</span></span> <br><span data-ttu-id="96489-140">Équipe de direction</span><span class="sxs-lookup"><span data-stu-id="96489-140">Executives Team</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | <span data-ttu-id="96489-141">Canaux</span><span class="sxs-lookup"><span data-stu-id="96489-141">Channels</span></span> <ul><li><span data-ttu-id="96489-142">Général\*</span><span class="sxs-lookup"><span data-stu-id="96489-142">General\*</span></span></li><li><span data-ttu-id="96489-143">Vulnérabilité\*</span><span class="sxs-lookup"><span data-stu-id="96489-143">Private \*</span></span></li></ul> <span data-ttu-id="96489-144">Applications</span><span class="sxs-lookup"><span data-stu-id="96489-144">Apps</span></span><ul><li><span data-ttu-id="96489-145">OneNote (épinglé au canal **privé** )</span><span class="sxs-lookup"><span data-stu-id="96489-145">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="96489-146">Planificateur (épinglé au canal **privé** )</span><span class="sxs-lookup"><span data-stu-id="96489-146">Planner (pinned to the **Private** channel)</span></span> </li></ul><br><span data-ttu-id="96489-147">Propriétés d’équipe</span><span class="sxs-lookup"><span data-stu-id="96489-147">Team properties</span></span> <ul><li><span data-ttu-id="96489-148">Visibilité de l’équipe définie sur privée</span><span class="sxs-lookup"><span data-stu-id="96489-148">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="96489-149">\* Canaux avec favoris automatique</span><span class="sxs-lookup"><span data-stu-id="96489-149">\*Auto-favorited channels</span></span><br>

<span data-ttu-id="96489-150">Pour créer l’équipe direction en prédéfinissant les valeurs par défaut du modèle prédéfini, fournissez la représentation JSON de l’objet équipe dans le corps de la requête.</span><span class="sxs-lookup"><span data-stu-id="96489-150">To create the Executives team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="96489-151">Pour en savoir plus sur le déploiement de modèles d’équipes, voir l' [article Microsoft Graph sur la création d’une équipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="96489-151">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="96489-152">Demande</span><span class="sxs-lookup"><span data-stu-id="96489-152">Request</span></span> 
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

## <a name="departmental-team-template"></a><span data-ttu-id="96489-153">Modèle d’équipe département</span><span class="sxs-lookup"><span data-stu-id="96489-153">Departmental Team template</span></span>

<span data-ttu-id="96489-154">Vous pouvez utiliser le modèle d’équipe départemental pour créer une équipe pour des services individuels ou pour des projets.</span><span class="sxs-lookup"><span data-stu-id="96489-154">The Departmental team template can be used for creating a team for individual departments or for projects.</span></span> <span data-ttu-id="96489-155">Le modèle d’équipe Finance est idéal pour tous les billets, annonces, collaboration quotidienne et communication au sein des membres de l’équipe finance (et membres de l’équipe de direction, le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="96489-155">The Finance team template is ideal for all posts, announcements and daily collaboration and communication within the Finance team members (and executive team members as appropriate).</span></span> <span data-ttu-id="96489-156">Le modèle est fourni avec un canal *privé* pour inviter des utilisateurs à sélectionner des rubriques spécifiques.</span><span class="sxs-lookup"><span data-stu-id="96489-156">The template comes with a *Private* channel to invite select users for specific topics.</span></span> <span data-ttu-id="96489-157">Nous fournissons également le script ci-dessous pour l’équipe finance qui peut être utilisée pour étendre le modèle à des services ou des projets spécifiques en ajoutant, supprimant ou en modifiant à votre gré.</span><span class="sxs-lookup"><span data-stu-id="96489-157">We also provide the script below for the Finance team which can be used to extend the template to additional departments or specific projects by adding, deleting from or editing to your liking.</span></span> <span data-ttu-id="96489-158">Par exemple, si vous avez un service *marketing* , le script peut être adapté en renommant l’équipe de *finance* en *marketing* pour créer une nouvelle équipe marketing.</span><span class="sxs-lookup"><span data-stu-id="96489-158">For example, if you have a *Marketing* department, then the script can be adapted by renaming the team from *Finance* to *Marketing* to create a new Marketing team</span></span>

| <span data-ttu-id="96489-159">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="96489-159">Base template type</span></span> | <span data-ttu-id="96489-160">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="96489-160">baseTemplateId</span></span> | <span data-ttu-id="96489-161">Propriétés fournies avec ce modèle de base</span><span class="sxs-lookup"><span data-stu-id="96489-161">Properties that come with this base template</span></span> |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="96489-162">Secteur</span><span class="sxs-lookup"><span data-stu-id="96489-162">SMB -</span></span> <br><span data-ttu-id="96489-163">Finances</span><span class="sxs-lookup"><span data-stu-id="96489-163">Finance</span></span>  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| <span data-ttu-id="96489-164">Canaux</span><span class="sxs-lookup"><span data-stu-id="96489-164">Channels</span></span> <ul><li><span data-ttu-id="96489-165">Général\*</span><span class="sxs-lookup"><span data-stu-id="96489-165">General\*</span></span></li><li><span data-ttu-id="96489-166">Vulnérabilité\*</span><span class="sxs-lookup"><span data-stu-id="96489-166">Private \*</span></span></li></ul><br> <span data-ttu-id="96489-167">Applications</span><span class="sxs-lookup"><span data-stu-id="96489-167">Apps</span></span><ul><li><span data-ttu-id="96489-168">OneNote (épinglé au canal **privé** )</span><span class="sxs-lookup"><span data-stu-id="96489-168">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="96489-169">Planificateur (épinglé au canal **privé** )</span><span class="sxs-lookup"><span data-stu-id="96489-169">Planner (pinned to the **Private** channel)</span></span> </li> </ul><br><span data-ttu-id="96489-170">Propriétés d’équipe</span><span class="sxs-lookup"><span data-stu-id="96489-170">Team properties</span></span> <ul><li><span data-ttu-id="96489-171">Visibilité de l’équipe définie sur privée</span><span class="sxs-lookup"><span data-stu-id="96489-171">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="96489-172">\* Canaux avec favoris automatique</span><span class="sxs-lookup"><span data-stu-id="96489-172">\*Auto-favorited channels</span></span>

<span data-ttu-id="96489-173">Pour créer l’équipe finance en prédéfinissant les valeurs par défaut du modèle prédéfini, fournissez la représentation JSON de l’objet équipe dans le corps de la requête.</span><span class="sxs-lookup"><span data-stu-id="96489-173">To create the Finance team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="96489-174">Pour en savoir plus sur le déploiement de modèles d’équipes, voir l' [article Microsoft Graph sur la création d’une équipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="96489-174">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="96489-175">Demande</span><span class="sxs-lookup"><span data-stu-id="96489-175">Request</span></span> 
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

### <a name="example-finance-team-template-extension-script"></a><span data-ttu-id="96489-176">Exemple : script d’extension du modèle d’équipe finance</span><span class="sxs-lookup"><span data-stu-id="96489-176">Example: Finance Team template extension script</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="96489-177">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="96489-177">Related topics</span></span>

- [<span data-ttu-id="96489-178">Prise en main des modèles Teams</span><span class="sxs-lookup"><span data-stu-id="96489-178">Get started with Teams templates</span></span>](get-started-with-teams-templates.md)
- <span data-ttu-id="96489-179">[Créer une équipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (en Preview)</span><span class="sxs-lookup"><span data-stu-id="96489-179">[Create team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (in preview)</span></span>

