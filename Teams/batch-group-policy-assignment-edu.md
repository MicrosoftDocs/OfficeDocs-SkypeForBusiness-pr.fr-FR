---
title: Attribuer des stratégies à un grand nombre d’utilisateurs dans votre établissement scolaire
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: karsmith, angch, cebulnes
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment attribuer des stratégies à un grand nombre d’utilisateurs de votre établissement d’enseignement en fonction de l’appartenance à un groupe ou directement par le biais d’une affectation par lot à des fins d’établissement scolaire distant (télé-école, télé-école).
f1keywords: ''
ms.openlocfilehash: f2d36db6a96f6a9a42590ada6600ef38738b30a9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092902"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a><span data-ttu-id="0d0d9-103">Attribuer des stratégies à un grand nombre d’utilisateurs dans votre établissement scolaire</span><span class="sxs-lookup"><span data-stu-id="0d0d9-103">Assign policies to large sets of users in your school</span></span>

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> <span data-ttu-id="0d0d9-104">Pour en savoir plus sur l’attribution de stratégies dans Microsoft Teams, voir Attribuer des stratégies à [vos utilisateurs dans Teams.](assign-policies.md)</span><span class="sxs-lookup"><span data-stu-id="0d0d9-104">For the larger story on assigning policies in Microsoft Teams, see [Assign policies to your users in Teams](assign-policies.md).</span></span>

## <a name="overview"></a><span data-ttu-id="0d0d9-105">Présentation</span><span class="sxs-lookup"><span data-stu-id="0d0d9-105">Overview</span></span>

<span data-ttu-id="0d0d9-106">Avez-vous besoin d’accorder à vos étudiants et enseignants l’accès aux différentes fonctionnalités de Microsoft Teams ?</span><span class="sxs-lookup"><span data-stu-id="0d0d9-106">Do you need to give your students and educators access to different features in Microsoft Teams?</span></span> <span data-ttu-id="0d0d9-107">Vous pouvez rapidement identifier les utilisateurs de votre organisation par type de licence, puis leur affecter la stratégie appropriée.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-107">You can quickly identify the users in your organization by license type and then assign them the appropriate policy.</span></span> <span data-ttu-id="0d0d9-108">Ce didacticiel vous montre comment affecter une stratégie de réunion à un grand nombre d’utilisateurs de votre établissement scolaire.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-108">This tutorial shows you how to assign a meeting policy to large sets of users in your school.</span></span> <span data-ttu-id="0d0d9-109">Vous pouvez attribuer des stratégies à l’aide du Microsoft Teams d’administration et de PowerShell. Nous allons vous montrer les deux façons de faire.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-109">You can assign policies using the Microsoft Teams admin center and PowerShell and we'll show you both ways.</span></span>

<span data-ttu-id="0d0d9-110">Vous pouvez affecter une stratégie de réunion à un groupe de sécurité dont les utilisateurs sont membres ou directement à l’échelle des utilisateurs via une affectation de stratégie de lot.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-110">You can assign a meeting policy to a security group that the users are members of or directly to users at scale through a batch policy assignment.</span></span> <span data-ttu-id="0d0d9-111">Vous apprendrez comment :</span><span class="sxs-lookup"><span data-stu-id="0d0d9-111">You'll learn how to:</span></span>

- <span data-ttu-id="0d0d9-112">**Utiliser [l’affectation de stratégies à](#assign-a-policy-to-a-group) des groupes pour affecter une stratégie de réunion à un groupe de sécurité (recommandé).**</span><span class="sxs-lookup"><span data-stu-id="0d0d9-112">**Use [policy assignment to groups](#assign-a-policy-to-a-group) to assign a meeting policy to a security group (recommended)**.</span></span> <span data-ttu-id="0d0d9-113">Cette méthode vous permet d’affecter une stratégie en fonction de l’appartenance aux groupes.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-113">This method lets you assign a policy based on group membership.</span></span> <span data-ttu-id="0d0d9-114">Vous pouvez affecter une stratégie à un groupe de sécurité ou une liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-114">You can assign a policy to a security group or distribution list.</span></span> <span data-ttu-id="0d0d9-115">À mesure que les membres sont ajoutés au groupe ou supprimés, leurs affectations de stratégie héritées sont mises à jour en conséquence.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-115">As members are added to or removed from the group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="0d0d9-116">Nous vous recommandons d’utiliser cette méthode, car elle réduit le temps de gestion des stratégies pour les nouveaux utilisateurs ou lorsque les rôles des utilisateurs changent.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-116">We recommend you use this method because it reduces the time to manage policies for new users or when users' roles change.</span></span> <span data-ttu-id="0d0d9-117">Cette méthode est plus efficace pour les groupes de 50 000 utilisateurs au plus, mais fonctionne également avec des groupes plus importants.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-117">This method works best for groups of up to 50,000 users but will also work with larger groups.</span></span>

- <span data-ttu-id="0d0d9-118">**Utilisez [l’affectation d’une stratégie de](assign-policies.md#assign-a-policy-to-a-batch-of-users) lot pour affecter une stratégie de réunion directement aux utilisateurs en bloc.**</span><span class="sxs-lookup"><span data-stu-id="0d0d9-118">**Use [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users) to assign a meeting policy directly to users in bulk**.</span></span> <span data-ttu-id="0d0d9-119">Vous pouvez affecter une stratégie à 5 000 utilisateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-119">You can assign a policy for up to 5,000 users at a time.</span></span> <span data-ttu-id="0d0d9-120">Si vous avez plus de 5 000 utilisateurs, vous pouvez envoyer plusieurs lots.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-120">If you have more than 5,000 users, you can submit multiple batches.</span></span> <span data-ttu-id="0d0d9-121">Avec cette méthode, lorsque vous avez de nouveaux utilisateurs, vous devez ré-exécuter l’affectation de lot pour affecter la stratégie à ces nouveaux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-121">With this method, when you have new users, you'll need to re-run the batch assignment to assign the policy to those new users.</span></span>

<span data-ttu-id="0d0d9-122">N’oubliez pas que, Teams, les utilisateurs obtiennent automatiquement la stratégie globale (à l’échelle de l’organisation par défaut) pour un type de stratégie Teams sauf si vous créez et attribuez une stratégie personnalisée.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-122">Remember that in Teams, users automatically get the Global (Org-wide default) policy for a Teams policy type unless you create and assign a custom policy.</span></span> <span data-ttu-id="0d0d9-123">Étant donné que la population d’étudiants est souvent le plus grand groupe d’utilisateurs et reçoit souvent les paramètres les plus restrictifs, nous vous recommandons de suivre les recommandations suivantes :</span><span class="sxs-lookup"><span data-stu-id="0d0d9-123">Because the student population is often the largest set of users and they often receive the most restrictive settings, we recommend that you do the following:</span></span>

- <span data-ttu-id="0d0d9-124">Créez une stratégie personnalisée qui autorise des fonctionnalités essentielles telles que la conversation privée et la planification de réunions, et affecter la stratégie à votre personnel et aux enseignants.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-124">Create a custom policy that allows core capabilities such as private chat and meeting scheduling and assign the policy to your staff and educators.</span></span>
- <span data-ttu-id="0d0d9-125">Attribuez la stratégie personnalisée à votre personnel et aux enseignants.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-125">Assign the custom policy to your staff and educators.</span></span>
- <span data-ttu-id="0d0d9-126">Modifiez et appliquez la stratégie globale (à l’échelle de l’organisation par défaut) pour restreindre les fonctionnalités pour les étudiants.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-126">Edit and apply the Global (Org-wide default) policy to restrict capabilities for students.</span></span>

<span data-ttu-id="0d0d9-127">N’oubliez pas que la stratégie globale s’appliquera à tous les utilisateurs de votre établissement scolaire jusqu’à ce que vous créez une stratégie personnalisée et l’affectiez à votre personnel et à vos enseignants.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-127">Keep in mind that the Global policy will apply to all users in your school until you create a custom policy and assign it to your staff and educators.</span></span>

<span data-ttu-id="0d0d9-128">Dans ce didacticiel, les étudiants auront accès à la stratégie de réunion globale et nous attribuerons une stratégie de réunion personnalisée nommée EducatorMeetingPolicy au personnel et aux enseignants.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-128">In this tutorial, students will get the Global meeting policy and we'll assign a custom meeting policy named EducatorMeetingPolicy to staff and educators.</span></span> <span data-ttu-id="0d0d9-129">Nous partons du principe que vous avez modifié la [](policy-packages-edu.md) stratégie globale pour personnaliser les paramètres de réunion pour les étudiants et que vous avez créé une stratégie personnalisée qui définit l’expérience de réunion pour le personnel et les enseignants.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-129">We assume that you've edited the Global policy to tailor meeting settings for students and [created a custom policy](policy-packages-edu.md) that defines the meeting experience for staff and educators.</span></span>

![Capture d’écran de la page Stratégies de réunion dans le Teams d’administration](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="0d0d9-131">Affecter une stratégie à un groupe</span><span class="sxs-lookup"><span data-stu-id="0d0d9-131">Assign a policy to a group</span></span>

<span data-ttu-id="0d0d9-132">Suivez ces étapes pour créer un groupe de sécurité pour votre personnel et vos enseignants, puis affectez une stratégie de réunion personnalisée nommée EducatorMeetingPolicy à ce groupe de sécurité.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-132">Follow these steps to create a security group for your staff and educators, and then assign a custom meeting policy named EducatorMeetingPolicy to that security group.</span></span>

### <a name="before-you-get-started"></a><span data-ttu-id="0d0d9-133">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="0d0d9-133">Before you get started</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0d0d9-134">Lorsque vous attribuez une stratégie à un groupe, l’affectation de stratégie est propagée aux membres du groupe selon les règles de priorité.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-134">When you assign a policy to a group, the policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="0d0d9-135">Par exemple, si un utilisateur est directement affecté à une stratégie (individuellement ou par le biais d’une affectation de lots), cette stratégie est prioritaire sur une stratégie héritée d’un groupe.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-135">For example, if a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence over a policy that's inherited from a group.</span></span> <span data-ttu-id="0d0d9-136">Cela signifie également que si un utilisateur a une stratégie de réunion qui lui a été attribuée directement, vous devez supprimer cette stratégie de réunion de l’utilisateur pour qu’il puisse hériter d’une stratégie de réunion d’un groupe de sécurité.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-136">This also means that if a user has a meeting policy that was directly assigned to them, you'll have to remove that meeting policy from the user before they can inherit a meeting policy from a security group.</span></span>

<span data-ttu-id="0d0d9-137">Avant de commencer, il est [](assign-policies.md#precedence-rules) important de comprendre les règles de priorité et le [classement d’affectation de groupe.](assign-policies.md#group-assignment-ranking)</span><span class="sxs-lookup"><span data-stu-id="0d0d9-137">Before you get started, it's important to understand [precedence rules](assign-policies.md#precedence-rules) and [group assignment ranking](assign-policies.md#group-assignment-ranking).</span></span> <span data-ttu-id="0d0d9-138">Veillez à lire et à comprendre les concepts de ce que vous devez savoir sur l’affectation de **[stratégies à des groupes.](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**</span><span class="sxs-lookup"><span data-stu-id="0d0d9-138">**Make sure that you read and understand the concepts in [What you need to know about policy assignment to groups](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**.</span></span>

<span data-ttu-id="0d0d9-139">Vous devez effectuer toutes ces étapes pour que votre personnel et vos enseignants héritent d’une stratégie de réunion d’un groupe de sécurité.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-139">You'll need to complete all these steps for your staff and educators to inherit a meeting policy from a security group.</span></span>

1. <span data-ttu-id="0d0d9-140">[Créer des groupes de sécurité.](#create-security-groups)</span><span class="sxs-lookup"><span data-stu-id="0d0d9-140">[Create security groups](#create-security-groups).</span></span>
2. <span data-ttu-id="0d0d9-141">[Attribuer une stratégie à un groupe de sécurité.](#assign-a-policy-to-a-security-group)</span><span class="sxs-lookup"><span data-stu-id="0d0d9-141">[Assign a policy to a security group](#assign-a-policy-to-a-security-group).</span></span>
3. <span data-ttu-id="0d0d9-142">[Supprimez une stratégie qui a été attribuée directement aux utilisateurs.](#remove-a-policy-that-was-directly-assigned-to-users)</span><span class="sxs-lookup"><span data-stu-id="0d0d9-142">[Remove a policy that was directly assigned to users](#remove-a-policy-that-was-directly-assigned-to-users).</span></span>

### <a name="create-security-groups"></a><span data-ttu-id="0d0d9-143">Créer des groupes de sécurité</span><span class="sxs-lookup"><span data-stu-id="0d0d9-143">Create security groups</span></span>

<span data-ttu-id="0d0d9-144">Tout d’abord, créez un groupe de sécurité pour votre personnel et vos enseignants.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-144">First, create a security group for your staff and educators.</span></span>

<span data-ttu-id="0d0d9-145">Avec [Synchronisation des données scolaires](/SchoolDataSync/) (SDS), vous pouvez facilement créer des groupes de sécurité pour les enseignants et [les](/SchoolDataSync/edu-security-groups) étudiants de votre établissement scolaire.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-145">With [School Data Sync](/SchoolDataSync/) (SDS), you can [easily create security groups educators and students](/SchoolDataSync/edu-security-groups) in your school.</span></span> <span data-ttu-id="0d0d9-146">Nous vous recommandons d’utiliser SDS pour créer les groupes de sécurité dont vous avez besoin pour gérer les stratégies pour votre établissement scolaire.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-146">We recommend that you use SDS to create the security groups you need to manage policies for your school.</span></span>

<span data-ttu-id="0d0d9-147">Si vous ne parvenez pas à déployer SDS au sein de votre environnement, utilisez ce [script PowerShell](scripts/powershell-script-security-groups-edu.md) pour créer deux groupes de sécurité, un pour tous les membres du personnel et les enseignants à qui une licence pour les enseignants est attribuée et l’autre pour tous les étudiants titulaires d’une licence Étudiant.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-147">If you're unable to deploy SDS within your environment, use [this PowerShell script](scripts/powershell-script-security-groups-edu.md) to create two security groups, one for all staff and educators who have a Faculty license assigned and another for all students who have a Student license assigned.</span></span> <span data-ttu-id="0d0d9-148">Vous devrez exécuter régulièrement ce script pour tenir les groupes à jour.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-148">You'll need to run this script routinely to keep the groups fresh and up to date.</span></span>

### <a name="assign-a-policy-to-a-security-group"></a><span data-ttu-id="0d0d9-149">Affecter une stratégie à un groupe de sécurité</span><span class="sxs-lookup"><span data-stu-id="0d0d9-149">Assign a policy to a security group</span></span>

#### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="0d0d9-150">Utiliser le centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0d0d9-150">Using the Microsoft Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="0d0d9-151">Pour l’instant, l’affectation de stratégies à des groupes à l’aide du Centre d’administration Microsoft Teams est disponible uniquement pour la stratégie d’appel Teams, la stratégie de parcage d’appel Teams, la stratégie Teams, la stratégie d’événements en direct Teams, la stratégie de réunion Teams et la stratégie de messagerie Teams.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-151">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="0d0d9-152">Pour d’autres types de stratégie, utilisez PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-152">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="0d0d9-153">Dans le volet de navigation gauche du centre d’administration Microsoft Teams, accédez aux **Réunions** > **Stratégies de réunion**.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-153">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="0d0d9-154">Sélectionnez **l’onglet Affectation de stratégie de** groupe.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-154">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="0d0d9-155">Sélectionnez **Ajouter un** groupe, puis dans le volet **Affecter** une stratégie à un groupe, comme suit :</span><span class="sxs-lookup"><span data-stu-id="0d0d9-155">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>

    ![Capture d’écran du volet Modifier les paramètres, affichant la stratégie de réunion](media/batch-group-policy-assignment-edu-group.png)
    1. <span data-ttu-id="0d0d9-157">Dans la **zone Sélectionner un groupe,** recherchez et ajoutez le groupe de sécurité qui contient votre personnel et vos enseignants.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-157">In the **Select a group** box, search for and add the security group that contains your staff and educators.</span></span>
    2. <span data-ttu-id="0d0d9-158">Dans la **zone Sélectionner le rang,** entrez **1.**</span><span class="sxs-lookup"><span data-stu-id="0d0d9-158">In the **Select rank** box, enter **1**.</span></span>
    3. <span data-ttu-id="0d0d9-159">Dans la **zone Sélectionner une stratégie,** **sélectionnez EducatorMeetingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="0d0d9-159">In the **Select a policy** box, select **EducatorMeetingPolicy**.</span></span>
    4. <span data-ttu-id="0d0d9-160">Sélectionnez **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="0d0d9-160">Select **Apply**.</span></span>

<span data-ttu-id="0d0d9-161">Pour supprimer une affectation de  stratégie de groupe, dans l’onglet Affectation de stratégie de groupe de la page stratégie, sélectionnez l’affectation de groupe, puis sélectionnez **Supprimer.**</span><span class="sxs-lookup"><span data-stu-id="0d0d9-161">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="0d0d9-162">Pour modifier le classement d’une affectation de groupe, vous devez d’abord supprimer l’affectation de stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-162">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="0d0d9-163">Suivez ensuite les étapes ci-dessus pour affecter la stratégie à un groupe.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-163">Then, follow the steps above to assign the policy to a group.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="0d0d9-164">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="0d0d9-164">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="0d0d9-165">Actuellement, l’affectation de stratégies à des groupes à l’aide de PowerShell n’est pas disponible pour tous Teams types de stratégies.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-165">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="0d0d9-166">Pour obtenir la liste des types de stratégies pris en charge, voir [New-CsGroupPolicyAssignment.](/powershell/module/teams/new-csgrouppolicyassignment)</span><span class="sxs-lookup"><span data-stu-id="0d0d9-166">See [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="0d0d9-167">Installer et se connecter au module PowerShell Microsoft Teams’équipe</span><span class="sxs-lookup"><span data-stu-id="0d0d9-167">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="0d0d9-168">Exécutez la commande suivante [pour installer Teams module PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (s’il n’est pas déjà installé).</span><span class="sxs-lookup"><span data-stu-id="0d0d9-168">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="0d0d9-169">Veillez à installer la version 1.0.5 ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-169">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="0d0d9-170">Exécutez ce qui suit pour vous connecter Teams et démarrer une session.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-170">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="0d0d9-171">Lorsque vous y êtes invité, connectez-vous à l’aide de vos informations d’identification d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-171">When you're prompted, sign in using your admin credentials.</span></span>

##### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="0d0d9-172">Affecter une stratégie à un groupe</span><span class="sxs-lookup"><span data-stu-id="0d0d9-172">Assign a policy to a group</span></span>

<span data-ttu-id="0d0d9-173">Exécutez la stratégie suivante pour attribuer la stratégie de réunion educatorMeetingPolicy au groupe de sécurité qui contient votre personnel et vos enseignants et définissez le classement des devoirs sur 1.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-173">Run the following to assign the meeting policy named EducatorMeetingPolicy to the security group that contains your staff and educators and set the assignment ranking to 1.</span></span> <span data-ttu-id="0d0d9-174">Vous pouvez spécifier un groupe de sécurité à l’aide de l’objet, de l’adresse SIP (Session Initiation Protocol) ou de l’adresse de messagerie.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-174">You can specify a security group by using the object Id, Session Initiation Protocol (SIP) address, or email address.</span></span> <span data-ttu-id="0d0d9-175">Dans cet exemple, nous utilisons une adresse de messagerie (staff-faculty@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="0d0d9-175">In this example, we use an email address (staff-faculty@contoso.com).</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a><span data-ttu-id="0d0d9-176">Supprimer une stratégie qui a été attribuée directement aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="0d0d9-176">Remove a policy that was directly assigned to users</span></span>

<span data-ttu-id="0d0d9-177">N’oubliez pas que si un utilisateur a été directement affecté à une stratégie (individuellement ou par le biais d’une affectation de lots), cette stratégie est prioritaire.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-177">Remember that if a user was directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="0d0d9-178">Cela signifie que si un utilisateur a une stratégie de réunion qui lui a été attribuée directement, vous devez supprimer cette stratégie de réunion de l’utilisateur pour qu’il puisse hériter d’une stratégie de réunion d’un groupe de sécurité.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-178">This means that if a user has a meeting policy that was directly assigned to them, you'll have to remove that meeting policy from the user before they can inherit a meeting policy from a security group.</span></span>

<span data-ttu-id="0d0d9-179">Pour en savoir plus, [consultez ce que vous devez savoir sur l’affectation de stratégies à des groupes.](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)</span><span class="sxs-lookup"><span data-stu-id="0d0d9-179">To learn more, see [What you need to know about policy assignment to groups](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups).</span></span>

<span data-ttu-id="0d0d9-180">Pour supprimer la stratégie de réunion directement attribuée à votre personnel et aux enseignants, suivez ces étapes.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-180">Follow these steps to remove the meeting policy that was directly assigned to your staff and educators.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="0d0d9-181">Installer et se connecter au module PowerShell Microsoft Teams’équipe</span><span class="sxs-lookup"><span data-stu-id="0d0d9-181">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="0d0d9-182">Exécutez la commande suivante [pour installer Teams module PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (s’il n’est pas déjà installé).</span><span class="sxs-lookup"><span data-stu-id="0d0d9-182">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="0d0d9-183">Veillez à installer la version 1.0.5 ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-183">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="0d0d9-184">Exécutez ce qui suit pour vous connecter Teams et démarrer une session.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-184">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="0d0d9-185">Lorsque vous y êtes invité, connectez-vous à l’aide des mêmes informations d’identification d’administrateur que vous avez utilisées pour vous connecter à Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-185">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a><span data-ttu-id="0d0d9-186">Désaffecter une stratégie directement attribuée à des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="0d0d9-186">Unassign a policy that was directly assigned to users</span></span>

<span data-ttu-id="0d0d9-187">Exécutez la stratégie suivante pour supprimer une stratégie de réunion pour les utilisateurs à qui cette stratégie a été attribuée directement.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-187">Run the following to remove a meeting policy from users who were directly assigned that policy.</span></span> <span data-ttu-id="0d0d9-188">Vous pouvez spécifier les utilisateurs par adresse e-mail ou ID d’objet.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-188">You can specify users by email address or object ID.</span></span>

<span data-ttu-id="0d0d9-189">Dans cet exemple, la stratégie de réunion est supprimée des utilisateurs spécifiés par leur adresse e-mail.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-189">In this example, the meeting policy is removed from users specified by their email address.</span></span>

```powershell
$users_ids = @("reda@contoso.com", "nikica@contoso.com", "jamie@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

<span data-ttu-id="0d0d9-190">Dans cet exemple, la stratégie de réunion est supprimée de la liste des utilisateurs dans un fichier texte nommé user_ids.txt.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-190">In this example, the meeting policy is removed from the list of users in a text file named user_ids.txt.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

##### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="0d0d9-191">Obtenir des affectations de stratégie pour un groupe</span><span class="sxs-lookup"><span data-stu-id="0d0d9-191">Get policy assignments for a group</span></span>

<span data-ttu-id="0d0d9-192">Exécutez ce qui suit pour voir toutes les stratégies affectées à un groupe de sécurité spécifique.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-192">Run the following to see all the policies assigned to a specific security group.</span></span> <span data-ttu-id="0d0d9-193">Notez que les groupes sont toujours répertoriés par leur ID de groupe, même si leur adresse SIP ou adresse de messagerie a été utilisée pour affecter la stratégie.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-193">Note that groups are always listed by their group ID even if its SIP address or email address was used to assign the policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="0d0d9-194">Obtenir les stratégies attribuées à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="0d0d9-194">Get the policies assigned to a user</span></span>

<span data-ttu-id="0d0d9-195">Exécutez ce qui suit pour voir toutes les stratégies affectées à un utilisateur spécifique.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-195">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="0d0d9-196">L’exemple suivant vous montre comment obtenir les stratégies affectées à reda@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-196">The following example shows you how to get the policies that are assigned to reda@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="0d0d9-197">Affecter une stratégie à un lot d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="0d0d9-197">Assign a policy to a batch of users</span></span>

<span data-ttu-id="0d0d9-198">Suivez ces étapes pour affecter une stratégie de réunion personnalisée nommée EducatorMeetingPolicy directement à votre personnel et aux enseignants en bloc.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-198">Follow these steps to assign a custom meeting policy named EducatorMeetingPolicy directly to your staff and educators in bulk.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="0d0d9-199">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="0d0d9-199">Using PowerShell</span></span>

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a><span data-ttu-id="0d0d9-200">Connecter le module Azure AD PowerShell Graph et le module Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="0d0d9-200">Connect to the Azure AD PowerShell for Graph module and the Teams PowerShell module</span></span>

<span data-ttu-id="0d0d9-201">Avant d’effectuer les étapes de cet article, vous devez installer et vous connecter au module Azure AD PowerShell pour Graph (afin d’identifier les utilisateurs par leurs licences attribuées) et au module Microsoft Teams PowerShell (pour affecter les stratégies à ces utilisateurs).</span><span class="sxs-lookup"><span data-stu-id="0d0d9-201">Before you perform the steps in this article, you'll need to install and connect to the Azure AD PowerShell for Graph module (to identify users by their assigned licenses) and the Microsoft Teams PowerShell module (to assign the policies to those users).</span></span>

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a><span data-ttu-id="0d0d9-202">Installer et se connecter au module Azure AD PowerShell Graph</span><span class="sxs-lookup"><span data-stu-id="0d0d9-202">Install and connect to the Azure AD PowerShell for Graph module</span></span>

<span data-ttu-id="0d0d9-203">Ouvrez une invite de commandes avec élévation de Windows PowerShell (exécutez Windows PowerShell en tant qu’administrateur), puis exécutez l’une des commandes suivantes pour installer le module PowerShell Azure Active Directory Graph’équipe.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-203">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator), and then run the following to install the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Install-Module -Name AzureAD
```

<span data-ttu-id="0d0d9-204">Exécutez ce qui suit pour vous connecter à Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-204">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="0d0d9-205">Lorsque vous y êtes invité, connectez-vous à l’aide de vos informations d’identification d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-205">When you're prompted, sign in using your admin credentials.</span></span>

<span data-ttu-id="0d0d9-206">Pour plus d’informations, [voir Connecter le module PowerShell Azure Active Directory PowerShell Graph’équipe.](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="0d0d9-206">To learn more, see [Connect with the Azure Active Directory PowerShell for Graph module](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="0d0d9-207">Installer et se connecter au module PowerShell Microsoft Teams’équipe</span><span class="sxs-lookup"><span data-stu-id="0d0d9-207">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="0d0d9-208">Exécutez la commande suivante [pour installer Teams module PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (s’il n’est pas déjà installé).</span><span class="sxs-lookup"><span data-stu-id="0d0d9-208">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="0d0d9-209">Veillez à installer la version 1.0.5 ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-209">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="0d0d9-210">Exécutez ce qui suit pour vous connecter Teams et démarrer une session.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-210">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="0d0d9-211">Lorsque vous y êtes invité, connectez-vous à l’aide des mêmes informations d’identification d’administrateur que vous avez utilisées pour vous connecter à Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-211">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

#### <a name="identify-your-users"></a><span data-ttu-id="0d0d9-212">Identifier vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="0d0d9-212">Identify your users</span></span>

<span data-ttu-id="0d0d9-213">Tout d’abord, exécutez la suivante pour identifier votre personnel et vos enseignants par type de licence.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-213">First, run the following to identify your staff and educators by license type.</span></span> <span data-ttu-id="0d0d9-214">Cela vous indique les S SKUS en cours d’utilisation dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-214">This tells you what SKUs are in use in your organization.</span></span> <span data-ttu-id="0d0d9-215">Vous pouvez ensuite identifier les membres du personnel et les enseignants à qui une référence SKU est attribuée.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-215">You can then identify staff and educators that have a Faculty SKU assigned.</span></span>

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

<span data-ttu-id="0d0d9-216">Ce qui renvoie :</span><span class="sxs-lookup"><span data-stu-id="0d0d9-216">Which returns:</span></span>

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

<span data-ttu-id="0d0d9-217">Dans cet exemple, la sortie indique que la licence SKUId pour les enseignants est « e97c048c-37a4-45fb-ab50-922fbf07a370 ».</span><span class="sxs-lookup"><span data-stu-id="0d0d9-217">In this example, the output shows that the Faculty license SkuId is "e97c048c-37a4-45fb-ab50-922fbf07a370".</span></span>

> [!NOTE]
> <span data-ttu-id="0d0d9-218">Pour consulter la liste des références SKU pour l’éducation et références de référence SKU Pour l’éducation, consultez la [référence SKU pour l’éducation.](sku-reference-edu.md)</span><span class="sxs-lookup"><span data-stu-id="0d0d9-218">To see a list of Education SKUs and SKU IDs, see [Education SKU reference](sku-reference-edu.md).</span></span>

<span data-ttu-id="0d0d9-219">Ensuite, nous exécuterons l’article suivant pour identifier les utilisateurs qui ont cette licence et les collecter tous ensemble.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-219">Next, we run the following to identify the users that have this license and collect them all together.</span></span>

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a><span data-ttu-id="0d0d9-220">Affecter une stratégie en bloc</span><span class="sxs-lookup"><span data-stu-id="0d0d9-220">Assign a policy in bulk</span></span>

<span data-ttu-id="0d0d9-221">À présent, nous affectons les stratégies appropriées aux utilisateurs en bloc.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-221">Now, we assign the appropriate policies to users in bulk.</span></span> <span data-ttu-id="0d0d9-222">Le nombre maximal d’utilisateurs pour lesquels vous pouvez affecter ou mettre à jour des stratégies est de 5 000 utilisateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-222">The maximum number of users for which you can assign or update policies is 5,000 at a time.</span></span> <span data-ttu-id="0d0d9-223">Par exemple, si vous avez plus de 5 000 enseignants et membres du personnel, vous devez envoyer plusieurs lots.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-223">For example, if you have more than 5,000 staff and educators, you'll need to submit multiple batches.</span></span>

<span data-ttu-id="0d0d9-224">Exécutez la commande suivante pour attribuer une stratégie de réunion personnalisée nommée EducatorMeetingPolicy à votre personnel et à vos enseignants.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-224">Run the following to assign a custom meeting policy named EducatorMeetingPolicy to your staff and educators.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> <span data-ttu-id="0d0d9-225">Pour affecter un autre type de stratégie en bloc, tel que TeamsMesspolicy, vous devez modifier la stratégie que vous attribuez et le nom de la ```PolicyType``` ```PolicyName``` stratégie.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-225">To assign a different policy type in bulk, like TeamsMessagingPolicy, you'll need to change ```PolicyType``` to the policy that you're assigning and ```PolicyName``` to the policy name.</span></span>

#### <a name="get-the-status-of-a-bulk-assignment"></a><span data-ttu-id="0d0d9-226">Obtenir l’état d’une affectation en bloc</span><span class="sxs-lookup"><span data-stu-id="0d0d9-226">Get the status of a bulk assignment</span></span>

<span data-ttu-id="0d0d9-227">Chaque affectation en bloc renvoie un ID d’opération, que vous pouvez utiliser pour suivre l’avancement des affectations de stratégie ou identifier les échecs qui peuvent se produire.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-227">Each bulk assignment returns an operation ID, which you can use to track the progress of the policy assignments or identify any failures that might occur.</span></span> <span data-ttu-id="0d0d9-228">Par exemple, exécutez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="0d0d9-228">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

<span data-ttu-id="0d0d9-229">Pour afficher le statut d’affectation de chaque utilisateur dans l’opération de lot, exécutez la commande suivante.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-229">To view the assignment status of each user in the batch operation, run the following.</span></span> <span data-ttu-id="0d0d9-230">Les détails de chaque utilisateur sont dans la ```UserState``` propriété.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-230">Details of each user are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a><span data-ttu-id="0d0d9-231">Affecter une stratégie en bloc si vous avez plus de 5 000 utilisateurs</span><span class="sxs-lookup"><span data-stu-id="0d0d9-231">Assign a policy in bulk if you have more than 5,000 users</span></span>

<span data-ttu-id="0d0d9-232">Tout d’abord, exécutez ce qui suit pour voir le nombre de membres du personnel et d’enseignants dont vous avez :</span><span class="sxs-lookup"><span data-stu-id="0d0d9-232">First, run the following to see how many staff and educators you have:</span></span>

```powershell
$faculty.count
```

<span data-ttu-id="0d0d9-233">Au lieu de fournir la liste complète des ID utilisateur, exécutez la liste suivante pour spécifier les 5 000 premiers, puis les 5 000 suivants, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-233">Instead of providing the whole list of user IDs, run the following to specify the first 5,000, and then the next 5,000, and so on.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

<span data-ttu-id="0d0d9-234">Vous pouvez modifier la plage d’ID utilisateur jusqu’à atteindre la liste complète des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-234">You can change the range of user IDs until you reach the full list of users.</span></span> <span data-ttu-id="0d0d9-235">Par exemple, entrez pour le premier lot, utilisez-le pour le deuxième lot, entrez pour ```$faculty[0..4999``` ```$faculty[5000..9999``` le troisième ```$faculty[10000..14999``` lot, etc.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-235">For example, enter ```$faculty[0..4999``` for the first batch, use ```$faculty[5000..9999``` for the second batch, enter ```$faculty[10000..14999``` for the third batch, and so on.</span></span>

#### <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="0d0d9-236">Obtenir les stratégies attribuées à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="0d0d9-236">Get the policies assigned to a user</span></span>

<span data-ttu-id="0d0d9-237">Exécutez ce qui suit pour voir toutes les stratégies affectées à un utilisateur spécifique.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-237">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="0d0d9-238">L’exemple suivant vous montre comment obtenir les stratégies affectées à hannah@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0d0d9-238">The following example shows you how to get the policies that are assigned to hannah@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a><span data-ttu-id="0d0d9-239">FAQ</span><span class="sxs-lookup"><span data-stu-id="0d0d9-239">FAQ</span></span>

<span data-ttu-id="0d0d9-240">**Je n’ai pas l’familiarisé avec PowerShell Teams. Où puis-je obtenir plus d’informations ?**</span><span class="sxs-lookup"><span data-stu-id="0d0d9-240">**I'm not familiar with PowerShell for Teams. Where can I learn more?**</span></span>

<span data-ttu-id="0d0d9-241">Pour une vue d’ensemble de l’utilisation de PowerShell pour Teams, voir [Teams vue d’ensemble de PowerShell.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="0d0d9-241">For an overview of using PowerShell to manage Teams, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span> <span data-ttu-id="0d0d9-242">Pour plus d’informations sur les cmdlets utilisées dans cet article, voir :</span><span class="sxs-lookup"><span data-stu-id="0d0d9-242">For more information about the cmdlets used in this article, see:</span></span>

- [<span data-ttu-id="0d0d9-243">New-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="0d0d9-243">New-CsGroupPolicyAssignment</span></span>](/powershell/module/teams/new-csgrouppolicyassignment)
- [<span data-ttu-id="0d0d9-244">Get-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="0d0d9-244">Get-CsGroupPolicyAssignment</span></span>](/powershell/module/teams/get-csgrouppolicyassignment)
- [<span data-ttu-id="0d0d9-245">New-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="0d0d9-245">New-CsBatchPolicyAssignmentOperation</span></span>](/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="0d0d9-246">Get-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="0d0d9-246">Get-CsBatchPolicyAssignmentOperation</span></span>](/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="0d0d9-247">Get-CsUserPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="0d0d9-247">Get-CsUserPolicyAssignment</span></span>](/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a><span data-ttu-id="0d0d9-248">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="0d0d9-248">Related topics</span></span>

- [<span data-ttu-id="0d0d9-249">Attribuer des stratégies à vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="0d0d9-249">Assign policies to your users</span></span>](assign-policies.md)
- [<span data-ttu-id="0d0d9-250">Stratégies et packages de stratégies Teams pour l’éducation</span><span class="sxs-lookup"><span data-stu-id="0d0d9-250">Teams policies and policy packages for Education</span></span>](policy-packages-edu.md)
- [<span data-ttu-id="0d0d9-251">Gérer les stratégies de réunion dans Teams</span><span class="sxs-lookup"><span data-stu-id="0d0d9-251">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)