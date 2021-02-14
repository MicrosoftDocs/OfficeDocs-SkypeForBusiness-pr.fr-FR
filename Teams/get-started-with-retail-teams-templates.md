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
description: Découvrez comment utiliser les modèles Teams pour créer des structures d’équipe conçues pour les besoins des revendeurs en fournissant des paramètres, des canaux et des applications préinstallées.
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
# <a name="get-started-with-teams-templates-in-retail"></a><span data-ttu-id="65135-103">Prise en main des modèles Teams de vente au détail</span><span class="sxs-lookup"><span data-stu-id="65135-103">Get started with Teams templates in retail</span></span>

<span data-ttu-id="65135-104">Les modèles Teams vous permettent de créer rapidement et facilement des équipes en fournissant un modèle prédéfindé de paramètres, de canaux et d’applications préinstallées.</span><span class="sxs-lookup"><span data-stu-id="65135-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="65135-105">Les modèles Teams ont des définitions pré-intégrées de structures d’équipe conçues autour des besoins des revendeurs.</span><span class="sxs-lookup"><span data-stu-id="65135-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="65135-106">Vous pouvez utiliser les modèles Teams pour créer rapidement les types d’équipes qui fonctionnent bien pour les revendeurs et les déployer dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="65135-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="65135-107">Vous pouvez également étendre les modèles Teams pour créer des équipes adaptées aux besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="65135-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="65135-108">Dans cet article, nous allons présenter chacun des modèles Teams et leur recommander comment les utiliser.</span><span class="sxs-lookup"><span data-stu-id="65135-108">In this article, we'll introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="65135-109">Cet article est pour vous si vous êtes responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="65135-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="65135-110">Vous avez déjà déployé le service Teams dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="65135-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="65135-111">Si vous n’avez pas encore déployé Teams, commencez par lire comment [déployer Microsoft Teams.](How-to-roll-out-teams.md)</span><span class="sxs-lookup"><span data-stu-id="65135-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="65135-112">Pour en savoir plus sur les modèles d’équipe en général, voir [Commencer à utiliser les modèles Teams.](get-started-with-teams-templates.md)</span><span class="sxs-lookup"><span data-stu-id="65135-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="store-template"></a><span data-ttu-id="65135-113">Modèle Store</span><span class="sxs-lookup"><span data-stu-id="65135-113">Store template</span></span>

<span data-ttu-id="65135-114">Le modèle de Magasin est idéal pour créer une équipe représentant un emplacement de magasin individuel.</span><span class="sxs-lookup"><span data-stu-id="65135-114">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="65135-115">En utilisant le modèle du Store, vous pouvez créer une équipe pour chaque emplacement de magasin de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="65135-115">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="65135-116">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="65135-116">Base template type</span></span> | <span data-ttu-id="65135-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="65135-117">baseTemplateId</span></span> | <span data-ttu-id="65135-118">Propriétés de ce modèle de base</span><span class="sxs-lookup"><span data-stu-id="65135-118">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="65135-119">Vente au détail -</span><span class="sxs-lookup"><span data-stu-id="65135-119">Retail -</span></span> <br><span data-ttu-id="65135-120">Magasin</span><span class="sxs-lookup"><span data-stu-id="65135-120">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="65135-121">Canaux</span><span class="sxs-lookup"><span data-stu-id="65135-121">Channels</span></span> <ul><li><span data-ttu-id="65135-122">Transfert des shifts\*</span><span class="sxs-lookup"><span data-stu-id="65135-122">Shifts handoff\*</span></span></li><li><span data-ttu-id="65135-123">Formation\*</span><span class="sxs-lookup"><span data-stu-id="65135-123">Learning\*</span></span></li></ul><span data-ttu-id="65135-124">\*Canaux favoris automatiquement</span><span class="sxs-lookup"><span data-stu-id="65135-124">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="65135-125">Propriétés de l’équipe</span><span class="sxs-lookup"><span data-stu-id="65135-125">Team properties</span></span> <ul><li><span data-ttu-id="65135-126">Visibilité de l’équipe définie sur Public</span><span class="sxs-lookup"><span data-stu-id="65135-126">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="65135-127">Autorisations des membres</span><span class="sxs-lookup"><span data-stu-id="65135-127">Member permissions</span></span> <ul><li><span data-ttu-id="65135-128">Création/mise à jour/suppression de canaux intéléments</span><span class="sxs-lookup"><span data-stu-id="65135-128">Can't create/update/delete channels</span></span> </li><li><span data-ttu-id="65135-129">Ajout/suppression d’applications non disponibles</span><span class="sxs-lookup"><span data-stu-id="65135-129">Can't add/remove apps</span></span> </li><li><span data-ttu-id="65135-130">Création/mise à jour/suppression d’onglets</span><span class="sxs-lookup"><span data-stu-id="65135-130">Can't create/update/remove tabs</span></span></li><li><span data-ttu-id="65135-131">Créer/mettre à jour/supprimer des connecteurs</span><span class="sxs-lookup"><span data-stu-id="65135-131">Can't create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="65135-132">Méthodes recommandées pour personnaliser le modèle du Store pour votre organisation :</span><span class="sxs-lookup"><span data-stu-id="65135-132">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="65135-133">Si votre organisation possède des services au sein de chaque magasin, ajoutez un canal pour chaque service.</span><span class="sxs-lookup"><span data-stu-id="65135-133">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="65135-134">L’ajout d’un canal facilite la communication et la collaboration au sein du service.</span><span class="sxs-lookup"><span data-stu-id="65135-134">Adding a channel facilitates communication and collaboration within the department.</span></span>

- <span data-ttu-id="65135-135">Si votre organisation possède des sites web internes (par exemple, un site SharePoint), vous pouvez les épingler sous la la direction d’onglets dans le canal d’équipe approprié.</span><span class="sxs-lookup"><span data-stu-id="65135-135">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="65135-136">[Reportez-vous aux modèles De mise en page de Teams](get-started-with-teams-templates.md) pour obtenir des instructions.</span><span class="sxs-lookup"><span data-stu-id="65135-136">Refer to [Get started with Teams templates](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="manager-collaboration-template"></a><span data-ttu-id="65135-137">Modèle de collaboration avec les responsables</span><span class="sxs-lookup"><span data-stu-id="65135-137">Manager Collaboration template</span></span>

<span data-ttu-id="65135-138">Le modèle Collaboration avec le responsable est un autre des modèles Teams conçus selon les besoins des revendeurs.</span><span class="sxs-lookup"><span data-stu-id="65135-138">The Manager Collaboration template is another one of the Teams templates designed around retailer needs.</span></span> <span data-ttu-id="65135-139">Le modèle collaboration avec les responsables est idéal pour créer une équipe pour un ensemble de responsables qui collaborent entre plusieurs magasins/régions, et bien plus encore.</span><span class="sxs-lookup"><span data-stu-id="65135-139">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, and more.</span></span> <span data-ttu-id="65135-140">Par exemple, si votre organisation possède des régions, vous pouvez créer une équipe de collaboration de responsable pour la région Californie et y inclure tous les responsables de magasin, ainsi que le responsable régional de cette région.</span><span class="sxs-lookup"><span data-stu-id="65135-140">For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="65135-141">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="65135-141">Base template type</span></span> | <span data-ttu-id="65135-142">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="65135-142">baseTemplateId</span></span> | <span data-ttu-id="65135-143">Propriétés de ce modèle de base</span><span class="sxs-lookup"><span data-stu-id="65135-143">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="65135-144">Vente au détail -</span><span class="sxs-lookup"><span data-stu-id="65135-144">Retail -</span></span> <br><span data-ttu-id="65135-145">Magasin</span><span class="sxs-lookup"><span data-stu-id="65135-145">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="65135-146">Canaux</span><span class="sxs-lookup"><span data-stu-id="65135-146">Channels</span></span> <ul><li><span data-ttu-id="65135-147">Opérations\*</span><span class="sxs-lookup"><span data-stu-id="65135-147">Operations\*</span></span></li><li><span data-ttu-id="65135-148">Formation\*</span><span class="sxs-lookup"><span data-stu-id="65135-148">Learning\*</span></span></li></ul><span data-ttu-id="65135-149">\*Canaux favoris automatiquement</span><span class="sxs-lookup"><span data-stu-id="65135-149">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="65135-150">Propriétés de l’équipe</span><span class="sxs-lookup"><span data-stu-id="65135-150">Team properties</span></span> <ul><li><span data-ttu-id="65135-151">Visibilité de l’équipe définie sur Privé</span><span class="sxs-lookup"><span data-stu-id="65135-151">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="65135-152">Autorisations des membres</span><span class="sxs-lookup"><span data-stu-id="65135-152">Member permissions</span></span> <ul><li><span data-ttu-id="65135-153">Peut créer/mettre à jour/supprimer des canaux</span><span class="sxs-lookup"><span data-stu-id="65135-153">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="65135-154">Peut ajouter/supprimer des applications</span><span class="sxs-lookup"><span data-stu-id="65135-154">Can add/remove apps</span></span> </li><li><span data-ttu-id="65135-155">Création/mise à jour/suppression d’onglets</span><span class="sxs-lookup"><span data-stu-id="65135-155">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="65135-156">Peut créer/mettre à jour/supprimer des connecteurs</span><span class="sxs-lookup"><span data-stu-id="65135-156">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="65135-157">Méthodes recommandées pour personnaliser le modèle de collaboration avec les responsables pour votre organisation :</span><span class="sxs-lookup"><span data-stu-id="65135-157">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="65135-158">Si votre organisation possède des sites web internes, tels qu’un site SharePoint, qui sont appropriés pour les responsables, vous envisagez de les épingler en tant qu’onglets dans un canal d’équipe approprié.</span><span class="sxs-lookup"><span data-stu-id="65135-158">If your organization has any internal websites, such as a SharePoint site, that are relevant for managers, consider pinning them as tabs in a relevant team channel.</span></span> <span data-ttu-id="65135-159">Pour obtenir des instructions, vous pouvez vous baser sur la documentation du modèle [Microsoft Teams.](get-started-with-teams-templates.md)</span><span class="sxs-lookup"><span data-stu-id="65135-159">You can take a look at the [Microsoft Teams Template documentation](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="65135-160">Comment utiliser des modèles de premier groupe</span><span class="sxs-lookup"><span data-stu-id="65135-160">How to use first party templates</span></span>

<span data-ttu-id="65135-161">Pour utiliser ces modèles, modifiez la propriété « template@odata.bind » dans le corps de la demande de « standard » à la propriété TemplateIDs ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="65135-161">To use these templates, change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="65135-162">Pour plus d’informations sur le déploiement de modèles Teams, voir l’article Microsoft Graph sur la création [d’une équipe.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="65135-162">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="65135-163">Les canaux du modèle sont automatiquement créés sous l’onglet Général.</span><span class="sxs-lookup"><span data-stu-id="65135-163">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-store-template-extension-script"></a><span data-ttu-id="65135-164">Exemple : Script d’extension de modèle Store</span><span class="sxs-lookup"><span data-stu-id="65135-164">Example: Store template extension script</span></span>

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
## <a name="relate-topic"></a><span data-ttu-id="65135-165">Sujet lié</span><span class="sxs-lookup"><span data-stu-id="65135-165">Relate topic</span></span>

[<span data-ttu-id="65135-166">Utiliser les modèles Teams dans le Centre d’administration</span><span class="sxs-lookup"><span data-stu-id="65135-166">Get started with Teams templates in the Admin center</span></span>](get-started-with-teams-templates-in-the-admin-console.md)
