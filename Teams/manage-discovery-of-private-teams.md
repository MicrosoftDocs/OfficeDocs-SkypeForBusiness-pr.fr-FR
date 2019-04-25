---
title: Gérer la découverte des équipes privées dans Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 4/25/2019
ms.reviewer: shpoddar
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment contrôler si les équipes privées pouvant être découvert par les utilisateurs de Microsoft Teams via les suggestions dans les résultats de recherche et de la galerie de l’équipe.
ms.openlocfilehash: 70d5b81bba719a9e6cc6a51d38d58fd309e07a3b
ms.sourcegitcommit: 9329d740a2060f9c055c5c0c03107a9268c0df5b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/24/2019
ms.locfileid: "33262753"
---
# <a name="manage-discovery-of-private-teams-in-microsoft-teams"></a><span data-ttu-id="c81de-103">Gérer la découverte des équipes privées dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c81de-103">Manage discovery of private teams in Microsoft Teams</span></span>

<span data-ttu-id="c81de-104">Les propriétaires de l’équipe et les administrateurs peuvent contrôler si les équipes privées pouvant être découvert par les utilisateurs Microsoft Teams dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c81de-104">Admins and team owners can control whether private teams can be discovered by Microsoft Teams users in your organization.</span></span> <span data-ttu-id="c81de-105">Lorsqu’une équipe privée est détectable, il s’affiche dans les résultats de recherche et est inclus dans les propositions dans la galerie de l’équipe avec des équipes publics dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="c81de-105">When a private team is discoverable, it shows up in search results and is included in suggestions in the team gallery alongside public teams in Teams.</span></span> <span data-ttu-id="c81de-106">Cela facilite pour les utilisateurs à rechercher pour trouver les équipes privés qu’ils souhaitent joindre.</span><span class="sxs-lookup"><span data-stu-id="c81de-106">This makes it easy for users to search for and find the private teams that they want to join.</span></span> <span data-ttu-id="c81de-107">Les utilisateurs peuvent demander à participer à une équipe privée qui un propriétaire de l’équipe puis approuver ou refuser.</span><span class="sxs-lookup"><span data-stu-id="c81de-107">Users can request to join a private team which a team owner can then approve or deny.</span></span>

## <a name="overview-of-public-teams-private-teams-and-discovery-in-teams"></a><span data-ttu-id="c81de-108">Vue d’ensemble des équipes publics privés et les équipes découverte dans les équipes</span><span class="sxs-lookup"><span data-stu-id="c81de-108">Overview of public teams, private teams, and discovery in Teams</span></span>

<span data-ttu-id="c81de-109">La plupart des organisations ont les types suivants d’équipes - équipes publics détectables privés et les équipes-découvrable équipes privés.</span><span class="sxs-lookup"><span data-stu-id="c81de-109">Most organizations have the following kinds of teams - public teams, discoverable private teams, and non-discoverable private teams.</span></span>

![Galerie d’équipe](media/private-team-discovery-team-gallery.png)

### <a name="public-teams"></a><span data-ttu-id="c81de-111">Équipes publics</span><span class="sxs-lookup"><span data-stu-id="c81de-111">Public teams</span></span>

<span data-ttu-id="c81de-112">Équipes publics sont disponibles pour tous les utilisateurs de votre organisation à rejoindre.</span><span class="sxs-lookup"><span data-stu-id="c81de-112">Public teams are available for all users in your organization to join.</span></span> <span data-ttu-id="c81de-113">Les équipes publics sont visibles par tout le monde dans la galerie des équipes et les utilisateurs peuvent participer à une équipe publique sans avoir à obtenir l’approbation du propriétaire de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="c81de-113">Public teams are visible to everyone in the teams gallery and users can join a public team without having to get approval from the team owner.</span></span> <span data-ttu-id="c81de-114">Exemples d’équipes publics une équipe pour discuter des news dans une équipe pour covoiturage personnes fonctionne, une équipe pour obtenir les commentaires dogfood pour vos produits et technologie.</span><span class="sxs-lookup"><span data-stu-id="c81de-114">Examples of public teams include a team to discuss news in technology, a team to get dogfood feedback for your products, and a team for people carpooling to work.</span></span>

### <a name="discoverable-private-teams"></a><span data-ttu-id="c81de-115">Équipes privées détectables</span><span class="sxs-lookup"><span data-stu-id="c81de-115">Discoverable private teams</span></span>

<span data-ttu-id="c81de-116">Détectables équipes privées ne peuvent être jointe lorsque le propriétaire de l’équipe ajoute les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c81de-116">Discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="c81de-117">Lorsque vous effectuez une équipe privée détectable, l’équipe est inclus dans la liste des équipes suggérées et les résultats de la recherche dans la galerie des équipes.</span><span class="sxs-lookup"><span data-stu-id="c81de-117">When you make a private team discoverable, the team is included in the list of suggested teams and search results in the teams gallery.</span></span> <span data-ttu-id="c81de-118">Utilisez des équipes privées détectables pour les projets et les groupes de votre organisation tout le monde connaît et où accéder à des conversations et les fichiers de l’équipe doivent être contrôlées.</span><span class="sxs-lookup"><span data-stu-id="c81de-118">Use discoverable private teams for projects and groups in your organization that everyone is aware of and where access to conversations and files in the team need to be controlled.</span></span> <span data-ttu-id="c81de-119">Une équipe pour votre service des ressources humaines, une équipe pour tous les gestionnaires de votre organisation et exemples une équipe pour un responsable et leurs collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="c81de-119">Examples include a team for your HR department, a team for all managers at your organization, and a team for a manager and their direct reports.</span></span>

### <a name="non-discoverable-private-teams"></a><span data-ttu-id="c81de-120">Équipes privées non-découvrable</span><span class="sxs-lookup"><span data-stu-id="c81de-120">Non-discoverable private teams</span></span>

<span data-ttu-id="c81de-121">Non-découvrable équipes privées ne peuvent être jointe lorsque le propriétaire de l’équipe ajoute les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c81de-121">Non-discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="c81de-122">Lorsque vous effectuez une équipe privée non détectables, elle a masqué dans la liste des équipes suggérées et supprimées des résultats de recherche dans la galerie des équipes.</span><span class="sxs-lookup"><span data-stu-id="c81de-122">When you make a private team not discoverable, it's hidden from the list of suggested teams and removed from search results in the teams gallery.</span></span> <span data-ttu-id="c81de-123">Utilisez-découvrable équipes de collaborer sur des sujets sensibles et hautement confidentielles.</span><span class="sxs-lookup"><span data-stu-id="c81de-123">Use non-discoverable teams to collaborate on sensitive and highly confidential topics.</span></span> <span data-ttu-id="c81de-124">Une équipe pour discuter d’une acquisition à venir et exemples une équipe pour discuter de changement de direction stratégique de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c81de-124">Examples include a team to discuss an upcoming acquisition and a team to discuss a change in your organization's strategic direction.</span></span>

## <a name="set-whether-new-private-teams-are-discoverable"></a><span data-ttu-id="c81de-125">Définir si les nouvelles équipes privées sont accessibles</span><span class="sxs-lookup"><span data-stu-id="c81de-125">Set whether new private teams are discoverable</span></span>

<span data-ttu-id="c81de-126">Lorsqu’un propriétaire de l’équipe crée une équipe privée, ils peuvent choisir de rendre accessibles en configurant le paramètre de découverte de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="c81de-126">When a team owner creates a private team, they can choose to make it discoverable by configuring the team's discovery setting.</span></span> <span data-ttu-id="c81de-127">Par défaut, nouvelles équipes privées sont utilisables dans une requête et facilement identifiables.</span><span class="sxs-lookup"><span data-stu-id="c81de-127">By default, new private teams are searchable and discoverable.</span></span> <span data-ttu-id="c81de-128">Si le propriétaire de l’équipe ne veut pas l’équipe privé s’affiche dans les résultats de recherche et les suggestions, ils peuvent désactiver le paramètre en sélectionnant **Modifier les paramètres** en regard de **cette équipe est disponible pour la recherche et facilement identifiables**.</span><span class="sxs-lookup"><span data-stu-id="c81de-128">If the team owner doesn't want the private team to show up in search results and suggestions, they can turn off the setting by selecting **Change setting** next to **This team is searchable and discoverable**.</span></span>

![paramètre de découverte de nouvelles équipes privées](media/private-team-discovery-new-team.png)

## <a name="set-whether-existing-private-teams-are-discoverable"></a><span data-ttu-id="c81de-130">Définir si les équipes privées existantes peuvent être découverts</span><span class="sxs-lookup"><span data-stu-id="c81de-130">Set whether existing private teams are discoverable</span></span>

<span data-ttu-id="c81de-131">Propriétaires de l’équipe peuvent définir le paramètre de découverte pour une équipe privée existante directement dans les paramètres de l’équipe et les administrateurs peuvent le faire à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c81de-131">Team owners can set the discovery setting for an existing private team directly in the team settings and admins can do so by using PowerShell.</span></span>

### <a name="in-team-settings"></a><span data-ttu-id="c81de-132">Dans les paramètres d’équipe</span><span class="sxs-lookup"><span data-stu-id="c81de-132">In team settings</span></span>

<span data-ttu-id="c81de-133">Dans les équipes, accédez à l’équipe privée, cliquez sur **plus d’options ˙˙˙** > **l’équipe de gestion**.</span><span class="sxs-lookup"><span data-stu-id="c81de-133">In Teams, go to the private team, click **More options ˙˙˙** > **Manage team**.</span></span> <span data-ttu-id="c81de-134">Sous l’onglet **paramètres** , développez la **détection de l’équipe**, puis désactivez ou activez la case à cocher **Activer la détectabilité** .</span><span class="sxs-lookup"><span data-stu-id="c81de-134">On the **Settings** tab, expand **Team discovery**, and then clear or select the **Turn on discoverability** check box.</span></span>

![paramètre de découverte pour les équipes privées existantes](media/private-team-discovery-existing-team.png)

### <a name="using-powershell"></a><span data-ttu-id="c81de-136">À l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="c81de-136">Using PowerShell</span></span>

<span data-ttu-id="c81de-137">Pour désactiver ou activer le paramètre de découverte pour une équipe privée existante, utilisez l’applet de commande **Set-équipe** .</span><span class="sxs-lookup"><span data-stu-id="c81de-137">Use the **Set-Team** cmdlet to turn off or turn on the discovery setting for an existing private team.</span></span> <span data-ttu-id="c81de-138">Voici un exemple illustrant comment rendre une équipe détectable :</span><span class="sxs-lookup"><span data-stu-id="c81de-138">Here's an example of how to make a team discoverable:</span></span>

    Set-Team -GroupId 0abc123d-e4f5-67gh-i890-jk1m2n345o6p -ShowInSearchAndSuggestions $true
<span data-ttu-id="c81de-139">Vous pouvez utiliser cette applet de commande dans un script pour définir le paramètre de découverte des équipes privées existantes en bloc.</span><span class="sxs-lookup"><span data-stu-id="c81de-139">You can use this cmdlet in a script to set the discovery setting of existing private teams in bulk.</span></span>

## <a name="set-whether-users-can-discover-private-teams"></a><span data-ttu-id="c81de-140">Définir si les utilisateurs peuvent découvrir des équipes privées</span><span class="sxs-lookup"><span data-stu-id="c81de-140">Set whether users can discover private teams</span></span>

<span data-ttu-id="c81de-141">En tant qu’administrateur, vous pouvez également contrôler les utilisateurs de votre organisation sont autorisés à découvrir des équipes privées dans les résultats de recherche et les suggestions équipes.</span><span class="sxs-lookup"><span data-stu-id="c81de-141">As an admin, you can also control which users in your organization are allowed to discover private teams in search results and suggestions in Teams.</span></span> <span data-ttu-id="c81de-142">Créer une stratégie à l’aide de l’applet de commande **New-CsTeamsChannelsPolicy** , puis affecter la stratégie aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c81de-142">Create a policy by using the **New-CsTeamsChannelsPolicy** cmdlet, and then assign the policy to users.</span></span>
 
<span data-ttu-id="c81de-143">Définissez le paramètre **AllowPrivateTeamDiscovery** sur **true** pour autoriser les utilisateurs auxquels la stratégie à voir détectables équipes privées dans les résultats de recherche et les suggestions.</span><span class="sxs-lookup"><span data-stu-id="c81de-143">Set the **AllowPrivateTeamDiscovery** parameter to **true** to allow users who are assigned the policy to see discoverable private teams in search results and suggestions.</span></span> <span data-ttu-id="c81de-144">Définissant le paramètre **AllowPrivateTeamDiscovery** sur **false** supprime toutes les équipes privées accessibles à partir des résultats de recherche et des suggestions pour les utilisateurs qui sont affectés à la stratégie.</span><span class="sxs-lookup"><span data-stu-id="c81de-144">Setting the **AllowPrivateTeamDiscovery** parameter to **false** removes all discoverable private teams from search results and suggestions for users who are assigned the policy.</span></span>

<span data-ttu-id="c81de-145">Par défaut, **AllowPrivateTeamDiscovery** est définie sur **true** pour tous les utilisateurs d’une organisation.</span><span class="sxs-lookup"><span data-stu-id="c81de-145">By default, **AllowPrivateTeamDiscovery** is set to **true** for all users in an organization.</span></span>

<span data-ttu-id="c81de-146">Dans cet exemple, nous créons une stratégie nommée VendorPolicy qui empêche les utilisateurs de la découverte des équipes privées apportées détectables, puis nous attribuer la stratégie à un utilisateur nommé vendoruser1.</span><span class="sxs-lookup"><span data-stu-id="c81de-146">In this example, we create a policy named VendorPolicy that prevents users from discovering any private teams that are made discoverable, and then we assign the policy to a user named vendoruser1.</span></span> 
   
     New-CsTeamsChannelsPolicy -Identity VendorPolicy -AllowPrivateTeamDiscovery $false
     Grant-CsTeamsChannelsPolicy -Identity vendoruser1@company.com -PolicyName VendorPolicy

> [!NOTE]
> <span data-ttu-id="c81de-147">Privée équipes qui ne sont pas accessibles ne sont jamais indiqués dans les résultats de recherche et de vos suggestions, quel que soit le paramètre de stratégie.</span><span class="sxs-lookup"><span data-stu-id="c81de-147">Private teams that are not discoverable are never shown in search results and suggestions, regardless of the policy setting.</span></span> <span data-ttu-id="c81de-148">Par exemple, si vous désactivez le paramètre de découverte pour une équipe privé, les utilisateurs ne peuvent pas détecter l’équipe, même si le paramètre **AllowPrivateTeamDiscovery** est défini sur **true** dans le paramètre de stratégie pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c81de-148">For example, if you turn off the discovery setting for a private team, users are unable to discover the team, even though  the **AllowPrivateTeamDiscovery** parameter is set to **true** in the policy setting for those users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c81de-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c81de-149">Related topics</span></span>
- [<span data-ttu-id="c81de-150">Aperçu de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="c81de-150">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)