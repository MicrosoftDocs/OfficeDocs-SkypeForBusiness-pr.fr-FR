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
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Apprenez à contrôler si les équipes privées peuvent être détectées par les utilisateurs de Microsoft teams par le biais de suggestions dans la Galerie d’équipe et les résultats de recherche.
ms.openlocfilehash: faae4c53f4fa17668ea69a783211e7ebe01bd4d6
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494625"
---
# <a name="manage-discovery-of-private-teams-in-microsoft-teams"></a><span data-ttu-id="217dc-103">Gérer la découverte des équipes privées dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="217dc-103">Manage discovery of private teams in Microsoft Teams</span></span>

> [!INCLUDE [preview feature](includes/preview-feature.md)] 

<span data-ttu-id="217dc-104">Les administrateurs et les propriétaires d’équipe peuvent contrôler si des équipes privées peuvent être découvertes par les utilisateurs de Microsoft teams au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="217dc-104">Admins and team owners can control whether private teams can be discovered by Microsoft Teams users in your organization.</span></span> <span data-ttu-id="217dc-105">Lorsqu’une équipe privée est détectable, elle apparaît dans les résultats de la recherche et est incluse dans les suggestions de la Galerie d’équipes et dans les équipes publiques de teams.</span><span class="sxs-lookup"><span data-stu-id="217dc-105">When a private team is discoverable, it shows up in search results and is included in suggestions in the team gallery alongside public teams in Teams.</span></span> <span data-ttu-id="217dc-106">Cela permet aux utilisateurs de rechercher et d’accéder facilement aux équipes privées qu’ils souhaitent rejoindre.</span><span class="sxs-lookup"><span data-stu-id="217dc-106">This makes it easy for users to search for and find the private teams that they want to join.</span></span> <span data-ttu-id="217dc-107">Les utilisateurs peuvent faire une demande de participation à une équipe privée qu’un propriétaire d’équipe peut ensuite approuver ou refuser.</span><span class="sxs-lookup"><span data-stu-id="217dc-107">Users can request to join a private team which a team owner can then approve or deny.</span></span>

## <a name="overview-of-public-teams-private-teams-and-discovery-in-teams"></a><span data-ttu-id="217dc-108">Vue d’ensemble des équipes publiques, des équipes privées et de la découverte dans teams</span><span class="sxs-lookup"><span data-stu-id="217dc-108">Overview of public teams, private teams, and discovery in Teams</span></span>

<span data-ttu-id="217dc-109">La plupart des organisations ont les types d’équipes suivants: équipes publiques, équipes privées détectable et équipes privées non détectablees.</span><span class="sxs-lookup"><span data-stu-id="217dc-109">Most organizations have the following kinds of teams - public teams, discoverable private teams, and non-discoverable private teams.</span></span>

![Capture d’écran de la Galerie d’équipes](media/private-team-discovery-team-gallery.png)

### <a name="public-teams"></a><span data-ttu-id="217dc-111">Équipes publiques</span><span class="sxs-lookup"><span data-stu-id="217dc-111">Public teams</span></span>

<span data-ttu-id="217dc-112">Les équipes publiques sont disponibles pour permettre à tous les utilisateurs de votre organisation de participer.</span><span class="sxs-lookup"><span data-stu-id="217dc-112">Public teams are available for all users in your organization to join.</span></span> <span data-ttu-id="217dc-113">Les équipes publiques sont visibles par tout le monde dans la Galerie d’équipes, et les utilisateurs peuvent rejoindre une équipe publique sans avoir besoin d’obtenir l’approbation du propriétaire de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="217dc-113">Public teams are visible to everyone in the teams gallery and users can join a public team without having to get approval from the team owner.</span></span> <span data-ttu-id="217dc-114">Par exemple, les équipes publiques incluent une équipe pour discuter des actualités en technologie, une équipe pour obtenir le retour de vos produits et une équipe pour les personnes carpooling de travailler.</span><span class="sxs-lookup"><span data-stu-id="217dc-114">Examples of public teams include a team to discuss news in technology, a team to get dogfood feedback for your products, and a team for people carpooling to work.</span></span>

### <a name="discoverable-private-teams"></a><span data-ttu-id="217dc-115">Équipe privée détectable</span><span class="sxs-lookup"><span data-stu-id="217dc-115">Discoverable private teams</span></span>

<span data-ttu-id="217dc-116">Les équipes privées détectables ne peuvent être jointes que lorsque le propriétaire de l’équipe y ajoute des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="217dc-116">Discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="217dc-117">Lorsque vous rendez une équipe privée détectable, l’équipe est incluse dans la liste des équipes et des résultats de recherche suggérés dans la Galerie d’équipes.</span><span class="sxs-lookup"><span data-stu-id="217dc-117">When you make a private team discoverable, the team is included in the list of suggested teams and search results in the teams gallery.</span></span> <span data-ttu-id="217dc-118">Utilisez les équipes privées détectables pour les projets et groupes de votre organisation que tout le monde a pris en considération et où l’accès à des conversations et des fichiers dans l’équipe doit être contrôlé.</span><span class="sxs-lookup"><span data-stu-id="217dc-118">Use discoverable private teams for projects and groups in your organization that everyone is aware of and where access to conversations and files in the team need to be controlled.</span></span> <span data-ttu-id="217dc-119">Les exemples incluent une équipe pour votre service de ressources humaines, une équipe pour tous les responsables au sein de votre organisation ainsi qu’une équipe pour un responsable et leurs rapports directs.</span><span class="sxs-lookup"><span data-stu-id="217dc-119">Examples include a team for your HR department, a team for all managers at your organization, and a team for a manager and their direct reports.</span></span>

### <a name="non-discoverable-private-teams"></a><span data-ttu-id="217dc-120">Équipes privées non détectable</span><span class="sxs-lookup"><span data-stu-id="217dc-120">Non-discoverable private teams</span></span>

<span data-ttu-id="217dc-121">Les équipes privées non détectablees ne peuvent être jointes que lorsque le propriétaire de l’équipe y ajoute des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="217dc-121">Non-discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="217dc-122">Lorsque vous rendez une équipe privée non détectable, celle-ci est masquée dans la liste des équipes suggérées et supprimées des résultats de recherche dans la Galerie d’équipes.</span><span class="sxs-lookup"><span data-stu-id="217dc-122">When you make a private team not discoverable, it's hidden from the list of suggested teams and removed from search results in the teams gallery.</span></span> <span data-ttu-id="217dc-123">Utilisez des équipes non détectable pour collaborer sur des sujets sensibles et hautement confidentiels.</span><span class="sxs-lookup"><span data-stu-id="217dc-123">Use non-discoverable teams to collaborate on sensitive and highly confidential topics.</span></span> <span data-ttu-id="217dc-124">Les exemples incluent une équipe pour discuter d’une prochaine acquisition et une équipe pour discuter d’une modification apportée à la direction stratégique de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="217dc-124">Examples include a team to discuss an upcoming acquisition and a team to discuss a change in your organization's strategic direction.</span></span>

## <a name="set-whether-new-private-teams-are-discoverable"></a><span data-ttu-id="217dc-125">Définir si de nouvelles équipes privées peuvent être découvertes</span><span class="sxs-lookup"><span data-stu-id="217dc-125">Set whether new private teams are discoverable</span></span>

<span data-ttu-id="217dc-126">Lorsque le propriétaire d’une équipe crée une équipe privée, il peut choisir de le rendre détectable en configurant le paramètre de découverte de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="217dc-126">When a team owner creates a private team, they can choose to make it discoverable by configuring the team's discovery setting.</span></span> <span data-ttu-id="217dc-127">Par défaut, les nouvelles équipes privées peuvent être recherchées et détectables.</span><span class="sxs-lookup"><span data-stu-id="217dc-127">By default, new private teams are searchable and discoverable.</span></span> <span data-ttu-id="217dc-128">Si le propriétaire de l’équipe ne souhaite pas qu’elle apparaisse dans les résultats de recherche et les suggestions, elle peut désactiver le paramètre en sélectionnant l' **option modifier les paramètres** en regard de **cette équipe est consultable et détectable**.</span><span class="sxs-lookup"><span data-stu-id="217dc-128">If the team owner doesn't want the private team to show up in search results and suggestions, they can turn off the setting by selecting **Change setting** next to **This team is searchable and discoverable**.</span></span>

![Capture d’écran du paramètre de découverte pour les nouvelles équipes privées](media/private-team-discovery-new-team.png)

## <a name="set-whether-existing-private-teams-are-discoverable"></a><span data-ttu-id="217dc-130">Définir si les équipes privées existantes sont détectables</span><span class="sxs-lookup"><span data-stu-id="217dc-130">Set whether existing private teams are discoverable</span></span>

<span data-ttu-id="217dc-131">Les propriétaires d’une équipe peuvent définir le paramètre de découverte pour une équipe privée existante directement dans les paramètres de l’équipe et les administrateurs peuvent le faire à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="217dc-131">Team owners can set the discovery setting for an existing private team directly in the team settings and admins can do so by using PowerShell.</span></span>

### <a name="in-team-settings"></a><span data-ttu-id="217dc-132">Dans les paramètres d’équipe</span><span class="sxs-lookup"><span data-stu-id="217dc-132">In team settings</span></span>

<span data-ttu-id="217dc-133">Dans Teams, accédez à l’équipe privée, cliquez sur **plus d’options ̇ ̇ ̇** > **gérer l’équipe**.</span><span class="sxs-lookup"><span data-stu-id="217dc-133">In Teams, go to the private team, click **More options ˙˙˙** > **Manage team**.</span></span> <span data-ttu-id="217dc-134">Dans l’onglet **paramètres** , développez **découverte d’équipe**, puis cochez ou décochez la case Activer la **détectabilité** .</span><span class="sxs-lookup"><span data-stu-id="217dc-134">On the **Settings** tab, expand **Team discovery**, and then clear or select the **Turn on discoverability** check box.</span></span>

![Capture d’écran du paramètre de découverte pour les équipes privées existantes](media/private-team-discovery-existing-team.png)

### <a name="using-powershell-coming-soon"></a><span data-ttu-id="217dc-136">Utiliser PowerShell (bientôt disponible)</span><span class="sxs-lookup"><span data-stu-id="217dc-136">Using PowerShell (coming soon)</span></span>

<span data-ttu-id="217dc-137">Utilisez l’applet de connexion **Set-Team** pour désactiver ou activer le paramètre de découverte pour une équipe privée existante.</span><span class="sxs-lookup"><span data-stu-id="217dc-137">Use the **Set-Team** cmdlet to turn off or turn on the discovery setting for an existing private team.</span></span> <span data-ttu-id="217dc-138">Voici un exemple illustrant comment rendre une équipe plus détectable:</span><span class="sxs-lookup"><span data-stu-id="217dc-138">Here's an example of how to make a team discoverable:</span></span>

    Set-Team -GroupId 0abc123d-e4f5-67gh-i890-jk1m2n345o6p -ShowInSearchAndSuggestions $true
<span data-ttu-id="217dc-139">Vous pouvez utiliser cette applet de cmdlet dans un script pour définir le paramètre de découverte des équipes privées existantes en bloc.</span><span class="sxs-lookup"><span data-stu-id="217dc-139">You can use this cmdlet in a script to set the discovery setting of existing private teams in bulk.</span></span>

## <a name="set-whether-users-can-discover-private-teams"></a><span data-ttu-id="217dc-140">Définir si les utilisateurs peuvent découvrir les équipes privées</span><span class="sxs-lookup"><span data-stu-id="217dc-140">Set whether users can discover private teams</span></span>

<span data-ttu-id="217dc-141">En tant qu’administrateur, vous pouvez également contrôler les utilisateurs de votre organisation qui sont autorisés à découvrir des équipes privées dans les résultats de recherche et les suggestions dans Teams.</span><span class="sxs-lookup"><span data-stu-id="217dc-141">As an admin, you can also control which users in your organization are allowed to discover private teams in search results and suggestions in Teams.</span></span> <span data-ttu-id="217dc-142">Créez une stratégie à l’aide de l’applet de **nouvelle applet de nouveau-CsTeamsChannelsPolicy** , puis affectez la stratégie aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="217dc-142">Create a policy by using the **New-CsTeamsChannelsPolicy** cmdlet, and then assign the policy to users.</span></span>
 
<span data-ttu-id="217dc-143">Définissez le paramètre **AllowPrivateTeamDiscovery** sur **true** pour autoriser les utilisateurs auxquels une stratégie est affectée pour voir les équipes privées détectables dans les résultats de recherche et les suggestions.</span><span class="sxs-lookup"><span data-stu-id="217dc-143">Set the **AllowPrivateTeamDiscovery** parameter to **true** to allow users who are assigned the policy to see discoverable private teams in search results and suggestions.</span></span> <span data-ttu-id="217dc-144">Le fait de définir le paramètre **AllowPrivateTeamDiscovery** sur **false** entraîne la suppression de toutes les équipes privées détectable des résultats de la recherche et des suggestions pour les utilisateurs auxquels cette stratégie est affectée.</span><span class="sxs-lookup"><span data-stu-id="217dc-144">Setting the **AllowPrivateTeamDiscovery** parameter to **false** removes all discoverable private teams from search results and suggestions for users who are assigned the policy.</span></span>

<span data-ttu-id="217dc-145">Par défaut, **AllowPrivateTeamDiscovery** est défini sur **true** pour tous les utilisateurs au sein d’une organisation.</span><span class="sxs-lookup"><span data-stu-id="217dc-145">By default, **AllowPrivateTeamDiscovery** is set to **true** for all users in an organization.</span></span>

<span data-ttu-id="217dc-146">Dans cet exemple, nous créons une stratégie nommée VendorPolicy qui empêche les utilisateurs de découvrir toutes les équipes privées découvertes, puis nous affectons la stratégie à un utilisateur nommé vendoruser1.</span><span class="sxs-lookup"><span data-stu-id="217dc-146">In this example, we create a policy named VendorPolicy that prevents users from discovering any private teams that are made discoverable, and then we assign the policy to a user named vendoruser1.</span></span> 
   
     New-CsTeamsChannelsPolicy -Identity VendorPolicy -AllowPrivateTeamDiscovery $false
     Grant-CsTeamsChannelsPolicy -Identity vendoruser1@company.com -PolicyName VendorPolicy

> [!NOTE]
> <span data-ttu-id="217dc-147">Les équipes privées qui ne sont pas détectables ne sont jamais affichées dans les résultats de recherche et les suggestions, indépendamment du paramètre de stratégie.</span><span class="sxs-lookup"><span data-stu-id="217dc-147">Private teams that are not discoverable are never shown in search results and suggestions, regardless of the policy setting.</span></span> <span data-ttu-id="217dc-148">Par exemple, si vous désactivez le paramètre de découverte pour une équipe privée, les utilisateurs ne parviennent pas à découvrir l’équipe, même si le paramètre **AllowPrivateTeamDiscovery** est défini sur **true** dans le paramètre de stratégie pour ces utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="217dc-148">For example, if you turn off the discovery setting for a private team, users are unable to discover the team, even though  the **AllowPrivateTeamDiscovery** parameter is set to **true** in the policy setting for those users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="217dc-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="217dc-149">Related topics</span></span>
- [<span data-ttu-id="217dc-150">Aperçu de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="217dc-150">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)