---
title: Gérer la découverte des équipes privées dans Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: shpoddar
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Apprenez à contrôler si les équipes privées peuvent être détectées par les utilisateurs de Microsoft teams par le biais de suggestions dans la Galerie d’équipe et les résultats de recherche.
ms.openlocfilehash: e06a9511d8198a069c3dccfdbbbacf3d3f1b2c42
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "46554694"
---
# <a name="manage-discovery-of-private-teams-in-microsoft-teams"></a><span data-ttu-id="03a5b-103">Gérer la découverte des équipes privées dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="03a5b-103">Manage discovery of private teams in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="03a5b-104">Sur la base des commentaires des clients, cette fonctionnalité est désactivée, en vigueur le 31 août 2020.</span><span class="sxs-lookup"><span data-stu-id="03a5b-104">Based on customer feedback, we're disabling this feature, effective August 31, 2020.</span></span> <span data-ttu-id="03a5b-105">En d’autres termes, après le 31 août 2020, vous ne serez plus en mesure de rendre détectable les équipes privées et toutes les nouvelles équipes privées et nouvelles ne seront plus détectables.</span><span class="sxs-lookup"><span data-stu-id="03a5b-105">This means that after August 31, 2020, you will no longer be able to set private teams to be discoverable and all existing and new private teams will no longer be discoverable.</span></span> <span data-ttu-id="03a5b-106">Pour en savoir plus, consultez la [documentation Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/roadmap?featureid=44370).</span><span class="sxs-lookup"><span data-stu-id="03a5b-106">To learn more, see the [Microsoft 365 Roadmap](https://www.microsoft.com/en-us/microsoft-365/roadmap?featureid=44370).</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="03a5b-107">Les administrateurs et les propriétaires d’équipe peuvent contrôler si des équipes privées peuvent être découvertes par les utilisateurs de Microsoft teams au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="03a5b-107">Admins and team owners can control whether private teams can be discovered by Microsoft Teams users in your organization.</span></span> <span data-ttu-id="03a5b-108">Lorsqu’une équipe privée est détectable, elle apparaît dans les résultats de la recherche et est incluse dans les suggestions de la Galerie d’équipes et dans les équipes publiques de teams.</span><span class="sxs-lookup"><span data-stu-id="03a5b-108">When a private team is discoverable, it shows up in search results and is included in suggestions in the team gallery alongside public teams in Teams.</span></span> <span data-ttu-id="03a5b-109">Cela permet aux utilisateurs de rechercher et d’accéder facilement aux équipes privées qu’ils souhaitent rejoindre.</span><span class="sxs-lookup"><span data-stu-id="03a5b-109">This makes it easy for users to search for and find the private teams that they want to join.</span></span> <span data-ttu-id="03a5b-110">Les utilisateurs peuvent demander à rejoindre une équipe privée, et le propriétaire d’une équipe peut ensuite approuver ou refuser la demande.</span><span class="sxs-lookup"><span data-stu-id="03a5b-110">Users can request to join a private team, and a team owner can then approve or deny the request.</span></span>

## <a name="overview-of-public-teams-private-teams-and-discovery-in-teams"></a><span data-ttu-id="03a5b-111">Vue d’ensemble des équipes publiques, des équipes privées et de la découverte dans teams</span><span class="sxs-lookup"><span data-stu-id="03a5b-111">Overview of public teams, private teams, and discovery in Teams</span></span>

<span data-ttu-id="03a5b-112">La plupart des organisations ont les types d’équipes suivants : équipes publiques, équipes privées détectable et équipes privées non détectablees.</span><span class="sxs-lookup"><span data-stu-id="03a5b-112">Most organizations have the following kinds of teams: public teams, discoverable private teams, and non-discoverable private teams.</span></span>

![Capture d’écran de la Galerie d’équipes](media/private-team-discovery-team-gallery.png)

### <a name="public-teams"></a><span data-ttu-id="03a5b-114">Équipes publiques</span><span class="sxs-lookup"><span data-stu-id="03a5b-114">Public teams</span></span>

<span data-ttu-id="03a5b-115">Les équipes publiques sont disponibles pour permettre à tous les utilisateurs de votre organisation de participer.</span><span class="sxs-lookup"><span data-stu-id="03a5b-115">Public teams are available for all users in your organization to join.</span></span> <span data-ttu-id="03a5b-116">Les équipes publiques sont visibles par tout le monde dans la Galerie d’équipes, et les utilisateurs peuvent rejoindre une équipe publique sans avoir besoin d’obtenir l’approbation du propriétaire de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="03a5b-116">Public teams are visible to everyone in the teams gallery, and users can join a public team without having to get approval from the team owner.</span></span> <span data-ttu-id="03a5b-117">Par exemple, les équipes publiques incluent une équipe pour discuter des nouvelles technologiques, une équipe pour obtenir des commentaires sur vos produits et une équipe pour les personnes carpooling de travailler.</span><span class="sxs-lookup"><span data-stu-id="03a5b-117">Examples of public teams include a team to discuss technology news, a team to get feedback for your products, and a team for people carpooling to work.</span></span>

### <a name="discoverable-private-teams"></a><span data-ttu-id="03a5b-118">Équipe privée détectable</span><span class="sxs-lookup"><span data-stu-id="03a5b-118">Discoverable private teams</span></span>

<span data-ttu-id="03a5b-119">Les équipes privées détectables ne peuvent être jointes que lorsque le propriétaire de l’équipe y ajoute des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="03a5b-119">Discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="03a5b-120">Lorsque vous rendez une équipe privée détectable, l’équipe est incluse dans la liste des équipes et des résultats de recherche suggérés dans la Galerie d’équipes.</span><span class="sxs-lookup"><span data-stu-id="03a5b-120">When you make a private team discoverable, the team is included in the list of suggested teams and search results in the teams gallery.</span></span> <span data-ttu-id="03a5b-121">Utilisez les équipes privées détectables pour les projets et groupes de votre organisation que tout le monde a pris en considération et où l’accès à des conversations et des fichiers dans l’équipe doit être contrôlé.</span><span class="sxs-lookup"><span data-stu-id="03a5b-121">Use discoverable private teams for projects and groups in your organization that everyone is aware of and where access to conversations and files in the team need to be controlled.</span></span> <span data-ttu-id="03a5b-122">Les exemples incluent une équipe pour votre service de ressources humaines, une équipe pour tous les responsables de votre organisation et une équipe pour un responsable et leurs rapports directs.</span><span class="sxs-lookup"><span data-stu-id="03a5b-122">Examples include a team for your HR department, a team for all managers in your organization, and a team for a manager and their direct reports.</span></span>

### <a name="non-discoverable-private-teams"></a><span data-ttu-id="03a5b-123">Équipes privées non détectable</span><span class="sxs-lookup"><span data-stu-id="03a5b-123">Non-discoverable private teams</span></span>

<span data-ttu-id="03a5b-124">Les équipes privées non détectablees ne peuvent être jointes que lorsque le propriétaire de l’équipe y ajoute des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="03a5b-124">Non-discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="03a5b-125">Lorsque vous rendez une équipe privée non détectable, celle-ci est masquée dans la liste des équipes suggérées et supprimées des résultats de recherche dans la Galerie d’équipes.</span><span class="sxs-lookup"><span data-stu-id="03a5b-125">When you make a private team not discoverable, it's hidden from the list of suggested teams and removed from search results in the teams gallery.</span></span> <span data-ttu-id="03a5b-126">Utilisez des équipes non détectable pour collaborer sur des sujets sensibles et hautement confidentiels.</span><span class="sxs-lookup"><span data-stu-id="03a5b-126">Use non-discoverable teams to collaborate on sensitive and highly confidential topics.</span></span> <span data-ttu-id="03a5b-127">Les exemples incluent une équipe pour discuter d’une prochaine acquisition et une équipe pour discuter d’une modification apportée à la direction stratégique de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="03a5b-127">Examples include a team to discuss an upcoming acquisition and a team to discuss a change in your organization's strategic direction.</span></span>

## <a name="set-whether-new-private-teams-are-discoverable"></a><span data-ttu-id="03a5b-128">Définir si de nouvelles équipes privées peuvent être découvertes</span><span class="sxs-lookup"><span data-stu-id="03a5b-128">Set whether new private teams are discoverable</span></span>

<span data-ttu-id="03a5b-129">Lorsque le propriétaire d’une équipe crée une équipe privée, il peut choisir de le rendre détectable en configurant le paramètre de découverte de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="03a5b-129">When a team owner creates a private team, they can choose to make it discoverable by configuring the team's discovery setting.</span></span> <span data-ttu-id="03a5b-130">Par défaut, les nouvelles équipes privées peuvent être recherchées et détectables.</span><span class="sxs-lookup"><span data-stu-id="03a5b-130">By default, new private teams are searchable and discoverable.</span></span> <span data-ttu-id="03a5b-131">Si le propriétaire de l’équipe ne souhaite pas qu’elle apparaisse dans les résultats de recherche et les suggestions, le propriétaire peut désactiver le paramètre en sélectionnant l' **option modifier les paramètres** en regard de **cette équipe peut effectuer une recherche ou une découverte**.</span><span class="sxs-lookup"><span data-stu-id="03a5b-131">If the team owner doesn't want the private team to show up in search results and suggestions, the owner can turn off the setting by selecting **Change setting** next to **This team is searchable and discoverable**.</span></span>

![Capture d’écran du paramètre de découverte pour les nouvelles équipes privées](media/private-team-discovery-new-team.png)

## <a name="set-whether-existing-private-teams-are-discoverable"></a><span data-ttu-id="03a5b-133">Définir si les équipes privées existantes sont détectables</span><span class="sxs-lookup"><span data-stu-id="03a5b-133">Set whether existing private teams are discoverable</span></span>

<span data-ttu-id="03a5b-134">Les propriétaires d’une équipe peuvent définir le paramètre de découverte pour une équipe privée existante directement dans les paramètres de l’équipe et les administrateurs peuvent le faire à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="03a5b-134">Team owners can set the discovery setting for an existing private team directly in the team settings and admins can do so by using PowerShell.</span></span>

### <a name="in-team-settings"></a><span data-ttu-id="03a5b-135">Dans les paramètres d’équipe</span><span class="sxs-lookup"><span data-stu-id="03a5b-135">In team settings</span></span>

<span data-ttu-id="03a5b-136">Dans Microsoft Teams, accédez à l’équipe privée, cliquez sur **plus d’options**  >  **gérer l’équipe**.</span><span class="sxs-lookup"><span data-stu-id="03a5b-136">In Teams, go to the private team, click **More options** > **Manage team**.</span></span> <span data-ttu-id="03a5b-137">Dans l’onglet **paramètres** , développez **découverte d’équipe**, puis cochez ou décochez la case Activer la **détectabilité** .</span><span class="sxs-lookup"><span data-stu-id="03a5b-137">On the **Settings** tab, expand **Team discovery**, and then clear or select the **Turn on discoverability** check box.</span></span>

![Capture d’écran du paramètre de découverte pour les équipes privées existantes](media/private-team-discovery-existing-team.png)

### <a name="using-powershell"></a><span data-ttu-id="03a5b-139">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="03a5b-139">Using PowerShell</span></span>

<span data-ttu-id="03a5b-140">Utilisez l’applet de connexion **[Set-Team](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps)** pour désactiver ou activer le paramètre de découverte pour une équipe privée existante.</span><span class="sxs-lookup"><span data-stu-id="03a5b-140">Use the **[Set-Team](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps)** cmdlet to turn off or turn on the discovery setting for an existing private team.</span></span> <span data-ttu-id="03a5b-141">Voici un exemple illustrant comment rendre une équipe plus détectable :</span><span class="sxs-lookup"><span data-stu-id="03a5b-141">Here's an example of how to make a team discoverable:</span></span>
```PowerShell
    Set-Team -GroupId 0abc123d-e4f5-67gh-i890-jk1m2n345o6p -ShowInTeamsSearchAndSuggestions $true
```
<span data-ttu-id="03a5b-142">Vous pouvez utiliser cette applet de cmdlet dans un script pour définir le paramètre de découverte des équipes privées existantes en bloc.</span><span class="sxs-lookup"><span data-stu-id="03a5b-142">You can use this cmdlet in a script to set the discovery setting of existing private teams in bulk.</span></span>

## <a name="set-whether-users-can-discover-private-teams"></a><span data-ttu-id="03a5b-143">Définir si les utilisateurs peuvent découvrir les équipes privées</span><span class="sxs-lookup"><span data-stu-id="03a5b-143">Set whether users can discover private teams</span></span>

<span data-ttu-id="03a5b-144">En tant qu’administrateur, vous pouvez également contrôler les utilisateurs de votre organisation qui sont autorisés à découvrir des équipes privées dans les résultats de recherche et les suggestions dans Teams.</span><span class="sxs-lookup"><span data-stu-id="03a5b-144">As an admin, you can also control which users in your organization are allowed to discover private teams in search results and suggestions in Teams.</span></span> <span data-ttu-id="03a5b-145">Créez une stratégie à l’aide de l’applet de **[nouvelle applet de nouveau-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)** , puis affectez la stratégie aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="03a5b-145">Create a policy by using the **[New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)** cmdlet, and then assign the policy to users.</span></span>
 
<span data-ttu-id="03a5b-146">Définissez le paramètre **AllowPrivateTeamDiscovery** sur **true** pour autoriser les utilisateurs auxquels une stratégie est affectée pour voir les équipes privées détectables dans les résultats de recherche et les suggestions.</span><span class="sxs-lookup"><span data-stu-id="03a5b-146">Set the **AllowPrivateTeamDiscovery** parameter to **true** to allow users who are assigned the policy to see discoverable private teams in search results and suggestions.</span></span> <span data-ttu-id="03a5b-147">Le fait de définir le paramètre **AllowPrivateTeamDiscovery** sur **false** entraîne la suppression de toutes les équipes privées détectable des résultats de la recherche et des suggestions pour les utilisateurs auxquels cette stratégie est affectée.</span><span class="sxs-lookup"><span data-stu-id="03a5b-147">Setting the **AllowPrivateTeamDiscovery** parameter to **false** removes all discoverable private teams from search results and suggestions for users who are assigned the policy.</span></span>

<span data-ttu-id="03a5b-148">Par défaut, **AllowPrivateTeamDiscovery** est défini sur **true** pour tous les utilisateurs au sein d’une organisation.</span><span class="sxs-lookup"><span data-stu-id="03a5b-148">By default, **AllowPrivateTeamDiscovery** is set to **true** for all users in an organization.</span></span>

<span data-ttu-id="03a5b-149">Dans cet exemple, nous créons une stratégie nommée VendorPolicy qui empêche les utilisateurs de découvrir toutes les équipes privées découvertes, puis nous affectons la stratégie à un utilisateur nommé vendoruser1.</span><span class="sxs-lookup"><span data-stu-id="03a5b-149">In this example, we create a policy named VendorPolicy that prevents users from discovering any private teams that are made discoverable, and then we assign the policy to a user named vendoruser1.</span></span>
```PowerShell
     New-CsTeamsChannelsPolicy -Identity VendorPolicy -AllowPrivateTeamDiscovery $false
     Grant-CsTeamsChannelsPolicy -Identity vendoruser1@company.com -PolicyName VendorPolicy
```

> [!NOTE]
> <span data-ttu-id="03a5b-150">Les équipes privées qui ne sont pas détectables ne sont jamais affichées dans les résultats de recherche et les suggestions, indépendamment du paramètre de stratégie.</span><span class="sxs-lookup"><span data-stu-id="03a5b-150">Private teams that are not discoverable are never shown in search results and suggestions, regardless of the policy setting.</span></span> <span data-ttu-id="03a5b-151">Par exemple, si vous désactivez le paramètre de découverte pour une équipe privée, les utilisateurs ne parviennent pas à découvrir l’équipe, même si le paramètre **AllowPrivateTeamDiscovery** est défini sur **true** dans le paramètre de stratégie pour ces utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="03a5b-151">For example, if you turn off the discovery setting for a private team, users are unable to discover the team, even though  the **AllowPrivateTeamDiscovery** parameter is set to **true** in the policy setting for those users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="03a5b-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="03a5b-152">Related topics</span></span>
- [<span data-ttu-id="03a5b-153">Aperçu de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="03a5b-153">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
