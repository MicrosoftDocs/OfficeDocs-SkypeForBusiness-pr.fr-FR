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
ms.openlocfilehash: ae007641734b71a34d9021283704d6b210626a28
ms.sourcegitcommit: 86b0956680b867b8bedb2e969220b8006829ee53
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/28/2020
ms.locfileid: "44410459"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="256ec-103">Attribuer des stratégies à vos utilisateurs dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="256ec-103">Assign policies to your users in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="256ec-104">**L’une des fonctionnalités de Microsoft teams abordées dans cet article, [affectation de stratégie à des groupes](#assign-a-policy-to-a-group), n’est actuellement disponible que dans la version préliminaire privée. Les applets de connexion PowerShell de cette fonctionnalité se trouvent dans le module pre-version PowerShell Teams.**</span><span class="sxs-lookup"><span data-stu-id="256ec-104">**One of the Microsoft Teams features discussed in this article, [policy assignment to groups](#assign-a-policy-to-a-group), is currently only available in private preview. The Powershell cmdlets for this feature are in the pre-release Teams PowerShell module.**</span></span> <span data-ttu-id="256ec-105">Pour en savoir plus sur l’état de publication de cette fonctionnalité, consultez la [documentation Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185).</span><span class="sxs-lookup"><span data-stu-id="256ec-105">To stay on top of the release status of this feature, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185).</span></span>

<span data-ttu-id="256ec-106">En tant qu’administrateur, vous utilisez des stratégies pour contrôler les fonctionnalités d’équipes disponibles pour les utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="256ec-106">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="256ec-107">Par exemple, il existe des stratégies d’appel, des stratégies de réunion et des stratégies de messagerie pour n’appeler qu’un seul nom.</span><span class="sxs-lookup"><span data-stu-id="256ec-107">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="256ec-108">Les organisations ont différents types d’utilisateurs dotés de besoins uniques et de stratégies personnalisées que vous créez et attribuez les paramètres de stratégie à différents ensembles d’utilisateurs en fonction de vos besoins.</span><span class="sxs-lookup"><span data-stu-id="256ec-108">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="256ec-109">Pour faciliter la gestion des stratégies au sein de votre organisation, teams permet d’attribuer des stratégies aux utilisateurs de différentes manières.</span><span class="sxs-lookup"><span data-stu-id="256ec-109">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="256ec-110">Vous pouvez affecter une stratégie directement aux utilisateurs, individuellement ou à l’échelle via une affectation de lot ou à un groupe dont l’utilisateur est membre.</span><span class="sxs-lookup"><span data-stu-id="256ec-110">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the user is a member of.</span></span> <span data-ttu-id="256ec-111">Vous pouvez également utiliser des packages de stratégie pour affecter une collection prédéfinie de stratégies aux utilisateurs de votre organisation possédant des rôles similaires.</span><span class="sxs-lookup"><span data-stu-id="256ec-111">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="256ec-112">L’option que vous choisissez dépend du nombre de stratégies que vous gérez et du nombre d’utilisateurs auxquels vous attribuez.</span><span class="sxs-lookup"><span data-stu-id="256ec-112">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span>

<span data-ttu-id="256ec-113">Cet article décrit les différentes façons dont vous pouvez attribuer des stratégies aux utilisateurs et les scénarios recommandés pour les situations dans lesquelles utiliser.</span><span class="sxs-lookup"><span data-stu-id="256ec-113">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="256ec-114">Quelle est la stratégie prioritaire ?</span><span class="sxs-lookup"><span data-stu-id="256ec-114">Which policy takes precedence?</span></span>

<span data-ttu-id="256ec-115">Un utilisateur dispose d’une stratégie efficace pour chaque type de stratégie.</span><span class="sxs-lookup"><span data-stu-id="256ec-115">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="256ec-116">Il est possible, ou même probable, que l’utilisateur dispose d’une stratégie directement affectée et qu’il soit membre d’un ou plusieurs groupes auxquels une stratégie du même type est affectée.</span><span class="sxs-lookup"><span data-stu-id="256ec-116">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="256ec-117">Dans ces types de scénarios, quelle stratégie est prioritaire ?</span><span class="sxs-lookup"><span data-stu-id="256ec-117">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="256ec-118">La stratégie d’effectivité d’un utilisateur est déterminée conformément aux règles de priorité, comme suit.</span><span class="sxs-lookup"><span data-stu-id="256ec-118">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="256ec-119">Si un utilisateur dispose d’une stratégie (individuelle ou par le biais d’une affectation de lot), cette stratégie est prioritaire.</span><span class="sxs-lookup"><span data-stu-id="256ec-119">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="256ec-120">Dans l’exemple suivant, la stratégie effective de l’utilisateur est la stratégie de réunion carrée d’Lincoln, qui est directement affectée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="256ec-120">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![Diagramme montrant comment une stratégie attribuée directement est prioritaire](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="256ec-122">Si un utilisateur n’a pas directement affecté une stratégie d’un type donné, la stratégie affectée à un groupe dont l’utilisateur est membre de a la priorité.</span><span class="sxs-lookup"><span data-stu-id="256ec-122">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="256ec-123">Si un utilisateur est membre de plusieurs groupes, la stratégie présentant le niveau de [classement des affectations de groupe](#group-assignment-ranking) le plus élevé pour le type de stratégie donné est prioritaire.</span><span class="sxs-lookup"><span data-stu-id="256ec-123">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="256ec-124">Dans cet exemple, la stratégie effective de l’utilisateur est la stratégie d’exécution et la stratégie HD, qui présente le niveau d’attribution le plus élevé par rapport aux autres groupes dont l’utilisateur est membre et auquel une stratégie du même type de stratégie est affectée.</span><span class="sxs-lookup"><span data-stu-id="256ec-124">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![Diagramme montrant comment une stratégie héritée du groupe est prioritaire](media/assign-policies-example-group.png)

<span data-ttu-id="256ec-126">Si un utilisateur n’est pas directement affecté à une stratégie ou n’est pas membre de tous les groupes auxquels une stratégie est affectée, l’utilisateur obtient la stratégie globale (par défaut de l’organisation par défaut) pour ce type de stratégie.</span><span class="sxs-lookup"><span data-stu-id="256ec-126">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="256ec-127">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="256ec-127">Here's an example.</span></span>

![Diagramme illustrant le niveau de priorité d’une stratégie globale](media/assign-policies-example-global.png)

<span data-ttu-id="256ec-129">Pour en savoir plus, voir [règles de précédence](#precedence-rules).</span><span class="sxs-lookup"><span data-stu-id="256ec-129">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="256ec-130">Méthodes d’attribution de stratégies</span><span class="sxs-lookup"><span data-stu-id="256ec-130">Ways to assign policies</span></span>

<span data-ttu-id="256ec-131">Vous trouverez ci-dessous une vue d’ensemble des méthodes permettant d’attribuer des stratégies aux utilisateurs et les scénarios recommandés pour chacun.</span><span class="sxs-lookup"><span data-stu-id="256ec-131">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="256ec-132">Cliquez sur les liens pour en savoir plus.</span><span class="sxs-lookup"><span data-stu-id="256ec-132">Click the links to learn more.</span></span>

|<span data-ttu-id="256ec-133">Procédez comme suit…</span><span class="sxs-lookup"><span data-stu-id="256ec-133">Do this</span></span>  |<span data-ttu-id="256ec-134">Si...</span><span class="sxs-lookup"><span data-stu-id="256ec-134">If...</span></span>  | <span data-ttu-id="256ec-135">Utilisation de...</span><span class="sxs-lookup"><span data-stu-id="256ec-135">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="256ec-136">Assigner une stratégie à des utilisateurs individuels</span><span class="sxs-lookup"><span data-stu-id="256ec-136">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="256ec-137">Vous débutez en équipe et vous commencez simplement à attribuer une ou plusieurs stratégies à un petit nombre d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="256ec-137">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="256ec-138">Centre d’administration Microsoft teams ou cmdlets PowerShell dans le module PowerShell de Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="256ec-138">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
| [<span data-ttu-id="256ec-139">Assigner un package de stratégie</span><span class="sxs-lookup"><span data-stu-id="256ec-139">Assign a policy package</span></span>](#assign-a-policy-package)   | <span data-ttu-id="256ec-140">Vous devez affecter plusieurs stratégies à des ensembles d’utilisateurs spécifiques de votre organisation qui ont des rôles identiques ou similaires.</span><span class="sxs-lookup"><span data-stu-id="256ec-140">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="256ec-141">Par exemple, attribuez le package de stratégie éducation (enseignant) aux enseignants de votre établissement scolaire pour leur permettre d’accéder à l’ensemble des conversations, appels et réunions, ainsi que le package d’étude (étudiant d’école secondaire) aux étudiants secondaires pour limiter certaines fonctionnalités, telles que les appels privés.</span><span class="sxs-lookup"><span data-stu-id="256ec-141">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="256ec-142">Centre d’administration Microsoft teams ou cmdlets PowerShell dans le module PowerShell teams</span><span class="sxs-lookup"><span data-stu-id="256ec-142">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="256ec-143">Attribuer une stratégie à un lot d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="256ec-143">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="256ec-144">Vous devez attribuer des stratégies à d’importants ensembles d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="256ec-144">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="256ec-145">Par exemple, vous pouvez attribuer une stratégie à des centaines ou des milliers d’utilisateurs de votre organisation à la fois.</span><span class="sxs-lookup"><span data-stu-id="256ec-145">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="256ec-146">Centre d’administration Microsoft teams ou cmdlets PowerShell dans le module PowerShell teams</span><span class="sxs-lookup"><span data-stu-id="256ec-146">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|<span data-ttu-id="256ec-147">[Assigner une stratégie à un groupe](#assign-a-policy-to-a-group) (en Preview)</span><span class="sxs-lookup"><span data-stu-id="256ec-147">[Assign a policy to a group](#assign-a-policy-to-a-group) (in preview)</span></span>   |<span data-ttu-id="256ec-148">Vous devez attribuer des stratégies en fonction de l’appartenance d’un utilisateur à un groupe.</span><span class="sxs-lookup"><span data-stu-id="256ec-148">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="256ec-149">Par exemple, vous souhaitez attribuer une stratégie à l’ensemble des utilisateurs d’un groupe de sécurité ou d’une unité d’organisation.</span><span class="sxs-lookup"><span data-stu-id="256ec-149">For example, you want to assign a policy to all users in a security group or organizational unit.</span></span>| <span data-ttu-id="256ec-150">Cmdlets PowerShell dans le module PowerShell teams</span><span class="sxs-lookup"><span data-stu-id="256ec-150">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="256ec-151">Affectation d’un package de stratégie à un lot d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="256ec-151">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="256ec-152">Vous devez affecter plusieurs stratégies à un lot d’utilisateurs de votre organisation qui ont des rôles identiques ou similaires.</span><span class="sxs-lookup"><span data-stu-id="256ec-152">You need to assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="256ec-153">Par exemple, attribuez le package de stratégie éducation (enseignant) à tous les enseignants de votre établissement scolaire à l’aide de la fonctionnalité d’attribution de lot pour leur permettre d’accéder à des conversations, des appels et des réunions, et d’affecter le package de stratégie éducation (école secondaire) à un lot d’étudiants secondaires pour limiter certaines fonctionnalités telles que les appels privés.</span><span class="sxs-lookup"><span data-stu-id="256ec-153">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings and assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities like private calling.</span></span>|<span data-ttu-id="256ec-154">Cmdlets PowerShell dans le module PowerShell teams</span><span class="sxs-lookup"><span data-stu-id="256ec-154">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="256ec-155">Assigner un package de stratégie à un groupe (bientôt disponible)</span><span class="sxs-lookup"><span data-stu-id="256ec-155">Assign a policy package to a group (coming soon)</span></span>   | ||

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="256ec-156">Assigner une stratégie à des utilisateurs individuels</span><span class="sxs-lookup"><span data-stu-id="256ec-156">Assign a policy to individual users</span></span>

<span data-ttu-id="256ec-157">Procédez comme suit pour attribuer une stratégie à un utilisateur individuel ou à un petit nombre d’utilisateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="256ec-157">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="256ec-158">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="256ec-158">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="256ec-159">Pour attribuer une stratégie à un utilisateur :</span><span class="sxs-lookup"><span data-stu-id="256ec-159">To assign a policy to a user:</span></span>

1. <span data-ttu-id="256ec-160">Dans le volet de navigation gauche du centre d’administration Microsoft Teams, et accédez aux **Utilisateurs**, puis cliquez sur l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="256ec-160">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="256ec-161">Sélectionnez l’utilisateur en cliquant à gauche du nom de celui-ci, puis cliquez sur **Modifier les paramètres**.</span><span class="sxs-lookup"><span data-stu-id="256ec-161">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="256ec-162">Sélectionnez la stratégie que vous voulez attribuer, puis cliquez sur **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="256ec-162">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="256ec-163">Vous pouvez également effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="256ec-163">Or, you can also do the following:</span></span>

1. <span data-ttu-id="256ec-164">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à la page de stratégie.</span><span class="sxs-lookup"><span data-stu-id="256ec-164">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="256ec-165">Sélectionnez la stratégie que vous voulez affecter en cliquant à gauche du nom de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="256ec-165">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="256ec-166">Sélectionnez **Gérer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="256ec-166">Select **Manage users**.</span></span>
4. <span data-ttu-id="256ec-167">Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="256ec-167">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="256ec-168">Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="256ec-168">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="256ec-169">Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="256ec-169">When you're finished adding users, select **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="256ec-170">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="256ec-170">Using PowerShell</span></span>

<span data-ttu-id="256ec-171">Chacun d’eux dispose d’un ensemble de cmdlets pour le gérer.</span><span class="sxs-lookup"><span data-stu-id="256ec-171">Each policy type has it's own set of cmdlets for managing it.</span></span> <span data-ttu-id="256ec-172">Utilisez l' ```Grant-``` applet de cmdlet d’un type de stratégie donné pour affecter la stratégie.</span><span class="sxs-lookup"><span data-stu-id="256ec-172">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="256ec-173">Par exemple, utilisez l' ```Grant-CsTeamsMeetingPolicy``` applet de cmdlet pour attribuer une stratégie de réunion teams à des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="256ec-173">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="256ec-174">Ces applets de service sont inclus dans le module PowerShell de Skype entreprise Online et sont décrits dans la référence de l’applet de connexion [Skype entreprise](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="256ec-174">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="256ec-175">Téléchargez et installez le [module PowerShell de Skype entreprise Online](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (si vous ne l’avez pas déjà fait), puis exécutez la commande suivante pour vous connecter à Skype entreprise Online et commencer une session.</span><span class="sxs-lookup"><span data-stu-id="256ec-175">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="256ec-176">Dans cet exemple, nous affectons une stratégie de réunion teams nommée Stratégie de réunion étudiant à un utilisateur nommé reda.</span><span class="sxs-lookup"><span data-stu-id="256ec-176">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="256ec-177">Pour en savoir plus, voir [gestion des stratégies via PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span><span class="sxs-lookup"><span data-stu-id="256ec-177">To learn more, see [Managing policies via PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span></span>

## <a name="assign-a-policy-package"></a><span data-ttu-id="256ec-178">Assigner un package de stratégie</span><span class="sxs-lookup"><span data-stu-id="256ec-178">Assign a policy package</span></span>

<span data-ttu-id="256ec-179">Un package de stratégie dans teams est un ensemble de stratégies et de paramètres de stratégie prédéfinis que vous pouvez affecter aux utilisateurs qui ont des rôles similaires ou similaires au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="256ec-179">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="256ec-180">Chaque package de stratégie est conçu à l’aide d’un rôle d’utilisateur et comprend des stratégies et des paramètres de stratégie prédéfinis qui prennent en charge les activités typiques pour ce rôle.</span><span class="sxs-lookup"><span data-stu-id="256ec-180">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="256ec-181">Voici quelques exemples de packages de stratégie : le package éducation (enseignant) et le module Healthcare (Medical Worker).</span><span class="sxs-lookup"><span data-stu-id="256ec-181">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span>

<span data-ttu-id="256ec-182">Lorsque vous attribuez un package de stratégie aux utilisateurs, les stratégies du package sont créées et vous pouvez personnaliser les paramètres de chaque stratégie du package pour répondre aux besoins des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="256ec-182">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of each policy in the package to meet users' needs.</span></span>

<span data-ttu-id="256ec-183">Pour en savoir plus sur les packages de stratégie, y compris des instructions détaillées sur la manière de les affecter et de les gérer, voir [gérer les packages de stratégie dans teams](manage-policy-packages.md).</span><span class="sxs-lookup"><span data-stu-id="256ec-183">To learn more about policy packages, including step-by-step guidance on how to assign and manage them, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="256ec-184">Attribuer une stratégie à un lot d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="256ec-184">Assign a policy to a batch of users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="256ec-185">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="256ec-185">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="256ec-186">Pour attribuer une stratégie aux utilisateurs en bloc :</span><span class="sxs-lookup"><span data-stu-id="256ec-186">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="256ec-187">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, sélectionnez **utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="256ec-187">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="256ec-188">Recherchez les utilisateurs auxquels vous voulez affecter la stratégie ou filtrez l’affichage pour afficher les utilisateurs souhaités.</span><span class="sxs-lookup"><span data-stu-id="256ec-188">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="256ec-189">Dans la colonne **&#x2713;** (coche), sélectionnez les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="256ec-189">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="256ec-190">Pour sélectionner tous les utilisateurs, cliquez sur &#x2713; (coche) en haut du tableau.</span><span class="sxs-lookup"><span data-stu-id="256ec-190">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="256ec-191">Cliquez sur **Modifier les paramètres**, apportez les modifications souhaitées, puis cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="256ec-191">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="256ec-192">Pour afficher l’état de votre affectation de stratégie, dans la bannière qui s’affiche en haut de la page **utilisateurs** après avoir cliqué sur **appliquer** pour valider votre affectation de stratégie, cliquez sur **Journal d’activité**.</span><span class="sxs-lookup"><span data-stu-id="256ec-192">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you click **Apply** to submit your policy assignment, click **Activity log**.</span></span> <span data-ttu-id="256ec-193">Ou, dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez au **tableau de bord**, puis sous **Journal d’activité**, cliquez sur Afficher les **Détails**.</span><span class="sxs-lookup"><span data-stu-id="256ec-193">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, click **View details**.</span></span> <span data-ttu-id="256ec-194">Le journal d’activité affiche les affectations de stratégie aux lots de plus de 20 utilisateurs par le biais du centre d’administration Microsoft teams depuis les 30 derniers jours.</span><span class="sxs-lookup"><span data-stu-id="256ec-194">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="256ec-195">Pour en savoir plus, voir [afficher les affectations de stratégie dans le journal d’activité](activity-log.md).</span><span class="sxs-lookup"><span data-stu-id="256ec-195">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="256ec-196">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="256ec-196">Using PowerShell</span></span>
 
<span data-ttu-id="256ec-197">Avec une affectation de stratégie de lot, vous pouvez attribuer une stratégie à un grand nombre d’utilisateurs à la fois sans avoir à utiliser de script.</span><span class="sxs-lookup"><span data-stu-id="256ec-197">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="256ec-198">Utilisez l' ```New-CsBatchPolicyAssignmentOperationd``` applet de commande pour signaler un lot d’utilisateurs et la stratégie que vous voulez affecter.</span><span class="sxs-lookup"><span data-stu-id="256ec-198">You use the ```New-CsBatchPolicyAssignmentOperationd``` cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="256ec-199">Les affectations sont traitées en tant qu’opérations en arrière-plan et chaque lot est généré.</span><span class="sxs-lookup"><span data-stu-id="256ec-199">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="256ec-200">Vous pouvez ensuite utiliser l' ```Get-CsBatchPolicyAssignmentOperation``` applet de commande pour effectuer le suivi de l’avancement et de l’état des devoirs d’un lot.</span><span class="sxs-lookup"><span data-stu-id="256ec-200">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span> 

<span data-ttu-id="256ec-201">Vous pouvez spécifier des utilisateurs selon leur ID d’objet, leur nom d’utilisateur principal (UPN), leur adresse SIP (Session Initiation Protocol) ou leur adresse de messagerie.</span><span class="sxs-lookup"><span data-stu-id="256ec-201">You can specify users by their object Id, user principal name (UPN), Session Initiation Protocol (SIP) address, or email address.</span></span> <span data-ttu-id="256ec-202">Si un lot inclut des utilisateurs en double, les doublons seront supprimés du lot avant traitement et le statut ne sera fourni qu’aux utilisateurs uniques figurant dans le lot.</span><span class="sxs-lookup"><span data-stu-id="256ec-202">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="256ec-203">Un lot peut contenir jusqu’à 5 000 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="256ec-203">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="256ec-204">Pour obtenir de meilleurs résultats, n’envoyez pas plus de quelques lots à la fois.</span><span class="sxs-lookup"><span data-stu-id="256ec-204">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="256ec-205">Autorisez le traitement des lots avant de soumettre d’autres lots.</span><span class="sxs-lookup"><span data-stu-id="256ec-205">Allow batches to complete processing before submitting more batches.</span></span>

> [!NOTE]
> <span data-ttu-id="256ec-206">Pour l’instant, l’affectation de stratégie de lot n’est pas disponible pour tous les types de stratégies d’équipe.</span><span class="sxs-lookup"><span data-stu-id="256ec-206">Currently, batch policy assignment isn't available for all Teams policy types.</span></span> <span data-ttu-id="256ec-207">Pour obtenir la liste des types de stratégie pris en charge, voir [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) .</span><span class="sxs-lookup"><span data-stu-id="256ec-207">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="256ec-208">Installer le module Microsoft teams PowerShell et s’y connecter</span><span class="sxs-lookup"><span data-stu-id="256ec-208">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="256ec-209">Exécutez la commande suivante pour installer le [module Microsoft teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams).</span><span class="sxs-lookup"><span data-stu-id="256ec-209">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="256ec-210">Vérifiez que vous avez installé la version 1.0.5 ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="256ec-210">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="256ec-211">Exécutez la commande suivante pour vous connecter à teams et démarrer une session.</span><span class="sxs-lookup"><span data-stu-id="256ec-211">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="256ec-212">Lorsque vous y êtes invité, connectez-vous à l’aide de vos informations d’identification d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="256ec-212">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="256ec-213">Installez et connectez-vous à Azure AD PowerShell pour le module Graph (facultatif)</span><span class="sxs-lookup"><span data-stu-id="256ec-213">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="256ec-214">Vous pouvez également [Télécharger et installer le module Azure ad PowerShell pour Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (le cas échéant) et vous connecter à Azure AD pour récupérer la liste des utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="256ec-214">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="256ec-215">Exécutez la commande suivante pour vous connecter à Azure AD.</span><span class="sxs-lookup"><span data-stu-id="256ec-215">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="256ec-216">Lorsque vous y êtes invité, connectez-vous à l’aide des informations d’identification d’administrateur que vous avez utilisées pour vous connecter à Teams.</span><span class="sxs-lookup"><span data-stu-id="256ec-216">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="256ec-217">Attribuer une stratégie à un lot d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="256ec-217">Assign a policy to a batch of users</span></span>

<span data-ttu-id="256ec-218">Dans cet exemple, nous utilisons l' ```New-CsBatchPolicyAssignmentOperation``` applet de commande pour assigner une stratégie d’installation d’application nommée Stratégie de configuration des applications humaines à un lot d’utilisateurs répertoriés dans le fichier Users_ids. Text.</span><span class="sxs-lookup"><span data-stu-id="256ec-218">In this example, we use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="256ec-219">Dans cet exemple, nous allons nous connecter à Azure AD pour récupérer une collection d’utilisateurs, puis attribuer une stratégie d’échange nommée nouvelle stratégie de messagerie à un lot d’utilisateurs spécifiés à l’aide de leur UPN.</span><span class="sxs-lookup"><span data-stu-id="256ec-219">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their UPNs.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.UserPrincipalName -OperationName "Example 2 batch"
```

<span data-ttu-id="256ec-220">Pour en savoir plus, voir [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="256ec-220">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="256ec-221">Obtenir l’état d’une affectation par lot</span><span class="sxs-lookup"><span data-stu-id="256ec-221">Get the status of a batch assignment</span></span>

<span data-ttu-id="256ec-222">Exécutez la commande suivante pour obtenir l’état d’une affectation de lot, où OperationId est l’ID d’opération renvoyé par l' ```New-CsBatchPolicyAssignmentOperation``` applet de commande pour un lot donné.</span><span class="sxs-lookup"><span data-stu-id="256ec-222">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="256ec-223">Si la sortie indique qu’une erreur s’est produite, exécutez la commande suivante pour obtenir plus d’informations sur les erreurs qui se trouvent dans la ```UserState``` propriété.</span><span class="sxs-lookup"><span data-stu-id="256ec-223">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="256ec-224">Pour en savoir plus, consultez la rubrique [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="256ec-224">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="256ec-225">Assigner une stratégie à un groupe</span><span class="sxs-lookup"><span data-stu-id="256ec-225">Assign a policy to a group</span></span>

<span data-ttu-id="256ec-226">**Pour l’instant, l’attribution de la stratégie aux groupes est uniquement disponible en version préliminaire privée. Les applets de fonction de cette fonctionnalité se trouvent dans le module pre-version PowerShell Teams.**</span><span class="sxs-lookup"><span data-stu-id="256ec-226">**Policy assignment to groups is currently only available in private preview. The cmdlets for this feature are in the pre-release Teams PowerShell module.**</span></span>

<span data-ttu-id="256ec-227">Attribution de stratégie aux groupes vous permet d’affecter une stratégie à un groupe d’utilisateurs, tel qu’un groupe de sécurité ou une unité d’organisation.</span><span class="sxs-lookup"><span data-stu-id="256ec-227">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or organizational unit.</span></span> <span data-ttu-id="256ec-228">L’affectation de stratégie est propagée aux membres du groupe conformément aux règles de priorité.</span><span class="sxs-lookup"><span data-stu-id="256ec-228">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="256ec-229">Les membres étant ajoutés ou supprimés d’un groupe, leurs affectations de stratégie héritées sont mises à jour en conséquence.</span><span class="sxs-lookup"><span data-stu-id="256ec-229">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="256ec-230">Vous pouvez utiliser l' ```New-CsGroupPolicyAssignment``` applet de cmdlet pour attribuer une stratégie à un groupe.</span><span class="sxs-lookup"><span data-stu-id="256ec-230">You use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="256ec-231">Vous pouvez spécifier un groupe à l’aide d’un ID d’objet, d’une adresse SIP ou d’une adresse de messagerie.</span><span class="sxs-lookup"><span data-stu-id="256ec-231">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="256ec-232">Lorsque vous affectez la stratégie, celle-ci est immédiatement affectée au groupe.</span><span class="sxs-lookup"><span data-stu-id="256ec-232">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="256ec-233">Toutefois, Notez que la propagation de l’affectation de stratégie aux membres du groupe est effectuée en tant qu’opération en arrière-plan et peut prendre un certain temps selon la taille du groupe.</span><span class="sxs-lookup"><span data-stu-id="256ec-233">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="256ec-234">Il en va de même lorsque la stratégie n’est pas attribuée à un groupe, ou lorsque les membres sont ajoutés à un groupe ou supprimés.</span><span class="sxs-lookup"><span data-stu-id="256ec-234">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!NOTE]
> <span data-ttu-id="256ec-235">Pour l’instant, l’affectation de stratégie à des groupes n’est pas disponible pour tous les types de stratégie d’équipe.</span><span class="sxs-lookup"><span data-stu-id="256ec-235">Currently, policy assignment to groups isn't available for all Teams policy types.</span></span> <span data-ttu-id="256ec-236">Pour obtenir la liste des types de stratégie pris en charge, voir [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) .</span><span class="sxs-lookup"><span data-stu-id="256ec-236">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="256ec-237">Ce que vous devez savoir sur l’attribution de stratégies aux groupes</span><span class="sxs-lookup"><span data-stu-id="256ec-237">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="256ec-238">Avant de commencer, il est important de comprendre les règles de précédence et le classement des affectations de groupe.</span><span class="sxs-lookup"><span data-stu-id="256ec-238">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="256ec-239">Règles de précédence</span><span class="sxs-lookup"><span data-stu-id="256ec-239">Precedence rules</span></span>

<span data-ttu-id="256ec-240">Pour un type de stratégie donné, la stratégie effective d’un utilisateur est déterminée conformément aux éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="256ec-240">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="256ec-241">Une stratégie attribuée directement à un utilisateur est prioritaire sur une autre stratégie du même type affectée à un groupe.</span><span class="sxs-lookup"><span data-stu-id="256ec-241">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="256ec-242">En d’autres termes, si un utilisateur reçoit directement une stratégie d’un type donné, il n’hérite pas d’une stratégie du même type d’un groupe.</span><span class="sxs-lookup"><span data-stu-id="256ec-242">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="256ec-243">En d’autres termes, si un utilisateur possède une stratégie d’un type donné qui lui a été directement affecté, vous devez supprimer cette stratégie de l’utilisateur pour pouvoir hériter d’une stratégie du même type d’un groupe.</span><span class="sxs-lookup"><span data-stu-id="256ec-243">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="256ec-244">Si un utilisateur ne dispose pas directement d’une stratégie et est membre de deux groupes ou plus, et qu’il dispose d’une stratégie du même type qui lui est affecté, il hérite de la stratégie du groupe affecté dont le classement est le plus élevé.</span><span class="sxs-lookup"><span data-stu-id="256ec-244">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="256ec-245">Si un utilisateur n’est pas membre de groupes auxquels une stratégie est affectée, la stratégie globale par défaut de l’Organisation pour ce type de stratégie s’applique à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="256ec-245">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="256ec-246">La stratégie effective d’un utilisateur est mise à jour en fonction de ces règles lorsqu’un utilisateur est ajouté ou supprimé d’un groupe auquel est affectée une stratégie, qu’une stratégie n’est pas attribuée à partir d’un groupe ou qu’une stratégie attribuée directement à l’utilisateur est supprimée.</span><span class="sxs-lookup"><span data-stu-id="256ec-246">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="256ec-247">Classement des affectations de groupe</span><span class="sxs-lookup"><span data-stu-id="256ec-247">Group assignment ranking</span></span>
 
<span data-ttu-id="256ec-248">Lorsque vous affectez une stratégie à un groupe, vous spécifiez le classement de l’affectation de groupe.</span><span class="sxs-lookup"><span data-stu-id="256ec-248">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="256ec-249">Il est utilisé pour identifier la stratégie qu’un utilisateur doit hériter en tant que stratégie effective si l’utilisateur est membre de deux groupes ou plus et qu’une stratégie du même type est affectée à chaque groupe.</span><span class="sxs-lookup"><span data-stu-id="256ec-249">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="256ec-250">Le classement des affectations de groupe est relatif par rapport à d’autres affectations de groupe du même type.</span><span class="sxs-lookup"><span data-stu-id="256ec-250">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="256ec-251">Par exemple, si vous attribuez une stratégie d’appel à deux groupes, définissez le classement d’une affectation sur 1 et l’autre sur 2, avec 1 en tant que classement le plus élevé.</span><span class="sxs-lookup"><span data-stu-id="256ec-251">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="256ec-252">Le classement des affectations de groupe indique l’appartenance au groupe qui est la plus importante ou la plus pertinente par rapport à d’autres appartenances aux groupes en ce qui concerne l’héritage.</span><span class="sxs-lookup"><span data-stu-id="256ec-252">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="256ec-253">Imaginons, par exemple, que vous avez deux groupes, que vous stockez des employés et des responsables du magasin.</span><span class="sxs-lookup"><span data-stu-id="256ec-253">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="256ec-254">Les deux groupes se voient attribuer une stratégie d’appel d’équipes, et les employés de la stratégie d’appel et de la stratégie d’appel des responsables de la boutique sont respectivement.</span><span class="sxs-lookup"><span data-stu-id="256ec-254">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="256ec-255">Dans le cas d’un responsable du Windows Store qui se trouve dans les deux groupes, son rôle en tant que responsable est supérieur à celui d’un employé, de sorte que la stratégie d’appel attribuée au groupe responsables du magasin doit présenter un niveau de classement supérieur.</span><span class="sxs-lookup"><span data-stu-id="256ec-255">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="256ec-256">Groupe</span><span class="sxs-lookup"><span data-stu-id="256ec-256">Group</span></span> |<span data-ttu-id="256ec-257">Nom de la stratégie d’appel teams</span><span class="sxs-lookup"><span data-stu-id="256ec-257">Teams calling policy name</span></span>  |<span data-ttu-id="256ec-258">Classement</span><span class="sxs-lookup"><span data-stu-id="256ec-258">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="256ec-259">Responsables du Windows Store</span><span class="sxs-lookup"><span data-stu-id="256ec-259">Store Managers</span></span>   |<span data-ttu-id="256ec-260">Stratégie d’appel des directeurs du Windows Store</span><span class="sxs-lookup"><span data-stu-id="256ec-260">Store Managers Calling Policy</span></span>         |<span data-ttu-id="256ec-261">1</span><span class="sxs-lookup"><span data-stu-id="256ec-261">1</span></span>|
|<span data-ttu-id="256ec-262">Magasin employés</span><span class="sxs-lookup"><span data-stu-id="256ec-262">Store Employees</span></span>    |<span data-ttu-id="256ec-263">Politique d’appel des employés du Store</span><span class="sxs-lookup"><span data-stu-id="256ec-263">Store Employees Calling Policy</span></span>      |<span data-ttu-id="256ec-264">2</span><span class="sxs-lookup"><span data-stu-id="256ec-264">2</span></span>|

<span data-ttu-id="256ec-265">Si vous ne spécifiez pas de classement, l’affectation de la stratégie est affectée du plus petit classement.</span><span class="sxs-lookup"><span data-stu-id="256ec-265">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="256ec-266">Installer le module Microsoft teams PowerShell et s’y connecter</span><span class="sxs-lookup"><span data-stu-id="256ec-266">Install and connect to the Microsoft Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="256ec-267">Les applets de contrôle se trouvent dans la version préliminaire du module PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="256ec-267">The cmdlets are in the pre-release version of the Teams PowerShell module.</span></span> <span data-ttu-id="256ec-268">Suivez ces étapes pour commencer par désinstaller la version disponible en général du module PowerShell Teams (s’il est installé), puis installez la dernière version préliminaire du module à partir de la Galerie de tests PowerShell.</span><span class="sxs-lookup"><span data-stu-id="256ec-268">Follow these steps to first uninstall the Generally Available version of the Teams PowerShell module (if it's installed), and then install the latest pre-release version of the module from the PowerShell Test Gallery.</span></span>

<span data-ttu-id="256ec-269">Si ce n’est déjà fait, exécutez la commande suivante pour inscrire la Galerie de tests PowerShell comme source fiable.</span><span class="sxs-lookup"><span data-stu-id="256ec-269">If you haven't already, run the following to register the PowerShell Test Gallery as a trusted source.</span></span>

```powershell
Register-PSRepository -SourceLocation https://www.poshtestgallery.com/api/v2 -Name PsTestGallery -InstallationPolicy Trusted
```

<span data-ttu-id="256ec-270">Si vous avez installé la version disponible en général du module PowerShell Teams, exécutez la commande suivante pour la désinstaller.</span><span class="sxs-lookup"><span data-stu-id="256ec-270">If you have the Generally Available version of the Teams PowerShell module installed, run the following to uninstall it.</span></span>

```powershell
Uninstall-Module MicrosoftTeams -AllVersions
```

<span data-ttu-id="256ec-271">Exécutez la commande suivante pour installer le module Microsoft teams PowerShell le plus récent à partir de la Galerie de tests PowerShell.</span><span class="sxs-lookup"><span data-stu-id="256ec-271">Run the following to install the latest Microsoft Teams PowerShell module from the PowerShell Test Gallery.</span></span>

```powershell
Install-Module MicrosoftTeams -Repository PSTestGallery
```

<span data-ttu-id="256ec-272">Exécutez la commande suivante pour vous connecter à teams et démarrer une session.</span><span class="sxs-lookup"><span data-stu-id="256ec-272">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="256ec-273">Lorsque vous y êtes invité, connectez-vous à l’aide de vos informations d’identification d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="256ec-273">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="256ec-274">Assigner une stratégie à un groupe</span><span class="sxs-lookup"><span data-stu-id="256ec-274">Assign a policy to a group</span></span>

<span data-ttu-id="256ec-275">Dans cet exemple, nous utilisons l' ```New-CsGroupPolicyAssignment``` applet de cmdlet pour assigner une stratégie de réunion équipes nommée Stratégie de réunion des responsables de revente à un groupe dont le classement de devoirs est 1.</span><span class="sxs-lookup"><span data-stu-id="256ec-275">In this example, we use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

<span data-ttu-id="256ec-276">Pour en savoir plus, voir [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="256ec-276">To learn more, see [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span></span>

### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="256ec-277">Obtenir des affectations de stratégie pour un groupe</span><span class="sxs-lookup"><span data-stu-id="256ec-277">Get policy assignments for a group</span></span>

<span data-ttu-id="256ec-278">Utilisez l' ```Get-CsGroupPolicyAssignment``` applet de cmdlet pour obtenir toutes les stratégies attribuées à un groupe.</span><span class="sxs-lookup"><span data-stu-id="256ec-278">Use the ```Get-CsGroupPolicyAssignment``` cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="256ec-279">Notez que les groupes sont toujours répertoriés par leur ID de groupe même si l’adresse ou l’adresse de messagerie SIP a été utilisée pour affecter la stratégie.</span><span class="sxs-lookup"><span data-stu-id="256ec-279">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="256ec-280">Dans cet exemple, nous récupérons toutes les stratégies affectées à un groupe spécifique.</span><span class="sxs-lookup"><span data-stu-id="256ec-280">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="256ec-281">Dans cet exemple, nous renvoyons tous les groupes auxquels une stratégie de réunion équipes est affectée.</span><span class="sxs-lookup"><span data-stu-id="256ec-281">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

<span data-ttu-id="256ec-282">Pour en savoir plus, consultez la rubrique [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="256ec-282">To learn more, see [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span></span>

### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="256ec-283">Supprimer une stratégie d’un groupe</span><span class="sxs-lookup"><span data-stu-id="256ec-283">Remove a policy from a group</span></span>

<span data-ttu-id="256ec-284">Utilisez l' ```Remove-CsGroupPolicyAssignment``` applet de cmdlet pour supprimer une stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="256ec-284">Use the ```Remove-CsGroupPolicyAssignment``` cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="256ec-285">Lorsque vous supprimez une stratégie d’un groupe, les priorités des autres stratégies du même type attribuées à ce groupe et dont le classement est inférieur sont mises à jour.</span><span class="sxs-lookup"><span data-stu-id="256ec-285">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="256ec-286">Par exemple, si vous supprimez une stratégie de classement de 2, les stratégies dont le classement est 3 et 4 sont mis à jour pour refléter leur nouveau classement.</span><span class="sxs-lookup"><span data-stu-id="256ec-286">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="256ec-287">Les deux tables suivantes montrent cet exemple.</span><span class="sxs-lookup"><span data-stu-id="256ec-287">The following two tables show this example.</span></span>

<span data-ttu-id="256ec-288">Vous trouverez ci-dessous une liste des affectations et des priorités pour une stratégie de réunion Teams.</span><span class="sxs-lookup"><span data-stu-id="256ec-288">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="256ec-289">Nom du groupe</span><span class="sxs-lookup"><span data-stu-id="256ec-289">Group name</span></span>  |<span data-ttu-id="256ec-290">Nom de la stratégie</span><span class="sxs-lookup"><span data-stu-id="256ec-290">Policy name</span></span>  |<span data-ttu-id="256ec-291">Classement</span><span class="sxs-lookup"><span data-stu-id="256ec-291">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="256ec-292">Ventes</span><span class="sxs-lookup"><span data-stu-id="256ec-292">Sales</span></span>    |<span data-ttu-id="256ec-293">Politique de vente</span><span class="sxs-lookup"><span data-stu-id="256ec-293">Sales policy</span></span>       | <span data-ttu-id="256ec-294">1</span><span class="sxs-lookup"><span data-stu-id="256ec-294">1</span></span>        |
|<span data-ttu-id="256ec-295">Région ouest</span><span class="sxs-lookup"><span data-stu-id="256ec-295">West Region</span></span>     |<span data-ttu-id="256ec-296">Politique de la région ouest</span><span class="sxs-lookup"><span data-stu-id="256ec-296">West Region policy</span></span>         |<span data-ttu-id="256ec-297">2</span><span class="sxs-lookup"><span data-stu-id="256ec-297">2</span></span>         |
|<span data-ttu-id="256ec-298">Division</span><span class="sxs-lookup"><span data-stu-id="256ec-298">Division</span></span>    |<span data-ttu-id="256ec-299">Politique de division</span><span class="sxs-lookup"><span data-stu-id="256ec-299">Division policy</span></span>         |<span data-ttu-id="256ec-300">3</span><span class="sxs-lookup"><span data-stu-id="256ec-300">3</span></span>         |
|<span data-ttu-id="256ec-301">Complémentaire</span><span class="sxs-lookup"><span data-stu-id="256ec-301">Subsidiary</span></span>   |<span data-ttu-id="256ec-302">Politique subsidiaire</span><span class="sxs-lookup"><span data-stu-id="256ec-302">Subsidiary policy</span></span>        |<span data-ttu-id="256ec-303">4</span><span class="sxs-lookup"><span data-stu-id="256ec-303">4</span></span>         |

<span data-ttu-id="256ec-304">Si nous supprimons la politique de la région ouest du groupe région ouest, les affectations et les priorités de la stratégie sont mises à jour comme suit.</span><span class="sxs-lookup"><span data-stu-id="256ec-304">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="256ec-305">Nom du groupe</span><span class="sxs-lookup"><span data-stu-id="256ec-305">Group name</span></span>  |<span data-ttu-id="256ec-306">Nom de la stratégie</span><span class="sxs-lookup"><span data-stu-id="256ec-306">Policy name</span></span>  |<span data-ttu-id="256ec-307">Classement</span><span class="sxs-lookup"><span data-stu-id="256ec-307">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="256ec-308">Ventes</span><span class="sxs-lookup"><span data-stu-id="256ec-308">Sales</span></span>    |<span data-ttu-id="256ec-309">Politique de vente</span><span class="sxs-lookup"><span data-stu-id="256ec-309">Sales policy</span></span>       | <span data-ttu-id="256ec-310">1</span><span class="sxs-lookup"><span data-stu-id="256ec-310">1</span></span>        |
|<span data-ttu-id="256ec-311">Division</span><span class="sxs-lookup"><span data-stu-id="256ec-311">Division</span></span>    |<span data-ttu-id="256ec-312">Politique de division</span><span class="sxs-lookup"><span data-stu-id="256ec-312">Division policy</span></span>         |<span data-ttu-id="256ec-313">2</span><span class="sxs-lookup"><span data-stu-id="256ec-313">2</span></span>         |
|<span data-ttu-id="256ec-314">Complémentaire</span><span class="sxs-lookup"><span data-stu-id="256ec-314">Subsidiary</span></span>   |<span data-ttu-id="256ec-315">Politique subsidiaire</span><span class="sxs-lookup"><span data-stu-id="256ec-315">Subsidiary policy</span></span>        |<span data-ttu-id="256ec-316">3</span><span class="sxs-lookup"><span data-stu-id="256ec-316">3</span></span>        |

<span data-ttu-id="256ec-317">Dans cet exemple, nous supprimons la stratégie de réunion teams d’un groupe.</span><span class="sxs-lookup"><span data-stu-id="256ec-317">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

<span data-ttu-id="256ec-318">Pour en savoir plus, consultez la rubrique [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="256ec-318">To learn more, see [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span></span>

### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="256ec-319">Modifier une affectation de stratégie pour un groupe</span><span class="sxs-lookup"><span data-stu-id="256ec-319">Change a policy assignment for a group</span></span>

<span data-ttu-id="256ec-320">Après avoir affecté une stratégie à un groupe, vous pouvez utiliser l' ```Set-CsGroupPolicyAssignmentd``` applet de cmdlet pour modifier l’affectation de stratégie de ce groupe comme suit :</span><span class="sxs-lookup"><span data-stu-id="256ec-320">After you assign a policy to a group, you can use the ```Set-CsGroupPolicyAssignmentd``` cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="256ec-321">Changer le classement</span><span class="sxs-lookup"><span data-stu-id="256ec-321">Change the ranking</span></span>
- <span data-ttu-id="256ec-322">Modifier la stratégie d’un type de stratégie donné</span><span class="sxs-lookup"><span data-stu-id="256ec-322">Change the policy of a given policy type</span></span>
- <span data-ttu-id="256ec-323">Modification de la stratégie d’un type de stratégie donné et du classement</span><span class="sxs-lookup"><span data-stu-id="256ec-323">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="256ec-324">Dans cet exemple, nous affectons à la stratégie de parc d’appels de groupe une stratégie nommée SupportCallPark et le classement de l’affectation à 3.</span><span class="sxs-lookup"><span data-stu-id="256ec-324">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

<span data-ttu-id="256ec-325">Pour en savoir plus, consultez la rubrique [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="256ec-325">To learn more, see [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span></span>

### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="256ec-326">Modification de la stratégie d’effectivité d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="256ec-326">Change the effective policy for a user</span></span>

<span data-ttu-id="256ec-327">Voici un exemple illustrant la modification de la stratégie d’effectivité d’un utilisateur qui a directement affecté une stratégie.</span><span class="sxs-lookup"><span data-stu-id="256ec-327">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="256ec-328">Tout d’abord, nous utilisons l’applet de connexion ```Get-CsUserPolicyAssignment``` conjointement avec le ```PolicySource``` paramètre pour obtenir des informations sur les stratégies de diffusion de réunion associées à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="256ec-328">First, we use the ```Get-CsUserPolicyAssignment``` cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> <span data-ttu-id="256ec-329">Pour en savoir plus, consultez la rubrique [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="256ec-329">To learn more, see [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="256ec-330">La sortie montre que l’utilisateur a été directement affecté à une stratégie de diffusion de réunion teams nommée événements de l’employé, qui est prioritaire sur la stratégie nommée événements dynamiques du fournisseur qui est affectée à un groupe auquel l’utilisateur appartient.</span><span class="sxs-lookup"><span data-stu-id="256ec-330">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="256ec-331">À présent, nous supprimons la stratégie d’événements des employés de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="256ec-331">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="256ec-332">Cela signifie que l’utilisateur ne dispose plus d’une stratégie de diffusion de réunion teams et qu’il hérite de la stratégie d’événements en direct du fournisseur qui est affectée au groupe auquel l’utilisateur appartient.</span><span class="sxs-lookup"><span data-stu-id="256ec-332">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="256ec-333">Utilisez l’applet de commande suivante dans le module PowerShell Skype entreprise pour effectuer cette opération.</span><span class="sxs-lookup"><span data-stu-id="256ec-333">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="256ec-334">Pour ce faire, vous pouvez utiliser l’applet de commande suivante dans le module PowerShell teams pour procéder à la mise à niveau en utilisant une affectation de stratégie de lot dans laquelle $users est une liste d’utilisateurs que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="256ec-334">You can use following cmdlet in the Teams Powershell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="256ec-335">Affectation d’un package de stratégie à un lot d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="256ec-335">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="256ec-336">Avec une affectation de package de stratégie de lot, vous pouvez attribuer un package de stratégie à un grand nombre d’utilisateurs à la fois sans avoir à utiliser de script.</span><span class="sxs-lookup"><span data-stu-id="256ec-336">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="256ec-337">Utilisez l' ```New-CsBatchPolicyPackageAssignmentOperation``` applet de commande pour transmettre un lot d’utilisateurs et le package de stratégie que vous voulez affecter.</span><span class="sxs-lookup"><span data-stu-id="256ec-337">You use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="256ec-338">Les affectations sont traitées en tant qu’opérations en arrière-plan et chaque lot est généré.</span><span class="sxs-lookup"><span data-stu-id="256ec-338">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="256ec-339">Vous pouvez ensuite utiliser l' ```Get-CsBatchPolicyAssignmentOperation``` applet de commande pour effectuer le suivi de l’avancement et de l’état des devoirs d’un lot.</span><span class="sxs-lookup"><span data-stu-id="256ec-339">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="256ec-340">Un lot peut contenir jusqu’à 20 000 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="256ec-340">A batch can contain up to 20,000 users.</span></span> <span data-ttu-id="256ec-341">Vous pouvez spécifier des utilisateurs en fonction de leur ID d’objet, de leur nom d’utilisateur principal, de leur adresse SIP ou de leur adresse de messagerie.</span><span class="sxs-lookup"><span data-stu-id="256ec-341">You can specify users by their object Id, UPN, SIP address, or email address.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="256ec-342">Pour l’instant, nous vous recommandons d’affecter des packages de stratégie par lot d’utilisateurs 5 000 à la fois.</span><span class="sxs-lookup"><span data-stu-id="256ec-342">We're currently recommending that you assign policy packages in batches of 5,000 users at a time.</span></span> <span data-ttu-id="256ec-343">Au cours de ces périodes de demande croissante, il est possible que les temps de traitement soient retardés.</span><span class="sxs-lookup"><span data-stu-id="256ec-343">During these times of increased demand, you may experience delays in processing times.</span></span> <span data-ttu-id="256ec-344">Pour réduire l’impact de ces délais de traitement, nous vous suggérons d’adresser de plus petites tailles de lot à des utilisateurs 5 000 et de n’en faire qu’après la fin de la précédente.</span><span class="sxs-lookup"><span data-stu-id="256ec-344">To minimize the impact of these increased processing times, we suggest that you submit smaller batch sizes of up to 5,000 users, and submit each batch only after the previous one is completed.</span></span> <span data-ttu-id="256ec-345">Vous pouvez également obtenir de l’aide pour soumettre des lots en dehors de vos heures de travail normales.</span><span class="sxs-lookup"><span data-stu-id="256ec-345">Submitting batches outside your regular business hours can also help.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="256ec-346">Installer le module Microsoft teams PowerShell et s’y connecter</span><span class="sxs-lookup"><span data-stu-id="256ec-346">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="256ec-347">Exécutez la commande suivante pour installer le [module Microsoft teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (si vous ne l’avez pas déjà fait).</span><span class="sxs-lookup"><span data-stu-id="256ec-347">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="256ec-348">Vérifiez que vous avez installé la version 1.0.5 ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="256ec-348">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="256ec-349">Exécutez la commande suivante pour vous connecter à teams et démarrer une session.</span><span class="sxs-lookup"><span data-stu-id="256ec-349">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="256ec-350">Lorsque vous y êtes invité, connectez-vous à l’aide de vos informations d’identification d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="256ec-350">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="256ec-351">Affectation d’un package de stratégie à un lot d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="256ec-351">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="256ec-352">Dans cet exemple, nous utilisons l' ```New-CsBatchPolicyPackageAssignmentOperation``` applet de commande pour affecter le package de stratégie de Education_PrimaryStudent à un lot d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="256ec-352">In this example, we use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

<span data-ttu-id="256ec-353">Pour en savoir plus, voir [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="256ec-353">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="256ec-354">Obtenir l’état d’une affectation par lot</span><span class="sxs-lookup"><span data-stu-id="256ec-354">Get the status of a batch assignment</span></span>

<span data-ttu-id="256ec-355">Exécutez la commande suivante pour obtenir l’état d’une affectation de lot, où OperationId est l’ID d’opération renvoyé par l' ```New-CsBatchPolicyAssignmentOperation``` applet de commande pour un lot donné.</span><span class="sxs-lookup"><span data-stu-id="256ec-355">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="256ec-356">Si la sortie indique qu’une erreur s’est produite, exécutez la commande suivante pour obtenir plus d’informations sur les erreurs qui se trouvent dans la ```UserState``` propriété.</span><span class="sxs-lookup"><span data-stu-id="256ec-356">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="256ec-357">Pour en savoir plus, consultez la rubrique [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="256ec-357">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="256ec-358">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="256ec-358">Related topics</span></span>

- [<span data-ttu-id="256ec-359">Aperçu de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="256ec-359">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
