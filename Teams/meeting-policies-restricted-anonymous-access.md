---
title: Supprimer la stratégie de réunion Teams RestrictedAnonymousAccess des utilisateurs
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: cebulnes, anyada
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
description: Découvrez comment supprimer la stratégie de réunion RestrictedAnonymousAccess Teams des utilisateurs de votre organisation.
ms.openlocfilehash: 55385cdd47f6b6c9882f8d4e8dcadc848f13755d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806254"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a><span data-ttu-id="8973a-103">Supprimer la stratégie de réunion Teams RestrictedAnonymousAccess des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="8973a-103">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>

<span data-ttu-id="8973a-104">[Les stratégies](meeting-policies-in-teams.md) de réunion dans Microsoft Teams sont utilisées pour contrôler les fonctionnalités disponibles pour les participants à la réunion qui sont programmées par les utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8973a-104">[Meeting policies](meeting-policies-in-teams.md) in Microsoft Teams are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> 

<span data-ttu-id="8973a-105">Teams inclut une stratégie intégrée nommée RestrictedAnonymousAccess, qui contient des paramètres prédéfinie qui incluent la limitation des utilisateurs anonymes de commencer une réunion.</span><span class="sxs-lookup"><span data-stu-id="8973a-105">Teams includes a built-in policy named RestrictedAnonymousAccess, which contains pre-defined settings that include restricting anonymous users from starting a meeting.</span></span> <span data-ttu-id="8973a-106">(Les utilisateurs anonymes sont des utilisateurs qui n’ont pas été authentifiés.) Les paramètres prédéfinyés dans la stratégie de réunion ne peuvent pas être modifiés ni modifiés par les administrateurs.</span><span class="sxs-lookup"><span data-stu-id="8973a-106">(Anonymous users are users who haven't been authenticated.) The predefined settings in the meeting policy can't be edited or changed by admins.</span></span>

<span data-ttu-id="8973a-107">Cet article vous explique comment utiliser PowerShell pour supprimer la stratégie de réunion RestrictedAnonymousAccess des utilisateurs à qui cette stratégie est affectée.</span><span class="sxs-lookup"><span data-stu-id="8973a-107">This article shows you how to use PowerShell to remove the RestrictedAnonymousAccess meeting policy from users who are assigned this policy.</span></span> <span data-ttu-id="8973a-108">Pour en savoir plus sur la gestion de Teams à l’aide de PowerShell, consultez la vue [d’ensemble de Teams PowerShell.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="8973a-108">To learn more about how to manage Teams using PowerShell, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="8973a-109">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="8973a-109">Before you start</span></span>

<span data-ttu-id="8973a-110">Installez et connectez-vous au [module Skype Entreprise PowerShell.](https://www.microsoft.com/download/details.aspx?id=39366)</span><span class="sxs-lookup"><span data-stu-id="8973a-110">Install and connect to the [Skype for Business PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="8973a-111">Pour obtenir une aide étape par étape, voir [Installer Microsoft Teams PowerShell.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="8973a-111">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a><span data-ttu-id="8973a-112">Obtenir les affectations de stratégie de réunion Teams pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="8973a-112">Get the Teams meeting policy assignments for your organization</span></span>

<span data-ttu-id="8973a-113">Exécutez ce qui suit pour obtenir les affectations de stratégie de réunion Teams pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8973a-113">Run the following to get the Teams meeting policy assignments for your organization.</span></span>

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

<span data-ttu-id="8973a-114">Dans cet exemple, la sortie suivante est renvoyée, qui montre que deux utilisateurs ont la stratégie de réunion RestrictedAnonymousAccess.</span><span class="sxs-lookup"><span data-stu-id="8973a-114">In this example, the following output is returned, which shows that two users are assigned the RestrictedAnonymousAccess meeting policy.</span></span>

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a><span data-ttu-id="8973a-115">Désaffecter la stratégie de réunion RestrictedAnonymous des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="8973a-115">Unassign the RestrictedAnonymous meeting policy from users</span></span>

<span data-ttu-id="8973a-116">Pour supprimer la stratégie de réunion RestrictedAnonymous des utilisateurs, vous pouvez utiliser l’let [Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) si vous avez un petit nombre d’utilisateurs (par exemple, moins de 100 utilisateurs).</span><span class="sxs-lookup"><span data-stu-id="8973a-116">To remove the the RestrictedAnonymous meeting policy from users, you can use the [Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) cmdlet if you have a small number of users (for example, less than 100 users).</span></span> <span data-ttu-id="8973a-117">Si vous avez un grand nombre d’utilisateurs (par exemple, plus de 100 utilisateurs), il est plus efficace d’utiliser la cmdlet  [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) pour envoyer une opération de lot.</span><span class="sxs-lookup"><span data-stu-id="8973a-117">If you have a large number of users (for example, more than 100 users), it's more efficient to use the  [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet to submit a batch operation.</span></span>

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a><span data-ttu-id="8973a-118">Utiliser l'Grant-CsTeamsMeeting de stratégie de gestion des biens</span><span class="sxs-lookup"><span data-stu-id="8973a-118">Use the Grant-CsTeamsMeeting Policy cmdlet</span></span>

<span data-ttu-id="8973a-119">Exécutez ce qui suit pour supprimer la stratégie de réunion RestrictedAnonymous des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8973a-119">Run the following to remove the RestrictedAnonymous meeting policy from users.</span></span>

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a><span data-ttu-id="8973a-120">Utiliser l'New-CsBatchPolicyAssignmentOperation de cmdlet</span><span class="sxs-lookup"><span data-stu-id="8973a-120">Use the New-CsBatchPolicyAssignmentOperation cmdlet</span></span>

<span data-ttu-id="8973a-121">Avec [l’affectation de](assign-policies.md#assign-a-policy-to-a-batch-of-users)stratégie de lot, le nombre maximal d’utilisateurs pour lesquels vous pouvez supprimer ou mettre à jour des stratégies est de 5 000 à la fois.</span><span class="sxs-lookup"><span data-stu-id="8973a-121">With [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users), the maximum number of users for which you can remove or update policies is 5,000 at a time.</span></span> <span data-ttu-id="8973a-122">Par exemple, si vous avez plus de 5 000 utilisateurs, vous devez envoyer plusieurs lots.</span><span class="sxs-lookup"><span data-stu-id="8973a-122">For example, if you have more than 5,000 users, you'll need to submit multiple batches.</span></span> <span data-ttu-id="8973a-123">Pour de meilleurs résultats, n’envoyez pas plusieurs lots à la fois.</span><span class="sxs-lookup"><span data-stu-id="8973a-123">For best results, do not submit multiple batches at a time.</span></span> <span data-ttu-id="8973a-124">Autorisez le traitement des lots avant l’envoi d’autres lots.</span><span class="sxs-lookup"><span data-stu-id="8973a-124">Allow batches to complete processing before submitting more batches.</span></span>

> [!NOTE]
> <span data-ttu-id="8973a-125">La [cmdlet New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) est dans le module Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8973a-125">The [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet is in the Teams PowerShell module.</span></span> <span data-ttu-id="8973a-126">Avant de suivre ces étapes, installez le module Teams PowerShell et connectez-vous [à celui-ci.](https://www.powershellgallery.com/packages/MicrosoftTeams)</span><span class="sxs-lookup"><span data-stu-id="8973a-126">Before you follow these steps, install and connect to the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="8973a-127">Pour obtenir une aide étape par étape, voir [Installer Microsoft Teams PowerShell.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="8973a-127">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

<span data-ttu-id="8973a-128">Exécutez les commandes suivantes pour supprimer la stratégie de réunion RestrictedAnonymousAccess d’un lot d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8973a-128">Run the following commands to remove the RestrictedAnonymousAccess meeting policy from a batch of users.</span></span>

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a><span data-ttu-id="8973a-129">Obtenir l’état du devoir de lot</span><span class="sxs-lookup"><span data-stu-id="8973a-129">Get the status of the batch assignment</span></span>

<span data-ttu-id="8973a-130">Chaque affectation de lot renvoie un ID d’opération, que vous pouvez utiliser pour suivre l’avancement et l’état des affectations et identifier les échecs qui peuvent se produire.</span><span class="sxs-lookup"><span data-stu-id="8973a-130">Each batch assignment returns an operation ID, which you can use to track the progress and status of the assignments and identify any failures that might occur.</span></span> <span data-ttu-id="8973a-131">Par exemple, exécutez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="8973a-131">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

<span data-ttu-id="8973a-132">Assurez-vous **que le nombre d’erreurs** est de **0** (zéro) et **que État** Global est **terminé.**</span><span class="sxs-lookup"><span data-stu-id="8973a-132">Make sure the **ErrorCount** is **0** (zero) and **OverallStatus** is **Completed**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8973a-133">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="8973a-133">Related topics</span></span>

- [<span data-ttu-id="8973a-134">Voir Gérer les stratégies de réunion dans Teams.</span><span class="sxs-lookup"><span data-stu-id="8973a-134">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
- [<span data-ttu-id="8973a-135">Présentation de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="8973a-135">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="8973a-136">Attribuer des stratégies à vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="8973a-136">Assign policies to your users in Teams</span></span>](assign-policies.md)
