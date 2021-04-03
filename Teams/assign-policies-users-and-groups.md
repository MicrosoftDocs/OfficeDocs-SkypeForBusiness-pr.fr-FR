---
title: Attribuer des stratégies aux utilisateurs et aux groupes
author: KarliStites
ms.author: kastites
ms.reviewer: tomkau, saragava, ritikag, jastark
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez les différentes façons d’attribuer des stratégies aux utilisateurs et aux groupes dans Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 6b0db8c3da93e561bf374b32d08750d705ded8a2
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574321"
---
# <a name="assign-policies-to-users-and-groups"></a><span data-ttu-id="d5607-103">Attribuer des stratégies aux utilisateurs et aux groupes</span><span class="sxs-lookup"><span data-stu-id="d5607-103">Assign policies to users and groups</span></span>

<span data-ttu-id="d5607-104">Cet article décrit les différentes manières d’affecter des stratégies aux utilisateurs et aux groupes dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d5607-104">This article reviews the different ways to assign policies to users and groups in Microsoft Teams.</span></span> <span data-ttu-id="d5607-105">Avant de lire, assurez-vous de lire Attribuer [des stratégies dans Teams.](policy-assignment-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d5607-105">Before reading, be sure you've read [Assign policies in Teams - getting started](policy-assignment-overview.md).</span></span>

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="d5607-106">Attribuer une stratégie à des utilisateurs individuels</span><span class="sxs-lookup"><span data-stu-id="d5607-106">Assign a policy to individual users</span></span>

<span data-ttu-id="d5607-107">Pour affecter une stratégie à un utilisateur individuel ou à un petit nombre d’utilisateurs à la fois, suivez ces étapes.</span><span class="sxs-lookup"><span data-stu-id="d5607-107">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="use-the-microsoft-teams-admin-center"></a><span data-ttu-id="d5607-108">Utiliser le Centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d5607-108">Use the Microsoft Teams admin center</span></span>

<span data-ttu-id="d5607-109">Pour affecter une stratégie à un utilisateur :</span><span class="sxs-lookup"><span data-stu-id="d5607-109">To assign a policy to a user:</span></span>

1. <span data-ttu-id="d5607-110">Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, sélectionnez Utilisateurs, puis l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d5607-110">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="d5607-111">Sélectionnez l’utilisateur en cliquant à gauche du nom d’utilisateur, puis **sélectionnez Modifier les paramètres.**</span><span class="sxs-lookup"><span data-stu-id="d5607-111">Select the user by clicking to the left of the user name, and then select **Edit settings**.</span></span>
3. <span data-ttu-id="d5607-112">Sélectionnez la stratégie que vous voulez attribuer, puis sélectionnez **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="d5607-112">Select the policy you want to assign, and then select **Apply**.</span></span>

![Attribuer une stratégie à un utilisateur dans le Centre d’administration Teams](media/assign-policy-user.png)

<span data-ttu-id="d5607-114">Vous pouvez également :</span><span class="sxs-lookup"><span data-stu-id="d5607-114">Or, you can also do the following:</span></span>

1. <span data-ttu-id="d5607-115">Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, allez sur la page stratégie.</span><span class="sxs-lookup"><span data-stu-id="d5607-115">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="d5607-116">Sélectionnez la stratégie que vous voulez attribuer en cliquant à gauche du nom de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="d5607-116">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="d5607-117">Sélectionnez **Gérer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="d5607-117">Select **Manage users**.</span></span>
4. <span data-ttu-id="d5607-118">Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="d5607-118">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="d5607-119">Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="d5607-119">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="d5607-120">Lorsque vous avez terminé d’ajouter des utilisateurs, sélectionnez **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="d5607-120">When you're finished adding users, select **Apply**.</span></span>

![Attribuer une stratégie à un utilisateur dans le Centre d’administration Teams via une deuxième méthode](media/assign-policy-user2.png)

### <a name="use-powershell"></a><span data-ttu-id="d5607-122">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="d5607-122">Use PowerShell</span></span>

<span data-ttu-id="d5607-123">Chaque type de stratégie dispose de son propre ensemble d’lets de cmdlets pour le gérer.</span><span class="sxs-lookup"><span data-stu-id="d5607-123">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="d5607-124">Utilisez ```Grant-``` l’cmdlet pour un type de stratégie donné pour affecter la stratégie.</span><span class="sxs-lookup"><span data-stu-id="d5607-124">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="d5607-125">Par exemple, utilisez ```Grant-CsTeamsMeetingPolicy``` l’cmdlet pour affecter une stratégie de réunion Teams aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d5607-125">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="d5607-126">Ces cmdlets sont incluses dans le module Teams PowerShell et sont documentées dans la référence de [l’cmdlet Skype Entreprise.](https://docs.microsoft.com/powershell/skype)</span><span class="sxs-lookup"><span data-stu-id="d5607-126">These cmdlets are included in the Teams PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype).</span></span>

 <span data-ttu-id="d5607-127">Téléchargez et installez la version [publique Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) (si vous ne l’avez pas déjà fait), puis exécutez l’application suivante pour vous connecter.</span><span class="sxs-lookup"><span data-stu-id="d5607-127">Download and install the [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) (if you haven't already), and then run the following to connect.</span></span>

> [!NOTE]
> <span data-ttu-id="d5607-128">Skype Entreprise Online Connector fait actuellement partie du dernier module PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="d5607-128">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="d5607-129">Si vous utilisez la dernière version publique [de Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)vous n’avez pas besoin d’installer Skype Entreprise Online Connector.</span><span class="sxs-lookup"><span data-stu-id="d5607-129">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="d5607-130">Dans cet exemple, nous affectons une stratégie de réunion Teams nommée Stratégie de réunion étudiant à un utilisateur nommé Reda.</span><span class="sxs-lookup"><span data-stu-id="d5607-130">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="d5607-131">Pour en savoir plus, [lisez Gérer les stratégies via PowerShell.](teams-powershell-managing-teams.md#manage-policies-via-powershell)</span><span class="sxs-lookup"><span data-stu-id="d5607-131">To learn more, read [Manage policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="d5607-132">Affecter une stratégie à un groupe</span><span class="sxs-lookup"><span data-stu-id="d5607-132">Assign a policy to a group</span></span>

<span data-ttu-id="d5607-133">L’affectation de stratégies à des groupes vous permet d’affecter une stratégie à un groupe d’utilisateurs, tel qu’un groupe de sécurité ou une liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="d5607-133">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="d5607-134">L’affectations de stratégie est propagée aux membres du groupe en fonction de règles de priorité.</span><span class="sxs-lookup"><span data-stu-id="d5607-134">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="d5607-135">Lorsque les membres sont ajoutés à un groupe ou supprimés de ceux-ci, leurs affectations de stratégie héritées sont mises à jour en conséquence.</span><span class="sxs-lookup"><span data-stu-id="d5607-135">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="d5607-136">L’affectation de stratégies à des groupes est recommandée pour les groupes de jusqu’à 50 000 utilisateurs, mais elle fonctionne également avec des groupes plus importants.</span><span class="sxs-lookup"><span data-stu-id="d5607-136">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="d5607-137">Lorsque vous attribuez la stratégie, elle est immédiatement affectée au groupe.</span><span class="sxs-lookup"><span data-stu-id="d5607-137">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="d5607-138">Toutefois, la propagation de l’affectation de stratégie aux membres du groupe est effectuée comme une opération en arrière-plan et peut prendre du temps, selon la taille du groupe.</span><span class="sxs-lookup"><span data-stu-id="d5607-138">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="d5607-139">Il en va de même lorsqu’une stratégie est non signée dans un groupe, ou lorsque des membres sont ajoutés ou supprimés d’un groupe.</span><span class="sxs-lookup"><span data-stu-id="d5607-139">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

<span data-ttu-id="d5607-140">Les affectations de stratégie de groupe sont propagées uniquement aux utilisateurs qui sont des membres directs du groupe.</span><span class="sxs-lookup"><span data-stu-id="d5607-140">Group policy assignments are only propagated to users who are direct members of the group.</span></span> <span data-ttu-id="d5607-141">Les affectations ne sont pas propagées aux membres de groupes imbrmbrés.</span><span class="sxs-lookup"><span data-stu-id="d5607-141">The assignments aren't propagated to members of nested groups.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="d5607-142">Ce que vous devez savoir sur l’affectation d’une stratégie à des groupes</span><span class="sxs-lookup"><span data-stu-id="d5607-142">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="d5607-143">Avant de commencer, il est important de comprendre les règles de priorité et le classement par affectation de groupe.</span><span class="sxs-lookup"><span data-stu-id="d5607-143">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="d5607-144">Règles de priorité</span><span class="sxs-lookup"><span data-stu-id="d5607-144">Precedence rules</span></span>

<span data-ttu-id="d5607-145">Pour un type de stratégie donné, la stratégie efficace d’un utilisateur est déterminée selon les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="d5607-145">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="d5607-146">Une stratégie assignée directement à un utilisateur est prioritaire sur toute autre stratégie du même type que celle affectée à un groupe.</span><span class="sxs-lookup"><span data-stu-id="d5607-146">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="d5607-147">En d’autres termes, si un utilisateur est directement affecté à une stratégie d’un type donné, cet utilisateur n’hérite pas d’une stratégie du même type à partir d’un groupe.</span><span class="sxs-lookup"><span data-stu-id="d5607-147">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="d5607-148">Cela signifie également que si un utilisateur a une stratégie d’un type donné qui lui a été directement attribuée, vous devez supprimer cette stratégie de l’utilisateur pour qu’il puisse hériter d’une stratégie du même type à partir d’un groupe.</span><span class="sxs-lookup"><span data-stu-id="d5607-148">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="d5607-149">Si un utilisateur ne dispose pas directement d’une stratégie et est membre de deux groupes ou plus et que chaque groupe a une stratégie du même type qui lui est attribuée, l’utilisateur hérite de la stratégie de l’affectation de groupe qui présente le classement le plus élevé.</span><span class="sxs-lookup"><span data-stu-id="d5607-149">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="d5607-150">Si un utilisateur n’est membre d’aucun groupe pour qui une stratégie est attribuée, la stratégie globale (à l’échelle de l’organisation) pour ce type de stratégie s’applique à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d5607-150">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="d5607-151">La stratégie efficace d’un utilisateur est mise à jour en fonction des règles ci-après :</span><span class="sxs-lookup"><span data-stu-id="d5607-151">A user's effective policy is updated according to these rules:</span></span>

- <span data-ttu-id="d5607-152">lorsqu’un utilisateur est ajouté ou supprimé d’un groupe pour qui une stratégie est assignée.</span><span class="sxs-lookup"><span data-stu-id="d5607-152">when a user is added to or removed from a group that's assigned a policy.</span></span>
- <span data-ttu-id="d5607-153">une stratégie n’est pas signée à partir d’un groupe.</span><span class="sxs-lookup"><span data-stu-id="d5607-153">a policy is unassigned from a group.</span></span>
- <span data-ttu-id="d5607-154">une stratégie directement attribuée à l’utilisateur est supprimée.</span><span class="sxs-lookup"><span data-stu-id="d5607-154">a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="d5607-155">Classement des affectations de groupe</span><span class="sxs-lookup"><span data-stu-id="d5607-155">Group assignment ranking</span></span>

<span data-ttu-id="d5607-156">Lorsque vous attribuez une stratégie à un groupe, vous spécifiez un classement pour l’affectation du groupe.</span><span class="sxs-lookup"><span data-stu-id="d5607-156">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="d5607-157">Permet de déterminer la stratégie qu’un utilisateur doit hériter de sa stratégie efficace si l’utilisateur est membre de deux groupes ou plus et qu’une stratégie du même type est assignée à chaque groupe.</span><span class="sxs-lookup"><span data-stu-id="d5607-157">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="d5607-158">Le classement d’affectation de groupe est relatif aux autres affectations de groupe du même type.</span><span class="sxs-lookup"><span data-stu-id="d5607-158">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="d5607-159">Par exemple, si vous affectez une stratégie d’appel à deux groupes, définissez le classement d’une affectation sur 1 et l’autre sur 2, 1 étant le plus élevé.</span><span class="sxs-lookup"><span data-stu-id="d5607-159">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="d5607-160">Le classement d’affectation de groupe indique quelle appartenance au groupe est plus importante ou plus pertinente que d’autres appartenances de groupe en ce qui concerne l’héritage.</span><span class="sxs-lookup"><span data-stu-id="d5607-160">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>

<span data-ttu-id="d5607-161">Par exemple, vous avez deux groupes, Employés du Store et Responsables de magasin.</span><span class="sxs-lookup"><span data-stu-id="d5607-161">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="d5607-162">Les deux groupes ont respectivement une stratégie d’appel Teams, une stratégie d’appel des employés du Store et une stratégie d’appel pour les responsables du Magasin.</span><span class="sxs-lookup"><span data-stu-id="d5607-162">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="d5607-163">Pour un responsable de magasin faisant partie des deux groupes, son rôle de responsable est plus pertinent que son rôle d’employé. Par ailleurs, la stratégie d’appel attribuée au groupe Responsables de magasin doit avoir un classement plus élevé.</span><span class="sxs-lookup"><span data-stu-id="d5607-163">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="d5607-164">Grouper</span><span class="sxs-lookup"><span data-stu-id="d5607-164">Group</span></span> |<span data-ttu-id="d5607-165">Nom de la stratégie d’appel Teams</span><span class="sxs-lookup"><span data-stu-id="d5607-165">Teams calling policy name</span></span>  |<span data-ttu-id="d5607-166">Classement</span><span class="sxs-lookup"><span data-stu-id="d5607-166">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="d5607-167">Responsables de magasin</span><span class="sxs-lookup"><span data-stu-id="d5607-167">Store Managers</span></span>   |<span data-ttu-id="d5607-168">Stratégie d’appel des responsables de magasin</span><span class="sxs-lookup"><span data-stu-id="d5607-168">Store Managers Calling Policy</span></span>         |<span data-ttu-id="d5607-169">1</span><span class="sxs-lookup"><span data-stu-id="d5607-169">1</span></span>|
|<span data-ttu-id="d5607-170">Employés du Store</span><span class="sxs-lookup"><span data-stu-id="d5607-170">Store Employees</span></span>    |<span data-ttu-id="d5607-171">Stratégie d’appel du Store Employees</span><span class="sxs-lookup"><span data-stu-id="d5607-171">Store Employees Calling Policy</span></span>      |<span data-ttu-id="d5607-172">2</span><span class="sxs-lookup"><span data-stu-id="d5607-172">2</span></span>|

<span data-ttu-id="d5607-173">Si vous ne spécifiez pas de classement, l’affectation de stratégie se voir attribué le classement le plus faible.</span><span class="sxs-lookup"><span data-stu-id="d5607-173">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="in-the-teams-admin-center"></a><span data-ttu-id="d5607-174">Dans le Centre d’administration Teams</span><span class="sxs-lookup"><span data-stu-id="d5607-174">In the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="d5607-175">Pour l’instant, l’affectation de stratégies à des groupes utilisant le Centre d’administration Microsoft Teams est disponible uniquement pour la stratégie d’appel de Teams, la stratégie de parc d’appels Teams, la stratégie Teams, la stratégie d’événements en direct Teams, la stratégie de réunion Teams et la stratégie de messagerie Teams.</span><span class="sxs-lookup"><span data-stu-id="d5607-175">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="d5607-176">Pour d’autres types de stratégie, utilisez PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5607-176">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="d5607-177">Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, allez sur la page du type de stratégie.</span><span class="sxs-lookup"><span data-stu-id="d5607-177">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="d5607-178">Par exemple, allez à **Stratégies de**  >  **réunion.**</span><span class="sxs-lookup"><span data-stu-id="d5607-178">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="d5607-179">Sélectionnez **l’onglet Affectation de stratégie de** groupe.</span><span class="sxs-lookup"><span data-stu-id="d5607-179">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="d5607-180">Sélectionnez **Ajouter un** groupe, puis dans le volet **Affecter** une stratégie à un groupe, comme suit :</span><span class="sxs-lookup"><span data-stu-id="d5607-180">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="d5607-181">Recherchez et ajoutez le groupe à qui vous voulez affecter la stratégie.</span><span class="sxs-lookup"><span data-stu-id="d5607-181">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="d5607-182">Définissez le classement pour l’affectation de groupe.</span><span class="sxs-lookup"><span data-stu-id="d5607-182">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="d5607-183">Sélectionnez la stratégie à affecter.</span><span class="sxs-lookup"><span data-stu-id="d5607-183">Select the policy that you want to assign.</span></span>
    4. <span data-ttu-id="d5607-184">Sélectionnez **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="d5607-184">Select **Apply**.</span></span>
    
![Affecter une stratégie à un groupe dans le Centre d’administration Teams](media/assign-policy-group.png)

<span data-ttu-id="d5607-186">Pour supprimer une affectation de  stratégie de groupe, dans l’onglet Affectation de stratégie de groupe de la page stratégie, sélectionnez l’affectation de groupe, puis sélectionnez **Supprimer.**</span><span class="sxs-lookup"><span data-stu-id="d5607-186">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="d5607-187">Pour modifier le classement d’une affectation de groupe, vous devez d’abord supprimer l’affectation de stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="d5607-187">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="d5607-188">Suivez ensuite les étapes ci-dessus pour affecter la stratégie à un groupe.</span><span class="sxs-lookup"><span data-stu-id="d5607-188">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="use-the-powershell-option"></a><span data-ttu-id="d5607-189">Utiliser l’option PowerShell</span><span class="sxs-lookup"><span data-stu-id="d5607-189">Use the PowerShell option</span></span>

> [!NOTE]
> <span data-ttu-id="d5607-190">Actuellement, l’affectation de stratégies à des groupes à l’aide de PowerShell n’est pas disponible pour tous les types de stratégie Teams.</span><span class="sxs-lookup"><span data-stu-id="d5607-190">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="d5607-191">Pour obtenir la liste des types de stratégies pris en charge, voir [New-CsGroupPolicyAssignment.](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)</span><span class="sxs-lookup"><span data-stu-id="d5607-191">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="d5607-192">Installer et se connecter au module Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="d5607-192">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="d5607-193">Pour obtenir une aide étape par étape, voir [Installer Teams PowerShell.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="d5607-193">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group-of-users"></a><span data-ttu-id="d5607-194">Affecter une stratégie à un groupe d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="d5607-194">Assign a policy to a group of users</span></span>

<span data-ttu-id="d5607-195">Utilisez [l’cmdlet New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) pour affecter une stratégie à un groupe.</span><span class="sxs-lookup"><span data-stu-id="d5607-195">Use the [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="d5607-196">Vous pouvez spécifier un groupe à l’aide de l’ID d’objet, de l’adresse SIP ou de l’adresse de messagerie.</span><span class="sxs-lookup"><span data-stu-id="d5607-196">You can specify a group by using the object ID, SIP address, or email address.</span></span>

<span data-ttu-id="d5607-197">Dans cet exemple, nous affectons une stratégie de réunion Teams nommée Stratégie de réunion des responsables de vente au détail à un groupe avec un classement d’affectations de 1.</span><span class="sxs-lookup"><span data-stu-id="d5607-197">In this example, we assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="d5607-198">Obtenir des affectations de stratégie pour un groupe</span><span class="sxs-lookup"><span data-stu-id="d5607-198">Get policy assignments for a group</span></span>

<span data-ttu-id="d5607-199">Utilisez [l’cmdlet Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) pour attribuer toutes les stratégies à un groupe.</span><span class="sxs-lookup"><span data-stu-id="d5607-199">Use the [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="d5607-200">Notez que les groupes sont toujours répertoriés par leur ID de groupe, même si leur adresse SIP ou adresse de messagerie a été utilisée pour affecter la stratégie.</span><span class="sxs-lookup"><span data-stu-id="d5607-200">Note that groups are always listed by their group ID even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="d5607-201">Dans cet exemple, nous récupérons toutes les stratégies affectées à un groupe spécifique.</span><span class="sxs-lookup"><span data-stu-id="d5607-201">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="d5607-202">Dans cet exemple, nous renvoyons tous les groupes pour qui une stratégie de réunion Teams est attribuée.</span><span class="sxs-lookup"><span data-stu-id="d5607-202">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="d5607-203">Supprimer une stratégie d’un groupe</span><span class="sxs-lookup"><span data-stu-id="d5607-203">Remove a policy from a group</span></span>

<span data-ttu-id="d5607-204">Utilisez [l’cmdlet Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) pour supprimer une stratégie d’un groupe.</span><span class="sxs-lookup"><span data-stu-id="d5607-204">Use the [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="d5607-205">Lorsque vous supprimez une stratégie d’un groupe, les priorités des autres stratégies du même type attribuées à ce groupe (avec un classement inférieur) sont mises à jour.</span><span class="sxs-lookup"><span data-stu-id="d5607-205">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group, and that have a lower ranking, are updated.</span></span> <span data-ttu-id="d5607-206">Par exemple, si vous supprimez une stratégie qui présente un classement de 2, les stratégies dont le classement est 3 et 4 sont mises à jour pour refléter leur nouveau classement.</span><span class="sxs-lookup"><span data-stu-id="d5607-206">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="d5607-207">Les deux tableaux suivants illustrent cet exemple.</span><span class="sxs-lookup"><span data-stu-id="d5607-207">The following two tables show this example.</span></span>

<span data-ttu-id="d5607-208">Voici une liste des affectations de stratégie et des priorités pour une stratégie de réunion Teams.</span><span class="sxs-lookup"><span data-stu-id="d5607-208">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="d5607-209">Nom du groupe</span><span class="sxs-lookup"><span data-stu-id="d5607-209">Group name</span></span>  |<span data-ttu-id="d5607-210">Nom de la stratégie</span><span class="sxs-lookup"><span data-stu-id="d5607-210">Policy name</span></span>  |<span data-ttu-id="d5607-211">Classement</span><span class="sxs-lookup"><span data-stu-id="d5607-211">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="d5607-212">Ventes</span><span class="sxs-lookup"><span data-stu-id="d5607-212">Sales</span></span>    |<span data-ttu-id="d5607-213">Politique commerciale</span><span class="sxs-lookup"><span data-stu-id="d5607-213">Sales policy</span></span>       | <span data-ttu-id="d5607-214">1</span><span class="sxs-lookup"><span data-stu-id="d5607-214">1</span></span>        |
|<span data-ttu-id="d5607-215">Région Ouest</span><span class="sxs-lookup"><span data-stu-id="d5607-215">West Region</span></span>     |<span data-ttu-id="d5607-216">Politique de la région Ouest</span><span class="sxs-lookup"><span data-stu-id="d5607-216">West Region policy</span></span>         |<span data-ttu-id="d5607-217">2</span><span class="sxs-lookup"><span data-stu-id="d5607-217">2</span></span>         |
|<span data-ttu-id="d5607-218">Division</span><span class="sxs-lookup"><span data-stu-id="d5607-218">Division</span></span>    |<span data-ttu-id="d5607-219">Stratégie de division</span><span class="sxs-lookup"><span data-stu-id="d5607-219">Division policy</span></span>         |<span data-ttu-id="d5607-220">3</span><span class="sxs-lookup"><span data-stu-id="d5607-220">3</span></span>         |
|<span data-ttu-id="d5607-221">Filiale</span><span class="sxs-lookup"><span data-stu-id="d5607-221">Subsidiary</span></span>   |<span data-ttu-id="d5607-222">Stratégie de filiale</span><span class="sxs-lookup"><span data-stu-id="d5607-222">Subsidiary policy</span></span>        |<span data-ttu-id="d5607-223">4</span><span class="sxs-lookup"><span data-stu-id="d5607-223">4</span></span>         |

<span data-ttu-id="d5607-224">Si nous ôtons la stratégie de la région Ouest du groupe Région Ouest, les affectations de stratégie et les priorités sont mises à jour comme suit.</span><span class="sxs-lookup"><span data-stu-id="d5607-224">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="d5607-225">Nom du groupe</span><span class="sxs-lookup"><span data-stu-id="d5607-225">Group name</span></span>  |<span data-ttu-id="d5607-226">Nom de la stratégie</span><span class="sxs-lookup"><span data-stu-id="d5607-226">Policy name</span></span>  |<span data-ttu-id="d5607-227">Classement</span><span class="sxs-lookup"><span data-stu-id="d5607-227">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="d5607-228">Ventes</span><span class="sxs-lookup"><span data-stu-id="d5607-228">Sales</span></span>    |<span data-ttu-id="d5607-229">Politique commerciale</span><span class="sxs-lookup"><span data-stu-id="d5607-229">Sales policy</span></span>       | <span data-ttu-id="d5607-230">1</span><span class="sxs-lookup"><span data-stu-id="d5607-230">1</span></span>        |
|<span data-ttu-id="d5607-231">Division</span><span class="sxs-lookup"><span data-stu-id="d5607-231">Division</span></span>    |<span data-ttu-id="d5607-232">Stratégie de division</span><span class="sxs-lookup"><span data-stu-id="d5607-232">Division policy</span></span>         |<span data-ttu-id="d5607-233">2</span><span class="sxs-lookup"><span data-stu-id="d5607-233">2</span></span>         |
|<span data-ttu-id="d5607-234">Filiale</span><span class="sxs-lookup"><span data-stu-id="d5607-234">Subsidiary</span></span>   |<span data-ttu-id="d5607-235">Stratégie de filiale</span><span class="sxs-lookup"><span data-stu-id="d5607-235">Subsidiary policy</span></span>        |<span data-ttu-id="d5607-236">3</span><span class="sxs-lookup"><span data-stu-id="d5607-236">3</span></span>        |

<span data-ttu-id="d5607-237">Dans cet exemple, nous allons supprimer la stratégie de réunion Teams d’un groupe.</span><span class="sxs-lookup"><span data-stu-id="d5607-237">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="d5607-238">Modifier une affectation de stratégie pour un groupe</span><span class="sxs-lookup"><span data-stu-id="d5607-238">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="d5607-239">[L’cmdlet Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) sera bientôt disponible.</span><span class="sxs-lookup"><span data-stu-id="d5607-239">The [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet will be available soon.</span></span> <span data-ttu-id="d5607-240">En attendant, pour modifier une affectation de stratégie de groupe, vous pouvez supprimer l’affectation de stratégie actuelle du groupe, puis ajouter une nouvelle affectation de stratégie.</span><span class="sxs-lookup"><span data-stu-id="d5607-240">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="d5607-241">Après avoir attribué une stratégie à un groupe, vous pouvez utiliser l’cmdlet [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) pour modifier l’affectation de stratégie de ce groupe comme suit :</span><span class="sxs-lookup"><span data-stu-id="d5607-241">After you assign a policy to a group, you can use the [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="d5607-242">Modifier le classement</span><span class="sxs-lookup"><span data-stu-id="d5607-242">Change the ranking</span></span>
- <span data-ttu-id="d5607-243">Modifier la stratégie d’un type de stratégie donné</span><span class="sxs-lookup"><span data-stu-id="d5607-243">Change the policy of a given policy type</span></span>
- <span data-ttu-id="d5607-244">Modifier la stratégie d’un type de stratégie donné et le classement</span><span class="sxs-lookup"><span data-stu-id="d5607-244">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="d5607-245">Dans cet exemple, nous avons changé la stratégie de parc d’appels Teams d’un groupe en une stratégie nommée SupportCallPark et le classement par affectation à 3.</span><span class="sxs-lookup"><span data-stu-id="d5607-245">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="d5607-246">Modifier la stratégie efficace d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="d5607-246">Change the effective policy for a user</span></span>

<span data-ttu-id="d5607-247">Voici un exemple de la façon de modifier la stratégie efficace pour un utilisateur à qui une stratégie est directement attribuée.</span><span class="sxs-lookup"><span data-stu-id="d5607-247">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="d5607-248">Tout d’abord, nous utilisons l’let [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) avec le paramètre pour obtenir les détails des stratégies de diffusion de réunion Teams associées à ```PolicySource``` l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d5607-248">First, we use the [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="d5607-249">La sortie indique que l’utilisateur a été directement affecté à une stratégie de diffusion de réunion Teams nommée Événements d’employés, qui prend le pas sur la stratégie Événements en direct du fournisseur appartenant à un groupe auquel l’utilisateur appartient.</span><span class="sxs-lookup"><span data-stu-id="d5607-249">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="d5607-250">À présent, nous ôtons la stratégie Événements d’employés de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d5607-250">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="d5607-251">Cela signifie que l’utilisateur ne dispose plus directement d’une stratégie de diffusion de réunion Teams et hérite de la stratégie Événements en direct du fournisseur qui est attribuée au groupe dont il appartient.</span><span class="sxs-lookup"><span data-stu-id="d5607-251">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span>

<span data-ttu-id="d5607-252">Pour ce faire, utilisez l’cmdlet suivant du module Skype Entreprise PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5607-252">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="d5607-253">Utilisez l’cmdlet suivante dans le module Teams PowerShell pour faire cela à l’échelle même si vous avez une affectation de stratégie de lot, où $users est une liste d’utilisateurs que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="d5607-253">Use following cmdlet in the Teams PowerShell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="d5607-254">Affecter une stratégie à un lot d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="d5607-254">Assign a policy to a batch of users</span></span>

### <a name="use-the-admin-center"></a><span data-ttu-id="d5607-255">Utiliser le Centre d’administration</span><span class="sxs-lookup"><span data-stu-id="d5607-255">Use the admin center</span></span>

<span data-ttu-id="d5607-256">Pour affecter une stratégie aux utilisateurs en bloc :</span><span class="sxs-lookup"><span data-stu-id="d5607-256">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="d5607-257">Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, sélectionnez **Utilisateurs.**</span><span class="sxs-lookup"><span data-stu-id="d5607-257">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="d5607-258">Recherchez les utilisateurs à qui vous voulez affecter la stratégie ou filtrez l’affichage pour afficher les utilisateurs que vous souhaitez.</span><span class="sxs-lookup"><span data-stu-id="d5607-258">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="d5607-259">Dans la colonne **&#x2713;** (coche), sélectionnez les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d5607-259">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="d5607-260">Pour sélectionner tous les utilisateurs, cliquez sur &#x2713; (coche) en haut du tableau.</span><span class="sxs-lookup"><span data-stu-id="d5607-260">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="d5607-261">Sélectionnez **Modifier les paramètres,** a apporter les modifications de votre choix, puis **sélectionnez Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="d5607-261">Select **Edit settings**, make the changes that you want, and then select **Apply**.</span></span>

<span data-ttu-id="d5607-262">Pour afficher l’état de votre affectation de stratégie, dans la bannière  qui apparaît en haut de la **page** Utilisateurs après avoir sélectionné Appliquer pour envoyer votre affectation de stratégie, sélectionnez Journal **d’activité.**</span><span class="sxs-lookup"><span data-stu-id="d5607-262">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you select **Apply** to submit your policy assignment, select **Activity log**.</span></span> <span data-ttu-id="d5607-263">Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, sélectionnez Tableau de **bord,** puis sous Journal d’activité, sélectionnez Afficher les **détails.**</span><span class="sxs-lookup"><span data-stu-id="d5607-263">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, select **View details**.</span></span> <span data-ttu-id="d5607-264">Le journal d’activité affiche les affectations de stratégie à des lots de plus de 20 utilisateurs via le Centre d’administration Microsoft Teams au cours des 30 derniers jours.</span><span class="sxs-lookup"><span data-stu-id="d5607-264">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="d5607-265">Pour plus d’informations, [voir Afficher vos affectations de stratégie dans le journal d’activité.](activity-log.md)</span><span class="sxs-lookup"><span data-stu-id="d5607-265">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="use-powershell-method"></a><span data-ttu-id="d5607-266">Utiliser la méthode PowerShell</span><span class="sxs-lookup"><span data-stu-id="d5607-266">Use PowerShell method</span></span>

> [!NOTE]
> <span data-ttu-id="d5607-267">Actuellement, l’affectation de stratégie de lot à l’aide de PowerShell n’est pas disponible pour tous les types de stratégie Teams.</span><span class="sxs-lookup"><span data-stu-id="d5607-267">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="d5607-268">Pour obtenir la liste des types de stratégies pris en charge, voir [New-CsBatchPolicyAssignmentOperation.](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="d5607-268">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

<span data-ttu-id="d5607-269">L’affectation de stratégie de lot vous permet d’affecter une stratégie à de grands ensembles d’utilisateurs à la fois sans utiliser de script.</span><span class="sxs-lookup"><span data-stu-id="d5607-269">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="d5607-270">Vous utilisez la [cmdlet New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) pour envoyer un lot d’utilisateurs et la stratégie que vous voulez attribuer.</span><span class="sxs-lookup"><span data-stu-id="d5607-270">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="d5607-271">Les attributions sont traitées comme une opération d’arrière-plan et un ID d’opération est généré pour chaque lot.</span><span class="sxs-lookup"><span data-stu-id="d5607-271">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="d5607-272">Vous pouvez ensuite utiliser la cmdlet [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) pour suivre l’avancement et l’état des devoirs d’un lot.</span><span class="sxs-lookup"><span data-stu-id="d5607-272">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="d5607-273">Spécifiez les utilisateurs selon leur ID d’objet ou leur adresse SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="d5607-273">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="d5607-274">L’adresse SIP d’un utilisateur a souvent la même valeur que le nom d’utilisateur principal (UPN) ou l’adresse de courrier, mais cela n’est pas obligatoire.</span><span class="sxs-lookup"><span data-stu-id="d5607-274">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="d5607-275">Si un utilisateur est spécifié à l’aide de son nom d’utilisateur supérieur ou de son adresse de courrier, mais que sa valeur est différente de celle de son adresse SIP, l’attribution de stratégie échoue pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d5607-275">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="d5607-276">Si un lot inclut des utilisateurs en double, les doublons sont supprimés du lot avant que le traitement et l’état ne soient fournis qu’aux utilisateurs uniques restants du lot.</span><span class="sxs-lookup"><span data-stu-id="d5607-276">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="d5607-277">Un lot peut contenir jusqu’à 5 000 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d5607-277">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="d5607-278">Pour de meilleurs résultats, n’envoyez pas plus de quelques lots à la fois.</span><span class="sxs-lookup"><span data-stu-id="d5607-278">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="d5607-279">Autorisez le traitement des lots avant l’envoi d’autres lots.</span><span class="sxs-lookup"><span data-stu-id="d5607-279">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-teams-powershell-module"></a><span data-ttu-id="d5607-280">Installer et se connecter au module Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="d5607-280">Install and connect to the Teams PowerShell module</span></span>

<span data-ttu-id="d5607-281">Exécutez la commande suivante pour installer [le module Microsoft Teams PowerShell.](https://www.powershellgallery.com/packages/MicrosoftTeams)</span><span class="sxs-lookup"><span data-stu-id="d5607-281">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="d5607-282">Veillez à installer la version 1.0.5 ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="d5607-282">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="d5607-283">Exécutez ce qui suit pour vous connecter à Teams et démarrer une session.</span><span class="sxs-lookup"><span data-stu-id="d5607-283">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="d5607-284">Lorsque vous y êtes invité, connectez-vous à l’aide de vos informations d’identification d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="d5607-284">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="d5607-285">Installer et se connecter au module Azure AD PowerShell for Graph (facultatif)</span><span class="sxs-lookup"><span data-stu-id="d5607-285">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="d5607-286">Vous pouvez également télécharger et installer le [module Azure AD PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (si vous ne l’avez pas déjà fait) et vous connecter à Azure AD afin de récupérer la liste des utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d5607-286">You might also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="d5607-287">Exécutez ce qui suit pour vous connecter à Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d5607-287">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="d5607-288">Lorsque vous y êtes invité, connectez-vous à l’aide des mêmes informations d’identification d’administrateur que vous avez utilisées pour vous connecter à Teams.</span><span class="sxs-lookup"><span data-stu-id="d5607-288">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a><span data-ttu-id="d5607-289">Affecter une stratégie d’installation à un lot d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="d5607-289">Assign a setup policy to a batch of users</span></span>

<span data-ttu-id="d5607-290">Dans cet exemple, nous utilisons la cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) pour affecter une stratégie de configuration d’application nommée HR App Setup Policy à un lot d’utilisateurs répertoriés dans le fichier Users_ids.text.</span><span class="sxs-lookup"><span data-stu-id="d5607-290">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="d5607-291">Dans cet exemple, nous nous connectons à Azure AD pour récupérer un ensemble d’utilisateurs, puis affectons une stratégie de messagerie nommée Stratégie de messagerie nouvelle embauche à un lot d’utilisateurs spécifiés à l’aide de leur adresse SIP.</span><span class="sxs-lookup"><span data-stu-id="d5607-291">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="d5607-292">Obtenir l’état d’une affectation de lot</span><span class="sxs-lookup"><span data-stu-id="d5607-292">Get the status of a batch assignment</span></span>

<span data-ttu-id="d5607-293">Exécutez ce qui suit pour obtenir l’état d’une affectation de lot, où OperationId est l’ID d’opération renvoyé par ```New-CsBatchPolicyAssignmentOperation``` l’cmdlet pour un lot donné.</span><span class="sxs-lookup"><span data-stu-id="d5607-293">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="d5607-294">Si la sortie indique qu’une erreur s’est produite, exécutez l’erreur suivante pour obtenir plus d’informations sur les erreurs, qui se trouver dans la ```UserState``` propriété.</span><span class="sxs-lookup"><span data-stu-id="d5607-294">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="d5607-295">Pour en savoir plus, [consultez Get-CsBatchPolicyAssignmentOperation.](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="d5607-295">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d5607-296">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d5607-296">Related topics</span></span>

- [<span data-ttu-id="d5607-297">Gérer Teams avec des stratégies</span><span class="sxs-lookup"><span data-stu-id="d5607-297">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
- [<span data-ttu-id="d5607-298">Aperçu de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="d5607-298">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="d5607-299">Attribuer des stratégies dans Teams - Mise en place</span><span class="sxs-lookup"><span data-stu-id="d5607-299">Assign policies in Teams - getting started</span></span>](policy-assignment-overview.md)
