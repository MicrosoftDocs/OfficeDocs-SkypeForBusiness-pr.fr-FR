---
title: Prise en main des modèles Teams de vente au détail
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser les modèles teams pour créer des structures d’équipe conçues pour les revendeurs en fournissant des paramètres prédéfinis, des canaux et des applications préinstallées.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f226b60bfc3a054166eb48596c505ccd7fa5ac9
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424634"
---
# <a name="get-started-with-teams-templates-in-retail"></a><span data-ttu-id="b6b88-103">Prise en main des modèles Teams de vente au détail</span><span class="sxs-lookup"><span data-stu-id="b6b88-103">Get started with Teams templates in retail</span></span>

<span data-ttu-id="b6b88-104">Les modèles d’équipes vous permettent de créer rapidement et facilement des équipes en fournissant un modèle prédéfini de paramètres, de canaux et d’applications déjà installées.</span><span class="sxs-lookup"><span data-stu-id="b6b88-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="b6b88-105">Les modèles d’équipes sont dotés de définitions prédéfinies de structures d’équipe conçues en fonction des besoins des détaillants.</span><span class="sxs-lookup"><span data-stu-id="b6b88-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="b6b88-106">Vous pouvez utiliser les modèles teams pour créer rapidement des types d’équipes adaptées aux détaillants et à déployer au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b6b88-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="b6b88-107">Vous pouvez également développer les modèles teams pour créer des équipes adaptées aux besoins spécifiques de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b6b88-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="b6b88-108">Dans cet article, nous allons présenter chacun des modèles d’équipes et nous vous conseillons de les utiliser.</span><span class="sxs-lookup"><span data-stu-id="b6b88-108">In this article, we'll introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="b6b88-109">Cet article est pour vous si vous êtes responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation commerciale.</span><span class="sxs-lookup"><span data-stu-id="b6b88-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="b6b88-110">Vous avez déjà déployé le service teams au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b6b88-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="b6b88-111">Si vous n’avez pas encore déployé Teams, commencez par lire la rubrique [comment déployer Microsoft teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b6b88-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="b6b88-112">Pour en savoir plus sur les modèles d’équipe en général, voir [commencer à utiliser les modèles](get-started-with-teams-templates.md)Teams.</span><span class="sxs-lookup"><span data-stu-id="b6b88-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="store-template"></a><span data-ttu-id="b6b88-113">Modèle du Windows Store</span><span class="sxs-lookup"><span data-stu-id="b6b88-113">Store template</span></span>

<span data-ttu-id="b6b88-114">Le modèle Windows Store est idéal pour créer une équipe et représenter une adresse de magasin commerciale individuelle.</span><span class="sxs-lookup"><span data-stu-id="b6b88-114">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="b6b88-115">À l’aide du modèle Windows Store, vous pouvez créer une équipe pour chaque emplacement de magasin commercial au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b6b88-115">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="b6b88-116">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="b6b88-116">Base template type</span></span> | <span data-ttu-id="b6b88-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="b6b88-117">baseTemplateId</span></span> | <span data-ttu-id="b6b88-118">Propriétés fournies avec ce modèle de base</span><span class="sxs-lookup"><span data-stu-id="b6b88-118">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="b6b88-119">Revendeur</span><span class="sxs-lookup"><span data-stu-id="b6b88-119">Retail -</span></span> <br><span data-ttu-id="b6b88-120">Boutique d’applications</span><span class="sxs-lookup"><span data-stu-id="b6b88-120">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="b6b88-121">Canaux</span><span class="sxs-lookup"><span data-stu-id="b6b88-121">Channels</span></span> <ul><li><span data-ttu-id="b6b88-122">Transfert de décalage\*</span><span class="sxs-lookup"><span data-stu-id="b6b88-122">Shifts handoff\*</span></span></li><li><span data-ttu-id="b6b88-123">LMS\*</span><span class="sxs-lookup"><span data-stu-id="b6b88-123">Learning\*</span></span></li></ul><span data-ttu-id="b6b88-124">\*Canaux favoris automatiquement</span><span class="sxs-lookup"><span data-stu-id="b6b88-124">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="b6b88-125">Propriétés d’équipe</span><span class="sxs-lookup"><span data-stu-id="b6b88-125">Team properties</span></span> <ul><li><span data-ttu-id="b6b88-126">Visibilité de l’équipe définie sur publique</span><span class="sxs-lookup"><span data-stu-id="b6b88-126">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="b6b88-127">Autorisations des membres</span><span class="sxs-lookup"><span data-stu-id="b6b88-127">Member permissions</span></span> <ul><li><span data-ttu-id="b6b88-128">Création/mise à jour/suppression de canaux impossible</span><span class="sxs-lookup"><span data-stu-id="b6b88-128">Can't create/update/delete channels</span></span> </li><li><span data-ttu-id="b6b88-129">Impossible d’ajouter/supprimer des applications</span><span class="sxs-lookup"><span data-stu-id="b6b88-129">Can't add/remove apps</span></span> </li><li><span data-ttu-id="b6b88-130">Impossible de créer/mettre à jour/supprimer des onglets</span><span class="sxs-lookup"><span data-stu-id="b6b88-130">Can't create/update/remove tabs</span></span></li><li><span data-ttu-id="b6b88-131">Création/mise à jour/suppression de connecteurs impossible</span><span class="sxs-lookup"><span data-stu-id="b6b88-131">Can't create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="b6b88-132">Méthodes conseillées pour personnaliser le modèle Windows Store pour votre organisation :</span><span class="sxs-lookup"><span data-stu-id="b6b88-132">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="b6b88-133">Si votre organisation a des services dans chaque banque, ajoutez un canal pour chaque service.</span><span class="sxs-lookup"><span data-stu-id="b6b88-133">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="b6b88-134">L’ajout d’un canal facilite la communication et la collaboration au sein du service.</span><span class="sxs-lookup"><span data-stu-id="b6b88-134">Adding a channel facilitates communication and collaboration within the department.</span></span>

- <span data-ttu-id="b6b88-135">Si votre organisation a des sites Web internes (par exemple, un site SharePoint), envisagez de les épingler en tant qu’onglets du canal d’équipe approprié.</span><span class="sxs-lookup"><span data-stu-id="b6b88-135">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="b6b88-136">Pour obtenir des instructions, voir [commencer à utiliser les modèles teams](get-started-with-teams-templates.md) .</span><span class="sxs-lookup"><span data-stu-id="b6b88-136">Refer to [Get started with Teams templates](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="manager-collaboration-template"></a><span data-ttu-id="b6b88-137">Modèle de collaboration responsable</span><span class="sxs-lookup"><span data-stu-id="b6b88-137">Manager Collaboration template</span></span>

<span data-ttu-id="b6b88-138">Le modèle de collaboration responsable est l’un des modèles d’équipe pour les besoins des détaillants.</span><span class="sxs-lookup"><span data-stu-id="b6b88-138">The Manager Collaboration template is another one of the Teams templates designed around retailer needs.</span></span> <span data-ttu-id="b6b88-139">Le modèle de collaboration responsable est idéal pour créer une équipe pour un ensemble de responsables pour collaborer entre des boutiques et des régions, et plus encore.</span><span class="sxs-lookup"><span data-stu-id="b6b88-139">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, and more.</span></span> <span data-ttu-id="b6b88-140">Par exemple, si votre organisation a des régions, vous pouvez créer une équipe de collaboration en chef pour la région Californie et inclure tous les responsables du Windows Store de cette région ainsi que le responsable régional de cette région.</span><span class="sxs-lookup"><span data-stu-id="b6b88-140">For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="b6b88-141">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="b6b88-141">Base template type</span></span> | <span data-ttu-id="b6b88-142">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="b6b88-142">baseTemplateId</span></span> | <span data-ttu-id="b6b88-143">Propriétés fournies avec ce modèle de base</span><span class="sxs-lookup"><span data-stu-id="b6b88-143">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="b6b88-144">Revendeur</span><span class="sxs-lookup"><span data-stu-id="b6b88-144">Retail -</span></span> <br><span data-ttu-id="b6b88-145">Boutique d’applications</span><span class="sxs-lookup"><span data-stu-id="b6b88-145">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="b6b88-146">Canaux</span><span class="sxs-lookup"><span data-stu-id="b6b88-146">Channels</span></span> <ul><li><span data-ttu-id="b6b88-147">Opérations\*</span><span class="sxs-lookup"><span data-stu-id="b6b88-147">Operations\*</span></span></li><li><span data-ttu-id="b6b88-148">LMS\*</span><span class="sxs-lookup"><span data-stu-id="b6b88-148">Learning\*</span></span></li></ul><span data-ttu-id="b6b88-149">\*Canaux favoris automatiquement</span><span class="sxs-lookup"><span data-stu-id="b6b88-149">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="b6b88-150">Propriétés d’équipe</span><span class="sxs-lookup"><span data-stu-id="b6b88-150">Team properties</span></span> <ul><li><span data-ttu-id="b6b88-151">Visibilité de l’équipe définie sur privée</span><span class="sxs-lookup"><span data-stu-id="b6b88-151">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="b6b88-152">Autorisations des membres</span><span class="sxs-lookup"><span data-stu-id="b6b88-152">Member permissions</span></span> <ul><li><span data-ttu-id="b6b88-153">Création/mise à jour/suppression de canaux</span><span class="sxs-lookup"><span data-stu-id="b6b88-153">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="b6b88-154">Ajout/suppression d’applications</span><span class="sxs-lookup"><span data-stu-id="b6b88-154">Can add/remove apps</span></span> </li><li><span data-ttu-id="b6b88-155">Peut créer/mettre à jour/supprimer des onglets</span><span class="sxs-lookup"><span data-stu-id="b6b88-155">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="b6b88-156">Création/mise à jour/suppression de connecteurs possibles</span><span class="sxs-lookup"><span data-stu-id="b6b88-156">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="b6b88-157">Méthodes conseillées pour personnaliser le modèle de collaboration responsable de votre organisation :</span><span class="sxs-lookup"><span data-stu-id="b6b88-157">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="b6b88-158">Si votre organisation possède un site Web interne, tel qu’un site SharePoint, qui convient aux responsables, envisagez de les épingler en tant qu’onglets dans un canal d’équipe approprié.</span><span class="sxs-lookup"><span data-stu-id="b6b88-158">If your organization has any internal websites, such as a SharePoint site, that are relevant for managers, consider pinning them as tabs in a relevant team channel.</span></span> <span data-ttu-id="b6b88-159">Pour obtenir des instructions, consultez la [documentation du modèle Microsoft teams](get-started-with-teams-templates.md) .</span><span class="sxs-lookup"><span data-stu-id="b6b88-159">You can take a look at the [Microsoft Teams Template documentation](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="b6b88-160">Utilisation de modèles de première partie</span><span class="sxs-lookup"><span data-stu-id="b6b88-160">How to use first party templates</span></span>

<span data-ttu-id="b6b88-161">Pour utiliser ces modèles, remplacez la propriété « template@odata. bind » du corps de la requête par « standard » par le TemplateIDs ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="b6b88-161">To use these templates, change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="b6b88-162">Pour plus d’informations sur le déploiement de modèles d’équipe, voir l’article Microsoft Graph sur la [création d’une équipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="b6b88-162">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="b6b88-163">Les canaux du modèle sont automatiquement créés sous l’onglet général.</span><span class="sxs-lookup"><span data-stu-id="b6b88-163">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-store-template-extension-script"></a><span data-ttu-id="b6b88-164">Exemple : script d’extension de modèle Store</span><span class="sxs-lookup"><span data-stu-id="b6b88-164">Example: Store template extension script</span></span>

``` PowerShell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('retailStore')",
  "DisplayName": "Contoso Store",
  "Description": "Team for all staff in Contoso Store",
  "Channels": [
    {
      "displayName": "Additional store channel",
      "IsFavoriteByDefault": false
    }
  ]
}
```
## <a name="relate-topic"></a><span data-ttu-id="b6b88-165">Thème lié</span><span class="sxs-lookup"><span data-stu-id="b6b88-165">Relate topic</span></span>

[<span data-ttu-id="b6b88-166">Commencer à utiliser les modèles teams dans le centre d’administration</span><span class="sxs-lookup"><span data-stu-id="b6b88-166">Get started with Teams templates in the Admin center</span></span>](get-started-with-teams-templates-in-the-admin-console.md)
