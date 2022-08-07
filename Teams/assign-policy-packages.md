---
title: Affecter des packages de stratégie à des utilisateurs et des groupes
author: mkbond007
ms.author: mabond
ms.reviewer: tomkau, saragava, ritikag, jastark
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez les différentes façons d’affecter des packages de stratégie aux utilisateurs et aux groupes dans Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: cd6cbaab900ce1e9e5f4a2bd19731573c66ab7eb
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272049"
---
# <a name="assign-policy-packages-to-users-and-groups"></a>Affecter des packages de stratégie à des utilisateurs et des groupes

Cet article passe en revue les différentes façons d’attribuer des packages de stratégie aux utilisateurs et aux groupes dans Microsoft Teams. Avant de lire, assurez-vous d’avoir lu [Affecter des stratégies dans Teams - Bien démarrer](policy-assignment-overview.md).

> [!NOTE]
> Chaque utilisateur aura besoin du module complémentaire Communications avancées pour recevoir une attribution de package de stratégie personnalisée. Pour plus d’informations, consultez [Module complémentaire Communications avancées pour Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).

## <a name="assign-a-policy-package-to-users"></a>Affecter un package de stratégie aux utilisateurs

Un package de stratégie dans Teams est une collection de stratégies et de paramètres de stratégie prédéfinis que vous pouvez attribuer aux utilisateurs qui ont les mêmes rôles ou des rôles similaires dans votre organisation. Chaque package de stratégie est conçu autour d’un rôle d’utilisateur et inclut des stratégies et des paramètres de stratégie prédéfinis qui prennent en charge les activités typiques de ce rôle. Les packages Éducation (Enseignant) et Santé (Travailleur clinique) sont quelques exemples de packages de politiques. Pour en savoir plus, consultez [Gérer les packages de stratégie dans Teams](manage-policy-packages.md).

### <a name="assign-a-policy-package-to-one-user"></a>Affecter un package de stratégie à un utilisateur

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à **Utilisateurs**, puis sélectionnez l’utilisateur.

2. Dans la page de l’utilisateur, sélectionnez **Stratégies**, puis, en regard du **package** de stratégie, **sélectionnez Modifier**.

3. Dans le volet **Affecter un package de stratégie** , sélectionnez le package que vous souhaitez affecter, puis **sélectionnez Appliquer**.

    :::image type="content" source="media/assign-policy-package-one-user.png" alt-text="Capture d’écran montrant le Centre d’administration Teams pour l’attribution de package de stratégie à un utilisateur." lightbox="media/assign-policy-package-one-user-expanded.png":::

### <a name="assign-a-policy-package-to-multiple-users"></a>Affecter un package de stratégie à plusieurs utilisateurs

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux **packages** de stratégie, puis sélectionnez le package de stratégie que vous souhaitez affecter en cliquant à gauche du nom du package.

2. Sélectionnez **Gérer les utilisateurs**.

3. Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.

4. Lorsque vous avez terminé d’ajouter des utilisateurs, **sélectionnez Appliquer**.

    :::image type="content" source="media/assign-policy-package-multiple-users.png" alt-text="Capture d’écran montrant l’attribution du package de stratégie du Centre d’administration Teams à plusieurs utilisateurs." lightbox="media/assign-policy-package-multiple-users-expanded.png":::

## <a name="assign-a-policy-package-to-a-group"></a>Attribuer le package stratégie à un groupe

Attribution de package de stratégie aux groupes vous permet d’attribuer plusieurs stratégies à un groupe d’utilisateurs, tel qu’un groupe de sécurité ou une liste de distribution. L’affectations de stratégie est propagée aux membres du groupe en fonction de règles de priorité. Lorsque les membres sont ajoutés à un groupe ou supprimés de ceux-ci, leurs affectations de stratégie héritées sont mises à jour en conséquence.

L’attribution de package de stratégie aux groupes est recommandée pour les groupes de 50 000 utilisateurs maximum, mais elle fonctionne également avec des groupes plus grands.

Lorsque vous affectez le package de stratégie, il est immédiatement affecté au groupe. Toutefois, la propagation de l’attribution de stratégie aux membres du groupe est effectuée en tant qu’opération en arrière-plan et peut prendre un certain temps, en fonction de la taille du groupe. Il en va de même lorsqu’une stratégie n’est pas affectée à partir d’un groupe, ou quand des membres sont ajoutés ou supprimés d’un groupe.

> [!IMPORTANT]
> Avant de commencer, il est important de comprendre (règles de [précédence](assign-policies-users-and-groups.md#precedence-rules)) et ([classement des affectations de groupe](assign-policies-users-and-groups.md#group-assignment-ranking)). Veillez à lire et à comprendre les concepts dans ([ce que vous devez savoir sur l’attribution de stratégie aux groupes](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)) plus haut dans cet article.

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a>Affecter un package de stratégie à un groupe d’utilisateurs dans le Centre d’administration

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à la page **Packages de** stratégie.

2. Sélectionnez l’onglet **Affectation de package de groupe** .

3. Sélectionnez **Ajouter**, puis, dans le **volet Affecter un package de stratégie à un groupe** , procédez comme suit :

    1. Recherchez et ajoutez le groupe auquel vous souhaitez affecter le package de stratégie.

    1. Sélectionnez un package de stratégie.

    1. Définissez le classement pour chaque type de stratégie.

    1. Sélectionnez **Appliquer**.

       :::image type="content" source="media/assign-policy-package-group.png" alt-text="Capture d’écran de l’attribution d’un package de stratégie à un volet de groupe." lightbox="media/assign-policy-package-group-expanded.png":::

4. Pour gérer le classement d’un type de stratégie spécifique, accédez à la page de stratégie spécifique.

5. Pour réaffecter un package de stratégie à un groupe, commencez par supprimer l’attribution de stratégie de groupe. Ensuite, suivez les étapes ci-dessus pour affecter le package de stratégie à un groupe.

### <a name="work-with-powershell"></a>Utiliser PowerShell

#### <a name="get-the-teams-powershell-module"></a>Obtenir le module Teams PowerShell

Pour obtenir des instructions pas à pas, consultez [Installer Teams PowerShell](teams-powershell-install.md).

#### <a name="assign-a-policy-package-to-a-group-of-users"></a>Affecter un package de stratégie à un groupe d’utilisateurs

Utilisez l’applet de commande [Grant-CsGroupPolicyPackageAssignment](/powershell/module/teams/grant-csgrouppolicypackageassignment) pour affecter un package de stratégie à un groupe. Vous pouvez spécifier un groupe à l’aide de l’ID d’objet, de l’adresse SIP ou de l’adresse e-mail. Lorsque vous affectez le package de stratégie, spécifiez un ([classement des affectations de groupe](assign-policies-users-and-groups.md#group-assignment-ranking)) pour chaque type de stratégie dans le package de stratégie.

Dans cet exemple, nous assignons le package de stratégie Education_Teacher à un groupe avec un classement d’affectation de 1 pour TeamsAppSetupPolicy et TeamsMeetingBroadcastPolicy et un classement de 2 pour TeamsMeetingPolicy.

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a>Affecter un package de stratégie à un lot d’utilisateurs

Avec l’attribution de package de stratégie de lot, vous pouvez affecter un package de stratégie à de grands ensembles d’utilisateurs à la fois sans avoir à utiliser de script. Vous utilisez l’applet de commande [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) pour envoyer un lot d’utilisateurs et le package de stratégie que vous souhaitez affecter. Les attributions sont traitées comme une opération d’arrière-plan et un ID d’opération est généré pour chaque lot. Vous pouvez ensuite utiliser l’applet de commande [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) pour suivre la progression et l’état des affectations dans un lot.

Spécifiez les utilisateurs par leur ID d’objet ou leur adresse SIP (Session Initiation Protocol). L’adresse SIP d’un utilisateur a souvent la même valeur que le nom d’utilisateur principal (UPN) ou l’adresse e-mail, mais cela n’est pas obligatoire. Si un utilisateur est spécifié à l’aide de son UPN ou de son e-mail, mais qu’il a une valeur différente de son adresse SIP, l’attribution de stratégie échoue pour l’utilisateur. Si un lot inclut des utilisateurs en double, les doublons seront supprimés du lot avant le traitement et l’état sera fourni uniquement pour les utilisateurs uniques restants dans le lot.

Un lot contient jusqu’à 5 000 utilisateurs. Pour obtenir de meilleurs résultats, n’envoyez pas plus de quelques lots à la fois. Autoriser les lots à terminer le traitement avant d’envoyer d’autres lots.

### <a name="use-the-teams-powershell-module"></a>Utiliser le module Teams PowerShell

Exécutez la commande suivante pour installer le [module Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (si ce n’est pas déjà fait). Veillez à installer la version 1.0.5 ou ultérieure.

```powershell
Install-Module -Name MicrosoftTeams
```

Exécutez la commande suivante pour vous connecter à Teams et démarrer une session.

```powershell
Connect-MicrosoftTeams
```

Lorsque vous y êtes invité, connectez-vous à l’aide de vos informations d’identification d’administrateur.

### <a name="assign-policy-packages-to-a-batch-of-users"></a>Affecter des packages de stratégie à un lot d’utilisateurs

Dans cet exemple, nous utilisons l’applet de commande [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) pour affecter le package de stratégie Education_PrimaryStudent à un lot d’utilisateurs.

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a>Afficher l’état d’une affectation de lot

Exécutez la commande suivante pour obtenir l’état d’une affectation de lot, où OperationId est l’ID d’opération retourné par l’applet `New-CsBatchPolicyAssignmentOperation` de commande pour un lot donné.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Si la sortie indique qu’une erreur s’est produite, exécutez la commande suivante pour obtenir plus d’informations sur les erreurs qui se trouvent dans la `UserState` propriété.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Pour plus [d’informations, consultez Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).

## <a name="related-topics"></a>Voir aussi

- [Gérer Teams avec des stratégies](manage-teams-with-policies.md)
- [Gérer les packages de stratégie dans Microsoft Teams](manage-policy-packages.md)
- [Aperçu de Teams PowerShell](teams-powershell-overview.md)
- [Affecter des stratégies dans Teams - Prise en main](policy-assignment-overview.md)
