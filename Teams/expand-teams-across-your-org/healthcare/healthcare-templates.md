---
title: Démarrage avec les modèles Teams pour les organismes de santé
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Démarrage avec les modèles Teams pour les organismes de santé
ms.openlocfilehash: 38b2067bc91a79ff2efa8bc20726ad14d793aa24
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32245881"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a><span data-ttu-id="56332-103">Démarrage avec les modèles Teams pour les organismes de santé</span><span class="sxs-lookup"><span data-stu-id="56332-103">Get started with Teams templates for Healthcare organizations</span></span>

<span data-ttu-id="56332-104">Modèles Microsoft Teams permettent de rapidement et facilement créer des équipes en fournissant un modèle prédéfini de paramètres, les canaux et applications préinstallées.</span><span class="sxs-lookup"><span data-stu-id="56332-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="56332-105">Pour les organisations de santé, les modèles peuvent être particulièrement puissantes, comme leur fournissent une structure pour les utilisateurs de devenir orienté avec comment exploiter au mieux les équipes efficacement.</span><span class="sxs-lookup"><span data-stu-id="56332-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to best leverage Teams effectively.</span></span> <span data-ttu-id="56332-106">Les modèles permettent également aux administrateurs de déployer des équipes cohérentes entre leurs organisations.</span><span class="sxs-lookup"><span data-stu-id="56332-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="56332-107">Si vous êtes responsable de la planification, le déploiement et la gestion de plusieurs équipes au sein de votre organisation prestataires, cet article est pour vous.</span><span class="sxs-lookup"><span data-stu-id="56332-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your Healthcare organization.</span></span>

<span data-ttu-id="56332-108">Nous actuellement offre deux première partie prestataires modèles que vous pouvez exploiter pour de nombreuses situations.</span><span class="sxs-lookup"><span data-stu-id="56332-108">We currently offer two first party healthcare templates that you can leverage for a variety of situations.</span></span> <span data-ttu-id="56332-109">Pour en savoir plus sur l’équipe modèles en général, consultez [mise en route les modèles d’équipe](../../get-started-with-teams-templates.md).</span><span class="sxs-lookup"><span data-stu-id="56332-109">To learn more about team templates in general, please see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span>

## <a name="ward-template"></a><span data-ttu-id="56332-110">Modèle comté</span><span class="sxs-lookup"><span data-stu-id="56332-110">Ward template</span></span>

<span data-ttu-id="56332-111">Le modèle comté est destiné à la communication et de collaboration au sein d’un comté, module ou par service.</span><span class="sxs-lookup"><span data-stu-id="56332-111">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="56332-112">Le modèle peut être utilisé afin de faciliter la gestion des patients, ainsi que des besoins opérationnels d’une comté.</span><span class="sxs-lookup"><span data-stu-id="56332-112">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="56332-113">Par exemple, annonces comté peuvent être publiés dans le canal *annonces* et équipes peuvent être gérés dans *personnel*.</span><span class="sxs-lookup"><span data-stu-id="56332-113">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="56332-114">Si vous avez besoin pour simplifier vos opérations comté, ce modèle est pour vous.</span><span class="sxs-lookup"><span data-stu-id="56332-114">If you’re looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="56332-115">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="56332-115">Base Template Type</span></span> |<span data-ttu-id="56332-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="56332-116">baseTemplateId</span></span> |<span data-ttu-id="56332-117">Canaux de modèle de base</span><span class="sxs-lookup"><span data-stu-id="56332-117">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="56332-118">Prestataires - comté</span><span class="sxs-lookup"><span data-stu-id="56332-118">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="56332-119">Annonces\*</span><span class="sxs-lookup"><span data-stu-id="56332-119">Announcements\*</span></span> <br> <span data-ttu-id="56332-120">Huddles\*</span><span class="sxs-lookup"><span data-stu-id="56332-120">Huddles\*</span></span> <br> <span data-ttu-id="56332-121">Arrondit\*</span><span class="sxs-lookup"><span data-stu-id="56332-121">Rounds\*</span></span> <br> <span data-ttu-id="56332-122">Personnel\*</span><span class="sxs-lookup"><span data-stu-id="56332-122">Staffing\*</span></span> <br> <span data-ttu-id="56332-123">Formation\*</span><span class="sxs-lookup"><span data-stu-id="56332-123">Training\*</span></span> |
|     | |         |

<span data-ttu-id="56332-124">\*Auto-favorited</span><span class="sxs-lookup"><span data-stu-id="56332-124">\* Auto-favorited</span></span>

## <a name="hospital-template"></a><span data-ttu-id="56332-125">Modèle hôpital</span><span class="sxs-lookup"><span data-stu-id="56332-125">Hospital template</span></span>

<span data-ttu-id="56332-126">Le modèle hôpital est destiné à la communication et la collaboration entre plusieurs départements au sein d’un hôpital, modules et longtemps.</span><span class="sxs-lookup"><span data-stu-id="56332-126">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="56332-127">Inclus dans ce modèle sont plusieurs chaînes opérationnelles notamment *annonces*, *Custodial*et *pharmacie*, mais nous fournissons également un script ci-dessous qui étend le modèle avec une variété de service supplémentaires ou canaux centrées spécialisés que vous pouvez ajouter, supprimer ou modifier à votre convenance.</span><span class="sxs-lookup"><span data-stu-id="56332-127">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="56332-128">Par exemple, si vous avez un service *Endocrinology* , mais que vous n’avez pas besoin un canal pour *ophtalmologie*, le script peut être adapté pour inclure une couche *Endocrinology* et de supprimer le canal *ophtalmologie* .</span><span class="sxs-lookup"><span data-stu-id="56332-128">For example, if you have an *Endocrinology* department, but don’t need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="56332-129">Nous recommandons que ces spécialisés ou des canaux modélisés comté ne pas favorited automatique pour éviter la saturation de la notification.</span><span class="sxs-lookup"><span data-stu-id="56332-129">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="56332-130">Utilisateurs sont généralement Favoris les canaux qu’ils rencontrent pertinentes.</span><span class="sxs-lookup"><span data-stu-id="56332-130">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="56332-131">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="56332-131">Base Template Type</span></span> |<span data-ttu-id="56332-132">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="56332-132">baseTemplateId</span></span> |<span data-ttu-id="56332-133">Canaux de modèle de base</span><span class="sxs-lookup"><span data-stu-id="56332-133">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="56332-134">Prestataires - hôpital</span><span class="sxs-lookup"><span data-stu-id="56332-134">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="56332-135">Annonces\*</span><span class="sxs-lookup"><span data-stu-id="56332-135">Announcements\*</span></span> <br> <span data-ttu-id="56332-136">Conformité\*</span><span class="sxs-lookup"><span data-stu-id="56332-136">Compliance\*</span></span> <br> <span data-ttu-id="56332-137">Garde</span><span class="sxs-lookup"><span data-stu-id="56332-137">Custodial</span></span> <br> <span data-ttu-id="56332-138">Ressources humaines</span><span class="sxs-lookup"><span data-stu-id="56332-138">Human Resources</span></span> <br> <span data-ttu-id="56332-139">Pharmacie</span><span class="sxs-lookup"><span data-stu-id="56332-139">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="56332-140">\*Auto-favorited</span><span class="sxs-lookup"><span data-stu-id="56332-140">\* Auto-favorited</span></span> 

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="56332-141">Comment utiliser des modèles de première partie</span><span class="sxs-lookup"><span data-stu-id="56332-141">How to use first party templates</span></span>

<span data-ttu-id="56332-142">Pour utiliser ces modèles, modifiez simplement la propriété 'template@odata.bind' dans le corps de la demande à partir de « standard » pour la TemplateIDs ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="56332-142">To use these templates, simply change the ‘template@odata.bind’ property in the request body from ‘standard’ to the TemplateIDs above.</span></span>  <span data-ttu-id="56332-143">Pour plus d’informations sur la façon de déployer les modèles d’équipe, voir [l’article sur la création d’une équipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="56332-143">For more information on how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="56332-144">Les canaux dans le modèle seront automatiquement créées sous l’onglet Général.</span><span class="sxs-lookup"><span data-stu-id="56332-144">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="56332-145">Exemple : Script d’extension hôpital modèle</span><span class="sxs-lookup"><span data-stu-id="56332-145">Example: Hospital template extension script</span></span>

``` Powershell
{ 
          "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('healthcareHospital')",
          "DisplayName": "Contoso Hospital",
          "Description": "Team for all staff in Contoso Hospital",
          "Channels": [
            {
              "displayName": "Ambulatory",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Anesthesiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Cardiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "CCU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ear, Nose, and Throat",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Emergency Care",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Family Medicine",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Gynecology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "ICU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Mother-Baby",
              "IsFavoriteByDefault": false
            }, 
            {
              "displayName": "Neonatal",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Neurology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Oncology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ophthalmology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "PACU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Psychiatric",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Radiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Rehabilitation",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Surgical",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Urology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Women’s Health",
              "IsFavoriteByDefault": false
            }
          ],
          "Apps": [
            {
              "Id": "1542629c-01b3-4a6d-8f76-1938b779e48d"
            }
          ]
          }

```

## <a name="related-topics"></a><span data-ttu-id="56332-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="56332-146">Related topics</span></span>

[<span data-ttu-id="56332-147">Prise en main des modèles Teams</span><span class="sxs-lookup"><span data-stu-id="56332-147">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="56332-148">Prise en main de Teams pour les organismes de santé</span><span class="sxs-lookup"><span data-stu-id="56332-148">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)
