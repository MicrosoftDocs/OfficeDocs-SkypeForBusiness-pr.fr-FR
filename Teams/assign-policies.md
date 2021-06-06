---
title: Attribuer des stratégies à vos utilisateurs dans Microsoft Teams.
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: tomkau, saragava, ritikag, jastark
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
description: Découvrez les différentes façons d’attribuer des stratégies à vos utilisateurs dans Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 05ed811c38b3f49e21933d575c82128360ca3390
ms.sourcegitcommit: 3840d72f9ad1c0c7803dc3662a0318f558fe92ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739714"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="4a6c4-103">Attribuer des stratégies à vos utilisateurs dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-103">Assign policies to your users in Microsoft Teams</span></span>

<span data-ttu-id="4a6c4-104">En tant qu’administrateur, vous utilisez des stratégies pour contrôler Teams fonctionnalités disponibles pour les utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-104">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="4a6c4-105">Par exemple, il existe des stratégies d’appel, des stratégies de réunion et des stratégies de messagerie, entre autres.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-105">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="4a6c4-106">Les organisations ont différents types d’utilisateurs ayant des besoins uniques.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-106">Organizations have different types of users with unique needs.</span></span> <span data-ttu-id="4a6c4-107">Les stratégies personnalisées que vous créez et attribuez vous personnalisationnt aux différents ensembles d’utilisateurs en fonction de ces besoins.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-107">Custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="4a6c4-108">Pour gérer facilement les stratégies dans votre organisation, Teams plusieurs façons d’affecter des stratégies aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-108">To easily manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="4a6c4-109">Affectez une stratégie directement aux utilisateurs, individuellement ou à l’échelle via une affectation de lot, ou à un groupe dont les utilisateurs sont membres.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-109">Assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="4a6c4-110">Vous pouvez également utiliser des packages de stratégies pour affecter une collection prédéfinfine de stratégies aux utilisateurs de votre organisation ayant des rôles similaires.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-110">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="4a6c4-111">L’option que vous choisissez dépend du nombre de stratégies que vous gérez et du nombre d’utilisateurs à qui vous affectez des stratégies.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-111">The option that you choose depends on the number of policies that you're managing and the number of users you're assigning policies to.</span></span> <span data-ttu-id="4a6c4-112">Les stratégies globales (à l’échelle de l’organisation par défaut) s’appliquent au plus grand nombre d’utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-112">Global (Org-wide default) policies apply to the largest number of users in your organization.</span></span> <span data-ttu-id="4a6c4-113">Il vous s agit uniquement d’affecter des stratégies aux utilisateurs qui ont besoin de stratégies spécialisées.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-113">You only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="4a6c4-114">Cet article décrit les différentes manières d’affecter des stratégies aux utilisateurs et les scénarios recommandés pour l’utilisation des stratégies.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-114">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="4a6c4-115">Quelle stratégie prend le pas ?</span><span class="sxs-lookup"><span data-stu-id="4a6c4-115">Which policy takes precedence?</span></span>

<span data-ttu-id="4a6c4-116">Un utilisateur a une stratégie efficace pour chaque type de stratégie.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-116">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="4a6c4-117">Il est possible, voire probable, qu’une stratégie soit attribuée directement à un utilisateur et qu’il soit également membre d’un ou plusieurs groupes à qui une stratégie du même type a été attribuée.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-117">It's possible, or even likely, that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="4a6c4-118">Dans ces types de scénarios, quelle stratégie prend le pas ?</span><span class="sxs-lookup"><span data-stu-id="4a6c4-118">In these kinds of scenarios, which policy takes precedence?</span></span> <span data-ttu-id="4a6c4-119">La stratégie efficace d’un utilisateur est déterminée selon les règles de priorité, comme suit.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-119">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="4a6c4-120">Si un utilisateur est affecté directement à une stratégie (individuellement ou par le biais d’une affectation de lot), cette stratégie est prioritaire.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-120">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="4a6c4-121">Dans l’exemple visuel suivant, la stratégie efficace de l’utilisateur est la stratégie de réunion carrée qu’il est directement affecté à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-121">In the following visual example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![Diagramme montrant la priorité d’une stratégie assignée directement](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="4a6c4-123">Si un utilisateur n’est pas directement affecté à une stratégie d’un type donné, la stratégie assignée à un groupe dont l’utilisateur est membre est prioritaire.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-123">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="4a6c4-124">Si un utilisateur est membre de plusieurs groupes, [](#group-assignment-ranking) la stratégie ayant le classement d’affectation de groupe le plus élevé pour le type de stratégie donné est prioritaire.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-124">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="4a6c4-125">Dans cet exemple visuel, la stratégie efficace de l’utilisateur est la stratégie Exec Teams et HD, qui présente le classement d’affectation le plus élevé par rapport aux autres groupes dont l’utilisateur est membre et pour lesquels une stratégie du même type de stratégie est également attribuée.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-125">In this visual example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![Diagramme montrant comment une stratégie héritée d’un groupe est prioritaire](media/assign-policies-example-group.png)

<span data-ttu-id="4a6c4-127">Si un utilisateur n’est pas directement affecté à une stratégie ou n’est membre d’aucun groupe à qui une stratégie est attribuée, l’utilisateur reçoit la stratégie globale (à l’échelle de l’organisation par défaut) pour ce type de stratégie.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-127">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="4a6c4-128">Voici un exemple visuel.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-128">Here's a visual example.</span></span>

![Diagramme montrant la manière dont une stratégie globale prend le pas](media/assign-policies-example-global.png)

<span data-ttu-id="4a6c4-130">Pour en savoir plus, consultez [les règles de priorité.](#precedence-rules)</span><span class="sxs-lookup"><span data-stu-id="4a6c4-130">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="4a6c4-131">Méthodes d’affectation des stratégies</span><span class="sxs-lookup"><span data-stu-id="4a6c4-131">Ways to assign policies</span></span>

<span data-ttu-id="4a6c4-132">Voici une vue d’ensemble des manières d’affecter des stratégies aux utilisateurs et des scénarios recommandés pour chacun d’eux.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-132">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="4a6c4-133">Sélectionnez les liens pour en savoir plus.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-133">Select the links to learn more.</span></span>

<span data-ttu-id="4a6c4-134">Avant d’affecter des stratégies à des utilisateurs ou groupes individuels, commencez par définir les stratégies globales (à l’échelle de l’organisation [par défaut)](#set-the-global-policies) de sorte qu’elles s’appliquent au plus grand nombre d’utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-134">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="4a6c4-135">Une fois les stratégies globales définies, vous devrez seulement affecter des stratégies aux utilisateurs qui ont besoin de stratégies spécialisées.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-135">Once the global policies are set, you'll only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="4a6c4-136">Pour ce faire,</span><span class="sxs-lookup"><span data-stu-id="4a6c4-136">Do this</span></span>  |<span data-ttu-id="4a6c4-137">Si...</span><span class="sxs-lookup"><span data-stu-id="4a6c4-137">If...</span></span>  | <span data-ttu-id="4a6c4-138">Utilisation...</span><span class="sxs-lookup"><span data-stu-id="4a6c4-138">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="4a6c4-139">Attribuer une stratégie à des utilisateurs individuels</span><span class="sxs-lookup"><span data-stu-id="4a6c4-139">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="4a6c4-140">Vous débutez dans Teams vous débutez, ou vous n’avez besoin d’affecter qu’une ou plusieurs stratégies à un petit nombre d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-140">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="4a6c4-141">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span><span class="sxs-lookup"><span data-stu-id="4a6c4-141">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>
|[<span data-ttu-id="4a6c4-142">Affecter une stratégie à un groupe</span><span class="sxs-lookup"><span data-stu-id="4a6c4-142">Assign a policy to a group</span></span>](#assign-a-policy-to-a-group) |<span data-ttu-id="4a6c4-143">Attribuer des stratégies en fonction de l’appartenance d’un utilisateur à un groupe.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-143">Assign policies based on a user's group membership.</span></span> <span data-ttu-id="4a6c4-144">Par exemple, affectez une stratégie à tous les utilisateurs d’un groupe de sécurité ou d’une liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-144">For example, assign a policy to all users in a security group or distribution list.</span></span>| <span data-ttu-id="4a6c4-145">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span><span class="sxs-lookup"><span data-stu-id="4a6c4-145">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="4a6c4-146">Affecter une stratégie à un lot d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="4a6c4-146">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="4a6c4-147">Attribuer des stratégies à de grands ensembles d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-147">Assign policies to large sets of users.</span></span> <span data-ttu-id="4a6c4-148">Par exemple, affectez une stratégie à des centaines ou des milliers d’utilisateurs à la fois dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-148">For example, assign a policy to hundreds or thousands of users in your organization at a time.</span></span> |<span data-ttu-id="4a6c4-149">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span><span class="sxs-lookup"><span data-stu-id="4a6c4-149">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="4a6c4-150">Attribuer un package de stratégies aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="4a6c4-150">Assign a policy package to users</span></span>](#assign-a-policy-package-to-users)  |<span data-ttu-id="4a6c4-151">Attribuez plusieurs stratégies à des ensembles spécifiques d’utilisateurs de votre organisation qui ont des rôles identiques ou similaires.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-151">Assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="4a6c4-152">Par exemple, affectez le package de stratégie Éducation (Enseignant) aux enseignants de votre établissement scolaire pour leur donner un accès total aux conversations, appels et réunions.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-152">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings.</span></span> <span data-ttu-id="4a6c4-153">Affectez le package de stratégie Éducation (étudiant secondaire) aux étudiants secondaires afin de limiter certaines fonctionnalités telles que les appels privés.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-153">Assign the Education (Secondary school student) policy package to secondary students to limit certain capabilities such as private calling.</span></span>  |<span data-ttu-id="4a6c4-154">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span><span class="sxs-lookup"><span data-stu-id="4a6c4-154">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="4a6c4-155">[Affecter un package de stratégie à un groupe](#assign-a-policy-package-to-a-group) (en prévisualisation privée)</span><span class="sxs-lookup"><span data-stu-id="4a6c4-155">[Assign a policy package to a group](#assign-a-policy-package-to-a-group) (in private preview)</span></span>   |<span data-ttu-id="4a6c4-156">Attribuer plusieurs stratégies à un groupe d’utilisateurs de votre organisation qui ont des rôles identiques ou similaires.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-156">Assign multiple policies to a group of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="4a6c4-157">Par exemple, affectez un package de stratégie à tous les utilisateurs d’un groupe de sécurité ou d’une liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-157">For example, assign a policy package to all users in a security group or distribution list.</span></span> |<span data-ttu-id="4a6c4-158">Le Microsoft Teams d’administration powershell (bientôt disponible) ou les cmdlets PowerShell dans Teams module PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a6c4-158">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="4a6c4-159">Affecter un package de stratégie à un lot d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="4a6c4-159">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="4a6c4-160">Affectez plusieurs stratégies à un lot d’utilisateurs de votre organisation qui ont des rôles identiques ou similaires.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-160">Assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="4a6c4-161">Par exemple, affectez le package de stratégie Éducation (Enseignant) à tous les enseignants de votre établissement en utilisant un devoir de lot pour leur donner un accès total aux conversations, appels et réunions.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-161">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings.</span></span> <span data-ttu-id="4a6c4-162">Affectez le package de stratégie Éducation (étudiant secondaire) à un lot d’étudiants secondaires afin de limiter certaines fonctionnalités telles que les appels privés.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-162">Assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities such as private calling.</span></span>|<span data-ttu-id="4a6c4-163">Cmdlets PowerShell dans le module Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a6c4-163">PowerShell cmdlets in the Teams PowerShell module</span></span>|

## <a name="set-the-global-policies"></a><span data-ttu-id="4a6c4-164">Définir les stratégies globales</span><span class="sxs-lookup"><span data-stu-id="4a6c4-164">Set the global policies</span></span>

<span data-ttu-id="4a6c4-165">Pour définir les stratégies globales (à l’échelle de l’organisation par défaut) pour chaque type de stratégie, suivez ces étapes.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-165">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="4a6c4-166">Utiliser le centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4a6c4-166">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="4a6c4-167">Dans le navigation gauche du Microsoft Teams d’administration, allez sur la page stratégie pour le type de stratégie que vous voulez mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-167">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="4a6c4-168">Par exemple, vous **Teams** Teams, les stratégies réunions, les stratégies de messagerie  >  ou les   >  **stratégies**    >  **d’appel vocal.**</span><span class="sxs-lookup"><span data-stu-id="4a6c4-168">For example, **Teams** > **Teams policies**, **Meetings** > **Meetings policies**, **Messaging policies**, or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="4a6c4-169">Sélectionnez **la stratégie globale (à l’échelle de l’organisation par défaut)** pour afficher les paramètres actuels.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-169">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="4a6c4-170">Mettez à jour la stratégie si nécessaire, puis sélectionnez **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="4a6c4-170">Update the policy as needed, and then select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="4a6c4-171">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a6c4-171">Using PowerShell</span></span>

<span data-ttu-id="4a6c4-172">Pour définir les stratégies globales à l’aide de PowerShell, utilisez l’identificateur global.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-172">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="4a6c4-173">Commencez par examiner la stratégie globale actuelle pour déterminer le paramètre à modifier.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-173">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

```powershell
Get-CsTeamsMessagingPolicy -Identity Global
 
Identity                      : Global
Description                   :
AllowUrlPreviews              : True
AllowOwnerDeleteMessage       : False
AllowUserEditMessage          : True
AllowUserDeleteMessage        : True
AllowUserChat                 : True
AllowRemoveUser               : True
AllowGiphy                    : True
GiphyRatingType               : Moderate
AllowMemes                    : True
AllowImmersiveReader          : True
AllowStickers                 : True
AllowUserTranslation          : False
ReadReceiptsEnabledType       : UserPreference
AllowPriorityMessages         : True
ChannelsInChatListEnabledType : DisabledUserOverride
AudioMessageEnabledType       : ChatsAndChannels
Expand (20 lines) Collapse 
```

<span data-ttu-id="4a6c4-174">Ensuite, mettez à jour la stratégie globale selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-174">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="4a6c4-175">Il vous suffit de spécifier des valeurs pour les paramètres à modifier.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-175">You only need to specify values for the settings that you want to change.</span></span>

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="4a6c4-176">Attribuer une stratégie à des utilisateurs individuels</span><span class="sxs-lookup"><span data-stu-id="4a6c4-176">Assign a policy to individual users</span></span>

<span data-ttu-id="4a6c4-177">Pour affecter une stratégie à un utilisateur individuel ou à un petit nombre d’utilisateurs à la fois, suivez ces étapes.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-177">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="use-the-microsoft-teams-admin-center"></a><span data-ttu-id="4a6c4-178">Utiliser le Microsoft Teams d’administration</span><span class="sxs-lookup"><span data-stu-id="4a6c4-178">Use the Microsoft Teams admin center</span></span>

<span data-ttu-id="4a6c4-179">Pour affecter une stratégie à un utilisateur :</span><span class="sxs-lookup"><span data-stu-id="4a6c4-179">To assign a policy to a user:</span></span>

1. <span data-ttu-id="4a6c4-180">Dans le panneau de navigation gauche du Microsoft Teams d’administration, sélectionnez Utilisateurs, puis l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-180">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="4a6c4-181">Sélectionnez l’utilisateur en cliquant à gauche du nom d’utilisateur, puis **sélectionnez Modifier les paramètres.**</span><span class="sxs-lookup"><span data-stu-id="4a6c4-181">Select the user by clicking to the left of the user name, and then select **Edit settings**.</span></span>
3. <span data-ttu-id="4a6c4-182">Sélectionnez la stratégie que vous voulez attribuer, puis sélectionnez **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="4a6c4-182">Select the policy you want to assign, and then select **Apply**.</span></span>

<span data-ttu-id="4a6c4-183">Vous pouvez également :</span><span class="sxs-lookup"><span data-stu-id="4a6c4-183">Or, you can also do the following:</span></span>

1. <span data-ttu-id="4a6c4-184">Dans le panneau de navigation gauche du Microsoft Teams d’administration, allez sur la page stratégie.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-184">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="4a6c4-185">Sélectionnez la stratégie que vous voulez attribuer en cliquant à gauche du nom de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-185">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="4a6c4-186">Sélectionnez **Gérer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-186">Select **Manage users**.</span></span>
4. <span data-ttu-id="4a6c4-187">Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-187">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="4a6c4-188">Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-188">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="4a6c4-189">Lorsque vous avez terminé d’ajouter des utilisateurs, sélectionnez **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="4a6c4-189">When you're finished adding users, select **Apply**.</span></span>

### <a name="use-powershell"></a><span data-ttu-id="4a6c4-190">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a6c4-190">Use PowerShell</span></span>

<span data-ttu-id="4a6c4-191">Chaque type de stratégie dispose de son propre ensemble d’lets de cmdlets pour le gérer.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-191">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="4a6c4-192">Utilisez ```Grant-``` l’cmdlet pour un type de stratégie donné pour affecter la stratégie.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-192">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="4a6c4-193">Par exemple, utilisez l’cmdlet pour affecter une stratégie ```Grant-CsTeamsMeetingPolicy``` Teams réunion aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-193">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="4a6c4-194">Ces cmdlets sont incluses dans le module Teams PowerShell et sont documentées dans la référence [Skype Entreprise cmdlet.](/powershell/skype/intro?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="4a6c4-194">These cmdlets are included in the Teams PowerShell module and are documented in the [Skype for Business cmdlet reference](/powershell/skype/intro?view=skype-ps).</span></span>

<span data-ttu-id="4a6c4-195">Téléchargez et installez [la Teams publique PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) (si vous ne l’avez pas déjà fait), puis exécutez l’application suivante pour vous connecter.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-195">Download and install the [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) (if you haven't already), and then run the following to connect.</span></span>

> [!NOTE]
> <span data-ttu-id="4a6c4-196">Skype Entreprise Online Connector fait actuellement partie du dernier module PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-196">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="4a6c4-197">Si vous utilisez la dernière version [Teams public PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)vous n’avez pas besoin d’installer Skype Entreprise Online Connector.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-197">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
# When using Teams PowerShell Module

Import-Module MicrosoftTeams
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="4a6c4-198">Dans cet exemple, nous affectons une stratégie Teams réunion nommée Stratégie de réunion étudiant à un utilisateur nommé Reda.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-198">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="4a6c4-199">Pour en savoir plus, [lisez Gérer les stratégies via PowerShell.](teams-powershell-managing-teams.md#manage-policies-via-powershell)</span><span class="sxs-lookup"><span data-stu-id="4a6c4-199">To learn more, read [Manage policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="4a6c4-200">Affecter une stratégie à un groupe</span><span class="sxs-lookup"><span data-stu-id="4a6c4-200">Assign a policy to a group</span></span>

<span data-ttu-id="4a6c4-201">L’affectation de stratégies à des groupes vous permet d’affecter une stratégie à un groupe d’utilisateurs, tel qu’un groupe de sécurité ou une liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-201">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="4a6c4-202">L’affectations de stratégie est propagée aux membres du groupe en fonction de règles de priorité.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-202">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="4a6c4-203">Lorsque les membres sont ajoutés à un groupe ou supprimés de ceux-ci, leurs affectations de stratégie héritées sont mises à jour en conséquence.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-203">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="4a6c4-204">L’affectation de stratégies à des groupes est recommandée pour les groupes de jusqu’à 50 000 utilisateurs, mais elle fonctionne également avec des groupes plus importants.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-204">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="4a6c4-205">Lorsque vous attribuez la stratégie, elle est immédiatement affectée au groupe.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-205">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="4a6c4-206">Toutefois, la propagation de l’affectation de stratégie aux membres du groupe est effectuée comme une opération en arrière-plan et peut prendre du temps, selon la taille du groupe.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-206">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="4a6c4-207">Il en va de même lorsqu’une stratégie est non signée dans un groupe, ou lorsque des membres sont ajoutés ou supprimés d’un groupe.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-207">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

<span data-ttu-id="4a6c4-208">Les affectations de stratégie de groupe sont propagées uniquement aux utilisateurs qui sont des membres directs du groupe.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-208">Group policy assignments are only propagated to users who are direct members of the group.</span></span> <span data-ttu-id="4a6c4-209">Les affectations ne sont pas propagées aux membres de groupes imbrmbrés.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-209">The assignments aren't propagated to members of nested groups.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="4a6c4-210">Ce que vous devez savoir sur l’affectation d’une stratégie à des groupes</span><span class="sxs-lookup"><span data-stu-id="4a6c4-210">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="4a6c4-211">Avant de commencer, il est important de comprendre les règles de priorité et le classement par affectation de groupe.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-211">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="4a6c4-212">Règles de priorité</span><span class="sxs-lookup"><span data-stu-id="4a6c4-212">Precedence rules</span></span>

<span data-ttu-id="4a6c4-213">Pour un type de stratégie donné, la stratégie efficace d’un utilisateur est déterminée selon les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="4a6c4-213">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="4a6c4-214">Une stratégie assignée directement à un utilisateur est prioritaire sur toute autre stratégie du même type que celle affectée à un groupe.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-214">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="4a6c4-215">En d’autres termes, si un utilisateur est directement affecté à une stratégie d’un type donné, cet utilisateur n’hérite pas d’une stratégie du même type à partir d’un groupe.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-215">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="4a6c4-216">Cela signifie également que si un utilisateur a une stratégie d’un type donné qui lui a été directement attribuée, vous devez supprimer cette stratégie de l’utilisateur pour qu’il puisse hériter d’une stratégie du même type à partir d’un groupe.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-216">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>

- <span data-ttu-id="4a6c4-217">Si un utilisateur ne dispose pas directement d’une stratégie et est membre de deux groupes ou plus et que chaque groupe a une stratégie du même type qui lui est attribuée, l’utilisateur hérite de la stratégie de l’affectation de groupe qui présente le classement le plus élevé.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-217">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>

- <span data-ttu-id="4a6c4-218">Si un utilisateur n’est membre d’aucun groupe pour qui une stratégie est attribuée, la stratégie globale (à l’échelle de l’organisation) pour ce type de stratégie s’applique à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-218">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="4a6c4-219">La stratégie efficace d’un utilisateur est mise à jour en fonction des règles ci-après :</span><span class="sxs-lookup"><span data-stu-id="4a6c4-219">A user's effective policy is updated according to these rules:</span></span>

- <span data-ttu-id="4a6c4-220">lorsqu’un utilisateur est ajouté ou supprimé d’un groupe pour qui une stratégie est assignée.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-220">when a user is added to or removed from a group that's assigned a policy.</span></span>
- <span data-ttu-id="4a6c4-221">une stratégie n’est pas signée à partir d’un groupe.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-221">a policy is unassigned from a group.</span></span>
- <span data-ttu-id="4a6c4-222">une stratégie directement attribuée à l’utilisateur est supprimée.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-222">a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="4a6c4-223">Classement des affectations de groupe</span><span class="sxs-lookup"><span data-stu-id="4a6c4-223">Group assignment ranking</span></span>

<span data-ttu-id="4a6c4-224">Lorsque vous attribuez une stratégie à un groupe, vous spécifiez un classement pour l’affectation du groupe.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-224">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="4a6c4-225">Permet de déterminer la stratégie qu’un utilisateur doit hériter de sa stratégie efficace si l’utilisateur est membre de deux groupes ou plus et qu’une stratégie du même type est assignée à chaque groupe.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-225">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="4a6c4-226">Le classement d’affectation de groupe est relatif aux autres affectations de groupe du même type.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-226">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="4a6c4-227">Par exemple, si vous affectez une stratégie d’appel à deux groupes, définissez le classement d’une affectation sur 1 et l’autre sur 2, 1 étant le plus élevé.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-227">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="4a6c4-228">Le classement d’affectation de groupe indique quelle appartenance au groupe est plus importante ou plus pertinente que d’autres appartenances de groupe en matière d’héritage.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-228">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships regarding inheritance.</span></span>

<span data-ttu-id="4a6c4-229">Par exemple, vous avez deux groupes, Employés du Store et Responsables de magasin.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-229">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="4a6c4-230">Les deux groupes se sont respectivement attribué une stratégie Teams d’appel, la stratégie d’appel du Store Employees et la Stratégie d’appel des responsables du Store.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-230">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="4a6c4-231">Pour un responsable de magasin faisant partie des deux groupes, son rôle de responsable est plus pertinent que son rôle d’employé. Par ailleurs, la stratégie d’appel attribuée au groupe Responsables de magasin doit avoir un classement plus élevé.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-231">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="4a6c4-232">Grouper</span><span class="sxs-lookup"><span data-stu-id="4a6c4-232">Group</span></span> |<span data-ttu-id="4a6c4-233">Teams de la stratégie d’appel</span><span class="sxs-lookup"><span data-stu-id="4a6c4-233">Teams calling policy name</span></span>  |<span data-ttu-id="4a6c4-234">Classement</span><span class="sxs-lookup"><span data-stu-id="4a6c4-234">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="4a6c4-235">Responsables de magasin</span><span class="sxs-lookup"><span data-stu-id="4a6c4-235">Store Managers</span></span>   |<span data-ttu-id="4a6c4-236">Stratégie d’appel des responsables de magasin</span><span class="sxs-lookup"><span data-stu-id="4a6c4-236">Store Managers Calling Policy</span></span>         |<span data-ttu-id="4a6c4-237">1</span><span class="sxs-lookup"><span data-stu-id="4a6c4-237">1</span></span>|
|<span data-ttu-id="4a6c4-238">Employés du Store</span><span class="sxs-lookup"><span data-stu-id="4a6c4-238">Store Employees</span></span>    |<span data-ttu-id="4a6c4-239">Stratégie d’appel du Store Employees</span><span class="sxs-lookup"><span data-stu-id="4a6c4-239">Store Employees Calling Policy</span></span>      |<span data-ttu-id="4a6c4-240">2</span><span class="sxs-lookup"><span data-stu-id="4a6c4-240">2</span></span>|

<span data-ttu-id="4a6c4-241">Si vous ne spécifiez pas de classement, l’affectation de stratégie se voir attribué le classement le plus faible.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-241">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="in-the-teams-admin-center"></a><span data-ttu-id="4a6c4-242">Dans le Teams d’administration</span><span class="sxs-lookup"><span data-stu-id="4a6c4-242">In the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="4a6c4-243">Pour l’instant, l’affectation de stratégies à des groupes à l’aide du Centre d’administration Microsoft Teams est disponible uniquement pour la stratégie d’appel Teams, la stratégie de parcage d’appel Teams, la stratégie Teams, la stratégie d’événements en direct Teams, la stratégie de réunion Teams et la stratégie de messagerie Teams.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-243">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="4a6c4-244">Pour d’autres types de stratégie, utilisez PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-244">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="4a6c4-245">Dans le navigation gauche du Microsoft Teams d’administration, allez à la page du type de stratégie.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-245">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="4a6c4-246">Par exemple, allez à **Stratégies de**  >  **réunion.**</span><span class="sxs-lookup"><span data-stu-id="4a6c4-246">For example, go to **Meetings** > **Meeting policies**.</span></span>

2. <span data-ttu-id="4a6c4-247">Sélectionnez **l’onglet Affectation de stratégie de** groupe.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-247">Select the **Group policy assignment** tab.</span></span>

3. <span data-ttu-id="4a6c4-248">Sélectionnez **Ajouter un** groupe, puis dans le volet **Affecter** une stratégie à un groupe, comme suit :</span><span class="sxs-lookup"><span data-stu-id="4a6c4-248">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="4a6c4-249">Recherchez et ajoutez le groupe à qui vous voulez affecter la stratégie.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-249">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="4a6c4-250">Définissez le classement pour l’affectation de groupe.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-250">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="4a6c4-251">Sélectionnez la stratégie à affecter.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-251">Select the policy that you want to assign.</span></span>
    4. <span data-ttu-id="4a6c4-252">Sélectionnez **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="4a6c4-252">Select **Apply**.</span></span>

<span data-ttu-id="4a6c4-253">Pour supprimer une affectation de  stratégie de groupe, dans l’onglet Affectation de stratégie de groupe de la page stratégie, sélectionnez l’affectation de groupe, puis sélectionnez **Supprimer.**</span><span class="sxs-lookup"><span data-stu-id="4a6c4-253">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="4a6c4-254">Pour modifier le classement d’une affectation de groupe, vous devez d’abord supprimer l’affectation de stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-254">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="4a6c4-255">Suivez ensuite les étapes ci-dessus pour affecter la stratégie à un groupe.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-255">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="use-the-powershell-option"></a><span data-ttu-id="4a6c4-256">Utiliser l’option PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a6c4-256">Use the PowerShell option</span></span>

> [!NOTE]
> <span data-ttu-id="4a6c4-257">Actuellement, l’affectation de stratégies à des groupes à l’aide de PowerShell n’est pas disponible pour tous Teams types de stratégies.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-257">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="4a6c4-258">Pour obtenir la liste des types de stratégies pris en charge, voir [New-CsGroupPolicyAssignment.](/powershell/module/teams/new-csgrouppolicyassignment)</span><span class="sxs-lookup"><span data-stu-id="4a6c4-258">See [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="4a6c4-259">Installer et se connecter au module PowerShell Microsoft Teams’équipe</span><span class="sxs-lookup"><span data-stu-id="4a6c4-259">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="4a6c4-260">Pour obtenir des instructions pas à pas, voir [Installer Teams PowerShell.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="4a6c4-260">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group-of-users"></a><span data-ttu-id="4a6c4-261">Affecter une stratégie à un groupe d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="4a6c4-261">Assign a policy to a group of users</span></span>

<span data-ttu-id="4a6c4-262">Utilisez [l’cmdlet New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) pour affecter une stratégie à un groupe.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-262">Use the [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="4a6c4-263">Vous pouvez spécifier un groupe à l’aide de l’ID d’objet, de l’adresse SIP ou de l’adresse de messagerie.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-263">You can specify a group by using the object ID, SIP address, or email address.</span></span>

<span data-ttu-id="4a6c4-264">Dans cet exemple, nous affectons une stratégie Teams réunion nommée Stratégie de réunion des responsables de vente au détail à un groupe avec un classement d’affectations de 1.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-264">In this example, we assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="4a6c4-265">Obtenir des affectations de stratégie pour un groupe</span><span class="sxs-lookup"><span data-stu-id="4a6c4-265">Get policy assignments for a group</span></span>

<span data-ttu-id="4a6c4-266">Utilisez [l’cmdlet Get-CsGroupPolicyAssignment](/powershell/module/teams/get-csgrouppolicyassignment) pour attribuer toutes les stratégies à un groupe.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-266">Use the [Get-CsGroupPolicyAssignment](/powershell/module/teams/get-csgrouppolicyassignment) cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="4a6c4-267">Notez que les groupes sont toujours répertoriés par leur ID de groupe, même si leur adresse SIP ou adresse de messagerie a été utilisée pour affecter la stratégie.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-267">Note that groups are always listed by their group ID even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="4a6c4-268">Dans cet exemple, nous récupérons toutes les stratégies affectées à un groupe spécifique.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-268">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="4a6c4-269">Dans cet exemple, nous renvoyons tous les groupes à qui une stratégie Teams réunion est affectée.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-269">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="4a6c4-270">Supprimer une stratégie d’un groupe</span><span class="sxs-lookup"><span data-stu-id="4a6c4-270">Remove a policy from a group</span></span>

<span data-ttu-id="4a6c4-271">Utilisez [l’cmdlet Remove-CsGroupPolicyAssignment](/powershell/module/teams/remove-csgrouppolicyassignment) pour supprimer une stratégie d’un groupe.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-271">Use the [Remove-CsGroupPolicyAssignment](/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="4a6c4-272">Lorsque vous supprimez une stratégie d’un groupe, les priorités des autres stratégies du même type attribuées à ce groupe (avec un classement inférieur) sont mises à jour.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-272">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group, and that have a lower ranking, are updated.</span></span> <span data-ttu-id="4a6c4-273">Par exemple, si vous supprimez une stratégie qui présente un classement de 2, les stratégies dont le classement est 3 et 4 sont mises à jour pour refléter leur nouveau classement.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-273">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="4a6c4-274">Les deux tableaux suivants illustrent cet exemple.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-274">The following two tables show this example.</span></span>

<span data-ttu-id="4a6c4-275">Voici une liste des affectations de stratégies et des priorités pour une stratégie de Teams réunion.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-275">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="4a6c4-276">Nom du groupe</span><span class="sxs-lookup"><span data-stu-id="4a6c4-276">Group name</span></span>  |<span data-ttu-id="4a6c4-277">Nom de la stratégie</span><span class="sxs-lookup"><span data-stu-id="4a6c4-277">Policy name</span></span>  |<span data-ttu-id="4a6c4-278">Classement</span><span class="sxs-lookup"><span data-stu-id="4a6c4-278">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="4a6c4-279">Ventes</span><span class="sxs-lookup"><span data-stu-id="4a6c4-279">Sales</span></span>    |<span data-ttu-id="4a6c4-280">Politique commerciale</span><span class="sxs-lookup"><span data-stu-id="4a6c4-280">Sales policy</span></span>       | <span data-ttu-id="4a6c4-281">1</span><span class="sxs-lookup"><span data-stu-id="4a6c4-281">1</span></span>        |
|<span data-ttu-id="4a6c4-282">Région Ouest</span><span class="sxs-lookup"><span data-stu-id="4a6c4-282">West Region</span></span>     |<span data-ttu-id="4a6c4-283">Politique de la région Ouest</span><span class="sxs-lookup"><span data-stu-id="4a6c4-283">West Region policy</span></span>         |<span data-ttu-id="4a6c4-284">2</span><span class="sxs-lookup"><span data-stu-id="4a6c4-284">2</span></span>         |
|<span data-ttu-id="4a6c4-285">Division</span><span class="sxs-lookup"><span data-stu-id="4a6c4-285">Division</span></span>    |<span data-ttu-id="4a6c4-286">Stratégie de division</span><span class="sxs-lookup"><span data-stu-id="4a6c4-286">Division policy</span></span>         |<span data-ttu-id="4a6c4-287">3</span><span class="sxs-lookup"><span data-stu-id="4a6c4-287">3</span></span>         |
|<span data-ttu-id="4a6c4-288">Filiale</span><span class="sxs-lookup"><span data-stu-id="4a6c4-288">Subsidiary</span></span>   |<span data-ttu-id="4a6c4-289">Stratégie de filiale</span><span class="sxs-lookup"><span data-stu-id="4a6c4-289">Subsidiary policy</span></span>        |<span data-ttu-id="4a6c4-290">4</span><span class="sxs-lookup"><span data-stu-id="4a6c4-290">4</span></span>         |

<span data-ttu-id="4a6c4-291">Si nous ôtons la stratégie de la région Ouest du groupe Région Ouest, les affectations de stratégie et les priorités sont mises à jour comme suit.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-291">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="4a6c4-292">Nom du groupe</span><span class="sxs-lookup"><span data-stu-id="4a6c4-292">Group name</span></span>  |<span data-ttu-id="4a6c4-293">Nom de la stratégie</span><span class="sxs-lookup"><span data-stu-id="4a6c4-293">Policy name</span></span>  |<span data-ttu-id="4a6c4-294">Classement</span><span class="sxs-lookup"><span data-stu-id="4a6c4-294">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="4a6c4-295">Ventes</span><span class="sxs-lookup"><span data-stu-id="4a6c4-295">Sales</span></span>    |<span data-ttu-id="4a6c4-296">Politique commerciale</span><span class="sxs-lookup"><span data-stu-id="4a6c4-296">Sales policy</span></span>       | <span data-ttu-id="4a6c4-297">1</span><span class="sxs-lookup"><span data-stu-id="4a6c4-297">1</span></span>        |
|<span data-ttu-id="4a6c4-298">Division</span><span class="sxs-lookup"><span data-stu-id="4a6c4-298">Division</span></span>    |<span data-ttu-id="4a6c4-299">Stratégie de division</span><span class="sxs-lookup"><span data-stu-id="4a6c4-299">Division policy</span></span>         |<span data-ttu-id="4a6c4-300">2</span><span class="sxs-lookup"><span data-stu-id="4a6c4-300">2</span></span>         |
|<span data-ttu-id="4a6c4-301">Filiale</span><span class="sxs-lookup"><span data-stu-id="4a6c4-301">Subsidiary</span></span>   |<span data-ttu-id="4a6c4-302">Stratégie de filiale</span><span class="sxs-lookup"><span data-stu-id="4a6c4-302">Subsidiary policy</span></span>        |<span data-ttu-id="4a6c4-303">3</span><span class="sxs-lookup"><span data-stu-id="4a6c4-303">3</span></span>        |

<span data-ttu-id="4a6c4-304">Dans cet exemple, nous allons supprimer la stratégie Teams réunion d’un groupe.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-304">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="4a6c4-305">Modifier une affectation de stratégie pour un groupe</span><span class="sxs-lookup"><span data-stu-id="4a6c4-305">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="4a6c4-306">[L’cmdlet Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) sera bientôt disponible.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-306">The [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) cmdlet will be available soon.</span></span> <span data-ttu-id="4a6c4-307">En attendant, pour modifier une affectation de stratégie de groupe, vous pouvez supprimer l’affectation de stratégie actuelle du groupe, puis ajouter une nouvelle affectation de stratégie.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-307">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="4a6c4-308">Après avoir attribué une stratégie à un groupe, vous pouvez utiliser l’cmdlet [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) pour modifier l’affectation de stratégie de ce groupe comme suit :</span><span class="sxs-lookup"><span data-stu-id="4a6c4-308">After you assign a policy to a group, you can use the [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="4a6c4-309">Modifier le classement</span><span class="sxs-lookup"><span data-stu-id="4a6c4-309">Change the ranking</span></span>
- <span data-ttu-id="4a6c4-310">Modifier la stratégie d’un type de stratégie donné</span><span class="sxs-lookup"><span data-stu-id="4a6c4-310">Change the policy of a given policy type</span></span>
- <span data-ttu-id="4a6c4-311">Modifier la stratégie d’un type de stratégie donné et le classement</span><span class="sxs-lookup"><span data-stu-id="4a6c4-311">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="4a6c4-312">Dans cet exemple, nous avons changé la stratégie d’un groupe en Teams par une stratégie nommée SupportCallPark et le classement d’affectations à 3.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-312">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="4a6c4-313">Modifier la stratégie efficace d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="4a6c4-313">Change the effective policy for a user</span></span>

<span data-ttu-id="4a6c4-314">Voici un exemple de la façon de modifier la stratégie efficace pour un utilisateur à qui une stratégie est directement attribuée.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-314">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="4a6c4-315">Tout d’abord, nous utilisons la cmdlet [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment) avec le paramètre pour obtenir les détails des stratégies de diffusion de réunion Teams associées à `PolicySource` l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-315">First, we use the [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment) cmdlet together with the `PolicySource` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="4a6c4-316">La sortie indique que l’utilisateur a été directement affecté à une stratégie de diffusion de réunion Teams nommée Événements d’employés, qui prend le pas sur la stratégie Événements en direct du fournisseur qui est attribuée à un groupe auquel l’utilisateur appartient.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-316">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="4a6c4-317">À présent, nous ôtons la stratégie Événements d’employés de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-317">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="4a6c4-318">Cela signifie que l’utilisateur n’a plus de stratégie de diffusion de réunion Teams qui lui est directement attribuée et hérite de la stratégie Événements en direct du fournisseur qui est attribuée au groupe dont l’utilisateur appartient.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-318">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span>

<span data-ttu-id="4a6c4-319">Pour ce faire, utilisez l’cmdlet Skype Entreprise le module PowerShell suivant.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-319">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="4a6c4-320">Utilisez l’cmdlet suivante dans le module Teams PowerShell pour le faire à l’échelle même si vous avez une affectation de stratégie de lot, où $users est une liste d’utilisateurs que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-320">Use following cmdlet in the Teams PowerShell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="4a6c4-321">Affecter une stratégie à un lot d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="4a6c4-321">Assign a policy to a batch of users</span></span>

### <a name="use-the-admin-center"></a><span data-ttu-id="4a6c4-322">Utiliser le Centre d’administration</span><span class="sxs-lookup"><span data-stu-id="4a6c4-322">Use the admin center</span></span>

<span data-ttu-id="4a6c4-323">Pour affecter une stratégie aux utilisateurs en bloc :</span><span class="sxs-lookup"><span data-stu-id="4a6c4-323">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="4a6c4-324">Dans le navigation gauche du centre d Microsoft Teams d’administration, sélectionnez **Utilisateurs.**</span><span class="sxs-lookup"><span data-stu-id="4a6c4-324">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>

2. <span data-ttu-id="4a6c4-325">Recherchez les utilisateurs à qui vous voulez affecter la stratégie ou filtrez l’affichage pour afficher les utilisateurs que vous souhaitez.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-325">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>

3. <span data-ttu-id="4a6c4-326">Dans la colonne **&#x2713;** (coche), sélectionnez les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-326">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="4a6c4-327">Pour sélectionner tous les utilisateurs, cliquez sur &#x2713; (coche) en haut du tableau.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-327">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>

4. <span data-ttu-id="4a6c4-328">Sélectionnez **Modifier les paramètres,** a apporter les modifications de votre choix, puis **sélectionnez Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="4a6c4-328">Select **Edit settings**, make the changes that you want, and then select **Apply**.</span></span>

<span data-ttu-id="4a6c4-329">Pour afficher l’état de votre affectation de stratégie, dans la bannière  qui apparaît en haut de la **page** Utilisateurs après avoir sélectionné Appliquer pour envoyer votre affectation de stratégie, sélectionnez Journal **d’activité.**</span><span class="sxs-lookup"><span data-stu-id="4a6c4-329">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you select **Apply** to submit your policy assignment, select **Activity log**.</span></span> <span data-ttu-id="4a6c4-330">Dans le navigation gauche du centre d’administration Microsoft Teams, sélectionnez Tableau de **bord,** puis sous Journal d’activité, sélectionnez Afficher les **détails.**</span><span class="sxs-lookup"><span data-stu-id="4a6c4-330">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, select **View details**.</span></span> <span data-ttu-id="4a6c4-331">Le journal d’activité affiche les affectations de stratégie à des lots de plus de 20 utilisateurs via le Centre Microsoft Teams d’administration à partir des 30 derniers jours.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-331">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="4a6c4-332">Pour plus d’informations, [voir Afficher vos affectations de stratégie dans le journal d’activité.](activity-log.md)</span><span class="sxs-lookup"><span data-stu-id="4a6c4-332">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="use-powershell-method"></a><span data-ttu-id="4a6c4-333">Utiliser la méthode PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a6c4-333">Use PowerShell method</span></span>

> [!NOTE]
> <span data-ttu-id="4a6c4-334">Actuellement, l’affectation de stratégie de lot à l’aide de PowerShell n’est pas disponible pour tous Teams types de stratégies.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-334">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="4a6c4-335">Pour obtenir la liste des types de stratégies pris en charge, voir [New-CsBatchPolicyAssignmentOperation.](/powershell/module/teams/new-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="4a6c4-335">See [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

<span data-ttu-id="4a6c4-336">L’affectation de stratégie de lot vous permet d’affecter une stratégie à de grands ensembles d’utilisateurs à la fois sans utiliser de script.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-336">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="4a6c4-337">Vous utilisez la [cmdlet New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) pour envoyer un lot d’utilisateurs et la stratégie que vous voulez attribuer.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-337">You use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="4a6c4-338">Les attributions sont traitées comme une opération d’arrière-plan et un ID d’opération est généré pour chaque lot.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-338">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="4a6c4-339">Vous pouvez ensuite utiliser la cmdlet [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) pour suivre l’avancement et l’état des devoirs d’un lot.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-339">You can then use the [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="4a6c4-340">Spécifiez les utilisateurs selon leur ID d’objet ou leur adresse SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="4a6c4-340">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="4a6c4-341">L’adresse SIP d’un utilisateur a souvent la même valeur que le nom d’utilisateur principal (UPN) ou l’adresse de courrier, mais cela n’est pas obligatoire.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-341">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="4a6c4-342">Si un utilisateur est spécifié à l’aide de son nom d’utilisateur supérieur ou de son adresse de courrier, mais que sa valeur est différente de celle de son adresse SIP, l’attribution de stratégie échoue pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-342">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="4a6c4-343">Si un lot inclut des utilisateurs en double, les doublons sont supprimés du lot avant que le traitement et l’état ne soient fournis qu’aux utilisateurs uniques restants du lot.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-343">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="4a6c4-344">Un lot peut contenir jusqu’à 5 000 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-344">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="4a6c4-345">Pour de meilleurs résultats, n’envoyez pas plus de quelques lots à la fois.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-345">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="4a6c4-346">Autorisez le traitement des lots avant l’envoi d’autres lots.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-346">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-teams-powershell-module"></a><span data-ttu-id="4a6c4-347">Installer et se connecter au module PowerShell Teams’équipe</span><span class="sxs-lookup"><span data-stu-id="4a6c4-347">Install and connect to the Teams PowerShell module</span></span>

<span data-ttu-id="4a6c4-348">Exécutez la commande suivante pour installer [Microsoft Teams module PowerShell.](https://www.powershellgallery.com/packages/MicrosoftTeams)</span><span class="sxs-lookup"><span data-stu-id="4a6c4-348">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="4a6c4-349">Veillez à installer la version 1.0.5 ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-349">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="4a6c4-350">Exécutez ce qui suit pour vous connecter Teams et démarrer une session.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-350">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="4a6c4-351">Lorsque vous y êtes invité, connectez-vous à l’aide de vos informations d’identification d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-351">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="4a6c4-352">Installer et se connecter au module Azure AD PowerShell Graph (facultatif)</span><span class="sxs-lookup"><span data-stu-id="4a6c4-352">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="4a6c4-353">Vous pouvez également télécharger et installer le [module Azure AD PowerShell](/powershell/azure/active-directory/install-adv2) pour Graph (si ce n’est déjà fait) et vous connecter à Azure AD afin de récupérer la liste des utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-353">You might also want to [download and install the Azure AD PowerShell for Graph module](/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="4a6c4-354">Exécutez ce qui suit pour vous connecter à Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-354">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="4a6c4-355">Lorsque vous y êtes invité, connectez-vous à l’aide des mêmes informations d’identification d’administrateur que vous avez utilisées pour vous connecter à Teams.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-355">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a><span data-ttu-id="4a6c4-356">Affecter une stratégie d’installation à un lot d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="4a6c4-356">Assign a setup policy to a batch of users</span></span>

<span data-ttu-id="4a6c4-357">Dans cet exemple, nous utilisons la cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) pour affecter une stratégie de configuration d’application nommée Hr App Setup Policy à un lot d’utilisateurs répertoriés dans le fichier Users_ids.txt.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-357">In this example, we use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.txt file.</span></span>

```powershell
$users_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="4a6c4-358">Dans cet exemple, nous nous connectons à Azure AD pour récupérer un ensemble d’utilisateurs, puis affectons une stratégie de messagerie nommée Stratégie de messagerie nouvelle embauche à un lot d’utilisateurs spécifiés à l’aide de leur adresse SIP.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-358">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="4a6c4-359">Obtenir l’état d’une affectation de lot</span><span class="sxs-lookup"><span data-stu-id="4a6c4-359">Get the status of a batch assignment</span></span>

<span data-ttu-id="4a6c4-360">Exécutez ce qui suit pour obtenir l’état d’une affectation de lot, où OperationId est l’ID d’opération renvoyé par `New-CsBatchPolicyAssignmentOperation` l’cmdlet pour un lot donné.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-360">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the `New-CsBatchPolicyAssignmentOperation` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="4a6c4-361">Si la sortie indique qu’une erreur s’est produite, exécutez l’erreur suivante pour obtenir plus d’informations sur les erreurs, qui se trouver dans la `UserState` propriété.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-361">If the output shows that an error occurred, run the following to get more information about errors, which are in the `UserState` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="4a6c4-362">Pour en savoir plus, [consultez Get-CsBatchPolicyAssignmentOperation.](/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="4a6c4-362">To learn more, see [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="4a6c4-363">Attribuer un package de stratégies aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="4a6c4-363">Assign a policy package to users</span></span>

<span data-ttu-id="4a6c4-364">Un package de stratégie dans Teams est un ensemble de stratégies et paramètres de stratégie prédéfinés que vous pouvez affecter aux utilisateurs ayant des rôles identiques ou similaires dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-364">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="4a6c4-365">Chaque package de stratégie est conçu autour d’un rôle d’utilisateur et inclut des stratégies et paramètres de stratégie prédéfinés qui supportent des activités classiques pour ce rôle.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-365">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="4a6c4-366">Le package Éducation (enseignant) et le package Soins de santé (travailleurs cliniques) sont quelques exemples de packages de stratégie.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-366">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="4a6c4-367">Pour plus d’informations, [voir Gérer les packages de stratégie dans Teams.](manage-policy-packages.md)</span><span class="sxs-lookup"><span data-stu-id="4a6c4-367">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="4a6c4-368">Attribuer un package de stratégie à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="4a6c4-368">Assign a policy package to one user</span></span>

1. <span data-ttu-id="4a6c4-369">Dans le panneau de navigation gauche du Microsoft Teams d’administration, sélectionnez Utilisateurs, puis l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-369">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>

2. <span data-ttu-id="4a6c4-370">Dans la page de l’utilisateur, sélectionnez **Stratégies,** puis, à côté du **package** de stratégie, sélectionnez **Modifier.**</span><span class="sxs-lookup"><span data-stu-id="4a6c4-370">On the user's page, select **Policies**, and then next to **Policy package**, select **Edit**.</span></span>

3. <span data-ttu-id="4a6c4-371">Dans le **volet Attribuer un package** de stratégie, sélectionnez le package à attribuer, puis sélectionnez **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="4a6c4-371">In the **Assign policy package** pane, select the package you want to assign, and then select **Save**.</span></span>

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="4a6c4-372">Attribuer un package de stratégie à plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="4a6c4-372">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="4a6c4-373">Dans le navigation gauche du Centre d’administration Microsoft Teams, sélectionnez Packages de **stratégie,** puis sélectionnez le package de stratégie à attribuer en cliquant à gauche du nom du package.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-373">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>

2. <span data-ttu-id="4a6c4-374">Sélectionnez **Gérer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-374">Select **Manage users**.</span></span>

3. <span data-ttu-id="4a6c4-375">Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-375">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="4a6c4-376">Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-376">Repeat this step for each user that you want to add.</span></span>

4. <span data-ttu-id="4a6c4-377">Lorsque vous avez terminé d’ajouter des utilisateurs, sélectionnez **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="4a6c4-377">When you're finished adding users, select **Save**.</span></span>

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="4a6c4-378">Attribuer le package stratégie à un groupe</span><span class="sxs-lookup"><span data-stu-id="4a6c4-378">Assign a policy package to a group</span></span>

<span data-ttu-id="4a6c4-379">Attribution de package de stratégie aux groupes vous permet d’attribuer plusieurs stratégies à un groupe d’utilisateurs, tel qu’un groupe de sécurité ou une liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-379">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="4a6c4-380">L’affectations de stratégie est propagée aux membres du groupe en fonction de règles de priorité.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-380">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="4a6c4-381">Lorsque les membres sont ajoutés à un groupe ou supprimés de ceux-ci, leurs affectations de stratégie héritées sont mises à jour en conséquence.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-381">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="4a6c4-382">L’affectation de package de stratégie à des groupes est recommandée pour les groupes de jusqu’à 50 000 utilisateurs, mais elle fonctionne également avec les groupes plus importants.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-382">Policy package assignment to groups is recommended for groups of up to 50,000 users, but it will also work with larger groups.</span></span>

<span data-ttu-id="4a6c4-383">Lorsque vous attribuez le package de stratégie, il est immédiatement affecté au groupe.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-383">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="4a6c4-384">Toutefois, la propagation de l’affectation de stratégie aux membres du groupe est effectuée comme une opération en arrière-plan et peut prendre du temps, selon la taille du groupe.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-384">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="4a6c4-385">Il en va de même lorsqu’une stratégie est non signée dans un groupe, ou lorsque des membres sont ajoutés ou supprimés d’un groupe.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-385">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4a6c4-386">Avant de commencer, il est [](#precedence-rules) important de comprendre les règles de priorité et le [classement d’affectation de groupe.](#group-assignment-ranking)</span><span class="sxs-lookup"><span data-stu-id="4a6c4-386">Before you get started, it's important to understand [precedence rules](#precedence-rules) and [group assignment ranking](#group-assignment-ranking).</span></span> <span data-ttu-id="4a6c4-387">Assurez-vous de lire et de comprendre les concepts de ce que vous devez savoir sur l’affectation de stratégie aux groupes [plus](#what-you-need-to-know-about-policy-assignment-to-groups) tôt dans cet article.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-387">Make sure you read and understand the concepts in [What you need to know about policy assignment to groups](#what-you-need-to-know-about-policy-assignment-to-groups) earlier in this article.</span></span>

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a><span data-ttu-id="4a6c4-388">Attribuer un package de stratégie à un groupe d’utilisateurs dans le Centre d’administration</span><span class="sxs-lookup"><span data-stu-id="4a6c4-388">Assign a policy package to a group of users in the admin center</span></span>

1. <span data-ttu-id="4a6c4-389">Se connecter au Centre d’administration de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-389">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="4a6c4-390">Dans le dossier de navigation de gauche, allez à la page du package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-390">In the left navigation, go to the policy package page.</span></span>

3. <span data-ttu-id="4a6c4-391">Sélectionnez l’onglet Affectation de stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-391">Select the Group policy assignment tab.</span></span>

4. <span data-ttu-id="4a6c4-392">Sélectionnez **Ajouter un groupe,** puis dans le volet Affecter un package de stratégie au volet de groupe, comme suit :</span><span class="sxs-lookup"><span data-stu-id="4a6c4-392">Select **Add group**, and then in the Assign a policy package to group pane, do the following:</span></span>

    1. <span data-ttu-id="4a6c4-393">Recherchez et ajoutez le groupe à qui vous voulez affecter le package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-393">Search for and add the group you want to assign the policy package to.</span></span>
    
    1. <span data-ttu-id="4a6c4-394">Sélectionnez un package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-394">Select a policy package.</span></span>
    
    1. <span data-ttu-id="4a6c4-395">Définissez le classement pour chaque type de stratégie.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-395">Set the ranking for each policy type.</span></span>
    
    1. <span data-ttu-id="4a6c4-396">Sélectionnez **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="4a6c4-396">Select **Apply**.</span></span>
    
    ![affiche l’affectation de stratégie de groupe](media/group-pkg-assignment.png)

5. <span data-ttu-id="4a6c4-398">Pour gérer le classement d’un type de stratégie spécifique, accédez à la page de stratégie spécifique.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-398">To manage ranking for a specific policy type, navigate to the specific policy page.</span></span>

6. <span data-ttu-id="4a6c4-399">Pour réattribuer un package de stratégie à un groupe, supprimez tout d’abord l’affectation de stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-399">To reassign a policy package to a group, first remove the group policy assignment.</span></span> <span data-ttu-id="4a6c4-400">Ensuite, suivez les étapes ci-dessus pour affecter le package de stratégie à un groupe.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-400">Then, follow the steps above to assign the policy package to a group.</span></span>

### <a name="work-with-powershell"></a><span data-ttu-id="4a6c4-401">Travailler avec PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a6c4-401">Work with PowerShell</span></span>

#### <a name="get-the-teams-powershell-module"></a><span data-ttu-id="4a6c4-402">Obtenir le module PowerShell Teams’équipe</span><span class="sxs-lookup"><span data-stu-id="4a6c4-402">Get the Teams PowerShell module</span></span>

<span data-ttu-id="4a6c4-403">Pour obtenir des instructions pas à pas, voir [Installer Teams PowerShell.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="4a6c4-403">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="4a6c4-404">Affecter un package de stratégie à un groupe d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="4a6c4-404">Assign a policy package to a group of users</span></span>

<span data-ttu-id="4a6c4-405">Utilisez la [cmdlet Grant-CsGroupPolicyPackageAssignment](/powershell/module/teams/grant-csgrouppolicypackageassignment) pour affecter un package de stratégie à un groupe.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-405">Use the [Grant-CsGroupPolicyPackageAssignment](/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="4a6c4-406">Vous pouvez spécifier un groupe à l’aide de l’ID d’objet, de l’adresse SIP ou de l’adresse de messagerie.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-406">You can specify a group by using the object ID, SIP address, or email address.</span></span> <span data-ttu-id="4a6c4-407">Lorsque vous attribuez le package de stratégie, spécifiez un classement [d’affectation](#group-assignment-ranking) de groupe pour chaque type de stratégie dans le package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-407">When you assign the policy package, specify a [group assignment ranking](#group-assignment-ranking) for each policy type in the policy package.</span></span>

<span data-ttu-id="4a6c4-408">Dans cet exemple, nous affectons le package de stratégie Education_Teacher à un groupe avec un classement d’affectations de 1 pour TeamsAppSetupPolicy et TeamsMeetingBroadcastPolicy et un classement de 2 pour TeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-408">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="4a6c4-409">Affecter un package de stratégie à un lot d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="4a6c4-409">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="4a6c4-410">L’affectation de package de stratégie de lot vous permet d’affecter un package de stratégie à de grands ensembles d’utilisateurs à la fois sans utiliser de script.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-410">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="4a6c4-411">Vous utilisez la cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) pour envoyer un lot d’utilisateurs et le package de stratégie que vous souhaitez affecter.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-411">You use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="4a6c4-412">Les attributions sont traitées comme une opération d’arrière-plan et un ID d’opération est généré pour chaque lot.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-412">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="4a6c4-413">Vous pouvez ensuite utiliser la cmdlet [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) pour suivre l’avancement et l’état des devoirs d’un lot.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-413">You can then use the [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="4a6c4-414">Spécifiez les utilisateurs selon leur ID d’objet ou leur adresse SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="4a6c4-414">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="4a6c4-415">L’adresse SIP d’un utilisateur a souvent la même valeur que le nom d’utilisateur principal (UPN) ou l’adresse de courrier, mais cela n’est pas obligatoire.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-415">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this isn't required.</span></span> <span data-ttu-id="4a6c4-416">Si un utilisateur est spécifié à l’aide de son nom d’utilisateur supérieur ou de son adresse de courrier, mais que sa valeur est différente de celle de son adresse SIP, l’attribution de stratégie échoue pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-416">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="4a6c4-417">Si un lot inclut des utilisateurs en double, les doublons sont supprimés du lot avant que le traitement et l’état ne soient fournis qu’aux utilisateurs uniques restants du lot.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-417">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="4a6c4-418">Un lot contient jusqu’à 5 000 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-418">A batch contains up to 5,000 users.</span></span> <span data-ttu-id="4a6c4-419">Pour de meilleurs résultats, n’envoyez pas plus de quelques lots à la fois.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-419">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="4a6c4-420">Autorisez le traitement des lots avant l’envoi d’autres lots.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-420">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="use-the-teams-powershell-module"></a><span data-ttu-id="4a6c4-421">Utiliser le module Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a6c4-421">Use the Teams PowerShell module</span></span>

<span data-ttu-id="4a6c4-422">Exécutez la commande suivante pour installer [Microsoft Teams module PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (si vous ne l’avez pas déjà fait).</span><span class="sxs-lookup"><span data-stu-id="4a6c4-422">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="4a6c4-423">Veillez à installer la version 1.0.5 ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-423">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="4a6c4-424">Exécutez ce qui suit pour vous connecter Teams et démarrer une session.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-424">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="4a6c4-425">Lorsque vous y êtes invité, connectez-vous à l’aide de vos informations d’identification d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-425">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-policy-packages-to-a-batch-of-users"></a><span data-ttu-id="4a6c4-426">Attribuer des packages de stratégie à un lot d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="4a6c4-426">Assign policy packages to a batch of users</span></span>

<span data-ttu-id="4a6c4-427">Dans cet exemple, nous utilisons la cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) pour affecter le package de stratégie Education_PrimaryStudent à un lot d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-427">In this example, we use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a><span data-ttu-id="4a6c4-428">Voir l’état d’une affectation de lot</span><span class="sxs-lookup"><span data-stu-id="4a6c4-428">See the status of a batch assignment</span></span>

<span data-ttu-id="4a6c4-429">Exécutez ce qui suit pour obtenir l’état d’une affectation de lot, où OperationId est l’ID d’opération renvoyé par `New-CsBatchPolicyAssignmentOperation` l’cmdlet pour un lot donné.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-429">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the `New-CsBatchPolicyAssignmentOperation` cmdlet for a given batch.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="4a6c4-430">Si la sortie indique qu’une erreur s’est produite, exécutez l’erreur suivante pour obtenir plus d’informations sur les erreurs, qui se trouver dans la `UserState` propriété.</span><span class="sxs-lookup"><span data-stu-id="4a6c4-430">If the output shows that an error occurred, run the following to get more information about errors, which are in the `UserState` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="4a6c4-431">Pour en savoir plus, [consultez Get-CsBatchPolicyAssignmentOperation.](/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="4a6c4-431">To learn more, see [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4a6c4-432">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="4a6c4-432">Related topics</span></span>

[<span data-ttu-id="4a6c4-433">Aperçu de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a6c4-433">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
