---
title: Créer une équipe à l’aide de modèles Médicaux Teams
author: cichur
ms.author: v-cichur
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
description: Utilisez les modèles Microsoft Teams dans le Centre d’administration ou avec Microsoft Graph pour créer rapidement et facilement des équipes en fournissant un modèle prédéféré de paramètres, de canaux et d’applications.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b45c949b70aa2a299f2aafe54d81cdd8a1a6c0b5
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260306"
---
# <a name="create-a-team-using-teams-healthcare-templates"></a><span data-ttu-id="4810f-103">Créer une équipe à l’aide de modèles médicaux Teams</span><span class="sxs-lookup"><span data-stu-id="4810f-103">Create a team using Teams healthcare templates</span></span>

<span data-ttu-id="4810f-104">Les modèles Microsoft Teams vous permettent de créer rapidement et facilement des équipes en fournissant un modèle prédéféré de paramètres, de canaux et d’applications préinstallées.</span><span class="sxs-lookup"><span data-stu-id="4810f-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="4810f-105">Pour les organisations de santé, les modèles peuvent être particulièrement puissants, car ils structurent les utilisateurs pour s’orienter dans l’utilisation efficace de Teams.</span><span class="sxs-lookup"><span data-stu-id="4810f-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Teams.</span></span> <span data-ttu-id="4810f-106">Les modèles permettent également aux administrateurs de déployer des équipes cohérentes au sein de leur organisation.</span><span class="sxs-lookup"><span data-stu-id="4810f-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="4810f-107">Cet article est pour vous si vous êtes responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation de soins de santé.</span><span class="sxs-lookup"><span data-stu-id="4810f-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your healthcare organization.</span></span>

<span data-ttu-id="4810f-108">Choisissez une méthode de création d’équipes avec les modèles Médicaux Teams :</span><span class="sxs-lookup"><span data-stu-id="4810f-108">Choose a method for creating teams with the Teams healthcare templates:</span></span>

| <span data-ttu-id="4810f-109">Qui</span><span class="sxs-lookup"><span data-stu-id="4810f-109">Who</span></span> | <span data-ttu-id="4810f-110">Méthode à utiliser :</span><span class="sxs-lookup"><span data-stu-id="4810f-110">Method to use:</span></span> |
| ---- | --------- |
| <span data-ttu-id="4810f-111">Administrateurs et professionnels de l’informatique</span><span class="sxs-lookup"><span data-stu-id="4810f-111">Admins and IT Professionals</span></span> | <span data-ttu-id="4810f-112">[Utilisez le Centre d’administration Teams pour](#use-the-teams-templates-in-the-teams-admin-center) créer des équipes basées sur les modèles Teams médicaux.</span><span class="sxs-lookup"><span data-stu-id="4810f-112">[Use the Teams admin center](#use-the-teams-templates-in-the-teams-admin-center) to create teams based on the healthcare Teams templates.</span></span>|
| <span data-ttu-id="4810f-113">Développeurs et intégrateurs de systèmes</span><span class="sxs-lookup"><span data-stu-id="4810f-113">Developers and systems integrators</span></span> | <span data-ttu-id="4810f-114">[Utilisez Microsoft Graph pour créer des](#use-the-teams-templates-with-the-microsoft-graph) équipes basées sur les modèles Healthcare Teams.</span><span class="sxs-lookup"><span data-stu-id="4810f-114">[Use the Microsoft Graph](#use-the-teams-templates-with-the-microsoft-graph) to create teams based on the healthcare Teams templates.</span></span> |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a><span data-ttu-id="4810f-115">Utiliser les modèles Teams dans le Centre d’administration Teams</span><span class="sxs-lookup"><span data-stu-id="4810f-115">Use the Teams templates in the Teams admin center</span></span>

<span data-ttu-id="4810f-116">Les administrateurs Microsoft Teams peuvent utiliser le Centre d’administration Teams pour créer des équipes à l’aide des modèles Teams.</span><span class="sxs-lookup"><span data-stu-id="4810f-116">Microsoft Teams admins can use the Teams admin center to create teams with the Teams templates.</span></span> <span data-ttu-id="4810f-117">Nous proposons actuellement deux modèles de soins de santé à usage unique, que vous pouvez utiliser dans différentes situations.</span><span class="sxs-lookup"><span data-stu-id="4810f-117">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="4810f-118">Pour en savoir plus sur les modèles d’équipe en général, voir Commencer à utiliser les [modèles Teams dans le Centre d’administration.](../../get-started-with-teams-templates-in-the-admin-console.md)</span><span class="sxs-lookup"><span data-stu-id="4810f-118">To learn more about team templates in general, see [Get started with Teams templates in the admin center](../../get-started-with-teams-templates-in-the-admin-console.md).</span></span>

### <a name="collaborate-on-patient-care"></a><span data-ttu-id="4810f-119">Collaborer sur les soins des patients</span><span class="sxs-lookup"><span data-stu-id="4810f-119">Collaborate on patient care</span></span>

 <span data-ttu-id="4810f-120">Simplifiez la communication et la collaboration au sein d’un service, d’une équipe ou d’un service.</span><span class="sxs-lookup"><span data-stu-id="4810f-120">Streamline healthcare communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="4810f-121">Le modèle peut être utilisé pour faciliter la gestion des patients et les besoins opérationnels d’une base de données.</span><span class="sxs-lookup"><span data-stu-id="4810f-121">The template can be used to facilitate patient management and operational needs of a ward.</span></span>

| <span data-ttu-id="4810f-122">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="4810f-122">Base template type</span></span> |<span data-ttu-id="4810f-123">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="4810f-123">baseTemplateId</span></span>| <span data-ttu-id="4810f-124">Propriétés de ce modèle de base</span><span class="sxs-lookup"><span data-stu-id="4810f-124">Properties that come with this base template</span></span> |
| ------------------ |---|----------------------------------------------------- |
| <span data-ttu-id="4810f-125">Collaborer sur les soins des patients</span><span class="sxs-lookup"><span data-stu-id="4810f-125">Collaborate on patient care</span></span> |`healthcareWard` | <span data-ttu-id="4810f-126">Canaux :</span><span class="sxs-lookup"><span data-stu-id="4810f-126">Channels:</span></span><ul><li><span data-ttu-id="4810f-127">Général</span><span class="sxs-lookup"><span data-stu-id="4810f-127">General</span></span></li><li><span data-ttu-id="4810f-128">Annonces</span><span class="sxs-lookup"><span data-stu-id="4810f-128">Announcements</span></span></li><li><span data-ttu-id="4810f-129">Bldles</span><span class="sxs-lookup"><span data-stu-id="4810f-129">Huddles</span></span></li><li><span data-ttu-id="4810f-130">Arrondit</span><span class="sxs-lookup"><span data-stu-id="4810f-130">Rounds</span></span></li><li><span data-ttu-id="4810f-131">Personnel</span><span class="sxs-lookup"><span data-stu-id="4810f-131">Staffing</span></span></li><li><span data-ttu-id="4810f-132">Formation</span><span class="sxs-lookup"><span data-stu-id="4810f-132">Training</span></span></li></ul> <span data-ttu-id="4810f-133">Applications :</span><span class="sxs-lookup"><span data-stu-id="4810f-133">Apps:</span></span> <ul><li><span data-ttu-id="4810f-134">Wiki</span><span class="sxs-lookup"><span data-stu-id="4810f-134">Wiki</span></span></li><li><span data-ttu-id="4810f-135">Listes</span><span class="sxs-lookup"><span data-stu-id="4810f-135">Lists</span></span></li></ul>|
||||

### <a name="hospital"></a><span data-ttu-id="4810f-136">Hôpital</span><span class="sxs-lookup"><span data-stu-id="4810f-136">Hospital</span></span>

<span data-ttu-id="4810f-137">Simplifiez la communication et la collaboration entre plusieurs productions, ainsi que des services au sein d’un hôpital.</span><span class="sxs-lookup"><span data-stu-id="4810f-137">Streamline communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="4810f-138">Ce modèle inclut un ensemble de canaux de base pour les opérations en hôpital et peut être étendu eux-mêmes de manière à inclure les tâches spéciales, ad hoc.</span><span class="sxs-lookup"><span data-stu-id="4810f-138">This template includes a set of base channels for hospital operations, and can be self-extended to include specialties, ad-hoc.</span></span>

| <span data-ttu-id="4810f-139">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="4810f-139">Base template type</span></span> |<span data-ttu-id="4810f-140">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="4810f-140">baseTemplateId</span></span> | <span data-ttu-id="4810f-141">Propriétés de ce modèle de base</span><span class="sxs-lookup"><span data-stu-id="4810f-141">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="4810f-142">Hôpital</span><span class="sxs-lookup"><span data-stu-id="4810f-142">Hospital</span></span>|`healthcareHospital`|<span data-ttu-id="4810f-143">Canaux :</span><span class="sxs-lookup"><span data-stu-id="4810f-143">Channels:</span></span> <ul><li><span data-ttu-id="4810f-144">Général</span><span class="sxs-lookup"><span data-stu-id="4810f-144">General</span></span></li><li><span data-ttu-id="4810f-145">Annonces</span><span class="sxs-lookup"><span data-stu-id="4810f-145">Announcements</span></span></li><li><span data-ttu-id="4810f-146">Conformité</span><span class="sxs-lookup"><span data-stu-id="4810f-146">Compliance</span></span></li><li><span data-ttu-id="4810f-147">Adess</span><span class="sxs-lookup"><span data-stu-id="4810f-147">Custodial</span></span></li><li><span data-ttu-id="4810f-148">Ressources humaines</span><span class="sxs-lookup"><span data-stu-id="4810f-148">Human resources</span></span></li><li><span data-ttu-id="4810f-149">Desse</span><span class="sxs-lookup"><span data-stu-id="4810f-149">Pharmacy</span></span></li></ul> <span data-ttu-id="4810f-150">Applications :</span><span class="sxs-lookup"><span data-stu-id="4810f-150">Apps:</span></span> <ul><li><span data-ttu-id="4810f-151">Wiki</span><span class="sxs-lookup"><span data-stu-id="4810f-151">Wiki</span></span></li><li><span data-ttu-id="4810f-152">Listes</span><span class="sxs-lookup"><span data-stu-id="4810f-152">Lists</span></span> </li></ul>|
||||


## <a name="use-the-teams-templates-with-the-microsoft-graph"></a><span data-ttu-id="4810f-153">Utiliser les modèles Teams avec Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="4810f-153">Use the Teams templates with the Microsoft Graph</span></span>

<span data-ttu-id="4810f-154">Les développeurs peuvent utiliser Microsoft Graph pour créer des équipes avec les modèles Teams.</span><span class="sxs-lookup"><span data-stu-id="4810f-154">Developers can use the Microsoft Graph to create teams with the Teams templates.</span></span> <span data-ttu-id="4810f-155">Nous proposons actuellement deux modèles de soins de santé à usage unique, que vous pouvez utiliser dans différentes situations.</span><span class="sxs-lookup"><span data-stu-id="4810f-155">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="4810f-156">Pour en savoir plus sur les modèles d’équipe en général, voir [Commencer à utiliser les modèles Teams.](../../get-started-with-teams-templates.md)</span><span class="sxs-lookup"><span data-stu-id="4810f-156">To learn more about team templates in general, see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span> <span data-ttu-id="4810f-157">Pour plus d’informations sur les modèles Teams et Microsoft Graph, consultez la vue d’ensemble de [l’API Microsoft Teams](https://docs.microsoft.com/graph/teams-concept-overview?view=graph-rest-1.0) et le type de ressource [teamsTemplate.](https://docs.microsoft.com/graph/api/resources/teamstemplate?view=graph-rest-1.0)</span><span class="sxs-lookup"><span data-stu-id="4810f-157">And for information about Teams templates and the Microsoft Graph, see [Microsoft Teams API overview](https://docs.microsoft.com/graph/teams-concept-overview?view=graph-rest-1.0) and [teamsTemplate resource type](https://docs.microsoft.com/graph/api/resources/teamstemplate?view=graph-rest-1.0).</span></span>

### <a name="ward-template"></a><span data-ttu-id="4810f-158">Modèle Template</span><span class="sxs-lookup"><span data-stu-id="4810f-158">Ward template</span></span>

<span data-ttu-id="4810f-159">Le modèle sont conçus pour la communication et la collaboration au sein d’un service, d’un groupe ou d’un service.</span><span class="sxs-lookup"><span data-stu-id="4810f-159">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="4810f-160">Le modèle peut être utilisé pour faciliter la gestion des patients, ainsi que pour répondre aux besoins opérationnels d’une équipe.</span><span class="sxs-lookup"><span data-stu-id="4810f-160">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="4810f-161">Par exemple, les annonces de groupe peuvent être publiées dans le canal *Annonces* et les shifts peuvent être gérés dans *staffing.*</span><span class="sxs-lookup"><span data-stu-id="4810f-161">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="4810f-162">Si vous cherchez à simplifier vos opérations de simplification, ce modèle est pour vous.</span><span class="sxs-lookup"><span data-stu-id="4810f-162">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="4810f-163">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="4810f-163">Base Template Type</span></span> |<span data-ttu-id="4810f-164">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="4810f-164">baseTemplateId</span></span> |<span data-ttu-id="4810f-165">Canaux de modèle de référence</span><span class="sxs-lookup"><span data-stu-id="4810f-165">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="4810f-166">Soins de santé - Unité</span><span class="sxs-lookup"><span data-stu-id="4810f-166">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="4810f-167">Annonces\*</span><span class="sxs-lookup"><span data-stu-id="4810f-167">Announcements\*</span></span> <br> <span data-ttu-id="4810f-168">Bldles\*</span><span class="sxs-lookup"><span data-stu-id="4810f-168">Huddles\*</span></span> <br> <span data-ttu-id="4810f-169">Arrondit\*</span><span class="sxs-lookup"><span data-stu-id="4810f-169">Rounds\*</span></span> <br> <span data-ttu-id="4810f-170">Personnel\*</span><span class="sxs-lookup"><span data-stu-id="4810f-170">Staffing\*</span></span> <br> <span data-ttu-id="4810f-171">Formation\*</span><span class="sxs-lookup"><span data-stu-id="4810f-171">Training\*</span></span> |
|     | |         |

<span data-ttu-id="4810f-172">\* Favoris automatiques</span><span class="sxs-lookup"><span data-stu-id="4810f-172">\* Auto-favorited</span></span>

### <a name="hospital-template"></a><span data-ttu-id="4810f-173">Modèle d’hôpital</span><span class="sxs-lookup"><span data-stu-id="4810f-173">Hospital template</span></span>

<span data-ttu-id="4810f-174">Le modèle de l’hôpital est destiné à la communication et à la collaboration entre plusieurs gardiens, pods et services au sein d’un hôpital.</span><span class="sxs-lookup"><span data-stu-id="4810f-174">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="4810f-175">Plusieurs canaux opérationnels sont inclus dans ce modèle, notamment *Annonces,* Film et Précédez, mais nous fournissons également un script ci-dessous qui étend le modèle avec toute une série de canaux supplémentaires ou spécialisés que vous pouvez ajouter, supprimer ou modifier à votre convenance.</span><span class="sxs-lookup"><span data-stu-id="4810f-175">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="4810f-176">Par exemple, si  vous avez un service de Quézy, mais que vous n’avez pas besoin d’un canal pour *Acécé,* le script peut être adapté afin d’inclure un canal *#A0* et de supprimer le canal acédant. </span><span class="sxs-lookup"><span data-stu-id="4810f-176">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="4810f-177">Nous recommandons que ces canaux spécialisés ou modelés ne soient pas marqués automatiquement pour éviter une saturation des notifications.</span><span class="sxs-lookup"><span data-stu-id="4810f-177">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="4810f-178">Généralement, les utilisateurs préfèrent les canaux qu’ils trouvent pertinents.</span><span class="sxs-lookup"><span data-stu-id="4810f-178">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="4810f-179">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="4810f-179">Base Template Type</span></span> |<span data-ttu-id="4810f-180">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="4810f-180">baseTemplateId</span></span> |<span data-ttu-id="4810f-181">Canaux de modèle de référence</span><span class="sxs-lookup"><span data-stu-id="4810f-181">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="4810f-182">Soins de santé - Hôpital</span><span class="sxs-lookup"><span data-stu-id="4810f-182">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="4810f-183">Annonces\*</span><span class="sxs-lookup"><span data-stu-id="4810f-183">Announcements\*</span></span> <br> <span data-ttu-id="4810f-184">Conformité\*</span><span class="sxs-lookup"><span data-stu-id="4810f-184">Compliance\*</span></span> <br> <span data-ttu-id="4810f-185">Adess</span><span class="sxs-lookup"><span data-stu-id="4810f-185">Custodial</span></span> <br> <span data-ttu-id="4810f-186">Ressources humaines</span><span class="sxs-lookup"><span data-stu-id="4810f-186">Human Resources</span></span> <br> <span data-ttu-id="4810f-187">Desse</span><span class="sxs-lookup"><span data-stu-id="4810f-187">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="4810f-188">\* Favoris automatiques</span><span class="sxs-lookup"><span data-stu-id="4810f-188">\* Auto-favorited</span></span> 

### <a name="how-to-use-first-party-templates"></a><span data-ttu-id="4810f-189">Comment utiliser des modèles tiers</span><span class="sxs-lookup"><span data-stu-id="4810f-189">How to use first-party templates</span></span>

<span data-ttu-id="4810f-190">Pour utiliser ces modèles, modifiez simplement la propriété « template@odata.bind » dans le corps de la demande de « standard » à la propriété TemplateIDs ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="4810f-190">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="4810f-191">Pour plus d’informations sur le déploiement de modèles Teams, voir l’article Microsoft Graph sur la création [d’une équipe.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="4810f-191">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="4810f-192">Les canaux du modèle sont automatiquement créés sous l’onglet Général.</span><span class="sxs-lookup"><span data-stu-id="4810f-192">The channels in the template will automatically be created under the General Tab.</span></span>

#### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="4810f-193">Exemple : Script d’extension de modèle d’hôpital</span><span class="sxs-lookup"><span data-stu-id="4810f-193">Example: Hospital template extension script</span></span>

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

### <a name="related-topics"></a><span data-ttu-id="4810f-194">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4810f-194">Related topics</span></span>

[<span data-ttu-id="4810f-195">Prise en main des modèles Teams</span><span class="sxs-lookup"><span data-stu-id="4810f-195">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="4810f-196">Prise en main de Teams pour les organismes de santé</span><span class="sxs-lookup"><span data-stu-id="4810f-196">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)
