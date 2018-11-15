---
title: Commencer avec les modèles d’équipe
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
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
ms.openlocfilehash: 151a789b6047540071aa5780fb81a895503dd70b
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531015"
---
# <a name="get-started-with-teams-templates"></a><span data-ttu-id="66a4b-103">Commencer avec les modèles d’équipe</span><span class="sxs-lookup"><span data-stu-id="66a4b-103">Get started with Teams templates</span></span> 

<span data-ttu-id="66a4b-104">Définitions de structure d’une équipe conçu autour d’un projet ou les besoins de l’entreprise, les modèles d’équipe sont prédéfinies.</span><span class="sxs-lookup"><span data-stu-id="66a4b-104">Team templates are pre-built definitions of a team's structure designed around a business need or project.</span></span> <span data-ttu-id="66a4b-105">Vous pouvez utiliser les modèles d’équipe pour créer rapidement des espaces de collaboration riche avec des canaux pour les différentes rubriques et préinstaller les applications pour extraire des services et contenu critique.</span><span class="sxs-lookup"><span data-stu-id="66a4b-105">You can use team templates to quickly create rich collaboration spaces with channels for different topics and preinstall apps to pull in mission-critical content and services.</span></span> <span data-ttu-id="66a4b-106">Les modèles d’équipe fournissent une structure de l’équipe prédéfinies qui peut vous aider à créer facilement des équipes cohérentes au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="66a4b-106">Team templates provide a predefined team structure that can help you easily create consistent teams across your organization.</span></span> 

<span data-ttu-id="66a4b-107">Dans cet article, nous expliquerons les propriétés qui peuvent être définies dans des modèles, le modèle de base sont de types, et comment vous pouvez utiliser quelques exemples de demandes pour créer une équipe à partir d’un modèle.</span><span class="sxs-lookup"><span data-stu-id="66a4b-107">In this article, we'll explain the properties that can be defined in templates, what base template types are, and how you can use a few sample requests to create a team from a template.</span></span>
 
<span data-ttu-id="66a4b-108">Cet article est pour vous si vous êtes :</span><span class="sxs-lookup"><span data-stu-id="66a4b-108">This article is for you if you're:</span></span>

<span data-ttu-id="66a4b-109">• Responsable de la planification, le déploiement et la gestion de plusieurs équipes sur le développeur de votre organisation • une recherche pour créer une équipe avec prédéfinies canaux et applications par programme</span><span class="sxs-lookup"><span data-stu-id="66a4b-109">•   Responsible for planning, deploying, and managing multiple teams across your organization •   A developer looking to create a team with predefined channels and apps programmatically</span></span>

## <a name="team-template-capabilities"></a><span data-ttu-id="66a4b-110">Fonctionnalités de modèle d’équipe</span><span class="sxs-lookup"><span data-stu-id="66a4b-110">Team template capabilities</span></span>

<span data-ttu-id="66a4b-111">La plupart des propriétés dans une équipe sont inclus et pris en charge par les modèles.</span><span class="sxs-lookup"><span data-stu-id="66a4b-111">Most properties in a team are included and supported by templates.</span></span> <span data-ttu-id="66a4b-112">Toutefois, il existe quelques propriétés et les fonctionnalités qui ne sont actuellement pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="66a4b-112">However, there are a few properties and features that are currently not supported.</span></span> <span data-ttu-id="66a4b-113">Le tableau suivant fournit un résumé rapide de contenu, et ce qui n’est pas inclus dans les modèles d’équipe.</span><span class="sxs-lookup"><span data-stu-id="66a4b-113">The following table provides a quick summary of what's included and what's not included in Teams templates.</span></span>

| <span data-ttu-id="66a4b-114">**Propriétés de l’équipe pris en charge par les modèles d’équipe**</span><span class="sxs-lookup"><span data-stu-id="66a4b-114">**Team properties supported by Teams templates**</span></span> | <span data-ttu-id="66a4b-115">**Propriétés de l’équipe n’est pas encore pris en charge par les modèles d’équipe**</span><span class="sxs-lookup"><span data-stu-id="66a4b-115">**Team properties not yet supported by Teams templates**</span></span> |
| ------------------------------------------------ | -------------------------------------------------------- |
| <span data-ttu-id="66a4b-116">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="66a4b-116">Base template type</span></span> | <span data-ttu-id="66a4b-117">Appartenance de l’équipe</span><span class="sxs-lookup"><span data-stu-id="66a4b-117">Team membership</span></span> |
| <span data-ttu-id="66a4b-118">Nom de l'équipe</span><span class="sxs-lookup"><span data-stu-id="66a4b-118">Team name</span></span> | <span data-ttu-id="66a4b-119">Image de l’équipe</span><span class="sxs-lookup"><span data-stu-id="66a4b-119">Team picture</span></span> |
| <span data-ttu-id="66a4b-120">Description de l’équipe</span><span class="sxs-lookup"><span data-stu-id="66a4b-120">Team description</span></span> | <span data-ttu-id="66a4b-121">Paramètres de canal (par exemple, auto-favori et confidentialité)</span><span class="sxs-lookup"><span data-stu-id="66a4b-121">Channel settings (for example, auto-favorite and privacy)</span></span> |
| <span data-ttu-id="66a4b-122">Visibilité de l’équipe (publique ou privée)</span><span class="sxs-lookup"><span data-stu-id="66a4b-122">Team visibility (public or private)</span></span> | <span data-ttu-id="66a4b-123">Connecteurs</span><span class="sxs-lookup"><span data-stu-id="66a4b-123">Connectors</span></span> |
| <span data-ttu-id="66a4b-124">Paramètres d’équipe (par exemple, membre, invité, @ mentions)</span><span class="sxs-lookup"><span data-stu-id="66a4b-124">Team settings (for example, member, guest, @ mentions)</span></span> | <span data-ttu-id="66a4b-125">Fichiers et contenu</span><span class="sxs-lookup"><span data-stu-id="66a4b-125">Files and content</span></span> |
| <span data-ttu-id="66a4b-126">Canal automatique-favoris</span><span class="sxs-lookup"><span data-stu-id="66a4b-126">Auto-favorite channel</span></span> | |
| <span data-ttu-id="66a4b-127">Application installée</span><span class="sxs-lookup"><span data-stu-id="66a4b-127">Installed app</span></span> | |
| <span data-ttu-id="66a4b-128">Onglets affichés</span><span class="sxs-lookup"><span data-stu-id="66a4b-128">Pinned tabs</span></span> | | 

> [!NOTE]
> <span data-ttu-id="66a4b-129">Nous allons ajouter davantage de fonctionnalités de modèle dans les versions futures de Microsoft Teams, donc vérifier les informations les plus récentes sur les propriétés prises en charge.</span><span class="sxs-lookup"><span data-stu-id="66a4b-129">We'll be adding more template capabilities in future releases of Microsoft Teams, so check back for the most up-to-date information on supported properties.</span></span>

## <a name="what-are-base-template-types"></a><span data-ttu-id="66a4b-130">Quels sont les types de modèle de base ?</span><span class="sxs-lookup"><span data-stu-id="66a4b-130">What are base template types?</span></span>

<span data-ttu-id="66a4b-131">Types de modèle de base des modèles spéciales créé par Microsoft pour industries spécifiques.</span><span class="sxs-lookup"><span data-stu-id="66a4b-131">Base template types are special templates that Microsoft created for specific industries.</span></span> <span data-ttu-id="66a4b-132">Ces modèles de base contiennent souvent des applications qui ne sont pas disponibles dans les propriétés du magasin et l’équipe n’est pas encore individuellement pris en charge dans les modèles d’équipe.</span><span class="sxs-lookup"><span data-stu-id="66a4b-132">These base templates often contain proprietary apps that aren't available in the store and team properties not yet supported individually in Teams templates.</span></span>

<span data-ttu-id="66a4b-133">Une fois qu’un type de modèle de base est défini, vous pouvez étendre ou remplacer ces modèles spéciaux avec les propriétés supplémentaires que vous souhaitez spécifier.</span><span class="sxs-lookup"><span data-stu-id="66a4b-133">Once a base template type is defined, you can extend or override these special templates with additional properties that you'd like to specify.</span></span> <span data-ttu-id="66a4b-134">Toutefois, certains types de modèle de base contiennent des propriétés qui ne peut pas être remplacées.</span><span class="sxs-lookup"><span data-stu-id="66a4b-134">However, some base template types contain properties that can't be overridden.</span></span> 

<span data-ttu-id="66a4b-135">Par défaut, le modèle de base est défini à **Standard** qui ne contient pas les applications propriétaires supplémentaires ou des propriétés spéciales.</span><span class="sxs-lookup"><span data-stu-id="66a4b-135">By default the base template is set to **Standard** which doesn't contain any additional proprietary apps or special properties.</span></span> <span data-ttu-id="66a4b-136">Voici la liste actuelle des types de modèles de base disponibles.</span><span class="sxs-lookup"><span data-stu-id="66a4b-136">Below is the current list of base templates types available.</span></span>

| <span data-ttu-id="66a4b-137">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="66a4b-137">Base template type</span></span> | <span data-ttu-id="66a4b-138">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="66a4b-138">baseTemplateId</span></span> | <span data-ttu-id="66a4b-139">Applications propriétaires de modèle de base et des propriétés spéciales</span><span class="sxs-lookup"><span data-stu-id="66a4b-139">Base template proprietary apps and special properties</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="66a4b-140">Standard</span><span class="sxs-lookup"><span data-stu-id="66a4b-140">Standard</span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json) | <span data-ttu-id="66a4b-141">Aucune propriétés et applications supplémentaires</span><span class="sxs-lookup"><span data-stu-id="66a4b-141">No additional apps and properties</span></span> |
| <span data-ttu-id="66a4b-142">Prestataires - coordination de soins</span><span class="sxs-lookup"><span data-stu-id="66a4b-142">Healthcare - care coordination</span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-CC.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-CC.json#) | <span data-ttu-id="66a4b-143">Applications :</span><span class="sxs-lookup"><span data-stu-id="66a4b-143">Apps:</span></span><br/> <span data-ttu-id="66a4b-144">-Application patients (épinglée sur l’onglet **Général** )</span><span class="sxs-lookup"><span data-stu-id="66a4b-144">- Patients app (pinned to the **General** tab)</span></span><br/> <br/><span data-ttu-id="66a4b-145">Canaux :</span><span class="sxs-lookup"><span data-stu-id="66a4b-145">Channels:</span></span> <br/> <span data-ttu-id="66a4b-146">-Annonces</span><span class="sxs-lookup"><span data-stu-id="66a4b-146">- Announcements</span></span><br/> <span data-ttu-id="66a4b-147">-DIABETE</span><span class="sxs-lookup"><span data-stu-id="66a4b-147">- Diabetes</span></span><br/> <span data-ttu-id="66a4b-148">-Des</span><span class="sxs-lookup"><span data-stu-id="66a4b-148">- Cardiovascular</span></span><br/> <span data-ttu-id="66a4b-149">-Registered personnel</span><span class="sxs-lookup"><span data-stu-id="66a4b-149">- Registered nurses</span></span> |
| <span data-ttu-id="66a4b-150">Prestataires - processus clin de œil</span><span class="sxs-lookup"><span data-stu-id="66a4b-150">Healthcare - process huddle</span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-PH.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-PH.json#) | <span data-ttu-id="66a4b-151">Canaux :</span><span class="sxs-lookup"><span data-stu-id="66a4b-151">Channels:</span></span><br/> <span data-ttu-id="66a4b-152">-Évitables décès</span><span class="sxs-lookup"><span data-stu-id="66a4b-152">- Avoidable deaths</span></span><br/> <span data-ttu-id="66a4b-153">-Passer en revue les mortalité</span><span class="sxs-lookup"><span data-stu-id="66a4b-153">- Mortality review</span></span> <br/> <span data-ttu-id="66a4b-154">-Prévention des appartient à</span><span class="sxs-lookup"><span data-stu-id="66a4b-154">- Preventing falls</span></span> <br/> <span data-ttu-id="66a4b-155">-Plans SEPSIE</span><span class="sxs-lookup"><span data-stu-id="66a4b-155">- Sepsis plans</span></span> |
| <span data-ttu-id="66a4b-156">Formation - classe équipe<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="66a4b-156">Education - Class team<sup>1</sup></span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-CT.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-CT.json#) | <span data-ttu-id="66a4b-157">Applications :</span><span class="sxs-lookup"><span data-stu-id="66a4b-157">Apps:</span></span><br/> <span data-ttu-id="66a4b-158">-OneNote classe bloc-notes (épinglés sur l’onglet **Général** )</span><span class="sxs-lookup"><span data-stu-id="66a4b-158">- OneNote Class Notebook (pinned to the **General** tab)</span></span> <br/> <span data-ttu-id="66a4b-159">-Application affectations (épinglée sur l’onglet **Général** )</span><span class="sxs-lookup"><span data-stu-id="66a4b-159">- Assignments app (pinned to the **General** tab)</span></span> <br/><br/> <span data-ttu-id="66a4b-160">Propriétés de l’équipe</span><span class="sxs-lookup"><span data-stu-id="66a4b-160">Team properties</span></span> <br/> <span data-ttu-id="66a4b-161">-Visibilité de l’équipe valeur **HiddenMembership** (ne peut pas être modifiée)</span><span class="sxs-lookup"><span data-stu-id="66a4b-161">- Team visibility set to **HiddenMembership** (cannot be overridden)</span></span> |
| <span data-ttu-id="66a4b-162">Formation - personnel de l’équipe<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="66a4b-162">Education - Staff team<sup>1</sup></span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-ST.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-ST.json#) | <span data-ttu-id="66a4b-163">Applications</span><span class="sxs-lookup"><span data-stu-id="66a4b-163">Apps</span></span><br/> <span data-ttu-id="66a4b-164">-Bloc-notes personnel (épinglés sur l’onglet **Général** )</span><span class="sxs-lookup"><span data-stu-id="66a4b-164">- OneNote Staff Notebook (pinned to the **General** tab)</span></span> |

<span data-ttu-id="66a4b-165">Publication en retard de 2018, octobre <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="66a4b-165"><sup>1</sup> Publication in late October, 2018</span></span>

> [!NOTE]
> <span data-ttu-id="66a4b-166">Nous allons ajouter d’autres modèle de base de types dans les futures versions de Microsoft Teams, afin de rechercher dans les informations les plus récentes sur les propriétés prises en charge.</span><span class="sxs-lookup"><span data-stu-id="66a4b-166">We'll be adding more base template types in future releases of Microsoft Teams, so check back for the most up-to-date information on supported properties.</span></span>

## <a name="examples"></a><span data-ttu-id="66a4b-167">Exemples</span><span class="sxs-lookup"><span data-stu-id="66a4b-167">Examples</span></span> 

<span data-ttu-id="66a4b-168">Vous pouvez commencer à créer une équipe via le modèle à l’installation de [Microsoft Graph](https://developer.microsoft.com/en-us/graph/docs/concepts/overview).</span><span class="sxs-lookup"><span data-stu-id="66a4b-168">You can start creating a team via template by installing [Microsoft Graph](https://developer.microsoft.com/en-us/graph/docs/concepts/overview).</span></span>

### <a name="create-a-team-from-a-template"></a><span data-ttu-id="66a4b-169">Créer une équipe à partir d’un modèle</span><span class="sxs-lookup"><span data-stu-id="66a4b-169">Create a team from a template</span></span>

#### <a name="requests"></a><span data-ttu-id="66a4b-170">Demandes</span><span class="sxs-lookup"><span data-stu-id="66a4b-170">Requests</span></span>

<span data-ttu-id="66a4b-171">**Demande de création d’une équipe avec le modèle de base standard**</span><span class="sxs-lookup"><span data-stu-id="66a4b-171">**Request to create a team with the standard base template**</span></span>

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
    
    "teamDisplayName": "My Sample Team",
    "teamDescription": "My Sample Team’s Description",
}

~~~

<span data-ttu-id="66a4b-172">**Demande de créer une équipe avec un canal supplémentaire et ne pas autoriser les membres de supprimer des canaux**</span><span class="sxs-lookup"><span data-stu-id="66a4b-172">**Request to create a team with an extra channel and disallow members from deleting channels**</span></span>

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
    
    "teamDisplayName": "My Sample Team",
    "teamDescription": "My Sample Team’s Description",
    "channels": [
        {
            "displayName": "Interns",
            "autoFavorite": false
        }
    ],
    "memberSettings": {
        "allowDeleteChannels": false,
    }
}

~~~

<span data-ttu-id="66a4b-173">**Demande de création d’une équipe avec toutes les propriétés prises en charge**</span><span class="sxs-lookup"><span data-stu-id="66a4b-173">**Request to create a team with all supported properties**</span></span>

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
 
    "teamType": "Healthcare_CareCoordination",
    "visibility": "Private",
    "teamDisplayName": "My Care Team",
    "teamDescription": "My Care Team’s description",
 
    "channels": [
        {
            "displayName": "General  ",
            "autoFavorite": true,
            "tabs": [
                   {
                       "appId": "0d820ecd-def2-4297-adad-78056cde7c78",
                       "tabDisplayName": "Intranet”
                   }
               ]
        },
        {
            "displayName": "Announcements",
            "autoFavorite": true
        },
        {
            "displayName": "Diabetes",
            "autoFavorite": true
        },
        {
            "displayName": "Cardiovascular",
            "autoFavorite": true
        },
        {
            "displayName": "Registered Nurses",
            "autoFavorite": true
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
 
      "messagingSettings": {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
      },
 
      "funSettings": {
        "allowGiphy": true,
        "giphyContentRating": "moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
      }
 
 
    "installedApplications": [
      {
        "id": "0d820ecd-def2-4297-adad-78056cde7c78"
      }
    ]
}
~~~

#### <a name="response"></a><span data-ttu-id="66a4b-174">Réponse</span><span class="sxs-lookup"><span data-stu-id="66a4b-174">Response</span></span>

~~~
HTTP/1.1 202 Accepted
Content-Type: application/json
Location: /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
{
    "workflowId": "c953c202-7b44-4a63-aa33-364fcb2d65aa",
    "statusUri": "https://<apihostandpath>/workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa"
}
~~~

### <a name="get-status"></a><span data-ttu-id="66a4b-175">Obtenir l’état</span><span class="sxs-lookup"><span data-stu-id="66a4b-175">Get status</span></span>

#### <a name="request"></a><span data-ttu-id="66a4b-176">Demande</span><span class="sxs-lookup"><span data-stu-id="66a4b-176">Request</span></span>

~~~
GET   /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
Authorization: Bearer <TOKEN>
~~~

#### <a name="response"></a><span data-ttu-id="66a4b-177">Réponse</span><span class="sxs-lookup"><span data-stu-id="66a4b-177">Response</span></span>

~~~
HTTP/1.1 200 OK
Content-Type: application/json
{
    "status": "[InProgress|Completed|Cancelled|Failed]"
}
~~~

## <a name="related-topics"></a><span data-ttu-id="66a4b-178">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="66a4b-178">Related topics</span></span>

- <span data-ttu-id="66a4b-179">[Équipe de création](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/team_put_teams) (en aperçu)</span><span class="sxs-lookup"><span data-stu-id="66a4b-179">[Create team](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/team_put_teams) (in preview)</span></span>
- [<span data-ttu-id="66a4b-180">Nouvelle équipe</span><span class="sxs-lookup"><span data-stu-id="66a4b-180">New-Team</span></span>](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [<span data-ttu-id="66a4b-181">Formation à Microsoft Teams pour les administrateurs</span><span class="sxs-lookup"><span data-stu-id="66a4b-181">Admin training for Microsoft Teams</span></span>](itadmin-readiness.md)