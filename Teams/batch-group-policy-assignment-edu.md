---
title: Attribution de stratégies à de grands ensembles d’utilisateurs dans votre établissement scolaire
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
description: Découvrez comment attribuer des stratégies à des ensembles de personnes importants dans votre établissement scolaire en fonction de l’appartenance à un groupe ou directement par le biais d’une affectation par lot dans le cadre de l’établissement scolaire à distance (télé-établissement).
f1keywords: ''
ms.openlocfilehash: afcaba9df0ff745977b84e34683c1bdfcaca0d01
ms.sourcegitcommit: 07afc959fec802db583e7111280d0035fdb6e412
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616938"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a><span data-ttu-id="81821-103">Attribution de stratégies à de grands ensembles d’utilisateurs dans votre établissement scolaire</span><span class="sxs-lookup"><span data-stu-id="81821-103">Assign policies to large sets of users in your school</span></span>

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> <span data-ttu-id="81821-104">Pour plus d’histoire sur l’attribution de stratégies dans Microsoft Teams, voir [attribuer des stratégies à vos utilisateurs dans teams](assign-policies.md).</span><span class="sxs-lookup"><span data-stu-id="81821-104">For the larger story on assigning policies in Microsoft Teams, see [Assign policies to your users in Teams](assign-policies.md).</span></span>

## <a name="overview"></a><span data-ttu-id="81821-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="81821-105">Overview</span></span>

<span data-ttu-id="81821-106">Avez-vous besoin d’offrir aux étudiants et aux enseignants l’accès à différentes fonctionnalités dans Microsoft teams ?</span><span class="sxs-lookup"><span data-stu-id="81821-106">Do you need to give your students and educators access to different features in Microsoft Teams?</span></span> <span data-ttu-id="81821-107">Vous pouvez rapidement identifier les utilisateurs de votre organisation par type de licence, puis leur attribuer la politique appropriée.</span><span class="sxs-lookup"><span data-stu-id="81821-107">You can quickly identify the users in your organization by license type and then assign them the appropriate policy.</span></span> <span data-ttu-id="81821-108">Ce didacticiel vous explique comment affecter une stratégie de réunion à de nombreux utilisateurs de votre établissement scolaire.</span><span class="sxs-lookup"><span data-stu-id="81821-108">This tutorial shows you how to assign a meeting policy to large sets of users in your school.</span></span> <span data-ttu-id="81821-109">Vous pouvez attribuer des stratégies à l’aide du centre d’administration Microsoft teams et de PowerShell et nous allons vous présenter les deux manières.</span><span class="sxs-lookup"><span data-stu-id="81821-109">You can assign policies using the Microsoft Teams admin center and PowerShell and we'll show you both ways.</span></span>

<span data-ttu-id="81821-110">Vous pouvez assigner une stratégie de réunion à un groupe de sécurité que les utilisateurs sont membres de ou directement aux utilisateurs lors de l’évolution via une affectation de stratégie de lot.</span><span class="sxs-lookup"><span data-stu-id="81821-110">You can assign a meeting policy to a security group that the users are members of or directly to users at scale through a batch policy assignment.</span></span> <span data-ttu-id="81821-111">Vous apprendrez comment :</span><span class="sxs-lookup"><span data-stu-id="81821-111">You'll learn how to:</span></span>

- <span data-ttu-id="81821-112">**Utiliser une [affectation de stratégie aux groupes](#assign-a-policy-to-a-group) pour attribuer une stratégie de réunion à un groupe de sécurité (recommandé)**.</span><span class="sxs-lookup"><span data-stu-id="81821-112">**Use [policy assignment to groups](#assign-a-policy-to-a-group) to assign a meeting policy to a security group (recommended)**.</span></span> <span data-ttu-id="81821-113">Cette méthode vous permet d’affecter une stratégie basée sur l’appartenance au groupe.</span><span class="sxs-lookup"><span data-stu-id="81821-113">This method lets you assign a policy based on group membership.</span></span> <span data-ttu-id="81821-114">Vous pouvez affecter une stratégie à un groupe de sécurité ou une liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="81821-114">You can assign a policy to a security group or distribution list.</span></span> <span data-ttu-id="81821-115">Les membres étant ajoutés ou supprimés du groupe, leurs affectations de stratégie héritées sont mises à jour en conséquence.</span><span class="sxs-lookup"><span data-stu-id="81821-115">As members are added to or removed from the group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="81821-116">Nous vous recommandons d’utiliser cette méthode, car elle réduit le temps de gestion des stratégies pour les nouveaux utilisateurs ou lorsque les rôles des utilisateurs changent.</span><span class="sxs-lookup"><span data-stu-id="81821-116">We recommend you use this method because it reduces the time to manage policies for new users or when users' roles change.</span></span> <span data-ttu-id="81821-117">Cette méthode est idéale pour les groupes d’utilisateurs 50 000, mais elle fonctionne également avec des groupes de plus grande taille.</span><span class="sxs-lookup"><span data-stu-id="81821-117">This method works best for groups of up to 50,000 users but will also work with larger groups.</span></span>

- <span data-ttu-id="81821-118">**Utiliser une [affectation de stratégie de batch](assign-policies.md#assign-a-policy-to-a-batch-of-users) pour attribuer une stratégie de réunion directement aux utilisateurs en bloc**.</span><span class="sxs-lookup"><span data-stu-id="81821-118">**Use [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users) to assign a meeting policy directly to users in bulk**.</span></span> <span data-ttu-id="81821-119">Vous pouvez assigner une stratégie pour un maximum de 5 000 utilisateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="81821-119">You can assign a policy for up to 5,000 users at a time.</span></span> <span data-ttu-id="81821-120">Si vous disposez de plus de 5 000 utilisateurs, vous pouvez en saisir plusieurs.</span><span class="sxs-lookup"><span data-stu-id="81821-120">If you have more than 5,000 users, you can submit multiple batches.</span></span> <span data-ttu-id="81821-121">Avec cette méthode, lorsque vous avez de nouveaux utilisateurs, vous devez réexécuter l’affectation de lot pour affecter la stratégie à ces nouveaux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="81821-121">With this method, when you have new users, you'll need to re-run the batch assignment to assign the policy to those new users.</span></span>

<span data-ttu-id="81821-122">Rappelez-vous que dans Teams, les utilisateurs obtiennent automatiquement la stratégie globale par défaut de l’organisation d’un type de stratégie d’équipe, sauf si vous créez et attribuez une stratégie personnalisée.</span><span class="sxs-lookup"><span data-stu-id="81821-122">Remember that in Teams, users automatically get the Global (Org-wide default) policy for a Teams policy type unless you create and assign a custom policy.</span></span> <span data-ttu-id="81821-123">Dans la mesure où la population étudiant est souvent le plus grand nombre d’utilisateurs et qu’ils reçoivent souvent les paramètres les plus restrictifs, nous vous recommandons de procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="81821-123">Because the student population is often the largest set of users and they often receive the most restrictive settings, we recommend that you do the following:</span></span>

- <span data-ttu-id="81821-124">Créez une stratégie personnalisée qui accepte les principales fonctionnalités, telles que la conversation privée et la planification de réunions, et attribuez-la à vos employés et enseignants.</span><span class="sxs-lookup"><span data-stu-id="81821-124">Create a custom policy that allows core capabilities such as private chat and meeting scheduling and assign the policy to your staff and educators.</span></span>
- <span data-ttu-id="81821-125">Affectez la stratégie personnalisée à votre personnel et aux enseignants.</span><span class="sxs-lookup"><span data-stu-id="81821-125">Assign the custom policy to your staff and educators.</span></span>
- <span data-ttu-id="81821-126">Modification et application de la stratégie globale par défaut de l’Organisation pour restreindre les capacités des étudiants.</span><span class="sxs-lookup"><span data-stu-id="81821-126">Edit and apply the Global (Org-wide default) policy to restrict capabilities for students.</span></span>

<span data-ttu-id="81821-127">Gardez à l’esprit que la politique globale s’applique à tous les utilisateurs de votre établissement scolaire tant que vous n’avez pas créé de stratégie personnalisée et que vous l’avez affectée à votre personnel et aux enseignants.</span><span class="sxs-lookup"><span data-stu-id="81821-127">Keep in mind that the Global policy will apply to all users in your school until you create a custom policy and assign it to your staff and educators.</span></span>

<span data-ttu-id="81821-128">Dans ce didacticiel, les étudiants recevront la politique de réunion globale et nous affecterons une stratégie de réunion personnalisée nommée EducatorMeetingPolicy au personnel et aux enseignants.</span><span class="sxs-lookup"><span data-stu-id="81821-128">In this tutorial, students will get the Global meeting policy and we'll assign a custom meeting policy named EducatorMeetingPolicy to staff and educators.</span></span> <span data-ttu-id="81821-129">Nous partons du principe que vous avez modifié la politique globale afin d’adapter les paramètres de la réunion aux étudiants et [créé une stratégie personnalisée](policy-packages-edu.md) qui définit l’interface de réunion pour les membres du personnel et les enseignants.</span><span class="sxs-lookup"><span data-stu-id="81821-129">We assume that you've edited the Global policy to tailor meeting settings for students and [created a custom policy](policy-packages-edu.md) that defines the meeting experience for staff and educators.</span></span>

![Capture d’écran de la page stratégies de réunion dans le centre d’administration teams](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="81821-131">Assigner une stratégie à un groupe</span><span class="sxs-lookup"><span data-stu-id="81821-131">Assign a policy to a group</span></span>

<span data-ttu-id="81821-132">Suivez ces étapes pour créer un groupe de sécurité pour votre personnel et vos enseignants, puis attribuez une stratégie de réunion personnalisée nommée EducatorMeetingPolicy à ce groupe de sécurité.</span><span class="sxs-lookup"><span data-stu-id="81821-132">Follow these steps to create a security group for your staff and educators, and then assign a custom meeting policy named EducatorMeetingPolicy to that security group.</span></span>

### <a name="before-you-get-started"></a><span data-ttu-id="81821-133">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="81821-133">Before you get started</span></span>

> [!IMPORTANT]
> <span data-ttu-id="81821-134">Lorsque vous affectez une stratégie à un groupe, l’affectation de stratégie est propagée aux membres du groupe en fonction des règles de priorité.</span><span class="sxs-lookup"><span data-stu-id="81821-134">When you assign a policy to a group, the policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="81821-135">Par exemple, si un utilisateur dispose d’une stratégie directement affectée (ou par le biais d’une affectation par lot), cette stratégie est prioritaire sur une stratégie héritée d’un groupe.</span><span class="sxs-lookup"><span data-stu-id="81821-135">For example, if a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence over a policy that's inherited from a group.</span></span> <span data-ttu-id="81821-136">Par ailleurs, si un utilisateur dispose d’une stratégie de réunion qui lui a été directement affectée, vous devez supprimer celle-ci de l’utilisateur pour pouvoir hériter d’une stratégie de réunion d’un groupe de sécurité.</span><span class="sxs-lookup"><span data-stu-id="81821-136">This also means that if a user has a meeting policy that was directly assigned to them, you'll have to remove that meeting policy from the user before they can inherit a meeting policy from a security group.</span></span>

<span data-ttu-id="81821-137">Avant de commencer, il est important de comprendre les [règles de précédence](assign-policies.md#precedence-rules) et le [classement des affectations de groupe](assign-policies.md#group-assignment-ranking).</span><span class="sxs-lookup"><span data-stu-id="81821-137">Before you get started, it's important to understand [precedence rules](assign-policies.md#precedence-rules) and [group assignment ranking](assign-policies.md#group-assignment-ranking).</span></span> <span data-ttu-id="81821-138">**Vérifiez que vous avez bien lu et compris les concepts décrits dans [ce que vous devez savoir sur l’attribution de stratégies à des groupes](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**.</span><span class="sxs-lookup"><span data-stu-id="81821-138">**Make sure that you read and understand the concepts in [What you need to know about policy assignment to groups](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**.</span></span>

<span data-ttu-id="81821-139">Pour pouvoir hériter d’une stratégie de réunion à partir d’un groupe de sécurité, vous devez effectuer toutes les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="81821-139">You'll need to complete all these steps for your staff and educators to inherit a meeting policy from a security group.</span></span>

1. <span data-ttu-id="81821-140">[Créer des groupes de sécurité](#create-security-groups).</span><span class="sxs-lookup"><span data-stu-id="81821-140">[Create security groups](#create-security-groups).</span></span>
2. <span data-ttu-id="81821-141">[Assigner une stratégie à un groupe de sécurité](#assign-a-policy-to-a-security-group).</span><span class="sxs-lookup"><span data-stu-id="81821-141">[Assign a policy to a security group](#assign-a-policy-to-a-security-group).</span></span>
3. <span data-ttu-id="81821-142">[Supprimez une stratégie attribuée directement aux utilisateurs](#remove-a-policy-that-was-directly-assigned-to-users).</span><span class="sxs-lookup"><span data-stu-id="81821-142">[Remove a policy that was directly assigned to users](#remove-a-policy-that-was-directly-assigned-to-users).</span></span>

### <a name="create-security-groups"></a><span data-ttu-id="81821-143">Créer des groupes de sécurité</span><span class="sxs-lookup"><span data-stu-id="81821-143">Create security groups</span></span>

<span data-ttu-id="81821-144">Tout d’abord, créez un groupe de sécurité pour votre personnel et vos enseignants.</span><span class="sxs-lookup"><span data-stu-id="81821-144">First, create a security group for your staff and educators.</span></span>

<span data-ttu-id="81821-145">Avec [School Data Sync](https://docs.microsoft.com/SchoolDataSync/) , vous pouvez [facilement créer des enseignants et des étudiants](https://docs.microsoft.com/SchoolDataSync/edu-security-groups) au sein de votre établissement scolaire.</span><span class="sxs-lookup"><span data-stu-id="81821-145">With [School Data Sync](https://docs.microsoft.com/SchoolDataSync/) (SDS), you can [easily create security groups educators and students](https://docs.microsoft.com/SchoolDataSync/edu-security-groups) in your school.</span></span> <span data-ttu-id="81821-146">Nous vous recommandons d’utiliser SDS pour créer des groupes de sécurité dont vous avez besoin pour gérer les stratégies de votre établissement scolaire.</span><span class="sxs-lookup"><span data-stu-id="81821-146">We recommend that you use SDS to create the security groups you need to manage policies for your school.</span></span>

<span data-ttu-id="81821-147">Si vous ne parvenez pas à déployer le SD au sein de votre environnement, utilisez [ce script PowerShell](scripts/powershell-script-security-groups-edu.md) pour créer deux groupes de sécurité, l’un pour tous les membres du personnel et les enseignants qui disposent d’une licence pour les enseignants attribués et une autre pour tous les étudiants qui disposent d’une licence étudiant.</span><span class="sxs-lookup"><span data-stu-id="81821-147">If you're unable to deploy SDS within your environment, use [this PowerShell script](scripts/powershell-script-security-groups-edu.md) to create two security groups, one for all staff and educators who have a Faculty license assigned and another for all students who have a Student license assigned.</span></span> <span data-ttu-id="81821-148">Vous devez exécuter le script en routine pour que les groupes soient actualisés et à jour.</span><span class="sxs-lookup"><span data-stu-id="81821-148">You'll need to run this script routinely to keep the groups fresh and up to date.</span></span>

### <a name="assign-a-policy-to-a-security-group"></a><span data-ttu-id="81821-149">Assigner une stratégie à un groupe de sécurité</span><span class="sxs-lookup"><span data-stu-id="81821-149">Assign a policy to a security group</span></span>

#### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="81821-150">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="81821-150">Using the Microsoft Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="81821-151">Pour l’instant, l’attribution de stratégies aux groupes à l’aide du centre d’administration Microsoft teams n’est disponible que pour les stratégies d’appel d’équipe, la stratégie de parc d’appels d’équipe, la stratégie d’équipe, la stratégie des événements en direct Teams, la stratégie de réunion équipes et la stratégie de messagerie</span><span class="sxs-lookup"><span data-stu-id="81821-151">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="81821-152">Pour les autres types de stratégies, utilisez PowerShell.</span><span class="sxs-lookup"><span data-stu-id="81821-152">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="81821-153">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, **accédez à**  >  **stratégies de réunion**.</span><span class="sxs-lookup"><span data-stu-id="81821-153">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="81821-154">Sélectionnez l’onglet **affectation de stratégie de groupe** .</span><span class="sxs-lookup"><span data-stu-id="81821-154">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="81821-155">Sélectionnez **Ajouter un groupe**, puis, dans le volet **affecter une stratégie à un groupe** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="81821-155">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>

    ![Capture d’écran du volet modifier les paramètres affichant la stratégie de réunion](media/batch-group-policy-assignment-edu-group.png)
    1. <span data-ttu-id="81821-157">Dans la zone **Sélectionner un groupe** , recherchez et ajoutez le groupe de sécurité contenant votre personnel et vos enseignants.</span><span class="sxs-lookup"><span data-stu-id="81821-157">In the **Select a group** box, search for and add the security group that contains your staff and educators.</span></span>
    2. <span data-ttu-id="81821-158">Dans la zone **Sélectionner un rang** , entrez **1**.</span><span class="sxs-lookup"><span data-stu-id="81821-158">In the **Select rank** box, enter **1**.</span></span>
    3. <span data-ttu-id="81821-159">Dans la zone **Sélectionner une stratégie** , sélectionnez **EducatorMeetingPolicy**.</span><span class="sxs-lookup"><span data-stu-id="81821-159">In the **Select a policy** box, select **EducatorMeetingPolicy**.</span></span>
    4. <span data-ttu-id="81821-160">Sélectionnez **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="81821-160">Select **Apply**.</span></span>

<span data-ttu-id="81821-161">Pour supprimer une affectation de stratégie de groupe, dans l’onglet **affectation de stratégie de groupe** de la page de stratégie, sélectionnez l’affectation de groupe, puis sélectionnez **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="81821-161">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="81821-162">Pour modifier le classement d’une affectation de groupe, vous devez d’abord supprimer l’affectation de stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="81821-162">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="81821-163">Ensuite, suivez les étapes ci-dessus pour affecter la stratégie à un groupe.</span><span class="sxs-lookup"><span data-stu-id="81821-163">Then, follow the steps above to assign the policy to a group.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="81821-164">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="81821-164">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="81821-165">Pour l’instant, l’affectation de stratégie à des groupes à l’aide de PowerShell n’est pas disponible pour tous les types de stratégie d’équipe.</span><span class="sxs-lookup"><span data-stu-id="81821-165">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="81821-166">Pour obtenir la liste des types de stratégie pris en charge, voir [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) .</span><span class="sxs-lookup"><span data-stu-id="81821-166">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="81821-167">Installer le module Microsoft teams PowerShell et s’y connecter</span><span class="sxs-lookup"><span data-stu-id="81821-167">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="81821-168">Exécutez la commande suivante pour installer le [module teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (si ce n’est pas déjà fait).</span><span class="sxs-lookup"><span data-stu-id="81821-168">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="81821-169">Vérifiez que vous avez installé la version 1.0.5 ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="81821-169">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="81821-170">Exécutez la commande suivante pour vous connecter à teams et démarrer une session.</span><span class="sxs-lookup"><span data-stu-id="81821-170">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="81821-171">Lorsque vous y êtes invité, connectez-vous à l’aide de vos informations d’identification d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="81821-171">When you're prompted, sign in using your admin credentials.</span></span>

##### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="81821-172">Assigner une stratégie à un groupe</span><span class="sxs-lookup"><span data-stu-id="81821-172">Assign a policy to a group</span></span>

<span data-ttu-id="81821-173">Exécutez la commande suivante pour affecter la stratégie de réunion nommée EducatorMeetingPolicy au groupe de sécurité qui contient votre personnel et vos enseignants et définissez le classement des affectations sur 1.</span><span class="sxs-lookup"><span data-stu-id="81821-173">Run the following to assign the meeting policy named EducatorMeetingPolicy to the security group that contains your staff and educators and set the assignment ranking to 1.</span></span> <span data-ttu-id="81821-174">Vous pouvez spécifier un groupe de sécurité à l’aide d’un ID d’objet, d’une adresse SIP (Session Initiation Protocol) ou d’une adresse de messagerie.</span><span class="sxs-lookup"><span data-stu-id="81821-174">You can specify a security group by using the object Id, Session Initiation Protocol (SIP) address, or email address.</span></span> <span data-ttu-id="81821-175">Dans cet exemple, nous utilisons une adresse de messagerie (staff-faculty@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="81821-175">In this example, we use an email address (staff-faculty@contoso.com).</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a><span data-ttu-id="81821-176">Supprimer une stratégie attribuée directement aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="81821-176">Remove a policy that was directly assigned to users</span></span>

<span data-ttu-id="81821-177">N’oubliez pas que si un utilisateur a été directement affecté à une stratégie (par le biais d’une affectation individuelle ou par lot), cette stratégie est prioritaire.</span><span class="sxs-lookup"><span data-stu-id="81821-177">Remember that if a user was directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="81821-178">Autrement dit, si un utilisateur dispose d’une stratégie de réunion qui lui a été directement affectée, vous devez supprimer cette stratégie de réunion de l’utilisateur pour pouvoir hériter d’une stratégie de réunion d’un groupe de sécurité.</span><span class="sxs-lookup"><span data-stu-id="81821-178">This means that if a user has a meeting policy that was directly assigned to them, you'll have to remove that meeting policy from the user before they can inherit a meeting policy from a security group.</span></span>

<span data-ttu-id="81821-179">Pour en savoir plus, voir [ce que vous devez savoir sur l’attribution de stratégies à des groupes](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups).</span><span class="sxs-lookup"><span data-stu-id="81821-179">To learn more, see [What you need to know about policy assignment to groups](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups).</span></span>

<span data-ttu-id="81821-180">Suivez ces étapes pour supprimer la politique de réunion qui a été directement affectée à votre personnel et aux enseignants.</span><span class="sxs-lookup"><span data-stu-id="81821-180">Follow these steps to remove the meeting policy that was directly assigned to your staff and educators.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="81821-181">Installer le module Microsoft teams PowerShell et s’y connecter</span><span class="sxs-lookup"><span data-stu-id="81821-181">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="81821-182">Exécutez la commande suivante pour installer le [module teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (si ce n’est pas déjà fait).</span><span class="sxs-lookup"><span data-stu-id="81821-182">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="81821-183">Vérifiez que vous avez installé la version 1.0.5 ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="81821-183">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="81821-184">Exécutez la commande suivante pour vous connecter à teams et démarrer une session.</span><span class="sxs-lookup"><span data-stu-id="81821-184">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="81821-185">Lorsque vous y êtes invité, connectez-vous à l’aide des informations d’identification d’administrateur que vous avez utilisées pour vous connecter à Azure AD.</span><span class="sxs-lookup"><span data-stu-id="81821-185">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a><span data-ttu-id="81821-186">Annuler l’affectation d’une stratégie attribuée directement aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="81821-186">Unassign a policy that was directly assigned to users</span></span>

<span data-ttu-id="81821-187">Exécutez la commande suivante pour supprimer une stratégie de réunion des utilisateurs auxquels cette stratégie a été directement affectée.</span><span class="sxs-lookup"><span data-stu-id="81821-187">Run the following to remove a meeting policy from users who were directly assigned that policy.</span></span> <span data-ttu-id="81821-188">Vous pouvez spécifier des utilisateurs par adresse de courrier ou ID d’objet.</span><span class="sxs-lookup"><span data-stu-id="81821-188">You can specify users by email address or object ID.</span></span>

<span data-ttu-id="81821-189">Dans cet exemple, la stratégie de réunion est supprimée des utilisateurs spécifiés par son adresse de courrier.</span><span class="sxs-lookup"><span data-stu-id="81821-189">In this example, the meeting policy is removed from users specified by their email address.</span></span>

```powershell
$users_ids = @("reda@contoso.com", "nikica@contoso.com", "jamie@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

<span data-ttu-id="81821-190">Dans cet exemple, la stratégie de réunion est supprimée de la liste des utilisateurs dans un fichier texte nommé user_ids.txt.</span><span class="sxs-lookup"><span data-stu-id="81821-190">In this example, the meeting policy is removed from the list of users in a text file named user_ids.txt.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

##### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="81821-191">Obtenir des affectations de stratégie pour un groupe</span><span class="sxs-lookup"><span data-stu-id="81821-191">Get policy assignments for a group</span></span>

<span data-ttu-id="81821-192">Exécutez la commande suivante pour afficher toutes les stratégies affectées à un groupe de sécurité spécifique.</span><span class="sxs-lookup"><span data-stu-id="81821-192">Run the following to see all the policies assigned to a specific security group.</span></span> <span data-ttu-id="81821-193">Notez que les groupes sont toujours répertoriés par leur ID de groupe même si l’adresse ou l’adresse de messagerie SIP a été utilisée pour affecter la stratégie.</span><span class="sxs-lookup"><span data-stu-id="81821-193">Note that groups are always listed by their group ID even if its SIP address or email address was used to assign the policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="81821-194">Obtention des stratégies affectées à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="81821-194">Get the policies assigned to a user</span></span>

<span data-ttu-id="81821-195">Exécutez la commande suivante pour afficher toutes les stratégies affectées à un utilisateur spécifique.</span><span class="sxs-lookup"><span data-stu-id="81821-195">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="81821-196">L’exemple suivant vous montre comment obtenir les stratégies affectées à reda@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="81821-196">The following example shows you how to get the policies that are assigned to reda@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="81821-197">Attribuer une stratégie à un lot d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="81821-197">Assign a policy to a batch of users</span></span>

<span data-ttu-id="81821-198">Suivez ces étapes pour attribuer une stratégie de réunion personnalisée nommée EducatorMeetingPolicy directement à votre personnel et aux enseignants en bloc.</span><span class="sxs-lookup"><span data-stu-id="81821-198">Follow these steps to assign a custom meeting policy named EducatorMeetingPolicy directly to your staff and educators in bulk.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="81821-199">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="81821-199">Using PowerShell</span></span>

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a><span data-ttu-id="81821-200">Se connecter à Azure AD PowerShell pour le module Graph et au module PowerShell teams</span><span class="sxs-lookup"><span data-stu-id="81821-200">Connect to the Azure AD PowerShell for Graph module and the Teams PowerShell module</span></span>

<span data-ttu-id="81821-201">Avant d’effectuer les étapes décrites dans cet article, vous devez installer et vous connecter à Azure AD PowerShell pour le module Graph (afin d’identifier les utilisateurs selon leurs licences affectées) et le module Microsoft teams PowerShell (pour affecter les stratégies à ces utilisateurs).</span><span class="sxs-lookup"><span data-stu-id="81821-201">Before you perform the steps in this article, you'll need to install and connect to the Azure AD PowerShell for Graph module (to identify users by their assigned licenses) and the Microsoft Teams PowerShell module (to assign the policies to those users).</span></span>

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a><span data-ttu-id="81821-202">Installer et se connecter à Azure AD PowerShell pour le module Graph</span><span class="sxs-lookup"><span data-stu-id="81821-202">Install and connect to the Azure AD PowerShell for Graph module</span></span>

<span data-ttu-id="81821-203">Ouvrez une invite de commandes Windows PowerShell avec élévation de privilèges (exécutez Windows PowerShell en tant qu’administrateur), puis exécutez la commande suivante pour installer Azure Active Directory PowerShell pour le module Graph.</span><span class="sxs-lookup"><span data-stu-id="81821-203">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator), and then run the following to install the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Install-Module -Name AzureAD
```

<span data-ttu-id="81821-204">Exécutez la commande suivante pour vous connecter à Azure AD.</span><span class="sxs-lookup"><span data-stu-id="81821-204">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="81821-205">Lorsque vous y êtes invité, connectez-vous à l’aide de vos informations d’identification d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="81821-205">When you're prompted, sign in using your admin credentials.</span></span>

<span data-ttu-id="81821-206">Pour en savoir plus, voir [se connecter à l’aide d’Azure Active Directory PowerShell pour le module Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="81821-206">To learn more, see [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="81821-207">Installer le module Microsoft teams PowerShell et s’y connecter</span><span class="sxs-lookup"><span data-stu-id="81821-207">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="81821-208">Exécutez la commande suivante pour installer le [module teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (si ce n’est pas déjà fait).</span><span class="sxs-lookup"><span data-stu-id="81821-208">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="81821-209">Vérifiez que vous avez installé la version 1.0.5 ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="81821-209">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="81821-210">Exécutez la commande suivante pour vous connecter à teams et démarrer une session.</span><span class="sxs-lookup"><span data-stu-id="81821-210">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="81821-211">Lorsque vous y êtes invité, connectez-vous à l’aide des informations d’identification d’administrateur que vous avez utilisées pour vous connecter à Azure AD.</span><span class="sxs-lookup"><span data-stu-id="81821-211">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

#### <a name="identify-your-users"></a><span data-ttu-id="81821-212">Identifier vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="81821-212">Identify your users</span></span>

<span data-ttu-id="81821-213">Tout d’abord, exécutez la commande suivante pour identifier votre personnel et vos enseignants par type de licence.</span><span class="sxs-lookup"><span data-stu-id="81821-213">First, run the following to identify your staff and educators by license type.</span></span> <span data-ttu-id="81821-214">Cette option vous indique les références (SKU) utilisées au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="81821-214">This tells you what SKUs are in use in your organization.</span></span> <span data-ttu-id="81821-215">Vous pouvez ensuite identifier le personnel et les enseignants qui ont affecté une référence pour les enseignants.</span><span class="sxs-lookup"><span data-stu-id="81821-215">You can then identify staff and educators that have a Faculty SKU assigned.</span></span>

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

<span data-ttu-id="81821-216">Qui renvoie :</span><span class="sxs-lookup"><span data-stu-id="81821-216">Which returns:</span></span>

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

<span data-ttu-id="81821-217">Dans cet exemple, la sortie indique que la licence Université SkuId est « e97c048c-37a4-45FB-ab50-922fbf07a370 ».</span><span class="sxs-lookup"><span data-stu-id="81821-217">In this example, the output shows that the Faculty license SkuId is "e97c048c-37a4-45fb-ab50-922fbf07a370".</span></span>

> [!NOTE]
> <span data-ttu-id="81821-218">Pour afficher une liste des références SKU et des références SKU éducation, voir référence des références [SKU éducation](sku-reference-edu.md).</span><span class="sxs-lookup"><span data-stu-id="81821-218">To see a list of Education SKUs and SKU IDs, see [Education SKU reference](sku-reference-edu.md).</span></span>

<span data-ttu-id="81821-219">Ensuite, nous exécutons la commande suivante pour identifier les utilisateurs disposant de cette licence et les rassembler.</span><span class="sxs-lookup"><span data-stu-id="81821-219">Next, we run the following to identify the users that have this license and collect them all together.</span></span>

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a><span data-ttu-id="81821-220">Assigner une stratégie en bloc</span><span class="sxs-lookup"><span data-stu-id="81821-220">Assign a policy in bulk</span></span>

<span data-ttu-id="81821-221">À présent, nous affectons les stratégies appropriées aux utilisateurs en bloc.</span><span class="sxs-lookup"><span data-stu-id="81821-221">Now, we assign the appropriate policies to users in bulk.</span></span> <span data-ttu-id="81821-222">Le nombre maximal d’utilisateurs pour lesquels vous pouvez attribuer ou mettre à jour des stratégies est 5 000 à la fois.</span><span class="sxs-lookup"><span data-stu-id="81821-222">The maximum number of users for which you can assign or update policies is 5,000 at a time.</span></span> <span data-ttu-id="81821-223">Par exemple, si vous avez plus de 5 000 employé et enseignants, vous devrez ennoter plusieurs lots.</span><span class="sxs-lookup"><span data-stu-id="81821-223">For example, if you have more than 5,000 staff and educators, you'll need to submit multiple batches.</span></span>

<span data-ttu-id="81821-224">Exécutez la commande suivante pour affecter une stratégie de réunion personnalisée nommée EducatorMeetingPolicy à votre personnel et aux enseignants.</span><span class="sxs-lookup"><span data-stu-id="81821-224">Run the following to assign a custom meeting policy named EducatorMeetingPolicy to your staff and educators.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> <span data-ttu-id="81821-225">Pour attribuer un type de stratégie différent en bloc (par exemple, TeamsMessagingPolicy), vous devez utiliser ```PolicyType``` la stratégie que vous affectez et ```PolicyName``` le nom de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="81821-225">To assign a different policy type in bulk, like TeamsMessagingPolicy, you'll need to change ```PolicyType``` to the policy that you're assigning and ```PolicyName``` to the policy name.</span></span>

#### <a name="get-the-status-of-a-bulk-assignment"></a><span data-ttu-id="81821-226">Obtenir l’état d’une affectation en bloc</span><span class="sxs-lookup"><span data-stu-id="81821-226">Get the status of a bulk assignment</span></span>

<span data-ttu-id="81821-227">Chaque affectation en bloc renvoie un ID d’opération, que vous pouvez utiliser pour effectuer le suivi de l’avancement des affectations de stratégie ou identifier les échecs qui peuvent se produire.</span><span class="sxs-lookup"><span data-stu-id="81821-227">Each bulk assignment returns an operation ID, which you can use to track the progress of the policy assignments or identify any failures that might occur.</span></span> <span data-ttu-id="81821-228">Par exemple, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="81821-228">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

<span data-ttu-id="81821-229">Pour afficher l’état de l’affectation de chaque utilisateur dans l’opération de traitement par lot, exécutez la commande suivante.</span><span class="sxs-lookup"><span data-stu-id="81821-229">To view the assignment status of each user in the batch operation, run the following.</span></span> <span data-ttu-id="81821-230">Les détails de chaque utilisateur sont dans la ```UserState``` propriété.</span><span class="sxs-lookup"><span data-stu-id="81821-230">Details of each user are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a><span data-ttu-id="81821-231">Affecter une stratégie en bloc si vous avez plus de 5 000 utilisateurs</span><span class="sxs-lookup"><span data-stu-id="81821-231">Assign a policy in bulk if you have more than 5,000 users</span></span>

<span data-ttu-id="81821-232">Tout d’abord, exécutez la commande suivante pour voir combien de personnes et de enseignants vous avez :</span><span class="sxs-lookup"><span data-stu-id="81821-232">First, run the following to see how many staff and educators you have:</span></span>

```powershell
$faculty.count
```

<span data-ttu-id="81821-233">Au lieu de fournir la liste complète des identifiants utilisateur, exécutez la commande suivante pour spécifier le premier 5 000, puis la 5 000 suivante, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="81821-233">Instead of providing the whole list of user IDs, run the following to specify the first 5,000, and then the next 5,000, and so on.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

<span data-ttu-id="81821-234">Vous pouvez modifier la plage d’ID utilisateur jusqu’à ce que vous accédiez à la liste complète des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="81821-234">You can change the range of user IDs until you reach the full list of users.</span></span> <span data-ttu-id="81821-235">Par exemple, entrez pour le ```$faculty[0..4999``` premier lot, utilisez ```$faculty[5000..9999``` pour le second lot, entrez ```$faculty[10000..14999``` pour le troisième lot, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="81821-235">For example, enter ```$faculty[0..4999``` for the first batch, use ```$faculty[5000..9999``` for the second batch, enter ```$faculty[10000..14999``` for the third batch, and so on.</span></span>

#### <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="81821-236">Obtention des stratégies affectées à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="81821-236">Get the policies assigned to a user</span></span>

<span data-ttu-id="81821-237">Exécutez la commande suivante pour afficher toutes les stratégies affectées à un utilisateur spécifique.</span><span class="sxs-lookup"><span data-stu-id="81821-237">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="81821-238">L’exemple suivant vous montre comment obtenir les stratégies affectées à hannah@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="81821-238">The following example shows you how to get the policies that are assigned to hannah@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a><span data-ttu-id="81821-239">FAQ</span><span class="sxs-lookup"><span data-stu-id="81821-239">FAQ</span></span>

<span data-ttu-id="81821-240">**Je ne connais pas PowerShell pour Teams. Où trouver d’autres informations ?**</span><span class="sxs-lookup"><span data-stu-id="81821-240">**I'm not familiar with PowerShell for Teams. Where can I learn more?**</span></span>

<span data-ttu-id="81821-241">Pour obtenir une vue d’ensemble de l’utilisation de PowerShell pour gérer Teams, voir [vue d’ensemble de teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="81821-241">For an overview of using PowerShell to manage Teams, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span> <span data-ttu-id="81821-242">Pour plus d’informations sur les applets de vue utilisées dans cet article, voir :</span><span class="sxs-lookup"><span data-stu-id="81821-242">For more information about the cmdlets used in this article, see:</span></span>

- [<span data-ttu-id="81821-243">Nouveau-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="81821-243">New-CsGroupPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)
- [<span data-ttu-id="81821-244">Get-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="81821-244">Get-CsGroupPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment)
- [<span data-ttu-id="81821-245">Nouveau-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="81821-245">New-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="81821-246">Get-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="81821-246">Get-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="81821-247">Get-CsUserPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="81821-247">Get-CsUserPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a><span data-ttu-id="81821-248">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="81821-248">Related topics</span></span>

- [<span data-ttu-id="81821-249">Attribution de stratégies à vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="81821-249">Assign policies to your users</span></span>](assign-policies.md)
- [<span data-ttu-id="81821-250">Stratégies d’équipe et packages de stratégie pour l’éducation</span><span class="sxs-lookup"><span data-stu-id="81821-250">Teams policies and policy packages for Education</span></span>](policy-packages-edu.md)
- [<span data-ttu-id="81821-251">Gérer les stratégies de réunion dans teams</span><span class="sxs-lookup"><span data-stu-id="81821-251">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
