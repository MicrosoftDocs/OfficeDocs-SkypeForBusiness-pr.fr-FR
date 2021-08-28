---
title: Gérer les propriétaires de plannings pour la gestion des shifts
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Découvrez comment gérer les propriétaires de shift pour la gestion du planning. Vous pouvez définir une stratégie pour élever l’autorisation d’un membre d’équipe à un propriétaire de planning.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 702ca0fd5b392755b1966d16024d5ecf10cdacab
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627536"
---
# <a name="schedule-owner-for-shift-management"></a>Propriétaire de planning pour la gestion des shifts

## <a name="overview"></a>Présentation

Le Propriétaire de planning est une fonctionnalité qui vous permet de donner à un membre de l’équipe les autorisations qu’il vous autorise à devenir propriétaire du planning sans donner à l’employé le niveau de propriétaire de l’équipe. Cela signifie que l’employé est autorisé à gérer le planning de son équipe sans pouvoir modifier les autres propriétés de l’équipe telles que la mise à jour, la modification ou la suppression de canaux d’équipe.

Que peut faire un utilisateur titulaire des autorisations de propriétaire de planification ?

- Créez, modifiez et publiez des plannings pour gérer les missions de leur équipe.
- Affichez et approuvez les demandes de shift, y compris les demandes d’échange de shifts et de shifts ouverts.
- Gérez les paramètres dans Shifts pour activer certaines fonctionnalités pour l’équipe.
- Affichez et modifiez la feuille de temps de l’équipe pour traiter les salaires des employés.

## <a name="why-schedule-owner"></a>Pourquoi propriétaire de la planification ?

Sans la fonctionnalité Propriétaire de planning, les fonctions métier au quotidien pourraient être interrompues. Si le propriétaire de l’équipe vous aide à gérer l’équipe, il ne s’agit pas nécessairement de la personne chargée de la planification quotidienne. Dans ce cas, le transfert de la responsabilité de la gestion des plannings uniquement à un autre membre de l’équipe simplifie les opérations quotidiennes au sein de l’équipe et élimine la confusion entre deux membres d’équipe disposer des mêmes privilèges d’accès.

## <a name="scenario"></a>Scénario

Voici un exemple de la façon dont votre organisation peut utiliser la fonctionnalité Propriétaire de planning.

Vous travaillez dans une grande organisation où les responsables de service signalent directement au responsable du magasin. Le responsable du magasin a plus d’autorité au sein de votre entreprise et est le propriétaire de l’équipe dans Shifts. En revanche, les responsables de département ne sont ajoutés qu’à Shifts en tant que membres d’équipe. Bien que les responsables de magasin ont plus de niveau supérieur que les responsables de département, il est plus logique pour les responsables de département de gérer la planification quotidienne des employés de leur équipe.

*Sans propriétaire de planning,* les responsables de service doivent avoir les mêmes privilèges que le propriétaire de l’équipe. Récemment, les responsables de département ont commencé à déplacer des informations et à changer le nom des canaux, ce qui a provoqué des complications dans le travail du responsable de magasin. Le responsable de magasin souhaite que les responsables de service puissent organiser leurs plannings, mais ne souhaite pas qu’ils puissent modifier autre chose dans l’équipe, en dehors de Shifts.

*Avec le propriétaire de la* planification, les responsables de département peuvent obtenir des privilèges de planification, sans aucun autre privilège de propriétaire d’équipe.

## <a name="manage-schedule-ownership"></a>Gérer la propriété du planning

En tant qu’administrateur, vous utilisez des stratégies pour contrôler la propriété de la gestion des plannings dans votre organisation. Vous gérez ces stratégies à l’aide des cmdlets PowerShell suivantes :

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy?view=teams-ps)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy?view=teams-ps)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy?view=teams-ps)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy?view=teams-ps)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy?view=teams-ps)

### <a name="example-1"></a>Exemple 1

Ici, nous créons une stratégie nommée ScheduleOwnerPolicy avec la fonctionnalité Schedule Owner désactivée.

```powershell
New-CsTeamsShiftsPolicy –Identity ScheduleOwnerPolicy  -EnableScheduleOwnerPermissions $true -AccessType UnrestrictedAccess_TeamsApp
```

### <a name="example-2"></a>Exemple 2

Dans cet exemple, nous affectons une stratégie nommée ScheduleOwnerPolicy à un utilisateur nommé remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName ScheduleOwnerPolicy
```

## <a name="related-articles"></a>Articles connexes

- [Gérer l’application Shifts pour votre organisation dans Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Gérer l’accès par équipe pour les employés en première ligne dans Teams](manage-shift-based-access-flw.md) 
