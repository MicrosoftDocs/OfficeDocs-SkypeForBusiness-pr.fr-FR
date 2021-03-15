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
description: Découvrez comment utiliser les modèles Teams pour créer des structures d’équipe conçues pour les besoins d’un revendeur en fournissant des paramètres, des canaux et des applications préinstallées.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f226b60bfc3a054166eb48596c505ccd7fa5ac9
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424634"
---
# <a name="get-started-with-teams-templates-in-retail"></a><span data-ttu-id="36d85-103">Prise en main des modèles Teams de vente au détail</span><span class="sxs-lookup"><span data-stu-id="36d85-103">Get started with Teams templates in retail</span></span>

<span data-ttu-id="36d85-104">Les modèles Teams vous permettent de créer rapidement et facilement des équipes en fournissant un modèle prédéfini de paramètres, de canaux et d'applications préinstallées.</span><span class="sxs-lookup"><span data-stu-id="36d85-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="36d85-105">Les modèles Teams ont des définitions pré-conçues pour les structures d’équipe conçues autour des besoins d’un revendeur.</span><span class="sxs-lookup"><span data-stu-id="36d85-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="36d85-106">Vous pouvez utiliser des modèles Teams pour créer rapidement les types d’équipes qui fonctionnent bien pour les revendeurs et les déployer au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="36d85-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="36d85-107">Vous pouvez également étendre les modèles Teams pour créer des équipes adaptées aux besoins spécifiques de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="36d85-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="36d85-108">Cet article présente chacun des modèles Teams et vous explique comment les utiliser.</span><span class="sxs-lookup"><span data-stu-id="36d85-108">In this article, we'll introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="36d85-109">Cet article est pour vous si vous êtes responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="36d85-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="36d85-110">Vous avez déjà déployé le service Teams dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="36d85-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="36d85-111">Si vous n’avez pas encore déployé Teams, commencez par lire l’article [Comment déployer Microsoft Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="36d85-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="36d85-112">Pour en savoir plus sur les modèles d’équipe en général, consultez [Prise en main des modèles Teams](get-started-with-teams-templates.md).</span><span class="sxs-lookup"><span data-stu-id="36d85-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="store-template"></a><span data-ttu-id="36d85-113">Modèle Store</span><span class="sxs-lookup"><span data-stu-id="36d85-113">Store template</span></span>

<span data-ttu-id="36d85-114">Le modèle Store est idéal pour créer une équipe afin de représenter un emplacement de magasin de détail.</span><span class="sxs-lookup"><span data-stu-id="36d85-114">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="36d85-115">Le modèle Store vous permet de créer une équipe pour chaque emplacement de vente au détail dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="36d85-115">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="36d85-116">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="36d85-116">Base template type</span></span> | <span data-ttu-id="36d85-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="36d85-117">baseTemplateId</span></span> | <span data-ttu-id="36d85-118">Propriétés fournies avec ce modèle de base</span><span class="sxs-lookup"><span data-stu-id="36d85-118">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="36d85-119">Commerce -</span><span class="sxs-lookup"><span data-stu-id="36d85-119">Retail -</span></span> <br><span data-ttu-id="36d85-120">Magasin</span><span class="sxs-lookup"><span data-stu-id="36d85-120">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="36d85-121">Canaux</span><span class="sxs-lookup"><span data-stu-id="36d85-121">Channels</span></span> <ul><li><span data-ttu-id="36d85-122">Procédure de transfert des Plannings\*</span><span class="sxs-lookup"><span data-stu-id="36d85-122">Shifts handoff\*</span></span></li><li><span data-ttu-id="36d85-123">Apprentissage\*</span><span class="sxs-lookup"><span data-stu-id="36d85-123">Learning\*</span></span></li></ul><span data-ttu-id="36d85-124">\*Canaux ajoutés automatiquement aux favoris</span><span class="sxs-lookup"><span data-stu-id="36d85-124">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="36d85-125">Propriétés de l’équipe</span><span class="sxs-lookup"><span data-stu-id="36d85-125">Team properties</span></span> <ul><li><span data-ttu-id="36d85-126">Visibilité de l’équipe définie sur Public</span><span class="sxs-lookup"><span data-stu-id="36d85-126">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="36d85-127">Autorisations de membre</span><span class="sxs-lookup"><span data-stu-id="36d85-127">Member permissions</span></span> <ul><li><span data-ttu-id="36d85-128">Impossible de créer/mettre à jour/supprimer des canaux</span><span class="sxs-lookup"><span data-stu-id="36d85-128">Can't create/update/delete channels</span></span> </li><li><span data-ttu-id="36d85-129">Impossible d’ajouter/supprimer des applications</span><span class="sxs-lookup"><span data-stu-id="36d85-129">Can't add/remove apps</span></span> </li><li><span data-ttu-id="36d85-130">Impossible de créer/mettre à jour/supprimer des onglets</span><span class="sxs-lookup"><span data-stu-id="36d85-130">Can't create/update/remove tabs</span></span></li><li><span data-ttu-id="36d85-131">Impossible de créer/mettre à jour/supprimer des connecteurs</span><span class="sxs-lookup"><span data-stu-id="36d85-131">Can't create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="36d85-132">Méthodes recommandées pour personnaliser le modèle Store pour votre organisation :</span><span class="sxs-lookup"><span data-stu-id="36d85-132">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="36d85-133">Si votre organisation comporte des départements au sein de chaque magasin, ajoutez un canal pour chaque département.</span><span class="sxs-lookup"><span data-stu-id="36d85-133">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="36d85-134">L’ajout d’un canal facilite la communication et la collaboration au sein du service.</span><span class="sxs-lookup"><span data-stu-id="36d85-134">Adding a channel facilitates communication and collaboration within the department.</span></span>

- <span data-ttu-id="36d85-135">Si votre organisation possède des sites web internes (par exemple, un site SharePoint), pensez à les épingler comme onglets dans le canal de l'équipe concernée.</span><span class="sxs-lookup"><span data-stu-id="36d85-135">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="36d85-136">Pour obtenir des instructions, consultez [Prise en main des modèles Teams](get-started-with-teams-templates.md).</span><span class="sxs-lookup"><span data-stu-id="36d85-136">Refer to [Get started with Teams templates](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="manager-collaboration-template"></a><span data-ttu-id="36d85-137">Modèle de collaboration entre responsables</span><span class="sxs-lookup"><span data-stu-id="36d85-137">Manager Collaboration template</span></span>

<span data-ttu-id="36d85-138">Le modèle de collaboration entre responsables est un autre modèle de l'équipe conçu pour répondre aux besoins des détaillants.</span><span class="sxs-lookup"><span data-stu-id="36d85-138">The Manager Collaboration template is another one of the Teams templates designed around retailer needs.</span></span> <span data-ttu-id="36d85-139">Le modèle de collaboration entre responsables est idéal pour créer une équipe permettant à un ensemble de responsables de collaborer entre magasins/régions, et plus encore.</span><span class="sxs-lookup"><span data-stu-id="36d85-139">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, and more.</span></span> <span data-ttu-id="36d85-140">Par exemple, si votre organisation comporte des régions, vous pouvez créer une équipe de collaboration entre responsables pour la région de Californie et y inclure tous les responsables de magasin de cette région, ainsi que le responsable régional de cette région.</span><span class="sxs-lookup"><span data-stu-id="36d85-140">For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="36d85-141">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="36d85-141">Base template type</span></span> | <span data-ttu-id="36d85-142">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="36d85-142">baseTemplateId</span></span> | <span data-ttu-id="36d85-143">Propriétés fournies avec ce modèle de base</span><span class="sxs-lookup"><span data-stu-id="36d85-143">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="36d85-144">Commerce -</span><span class="sxs-lookup"><span data-stu-id="36d85-144">Retail -</span></span> <br><span data-ttu-id="36d85-145">Magasin</span><span class="sxs-lookup"><span data-stu-id="36d85-145">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="36d85-146">Canaux</span><span class="sxs-lookup"><span data-stu-id="36d85-146">Channels</span></span> <ul><li><span data-ttu-id="36d85-147">Opérations\*</span><span class="sxs-lookup"><span data-stu-id="36d85-147">Operations\*</span></span></li><li><span data-ttu-id="36d85-148">Apprentissage\*</span><span class="sxs-lookup"><span data-stu-id="36d85-148">Learning\*</span></span></li></ul><span data-ttu-id="36d85-149">\*Canaux ajoutés automatiquement aux favoris</span><span class="sxs-lookup"><span data-stu-id="36d85-149">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="36d85-150">Propriétés de l’équipe</span><span class="sxs-lookup"><span data-stu-id="36d85-150">Team properties</span></span> <ul><li><span data-ttu-id="36d85-151">Visibilité de l’équipe définie sur Privé</span><span class="sxs-lookup"><span data-stu-id="36d85-151">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="36d85-152">Autorisations de membre</span><span class="sxs-lookup"><span data-stu-id="36d85-152">Member permissions</span></span> <ul><li><span data-ttu-id="36d85-153">Création/mise à jour/suppression de canaux</span><span class="sxs-lookup"><span data-stu-id="36d85-153">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="36d85-154">Ajout/suppression d’applications</span><span class="sxs-lookup"><span data-stu-id="36d85-154">Can add/remove apps</span></span> </li><li><span data-ttu-id="36d85-155">Création/mise à jour/suppression d’onglets</span><span class="sxs-lookup"><span data-stu-id="36d85-155">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="36d85-156">Création/mise à jour/suppression des connecteurs</span><span class="sxs-lookup"><span data-stu-id="36d85-156">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="36d85-157">Méthodes recommandées pour personnaliser le modèle de collaboration entre responsables pour votre organisation :</span><span class="sxs-lookup"><span data-stu-id="36d85-157">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="36d85-158">Si votre organisation possède des sites web internes, tels qu'un site SharePoint, qui sont pertinents pour les responsables, pensez à les épingler comme onglets dans un canal d'équipe pertinent.</span><span class="sxs-lookup"><span data-stu-id="36d85-158">If your organization has any internal websites, such as a SharePoint site, that are relevant for managers, consider pinning them as tabs in a relevant team channel.</span></span> <span data-ttu-id="36d85-159">Pour les instructions, vous pouvez consulter la [documentation sur les modèles Microsoft Teams](get-started-with-teams-templates.md).</span><span class="sxs-lookup"><span data-stu-id="36d85-159">You can take a look at the [Microsoft Teams Template documentation](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="36d85-160">Comment utiliser les modèles de premier groupe</span><span class="sxs-lookup"><span data-stu-id="36d85-160">How to use first party templates</span></span>

<span data-ttu-id="36d85-161">Pour utiliser ces modèles, modifiez la propriété « template@odata.bind » dans le corps de la demande de « standard » en valeurs TemplateID ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="36d85-161">To use these templates, change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="36d85-162">Pour plus d’informations sur le déploiement des modèles Teams, consultez l’article Microsoft Graph sur la [création d’un groupe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="36d85-162">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="36d85-163">Les canaux dans le modèle seront automatiquement créés sous l’onglet Général.</span><span class="sxs-lookup"><span data-stu-id="36d85-163">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-store-template-extension-script"></a><span data-ttu-id="36d85-164">Exemple : script d’extension de modèle Store</span><span class="sxs-lookup"><span data-stu-id="36d85-164">Example: Store template extension script</span></span>

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
## <a name="relate-topic"></a><span data-ttu-id="36d85-165">Rubrique concernée</span><span class="sxs-lookup"><span data-stu-id="36d85-165">Relate topic</span></span>

[<span data-ttu-id="36d85-166">Prise en main des modèles Teams dans le Centre d'administration</span><span class="sxs-lookup"><span data-stu-id="36d85-166">Get started with Teams templates in the Admin center</span></span>](get-started-with-teams-templates-in-the-admin-console.md)
