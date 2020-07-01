---
title: Attribuer des stratégies à vos utilisateurs dans Microsoft Teams.
author: lanachin
ms.author: v-lanac
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
description: Découvrez les différentes méthodes d’attribution de stratégies aux utilisateurs de Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 403131fa3e7bd2b3fb2a128640ac49497394d669
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938543"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="f5776-103">Attribuer des stratégies à vos utilisateurs dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f5776-103">Assign policies to your users in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="f5776-104">**Notez ce qui suit à propos de l’une des fonctionnalités décrites dans cet article intitulé affectation de stratégie aux groupes**:</span><span class="sxs-lookup"><span data-stu-id="f5776-104">**Note the following about one of the features discussed in this article, policy assignment to groups**:</span></span> 
> - <span data-ttu-id="f5776-105">Une [affectation de stratégie à des groupes à l’aide du centre d’administration Microsoft teams](#using-the-microsoft-teams-admin-center-3)n’a pas encore été publiée.</span><span class="sxs-lookup"><span data-stu-id="f5776-105">[Policy assignment to groups using the Microsoft Teams admin center](#using-the-microsoft-teams-admin-center-3), hasn't yet been released.</span></span> <span data-ttu-id="f5776-106">Il a été annoncé et est bientôt disponible.</span><span class="sxs-lookup"><span data-stu-id="f5776-106">It's been announced, and it's coming soon.</span></span> 
> - <span data-ttu-id="f5776-107">[Pour l’instant, l’attribution de stratégies aux groupes à l’aide de PowerShell](#using-powershell-3)n’est disponible qu’en version préliminaire privée.</span><span class="sxs-lookup"><span data-stu-id="f5776-107">[Policy assignment to groups using PowerShell](#using-powershell-3), is currently only available in private preview.</span></span> <span data-ttu-id="f5776-108">Les applets de connexion PowerShell de cette fonctionnalité se trouvent dans le module pre-version PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="f5776-108">The Powershell cmdlets for this feature are in the pre-release Teams PowerShell module.</span></span>
>
> <span data-ttu-id="f5776-109">Pour en savoir plus sur l’état de publication de cette fonctionnalité, consultez la [documentation Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185).</span><span class="sxs-lookup"><span data-stu-id="f5776-109">To stay on top of the release status of this feature, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185).</span></span>

<span data-ttu-id="f5776-110">En tant qu’administrateur, vous utilisez des stratégies pour contrôler les fonctionnalités d’équipes disponibles pour les utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f5776-110">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="f5776-111">Par exemple, il existe des stratégies d’appel, des stratégies de réunion et des stratégies de messagerie pour n’appeler qu’un seul nom.</span><span class="sxs-lookup"><span data-stu-id="f5776-111">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="f5776-112">Les organisations ont différents types d’utilisateurs dotés de besoins uniques et de stratégies personnalisées que vous créez et attribuez les paramètres de stratégie à différents ensembles d’utilisateurs en fonction de vos besoins.</span><span class="sxs-lookup"><span data-stu-id="f5776-112">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="f5776-113">Pour faciliter la gestion des stratégies au sein de votre organisation, teams permet d’attribuer des stratégies aux utilisateurs de différentes manières.</span><span class="sxs-lookup"><span data-stu-id="f5776-113">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="f5776-114">Vous pouvez affecter une stratégie directement aux utilisateurs, individuellement ou à la fois par le biais d’une affectation par lot ou à un groupe dont les utilisateurs sont membres.</span><span class="sxs-lookup"><span data-stu-id="f5776-114">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="f5776-115">Vous pouvez également utiliser des packages de stratégie pour affecter une collection prédéfinie de stratégies aux utilisateurs de votre organisation possédant des rôles similaires.</span><span class="sxs-lookup"><span data-stu-id="f5776-115">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="f5776-116">L’option que vous choisissez dépend du nombre de stratégies que vous gérez et du nombre d’utilisateurs auxquels vous attribuez.</span><span class="sxs-lookup"><span data-stu-id="f5776-116">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span> <span data-ttu-id="f5776-117">En définissant les stratégies globales par défaut de l’organisation, afin qu’elles s’appliquent au plus grand nombre d’utilisateurs de votre organisation, il vous suffit d’affecter des stratégies aux utilisateurs qui ont besoin de stratégies spécialisées.</span><span class="sxs-lookup"><span data-stu-id="f5776-117">By setting the global (Org-wide default) policies so that they apply to the largest number of users in your organization, you only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="f5776-118">Cet article décrit les différentes façons dont vous pouvez attribuer des stratégies aux utilisateurs et les scénarios recommandés pour les situations dans lesquelles utiliser.</span><span class="sxs-lookup"><span data-stu-id="f5776-118">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="f5776-119">Quelle est la stratégie prioritaire ?</span><span class="sxs-lookup"><span data-stu-id="f5776-119">Which policy takes precedence?</span></span>

<span data-ttu-id="f5776-120">Un utilisateur dispose d’une stratégie efficace pour chaque type de stratégie.</span><span class="sxs-lookup"><span data-stu-id="f5776-120">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="f5776-121">Il est possible, ou même probable, que l’utilisateur dispose d’une stratégie directement affectée et qu’il soit membre d’un ou plusieurs groupes auxquels une stratégie du même type est affectée.</span><span class="sxs-lookup"><span data-stu-id="f5776-121">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="f5776-122">Dans ces types de scénarios, quelle stratégie est prioritaire ?</span><span class="sxs-lookup"><span data-stu-id="f5776-122">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="f5776-123">La stratégie d’effectivité d’un utilisateur est déterminée conformément aux règles de priorité, comme suit.</span><span class="sxs-lookup"><span data-stu-id="f5776-123">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="f5776-124">Si un utilisateur dispose d’une stratégie (individuelle ou par le biais d’une affectation de lot), cette stratégie est prioritaire.</span><span class="sxs-lookup"><span data-stu-id="f5776-124">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="f5776-125">Dans l’exemple suivant, la stratégie effective de l’utilisateur est la stratégie de réunion carrée d’Lincoln, qui est directement affectée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f5776-125">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![Diagramme montrant comment une stratégie attribuée directement est prioritaire](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="f5776-127">Si un utilisateur n’a pas directement affecté une stratégie d’un type donné, la stratégie affectée à un groupe dont l’utilisateur est membre de a la priorité.</span><span class="sxs-lookup"><span data-stu-id="f5776-127">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="f5776-128">Si un utilisateur est membre de plusieurs groupes, la stratégie présentant le niveau de [classement des affectations de groupe](#group-assignment-ranking) le plus élevé pour le type de stratégie donné est prioritaire.</span><span class="sxs-lookup"><span data-stu-id="f5776-128">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="f5776-129">Dans cet exemple, la stratégie effective de l’utilisateur est la stratégie d’exécution et la stratégie HD, qui présente le niveau d’attribution le plus élevé par rapport aux autres groupes dont l’utilisateur est membre et auquel une stratégie du même type de stratégie est affectée.</span><span class="sxs-lookup"><span data-stu-id="f5776-129">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![Diagramme montrant comment une stratégie héritée du groupe est prioritaire](media/assign-policies-example-group.png)

<span data-ttu-id="f5776-131">Si un utilisateur n’est pas directement affecté à une stratégie ou n’est pas membre de tous les groupes auxquels une stratégie est affectée, l’utilisateur obtient la stratégie globale (par défaut de l’organisation par défaut) pour ce type de stratégie.</span><span class="sxs-lookup"><span data-stu-id="f5776-131">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="f5776-132">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="f5776-132">Here's an example.</span></span>

![Diagramme illustrant le niveau de priorité d’une stratégie globale](media/assign-policies-example-global.png)

<span data-ttu-id="f5776-134">Pour en savoir plus, voir [règles de précédence](#precedence-rules).</span><span class="sxs-lookup"><span data-stu-id="f5776-134">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="f5776-135">Méthodes d’attribution de stratégies</span><span class="sxs-lookup"><span data-stu-id="f5776-135">Ways to assign policies</span></span>

<span data-ttu-id="f5776-136">Vous trouverez ci-dessous une vue d’ensemble des méthodes permettant d’attribuer des stratégies aux utilisateurs et les scénarios recommandés pour chacun.</span><span class="sxs-lookup"><span data-stu-id="f5776-136">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="f5776-137">Cliquez sur les liens pour en savoir plus.</span><span class="sxs-lookup"><span data-stu-id="f5776-137">Click the links to learn more.</span></span>

<span data-ttu-id="f5776-138">Avant d’affecter des stratégies à des utilisateurs ou des groupes spécifiques, commencez par [définir les stratégies globales par défaut](#set-the-global-policies) de l’organisation afin qu’elles s’appliquent au plus grand nombre d’utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f5776-138">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="f5776-139">Une fois les stratégies globales définies, vous n’aurez besoin d’affecter des stratégies qu’aux utilisateurs qui ont besoin de stratégies spécialisées.</span><span class="sxs-lookup"><span data-stu-id="f5776-139">Once the global policies are set, you will only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="f5776-140">Procédez comme suit…</span><span class="sxs-lookup"><span data-stu-id="f5776-140">Do this</span></span>  |<span data-ttu-id="f5776-141">Si...</span><span class="sxs-lookup"><span data-stu-id="f5776-141">If...</span></span>  | <span data-ttu-id="f5776-142">Utilisation de...</span><span class="sxs-lookup"><span data-stu-id="f5776-142">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="f5776-143">Assigner une stratégie à des utilisateurs individuels</span><span class="sxs-lookup"><span data-stu-id="f5776-143">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="f5776-144">Vous débutez en équipe et vous commencez simplement à attribuer une ou plusieurs stratégies à un petit nombre d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f5776-144">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="f5776-145">Centre d’administration Microsoft teams ou cmdlets PowerShell dans le module PowerShell de Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="f5776-145">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
| [<span data-ttu-id="f5776-146">Assigner un package de stratégie</span><span class="sxs-lookup"><span data-stu-id="f5776-146">Assign a policy package</span></span>](#assign-a-policy-package)   | <span data-ttu-id="f5776-147">Vous devez affecter plusieurs stratégies à des ensembles d’utilisateurs spécifiques de votre organisation qui ont des rôles identiques ou similaires.</span><span class="sxs-lookup"><span data-stu-id="f5776-147">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="f5776-148">Par exemple, attribuez le package de stratégie éducation (enseignant) aux enseignants de votre établissement scolaire pour leur permettre d’accéder à l’ensemble des conversations, appels et réunions, ainsi que le package d’étude (étudiant d’école secondaire) aux étudiants secondaires pour limiter certaines fonctionnalités, telles que les appels privés.</span><span class="sxs-lookup"><span data-stu-id="f5776-148">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="f5776-149">Centre d’administration Microsoft teams ou cmdlets PowerShell dans le module PowerShell teams</span><span class="sxs-lookup"><span data-stu-id="f5776-149">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="f5776-150">Attribuer une stratégie à un lot d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="f5776-150">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="f5776-151">Vous devez attribuer des stratégies à d’importants ensembles d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f5776-151">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="f5776-152">Par exemple, vous pouvez attribuer une stratégie à des centaines ou des milliers d’utilisateurs de votre organisation à la fois.</span><span class="sxs-lookup"><span data-stu-id="f5776-152">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="f5776-153">Centre d’administration Microsoft teams ou cmdlets PowerShell dans le module PowerShell teams</span><span class="sxs-lookup"><span data-stu-id="f5776-153">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|<span data-ttu-id="f5776-154">[Assigner une stratégie à un groupe](#assign-a-policy-to-a-group) (dans Preview ou bientôt disponible)</span><span class="sxs-lookup"><span data-stu-id="f5776-154">[Assign a policy to a group](#assign-a-policy-to-a-group) (in preview/coming soon)</span></span>|<span data-ttu-id="f5776-155">Vous devez attribuer des stratégies en fonction de l’appartenance d’un utilisateur à un groupe.</span><span class="sxs-lookup"><span data-stu-id="f5776-155">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="f5776-156">Par exemple, vous souhaitez attribuer une stratégie à l’ensemble des utilisateurs d’un groupe de sécurité ou d’une unité d’organisation.</span><span class="sxs-lookup"><span data-stu-id="f5776-156">For example, you want to assign a policy to all users in a security group or organizational unit.</span></span>| <span data-ttu-id="f5776-157">Centre d’administration de Microsoft Teams (bientôt disponible) ou cmdlets PowerShell dans le module PowerShell Teams (en version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="f5776-157">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module (in preview)</span></span>|
| [<span data-ttu-id="f5776-158">Affectation d’un package de stratégie à un lot d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="f5776-158">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="f5776-159">Vous devez affecter plusieurs stratégies à un lot d’utilisateurs de votre organisation qui ont des rôles identiques ou similaires.</span><span class="sxs-lookup"><span data-stu-id="f5776-159">You need to assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="f5776-160">Par exemple, attribuez le package de stratégie éducation (enseignant) à tous les enseignants de votre établissement scolaire à l’aide de la fonctionnalité d’attribution de lot pour leur permettre d’accéder à des conversations, des appels et des réunions, et d’affecter le package de stratégie éducation (école secondaire) à un lot d’étudiants secondaires pour limiter certaines fonctionnalités telles que les appels privés.</span><span class="sxs-lookup"><span data-stu-id="f5776-160">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings and assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities like private calling.</span></span>|<span data-ttu-id="f5776-161">Cmdlets PowerShell dans le module PowerShell teams</span><span class="sxs-lookup"><span data-stu-id="f5776-161">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="f5776-162">Assigner un package de stratégie à un groupe (bientôt disponible)</span><span class="sxs-lookup"><span data-stu-id="f5776-162">Assign a policy package to a group (coming soon)</span></span>   | ||

## <a name="set-the-global-policies"></a><span data-ttu-id="f5776-163">Définir les stratégies globales</span><span class="sxs-lookup"><span data-stu-id="f5776-163">Set the global policies</span></span>

<span data-ttu-id="f5776-164">Pour définir les stratégies globales par défaut de chaque type de stratégie, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="f5776-164">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="f5776-165">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f5776-165">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="f5776-166">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à la page de stratégie correspondant au type de stratégie que vous voulez mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="f5776-166">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="f5776-167">Par **exemple, les**politiques teams Teams, les stratégies de  >  **Teams policies** **Meetings**  >  **réunions**, les **stratégies de messagerie**ou les politiques d' **Voice**  >  **appel**vocal.</span><span class="sxs-lookup"><span data-stu-id="f5776-167">For example, **Teams** > **Teams policies**, **Meetings** > **Meetings policies**, **Messaging policies**, or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="f5776-168">Sélectionnez la stratégie **globale par défaut** de l’Organisation pour afficher les paramètres actuels.</span><span class="sxs-lookup"><span data-stu-id="f5776-168">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="f5776-169">Mettez à jour la stratégie selon vos besoins, puis sélectionnez **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="f5776-169">Update the policy as needed, and then select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="f5776-170">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5776-170">Using PowerShell</span></span>

<span data-ttu-id="f5776-171">Pour définir les stratégies globales à l’aide de PowerShell, utilisez l’identificateur global.</span><span class="sxs-lookup"><span data-stu-id="f5776-171">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="f5776-172">Commencez par examiner la stratégie globale actuelle pour déterminer le paramètre que vous voulez modifier.</span><span class="sxs-lookup"><span data-stu-id="f5776-172">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

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

<span data-ttu-id="f5776-173">Ensuite, mettez à jour la stratégie globale selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="f5776-173">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="f5776-174">Il vous suffit de spécifier des valeurs pour les paramètres que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="f5776-174">You only need to specify values for the settings that you want to change.</span></span> 
 
```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="f5776-175">Assigner une stratégie à des utilisateurs individuels</span><span class="sxs-lookup"><span data-stu-id="f5776-175">Assign a policy to individual users</span></span>

<span data-ttu-id="f5776-176">Procédez comme suit pour attribuer une stratégie à un utilisateur individuel ou à un petit nombre d’utilisateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="f5776-176">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="f5776-177">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f5776-177">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="f5776-178">Pour attribuer une stratégie à un utilisateur :</span><span class="sxs-lookup"><span data-stu-id="f5776-178">To assign a policy to a user:</span></span>

1. <span data-ttu-id="f5776-179">Dans le volet de navigation gauche du centre d’administration Microsoft Teams, et accédez aux **Utilisateurs**, puis cliquez sur l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f5776-179">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="f5776-180">Sélectionnez l’utilisateur en cliquant à gauche du nom de celui-ci, puis cliquez sur **Modifier les paramètres**.</span><span class="sxs-lookup"><span data-stu-id="f5776-180">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="f5776-181">Sélectionnez la stratégie que vous voulez attribuer, puis cliquez sur **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="f5776-181">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="f5776-182">Vous pouvez également effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="f5776-182">Or, you can also do the following:</span></span>

1. <span data-ttu-id="f5776-183">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à la page de stratégie.</span><span class="sxs-lookup"><span data-stu-id="f5776-183">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="f5776-184">Sélectionnez la stratégie que vous voulez affecter en cliquant à gauche du nom de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="f5776-184">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="f5776-185">Sélectionnez **Gérer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="f5776-185">Select **Manage users**.</span></span>
4. <span data-ttu-id="f5776-186">Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f5776-186">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="f5776-187">Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="f5776-187">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="f5776-188">Lorsque vous avez terminé d’ajouter des utilisateurs, sélectionnez **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="f5776-188">When you're finished adding users, select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="f5776-189">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5776-189">Using PowerShell</span></span>

<span data-ttu-id="f5776-190">Chaque type de stratégie dispose de son propre ensemble d’applets de service pour sa gestion.</span><span class="sxs-lookup"><span data-stu-id="f5776-190">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="f5776-191">Utilisez l' ```Grant-``` applet de cmdlet d’un type de stratégie donné pour affecter la stratégie.</span><span class="sxs-lookup"><span data-stu-id="f5776-191">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="f5776-192">Par exemple, utilisez l' ```Grant-CsTeamsMeetingPolicy``` applet de cmdlet pour attribuer une stratégie de réunion teams à des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f5776-192">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="f5776-193">Ces applets de service sont inclus dans le module PowerShell de Skype entreprise Online et sont décrits dans la référence de l’applet de connexion [Skype entreprise](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f5776-193">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="f5776-194">Téléchargez et installez le [module PowerShell de Skype entreprise Online](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (si vous ne l’avez pas déjà fait), puis exécutez la commande suivante pour vous connecter à Skype entreprise Online et commencer une session.</span><span class="sxs-lookup"><span data-stu-id="f5776-194">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="f5776-195">Dans cet exemple, nous affectons une stratégie de réunion teams nommée Stratégie de réunion étudiant à un utilisateur nommé reda.</span><span class="sxs-lookup"><span data-stu-id="f5776-195">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="f5776-196">Pour en savoir plus, voir [gestion des stratégies via PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span><span class="sxs-lookup"><span data-stu-id="f5776-196">To learn more, see [Managing policies via PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span></span>

## <a name="assign-a-policy-package"></a><span data-ttu-id="f5776-197">Assigner un package de stratégie</span><span class="sxs-lookup"><span data-stu-id="f5776-197">Assign a policy package</span></span>

<span data-ttu-id="f5776-198">Un package de stratégie dans teams est un ensemble de stratégies et de paramètres de stratégie prédéfinis que vous pouvez affecter aux utilisateurs qui ont des rôles similaires ou similaires au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f5776-198">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="f5776-199">Chaque package de stratégie est conçu à l’aide d’un rôle d’utilisateur et comprend des stratégies et des paramètres de stratégie prédéfinis qui prennent en charge les activités typiques pour ce rôle.</span><span class="sxs-lookup"><span data-stu-id="f5776-199">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="f5776-200">Voici quelques exemples de packages de stratégie : le package éducation (enseignant) et le module Healthcare (Medical Worker).</span><span class="sxs-lookup"><span data-stu-id="f5776-200">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span>

<span data-ttu-id="f5776-201">Lorsque vous attribuez un package de stratégie aux utilisateurs, les stratégies du package sont créées et vous pouvez personnaliser les paramètres de chaque stratégie du package pour répondre aux besoins des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f5776-201">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of each policy in the package to meet users' needs.</span></span>

<span data-ttu-id="f5776-202">Pour en savoir plus sur les packages de stratégie, y compris des instructions détaillées sur la manière de les affecter et de les gérer, voir [gérer les packages de stratégie dans teams](manage-policy-packages.md).</span><span class="sxs-lookup"><span data-stu-id="f5776-202">To learn more about policy packages, including step-by-step guidance on how to assign and manage them, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="f5776-203">Attribuer une stratégie à un lot d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="f5776-203">Assign a policy to a batch of users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="f5776-204">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f5776-204">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="f5776-205">Pour attribuer une stratégie aux utilisateurs en bloc :</span><span class="sxs-lookup"><span data-stu-id="f5776-205">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="f5776-206">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, sélectionnez **utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="f5776-206">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="f5776-207">Recherchez les utilisateurs auxquels vous voulez affecter la stratégie ou filtrez l’affichage pour afficher les utilisateurs souhaités.</span><span class="sxs-lookup"><span data-stu-id="f5776-207">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="f5776-208">Dans la colonne **&#x2713;** (coche), sélectionnez les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f5776-208">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="f5776-209">Pour sélectionner tous les utilisateurs, cliquez sur &#x2713; (coche) en haut du tableau.</span><span class="sxs-lookup"><span data-stu-id="f5776-209">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="f5776-210">Cliquez sur **Modifier les paramètres**, apportez les modifications souhaitées, puis cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="f5776-210">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="f5776-211">Pour afficher l’état de votre affectation de stratégie, dans la bannière qui s’affiche en haut de la page **utilisateurs** après avoir cliqué sur **appliquer** pour valider votre affectation de stratégie, cliquez sur **Journal d’activité**.</span><span class="sxs-lookup"><span data-stu-id="f5776-211">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you click **Apply** to submit your policy assignment, click **Activity log**.</span></span> <span data-ttu-id="f5776-212">Ou, dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez au **tableau de bord**, puis sous **Journal d’activité**, cliquez sur Afficher les **Détails**.</span><span class="sxs-lookup"><span data-stu-id="f5776-212">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, click **View details**.</span></span> <span data-ttu-id="f5776-213">Le journal d’activité affiche les affectations de stratégie aux lots de plus de 20 utilisateurs par le biais du centre d’administration Microsoft teams depuis les 30 derniers jours.</span><span class="sxs-lookup"><span data-stu-id="f5776-213">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="f5776-214">Pour en savoir plus, voir [afficher les affectations de stratégie dans le journal d’activité](activity-log.md).</span><span class="sxs-lookup"><span data-stu-id="f5776-214">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="f5776-215">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5776-215">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="f5776-216">Pour l’instant, l’affectation de stratégie de lot à l’aide de PowerShell n’est pas disponible pour tous les types de stratégie équipes.</span><span class="sxs-lookup"><span data-stu-id="f5776-216">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="f5776-217">Pour obtenir la liste des types de stratégie pris en charge, voir [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) .</span><span class="sxs-lookup"><span data-stu-id="f5776-217">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>
 
<span data-ttu-id="f5776-218">Avec une affectation de stratégie de lot, vous pouvez attribuer une stratégie à un grand nombre d’utilisateurs à la fois sans avoir à utiliser de script.</span><span class="sxs-lookup"><span data-stu-id="f5776-218">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="f5776-219">Utilisez l' ```New-CsBatchPolicyAssignmentOperation``` applet de commande pour signaler un lot d’utilisateurs et la stratégie que vous voulez affecter.</span><span class="sxs-lookup"><span data-stu-id="f5776-219">You use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="f5776-220">Les affectations sont traitées en tant qu’opérations en arrière-plan et chaque lot est généré.</span><span class="sxs-lookup"><span data-stu-id="f5776-220">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="f5776-221">Vous pouvez ensuite utiliser l' ```Get-CsBatchPolicyAssignmentOperation``` applet de commande pour effectuer le suivi de l’avancement et de l’état des devoirs d’un lot.</span><span class="sxs-lookup"><span data-stu-id="f5776-221">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="f5776-222">Vous pouvez spécifier des utilisateurs en fonction de leur ID d’objet ou de leur adresse SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="f5776-222">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="f5776-223">Notez que le nom d’utilisateur principal (UPN) ou l’adresse de messagerie de l’utilisateur a souvent la même valeur que le nom d’utilisateur principal (UPN) ou l’adresse de messagerie, mais cela n’est pas obligatoire.</span><span class="sxs-lookup"><span data-stu-id="f5776-223">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="f5776-224">Si un utilisateur est spécifié à l’aide de son nom d’utilisateur principal ou de son adresse de messagerie, mais qu’il a une valeur différente de son adresse SIP, l’affectation de stratégie échouera pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f5776-224">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="f5776-225">Si un lot inclut des utilisateurs en double, les doublons seront supprimés du lot avant traitement et le statut ne sera fourni qu’aux utilisateurs uniques figurant dans le lot.</span><span class="sxs-lookup"><span data-stu-id="f5776-225">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="f5776-226">Un lot peut contenir jusqu’à 5 000 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f5776-226">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="f5776-227">Pour obtenir de meilleurs résultats, n’envoyez pas plus de quelques lots à la fois.</span><span class="sxs-lookup"><span data-stu-id="f5776-227">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="f5776-228">Autorisez le traitement des lots avant de soumettre d’autres lots.</span><span class="sxs-lookup"><span data-stu-id="f5776-228">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="f5776-229">Installer le module Microsoft teams PowerShell et s’y connecter</span><span class="sxs-lookup"><span data-stu-id="f5776-229">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="f5776-230">Exécutez la commande suivante pour installer le [module Microsoft teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams).</span><span class="sxs-lookup"><span data-stu-id="f5776-230">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="f5776-231">Vérifiez que vous avez installé la version 1.0.5 ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="f5776-231">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="f5776-232">Exécutez la commande suivante pour vous connecter à teams et démarrer une session.</span><span class="sxs-lookup"><span data-stu-id="f5776-232">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="f5776-233">Lorsque vous y êtes invité, connectez-vous à l’aide de vos informations d’identification d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="f5776-233">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="f5776-234">Installez et connectez-vous à Azure AD PowerShell pour le module Graph (facultatif)</span><span class="sxs-lookup"><span data-stu-id="f5776-234">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="f5776-235">Vous pouvez également [Télécharger et installer le module Azure ad PowerShell pour Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (le cas échéant) et vous connecter à Azure AD pour récupérer la liste des utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f5776-235">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="f5776-236">Exécutez la commande suivante pour vous connecter à Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f5776-236">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="f5776-237">Lorsque vous y êtes invité, connectez-vous à l’aide des informations d’identification d’administrateur que vous avez utilisées pour vous connecter à Teams.</span><span class="sxs-lookup"><span data-stu-id="f5776-237">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="f5776-238">Attribuer une stratégie à un lot d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="f5776-238">Assign a policy to a batch of users</span></span>

<span data-ttu-id="f5776-239">Dans cet exemple, nous utilisons l' ```New-CsBatchPolicyAssignmentOperation``` applet de commande pour assigner une stratégie d’installation d’application nommée Stratégie de configuration des applications humaines à un lot d’utilisateurs répertoriés dans le fichier Users_ids. Text.</span><span class="sxs-lookup"><span data-stu-id="f5776-239">In this example, we use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="f5776-240">Dans cet exemple, nous allons nous connecter à Azure AD pour récupérer une collection d’utilisateurs, puis affecter une stratégie de messagerie nommée nouvelle stratégie de messagerie à un lot d’utilisateurs spécifiés à l’aide de leur adresse SIP.</span><span class="sxs-lookup"><span data-stu-id="f5776-240">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

<span data-ttu-id="f5776-241">Pour en savoir plus, voir [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="f5776-241">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="f5776-242">Obtenir l’état d’une affectation par lot</span><span class="sxs-lookup"><span data-stu-id="f5776-242">Get the status of a batch assignment</span></span>

<span data-ttu-id="f5776-243">Exécutez la commande suivante pour obtenir l’état d’une affectation de lot, où OperationId est l’ID d’opération renvoyé par l' ```New-CsBatchPolicyAssignmentOperation``` applet de commande pour un lot donné.</span><span class="sxs-lookup"><span data-stu-id="f5776-243">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="f5776-244">Si la sortie indique qu’une erreur s’est produite, exécutez la commande suivante pour obtenir plus d’informations sur les erreurs qui se trouvent dans la ```UserState``` propriété.</span><span class="sxs-lookup"><span data-stu-id="f5776-244">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="f5776-245">Pour en savoir plus, consultez la rubrique [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="f5776-245">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="f5776-246">Assigner une stratégie à un groupe</span><span class="sxs-lookup"><span data-stu-id="f5776-246">Assign a policy to a group</span></span>

<span data-ttu-id="f5776-247">Attribution de stratégie aux groupes vous permet d’affecter une stratégie à un groupe d’utilisateurs, tel qu’un groupe de sécurité ou une unité d’organisation.</span><span class="sxs-lookup"><span data-stu-id="f5776-247">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or organizational unit.</span></span> <span data-ttu-id="f5776-248">L’affectation de stratégie est propagée aux membres du groupe conformément aux règles de priorité.</span><span class="sxs-lookup"><span data-stu-id="f5776-248">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="f5776-249">Les membres étant ajoutés ou supprimés d’un groupe, leurs affectations de stratégie héritées sont mises à jour en conséquence.</span><span class="sxs-lookup"><span data-stu-id="f5776-249">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="f5776-250">Une affectation de stratégie à des groupes est recommandée pour des groupes d’utilisateurs 50 000, mais elle fonctionne également avec des groupes de plus grande taille.</span><span class="sxs-lookup"><span data-stu-id="f5776-250">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="f5776-251">Lorsque vous affectez la stratégie, celle-ci est immédiatement affectée au groupe.</span><span class="sxs-lookup"><span data-stu-id="f5776-251">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="f5776-252">Toutefois, Notez que la propagation de l’affectation de stratégie aux membres du groupe est effectuée en tant qu’opération en arrière-plan et peut prendre un certain temps selon la taille du groupe.</span><span class="sxs-lookup"><span data-stu-id="f5776-252">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="f5776-253">Il en va de même lorsque la stratégie n’est pas attribuée à un groupe, ou lorsque les membres sont ajoutés à un groupe ou supprimés.</span><span class="sxs-lookup"><span data-stu-id="f5776-253">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="f5776-254">Ce que vous devez savoir sur l’attribution de stratégies aux groupes</span><span class="sxs-lookup"><span data-stu-id="f5776-254">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="f5776-255">Avant de commencer, il est important de comprendre les règles de précédence et le classement des affectations de groupe.</span><span class="sxs-lookup"><span data-stu-id="f5776-255">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="f5776-256">Règles de précédence</span><span class="sxs-lookup"><span data-stu-id="f5776-256">Precedence rules</span></span>

<span data-ttu-id="f5776-257">Pour un type de stratégie donné, la stratégie effective d’un utilisateur est déterminée conformément aux éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="f5776-257">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="f5776-258">Une stratégie attribuée directement à un utilisateur est prioritaire sur une autre stratégie du même type affectée à un groupe.</span><span class="sxs-lookup"><span data-stu-id="f5776-258">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="f5776-259">En d’autres termes, si un utilisateur reçoit directement une stratégie d’un type donné, il n’hérite pas d’une stratégie du même type d’un groupe.</span><span class="sxs-lookup"><span data-stu-id="f5776-259">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="f5776-260">En d’autres termes, si un utilisateur possède une stratégie d’un type donné qui lui a été directement affecté, vous devez supprimer cette stratégie de l’utilisateur pour pouvoir hériter d’une stratégie du même type d’un groupe.</span><span class="sxs-lookup"><span data-stu-id="f5776-260">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="f5776-261">Si un utilisateur ne dispose pas directement d’une stratégie et est membre de deux groupes ou plus, et qu’il dispose d’une stratégie du même type qui lui est affecté, il hérite de la stratégie du groupe affecté dont le classement est le plus élevé.</span><span class="sxs-lookup"><span data-stu-id="f5776-261">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="f5776-262">Si un utilisateur n’est pas membre de groupes auxquels une stratégie est affectée, la stratégie globale par défaut de l’Organisation pour ce type de stratégie s’applique à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f5776-262">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="f5776-263">La stratégie effective d’un utilisateur est mise à jour en fonction de ces règles lorsqu’un utilisateur est ajouté ou supprimé d’un groupe auquel est affectée une stratégie, qu’une stratégie n’est pas attribuée à partir d’un groupe ou qu’une stratégie attribuée directement à l’utilisateur est supprimée.</span><span class="sxs-lookup"><span data-stu-id="f5776-263">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="f5776-264">Classement des affectations de groupe</span><span class="sxs-lookup"><span data-stu-id="f5776-264">Group assignment ranking</span></span>
 
<span data-ttu-id="f5776-265">Lorsque vous affectez une stratégie à un groupe, vous spécifiez le classement de l’affectation de groupe.</span><span class="sxs-lookup"><span data-stu-id="f5776-265">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="f5776-266">Il est utilisé pour identifier la stratégie qu’un utilisateur doit hériter en tant que stratégie effective si l’utilisateur est membre de deux groupes ou plus et qu’une stratégie du même type est affectée à chaque groupe.</span><span class="sxs-lookup"><span data-stu-id="f5776-266">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="f5776-267">Le classement des affectations de groupe est relatif par rapport à d’autres affectations de groupe du même type.</span><span class="sxs-lookup"><span data-stu-id="f5776-267">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="f5776-268">Par exemple, si vous attribuez une stratégie d’appel à deux groupes, définissez le classement d’une affectation sur 1 et l’autre sur 2, avec 1 en tant que classement le plus élevé.</span><span class="sxs-lookup"><span data-stu-id="f5776-268">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="f5776-269">Le classement des affectations de groupe indique l’appartenance au groupe qui est la plus importante ou la plus pertinente par rapport à d’autres appartenances aux groupes en ce qui concerne l’héritage.</span><span class="sxs-lookup"><span data-stu-id="f5776-269">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="f5776-270">Imaginons, par exemple, que vous avez deux groupes, que vous stockez des employés et des responsables du magasin.</span><span class="sxs-lookup"><span data-stu-id="f5776-270">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="f5776-271">Les deux groupes se voient attribuer une stratégie d’appel d’équipes, et les employés de la stratégie d’appel et de la stratégie d’appel des responsables de la boutique sont respectivement.</span><span class="sxs-lookup"><span data-stu-id="f5776-271">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="f5776-272">Dans le cas d’un responsable du Windows Store qui se trouve dans les deux groupes, son rôle en tant que responsable est supérieur à celui d’un employé, de sorte que la stratégie d’appel attribuée au groupe responsables du magasin doit présenter un niveau de classement supérieur.</span><span class="sxs-lookup"><span data-stu-id="f5776-272">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="f5776-273">Groupe</span><span class="sxs-lookup"><span data-stu-id="f5776-273">Group</span></span> |<span data-ttu-id="f5776-274">Nom de la stratégie d’appel teams</span><span class="sxs-lookup"><span data-stu-id="f5776-274">Teams calling policy name</span></span>  |<span data-ttu-id="f5776-275">Classement</span><span class="sxs-lookup"><span data-stu-id="f5776-275">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="f5776-276">Responsables du Windows Store</span><span class="sxs-lookup"><span data-stu-id="f5776-276">Store Managers</span></span>   |<span data-ttu-id="f5776-277">Stratégie d’appel des directeurs du Windows Store</span><span class="sxs-lookup"><span data-stu-id="f5776-277">Store Managers Calling Policy</span></span>         |<span data-ttu-id="f5776-278">1</span><span class="sxs-lookup"><span data-stu-id="f5776-278">1</span></span>|
|<span data-ttu-id="f5776-279">Magasin employés</span><span class="sxs-lookup"><span data-stu-id="f5776-279">Store Employees</span></span>    |<span data-ttu-id="f5776-280">Politique d’appel des employés du Store</span><span class="sxs-lookup"><span data-stu-id="f5776-280">Store Employees Calling Policy</span></span>      |<span data-ttu-id="f5776-281">2</span><span class="sxs-lookup"><span data-stu-id="f5776-281">2</span></span>|

<span data-ttu-id="f5776-282">Si vous ne spécifiez pas de classement, l’affectation de la stratégie est affectée du plus petit classement.</span><span class="sxs-lookup"><span data-stu-id="f5776-282">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="f5776-283">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f5776-283">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="f5776-284">**Cette fonctionnalité n’a pas encore été publiée. Il a été annoncé et est bientôt disponible.**</span><span class="sxs-lookup"><span data-stu-id="f5776-284">**This feature hasn't yet been released. It's been announced, and it's coming soon.**</span></span>

> [!NOTE]
> <span data-ttu-id="f5776-285">Pour l’instant, l’affectation de stratégie à des groupes à l’aide du centre d’administration Microsoft teams n’est disponible que pour la stratégie d’appel d’équipe, la stratégie de réunion équipes et la stratégie de messagerie Teams.</span><span class="sxs-lookup"><span data-stu-id="f5776-285">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="f5776-286">Pour les autres types de stratégies, utilisez PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f5776-286">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="f5776-287">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à la page type de stratégie.</span><span class="sxs-lookup"><span data-stu-id="f5776-287">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="f5776-288">Par exemple, accédez à **Meetings**  >  **stratégies de réunion**réunions.</span><span class="sxs-lookup"><span data-stu-id="f5776-288">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="f5776-289">Sélectionnez l’onglet **affectation de stratégie de groupe** .</span><span class="sxs-lookup"><span data-stu-id="f5776-289">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="f5776-290">Sélectionnez **Ajouter un groupe**, puis, dans le volet **affecter une stratégie à un groupe** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f5776-290">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="f5776-291">Recherchez et ajoutez le groupe auquel vous voulez affecter la stratégie.</span><span class="sxs-lookup"><span data-stu-id="f5776-291">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="f5776-292">Définissez le classement de l’affectation de groupe.</span><span class="sxs-lookup"><span data-stu-id="f5776-292">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="f5776-293">Sélectionnez la stratégie que vous voulez attribuer.</span><span class="sxs-lookup"><span data-stu-id="f5776-293">Select the policy that you want to assign.</span></span> 
    4. <span data-ttu-id="f5776-294">Sélectionnez **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="f5776-294">Select **Apply**.</span></span>

<span data-ttu-id="f5776-295">Pour supprimer une affectation de stratégie de groupe, dans l’onglet **affectation de stratégie de groupe** de la page de stratégie, sélectionnez l’affectation de groupe, puis sélectionnez **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="f5776-295">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="f5776-296">Pour modifier le classement d’une affectation de groupe, vous devez d’abord supprimer l’affectation de stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="f5776-296">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="f5776-297">Ensuite, suivez les étapes ci-dessus pour affecter la stratégie à un groupe.</span><span class="sxs-lookup"><span data-stu-id="f5776-297">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="f5776-298">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5776-298">Using PowerShell</span></span>

<span data-ttu-id="f5776-299">**Pour le moment, cette fonctionnalité est uniquement disponible dans la version préliminaire privée. Les applets de fonction de cette fonctionnalité se trouvent dans le module pre-version PowerShell Teams.**</span><span class="sxs-lookup"><span data-stu-id="f5776-299">**This feature is currently only available in private preview. The cmdlets for this feature are in the pre-release Teams PowerShell module.**</span></span>

> [!NOTE]
> <span data-ttu-id="f5776-300">Pour l’instant, l’affectation de stratégie à des groupes à l’aide de PowerShell n’est pas disponible pour tous les types de stratégie d’équipe.</span><span class="sxs-lookup"><span data-stu-id="f5776-300">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="f5776-301">Pour obtenir la liste des types de stratégie pris en charge, voir [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) .</span><span class="sxs-lookup"><span data-stu-id="f5776-301">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="f5776-302">Installer le module Microsoft teams PowerShell et s’y connecter</span><span class="sxs-lookup"><span data-stu-id="f5776-302">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="f5776-303">Les applets de contrôle se trouvent dans la version préliminaire du module PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="f5776-303">The cmdlets are in the pre-release version of the Teams PowerShell module.</span></span> <span data-ttu-id="f5776-304">Suivez ces étapes pour commencer par désinstaller la version disponible en général du module PowerShell Teams (s’il est installé), puis installez la dernière version préliminaire du module à partir de la Galerie de tests PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f5776-304">Follow these steps to first uninstall the Generally Available version of the Teams PowerShell module (if it's installed), and then install the latest pre-release version of the module from the PowerShell Test Gallery.</span></span>

<span data-ttu-id="f5776-305">Si ce n’est déjà fait, exécutez la commande suivante pour inscrire la Galerie de tests PowerShell comme source fiable.</span><span class="sxs-lookup"><span data-stu-id="f5776-305">If you haven't already, run the following to register the PowerShell Test Gallery as a trusted source.</span></span>

```powershell
Register-PSRepository -SourceLocation https://www.poshtestgallery.com/api/v2 -Name PsTestGallery -InstallationPolicy Trusted
```

<span data-ttu-id="f5776-306">Si vous avez installé la version disponible en général du module PowerShell Teams, exécutez la commande suivante pour la désinstaller.</span><span class="sxs-lookup"><span data-stu-id="f5776-306">If you have the Generally Available version of the Teams PowerShell module installed, run the following to uninstall it.</span></span>

```powershell
Uninstall-Module MicrosoftTeams -AllVersions
```

<span data-ttu-id="f5776-307">Exécutez la commande suivante pour installer le module Microsoft teams PowerShell le plus récent à partir de la Galerie de tests PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f5776-307">Run the following to install the latest Microsoft Teams PowerShell module from the PowerShell Test Gallery.</span></span>

```powershell
Install-Module MicrosoftTeams -Repository PSTestGallery
```

<span data-ttu-id="f5776-308">Exécutez la commande suivante pour vous connecter à teams et démarrer une session.</span><span class="sxs-lookup"><span data-stu-id="f5776-308">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="f5776-309">Lorsque vous y êtes invité, connectez-vous à l’aide de vos informations d’identification d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="f5776-309">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="f5776-310">Assigner une stratégie à un groupe</span><span class="sxs-lookup"><span data-stu-id="f5776-310">Assign a policy to a group</span></span>

<span data-ttu-id="f5776-311">Vous pouvez utiliser l' ```New-CsGroupPolicyAssignment``` applet de cmdlet pour attribuer une stratégie à un groupe.</span><span class="sxs-lookup"><span data-stu-id="f5776-311">You use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="f5776-312">Vous pouvez spécifier un groupe à l’aide d’un ID d’objet, d’une adresse SIP ou d’une adresse de messagerie.</span><span class="sxs-lookup"><span data-stu-id="f5776-312">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="f5776-313">Dans cet exemple, nous utilisons l' ```New-CsGroupPolicyAssignment``` applet de cmdlet pour assigner une stratégie de réunion équipes nommée Stratégie de réunion des responsables de revente à un groupe dont le classement de devoirs est 1.</span><span class="sxs-lookup"><span data-stu-id="f5776-313">In this example, we use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

<span data-ttu-id="f5776-314">Pour en savoir plus, voir [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="f5776-314">To learn more, see [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span></span>

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="f5776-315">Obtenir des affectations de stratégie pour un groupe</span><span class="sxs-lookup"><span data-stu-id="f5776-315">Get policy assignments for a group</span></span>

<span data-ttu-id="f5776-316">Utilisez l' ```Get-CsGroupPolicyAssignment``` applet de cmdlet pour obtenir toutes les stratégies attribuées à un groupe.</span><span class="sxs-lookup"><span data-stu-id="f5776-316">Use the ```Get-CsGroupPolicyAssignment``` cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="f5776-317">Notez que les groupes sont toujours répertoriés par leur ID de groupe même si l’adresse ou l’adresse de messagerie SIP a été utilisée pour affecter la stratégie.</span><span class="sxs-lookup"><span data-stu-id="f5776-317">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="f5776-318">Dans cet exemple, nous récupérons toutes les stratégies affectées à un groupe spécifique.</span><span class="sxs-lookup"><span data-stu-id="f5776-318">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="f5776-319">Dans cet exemple, nous renvoyons tous les groupes auxquels une stratégie de réunion équipes est affectée.</span><span class="sxs-lookup"><span data-stu-id="f5776-319">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

<span data-ttu-id="f5776-320">Pour en savoir plus, consultez la rubrique [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="f5776-320">To learn more, see [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span></span>

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="f5776-321">Supprimer une stratégie d’un groupe</span><span class="sxs-lookup"><span data-stu-id="f5776-321">Remove a policy from a group</span></span>

<span data-ttu-id="f5776-322">Utilisez l' ```Remove-CsGroupPolicyAssignment``` applet de cmdlet pour supprimer une stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="f5776-322">Use the ```Remove-CsGroupPolicyAssignment``` cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="f5776-323">Lorsque vous supprimez une stratégie d’un groupe, les priorités des autres stratégies du même type attribuées à ce groupe et dont le classement est inférieur sont mises à jour.</span><span class="sxs-lookup"><span data-stu-id="f5776-323">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="f5776-324">Par exemple, si vous supprimez une stratégie de classement de 2, les stratégies dont le classement est 3 et 4 sont mis à jour pour refléter leur nouveau classement.</span><span class="sxs-lookup"><span data-stu-id="f5776-324">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="f5776-325">Les deux tables suivantes montrent cet exemple.</span><span class="sxs-lookup"><span data-stu-id="f5776-325">The following two tables show this example.</span></span>

<span data-ttu-id="f5776-326">Vous trouverez ci-dessous une liste des affectations et des priorités pour une stratégie de réunion Teams.</span><span class="sxs-lookup"><span data-stu-id="f5776-326">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="f5776-327">Nom du groupe</span><span class="sxs-lookup"><span data-stu-id="f5776-327">Group name</span></span>  |<span data-ttu-id="f5776-328">Nom de la stratégie</span><span class="sxs-lookup"><span data-stu-id="f5776-328">Policy name</span></span>  |<span data-ttu-id="f5776-329">Classement</span><span class="sxs-lookup"><span data-stu-id="f5776-329">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="f5776-330">Ventes</span><span class="sxs-lookup"><span data-stu-id="f5776-330">Sales</span></span>    |<span data-ttu-id="f5776-331">Politique de vente</span><span class="sxs-lookup"><span data-stu-id="f5776-331">Sales policy</span></span>       | <span data-ttu-id="f5776-332">1</span><span class="sxs-lookup"><span data-stu-id="f5776-332">1</span></span>        |
|<span data-ttu-id="f5776-333">Région ouest</span><span class="sxs-lookup"><span data-stu-id="f5776-333">West Region</span></span>     |<span data-ttu-id="f5776-334">Politique de la région ouest</span><span class="sxs-lookup"><span data-stu-id="f5776-334">West Region policy</span></span>         |<span data-ttu-id="f5776-335">2</span><span class="sxs-lookup"><span data-stu-id="f5776-335">2</span></span>         |
|<span data-ttu-id="f5776-336">Division</span><span class="sxs-lookup"><span data-stu-id="f5776-336">Division</span></span>    |<span data-ttu-id="f5776-337">Politique de division</span><span class="sxs-lookup"><span data-stu-id="f5776-337">Division policy</span></span>         |<span data-ttu-id="f5776-338">3</span><span class="sxs-lookup"><span data-stu-id="f5776-338">3</span></span>         |
|<span data-ttu-id="f5776-339">Complémentaire</span><span class="sxs-lookup"><span data-stu-id="f5776-339">Subsidiary</span></span>   |<span data-ttu-id="f5776-340">Politique subsidiaire</span><span class="sxs-lookup"><span data-stu-id="f5776-340">Subsidiary policy</span></span>        |<span data-ttu-id="f5776-341">4</span><span class="sxs-lookup"><span data-stu-id="f5776-341">4</span></span>         |

<span data-ttu-id="f5776-342">Si nous supprimons la politique de la région ouest du groupe région ouest, les affectations et les priorités de la stratégie sont mises à jour comme suit.</span><span class="sxs-lookup"><span data-stu-id="f5776-342">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="f5776-343">Nom du groupe</span><span class="sxs-lookup"><span data-stu-id="f5776-343">Group name</span></span>  |<span data-ttu-id="f5776-344">Nom de la stratégie</span><span class="sxs-lookup"><span data-stu-id="f5776-344">Policy name</span></span>  |<span data-ttu-id="f5776-345">Classement</span><span class="sxs-lookup"><span data-stu-id="f5776-345">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="f5776-346">Ventes</span><span class="sxs-lookup"><span data-stu-id="f5776-346">Sales</span></span>    |<span data-ttu-id="f5776-347">Politique de vente</span><span class="sxs-lookup"><span data-stu-id="f5776-347">Sales policy</span></span>       | <span data-ttu-id="f5776-348">1</span><span class="sxs-lookup"><span data-stu-id="f5776-348">1</span></span>        |
|<span data-ttu-id="f5776-349">Division</span><span class="sxs-lookup"><span data-stu-id="f5776-349">Division</span></span>    |<span data-ttu-id="f5776-350">Politique de division</span><span class="sxs-lookup"><span data-stu-id="f5776-350">Division policy</span></span>         |<span data-ttu-id="f5776-351">2</span><span class="sxs-lookup"><span data-stu-id="f5776-351">2</span></span>         |
|<span data-ttu-id="f5776-352">Complémentaire</span><span class="sxs-lookup"><span data-stu-id="f5776-352">Subsidiary</span></span>   |<span data-ttu-id="f5776-353">Politique subsidiaire</span><span class="sxs-lookup"><span data-stu-id="f5776-353">Subsidiary policy</span></span>        |<span data-ttu-id="f5776-354">3</span><span class="sxs-lookup"><span data-stu-id="f5776-354">3</span></span>        |

<span data-ttu-id="f5776-355">Dans cet exemple, nous supprimons la stratégie de réunion teams d’un groupe.</span><span class="sxs-lookup"><span data-stu-id="f5776-355">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

<span data-ttu-id="f5776-356">Pour en savoir plus, consultez la rubrique [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="f5776-356">To learn more, see [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span></span>

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="f5776-357">Modifier une affectation de stratégie pour un groupe</span><span class="sxs-lookup"><span data-stu-id="f5776-357">Change a policy assignment for a group</span></span>

<span data-ttu-id="f5776-358">Après avoir affecté une stratégie à un groupe, vous pouvez utiliser l' ```Set-CsGroupPolicyAssignment``` applet de cmdlet pour modifier l’affectation de stratégie de ce groupe comme suit :</span><span class="sxs-lookup"><span data-stu-id="f5776-358">After you assign a policy to a group, you can use the ```Set-CsGroupPolicyAssignment``` cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="f5776-359">Changer le classement</span><span class="sxs-lookup"><span data-stu-id="f5776-359">Change the ranking</span></span>
- <span data-ttu-id="f5776-360">Modifier la stratégie d’un type de stratégie donné</span><span class="sxs-lookup"><span data-stu-id="f5776-360">Change the policy of a given policy type</span></span>
- <span data-ttu-id="f5776-361">Modification de la stratégie d’un type de stratégie donné et du classement</span><span class="sxs-lookup"><span data-stu-id="f5776-361">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="f5776-362">Dans cet exemple, nous affectons à la stratégie de parc d’appels de groupe une stratégie nommée SupportCallPark et le classement de l’affectation à 3.</span><span class="sxs-lookup"><span data-stu-id="f5776-362">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

<span data-ttu-id="f5776-363">Pour en savoir plus, consultez la rubrique [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="f5776-363">To learn more, see [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span></span>

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="f5776-364">Modification de la stratégie d’effectivité d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="f5776-364">Change the effective policy for a user</span></span>

<span data-ttu-id="f5776-365">Voici un exemple illustrant la modification de la stratégie d’effectivité d’un utilisateur qui a directement affecté une stratégie.</span><span class="sxs-lookup"><span data-stu-id="f5776-365">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="f5776-366">Tout d’abord, nous utilisons l’applet de connexion ```Get-CsUserPolicyAssignment``` conjointement avec le ```PolicySource``` paramètre pour obtenir des informations sur les stratégies de diffusion de réunion associées à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f5776-366">First, we use the ```Get-CsUserPolicyAssignment``` cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> <span data-ttu-id="f5776-367">Pour en savoir plus, consultez la rubrique [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="f5776-367">To learn more, see [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="f5776-368">La sortie montre que l’utilisateur a été directement affecté à une stratégie de diffusion de réunion teams nommée événements de l’employé, qui est prioritaire sur la stratégie nommée événements dynamiques du fournisseur qui est affectée à un groupe auquel l’utilisateur appartient.</span><span class="sxs-lookup"><span data-stu-id="f5776-368">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="f5776-369">À présent, nous supprimons la stratégie d’événements des employés de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f5776-369">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="f5776-370">Cela signifie que l’utilisateur ne dispose plus d’une stratégie de diffusion de réunion teams et qu’il hérite de la stratégie d’événements en direct du fournisseur qui est affectée au groupe auquel l’utilisateur appartient.</span><span class="sxs-lookup"><span data-stu-id="f5776-370">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="f5776-371">Utilisez l’applet de commande suivante dans le module PowerShell Skype entreprise pour effectuer cette opération.</span><span class="sxs-lookup"><span data-stu-id="f5776-371">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="f5776-372">Pour ce faire, vous pouvez utiliser l’applet de commande suivante dans le module PowerShell teams pour procéder à la mise à niveau en utilisant une affectation de stratégie de lot dans laquelle $users est une liste d’utilisateurs que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="f5776-372">You can use following cmdlet in the Teams Powershell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="f5776-373">Affectation d’un package de stratégie à un lot d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="f5776-373">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="f5776-374">Avec une affectation de package de stratégie de lot, vous pouvez attribuer un package de stratégie à un grand nombre d’utilisateurs à la fois sans avoir à utiliser de script.</span><span class="sxs-lookup"><span data-stu-id="f5776-374">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="f5776-375">Utilisez l' ```New-CsBatchPolicyPackageAssignmentOperation``` applet de commande pour transmettre un lot d’utilisateurs et le package de stratégie que vous voulez affecter.</span><span class="sxs-lookup"><span data-stu-id="f5776-375">You use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="f5776-376">Les affectations sont traitées en tant qu’opérations en arrière-plan et chaque lot est généré.</span><span class="sxs-lookup"><span data-stu-id="f5776-376">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="f5776-377">Vous pouvez ensuite utiliser l' ```Get-CsBatchPolicyAssignmentOperation``` applet de commande pour effectuer le suivi de l’avancement et de l’état des devoirs d’un lot.</span><span class="sxs-lookup"><span data-stu-id="f5776-377">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="f5776-378">Vous pouvez spécifier des utilisateurs en fonction de leur ID d’objet ou de leur adresse SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="f5776-378">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="f5776-379">Notez que le nom d’utilisateur principal (UPN) ou l’adresse de messagerie de l’utilisateur a souvent la même valeur que le nom d’utilisateur principal (UPN) ou l’adresse de messagerie, mais cela n’est pas obligatoire.</span><span class="sxs-lookup"><span data-stu-id="f5776-379">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="f5776-380">Si un utilisateur est spécifié à l’aide de son nom d’utilisateur principal ou de son adresse de messagerie, mais qu’il a une valeur différente de son adresse SIP, l’affectation de stratégie échouera pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f5776-380">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="f5776-381">Si un lot inclut des utilisateurs en double, les doublons seront supprimés du lot avant traitement et le statut ne sera fourni qu’aux utilisateurs uniques figurant dans le lot.</span><span class="sxs-lookup"><span data-stu-id="f5776-381">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="f5776-382">Un lot peut contenir jusqu’à 5 000 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f5776-382">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="f5776-383">Pour obtenir de meilleurs résultats, n’envoyez pas plus de quelques lots à la fois.</span><span class="sxs-lookup"><span data-stu-id="f5776-383">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="f5776-384">Autorisez le traitement des lots avant de soumettre d’autres lots.</span><span class="sxs-lookup"><span data-stu-id="f5776-384">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="f5776-385">Installer le module Microsoft teams PowerShell et s’y connecter</span><span class="sxs-lookup"><span data-stu-id="f5776-385">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="f5776-386">Exécutez la commande suivante pour installer le [module Microsoft teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (si vous ne l’avez pas déjà fait).</span><span class="sxs-lookup"><span data-stu-id="f5776-386">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="f5776-387">Vérifiez que vous avez installé la version 1.0.5 ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="f5776-387">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="f5776-388">Exécutez la commande suivante pour vous connecter à teams et démarrer une session.</span><span class="sxs-lookup"><span data-stu-id="f5776-388">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="f5776-389">Lorsque vous y êtes invité, connectez-vous à l’aide de vos informations d’identification d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="f5776-389">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="f5776-390">Affectation d’un package de stratégie à un lot d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="f5776-390">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="f5776-391">Dans cet exemple, nous utilisons l' ```New-CsBatchPolicyPackageAssignmentOperation``` applet de commande pour affecter le package de stratégie de Education_PrimaryStudent à un lot d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f5776-391">In this example, we use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

<span data-ttu-id="f5776-392">Pour en savoir plus, voir [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="f5776-392">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="f5776-393">Obtenir l’état d’une affectation par lot</span><span class="sxs-lookup"><span data-stu-id="f5776-393">Get the status of a batch assignment</span></span>

<span data-ttu-id="f5776-394">Exécutez la commande suivante pour obtenir l’état d’une affectation de lot, où OperationId est l’ID d’opération renvoyé par l' ```New-CsBatchPolicyAssignmentOperation``` applet de commande pour un lot donné.</span><span class="sxs-lookup"><span data-stu-id="f5776-394">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="f5776-395">Si la sortie indique qu’une erreur s’est produite, exécutez la commande suivante pour obtenir plus d’informations sur les erreurs qui se trouvent dans la ```UserState``` propriété.</span><span class="sxs-lookup"><span data-stu-id="f5776-395">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="f5776-396">Pour en savoir plus, consultez la rubrique [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="f5776-396">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="f5776-397">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="f5776-397">Related topics</span></span>

[<span data-ttu-id="f5776-398">Aperçu de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5776-398">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
