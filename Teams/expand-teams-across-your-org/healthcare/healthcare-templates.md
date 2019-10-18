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
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Démarrage avec les modèles Teams pour les organismes de santé
ms.openlocfilehash: df917c3a6f1cbf20c9226dd58e4706c4c0e3bc2c
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570346"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a><span data-ttu-id="7e984-103">Démarrage avec les modèles Teams pour les organismes de santé</span><span class="sxs-lookup"><span data-stu-id="7e984-103">Get started with Teams templates for Healthcare organizations</span></span>

<span data-ttu-id="7e984-104">Les modèles Microsoft teams vous permettent de créer rapidement et facilement des équipes en fournissant un modèle prédéfini de paramètres, de canaux et d’applications préinstallées.</span><span class="sxs-lookup"><span data-stu-id="7e984-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="7e984-105">Pour les entreprises de santé, les modèles peuvent être particulièrement puissants, car ils permettent aux utilisateurs de se familiariser avec l’utilisation des équipes efficacement.</span><span class="sxs-lookup"><span data-stu-id="7e984-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to best leverage Teams effectively.</span></span> <span data-ttu-id="7e984-106">Les modèles permettent également aux administrateurs de déployer des équipes cohérentes au sein de leurs organisations.</span><span class="sxs-lookup"><span data-stu-id="7e984-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="7e984-107">Cet article est pour vous si vous êtes responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation de santé.</span><span class="sxs-lookup"><span data-stu-id="7e984-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your Healthcare organization.</span></span>

<span data-ttu-id="7e984-108">Nous proposons actuellement deux modèles de soins de santé que vous pouvez utiliser pour différentes situations.</span><span class="sxs-lookup"><span data-stu-id="7e984-108">We currently offer two first party healthcare templates that you can leverage for a variety of situations.</span></span> <span data-ttu-id="7e984-109">Pour en savoir plus sur les modèles d’équipe en général, voir [prendre en main les modèles](../../get-started-with-teams-templates.md)Teams.</span><span class="sxs-lookup"><span data-stu-id="7e984-109">To learn more about team templates in general, please see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span>

## <a name="ward-template"></a><span data-ttu-id="7e984-110">Modèle vers le haut</span><span class="sxs-lookup"><span data-stu-id="7e984-110">Ward template</span></span>

<span data-ttu-id="7e984-111">Le modèle à l’envers est destiné à la communication et à la collaboration dans une direction, une pod ou un service.</span><span class="sxs-lookup"><span data-stu-id="7e984-111">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="7e984-112">Le modèle peut être utilisé pour faciliter la gestion du patient, ainsi que pour les besoins de fonctionnement de a à l’envers.</span><span class="sxs-lookup"><span data-stu-id="7e984-112">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="7e984-113">Par exemple, les annonces à l’envers peuvent être publiées dans le canal *annonces* et les équipes peuvent être gérées en *équipe*.</span><span class="sxs-lookup"><span data-stu-id="7e984-113">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="7e984-114">Si vous cherchez à rationaliser vos opérations à l’envers, ce modèle vous appartient.</span><span class="sxs-lookup"><span data-stu-id="7e984-114">If you’re looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="7e984-115">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="7e984-115">Base Template Type</span></span> |<span data-ttu-id="7e984-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="7e984-116">baseTemplateId</span></span> |<span data-ttu-id="7e984-117">Canaux de modèles de base</span><span class="sxs-lookup"><span data-stu-id="7e984-117">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="7e984-118">Soins de santé-au</span><span class="sxs-lookup"><span data-stu-id="7e984-118">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="7e984-119">Annonces\*</span><span class="sxs-lookup"><span data-stu-id="7e984-119">Announcements\*</span></span> <br> <span data-ttu-id="7e984-120">Huddles\*</span><span class="sxs-lookup"><span data-stu-id="7e984-120">Huddles\*</span></span> <br> <span data-ttu-id="7e984-121">Négative\*</span><span class="sxs-lookup"><span data-stu-id="7e984-121">Rounds\*</span></span> <br> <span data-ttu-id="7e984-122">Spécifient\*</span><span class="sxs-lookup"><span data-stu-id="7e984-122">Staffing\*</span></span> <br> <span data-ttu-id="7e984-123">Formation\*</span><span class="sxs-lookup"><span data-stu-id="7e984-123">Training\*</span></span> |
|     | |         |

<span data-ttu-id="7e984-124">\*Favoris automatique</span><span class="sxs-lookup"><span data-stu-id="7e984-124">\* Auto-favorited</span></span>

## <a name="hospital-template"></a><span data-ttu-id="7e984-125">Modèle d’hôpital</span><span class="sxs-lookup"><span data-stu-id="7e984-125">Hospital template</span></span>

<span data-ttu-id="7e984-126">Le modèle d’hôpital est destiné à la communication et à la collaboration entre divers services, modules et services d’un hôpital.</span><span class="sxs-lookup"><span data-stu-id="7e984-126">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="7e984-127">Inclus dans ce modèle sont des canaux opérationnels, y compris les *annonces*, la *privative*d’emploi et la *pharmacie*, mais nous proposons également un script ci-dessous qui étend le modèle à un large éventail de services supplémentaires ou canaux centrés sur les spécialisations que vous pouvez ajouter, supprimer ou modifier selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="7e984-127">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="7e984-128">Par exemple, si vous avez un service *Endocrinology* , mais que vous n’avez pas besoin d’un canal pour *Ophthalmology*, le script peut être adapté pour inclure un canal *Endocrinology* et supprimer le canal *Ophthalmology* .</span><span class="sxs-lookup"><span data-stu-id="7e984-128">For example, if you have an *Endocrinology* department, but don’t need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="7e984-129">Nous vous conseillons de ne pas ajouter de favoris automatique pour ces canaux spécialisés ou les canaux à l’envers.</span><span class="sxs-lookup"><span data-stu-id="7e984-129">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="7e984-130">En général, les utilisateurs favoris sont les canaux qu’ils recherchent.</span><span class="sxs-lookup"><span data-stu-id="7e984-130">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="7e984-131">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="7e984-131">Base Template Type</span></span> |<span data-ttu-id="7e984-132">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="7e984-132">baseTemplateId</span></span> |<span data-ttu-id="7e984-133">Canaux de modèles de base</span><span class="sxs-lookup"><span data-stu-id="7e984-133">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="7e984-134">Healthcare-hôpital</span><span class="sxs-lookup"><span data-stu-id="7e984-134">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="7e984-135">Annonces\*</span><span class="sxs-lookup"><span data-stu-id="7e984-135">Announcements\*</span></span> <br> <span data-ttu-id="7e984-136">Conformément\*</span><span class="sxs-lookup"><span data-stu-id="7e984-136">Compliance\*</span></span> <br> <span data-ttu-id="7e984-137">Privatives de Troie</span><span class="sxs-lookup"><span data-stu-id="7e984-137">Custodial</span></span> <br> <span data-ttu-id="7e984-138">Ressources humaines</span><span class="sxs-lookup"><span data-stu-id="7e984-138">Human Resources</span></span> <br> <span data-ttu-id="7e984-139">Pharmaceutiques</span><span class="sxs-lookup"><span data-stu-id="7e984-139">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="7e984-140">\*Favoris automatique</span><span class="sxs-lookup"><span data-stu-id="7e984-140">\* Auto-favorited</span></span> 

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="7e984-141">Utilisation de modèles de première partie</span><span class="sxs-lookup"><span data-stu-id="7e984-141">How to use first party templates</span></span>

<span data-ttu-id="7e984-142">Pour utiliser ces modèles, il suffit de changer la propriété « template@odata.bind » dans le corps de la requête de « standard » en TemplateIDs ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="7e984-142">To use these templates, simply change the ‘template@odata.bind’ property in the request body from ‘standard’ to the TemplateIDs above.</span></span>  <span data-ttu-id="7e984-143">Pour plus d’informations sur le déploiement de modèles d’équipe, voir l’article Microsoft Graph sur la [création d’une équipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="7e984-143">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="7e984-144">Les canaux du modèle sont automatiquement créés sous l’onglet général.</span><span class="sxs-lookup"><span data-stu-id="7e984-144">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="7e984-145">Exemple : script d’extension de modèle d’hôpital</span><span class="sxs-lookup"><span data-stu-id="7e984-145">Example: Hospital template extension script</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="7e984-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7e984-146">Related topics</span></span>

[<span data-ttu-id="7e984-147">Prise en main des modèles Teams</span><span class="sxs-lookup"><span data-stu-id="7e984-147">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="7e984-148">Prise en main de Teams pour les organismes de santé</span><span class="sxs-lookup"><span data-stu-id="7e984-148">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)
