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
ms.openlocfilehash: aab4b524ee0c9ab5cab3244a0897730fea0361a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121342"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a>Supprimer la stratégie de réunion Teams RestrictedAnonymousAccess des utilisateurs

[Les stratégies](meeting-policies-in-teams.md) de réunion dans Microsoft Teams sont utilisées pour contrôler les fonctionnalités disponibles pour les participants à la réunion qui sont programmées par les utilisateurs de votre organisation. 

Teams inclut une stratégie intégrée nommée RestrictedAnonymousAccess, qui contient des paramètres prédéfinie qui incluent la limitation des utilisateurs anonymes de commencer une réunion. (Les utilisateurs anonymes sont des utilisateurs qui n’ont pas été authentifiés.) Les paramètres prédéfinyés dans la stratégie de réunion ne peuvent pas être modifiés ni modifiés par les administrateurs.

Cet article vous explique comment utiliser PowerShell pour supprimer la stratégie de réunion RestrictedAnonymousAccess des utilisateurs à qui cette stratégie est affectée. Pour en savoir plus sur la gestion de Teams à l’aide de PowerShell, consultez la vue [d’ensemble de Teams PowerShell.](teams-powershell-overview.md)

## <a name="before-you-start"></a>Avant de commencer

Installez et connectez-vous au [module Skype Entreprise PowerShell.](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell) Pour obtenir une aide étape par étape, voir [Installer Microsoft Teams PowerShell.](teams-powershell-install.md)

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a>Obtenir les affectations de stratégie de réunion Teams pour votre organisation

Exécutez ce qui suit pour obtenir les affectations de stratégie de réunion Teams pour votre organisation.

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

Dans cet exemple, la sortie suivante est renvoyée, qui montre que deux utilisateurs ont la stratégie de réunion RestrictedAnonymousAccess.

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a>Désaffecter la stratégie de réunion RestrictedAnonymous des utilisateurs

Pour supprimer la stratégie de réunion RestrictedAnonymous des utilisateurs, vous pouvez utiliser l’let [Grant-CSTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) si vous avez un petit nombre d’utilisateurs (par exemple, moins de 100 utilisateurs). Si vous avez un grand nombre d’utilisateurs (par exemple, plus de 100 utilisateurs), il est plus efficace d’utiliser la cmdlet  [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) pour envoyer une opération de lot.

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a>Utiliser l'Grant-CsTeamsMeeting de stratégie de gestion des biens

Exécutez ce qui suit pour supprimer la stratégie de réunion RestrictedAnonymous des utilisateurs.

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a>Utiliser l'New-CsBatchPolicyAssignmentOperation de cmdlet

Avec [l’affectation de](assign-policies.md#assign-a-policy-to-a-batch-of-users)stratégie de lot, le nombre maximal d’utilisateurs pour lesquels vous pouvez supprimer ou mettre à jour des stratégies est de 5 000 à la fois. Par exemple, si vous avez plus de 5 000 utilisateurs, vous devez envoyer plusieurs lots. Pour de meilleurs résultats, n’envoyez pas plusieurs lots à la fois. Autorisez le traitement des lots avant l’envoi d’autres lots.

> [!NOTE]
> La [cmdlet New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) est dans le module Teams PowerShell. Avant de suivre ces étapes, installez le module Teams PowerShell et connectez-vous [à celui-ci.](https://www.powershellgallery.com/packages/MicrosoftTeams) Pour obtenir une aide étape par étape, voir [Installer Microsoft Teams PowerShell.](teams-powershell-install.md)

Exécutez les commandes suivantes pour supprimer la stratégie de réunion RestrictedAnonymousAccess d’un lot d’utilisateurs.

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a>Obtenir l’état du devoir de lot

Chaque affectation de lot renvoie un ID d’opération, que vous pouvez utiliser pour suivre l’avancement et l’état des affectations et identifier les échecs qui peuvent se produire. Par exemple, exécutez ce qui suit :

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

Assurez-vous **que le nombre d’erreurs** est de **0** (zéro) et **que État** Global est **terminé.**

## <a name="related-topics"></a>Rubriques connexes

- [Gérer les stratégies de réunion dans Teams](meeting-policies-in-teams.md)
- [Présentation de Teams PowerShell](teams-powershell-overview.md)
- [Attribuer des stratégies à vos utilisateurs](assign-policies.md)