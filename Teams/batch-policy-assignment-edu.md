---
title: Attribution de stratégies à de grands ensembles d’utilisateurs dans votre établissement scolaire
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: saragava,karsmith
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
description: Découvrez comment utiliser une affectation de stratégie de lot pour attribuer des stratégies aux utilisateurs de votre établissement d’enseignement en bloc pour les usages de l’établissement scolaire
f1keywords: ''
ms.openlocfilehash: 5772a260642b09232e4df5eec57751a39ec2a74a
ms.sourcegitcommit: 86b0956680b867b8bedb2e969220b8006829ee53
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/28/2020
ms.locfileid: "44410439"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a><span data-ttu-id="7e146-103">Attribution de stratégies à de grands ensembles d’utilisateurs dans votre établissement scolaire</span><span class="sxs-lookup"><span data-stu-id="7e146-103">Assign policies to large sets of users in your school</span></span>

<span data-ttu-id="7e146-104">Avez-vous besoin d’offrir aux étudiants et aux enseignants l’accès à différentes fonctionnalités dans Microsoft teams ?</span><span class="sxs-lookup"><span data-stu-id="7e146-104">Do you need to give your students and educators access to different features in Microsoft Teams?</span></span> <span data-ttu-id="7e146-105">Vous pouvez rapidement identifier les utilisateurs de votre organisation par type de licence, puis leur attribuer la politique appropriée.</span><span class="sxs-lookup"><span data-stu-id="7e146-105">You can quickly identify the users in your organization by license type and then assign them the appropriate policy.</span></span> <span data-ttu-id="7e146-106">Ce didacticiel vous explique comment utiliser une [affectation de stratégie de batch](assign-policies.md#assign-a-policy-to-a-batch-of-users) pour assigner une stratégie de réunion aux utilisateurs en bloc.</span><span class="sxs-lookup"><span data-stu-id="7e146-106">This tutorial shows you how to use [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users) to assign a meeting policy to users in bulk.</span></span>

<span data-ttu-id="7e146-107">Rappelez-vous que dans Teams, les utilisateurs obtiennent automatiquement la stratégie globale par défaut de l’organisation d’un type de stratégie d’équipe, sauf si vous créez et attribuez une stratégie personnalisée.</span><span class="sxs-lookup"><span data-stu-id="7e146-107">Remember that in Teams, users automatically get the Global (Org-wide default) policy for a Teams policy type unless you create and assign a custom policy.</span></span> <span data-ttu-id="7e146-108">Dans la mesure où la population étudiant est souvent le plus grand nombre d’utilisateurs et qu’ils reçoivent souvent les paramètres les plus restrictifs, nous vous recommandons de procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="7e146-108">Because the student population is often the largest set of users and they often receive the most restrictive settings, we recommend that you do the following:</span></span>

- <span data-ttu-id="7e146-109">Modification et application de la stratégie globale par défaut de l’Organisation pour restreindre les capacités des étudiants.</span><span class="sxs-lookup"><span data-stu-id="7e146-109">Edit and apply the Global (Org-wide default) policy to restrict capabilities for students.</span></span> 
- <span data-ttu-id="7e146-110">Créez une stratégie personnalisée qui accepte les principales fonctionnalités, telles que la conversation privée et la planification de réunions, et attribuez-la à vos employés et enseignants.</span><span class="sxs-lookup"><span data-stu-id="7e146-110">Create a custom policy that allows core capabilities such as private chat and meeting scheduling and assign the policy to your staff and educators.</span></span>

<span data-ttu-id="7e146-111">Gardez à l’esprit que la politique globale s’applique à tous les utilisateurs de votre établissement scolaire tant que vous n’avez pas créé de stratégie personnalisée et que vous l’avez affectée à votre personnel et aux enseignants.</span><span class="sxs-lookup"><span data-stu-id="7e146-111">Keep in mind that the Global policy will apply to all users in your school until you create a custom policy and assign it to your staff and educators.</span></span>

<span data-ttu-id="7e146-112">Dans ce didacticiel, les étudiants recevront la stratégie de réunion globale et utiliserons PowerShell pour attribuer une stratégie de réunion personnalisée nommée EducatorMeetingPolicy au personnel et aux enseignants en bloc.</span><span class="sxs-lookup"><span data-stu-id="7e146-112">In this tutorial, students will get the Global meeting policy and we use PowerShell to assign a custom meeting policy named EducatorMeetingPolicy to staff and educators in bulk.</span></span> <span data-ttu-id="7e146-113">Nous partons du principe que vous avez modifié la politique globale afin d’adapter les paramètres de la réunion aux étudiants et créé une stratégie personnalisée qui définit l’interface de réunion pour les membres du personnel et les enseignants.</span><span class="sxs-lookup"><span data-stu-id="7e146-113">We assume that you've edited the Global policy to tailor meeting settings for students and created a custom policy that defines the meeting experience for staff and educators.</span></span>

![Capture d’écran de la page stratégies de réunion dans le centre d’administration teams](media/edu-batch-policy-assignment.png)

<span data-ttu-id="7e146-115">Suivez ces étapes pour attribuer une stratégie de réunion personnalisée aux membres du personnel et aux enseignants en bloc.</span><span class="sxs-lookup"><span data-stu-id="7e146-115">Follow these steps to assign a custom meeting policy to staff and educators in bulk.</span></span>

## <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a><span data-ttu-id="7e146-116">Se connecter à Azure AD PowerShell pour le module Graph et au module PowerShell teams</span><span class="sxs-lookup"><span data-stu-id="7e146-116">Connect to the Azure AD PowerShell for Graph module and the Teams PowerShell module</span></span>

<span data-ttu-id="7e146-117">Avant d’effectuer les étapes décrites dans cet article, vous devez installer et vous connecter à Azure AD PowerShell pour le module Graph (afin d’identifier les utilisateurs selon leurs licences affectées) et le module Microsoft teams PowerShell (pour affecter les stratégies à ces utilisateurs).</span><span class="sxs-lookup"><span data-stu-id="7e146-117">Before you perform the steps in this article, you'll need to install and connect to the Azure AD PowerShell for Graph module (to identify users by their assigned licenses) and the Microsoft Teams PowerShell module (to assign the policies to those users).</span></span>

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a><span data-ttu-id="7e146-118">Installer et se connecter à Azure AD PowerShell pour le module Graph</span><span class="sxs-lookup"><span data-stu-id="7e146-118">Install and connect to the Azure AD PowerShell for Graph module</span></span>

<span data-ttu-id="7e146-119">Ouvrez une invite de commandes Windows PowerShell avec élévation de privilèges (exécutez Windows PowerShell en tant qu’administrateur), puis exécutez la commande suivante pour installer Azure Active Directory PowerShell pour le module Graph.</span><span class="sxs-lookup"><span data-stu-id="7e146-119">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator), and then run the following to install the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Install-Module -Name AzureAD
```

<span data-ttu-id="7e146-120">Exécutez la commande suivante pour vous connecter à Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7e146-120">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="7e146-121">Lorsque vous y êtes invité, connectez-vous à l’aide de vos informations d’identification d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="7e146-121">When you're prompted, sign in using your admin credentials.</span></span>

<span data-ttu-id="7e146-122">Pour en savoir plus, voir [se connecter à l’aide d’Azure Active Directory PowerShell pour le module Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="7e146-122">To learn more, see [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="7e146-123">Installer le module Microsoft teams PowerShell et s’y connecter</span><span class="sxs-lookup"><span data-stu-id="7e146-123">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="7e146-124">Exécutez la commande suivante pour installer le [module Microsoft teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams).</span><span class="sxs-lookup"><span data-stu-id="7e146-124">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="7e146-125">Vérifiez que vous avez installé la version 1.0.5 ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="7e146-125">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="7e146-126">Exécutez la commande suivante pour vous connecter à teams et démarrer une session.</span><span class="sxs-lookup"><span data-stu-id="7e146-126">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```
<span data-ttu-id="7e146-127">Lorsque vous y êtes invité, connectez-vous à l’aide des informations d’identification d’administrateur que vous avez utilisées pour vous connecter à Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7e146-127">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

## <a name="identify-your-users"></a><span data-ttu-id="7e146-128">Identifier vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="7e146-128">Identify your users</span></span>

<span data-ttu-id="7e146-129">Tout d’abord, exécutez la commande suivante pour identifier votre personnel et vos enseignants par type de licence.</span><span class="sxs-lookup"><span data-stu-id="7e146-129">First, run the following to identify your staff and educators by license type.</span></span> <span data-ttu-id="7e146-130">Cette option vous indique les références (SKU) utilisées au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="7e146-130">This tells you what SKUs are in use in your organization.</span></span> <span data-ttu-id="7e146-131">Vous pouvez ensuite identifier le personnel et les enseignants qui ont affecté une référence pour les enseignants.</span><span class="sxs-lookup"><span data-stu-id="7e146-131">You can then identify staff and educators that have a Faculty SKU assigned.</span></span>

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

<span data-ttu-id="7e146-132">Qui renvoie :</span><span class="sxs-lookup"><span data-stu-id="7e146-132">Which returns:</span></span>

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

<span data-ttu-id="7e146-133">Dans cet exemple, la sortie indique que la licence Université SkuId est « e97c048c-37a4-45FB-ab50-922fbf07a370 ».</span><span class="sxs-lookup"><span data-stu-id="7e146-133">In this example, the output shows that the Faculty license SkuId is "e97c048c-37a4-45fb-ab50-922fbf07a370".</span></span>

> [!NOTE]
> <span data-ttu-id="7e146-134">Pour afficher une liste des références SKU et des références SKU éducation, voir référence des références [SKU éducation](sku-reference-edu.md).</span><span class="sxs-lookup"><span data-stu-id="7e146-134">To see a list of Education SKUs and SKU IDs, see [Education SKU reference](sku-reference-edu.md).</span></span>

<span data-ttu-id="7e146-135">Ensuite, nous exécutons la commande suivante pour identifier les utilisateurs disposant de cette licence et les rassembler.</span><span class="sxs-lookup"><span data-stu-id="7e146-135">Next, we run the following to identify the users that have this license and collect them all together.</span></span>

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

## <a name="assign-a-policy-in-bulk"></a><span data-ttu-id="7e146-136">Assigner une stratégie en bloc</span><span class="sxs-lookup"><span data-stu-id="7e146-136">Assign a policy in bulk</span></span>

<span data-ttu-id="7e146-137">À présent, nous affectons les stratégies appropriées aux utilisateurs en bloc.</span><span class="sxs-lookup"><span data-stu-id="7e146-137">Now, we assign the appropriate policies to users in bulk.</span></span> <span data-ttu-id="7e146-138">Le nombre maximal d’utilisateurs pour lesquels vous pouvez attribuer ou mettre à jour des stratégies est 5 000 à la fois.</span><span class="sxs-lookup"><span data-stu-id="7e146-138">The maximum number of users for which you can assign or update policies is 5,000 at a time.</span></span> <span data-ttu-id="7e146-139">Par exemple, si vous avez plus de 5 000 employé et enseignants, vous devrez ennoter plusieurs lots.</span><span class="sxs-lookup"><span data-stu-id="7e146-139">For example, if you have more than 5,000 staff and educators, you'll need to submit multiple batches.</span></span>


<span data-ttu-id="7e146-140">Exécutez la commande suivante pour affecter la stratégie de réunion nommée EducatorMeetingPolicy à votre personnel et aux enseignants.</span><span class="sxs-lookup"><span data-stu-id="7e146-140">Run the following to assign the meeting policy named EducatorMeetingPolicy to your staff and educators.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> <span data-ttu-id="7e146-141">Pour attribuer un type de stratégie différent en bloc (par exemple, TeamsMessagingPolicy), vous devez utiliser ```PolicyType``` la stratégie que vous affectez et ```PolicyName``` le nom de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="7e146-141">To assign a different policy type in bulk, like TeamsMessagingPolicy, you'll need to change ```PolicyType``` to the policy that you're assigning and ```PolicyName``` to the policy name.</span></span>

## <a name="get-the-status-of-a-bulk-assignment"></a><span data-ttu-id="7e146-142">Obtenir l’état d’une affectation en bloc</span><span class="sxs-lookup"><span data-stu-id="7e146-142">Get the status of a bulk assignment</span></span>

<span data-ttu-id="7e146-143">Chaque affectation en bloc renvoie un ID d’opération, que vous pouvez utiliser pour effectuer le suivi de l’avancement des affectations de stratégie ou identifier les échecs qui peuvent se produire.</span><span class="sxs-lookup"><span data-stu-id="7e146-143">Each bulk assignment returns an operation ID, which you can use to track the progress of the policy assignments or identify any failures that might occur.</span></span> <span data-ttu-id="7e146-144">Par exemple, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="7e146-144">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

<span data-ttu-id="7e146-145">Pour afficher l’état de l’affectation de chaque utilisateur dans l’opération de traitement par lot, exécutez la commande suivante.</span><span class="sxs-lookup"><span data-stu-id="7e146-145">To view the assignment status of each user in the batch operation, run the following.</span></span> <span data-ttu-id="7e146-146">Les détails de chaque utilisateur sont dans la ```UserState``` propriété.</span><span class="sxs-lookup"><span data-stu-id="7e146-146">Details of each user are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

## <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a><span data-ttu-id="7e146-147">Affecter une stratégie en bloc si vous avez plus de 5 000 utilisateurs</span><span class="sxs-lookup"><span data-stu-id="7e146-147">Assign a policy in bulk if you have more than 5,000 users</span></span>

<span data-ttu-id="7e146-148">Tout d’abord, exécutez la commande suivante pour voir combien de personnes et de enseignants vous avez :</span><span class="sxs-lookup"><span data-stu-id="7e146-148">First, run the following to see how many staff and educators you have:</span></span>

```powershell
$faculty.count
```

<span data-ttu-id="7e146-149">Au lieu de fournir la liste complète des identifiants utilisateur, exécutez la commande suivante pour spécifier le premier 5 000, puis la 5 000 suivante, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="7e146-149">Instead of providing the whole list of user IDs, run the following to specify the first 5,000, and then the next 5,000, and so on.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

<span data-ttu-id="7e146-150">Vous pouvez modifier la plage d’ID utilisateur jusqu’à ce que vous accédiez à la liste complète des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="7e146-150">You can change the range of user IDs until you reach the full list of users.</span></span> <span data-ttu-id="7e146-151">Par exemple, entrez pour le ```$faculty[0..4999``` premier lot, utilisez ```$faculty[5000..9999``` pour le second lot, entrez ```$faculty[10000..14999``` pour le troisième lot, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="7e146-151">For example, enter ```$faculty[0..4999``` for the first batch, use ```$faculty[5000..9999``` for the second batch, enter ```$faculty[10000..14999``` for the third batch, and so on.</span></span>

## <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="7e146-152">Obtention des stratégies affectées à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="7e146-152">Get the policies assigned to a user</span></span>

<span data-ttu-id="7e146-153">Exécutez la commande suivante pour afficher toutes les stratégies affectées à un utilisateur spécifique.</span><span class="sxs-lookup"><span data-stu-id="7e146-153">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="7e146-154">L’exemple suivant vous montre comment obtenir les stratégies affectées à hannah@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7e146-154">The following example shows you how to get the policies that are assigned to hannah@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a><span data-ttu-id="7e146-155">FAQ</span><span class="sxs-lookup"><span data-stu-id="7e146-155">FAQ</span></span>

<span data-ttu-id="7e146-156">**Je souhaite veiller à ce que tous les utilisateurs qui sont des étudiants, des enseignants et des enseignants obtiennent automatiquement des stratégies affectées. Comment faire ?**</span><span class="sxs-lookup"><span data-stu-id="7e146-156">**I want to make sure that all users that are students, staff, and educators automatically get policies assigned. How can I do that?**</span></span>

<span data-ttu-id="7e146-157">L’équipe de produit équipes effectue son travail pour prendre en charge l’attribution de stratégies aux groupes de sécurité.</span><span class="sxs-lookup"><span data-stu-id="7e146-157">The Teams product team is doing work to support assigning policies to security groups.</span></span> <span data-ttu-id="7e146-158">À ce stade, vous serez en mesure de créer des groupes pour vos étudiants et enseignants, puis les politiques appropriées à ces groupes.</span><span class="sxs-lookup"><span data-stu-id="7e146-158">At that time, you'll be able to create groups for your students and teachers, and then the appropriate policies to those groups.</span></span> <span data-ttu-id="7e146-159">Notez que les affectations utilisateur explicites (telles que les stratégies que vous avez affectées à l’aide de ce didacticiel) remplaceront les stratégies héritées d’un groupe.</span><span class="sxs-lookup"><span data-stu-id="7e146-159">Note that explicit user assignments (such as the policies that you've assigned using this tutorial) will override policies inherited from a group.</span></span> <span data-ttu-id="7e146-160">Lorsque cette fonctionnalité est prise en charge, nous vous fournirons des instructions supplémentaires sur la façon d’utiliser une affectation de stratégie aux groupes et de mettre à jour vos utilisateurs pour s’assurer qu’ils reçoivent les stratégies de groupe héritées.</span><span class="sxs-lookup"><span data-stu-id="7e146-160">When this feature is supported, we'll provide more instructions on how to use policy assignment to groups and update your users to ensure they get the inherited group policies.</span></span>

<span data-ttu-id="7e146-161">**Je ne connais pas PowerShell pour Teams. Où trouver d’autres informations ?**</span><span class="sxs-lookup"><span data-stu-id="7e146-161">**I'm not familiar with PowerShell for Teams. Where can I learn more?**</span></span>

<span data-ttu-id="7e146-162">Consultez [vue d’ensemble de PowerShell teams](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7e146-162">See [Teams Powershell overview](teams-powershell-overview.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="7e146-163">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7e146-163">Related topics</span></span>

- [<span data-ttu-id="7e146-164">Attribution de stratégies à vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="7e146-164">Assign policies to your users</span></span>](assign-policies.md)
- [<span data-ttu-id="7e146-165">Nouveau-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="7e146-165">New-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="7e146-166">Get-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="7e146-166">Get-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="7e146-167">Get-CsUserPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="7e146-167">Get-CsUserPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)
