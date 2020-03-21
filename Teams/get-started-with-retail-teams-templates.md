---
title: Prise en main des modèles Teams de vente au détail
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser les modèles teams pour créer des structures d’équipe conçues pour les besoins des détaillants.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: ec16f919bad5ed696741664836aa3d7127837c5a
ms.sourcegitcommit: 92a278c0145798266ecbe052e645b2259bcbd62d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/21/2020
ms.locfileid: "42892364"
---
# <a name="get-started-with-teams-templates-in-retail"></a><span data-ttu-id="b0c64-103">Prise en main des modèles Teams de vente au détail</span><span class="sxs-lookup"><span data-stu-id="b0c64-103">Get started with Teams templates in retail</span></span> 

<span data-ttu-id="b0c64-104">Les modèles d’équipes vous permettent de créer rapidement et facilement des équipes en fournissant un modèle prédéfini de paramètres, de canaux et d’applications déjà installées.</span><span class="sxs-lookup"><span data-stu-id="b0c64-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="b0c64-105">Les modèles d’équipes sont dotés de définitions prédéfinies de structures d’équipe conçues en fonction des besoins des détaillants.</span><span class="sxs-lookup"><span data-stu-id="b0c64-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="b0c64-106">Vous pouvez utiliser les modèles teams pour créer rapidement des types d’équipes adaptées aux détaillants et à déployer au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b0c64-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="b0c64-107">Vous pouvez également développer les modèles teams pour créer des équipes adaptées aux besoins spécifiques de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b0c64-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="b0c64-108">Dans cet article, nous allons présenter chacun des modèles d’équipes et la façon dont nous vous conseillons de les utiliser.</span><span class="sxs-lookup"><span data-stu-id="b0c64-108">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="b0c64-109">Cet article est pour vous si vous êtes responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation commerciale.</span><span class="sxs-lookup"><span data-stu-id="b0c64-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="b0c64-110">Nous partons du principe que vous avez déjà déployé teams service au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b0c64-110">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="b0c64-111">Si vous n’avez pas encore déployé Teams, commencez par lire la rubrique [comment déployer Microsoft teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b0c64-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="b0c64-112">Pour en savoir plus sur les modèles d’équipe en général, consultez la rubrique [commencer à utiliser les modèles](get-started-with-teams-templates.md)Teams.</span><span class="sxs-lookup"><span data-stu-id="b0c64-112">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="store-template"></a><span data-ttu-id="b0c64-113">Modèle du Windows Store</span><span class="sxs-lookup"><span data-stu-id="b0c64-113">Store template</span></span>

<span data-ttu-id="b0c64-114">Le modèle Windows Store est idéal pour créer une équipe et représenter une adresse de magasin commerciale individuelle.</span><span class="sxs-lookup"><span data-stu-id="b0c64-114">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="b0c64-115">À l’aide du modèle Windows Store, vous pouvez créer une équipe pour chaque emplacement de magasin commercial au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b0c64-115">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="b0c64-116">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="b0c64-116">Base template type</span></span> | <span data-ttu-id="b0c64-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="b0c64-117">baseTemplateId</span></span> | <span data-ttu-id="b0c64-118">Propriétés fournies avec ce modèle de base</span><span class="sxs-lookup"><span data-stu-id="b0c64-118">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="b0c64-119">Revendeur</span><span class="sxs-lookup"><span data-stu-id="b0c64-119">Retail -</span></span> <br><span data-ttu-id="b0c64-120">Boutique d’applications</span><span class="sxs-lookup"><span data-stu-id="b0c64-120">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="b0c64-121">Canaux</span><span class="sxs-lookup"><span data-stu-id="b0c64-121">Channels</span></span> <ul><li><span data-ttu-id="b0c64-122">Transfert de décalage\*</span><span class="sxs-lookup"><span data-stu-id="b0c64-122">Shifts handoff\*</span></span></li><li><span data-ttu-id="b0c64-123">LMS\*</span><span class="sxs-lookup"><span data-stu-id="b0c64-123">Learning\*</span></span></li></ul><span data-ttu-id="b0c64-124">\*Canaux favoris automatiquement</span><span class="sxs-lookup"><span data-stu-id="b0c64-124">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="b0c64-125">Propriétés d’équipe</span><span class="sxs-lookup"><span data-stu-id="b0c64-125">Team properties</span></span> <ul><li><span data-ttu-id="b0c64-126">Visibilité de l’équipe définie sur publique</span><span class="sxs-lookup"><span data-stu-id="b0c64-126">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="b0c64-127">Autorisations des membres</span><span class="sxs-lookup"><span data-stu-id="b0c64-127">Member permissions</span></span> <ul><li><span data-ttu-id="b0c64-128">Création/mise à jour/suppression de canaux impossible</span><span class="sxs-lookup"><span data-stu-id="b0c64-128">Cannot create/update/delete channels</span></span> </li><li><span data-ttu-id="b0c64-129">Impossible d’ajouter/supprimer des applications</span><span class="sxs-lookup"><span data-stu-id="b0c64-129">Cannot add/remove apps</span></span> </li><li><span data-ttu-id="b0c64-130">Impossible de créer/mettre à jour/supprimer des onglets</span><span class="sxs-lookup"><span data-stu-id="b0c64-130">Cannot create/update/remove tabs</span></span></li><li><span data-ttu-id="b0c64-131">Création/mise à jour/suppression de connecteurs impossible</span><span class="sxs-lookup"><span data-stu-id="b0c64-131">Cannot create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="b0c64-132">Méthodes conseillées pour personnaliser le modèle Windows Store pour votre organisation :</span><span class="sxs-lookup"><span data-stu-id="b0c64-132">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="b0c64-133">Si votre organisation a des services dans chaque banque, ajoutez un canal pour chaque service.</span><span class="sxs-lookup"><span data-stu-id="b0c64-133">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="b0c64-134">Cela facilite la communication et la collaboration au sein du service.</span><span class="sxs-lookup"><span data-stu-id="b0c64-134">This will facilitate communication and collaboration within the department.</span></span>

- <span data-ttu-id="b0c64-135">Si votre organisation a des sites Web internes (par exemple, un site SharePoint), envisagez de les épingler en tant qu’onglets du canal d’équipe approprié.</span><span class="sxs-lookup"><span data-stu-id="b0c64-135">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="b0c64-136">Pour obtenir des instructions, voir [commencer à utiliser les modèles teams](get-started-with-teams-templates.md) .</span><span class="sxs-lookup"><span data-stu-id="b0c64-136">Refer to [Get started with Teams templates](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="manager-collaboration-template"></a><span data-ttu-id="b0c64-137">Modèle de collaboration responsable</span><span class="sxs-lookup"><span data-stu-id="b0c64-137">Manager Collaboration template</span></span>

<span data-ttu-id="b0c64-138">Le modèle de collaboration responsable est l’un des modèles d’équipe pour les besoins des détaillants.</span><span class="sxs-lookup"><span data-stu-id="b0c64-138">The Manager Collaboration template is another one of the Teams templates designed around retailer needs.</span></span> <span data-ttu-id="b0c64-139">Le modèle de collaboration responsable est idéal pour créer une équipe pour un ensemble de responsables pour collaborer entre des boutiques et des régions, etc. Par exemple, si votre organisation a des régions, vous pouvez créer une équipe de collaboration en chef pour la région Californie et inclure tous les responsables du Windows Store de cette région ainsi que le responsable régional de cette région.</span><span class="sxs-lookup"><span data-stu-id="b0c64-139">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="b0c64-140">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="b0c64-140">Base template type</span></span> | <span data-ttu-id="b0c64-141">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="b0c64-141">baseTemplateId</span></span> | <span data-ttu-id="b0c64-142">Propriétés fournies avec ce modèle de base</span><span class="sxs-lookup"><span data-stu-id="b0c64-142">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="b0c64-143">Revendeur</span><span class="sxs-lookup"><span data-stu-id="b0c64-143">Retail -</span></span> <br><span data-ttu-id="b0c64-144">Boutique d’applications</span><span class="sxs-lookup"><span data-stu-id="b0c64-144">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="b0c64-145">Canaux</span><span class="sxs-lookup"><span data-stu-id="b0c64-145">Channels</span></span> <ul><li><span data-ttu-id="b0c64-146">Opérations\*</span><span class="sxs-lookup"><span data-stu-id="b0c64-146">Operations\*</span></span></li><li><span data-ttu-id="b0c64-147">LMS\*</span><span class="sxs-lookup"><span data-stu-id="b0c64-147">Learning\*</span></span></li></ul><span data-ttu-id="b0c64-148">\*Canaux favoris automatiquement</span><span class="sxs-lookup"><span data-stu-id="b0c64-148">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="b0c64-149">Propriétés d’équipe</span><span class="sxs-lookup"><span data-stu-id="b0c64-149">Team properties</span></span> <ul><li><span data-ttu-id="b0c64-150">Visibilité de l’équipe définie sur privée</span><span class="sxs-lookup"><span data-stu-id="b0c64-150">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="b0c64-151">Autorisations des membres</span><span class="sxs-lookup"><span data-stu-id="b0c64-151">Member permissions</span></span> <ul><li><span data-ttu-id="b0c64-152">Création/mise à jour/suppression de canaux</span><span class="sxs-lookup"><span data-stu-id="b0c64-152">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="b0c64-153">Ajout/suppression d’applications</span><span class="sxs-lookup"><span data-stu-id="b0c64-153">Can add/remove apps</span></span> </li><li><span data-ttu-id="b0c64-154">Peut créer/mettre à jour/supprimer des onglets</span><span class="sxs-lookup"><span data-stu-id="b0c64-154">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="b0c64-155">Création/mise à jour/suppression de connecteurs possibles</span><span class="sxs-lookup"><span data-stu-id="b0c64-155">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="b0c64-156">Méthodes conseillées pour personnaliser le modèle de collaboration responsable de votre organisation :</span><span class="sxs-lookup"><span data-stu-id="b0c64-156">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="b0c64-157">Si votre organisation a des sites Web internes (par exemple, un site SharePoint) qui sont appropriés pour les responsables, envisagez de les épingler en tant qu’onglets dans un canal d’équipe approprié (voir la documentation [ici](get-started-with-teams-templates.md) pour obtenir des instructions).</span><span class="sxs-lookup"><span data-stu-id="b0c64-157">If your organization has any internal websites (for example, a SharePoint site) that are relevant for managers, consider pinning them as tabs in a relevant team channel (refer to documentation [here](get-started-with-teams-templates.md) for instructions).</span></span>

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="b0c64-158">Utilisation de modèles de première partie</span><span class="sxs-lookup"><span data-stu-id="b0c64-158">How to use first party templates</span></span>

<span data-ttu-id="b0c64-159">Pour utiliser ces modèles, il vous suffit de changer la propriété « template@odata. bind » dans le corps de la requête de « standard » vers le TemplateIDs ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="b0c64-159">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="b0c64-160">Pour plus d’informations sur le déploiement de modèles d’équipe, voir l’article Microsoft Graph sur la [création d’une équipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="b0c64-160">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="b0c64-161">Les canaux du modèle sont automatiquement créés sous l’onglet général.</span><span class="sxs-lookup"><span data-stu-id="b0c64-161">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-store-template-extension-script"></a><span data-ttu-id="b0c64-162">Exemple : script d’extension de modèle Store</span><span class="sxs-lookup"><span data-stu-id="b0c64-162">Example: Store template extension script</span></span>

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
