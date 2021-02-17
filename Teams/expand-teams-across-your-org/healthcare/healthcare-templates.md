---
title: Modèles pour les organisations de soins de santé
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Utilisez les modèles Microsoft Teams avec Microsoft Graph pour créer rapidement et facilement des équipes en fournissant un modèle prédéféré de paramètres, de canaux et d’applications.
ms.custom: seo-marvel-mar2020
ROBOTS: NOINDEX
ms.openlocfilehash: e288bc68c8160fb80d4e56a6477437e0a79fea0a
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260336"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a><span data-ttu-id="22596-103">Commencer à utiliser les modèles Teams pour les organismes de santé</span><span class="sxs-lookup"><span data-stu-id="22596-103">Get started with Teams templates for healthcare organizations</span></span>

<span data-ttu-id="22596-104">Les modèles Microsoft Teams vous permettent de créer rapidement et facilement des équipes en fournissant un modèle prédéféré de paramètres, de canaux et d’applications préinstallées.</span><span class="sxs-lookup"><span data-stu-id="22596-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="22596-105">Pour les organisations de santé, les modèles peuvent être particulièrement puissants, car ils structurent les utilisateurs pour s’orienter dans l’utilisation efficace de Teams.</span><span class="sxs-lookup"><span data-stu-id="22596-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Teams.</span></span> <span data-ttu-id="22596-106">Les modèles permettent également aux administrateurs de déployer des équipes cohérentes au sein de leur organisation.</span><span class="sxs-lookup"><span data-stu-id="22596-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="22596-107">Cet article est pour vous si vous êtes responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation de soins de santé.</span><span class="sxs-lookup"><span data-stu-id="22596-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your healthcare organization.</span></span>

<span data-ttu-id="22596-108">Nous proposons actuellement deux modèles de soins de santé à usage unique, que vous pouvez utiliser dans différentes situations.</span><span class="sxs-lookup"><span data-stu-id="22596-108">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="22596-109">Pour en savoir plus sur les modèles d’équipe en général, voir [Commencer à utiliser les modèles Teams.](../../get-started-with-teams-templates.md)</span><span class="sxs-lookup"><span data-stu-id="22596-109">To learn more about team templates in general, see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span>

## <a name="ward-template"></a><span data-ttu-id="22596-110">Modèle Template</span><span class="sxs-lookup"><span data-stu-id="22596-110">Ward template</span></span>

<span data-ttu-id="22596-111">Le modèle sont conçus pour la communication et la collaboration au sein d’un service, d’un groupe ou d’un service.</span><span class="sxs-lookup"><span data-stu-id="22596-111">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="22596-112">Le modèle peut être utilisé pour faciliter la gestion des patients, ainsi que pour répondre aux besoins opérationnels d’une équipe.</span><span class="sxs-lookup"><span data-stu-id="22596-112">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="22596-113">Par exemple, les annonces de groupe peuvent être publiées dans le canal *Annonces* et les shifts peuvent être gérés dans *staffing.*</span><span class="sxs-lookup"><span data-stu-id="22596-113">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="22596-114">Si vous cherchez à simplifier vos opérations de simplification, ce modèle est pour vous.</span><span class="sxs-lookup"><span data-stu-id="22596-114">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="22596-115">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="22596-115">Base Template Type</span></span> |<span data-ttu-id="22596-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="22596-116">baseTemplateId</span></span> |<span data-ttu-id="22596-117">Canaux de modèle de référence</span><span class="sxs-lookup"><span data-stu-id="22596-117">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="22596-118">Soins de santé -Desso</span><span class="sxs-lookup"><span data-stu-id="22596-118">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="22596-119">Annonces\*</span><span class="sxs-lookup"><span data-stu-id="22596-119">Announcements\*</span></span> <br> <span data-ttu-id="22596-120">Bldles\*</span><span class="sxs-lookup"><span data-stu-id="22596-120">Huddles\*</span></span> <br> <span data-ttu-id="22596-121">Arrondit\*</span><span class="sxs-lookup"><span data-stu-id="22596-121">Rounds\*</span></span> <br> <span data-ttu-id="22596-122">Personnel\*</span><span class="sxs-lookup"><span data-stu-id="22596-122">Staffing\*</span></span> <br> <span data-ttu-id="22596-123">Formation\*</span><span class="sxs-lookup"><span data-stu-id="22596-123">Training\*</span></span> |
|     | |         |

<span data-ttu-id="22596-124">\* Favoris automatiques</span><span class="sxs-lookup"><span data-stu-id="22596-124">\* Auto-favorited</span></span>

## <a name="hospital-template"></a><span data-ttu-id="22596-125">Modèle d’hôpital</span><span class="sxs-lookup"><span data-stu-id="22596-125">Hospital template</span></span>

<span data-ttu-id="22596-126">Le modèle de l’hôpital est destiné à la communication et à la collaboration entre plusieurs gardiens, pods et services au sein d’un hôpital.</span><span class="sxs-lookup"><span data-stu-id="22596-126">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="22596-127">Plusieurs canaux opérationnels sont inclus dans ce modèle, notamment Les *annonces,* Les Événements et Les Précédents, mais nous fournissons également un script ci-dessous qui étend le modèle avec toute une série de canaux supplémentaires ou spécialisés que vous pouvez ajouter, supprimer ou modifier à votre convenance.</span><span class="sxs-lookup"><span data-stu-id="22596-127">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="22596-128">Par exemple, si vous avez un service de *Quézy,* mais que vous n’avez  pas besoin de canal pour Acécédant, le script peut être adapté afin d’inclure un canal #A0 et de supprimer le canal acédant. </span><span class="sxs-lookup"><span data-stu-id="22596-128">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="22596-129">Nous recommandons que ces canaux spécialisés ou modelés ne soient pas marqués automatiquement pour éviter une saturation des notifications.</span><span class="sxs-lookup"><span data-stu-id="22596-129">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="22596-130">Généralement, les utilisateurs préfèrent les canaux qu’ils trouvent pertinents.</span><span class="sxs-lookup"><span data-stu-id="22596-130">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="22596-131">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="22596-131">Base Template Type</span></span> |<span data-ttu-id="22596-132">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="22596-132">baseTemplateId</span></span> |<span data-ttu-id="22596-133">Canaux de modèle de référence</span><span class="sxs-lookup"><span data-stu-id="22596-133">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="22596-134">Soins de santé - Hôpital</span><span class="sxs-lookup"><span data-stu-id="22596-134">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="22596-135">Annonces\*</span><span class="sxs-lookup"><span data-stu-id="22596-135">Announcements\*</span></span> <br> <span data-ttu-id="22596-136">Conformité\*</span><span class="sxs-lookup"><span data-stu-id="22596-136">Compliance\*</span></span> <br> <span data-ttu-id="22596-137">Adess</span><span class="sxs-lookup"><span data-stu-id="22596-137">Custodial</span></span> <br> <span data-ttu-id="22596-138">Ressources humaines</span><span class="sxs-lookup"><span data-stu-id="22596-138">Human Resources</span></span> <br> <span data-ttu-id="22596-139">Desse</span><span class="sxs-lookup"><span data-stu-id="22596-139">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="22596-140">\* Favoris automatiques</span><span class="sxs-lookup"><span data-stu-id="22596-140">\* Auto-favorited</span></span> 

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="22596-141">Comment utiliser des modèles tiers</span><span class="sxs-lookup"><span data-stu-id="22596-141">How to use first-party templates</span></span>

<span data-ttu-id="22596-142">Pour utiliser ces modèles, modifiez simplement la propriété « template@odata.bind » dans le corps de la demande de « standard » à la propriété TemplateIDs ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="22596-142">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="22596-143">Pour plus d’informations sur le déploiement de modèles Teams, voir l’article Microsoft Graph sur la création [d’une équipe.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="22596-143">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="22596-144">Les canaux du modèle sont automatiquement créés sous l’onglet Général.</span><span class="sxs-lookup"><span data-stu-id="22596-144">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="22596-145">Exemple : Script d’extension de modèle d’hôpital</span><span class="sxs-lookup"><span data-stu-id="22596-145">Example: Hospital template extension script</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="22596-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="22596-146">Related topics</span></span>

[<span data-ttu-id="22596-147">Prise en main des modèles Teams</span><span class="sxs-lookup"><span data-stu-id="22596-147">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="22596-148">Prise en main de Teams pour les organismes de santé</span><span class="sxs-lookup"><span data-stu-id="22596-148">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)

[<span data-ttu-id="22596-149">Commencer à utiliser les modèles Teams dans la console d’administration</span><span class="sxs-lookup"><span data-stu-id="22596-149">Get started with Teams templates in the admin console</span></span>](../../get-started-with-teams-templates-in-the-admin-console.md)
