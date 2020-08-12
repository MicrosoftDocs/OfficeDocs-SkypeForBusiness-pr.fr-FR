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
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a>Suppression de la stratégie de réunion RestrictedAnonymousAccess teams des utilisateurs

Les [stratégies de réunion](meeting-policies-in-teams.md) dans Microsoft teams sont utilisées pour contrôler les fonctionnalités qui sont disponibles pour les participants à la réunion, pour les réunions planifiées par les utilisateurs de votre organisation. 

Teams inclut une stratégie intégrée nommée RestrictedAnonymousAccess, qui contient des paramètres prédéfinis qui englobent la limitation des utilisateurs anonymes au démarrage d’une réunion. (Les utilisateurs anonymes sont des utilisateurs qui n’ont pas été authentifiés.) Les paramètres prédéfinis de la stratégie de réunion ne peuvent pas être modifiés ou modifiés par les administrateurs.

Cet article vous montre comment utiliser PowerShell pour supprimer la stratégie de réunion RestrictedAnonymousAccess des utilisateurs auxquels cette stratégie est affectée. Pour en savoir plus sur la gestion des équipes à l’aide de PowerShell, voir [vue d’ensemble de PowerShell teams](teams-powershell-overview.md).

## <a name="before-you-start"></a>Avant de commencer

Installez le [module PowerShell Skype entreprise](https://www.microsoft.com/download/details.aspx?id=39366)et connectez-vous. Pour obtenir des instructions détaillées, voir [installer Microsoft teams PowerShell](teams-powershell-install.md).

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a>Obtenir les affectations de stratégie de réunion teams pour votre organisation

Exécutez la commande suivante pour obtenir les affectations de stratégie de réunion teams pour votre organisation.

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

Dans cet exemple, la sortie suivante est renvoyée, ce qui indique que deux utilisateurs sont affectés à la stratégie de réunion RestrictedAnonymousAccess.

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a>Annuler l’affectation de la stratégie de réunion RestrictedAnonymous aux utilisateurs

Pour supprimer la stratégie de réunion RestrictedAnonymous des utilisateurs, vous pouvez utiliser l’applet [de passe Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) si vous avez un petit nombre d’utilisateurs (par exemple, moins de 100 utilisateurs). Si vous avez un grand nombre d’utilisateurs (par exemple, plus de 100), il est plus efficace d’utiliser l’applet de commande [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) pour effectuer une opération de traitement par lot.

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a>Utiliser l’applet de passe de stratégie d’attribution-CsTeamsMeeting

Exécutez la commande suivante pour supprimer la stratégie de réunion RestrictedAnonymous des utilisateurs.

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a>Utiliser l’applet de nouvelle applet de CsBatchPolicyAssignmentOperation

Avec une [affectation de stratégie de lot](assign-policies.md#assign-a-policy-to-a-batch-of-users), le nombre maximal d’utilisateurs pour lesquels vous pouvez supprimer ou mettre à jour des stratégies est 5 000 à la fois. Par exemple, si vous avez plus d’utilisateurs 5 000, vous devez en saisir plusieurs. Pour obtenir de meilleurs résultats, n’envoyez pas plusieurs lots à la fois. Autorisez le traitement des lots avant de soumettre d’autres lots.

> [!NOTE]
> L’applet de nouvelle applet de [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) se trouve dans le module PowerShell Teams. Avant de suivre ces étapes, installez et connectez-vous au [module PowerShell teams](https://www.powershellgallery.com/packages/MicrosoftTeams). Pour obtenir des instructions détaillées, voir [installer Microsoft teams PowerShell](teams-powershell-install.md).

Pour supprimer une stratégie de réunion RestrictedAnonymousAccess d’un lot d’utilisateurs, exécutez les commandes suivantes.

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a>Obtient l’état de l’affectation par lot.

Chaque affectation de lot renvoie un ID d’opération, que vous pouvez utiliser pour effectuer le suivi de la progression et de l’état des devoirs et identifier les échecs qui peuvent se produire. Par exemple, exécutez la commande suivante :

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

Vérifiez que la valeur de **ErrorCount** est **égale à 0** (zéro) et que **OverallStatus** est **terminé**.

## <a name="related-topics"></a>Voir aussi

- [Gérer les stratégies de réunion dans teams](meeting-policies-in-teams.md)
- [Présentation de Teams PowerShell](teams-powershell-overview.md)
- [Attribuer des stratégies à vos utilisateurs dans teams](assign-policies.md)
