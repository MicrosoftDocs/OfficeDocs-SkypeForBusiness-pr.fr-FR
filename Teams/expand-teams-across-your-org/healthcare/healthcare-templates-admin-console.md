---
title: Créer une équipe à l’aide de modèles médicaux
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
description: Utilisez des modèles d’équipe dans le Centre d’administration ou avec Microsoft Graph pour créer rapidement et facilement des équipes en fournissant un modèle prédéféré de paramètres, de canaux et d’applications.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f90ddfa9682c7000c4698977c51a39c9631ff9b1
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684351"
---
# <a name="use-a-healthcare-team-templates"></a><span data-ttu-id="5ecda-103">Utiliser des modèles d’équipe de santé</span><span class="sxs-lookup"><span data-stu-id="5ecda-103">Use a healthcare team templates</span></span>

<span data-ttu-id="5ecda-104">Les modèles vous permettent de créer rapidement et facilement des équipes en fournissant un modèle prédéféré de paramètres, de canaux et d’applications préinstallées.</span><span class="sxs-lookup"><span data-stu-id="5ecda-104">Templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="5ecda-105">Pour les organisations de soins de santé, les modèles peuvent être particulièrement puissants, car ils fournissent aux utilisateurs une structure qui leur permet de s’orienter dans l’utilisation efficace d’Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5ecda-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Microsoft Teams.</span></span> <span data-ttu-id="5ecda-106">Les modèles permettent également aux administrateurs de déployer des équipes cohérentes au sein de leur organisation.</span><span class="sxs-lookup"><span data-stu-id="5ecda-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="5ecda-107">Cet article est pour vous si vous êtes responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation de soin de santé.</span><span class="sxs-lookup"><span data-stu-id="5ecda-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your healthcare organization.</span></span>

<span data-ttu-id="5ecda-108">Choisissez une méthode de création d’équipes avec les modèles médicaux d’équipe :</span><span class="sxs-lookup"><span data-stu-id="5ecda-108">Choose a method for creating teams with the team healthcare templates:</span></span>

| <span data-ttu-id="5ecda-109">Qui</span><span class="sxs-lookup"><span data-stu-id="5ecda-109">Who</span></span> | <span data-ttu-id="5ecda-110">Méthode à utiliser :</span><span class="sxs-lookup"><span data-stu-id="5ecda-110">Method to use:</span></span> |
| ---- | --------- |
| <span data-ttu-id="5ecda-111">Administrateurs et professionnels de l’informatique</span><span class="sxs-lookup"><span data-stu-id="5ecda-111">Admins and IT Professionals</span></span> | <span data-ttu-id="5ecda-112">[Utilisez le centre Teams d’administration](#use-the-team-templates-in-the-admin-center) pour créer des équipes basées sur les modèles de l’équipe de santé.</span><span class="sxs-lookup"><span data-stu-id="5ecda-112">[Use the Teams admin center](#use-the-team-templates-in-the-admin-center) to create teams based on the healthcare team templates.</span></span>|
| <span data-ttu-id="5ecda-113">Développeurs et intégrateurs de systèmes</span><span class="sxs-lookup"><span data-stu-id="5ecda-113">Developers and systems integrators</span></span> | <span data-ttu-id="5ecda-114">[Utilisez le site Web Graph](#use-the-team-templates-with-the-microsoft-graph) Microsoft pour créer une équipe basée sur les modèles de l’équipe médicale.</span><span class="sxs-lookup"><span data-stu-id="5ecda-114">[Use the Microsoft Graph](#use-the-team-templates-with-the-microsoft-graph) to create a team based on the healthcare team templates.</span></span> |

## <a name="use-the-team-templates-in-the-admin-center"></a><span data-ttu-id="5ecda-115">Utiliser les modèles d’équipe dans le Centre d’administration</span><span class="sxs-lookup"><span data-stu-id="5ecda-115">Use the team templates in the admin center</span></span>

<span data-ttu-id="5ecda-116">Microsoft Teams les administrateurs peuvent utiliser le centre Teams’administration pour créer des équipes à l’grâce aux modèles d’équipe.</span><span class="sxs-lookup"><span data-stu-id="5ecda-116">Microsoft Teams admins can use the Teams admin center to create teams with the team templates.</span></span> <span data-ttu-id="5ecda-117">Nous proposons actuellement deux modèles de soins de santé pour un large éventail de situations.</span><span class="sxs-lookup"><span data-stu-id="5ecda-117">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="5ecda-118">Pour en savoir plus sur les modèles d’équipe en général, voir Commencer à utiliser les [modèles d’équipe dans le Centre d’administration.](../../get-started-with-teams-templates-in-the-admin-console.md)</span><span class="sxs-lookup"><span data-stu-id="5ecda-118">To learn more about team templates in general, see [Get started with team templates in the admin center](../../get-started-with-teams-templates-in-the-admin-console.md).</span></span>

### <a name="collaborate-on-patient-care"></a><span data-ttu-id="5ecda-119">Collaborer sur les soins aux patients</span><span class="sxs-lookup"><span data-stu-id="5ecda-119">Collaborate on patient care</span></span>

 <span data-ttu-id="5ecda-120">Simplifiez la communication et la collaboration en matière de soins de santé au sein d'un service, d'une unité ou d'un département.</span><span class="sxs-lookup"><span data-stu-id="5ecda-120">Streamline healthcare communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="5ecda-121">Ce modèle peut être utilisé pour faciliter la gestion des patients et les besoins opérationnels d'un service.</span><span class="sxs-lookup"><span data-stu-id="5ecda-121">The template can be used to facilitate patient management and operational needs of a ward.</span></span>

| <span data-ttu-id="5ecda-122">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="5ecda-122">Base template type</span></span> |<span data-ttu-id="5ecda-123">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="5ecda-123">baseTemplateId</span></span>| <span data-ttu-id="5ecda-124">Propriétés fournies avec ce modèle de base</span><span class="sxs-lookup"><span data-stu-id="5ecda-124">Properties that come with this base template</span></span> |
| ------------------ |---|----------------------------------------------------- |
| <span data-ttu-id="5ecda-125">Collaborer sur les soins aux patients</span><span class="sxs-lookup"><span data-stu-id="5ecda-125">Collaborate on patient care</span></span> |`healthcareWard` | <span data-ttu-id="5ecda-126">Canaux :</span><span class="sxs-lookup"><span data-stu-id="5ecda-126">Channels:</span></span><ul><li><span data-ttu-id="5ecda-127">Général</span><span class="sxs-lookup"><span data-stu-id="5ecda-127">General</span></span></li><li><span data-ttu-id="5ecda-128">Annonces</span><span class="sxs-lookup"><span data-stu-id="5ecda-128">Announcements</span></span></li><li><span data-ttu-id="5ecda-129">Blotti</span><span class="sxs-lookup"><span data-stu-id="5ecda-129">Huddles</span></span></li><li><span data-ttu-id="5ecda-130">Rondes</span><span class="sxs-lookup"><span data-stu-id="5ecda-130">Rounds</span></span></li><li><span data-ttu-id="5ecda-131">Personnel</span><span class="sxs-lookup"><span data-stu-id="5ecda-131">Staffing</span></span></li><li><span data-ttu-id="5ecda-132">Formation</span><span class="sxs-lookup"><span data-stu-id="5ecda-132">Training</span></span></li></ul> <span data-ttu-id="5ecda-133">Applications :</span><span class="sxs-lookup"><span data-stu-id="5ecda-133">Apps:</span></span> <ul><li><span data-ttu-id="5ecda-134">Wiki</span><span class="sxs-lookup"><span data-stu-id="5ecda-134">Wiki</span></span></li><li><span data-ttu-id="5ecda-135">Listes</span><span class="sxs-lookup"><span data-stu-id="5ecda-135">Lists</span></span></li></ul>|
||||

### <a name="hospital"></a><span data-ttu-id="5ecda-136">Hôpital</span><span class="sxs-lookup"><span data-stu-id="5ecda-136">Hospital</span></span>

<span data-ttu-id="5ecda-137">Simplifiez la communication et la collaboration entre plusieurs salles, services et départements d'un hôpital.</span><span class="sxs-lookup"><span data-stu-id="5ecda-137">Streamline communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="5ecda-138">Ce modèle comprend un ensemble de canaux de base pour les opérations hospitalières, et peut être auto-étendu pour inclure des spécialités, ad-hoc.</span><span class="sxs-lookup"><span data-stu-id="5ecda-138">This template includes a set of base channels for hospital operations, and can be self-extended to include specialties, ad-hoc.</span></span>

| <span data-ttu-id="5ecda-139">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="5ecda-139">Base template type</span></span> |<span data-ttu-id="5ecda-140">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="5ecda-140">baseTemplateId</span></span> | <span data-ttu-id="5ecda-141">Propriétés fournies avec ce modèle de base</span><span class="sxs-lookup"><span data-stu-id="5ecda-141">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="5ecda-142">Hôpital</span><span class="sxs-lookup"><span data-stu-id="5ecda-142">Hospital</span></span>|`healthcareHospital`|<span data-ttu-id="5ecda-143">Canaux :</span><span class="sxs-lookup"><span data-stu-id="5ecda-143">Channels:</span></span> <ul><li><span data-ttu-id="5ecda-144">Général</span><span class="sxs-lookup"><span data-stu-id="5ecda-144">General</span></span></li><li><span data-ttu-id="5ecda-145">Annonces</span><span class="sxs-lookup"><span data-stu-id="5ecda-145">Announcements</span></span></li><li><span data-ttu-id="5ecda-146">Conformité</span><span class="sxs-lookup"><span data-stu-id="5ecda-146">Compliance</span></span></li><li><span data-ttu-id="5ecda-147">Consignataires</span><span class="sxs-lookup"><span data-stu-id="5ecda-147">Custodial</span></span></li><li><span data-ttu-id="5ecda-148">Ressources humaines</span><span class="sxs-lookup"><span data-stu-id="5ecda-148">Human resources</span></span></li><li><span data-ttu-id="5ecda-149">Pharmacie</span><span class="sxs-lookup"><span data-stu-id="5ecda-149">Pharmacy</span></span></li></ul> <span data-ttu-id="5ecda-150">Applications :</span><span class="sxs-lookup"><span data-stu-id="5ecda-150">Apps:</span></span> <ul><li><span data-ttu-id="5ecda-151">Wiki</span><span class="sxs-lookup"><span data-stu-id="5ecda-151">Wiki</span></span></li><li><span data-ttu-id="5ecda-152">Listes</span><span class="sxs-lookup"><span data-stu-id="5ecda-152">Lists</span></span> </li></ul>|
||||


## <a name="use-the-team-templates-with-the-microsoft-graph"></a><span data-ttu-id="5ecda-153">Utiliser les modèles d’équipe avec l’Graph</span><span class="sxs-lookup"><span data-stu-id="5ecda-153">Use the team templates with the Microsoft Graph</span></span>

<span data-ttu-id="5ecda-154">Les développeurs peuvent utiliser le programme Microsoft Graph pour créer des équipes à l’aide des modèles d’équipe.</span><span class="sxs-lookup"><span data-stu-id="5ecda-154">Developers can use the Microsoft Graph to create teams with the team templates.</span></span> <span data-ttu-id="5ecda-155">Nous proposons actuellement deux modèles de soins de santé pour un large éventail de situations.</span><span class="sxs-lookup"><span data-stu-id="5ecda-155">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="5ecda-156">Pour en savoir plus sur les modèles d’équipe en général, voir [Commencer à utiliser les modèles d’équipe.](../../get-started-with-teams-templates.md)</span><span class="sxs-lookup"><span data-stu-id="5ecda-156">To learn more about team templates in general, see [Get started with team templates](../../get-started-with-teams-templates.md).</span></span> <span data-ttu-id="5ecda-157">Pour plus d’informations sur les modèles d’équipe et le modèle Microsoft Graph, voir Microsoft Teams vue d’ensemble de [l’API](/graph/teams-concept-overview?view=graph-rest-1.0) et le type de ressource [teamsTemplate.](/graph/api/resources/teamstemplate?view=graph-rest-1.0)</span><span class="sxs-lookup"><span data-stu-id="5ecda-157">And for information about team templates and the Microsoft Graph, see [Microsoft Teams API overview](/graph/teams-concept-overview?view=graph-rest-1.0) and [teamsTemplate resource type](/graph/api/resources/teamstemplate?view=graph-rest-1.0).</span></span>

### <a name="ward-template"></a><span data-ttu-id="5ecda-158">Modèle de pavillon</span><span class="sxs-lookup"><span data-stu-id="5ecda-158">Ward template</span></span>

<span data-ttu-id="5ecda-159">Le modèle de salle est destiné à la communication et à la collaboration au sein d'un pavillon, d'un service ou d'un département.</span><span class="sxs-lookup"><span data-stu-id="5ecda-159">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="5ecda-160">Ce modèle peut être utilisé pour faciliter la gestion des patients et les besoins opérationnels d'un service.</span><span class="sxs-lookup"><span data-stu-id="5ecda-160">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="5ecda-161">Par exemple, les annonces de recherche peuvent être publiées dans le canal *Annonces* et les Plannings peuvent être gérés dans *Staffing*.</span><span class="sxs-lookup"><span data-stu-id="5ecda-161">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="5ecda-162">Si vous cherchez à simplifier les opérations de présentation, ce modèle est fait pour vous.</span><span class="sxs-lookup"><span data-stu-id="5ecda-162">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="5ecda-163">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="5ecda-163">Base Template Type</span></span> |<span data-ttu-id="5ecda-164">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="5ecda-164">baseTemplateId</span></span> |<span data-ttu-id="5ecda-165">Canaux modèles de référence</span><span class="sxs-lookup"><span data-stu-id="5ecda-165">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="5ecda-166">Soins de santé : pavillon</span><span class="sxs-lookup"><span data-stu-id="5ecda-166">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="5ecda-167">Annonces\*</span><span class="sxs-lookup"><span data-stu-id="5ecda-167">Announcements\*</span></span> <br> <span data-ttu-id="5ecda-168">Blotti\*</span><span class="sxs-lookup"><span data-stu-id="5ecda-168">Huddles\*</span></span> <br> <span data-ttu-id="5ecda-169">Rondes\*</span><span class="sxs-lookup"><span data-stu-id="5ecda-169">Rounds\*</span></span> <br> <span data-ttu-id="5ecda-170">Personnel\*</span><span class="sxs-lookup"><span data-stu-id="5ecda-170">Staffing\*</span></span> <br> <span data-ttu-id="5ecda-171">Formation\*</span><span class="sxs-lookup"><span data-stu-id="5ecda-171">Training\*</span></span> |
|     | |         |

<span data-ttu-id="5ecda-172">\* Favoris automatiques</span><span class="sxs-lookup"><span data-stu-id="5ecda-172">\* Auto-favorited</span></span>

### <a name="hospital-template"></a><span data-ttu-id="5ecda-173">Modèle d’hôpital</span><span class="sxs-lookup"><span data-stu-id="5ecda-173">Hospital template</span></span>

<span data-ttu-id="5ecda-174">Le modèle d'hôpital est destiné à la communication et à la collaboration entre les différents services et départements d'un hôpital.</span><span class="sxs-lookup"><span data-stu-id="5ecda-174">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="5ecda-175">Ce modèle inclut plusieurs canaux opérationnels, notamment *Annonces*, *Consignataires* et *Pharmacie*, mais nous fournissons également un script ci-dessous qui étend le modèle avec de nombreux canaux supplémentaires de service ou spécialisés que vous pouvez ajouter, supprimer ou modifier à votre convenance.</span><span class="sxs-lookup"><span data-stu-id="5ecda-175">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="5ecda-176">Par exemple, si vous avez un service *Endocrinologie* , mais que vous n’avez pas besoin d’un canal pour *Ophtalmologie*, le script peut être adapté pour inclure un canal *Endocrinologie* et supprimer le canal *Ophtalmologie* .</span><span class="sxs-lookup"><span data-stu-id="5ecda-176">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="5ecda-177">Nous vous recommandons de ne pas faire attention à ces canaux de spécialité ou à modélisation automatique afin d’éviter une saturation des notifications.</span><span class="sxs-lookup"><span data-stu-id="5ecda-177">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="5ecda-178">Les utilisateurs préfèrent généralement tous les canaux qu’ils trouvent pertinents.</span><span class="sxs-lookup"><span data-stu-id="5ecda-178">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="5ecda-179">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="5ecda-179">Base Template Type</span></span> |<span data-ttu-id="5ecda-180">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="5ecda-180">baseTemplateId</span></span> |<span data-ttu-id="5ecda-181">Canaux modèles de référence</span><span class="sxs-lookup"><span data-stu-id="5ecda-181">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="5ecda-182">Soins de santé : hôpital</span><span class="sxs-lookup"><span data-stu-id="5ecda-182">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="5ecda-183">Annonces\*</span><span class="sxs-lookup"><span data-stu-id="5ecda-183">Announcements\*</span></span> <br> <span data-ttu-id="5ecda-184">Conformité\*</span><span class="sxs-lookup"><span data-stu-id="5ecda-184">Compliance\*</span></span> <br> <span data-ttu-id="5ecda-185">Consignataires</span><span class="sxs-lookup"><span data-stu-id="5ecda-185">Custodial</span></span> <br> <span data-ttu-id="5ecda-186">Ressources humaines</span><span class="sxs-lookup"><span data-stu-id="5ecda-186">Human Resources</span></span> <br> <span data-ttu-id="5ecda-187">Pharmacie</span><span class="sxs-lookup"><span data-stu-id="5ecda-187">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="5ecda-188">\* Favoris automatiques</span><span class="sxs-lookup"><span data-stu-id="5ecda-188">\* Auto-favorited</span></span> 

### <a name="how-to-use-first-party-templates"></a><span data-ttu-id="5ecda-189">Comment utiliser les modèles de premier groupe</span><span class="sxs-lookup"><span data-stu-id="5ecda-189">How to use first-party templates</span></span>

<span data-ttu-id="5ecda-190">Pour utiliser ces modèles, modifiez simplement la propriété « template@odata.bind » dans le corps de la demande de « standard » en valeurs TemplateID ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="5ecda-190">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="5ecda-191">Pour plus d’informations sur le déploiement de modèles d’équipe, consultez l’article Graph Microsoft sur la création [d’une équipe.](/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="5ecda-191">For more information on how to deploy team templates, see the Microsoft Graph article on how to [create a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="5ecda-192">Les canaux dans le modèle seront automatiquement créés sous l’onglet Général.</span><span class="sxs-lookup"><span data-stu-id="5ecda-192">The channels in the template will automatically be created under the General Tab.</span></span>

#### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="5ecda-193">Exemple : script d’extension de modèle d’hôpital</span><span class="sxs-lookup"><span data-stu-id="5ecda-193">Example: Hospital template extension script</span></span>

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

### <a name="related-topics"></a><span data-ttu-id="5ecda-194">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="5ecda-194">Related topics</span></span>

[<span data-ttu-id="5ecda-195">Utiliser les modèles d’équipe</span><span class="sxs-lookup"><span data-stu-id="5ecda-195">Get started with team templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="5ecda-196">Commencer à travailler avec l’équipe pour les organisations du secteur des soins de santé</span><span class="sxs-lookup"><span data-stu-id="5ecda-196">Get started with team for Healthcare organizations</span></span>](teams-in-hc.md)