---
title: Modèles d’organisations de santé
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Utilisez les modèles de Microsoft teams pour créer rapidement et facilement des équipes en fournissant un modèle prédéfini de paramètres, de canaux et d’applications.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f2ef6bd4bf358a90654e7fda643effbfcc34b3c2
ms.sourcegitcommit: 340c2f432b78af4e78b21056af56c6421627045d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294434"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations-using-microsoft-graph"></a><span data-ttu-id="5372f-103">Premiers pas dans les modèles teams pour les établissements de santé utilisant Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="5372f-103">Get started with Teams templates for Healthcare organizations using Microsoft Graph</span></span>

<span data-ttu-id="5372f-104">Les modèles Microsoft teams vous permettent de créer rapidement et facilement des équipes en fournissant un modèle prédéfini de paramètres, de canaux et d’applications préinstallées.</span><span class="sxs-lookup"><span data-stu-id="5372f-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="5372f-105">Pour les entreprises de santé, les modèles peuvent être particulièrement puissants, car ils permettent aux utilisateurs de se familiariser avec l’utilisation efficace d’équipes.</span><span class="sxs-lookup"><span data-stu-id="5372f-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Teams.</span></span> <span data-ttu-id="5372f-106">Les modèles permettent également aux administrateurs de déployer des équipes cohérentes au sein de leurs organisations.</span><span class="sxs-lookup"><span data-stu-id="5372f-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="5372f-107">Cet article est pour vous si vous êtes responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation de santé.</span><span class="sxs-lookup"><span data-stu-id="5372f-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your Healthcare organization.</span></span>

<span data-ttu-id="5372f-108">Pour l’instant, nous proposons deux modèles de soins de santé que vous pouvez utiliser pour différentes situations.</span><span class="sxs-lookup"><span data-stu-id="5372f-108">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="5372f-109">Pour en savoir plus sur les modèles d’équipe en général, voir [prendre en main les modèles](../../get-started-with-teams-templates.md)Teams.</span><span class="sxs-lookup"><span data-stu-id="5372f-109">To learn more about team templates in general, see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span>

## <a name="ward-template"></a><span data-ttu-id="5372f-110">Modèle vers le haut</span><span class="sxs-lookup"><span data-stu-id="5372f-110">Ward template</span></span>

<span data-ttu-id="5372f-111">Le modèle à l’envers est destiné à la communication et à la collaboration dans une direction, une pod ou un service.</span><span class="sxs-lookup"><span data-stu-id="5372f-111">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="5372f-112">Le modèle peut être utilisé pour faciliter la gestion du patient, ainsi que pour les besoins de fonctionnement de a à l’envers.</span><span class="sxs-lookup"><span data-stu-id="5372f-112">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="5372f-113">Par exemple, les annonces à l’envers peuvent être publiées dans le canal *annonces* et les équipes peuvent être gérées en *équipe*.</span><span class="sxs-lookup"><span data-stu-id="5372f-113">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="5372f-114">Si vous cherchez à rationaliser vos opérations à l’envers, ce modèle vous appartient.</span><span class="sxs-lookup"><span data-stu-id="5372f-114">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="5372f-115">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="5372f-115">Base Template Type</span></span> |<span data-ttu-id="5372f-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="5372f-116">baseTemplateId</span></span> |<span data-ttu-id="5372f-117">Canaux de modèles de base</span><span class="sxs-lookup"><span data-stu-id="5372f-117">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="5372f-118">Soins de santé-au</span><span class="sxs-lookup"><span data-stu-id="5372f-118">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="5372f-119">Annonces\*</span><span class="sxs-lookup"><span data-stu-id="5372f-119">Announcements\*</span></span> <br> <span data-ttu-id="5372f-120">Huddles\*</span><span class="sxs-lookup"><span data-stu-id="5372f-120">Huddles\*</span></span> <br> <span data-ttu-id="5372f-121">Négative\*</span><span class="sxs-lookup"><span data-stu-id="5372f-121">Rounds\*</span></span> <br> <span data-ttu-id="5372f-122">Spécifient\*</span><span class="sxs-lookup"><span data-stu-id="5372f-122">Staffing\*</span></span> <br> <span data-ttu-id="5372f-123">Formation\*</span><span class="sxs-lookup"><span data-stu-id="5372f-123">Training\*</span></span> |
|     | |         |

<span data-ttu-id="5372f-124">\* Favoris automatique</span><span class="sxs-lookup"><span data-stu-id="5372f-124">\* Auto-favorited</span></span>

## <a name="hospital-template"></a><span data-ttu-id="5372f-125">Modèle d’hôpital</span><span class="sxs-lookup"><span data-stu-id="5372f-125">Hospital template</span></span>

<span data-ttu-id="5372f-126">Le modèle d’hôpital est destiné à la communication et à la collaboration entre divers services, modules et services d’un hôpital.</span><span class="sxs-lookup"><span data-stu-id="5372f-126">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="5372f-127">Il s’agit de nombreux canaux opérationnels, y compris les *annonces*, la *privative*d’emploi et la *pharmacie*, mais nous proposons également un script ci-dessous qui étend le modèle à un large éventail de canaux centrés sur des services ou des spécialisations, que vous pouvez ajouter, supprimer ou modifier selon vos souhaits.</span><span class="sxs-lookup"><span data-stu-id="5372f-127">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="5372f-128">Par exemple, si vous avez un service *Endocrinology* , mais que vous n’avez pas besoin d’un canal pour *Ophthalmology*, le script peut être adapté pour inclure un canal *Endocrinology* et supprimer le canal *Ophthalmology* .</span><span class="sxs-lookup"><span data-stu-id="5372f-128">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="5372f-129">Nous vous conseillons de ne pas ajouter de favoris automatique pour ces canaux spécialisés ou les canaux à l’envers.</span><span class="sxs-lookup"><span data-stu-id="5372f-129">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="5372f-130">En général, les utilisateurs favoris sont les canaux qu’ils recherchent.</span><span class="sxs-lookup"><span data-stu-id="5372f-130">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="5372f-131">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="5372f-131">Base Template Type</span></span> |<span data-ttu-id="5372f-132">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="5372f-132">baseTemplateId</span></span> |<span data-ttu-id="5372f-133">Canaux de modèles de base</span><span class="sxs-lookup"><span data-stu-id="5372f-133">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="5372f-134">Healthcare-hôpital</span><span class="sxs-lookup"><span data-stu-id="5372f-134">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="5372f-135">Annonces\*</span><span class="sxs-lookup"><span data-stu-id="5372f-135">Announcements\*</span></span> <br> <span data-ttu-id="5372f-136">Conformité\*</span><span class="sxs-lookup"><span data-stu-id="5372f-136">Compliance\*</span></span> <br> <span data-ttu-id="5372f-137">Privatives de Troie</span><span class="sxs-lookup"><span data-stu-id="5372f-137">Custodial</span></span> <br> <span data-ttu-id="5372f-138">Ressources humaines</span><span class="sxs-lookup"><span data-stu-id="5372f-138">Human Resources</span></span> <br> <span data-ttu-id="5372f-139">Pharmaceutiques</span><span class="sxs-lookup"><span data-stu-id="5372f-139">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="5372f-140">\* Favoris automatique</span><span class="sxs-lookup"><span data-stu-id="5372f-140">\* Auto-favorited</span></span> 

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="5372f-141">Utiliser les modèles de parties tierces</span><span class="sxs-lookup"><span data-stu-id="5372f-141">How to use first-party templates</span></span>

<span data-ttu-id="5372f-142">Pour utiliser ces modèles, il vous suffit de changer la propriété « template@odata. bind » dans le corps de la requête de « standard » vers le TemplateIDs ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="5372f-142">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="5372f-143">Pour plus d’informations sur le déploiement de modèles d’équipe, voir l’article Microsoft Graph sur la [création d’une équipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="5372f-143">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="5372f-144">Les canaux du modèle sont automatiquement créés sous l’onglet général.</span><span class="sxs-lookup"><span data-stu-id="5372f-144">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="5372f-145">Exemple : script d’extension de modèle d’hôpital</span><span class="sxs-lookup"><span data-stu-id="5372f-145">Example: Hospital template extension script</span></span>

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
              "displayName": "Women's Health",
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

## <a name="related-topics"></a><span data-ttu-id="5372f-146">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="5372f-146">Related topics</span></span>

[<span data-ttu-id="5372f-147">Prise en main des modèles Teams</span><span class="sxs-lookup"><span data-stu-id="5372f-147">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="5372f-148">Prise en main de Teams pour les organismes de santé</span><span class="sxs-lookup"><span data-stu-id="5372f-148">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)

[<span data-ttu-id="5372f-149">Commencer à utiliser les modèles teams dans la console d’administration</span><span class="sxs-lookup"><span data-stu-id="5372f-149">Get started with Teams templates in the admin console</span></span>](../../get-started-with-teams-templates-in-the-admin-console.md)
