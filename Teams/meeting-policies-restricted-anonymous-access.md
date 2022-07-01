---
title: Supprimer la stratégie de réunion Teams RestrictedAnonymousAccess des utilisateurs
ms.author: mabond
author: mkbond007
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: cebulnes, anyada
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
description: Découvrez comment supprimer la stratégie de réunion RestrictedAnonymousAccess Teams des utilisateurs de votre organisation.
ms.openlocfilehash: e5ea203e52ca1b81ed7ce37f31c9f8cb5900c131
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66564102"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a>Supprimer la stratégie de réunion Teams RestrictedAnonymousAccess des utilisateurs

[Les stratégies de réunion](meeting-policies-overview.md) dans Microsoft Teams sont utilisées pour contrôler les fonctionnalités disponibles pour les participants aux réunions planifiées par les utilisateurs de votre organisation. 

Teams inclut une stratégie intégrée nommée RestrictedAnonymousAccess, qui contient des paramètres prédéfinis qui incluent la restriction des utilisateurs anonymes au démarrage d’une réunion. (Les utilisateurs anonymes sont des utilisateurs qui n’ont pas été authentifiés.) Les paramètres prédéfinis dans la stratégie de réunion ne peuvent pas être modifiés ou modifiés par les administrateurs.

Cet article explique comment utiliser PowerShell pour supprimer la stratégie de réunion RestrictedAnonymousAccess des utilisateurs auxquels cette stratégie est affectée. Pour en savoir plus sur la gestion de Teams à l’aide de PowerShell, consultez [la vue d’ensemble de Teams PowerShell](teams-powershell-overview.md).

## <a name="before-you-start"></a>Avant de commencer

Installez et connectez-vous au [module PowerShell Skype Entreprise](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell). Pour obtenir des conseils pas à pas, consultez [Installer Microsoft Teams PowerShell](teams-powershell-install.md).

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a>Obtenir les affectations de stratégie de réunion Teams pour votre organisation

Exécutez ce qui suit pour obtenir les affectations de stratégie de réunion Teams pour votre organisation.

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

Dans cet exemple, la sortie suivante est retournée, ce qui indique que la stratégie de réunion RestrictedAnonymousAccess est affectée à deux utilisateurs.

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a>Annuler l’affectation de la stratégie de réunion RestrictedAnonymous aux utilisateurs

Pour supprimer la stratégie de réunion RestrictedAnonymous des utilisateurs, vous pouvez utiliser l’applet de commande [Grant-CSTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) si vous avez un petit nombre d’utilisateurs (par exemple, moins de 100 utilisateurs). Si vous avez un grand nombre d’utilisateurs (par exemple, plus de 100 utilisateurs), il est plus efficace d’utiliser l’applet de commande  [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) pour envoyer une opération par lot.

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a>Utiliser l’applet de commande Grant-CsTeamsMeeting Policy

Exécutez ce qui suit pour supprimer la stratégie de réunion RestrictedAnonymous des utilisateurs.

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a>Utiliser l’applet de commande New-CsBatchPolicyAssignmentOperation

Avec [l’attribution](assign-policies-users-and-groups.md#assign-a-policy-to-a-batch-of-users) de stratégie de lot, le nombre maximal d’utilisateurs pour lesquels vous pouvez supprimer ou mettre à jour des stratégies est de 5 000 à la fois. Par exemple, si vous avez plus de 5 000 utilisateurs, vous devez envoyer plusieurs lots. Pour obtenir de meilleurs résultats, n’envoyez pas plusieurs lots à la fois. Autoriser les lots à terminer le traitement avant d’envoyer d’autres lots.

> [!NOTE]
> L’applet [de commande New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) se trouve dans le module Teams PowerShell. Avant de suivre ces étapes, installez et connectez-vous au [module Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams). Pour obtenir des conseils pas à pas, consultez [Installer Microsoft Teams PowerShell](teams-powershell-install.md).

Exécutez les commandes suivantes pour supprimer la stratégie de réunion RestrictedAnonymousAccess d’un lot d’utilisateurs.

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a>Obtenir l’état de l’affectation de lot

Chaque affectation par lot retourne un ID d’opération, que vous pouvez utiliser pour suivre la progression et l’état des affectations et identifier les défaillances susceptibles de se produire. Par exemple, exécutez ce qui suit :

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

Vérifiez que **errorCount** est **égal à 0** (zéro) et **OverallStatus** **est terminé**.

## <a name="related-topics"></a>Sujets associés

- [Gérer les stratégies de réunion dans Teams](meeting-policies-overview.md)
- [Présentation de Teams PowerShell](teams-powershell-overview.md)
- [Attribuer des stratégies à vos utilisateurs](policy-assignment-overview.md)