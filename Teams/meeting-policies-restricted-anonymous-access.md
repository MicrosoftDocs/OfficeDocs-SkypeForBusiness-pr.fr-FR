---
title: Suppression de la stratégie de réunion RestrictedAnonymousAccess teams des utilisateurs
author: LanaChin
ms.author: v-lanac
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
description: Découvrez comment supprimer la stratégie de réunion RestrictedAnonymousAccess teams des utilisateurs de votre organisation.
ms.openlocfilehash: 12224ec860552b17b6f7fe50396081943955a88c
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46640979"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a><span data-ttu-id="0082a-103">Suppression de la stratégie de réunion RestrictedAnonymousAccess teams des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="0082a-103">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>

<span data-ttu-id="0082a-104">Les [stratégies de réunion](meeting-policies-in-teams.md) dans Microsoft teams sont utilisées pour contrôler les fonctionnalités qui sont disponibles pour les participants à la réunion, pour les réunions planifiées par les utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="0082a-104">[Meeting policies](meeting-policies-in-teams.md) in Microsoft Teams are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> 

<span data-ttu-id="0082a-105">Teams inclut une stratégie intégrée nommée RestrictedAnonymousAccess, qui contient des paramètres prédéfinis qui englobent la limitation des utilisateurs anonymes au démarrage d’une réunion.</span><span class="sxs-lookup"><span data-stu-id="0082a-105">Teams includes a built-in policy named RestrictedAnonymousAccess, which contains pre-defined settings that include restricting anonymous users from starting a meeting.</span></span> <span data-ttu-id="0082a-106">(Les utilisateurs anonymes sont des utilisateurs qui n’ont pas été authentifiés.) Les paramètres prédéfinis de la stratégie de réunion ne peuvent pas être modifiés ou modifiés par les administrateurs.</span><span class="sxs-lookup"><span data-stu-id="0082a-106">(Anonymous users are users who haven't been authenticated.) The predefined settings in the meeting policy can't be edited or changed by admins.</span></span>

<span data-ttu-id="0082a-107">Cet article vous montre comment utiliser PowerShell pour supprimer la stratégie de réunion RestrictedAnonymousAccess des utilisateurs auxquels cette stratégie est affectée.</span><span class="sxs-lookup"><span data-stu-id="0082a-107">This article shows you how to use PowerShell to remove the RestrictedAnonymousAccess meeting policy from users who are assigned this policy.</span></span> <span data-ttu-id="0082a-108">Pour en savoir plus sur la gestion des équipes à l’aide de PowerShell, voir [vue d’ensemble de PowerShell teams](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0082a-108">To learn more about how to manage Teams using PowerShell, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="0082a-109">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="0082a-109">Before you start</span></span>

<span data-ttu-id="0082a-110">Installez le [module PowerShell Skype entreprise](https://www.microsoft.com/download/details.aspx?id=39366)et connectez-vous.</span><span class="sxs-lookup"><span data-stu-id="0082a-110">Install and connect to the [Skype for Business PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="0082a-111">Pour obtenir des instructions détaillées, voir [installer Microsoft teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="0082a-111">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a><span data-ttu-id="0082a-112">Obtenir les affectations de stratégie de réunion teams pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="0082a-112">Get the Teams meeting policy assignments for your organization</span></span>

<span data-ttu-id="0082a-113">Exécutez la commande suivante pour obtenir les affectations de stratégie de réunion teams pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="0082a-113">Run the following to get the Teams meeting policy assignments for your organization.</span></span>

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

<span data-ttu-id="0082a-114">Dans cet exemple, la sortie suivante est renvoyée, ce qui indique que deux utilisateurs sont affectés à la stratégie de réunion RestrictedAnonymousAccess.</span><span class="sxs-lookup"><span data-stu-id="0082a-114">In this example, the following output is returned, which shows that two users are assigned the RestrictedAnonymousAccess meeting policy.</span></span>

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a><span data-ttu-id="0082a-115">Annuler l’affectation de la stratégie de réunion RestrictedAnonymous aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="0082a-115">Unassign the RestrictedAnonymous meeting policy from users</span></span>

<span data-ttu-id="0082a-116">Pour supprimer la stratégie de réunion RestrictedAnonymous des utilisateurs, vous pouvez utiliser l’applet [de passe Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) si vous avez un petit nombre d’utilisateurs (par exemple, moins de 100 utilisateurs).</span><span class="sxs-lookup"><span data-stu-id="0082a-116">To remove the the RestrictedAnonymous meeting policy from users, you can use the [Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) cmdlet if you have a small number of users (for example, less than 100 users).</span></span> <span data-ttu-id="0082a-117">Si vous avez un grand nombre d’utilisateurs (par exemple, plus de 100), il est plus efficace d’utiliser l’applet de commande [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) pour effectuer une opération de traitement par lot.</span><span class="sxs-lookup"><span data-stu-id="0082a-117">If you have a large number of users (for example, more than 100 users), it's more efficient to use the  [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet to submit a batch operation.</span></span>

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a><span data-ttu-id="0082a-118">Utiliser l’applet de passe de stratégie d’attribution-CsTeamsMeeting</span><span class="sxs-lookup"><span data-stu-id="0082a-118">Use the Grant-CsTeamsMeeting Policy cmdlet</span></span>

<span data-ttu-id="0082a-119">Exécutez la commande suivante pour supprimer la stratégie de réunion RestrictedAnonymous des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0082a-119">Run the following to remove the RestrictedAnonymous meeting policy from users.</span></span>

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a><span data-ttu-id="0082a-120">Utiliser l’applet de nouvelle applet de CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="0082a-120">Use the New-CsBatchPolicyAssignmentOperation cmdlet</span></span>

<span data-ttu-id="0082a-121">Avec une [affectation de stratégie de lot](assign-policies.md#assign-a-policy-to-a-batch-of-users), le nombre maximal d’utilisateurs pour lesquels vous pouvez supprimer ou mettre à jour des stratégies est 5 000 à la fois.</span><span class="sxs-lookup"><span data-stu-id="0082a-121">With [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users), the maximum number of users for which you can remove or update policies is 5,000 at a time.</span></span> <span data-ttu-id="0082a-122">Par exemple, si vous avez plus d’utilisateurs 5 000, vous devez en saisir plusieurs.</span><span class="sxs-lookup"><span data-stu-id="0082a-122">For example, if you have more than 5,000 users, you'll need to submit multiple batches.</span></span> <span data-ttu-id="0082a-123">Pour obtenir de meilleurs résultats, n’envoyez pas plusieurs lots à la fois.</span><span class="sxs-lookup"><span data-stu-id="0082a-123">For best results, do not submit multiple batches at a time.</span></span> <span data-ttu-id="0082a-124">Autorisez le traitement des lots avant de soumettre d’autres lots.</span><span class="sxs-lookup"><span data-stu-id="0082a-124">Allow batches to complete processing before submitting more batches.</span></span>

> [!NOTE]
> <span data-ttu-id="0082a-125">L’applet de nouvelle applet de [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) se trouve dans le module PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="0082a-125">The [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet is in the Teams PowerShell module.</span></span> <span data-ttu-id="0082a-126">Avant de suivre ces étapes, installez et connectez-vous au [module PowerShell teams](https://www.powershellgallery.com/packages/MicrosoftTeams).</span><span class="sxs-lookup"><span data-stu-id="0082a-126">Before you follow these steps, install and connect to the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="0082a-127">Pour obtenir des instructions détaillées, voir [installer Microsoft teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="0082a-127">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

<span data-ttu-id="0082a-128">Pour supprimer une stratégie de réunion RestrictedAnonymousAccess d’un lot d’utilisateurs, exécutez les commandes suivantes.</span><span class="sxs-lookup"><span data-stu-id="0082a-128">Run the following commands to remove the RestrictedAnonymousAccess meeting policy from a batch of users.</span></span>

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a><span data-ttu-id="0082a-129">Obtient l’état de l’affectation par lot.</span><span class="sxs-lookup"><span data-stu-id="0082a-129">Get the status of the batch assignment</span></span>

<span data-ttu-id="0082a-130">Chaque affectation de lot renvoie un ID d’opération, que vous pouvez utiliser pour effectuer le suivi de la progression et de l’état des devoirs et identifier les échecs qui peuvent se produire.</span><span class="sxs-lookup"><span data-stu-id="0082a-130">Each batch assignment returns an operation ID, which you can use to track the progress and status of the assignments and identify any failures that might occur.</span></span> <span data-ttu-id="0082a-131">Par exemple, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="0082a-131">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

<span data-ttu-id="0082a-132">Vérifiez que la valeur de **ErrorCount** est **égale à 0** (zéro) et que **OverallStatus** est **terminé**.</span><span class="sxs-lookup"><span data-stu-id="0082a-132">Make sure the **ErrorCount** is **0** (zero) and **OverallStatus** is **Completed**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0082a-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0082a-133">Related topics</span></span>

- [<span data-ttu-id="0082a-134">Gérer les stratégies de réunion dans teams</span><span class="sxs-lookup"><span data-stu-id="0082a-134">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
- [<span data-ttu-id="0082a-135">Présentation de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="0082a-135">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="0082a-136">Attribuer des stratégies à vos utilisateurs dans teams</span><span class="sxs-lookup"><span data-stu-id="0082a-136">Assign policies to your users in Teams</span></span>](assign-policies.md)
