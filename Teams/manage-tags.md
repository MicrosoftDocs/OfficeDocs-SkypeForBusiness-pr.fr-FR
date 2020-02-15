---
title: Gérer les balises dans Microsoft teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: acolonna
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Apprenez à gérer l’utilisation des indicateurs au sein de votre organisation dans Microsoft Teams.
ms.openlocfilehash: 3ade2f47474fe8aaf16c568e8c141dcd84526d86
ms.sourcegitcommit: 561b9bab7d6f5a621436bc85ea28ea14657e7868
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034499"
---
# <a name="manage-tags-in-microsoft-teams"></a><span data-ttu-id="1a71b-103">Gérer les balises dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="1a71b-103">Manage tags in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="1a71b-104">Cette fonctionnalité n’est pas encore affichée dans le centre d’administration Microsoft teams ?</span><span class="sxs-lookup"><span data-stu-id="1a71b-104">Don't see this feature in the Microsoft Teams admin center yet?</span></span> <span data-ttu-id="1a71b-105">Ce service est actuellement déployé et n’est peut-être pas encore disponible dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1a71b-105">It's currently being rolled out and might not be available in your organization yet.</span></span> <span data-ttu-id="1a71b-106">Pour rester au courant des nouvelles fonctionnalités de teams, consultez la [documentation Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).</span><span class="sxs-lookup"><span data-stu-id="1a71b-106">To stay on top of upcoming Teams features, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).</span></span>

<span data-ttu-id="1a71b-107">Dans Microsoft Teams, les indicateurs permettent aux utilisateurs de communiquer avec un sous-ensemble de personnes d’une équipe.</span><span class="sxs-lookup"><span data-stu-id="1a71b-107">Tags in Microsoft Teams let users communicate with a subset of people on a team.</span></span> <span data-ttu-id="1a71b-108">Les balises peuvent être ajoutées à un ou plusieurs membres de l’équipe pour se connecter facilement au sous-ensemble de personnes approprié.</span><span class="sxs-lookup"><span data-stu-id="1a71b-108">Tags can be added to one or multiple team members to easily connect with the right subset of people.</span></span> <span data-ttu-id="1a71b-109">Les propriétaires d’équipe et les membres (si la fonctionnalité est activée pour eux) peuvent ajouter un ou plusieurs indicateurs à une personne.</span><span class="sxs-lookup"><span data-stu-id="1a71b-109">Team owners and members (if the feature is enabled for them) can add one or more tags to a person.</span></span> <span data-ttu-id="1a71b-110">Vous pouvez ensuite utiliser les balises dans @mentions par tout membre de l’équipe dans un billet de canal pour communiquer uniquement aux personnes auxquelles cette balise est affectée.</span><span class="sxs-lookup"><span data-stu-id="1a71b-110">The tags can then be used in @mentions by anyone on the team in a channel post to communicate with only those people who are assigned that tag.</span></span>

> [!NOTE]
> <span data-ttu-id="1a71b-111">Les balises ne sont pas encore prises en charge dans les canaux privés.</span><span class="sxs-lookup"><span data-stu-id="1a71b-111">Tags are not yet supported in private channels.</span></span>

## <a name="how-tags-work"></a><span data-ttu-id="1a71b-112">Fonctionnement des indicateurs</span><span class="sxs-lookup"><span data-stu-id="1a71b-112">How tags work</span></span>

<span data-ttu-id="1a71b-113">Vous pouvez ajouter un indicateur à une personne d’une équipe spécifique.</span><span class="sxs-lookup"><span data-stu-id="1a71b-113">A tag can be added to a person on a specific team.</span></span> <span data-ttu-id="1a71b-114">Dès lors que vous ajoutez une balise, celle-ci peut être utilisée dans @mentions de n’importe quel canal standard de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="1a71b-114">After a tag is added, it can be used in @mentions in any standard channel of the team.</span></span> <span data-ttu-id="1a71b-115">Voici quelques exemples de la manière dont les indicateurs peuvent être utilisés dans teams :</span><span class="sxs-lookup"><span data-stu-id="1a71b-115">Here's some examples of how tags can be used in Teams:</span></span>

- <span data-ttu-id="1a71b-116">Un responsable du Windows Store veut publier une annonce dans un canal et en informer tous les caissiers.</span><span class="sxs-lookup"><span data-stu-id="1a71b-116">A store manager wants to post an announcement to a channel and notify all cashiers.</span></span>
- <span data-ttu-id="1a71b-117">Un responsable de produit de groupe veut avertir tous les responsables de produits dans un canal.</span><span class="sxs-lookup"><span data-stu-id="1a71b-117">A group product manager wants to message all product managers in a channel.</span></span>
- <span data-ttu-id="1a71b-118">Un administrateur de l’hôpital veut envoyer un message à tous les Radiologists dans un canal.</span><span class="sxs-lookup"><span data-stu-id="1a71b-118">A hospital administrator wants to send a message to all radiologists in a channel.</span></span>

<span data-ttu-id="1a71b-119">Pour en savoir plus, voir [utilisation de balises dans teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span><span class="sxs-lookup"><span data-stu-id="1a71b-119">To learn more, check out [Using tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span></span>

## <a name="manage-tags-for-your-organization"></a><span data-ttu-id="1a71b-120">Gérer les indicateurs de votre organisation</span><span class="sxs-lookup"><span data-stu-id="1a71b-120">Manage tags for your organization</span></span>

<span data-ttu-id="1a71b-121">En tant qu’administrateur, vous pouvez contrôler qui peut ajouter des balises et comment les balises sont utilisées au sein de votre organisation dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1a71b-121">As an admin, you can control who can add tags and how tags are used across your organization in the Microsoft Teams admin center.</span></span>

![Capture d’écran des paramètres de marquage dans le centre d’administration Microsoft teams](media/manage-tags-admin-settings.png)

### <a name="set-who-can-add-tags"></a><span data-ttu-id="1a71b-123">Définir qui peut ajouter des indicateurs</span><span class="sxs-lookup"><span data-stu-id="1a71b-123">Set who can add tags</span></span>

<span data-ttu-id="1a71b-124">Par défaut, les propriétaires d’équipe peuvent ajouter des balises.</span><span class="sxs-lookup"><span data-stu-id="1a71b-124">By default, team owners can add tags.</span></span> <span data-ttu-id="1a71b-125">Vous pouvez modifier ce paramètre pour autoriser les propriétaires d’équipe et les membres de l’équipe à ajouter des indicateurs ou à désactiver les indicateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1a71b-125">You can change this setting to allow team owners and team members to add tags or you can turn off tags for your organization.</span></span>

1. <span data-ttu-id="1a71b-126">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, cliquez sur > **paramètres des équipes**des **paramètres à l’échelle**de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="1a71b-126">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="1a71b-127">Sous **marquage**, en regard de l’option **étiquetage est activée pour**, sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="1a71b-127">Under **Tagging**, next to **Tagging is enabled for**, select one of the following options:</span></span>

    - <span data-ttu-id="1a71b-128">**Propriétaires et membres**d’une équipe : autoriser les propriétaires et les membres de l’équipe à ajouter des indicateurs.</span><span class="sxs-lookup"><span data-stu-id="1a71b-128">**Team owners and members**: Allow team owners and members to add tags.</span></span>
    - <span data-ttu-id="1a71b-129">**Propriétaires d’équipe**: autoriser les propriétaires d’équipe à ajouter des indicateurs.</span><span class="sxs-lookup"><span data-stu-id="1a71b-129">**Team owners**: Allow team owners to add tags.</span></span>
    - <span data-ttu-id="1a71b-130">**Désactivé**: désactiver les balises.</span><span class="sxs-lookup"><span data-stu-id="1a71b-130">**Disabled**: Turn off tags.</span></span>

### <a name="configure-tags-settings"></a><span data-ttu-id="1a71b-131">Configurer les paramètres des indicateurs</span><span class="sxs-lookup"><span data-stu-id="1a71b-131">Configure tags settings</span></span>

<span data-ttu-id="1a71b-132">Vous pouvez configurer les paramètres de balises suivants pour contrôler l’utilisation des balises au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1a71b-132">You can configure the following tags settings to control how tags are used across your organization.</span></span>

1. <span data-ttu-id="1a71b-133">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, cliquez sur > **paramètres des équipes**des **paramètres à l’échelle**de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="1a71b-133">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="1a71b-134">Sous **marquage**, définissez les éléments suivants selon les besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1a71b-134">Under **Tagging**, set the following, depending on the needs of your organization.</span></span>

    - <span data-ttu-id="1a71b-135">Le propriétaire d’une **équipe peut remplacer les personnes qui peuvent appliquer des indicateurs**: lorsque cette fonction est activée, les propriétaires d’équipe peuvent autoriser ou interdire les membres à ajouter des indicateurs dans les paramètres d’équipe.</span><span class="sxs-lookup"><span data-stu-id="1a71b-135">**Team owner can override who can apply tags**: When this is turned on, team owners can allow or disallow members to add tags in team settings.</span></span>
    - <span data-ttu-id="1a71b-136">**Les membres peuvent ajouter des indicateurs supplémentaires**: Si vous autorisez les membres de l’équipe à ajouter des indicateurs, activez cette option pour permettre aux membres de l’équipe d’ajouter des balises autres que les balises par défaut suggérées.</span><span class="sxs-lookup"><span data-stu-id="1a71b-136">**Members can add additional tags**: If you allow team members to add tags, turn this on to let team members add tags other than the suggested default tags that you set.</span></span> <span data-ttu-id="1a71b-137">Si cette option est désactivée, les membres de l’équipe peuvent uniquement utiliser les balises par défaut.</span><span class="sxs-lookup"><span data-stu-id="1a71b-137">If this is turned off, team members can only use the default tags.</span></span>
    - <span data-ttu-id="1a71b-138">**Balises par défaut suggérées**: utilisez cet indicateur pour ajouter un ensemble de balises par défaut.</span><span class="sxs-lookup"><span data-stu-id="1a71b-138">**Suggested default tags**: Use this to add a set of default tags.</span></span> <span data-ttu-id="1a71b-139">Vous pouvez ajouter jusqu’à 25 indicateurs et chaque balise peut contenir un maximum de 25 caractères.</span><span class="sxs-lookup"><span data-stu-id="1a71b-139">You can add up to 25 tags, and each tag can contain a maximum of 25 characters.</span></span> <span data-ttu-id="1a71b-140">Les propriétaires d’équipe et les membres (si la fonctionnalité est activée pour eux) peuvent utiliser ces suggestions, y ajouter ou créer un ensemble de balises.</span><span class="sxs-lookup"><span data-stu-id="1a71b-140">Team owners and members (if the feature is enabled for them) can use these suggestions, add to them, or create a new set of tags.</span></span>

## <a name="manage-tags-settings-for-a-team"></a><span data-ttu-id="1a71b-141">Gérer les paramètres des indicateurs pour une équipe</span><span class="sxs-lookup"><span data-stu-id="1a71b-141">Manage tags settings for a team</span></span>

<span data-ttu-id="1a71b-142">Si vous avez activé la case à coadresse le propriétaire de l' **équipe peut remplacer les utilisateurs qui peuvent appliquer des indicateurs** dans le centre d’administration Microsoft Teams, les propriétaires d’équipe peuvent définir si les membres peuvent ajouter des balises au niveau de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="1a71b-142">If you turned on the **Team owner can override who can apply tags** setting in the Microsoft Teams admin center, team owners can set whether members can add tags at the team level.</span></span> <span data-ttu-id="1a71b-143">Pour ce faire, dans l’onglet **paramètres** d’une équipe, accédez à **balises**, puis sélectionnez qui peut ajouter des indicateurs.</span><span class="sxs-lookup"><span data-stu-id="1a71b-143">To do this, on the **Settings** tab for a team, go to **Tags**, and then choose who can add tags.</span></span>

![Capture d’écran du paramètre balises au niveau de l’équipe](media/manage-tags-team-settings.png)

## <a name="add-tags-in-teams"></a><span data-ttu-id="1a71b-145">Ajouter des balises dans teams</span><span class="sxs-lookup"><span data-stu-id="1a71b-145">Add tags in Teams</span></span>

<span data-ttu-id="1a71b-146">Dans Microsoft Teams, l’onglet **membres** de la page gérer l’équipe d’une équipe comprend une colonne **balises** .</span><span class="sxs-lookup"><span data-stu-id="1a71b-146">In Teams, the **Members** tab of the Manage team page for a team includes a **Tags** column.</span></span> <span data-ttu-id="1a71b-147">Les propriétaires d’équipe et les membres (si la fonctionnalité est activée pour eux), vous pouvez cliquer sur **gérer les indicateurs** en regard d’un membre pour afficher la liste des balises suggérées pour ce membre et ajouter des indicateurs à la liste.</span><span class="sxs-lookup"><span data-stu-id="1a71b-147">Team owners and members (if the feature is enabled for them) can click **Manage tags** next to a member to see the list of suggested tags for that member and add tags to the list.</span></span>

![<span data-ttu-id="1a71b-148">Capture d’écran de l’application de balises dans le client teams</span><span class="sxs-lookup"><span data-stu-id="1a71b-148">Screenshot of how to apply tags in the Teams client</span></span> ](media/manage-tags-teams.png) 
