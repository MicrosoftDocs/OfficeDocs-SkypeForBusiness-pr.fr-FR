---
title: Commencer avec les modèles d’équipe
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/10/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
localization_priority: Normal
robots: NOINDEX, NOFOLLOW
search.appverid: MET150
description: Découvrez comment utiliser les modèles d’équipe pour créer une équipe avec des canaux prédéfinis.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: ead0a3dc9e27b90c49808bcece0aab39bf01f13a
ms.sourcegitcommit: 4c5b9e8c4bdb1187d610209d365680702d4372fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/11/2019
ms.locfileid: "27801463"
---
# <a name="get-started-with-teams-templates"></a><span data-ttu-id="cd879-103">Commencer avec les modèles d’équipe</span><span class="sxs-lookup"><span data-stu-id="cd879-103">Get started with Teams templates</span></span> 

<span data-ttu-id="cd879-104">Définitions de structure d’une équipe conçu autour d’un projet ou les besoins de l’entreprise, les modèles d’équipe sont prédéfinies.</span><span class="sxs-lookup"><span data-stu-id="cd879-104">Teams templates are pre-built definitions of a team's structure designed around a business need or project.</span></span> <span data-ttu-id="cd879-105">Vous pouvez utiliser les modèles d’équipe pour créer rapidement des espaces de collaboration riche avec des canaux pour les différentes rubriques et préinstaller les applications pour extraire des services et contenu critique.</span><span class="sxs-lookup"><span data-stu-id="cd879-105">You can use Teams templates to quickly create rich collaboration spaces with channels for different topics and preinstall apps to pull in mission-critical content and services.</span></span> <span data-ttu-id="cd879-106">Les modèles d’équipe fournissent une structure de l’équipe prédéfinies qui peut vous aider à créer facilement des équipes cohérentes au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="cd879-106">Teams templates provide a predefined team structure that can help you easily create consistent teams across your organization.</span></span> 

<span data-ttu-id="cd879-107">Dans cet article, nous expliquerons les propriétés qui peuvent être définies dans des modèles, le modèle de base sont de types, et comment vous pouvez utiliser quelques exemples de demandes pour créer une équipe à partir d’un modèle.</span><span class="sxs-lookup"><span data-stu-id="cd879-107">In this article, we'll explain the properties that can be defined in templates, what base template types are, and how you can use a few sample requests to create a team from a template.</span></span>
 
<span data-ttu-id="cd879-108">Cet article est pour vous si vous êtes :</span><span class="sxs-lookup"><span data-stu-id="cd879-108">This article is for you if you're:</span></span>

- <span data-ttu-id="cd879-109">Responsable de la planification, le déploiement et la gestion de plusieurs équipes au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="cd879-109">Responsible for planning, deploying, and managing multiple teams across your organization</span></span><br>
- <span data-ttu-id="cd879-110">Un pour les développeurs souhaitant créer par programme une équipe avec les applications et les canaux prédéfinis</span><span class="sxs-lookup"><span data-stu-id="cd879-110">A developer wanting to programmatically create a team with predefined channels and apps</span></span> 

## <a name="teams-template-capabilities"></a><span data-ttu-id="cd879-111">Fonctionnalités de modèle d’équipes</span><span class="sxs-lookup"><span data-stu-id="cd879-111">Teams template capabilities</span></span>

<span data-ttu-id="cd879-112">La plupart des propriétés dans une équipe sont inclus et pris en charge par les modèles.</span><span class="sxs-lookup"><span data-stu-id="cd879-112">Most properties in a team are included and supported by templates.</span></span> <span data-ttu-id="cd879-113">Mais il existe quelques propriétés et les fonctionnalités qui ne sont pas actuellement pris en charge.</span><span class="sxs-lookup"><span data-stu-id="cd879-113">But there are a few properties and features that are not currently supported.</span></span> <span data-ttu-id="cd879-114">Le tableau suivant fournit un résumé rapide de contenu, et ce qui n’est pas inclus dans les modèles d’équipe.</span><span class="sxs-lookup"><span data-stu-id="cd879-114">The following table provides a quick summary of what's included and what's not included in Teams templates.</span></span>

| <span data-ttu-id="cd879-115">**Propriétés de l’équipe pris en charge par les modèles d’équipe**</span><span class="sxs-lookup"><span data-stu-id="cd879-115">**Team properties supported by Teams templates**</span></span> | <span data-ttu-id="cd879-116">**Propriétés de l’équipe n’est pas encore pris en charge par les modèles d’équipe**</span><span class="sxs-lookup"><span data-stu-id="cd879-116">**Team properties not yet supported by Teams templates**</span></span> |
| ------------------------------------------------ | -------------------------------------------------------- |
| <span data-ttu-id="cd879-117">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="cd879-117">Base template type</span></span> | <span data-ttu-id="cd879-118">Appartenance de l’équipe</span><span class="sxs-lookup"><span data-stu-id="cd879-118">Team membership</span></span> |
| <span data-ttu-id="cd879-119">Nom de l'équipe</span><span class="sxs-lookup"><span data-stu-id="cd879-119">Team name</span></span> | <span data-ttu-id="cd879-120">Image de l’équipe</span><span class="sxs-lookup"><span data-stu-id="cd879-120">Team picture</span></span> |
| <span data-ttu-id="cd879-121">Description de l’équipe</span><span class="sxs-lookup"><span data-stu-id="cd879-121">Team description</span></span> | <span data-ttu-id="cd879-122">Paramètres de canal</span><span class="sxs-lookup"><span data-stu-id="cd879-122">Channel settings</span></span> |
| <span data-ttu-id="cd879-123">Visibilité de l’équipe (publique ou privée)</span><span class="sxs-lookup"><span data-stu-id="cd879-123">Team visibility (public or private)</span></span> | <span data-ttu-id="cd879-124">Connecteurs</span><span class="sxs-lookup"><span data-stu-id="cd879-124">Connectors</span></span> |
| <span data-ttu-id="cd879-125">Paramètres d’équipe (par exemple, membre, invité, @ mentions)</span><span class="sxs-lookup"><span data-stu-id="cd879-125">Team settings (for example, member, guest, @ mentions)</span></span> | <span data-ttu-id="cd879-126">Fichiers et contenu</span><span class="sxs-lookup"><span data-stu-id="cd879-126">Files and content</span></span> |
| <span data-ttu-id="cd879-127">Canal automatique-favoris</span><span class="sxs-lookup"><span data-stu-id="cd879-127">Auto-favorite channel</span></span> | |
| <span data-ttu-id="cd879-128">Application installée</span><span class="sxs-lookup"><span data-stu-id="cd879-128">Installed app</span></span> | |
| <span data-ttu-id="cd879-129">Onglets affichés</span><span class="sxs-lookup"><span data-stu-id="cd879-129">Pinned tabs</span></span> | | 

> [!NOTE]
> <span data-ttu-id="cd879-130">Nous allons ajouter davantage de fonctionnalités de modèle dans les versions futures de Microsoft Teams, donc vérifier les informations les plus récentes sur les propriétés prises en charge.</span><span class="sxs-lookup"><span data-stu-id="cd879-130">We'll be adding more template capabilities in future releases of Microsoft Teams, so check back for the most up-to-date information on supported properties.</span></span>

## <a name="what-are-base-template-types"></a><span data-ttu-id="cd879-131">Quels sont les types de modèle de base ?</span><span class="sxs-lookup"><span data-stu-id="cd879-131">What are base template types?</span></span>

<span data-ttu-id="cd879-132">Types de modèle de base des modèles spéciales créé par Microsoft pour industries spécifiques.</span><span class="sxs-lookup"><span data-stu-id="cd879-132">Base template types are special templates that Microsoft created for specific industries.</span></span> <span data-ttu-id="cd879-133">Ces modèles de base contiennent souvent des applications qui ne sont pas disponibles dans les propriétés du magasin et l’équipe pas encore pris en charge individuellement dans les modèles d’équipe.</span><span class="sxs-lookup"><span data-stu-id="cd879-133">These base templates often contain proprietary apps that aren't available in the store and team properties that are not yet supported individually in Teams templates.</span></span>

<span data-ttu-id="cd879-134">Une fois qu’un type de modèle de base est défini, vous pouvez étendre ou remplacer ces modèles spéciaux avec les propriétés supplémentaires que vous souhaitez spécifier.</span><span class="sxs-lookup"><span data-stu-id="cd879-134">Once a base template type is defined, you can extend or override these special templates with additional properties that you'd like to specify.</span></span> <span data-ttu-id="cd879-135">Mais certains types de modèle de base contiennent des propriétés qui ne peut pas être remplacées.</span><span class="sxs-lookup"><span data-stu-id="cd879-135">But some base template types contain properties that can't be overridden.</span></span> 

<span data-ttu-id="cd879-136">Par défaut, le modèle de base est défini à **Standard** qui ne contient pas les applications propriétaires supplémentaires ou des propriétés spéciales.</span><span class="sxs-lookup"><span data-stu-id="cd879-136">By default the base template is set to **Standard** which doesn't contain any additional proprietary apps or special properties.</span></span> <span data-ttu-id="cd879-137">Voici la liste actuelle des types de modèles de base disponibles.</span><span class="sxs-lookup"><span data-stu-id="cd879-137">Below is the current list of base templates types available.</span></span>

| <span data-ttu-id="cd879-138">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="cd879-138">Base template type</span></span> | <span data-ttu-id="cd879-139">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="cd879-139">baseTemplateId</span></span> | <span data-ttu-id="cd879-140">Applications propriétaires de modèle de base et des propriétés spéciales</span><span class="sxs-lookup"><span data-stu-id="cd879-140">Base template proprietary apps and special properties</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="cd879-141">Standard</span><span class="sxs-lookup"><span data-stu-id="cd879-141">Standard</span></span> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`standard` | <span data-ttu-id="cd879-142">Aucune propriétés et applications supplémentaires</span><span class="sxs-lookup"><span data-stu-id="cd879-142">No additional apps and properties</span></span> |
| <span data-ttu-id="cd879-143">Formation-</span><span class="sxs-lookup"><span data-stu-id="cd879-143">Education -</span></span> <br><span data-ttu-id="cd879-144">Classe de l’équipe<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="cd879-144">Class team<sup>1</sup></span></span> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationClass` | <span data-ttu-id="cd879-145">Applications :</span><span class="sxs-lookup"><span data-stu-id="cd879-145">Apps:</span></span><ul><li><span data-ttu-id="cd879-146">Bloc-notes OneNote de classe (épinglés sur l’onglet **Général** )</span><span class="sxs-lookup"><span data-stu-id="cd879-146">OneNote Class Notebook (pinned to the **General** tab)</span></span> </li><li><span data-ttu-id="cd879-147">Application des affectations (épinglée sur l’onglet **Général** )</span><span class="sxs-lookup"><span data-stu-id="cd879-147">Assignments app (pinned to the **General** tab)</span></span></li></ul> <span data-ttu-id="cd879-148">Propriétés de l’équipe :</span><span class="sxs-lookup"><span data-stu-id="cd879-148">Team properties:</span></span><ul><li><span data-ttu-id="cd879-149">Visibilité de l’équipe définie sur **HiddenMembership** (ne peut pas être modifiée)</span><span class="sxs-lookup"><span data-stu-id="cd879-149">Team visibility set to **HiddenMembership** (cannot be overridden)</span></span></li></ul> |
| <span data-ttu-id="cd879-150">Formation-</span><span class="sxs-lookup"><span data-stu-id="cd879-150">Education -</span></span><br><span data-ttu-id="cd879-151">Personnel de l’équipe<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="cd879-151">Staff team<sup>1</sup></span></span> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationStaff` | <span data-ttu-id="cd879-152">Applications :</span><span class="sxs-lookup"><span data-stu-id="cd879-152">Apps:</span></span><ul><li><span data-ttu-id="cd879-153">Bloc-notes OneNote de personnel (épinglés sur l’onglet **Général** )</span><span class="sxs-lookup"><span data-stu-id="cd879-153">OneNote Staff Notebook (pinned to the **General** tab)</span></span></li></ul> |
|<span data-ttu-id="cd879-154">Formation-</span><span class="sxs-lookup"><span data-stu-id="cd879-154">Education -</span></span><br><span data-ttu-id="cd879-155">Équipe PLC</span><span class="sxs-lookup"><span data-stu-id="cd879-155">PLC team</span></span> |`https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationProfessionalLearningCommunity` | <span data-ttu-id="cd879-156">Applications :</span><span class="sxs-lookup"><span data-stu-id="cd879-156">Apps:</span></span><ul><li><span data-ttu-id="cd879-157">Bloc-notes OneNote de PLC (épinglés sur l’onglet **Général** )</span><span class="sxs-lookup"><span data-stu-id="cd879-157">OneNote PLC Notebook (pinned to the **General** tab)</span></span></ul></li>|
|||

<span data-ttu-id="cd879-158">Publication en retard de 2018, octobre <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="cd879-158"><sup>1</sup> Publication in late October, 2018</span></span>

> [!NOTE]
> <span data-ttu-id="cd879-159">Nous allons ajouter d’autres modèle de base de types dans les futures versions de Microsoft Teams, afin de rechercher dans les informations les plus récentes sur les propriétés prises en charge.</span><span class="sxs-lookup"><span data-stu-id="cd879-159">We'll be adding more base template types in future releases of Microsoft Teams, so check back for the most up-to-date information on supported properties.</span></span>

## <a name="examples"></a><span data-ttu-id="cd879-160">Exemples</span><span class="sxs-lookup"><span data-stu-id="cd879-160">Examples</span></span> 

<span data-ttu-id="cd879-161">Vous pouvez démarrer à l’aide d’un modèle pour créer une équipe à l’aide de l' [API de Microsoft Graph](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="cd879-161">You can start using a template to create a team by using the [Microsoft Graph API](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

### <a name="create-a-team-from-a-template"></a><span data-ttu-id="cd879-162">Créer une équipe à partir d’un modèle</span><span class="sxs-lookup"><span data-stu-id="cd879-162">Create a team from a template</span></span>

#### <a name="requests"></a><span data-ttu-id="cd879-163">Demandes</span><span class="sxs-lookup"><span data-stu-id="cd879-163">Requests</span></span>

<span data-ttu-id="cd879-164">**Demande de création d’une équipe avec le modèle de base standard**</span><span class="sxs-lookup"><span data-stu-id="cd879-164">**Request to create a team with the standard base template**</span></span>

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates/standard",
  "displayName": "Sample Team",
  "description": "Sample Team’s Description"
}

~~~

<span data-ttu-id="cd879-165">**Demande de créer une équipe avec un canal supplémentaire et ne pas autoriser les membres de supprimer des canaux**</span><span class="sxs-lookup"><span data-stu-id="cd879-165">**Request to create a team with an extra channel and disallow members from deleting channels**</span></span>

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates/standard",
  "displayName": "My Sample Team",
  "description": "My Sample Team’s Description",
  "channels": [
    {
        "displayName": "Random",
        "isFavoriteByDefault": true
    }
              ],
    "memberSettings": {
        "allowDeleteChannels": false
    }
}

~~~

<span data-ttu-id="cd879-166">**Demande de création d’une équipe avec toutes les propriétés prises en charge**</span><span class="sxs-lookup"><span data-stu-id="cd879-166">**Request to create a team with all supported properties**</span></span>

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('standard')",
    "visibility": "Private",
    "displayName": "Sample Engineering Team",
    "description": "This is a sample engineering team, used to showcase the range of properties 
supported by this API",
    "channels": [
        {
            "displayName": "Announcements 📢",
            "isFavoriteByDefault": true,
            "description": "This is a sample announcements channel that is favorited by default. Use this 
channel to make important team, product, and service announcements."
        },
        {
            "displayName": "Training 🏋️",
            "isFavoriteByDefault": true,
            "description": "This is a sample training channel that is favorited by default and contains an 
example of pinned website and YouTube tabs.",
            "tabs": [
                {
                    "teamsApp@odata.bind":
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.web')",
                   "name": "A Pinned Website",
                    "configuration": {
                        "contentUrl": "https://docs.microsoft.com/en-us/microsoftteams/microsoft-teams"
                    }
                },
                {
                    "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.youtube')",
                    "name": "A Pinned YouTube Video",
                    "configuration": {
                        "contentUrl": "https://tabs.teams.microsoft.com/Youtube/Home/YoutubeTab?
videoId=X8krAMdGvCQ",
                        "websiteUrl": "https://www.youtube.com/watch?v=X8krAMdGvCQ"
                    }
                }
            ]
        },
        {
"displayName": "Planning 📅 ",
            "description": "This is a sample of a channel that is not favorited by default, these channels 
will appear in the more channels overflow menu.",
            "isFavoriteByDefault": false
        },
        {
            "displayName": "Issues and Feedback 🐞",
            "description": "This is a sample of a channel that is not favorited by default, these channels 
will appear in the more channels overflow menu."
        }
    ],
    "memberSettings": {
        "allowCreateUpdateChannels": true,
        "allowDeleteChannels": true,
        "allowAddRemoveApps": true,
        "allowCreateUpdateRemoveTabs": true,
        "allowCreateUpdateRemoveConnectors": true
    },
    "guestSettings": {
        "allowCreateUpdateChannels": false,
        "allowDeleteChannels": false
    },
    "funSettings": {
        "allowGiphy": true,
        "giphyContentRating": "Moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
    },
    "messagingSettings": {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
    },
    "installedApps": [
        {
            "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.vsts')"
        },
        {
            "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('1542629c-01b3-4a6d-8f76-1938b779e48d')"
        }
    ]
}
~~~

### <a name="get-status"></a><span data-ttu-id="cd879-167">Obtenir l’état</span><span class="sxs-lookup"><span data-stu-id="cd879-167">Get status</span></span>

#### <a name="request"></a><span data-ttu-id="cd879-168">Demande</span><span class="sxs-lookup"><span data-stu-id="cd879-168">Request</span></span>

~~~
GET   /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
Authorization: Bearer <TOKEN>
~~~

#### <a name="response"></a><span data-ttu-id="cd879-169">Réponse</span><span class="sxs-lookup"><span data-stu-id="cd879-169">Response</span></span>

~~~
HTTP/1.1 200 OK
Content-Type: application/json
{
    "status": "[InProgress|Completed|Cancelled|Failed]"
}
~~~

## <a name="related-topics"></a><span data-ttu-id="cd879-170">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="cd879-170">Related topics</span></span>

- <span data-ttu-id="cd879-171">[Équipe de création](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (en aperçu)</span><span class="sxs-lookup"><span data-stu-id="cd879-171">[Create team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (in preview)</span></span>
- [<span data-ttu-id="cd879-172">Nouvelle équipe</span><span class="sxs-lookup"><span data-stu-id="cd879-172">New-Team</span></span>](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [<span data-ttu-id="cd879-173">Formation à Microsoft Teams pour les administrateurs</span><span class="sxs-lookup"><span data-stu-id="cd879-173">Admin training for Microsoft Teams</span></span>](itadmin-readiness.md)