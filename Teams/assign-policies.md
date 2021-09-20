---
title: Attribuer des stratégies à vos utilisateurs dans Microsoft Teams.
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: tomkau, saragava, ritikag, jastark
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
description: Découvrez les différentes façons d’attribuer des stratégies à vos utilisateurs dans Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: ed0ed4b03d6472a646cd19897b33a22b2fc4df06
ms.sourcegitcommit: cf2f96dbd485ac4cc822c5a591ccce6b47f12cc7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/20/2021
ms.locfileid: "59456364"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a>Attribuer des stratégies à vos utilisateurs dans Microsoft Teams.

En tant qu’administrateur, vous utilisez des stratégies pour contrôler Teams fonctionnalités disponibles pour les utilisateurs de votre organisation. Par exemple, il existe des stratégies d’appel, des stratégies de réunion et des stratégies de messagerie, entre autres.

Les organisations ont différents types d’utilisateurs ayant des besoins uniques. Les stratégies personnalisées que vous créez et attribuez vous personnalisationnt aux différents ensembles d’utilisateurs en fonction de ces besoins.

Pour gérer facilement les stratégies dans votre organisation, Teams plusieurs façons d’affecter des stratégies aux utilisateurs. Affectez une stratégie directement aux utilisateurs, individuellement ou à l’échelle via une affectation de lot, ou à un groupe dont les utilisateurs sont membres. Vous pouvez également utiliser des packages de stratégies pour affecter une collection prédéfinfine de stratégies aux utilisateurs de votre organisation ayant des rôles similaires. L’option que vous choisissez dépend du nombre de stratégies que vous gérez et du nombre d’utilisateurs à qui vous affectez des stratégies. Les stratégies globales (à l’échelle de l’organisation par défaut) s’appliquent au plus grand nombre d’utilisateurs de votre organisation. Il vous s agit uniquement d’affecter des stratégies aux utilisateurs qui ont besoin de stratégies spécialisées.

Cet article décrit les différentes manières d’affecter des stratégies aux utilisateurs et les scénarios recommandés pour l’utilisation des stratégies.

## <a name="which-policy-takes-precedence"></a>Quelle stratégie prend le pas ?

Un utilisateur a une stratégie efficace pour chaque type de stratégie. Il est possible, voire probable, qu’une stratégie soit attribuée directement à un utilisateur et qu’il soit également membre d’un ou plusieurs groupes à qui une stratégie du même type a été attribuée. Dans ces types de scénarios, quelle stratégie prend le pas ? La stratégie efficace d’un utilisateur est déterminée selon les règles de priorité, comme suit.

Si un utilisateur est affecté directement à une stratégie (individuellement ou par le biais d’une affectation de lot), cette stratégie est prioritaire. Dans l’exemple visuel suivant, la stratégie efficace de l’utilisateur est la stratégie de réunion carrée qu’il est directement affecté à l’utilisateur.

![Diagramme montrant comment une stratégie assignée directement prend le pas.](media/assign-policies-example-directly-assigned.png)

Si un utilisateur n’est pas directement affecté à une stratégie d’un type donné, la stratégie assignée à un groupe dont l’utilisateur est membre est prioritaire. Si un utilisateur est membre de plusieurs groupes, [](#group-assignment-ranking) la stratégie ayant le classement d’affectation de groupe le plus élevé pour le type de stratégie donné est prioritaire.

Dans cet exemple visuel, la stratégie efficace de l’utilisateur est la stratégie Exec Teams et HD, qui présente le classement d’affectation le plus élevé par rapport aux autres groupes dont l’utilisateur est membre et pour lesquels une stratégie du même type de stratégie est également attribuée.  

![Diagramme montrant comment une stratégie héritée d’un groupe est prioritaire.](media/assign-policies-example-group.png)

Si un utilisateur n’est pas directement affecté à une stratégie ou n’est membre d’aucun groupe à qui une stratégie est attribuée, l’utilisateur reçoit la stratégie globale (à l’échelle de l’organisation par défaut) pour ce type de stratégie. Voici un exemple visuel.

![Diagramme montrant comment une stratégie globale prend le pas.](media/assign-policies-example-global.png)

Pour en savoir plus, consultez [les règles de priorité.](#precedence-rules)

## <a name="ways-to-assign-policies"></a>Méthodes d’affectation des stratégies

Voici une vue d’ensemble des manières d’affecter des stratégies aux utilisateurs et des scénarios recommandés pour chacun d’eux. Sélectionnez les liens pour en savoir plus.

Avant d’affecter des stratégies à des utilisateurs ou groupes individuels, commencez par définir les stratégies globales (à l’échelle de l’organisation [par défaut)](#set-the-global-policies) de sorte qu’elles s’appliquent au plus grand nombre d’utilisateurs de votre organisation.  Une fois les stratégies globales définies, vous devrez seulement affecter des stratégies aux utilisateurs qui ont besoin de stratégies spécialisées.

|Pour ce faire,  |Si...  | Utilisation...
|---------|---------|----|
|[Attribuer une stratégie à des utilisateurs individuels](#assign-a-policy-to-individual-users)    | Vous débutez dans Teams vous débutez, ou vous n’avez besoin d’affecter qu’une ou plusieurs stratégies à un petit nombre d’utilisateurs. |The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module
|[Affecter une stratégie à un groupe](#assign-a-policy-to-a-group) |Attribuer des stratégies en fonction de l’appartenance d’un utilisateur à un groupe. Par exemple, affectez une stratégie à tous les utilisateurs d’un groupe de sécurité ou d’une liste de distribution.| The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module|
|[Affecter une stratégie à un lot d’utilisateurs](#assign-a-policy-to-a-batch-of-users)   | Attribuer des stratégies à de grands ensembles d’utilisateurs. Par exemple, affectez une stratégie à des centaines ou des milliers d’utilisateurs à la fois dans votre organisation. |The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module|
| [Attribuer un package de stratégies aux utilisateurs](#assign-a-policy-package-to-users)  |Attribuez plusieurs stratégies à des ensembles spécifiques d’utilisateurs de votre organisation qui ont des rôles identiques ou similaires. Par exemple, affectez le package de stratégie Éducation (Enseignant) aux enseignants de votre établissement scolaire pour leur donner un accès total aux conversations, appels et réunions. Affectez le package de stratégie Éducation (étudiant secondaire) aux étudiants secondaires afin de limiter certaines fonctionnalités telles que les appels privés.  |The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module|
| [Affecter un package de stratégie à un groupe](#assign-a-policy-package-to-a-group) (en prévisualisation privée)   |Attribuer plusieurs stratégies à un groupe d’utilisateurs de votre organisation qui ont des rôles identiques ou similaires. Par exemple, affectez un package de stratégie à tous les utilisateurs d’un groupe de sécurité ou d’une liste de distribution. |Le Microsoft Teams d’administration powershell (bientôt disponible) ou les cmdlets PowerShell dans Teams module PowerShell|
| [Affecter un package de stratégie à un lot d’utilisateurs](#assign-a-policy-package-to-a-batch-of-users)|Affectez plusieurs stratégies à un lot d’utilisateurs de votre organisation qui ont des rôles identiques ou similaires. Par exemple, affectez le package de stratégie Éducation (Enseignant) à tous les enseignants de votre établissement en utilisant un devoir de lot pour leur donner un accès total aux conversations, appels et réunions. Affectez le package de stratégie Éducation (étudiant secondaire) à un lot d’étudiants secondaires afin de limiter certaines fonctionnalités telles que les appels privés.|Cmdlets PowerShell dans le module Teams PowerShell|

## <a name="set-the-global-policies"></a>Définir les stratégies globales

Pour définir les stratégies globales (à l’échelle de l’organisation par défaut) pour chaque type de stratégie, suivez ces étapes.

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le navigation gauche du Microsoft Teams d’administration, allez sur la page stratégie pour le type de stratégie que vous voulez mettre à jour. Par exemple, vous **Teams** Teams, les stratégies réunions, les stratégies de messagerie  >  ou les   >  **stratégies**    >  **d’appel vocal.**
2. Sélectionnez **la stratégie globale (à l’échelle de l’organisation par défaut)** pour afficher les paramètres actuels.
3. Mettez à jour la stratégie si nécessaire, puis sélectionnez **Appliquer.**

### <a name="using-powershell"></a>Utiliser PowerShell

Pour définir les stratégies globales à l’aide de PowerShell, utilisez l’identificateur global.  Commencez par examiner la stratégie globale actuelle pour déterminer le paramètre à modifier.

```powershell
Get-CsTeamsMessagingPolicy -Identity Global
 
Identity                      : Global
Description                   :
AllowUrlPreviews              : True
AllowOwnerDeleteMessage       : False
AllowUserEditMessage          : True
AllowUserDeleteMessage        : True
AllowUserChat                 : True
AllowRemoveUser               : True
AllowGiphy                    : True
GiphyRatingType               : Moderate
AllowMemes                    : True
AllowImmersiveReader          : True
AllowStickers                 : True
AllowUserTranslation          : False
ReadReceiptsEnabledType       : UserPreference
AllowPriorityMessages         : True
ChannelsInChatListEnabledType : DisabledUserOverride
AudioMessageEnabledType       : ChatsAndChannels
Expand (20 lines) Collapse 
```

Ensuite, mettez à jour la stratégie globale selon vos besoins.  Il vous suffit de spécifier des valeurs pour les paramètres à modifier.

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a>Attribuer une stratégie à des utilisateurs individuels

Pour affecter une stratégie à un utilisateur individuel ou à un petit nombre d’utilisateurs à la fois, suivez ces étapes.

### <a name="use-the-microsoft-teams-admin-center"></a>Utiliser le Microsoft Teams d’administration

Pour affecter une stratégie à un utilisateur :

1. Dans le panneau de navigation gauche du Microsoft Teams d’administration, sélectionnez Utilisateurs, puis l’utilisateur.
2. Sélectionnez l’utilisateur en cliquant à gauche du nom d’utilisateur, puis **sélectionnez Modifier les paramètres.**
3. Sélectionnez la stratégie que vous voulez attribuer, puis sélectionnez **Appliquer.**

Vous pouvez également :

1. Dans le panneau de navigation gauche du Microsoft Teams d’administration, allez sur la page stratégie.
2. Sélectionnez la stratégie que vous voulez attribuer en cliquant à gauche du nom de la stratégie.
3. Sélectionnez **Gérer les utilisateurs**.
4. Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
5. Lorsque vous avez terminé d’ajouter des utilisateurs, sélectionnez **Appliquer.**

### <a name="use-powershell"></a>Utiliser PowerShell

Chaque type de stratégie dispose de son propre ensemble d’lets de cmdlets pour le gérer. Utilisez `Grant-` l’cmdlet pour un type de stratégie donné pour affecter la stratégie. Par exemple, utilisez l’cmdlet pour affecter une stratégie `Grant-CsTeamsMeetingPolicy` Teams réunion aux utilisateurs. Ces cmdlets sont incluses dans le module Teams PowerShell et sont documentées dans la référence [Skype Entreprise cmdlet.](/powershell/skype/intro?view=skype-ps&preserve-view=true)

Téléchargez et installez [la Teams publique PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) (si vous ne l’avez pas déjà fait), puis exécutez l’application suivante pour vous connecter.

> [!NOTE]
> Skype Entreprise Online Connector fait actuellement partie du dernier module PowerShell Teams.
>
> Si vous utilisez la dernière version [Teams public PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)vous n’avez pas besoin d’installer Skype Entreprise Online Connector.

```powershell
# When using Teams PowerShell Module

Import-Module MicrosoftTeams
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
```

Dans cet exemple, nous affectons une stratégie Teams réunion nommée Stratégie de réunion étudiant à un utilisateur nommé Reda.

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

Pour en savoir plus, [lisez Gérer les stratégies via PowerShell.](teams-powershell-managing-teams.md#manage-policies-via-powershell)

## <a name="assign-a-policy-to-a-group"></a>Affecter une stratégie à un groupe

L’affectation de stratégies à des groupes vous permet d’affecter une stratégie à un groupe d’utilisateurs, tel qu’un groupe de sécurité ou une liste de distribution. L’affectations de stratégie est propagée aux membres du groupe en fonction de règles de priorité. Lorsque les membres sont ajoutés à un groupe ou supprimés de ceux-ci, leurs affectations de stratégie héritées sont mises à jour en conséquence.

L’affectation de stratégies à des groupes est recommandée pour les groupes de jusqu’à 50 000 utilisateurs, mais elle fonctionne également avec des groupes plus importants.

Lorsque vous attribuez la stratégie, elle est immédiatement affectée au groupe. Toutefois, la propagation de l’affectation de stratégie aux membres du groupe est effectuée comme une opération en arrière-plan et peut prendre du temps, selon la taille du groupe. Il en va de même lorsqu’une stratégie est non signée dans un groupe, ou lorsque des membres sont ajoutés ou supprimés d’un groupe.

Les affectations de stratégie de groupe sont propagées uniquement aux utilisateurs qui sont des membres directs du groupe. Les affectations ne sont pas propagées aux membres de groupes imbrmbrés.

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a>Ce que vous devez savoir sur l’affectation d’une stratégie à des groupes

Avant de commencer, il est important de comprendre les règles de priorité et le classement par affectation de groupe.

#### <a name="precedence-rules"></a>Règles de priorité

Pour un type de stratégie donné, la stratégie efficace d’un utilisateur est déterminée selon les informations suivantes :

- Une stratégie assignée directement à un utilisateur est prioritaire sur toute autre stratégie du même type que celle affectée à un groupe. En d’autres termes, si un utilisateur est directement affecté à une stratégie d’un type donné, cet utilisateur n’hérite pas d’une stratégie du même type à partir d’un groupe. Cela signifie également que si un utilisateur a une stratégie d’un type donné qui lui a été directement attribuée, vous devez supprimer cette stratégie de l’utilisateur pour qu’il puisse hériter d’une stratégie du même type à partir d’un groupe.

- Si un utilisateur ne dispose pas directement d’une stratégie et est membre de deux groupes ou plus et que chaque groupe a une stratégie du même type qui lui est attribuée, l’utilisateur hérite de la stratégie de l’affectation de groupe qui présente le classement le plus élevé.

- Si un utilisateur n’est membre d’aucun groupe pour qui une stratégie est attribuée, la stratégie globale (à l’échelle de l’organisation) pour ce type de stratégie s’applique à l’utilisateur.

La stratégie efficace d’un utilisateur est mise à jour en fonction des règles ci-après :

- lorsqu’un utilisateur est ajouté ou supprimé d’un groupe pour qui une stratégie est assignée.
- une stratégie n’est pas signée à partir d’un groupe.
- une stratégie directement attribuée à l’utilisateur est supprimée.

#### <a name="group-assignment-ranking"></a>Classement des affectations de groupe

Lorsque vous attribuez une stratégie à un groupe, vous spécifiez un classement pour l’affectation du groupe. Permet de déterminer la stratégie qu’un utilisateur doit hériter de sa stratégie efficace si l’utilisateur est membre de deux groupes ou plus et qu’une stratégie du même type est assignée à chaque groupe.

Le classement d’affectation de groupe est relatif aux autres affectations de groupe du même type. Par exemple, si vous affectez une stratégie d’appel à deux groupes, définissez le classement d’une affectation sur 1 et l’autre sur 2, 1 étant le plus élevé. Le classement d’affectation de groupe indique quelle appartenance au groupe est plus importante ou plus pertinente que d’autres appartenances de groupe en matière d’héritage.

Par exemple, vous avez deux groupes, Employés du Store et Responsables de magasin. Les deux groupes se sont respectivement attribué une stratégie Teams d’appel, la stratégie d’appel du Store Employees et la Stratégie d’appel des responsables du Store. Pour un responsable de magasin faisant partie des deux groupes, son rôle de responsable est plus pertinent que son rôle d’employé. Par ailleurs, la stratégie d’appel attribuée au groupe Responsables de magasin doit avoir un classement plus élevé.

|Grouper |Teams de la stratégie d’appel  |Classement|
|---------|---------|---|
|Responsables de magasin   |Stratégie d’appel des responsables de magasin         |1|
|Employés du Store    |Stratégie d’appel du Store Employees      |2|

Si vous ne spécifiez pas de classement, l’affectation de stratégie se voir attribué le classement le plus faible.

### <a name="in-the-teams-admin-center"></a>Dans le Teams d’administration

> [!NOTE]
> Pour l’instant, l’affectation de stratégies à des groupes à l’aide du Centre d’administration Microsoft Teams est disponible uniquement pour la stratégie d’appel Teams, la stratégie de parcage d’appel Teams, la stratégie Teams, la stratégie d’événements en direct Teams, la stratégie de réunion Teams et la stratégie de messagerie Teams. Pour d’autres types de stratégie, utilisez PowerShell.

1. Dans le navigation gauche du Microsoft Teams d’administration, allez à la page du type de stratégie. Par exemple, allez à **Stratégies de**  >  **réunion.**

2. Sélectionnez **l’onglet Affectation de stratégie de** groupe.

3. Sélectionnez **Ajouter un** groupe, puis dans le volet **Affecter** une stratégie à un groupe, comme suit :
    1. Recherchez et ajoutez le groupe à qui vous voulez affecter la stratégie.
    2. Définissez le classement pour l’affectation de groupe.
    3. Sélectionnez la stratégie à affecter.
    4. Sélectionnez **Appliquer.**

Pour supprimer une affectation de  stratégie de groupe, dans l’onglet Affectation de stratégie de groupe de la page stratégie, sélectionnez l’affectation de groupe, puis sélectionnez **Supprimer.**

Pour modifier le classement d’une affectation de groupe, vous devez d’abord supprimer l’affectation de stratégie de groupe. Suivez ensuite les étapes ci-dessus pour affecter la stratégie à un groupe.

### <a name="use-the-powershell-option"></a>Utiliser l’option PowerShell

> [!NOTE]
> Actuellement, l’affectation de stratégies à des groupes à l’aide de PowerShell n’est pas disponible pour tous Teams types de stratégies. Pour obtenir la liste des types de stratégies pris en charge, voir [New-CsGroupPolicyAssignment.](/powershell/module/teams/new-csgrouppolicyassignment)

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installer et se connecter au module PowerShell Microsoft Teams’équipe

Pour obtenir des instructions pas à pas, voir [Installer Teams PowerShell.](teams-powershell-install.md)

#### <a name="assign-a-policy-to-a-group-of-users"></a>Affecter une stratégie à un groupe d’utilisateurs

Utilisez [l’cmdlet New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) pour affecter une stratégie à un groupe. Vous pouvez spécifier un groupe à l’aide de l’ID d’objet, de l’adresse SIP ou de l’adresse de messagerie.

Dans cet exemple, nous affectons une stratégie Teams réunion nommée Stratégie de réunion des responsables de vente au détail à un groupe avec un classement d’affectations de 1.

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a>Obtenir des affectations de stratégie pour un groupe

Utilisez [l’cmdlet Get-CsGroupPolicyAssignment](/powershell/module/teams/get-csgrouppolicyassignment) pour attribuer toutes les stratégies à un groupe. Notez que les groupes sont toujours répertoriés par leur ID de groupe, même si leur adresse SIP ou adresse de messagerie a été utilisée pour affecter la stratégie.

Dans cet exemple, nous récupérons toutes les stratégies affectées à un groupe spécifique.

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

Dans cet exemple, nous renvoyons tous les groupes à qui une stratégie Teams réunion est affectée.

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a>Supprimer une stratégie d’un groupe

Utilisez [l’cmdlet Remove-CsGroupPolicyAssignment](/powershell/module/teams/remove-csgrouppolicyassignment) pour supprimer une stratégie d’un groupe. Lorsque vous supprimez une stratégie d’un groupe, les priorités des autres stratégies du même type attribuées à ce groupe (avec un classement inférieur) sont mises à jour. Par exemple, si vous supprimez une stratégie qui présente un classement de 2, les stratégies dont le classement est 3 et 4 sont mises à jour pour refléter leur nouveau classement. Les deux tableaux suivants illustrent cet exemple.

Voici une liste des affectations de stratégies et des priorités pour une stratégie de Teams réunion.

|Nom du groupe  |Nom de la stratégie  |Classement|
|---------|---------|---------|
|Ventes    |Politique commerciale       | 1        |
|Région Ouest     |Politique de la région Ouest         |2         |
|Division    |Stratégie de division         |3         |
|Filiale   |Stratégie de filiale        |4         |

Si nous ôtons la stratégie de la région Ouest du groupe Région Ouest, les affectations de stratégie et les priorités sont mises à jour comme suit.

|Nom du groupe  |Nom de la stratégie  |Classement|
|---------|---------|---------|
|Ventes    |Politique commerciale       | 1        |
|Division    |Stratégie de division         |2         |
|Filiale   |Stratégie de filiale        |3        |

Dans cet exemple, nous allons supprimer la stratégie Teams réunion d’un groupe.

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a>Modifier une affectation de stratégie pour un groupe

> [!NOTE]
> [L’cmdlet Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) sera bientôt disponible. En attendant, pour modifier une affectation de stratégie de groupe, vous pouvez supprimer l’affectation de stratégie actuelle du groupe, puis ajouter une nouvelle affectation de stratégie.

Après avoir attribué une stratégie à un groupe, vous pouvez utiliser l’cmdlet [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) pour modifier l’affectation de stratégie de ce groupe comme suit :

- Modifier le classement
- Modifier la stratégie d’un type de stratégie donné
- Modifier la stratégie d’un type de stratégie donné et le classement

Dans cet exemple, nous avons changé la stratégie d’un groupe en Teams par une stratégie nommée SupportCallPark et le classement d’affectations à 3.

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a>Modifier la stratégie efficace d’un utilisateur

Voici un exemple de la façon de modifier la stratégie efficace pour un utilisateur à qui une stratégie est directement attribuée.

Tout d’abord, nous utilisons la cmdlet [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment) avec le paramètre pour obtenir les détails des stratégies de diffusion de réunion Teams associées à ```PolicySource``` l’utilisateur.

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

La sortie indique que l’utilisateur a été directement affecté à une stratégie de diffusion de réunion Teams nommée Événements d’employés, qui prend le pas sur la stratégie Événements en direct du fournisseur qui est attribuée à un groupe auquel l’utilisateur appartient.

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

À présent, nous ôtons la stratégie Événements d’employés de l’utilisateur. Cela signifie que l’utilisateur n’a plus de stratégie de diffusion de réunion Teams qui lui est directement attribuée et hérite de la stratégie Événements en direct du fournisseur qui est attribuée au groupe dont l’utilisateur appartient.

Pour ce faire, utilisez l’cmdlet Skype Entreprise le module PowerShell suivant.

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

Utilisez l’cmdlet suivante dans le module Teams PowerShell pour le faire à l’échelle même si vous avez une affectation de stratégie de lot, où $users est une liste d’utilisateurs que vous spécifiez.

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>Affecter une stratégie à un lot d’utilisateurs

### <a name="use-the-admin-center"></a>Utiliser le Centre d’administration

Pour affecter une stratégie aux utilisateurs en bloc :

1. Dans le navigation gauche du centre d Microsoft Teams d’administration, sélectionnez **Utilisateurs.**

2. Recherchez les utilisateurs à qui vous voulez affecter la stratégie ou filtrez l’affichage pour afficher les utilisateurs que vous souhaitez.

3. Dans la colonne **&#x2713;** (coche), sélectionnez les utilisateurs. Pour sélectionner tous les utilisateurs, cliquez sur &#x2713; (coche) en haut du tableau.

4. Sélectionnez **Modifier les paramètres,** a apporter les modifications de votre choix, puis **sélectionnez Appliquer.**

Pour afficher l’état de votre affectation de stratégie, dans la bannière  qui apparaît en haut de la **page** Utilisateurs après avoir sélectionné Appliquer pour envoyer votre affectation de stratégie, sélectionnez Journal **d’activité.** Dans le navigation gauche du centre d’administration Microsoft Teams, sélectionnez Tableau de **bord,** puis sous Journal d’activité, sélectionnez Afficher les **détails.** Le journal d’activité affiche les affectations de stratégie à des lots de plus de 20 utilisateurs via le Centre Microsoft Teams d’administration à partir des 30 derniers jours. Pour plus d’informations, [voir Afficher vos affectations de stratégie dans le journal d’activité.](activity-log.md)

### <a name="use-powershell-method"></a>Utiliser la méthode PowerShell

> [!NOTE]
> Actuellement, l’affectation de stratégie de lot à l’aide de PowerShell n’est pas disponible pour tous Teams types de stratégies. Pour obtenir la liste des types de stratégies pris en charge, voir [New-CsBatchPolicyAssignmentOperation.](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

L’affectation de stratégie de lot vous permet d’affecter une stratégie à de grands ensembles d’utilisateurs à la fois sans utiliser de script. Vous utilisez la [cmdlet New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) pour envoyer un lot d’utilisateurs et la stratégie que vous voulez attribuer. Les attributions sont traitées comme une opération d’arrière-plan et un ID d’opération est généré pour chaque lot. Vous pouvez ensuite utiliser la cmdlet [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) pour suivre l’avancement et l’état des devoirs d’un lot.

Spécifiez les utilisateurs selon leur ID d’objet ou leur adresse SIP (Session Initiation Protocol). L’adresse SIP d’un utilisateur a souvent la même valeur que le nom d’utilisateur principal (UPN) ou l’adresse de courrier, mais cela n’est pas obligatoire. Si un utilisateur est spécifié à l’aide de son nom d’utilisateur supérieur ou de son adresse de courrier, mais que sa valeur est différente de celle de son adresse SIP, l’attribution de stratégie échoue pour l’utilisateur. Si un lot inclut des utilisateurs en double, les doublons sont supprimés du lot avant que le traitement et l’état ne soient fournis qu’aux utilisateurs uniques restants du lot.

Un lot peut contenir jusqu’à 5 000 utilisateurs. Pour de meilleurs résultats, n’envoyez pas plus de quelques lots à la fois. Autorisez le traitement des lots avant l’envoi d’autres lots.

#### <a name="install-and-connect-to-the-teams-powershell-module"></a>Installer et se connecter au module PowerShell Teams’équipe

Exécutez la commande suivante pour installer [Microsoft Teams module PowerShell.](https://www.powershellgallery.com/packages/MicrosoftTeams) Veillez à installer la version 1.0.5 ou ultérieure.

```powershell
Install-Module -Name MicrosoftTeams
```

Exécutez ce qui suit pour vous connecter Teams et démarrer une session.

```powershell
Connect-MicrosoftTeams
```

Lorsque vous y êtes invité, connectez-vous à l’aide de vos informations d’identification d’administrateur.

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a>Installer et se connecter au module Azure AD PowerShell Graph (facultatif)

Vous pouvez également télécharger et installer le [module Azure AD PowerShell](/powershell/azure/active-directory/install-adv2) pour Graph (si ce n’est déjà fait) et vous connecter à Azure AD afin de récupérer la liste des utilisateurs de votre organisation.

Exécutez ce qui suit pour vous connecter à Azure AD.

```powershell
Connect-AzureAD
```

Lorsque vous y êtes invité, connectez-vous à l’aide des mêmes informations d’identification d’administrateur que vous avez utilisées pour vous connecter à Teams.

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a>Affecter une stratégie d’installation à un lot d’utilisateurs

Dans cet exemple, nous utilisons la cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) pour affecter une stratégie de configuration d’application nommée HR App Setup Policy à un lot d’utilisateurs répertoriés dans le fichier Users_ids.text.

```powershell
$users_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

Dans cet exemple, nous nous connectons à Azure AD pour récupérer un ensemble d’utilisateurs, puis affectons une stratégie de messagerie nommée Stratégie de messagerie nouvelle embauche à un lot d’utilisateurs spécifiés à l’aide de leur adresse SIP.

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a>Obtenir l’état d’une affectation de lot

Exécutez ce qui suit pour obtenir l’état d’une affectation de lot, où OperationId est l’ID d’opération renvoyé par `New-CsBatchPolicyAssignmentOperation` l’cmdlet pour un lot donné.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Si la sortie indique qu’une erreur s’est produite, exécutez l’erreur suivante pour obtenir plus d’informations sur les erreurs, qui se trouver dans la `UserState` propriété.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Pour en savoir plus, [consultez Get-CsBatchPolicyAssignmentOperation.](/powershell/module/teams/get-csbatchpolicyassignmentoperation)

## <a name="assign-a-policy-package-to-users"></a>Attribuer un package de stratégies aux utilisateurs

Un package de stratégie dans Teams est un ensemble de stratégies et paramètres de stratégie prédéfinés que vous pouvez affecter aux utilisateurs ayant des rôles identiques ou similaires dans votre organisation. Chaque package de stratégie est conçu autour d’un rôle d’utilisateur et inclut des stratégies et paramètres de stratégie prédéfinés qui supportent des activités classiques pour ce rôle. Le package Éducation (enseignant) et le package Soins de santé (travailleurs cliniques) sont quelques exemples de packages de stratégie. Pour plus d’informations, [voir Gérer les packages de stratégie dans Teams.](manage-policy-packages.md)

### <a name="assign-a-policy-package-to-one-user"></a>Attribuer un package de stratégie à un utilisateur

1. Dans le panneau de navigation gauche du Microsoft Teams d’administration, sélectionnez Utilisateurs, puis l’utilisateur.

2. Dans la page de l’utilisateur, sélectionnez **Stratégies,** puis, à côté du **package** de stratégie, sélectionnez **Modifier.**

3. Dans le **volet Attribuer un package** de stratégie, sélectionnez le package à attribuer, puis sélectionnez **Enregistrer.**

### <a name="assign-a-policy-package-to-multiple-users"></a>Attribuer un package de stratégie à plusieurs utilisateurs

1. Dans le navigation gauche du Centre d’administration Microsoft Teams, sélectionnez Packages de **stratégie,** puis sélectionnez le package de stratégie à attribuer en cliquant à gauche du nom du package.

2. Sélectionnez **Gérer les utilisateurs**.

3. Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.

4. Lorsque vous avez terminé d’ajouter des utilisateurs, sélectionnez **Enregistrer.**

## <a name="assign-a-policy-package-to-a-group"></a>Attribuer le package stratégie à un groupe

Attribution de package de stratégie aux groupes vous permet d’attribuer plusieurs stratégies à un groupe d’utilisateurs, tel qu’un groupe de sécurité ou une liste de distribution. L’affectations de stratégie est propagée aux membres du groupe en fonction de règles de priorité. Lorsque les membres sont ajoutés à un groupe ou supprimés de ceux-ci, leurs affectations de stratégie héritées sont mises à jour en conséquence.

L’affectation de package de stratégie à des groupes est recommandée pour les groupes de jusqu’à 50 000 utilisateurs, mais elle fonctionne également avec les groupes plus importants.

Lorsque vous attribuez le package de stratégie, il est immédiatement affecté au groupe. Toutefois, la propagation de l’affectation de stratégie aux membres du groupe est effectuée comme une opération en arrière-plan et peut prendre du temps, selon la taille du groupe. Il en va de même lorsqu’une stratégie est non signée dans un groupe, ou lorsque des membres sont ajoutés ou supprimés d’un groupe.

> [!IMPORTANT]
> Avant de commencer, il est [](#precedence-rules) important de comprendre les règles de priorité et le [classement d’affectation de groupe.](#group-assignment-ranking) Assurez-vous de lire et de comprendre les concepts de ce que vous devez savoir sur l’affectation de stratégie aux groupes [plus](#what-you-need-to-know-about-policy-assignment-to-groups) tôt dans cet article.

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a>Attribuer un package de stratégie à un groupe d’utilisateurs dans le Centre d’administration

1. Se connecter au Centre d’administration de Microsoft Teams.
2. Dans le dossier de navigation de gauche, allez à la page du package de stratégie.
3. Sélectionnez l’onglet d’affectation du package de groupe.
4. Sélectionnez **Ajouter un groupe,** puis dans le volet Affecter un package de stratégie au volet de groupe, comme suit :

   - Recherchez et ajoutez le groupe à qui vous voulez affecter le package de stratégie.

2. Dans le dossier de navigation de gauche, allez à la page du package de stratégie.

3. Sélectionnez l’onglet Affectation de stratégie de groupe.

4. Sélectionnez **Ajouter un groupe,** puis dans le volet Affecter un package de stratégie au volet de groupe, comme suit :

    1. Recherchez et ajoutez le groupe à qui vous voulez affecter le package de stratégie.
    
    1. Sélectionnez un package de stratégie.
    
    1. Définissez le classement pour chaque type de stratégie.
    
    1. Sélectionnez **Appliquer.**
    
    ![affiche l’affectation de stratégie de groupe.](media/group-pkg-assignment.png)

5. Pour gérer le classement d’un type de stratégie spécifique, accédez à la page de stratégie spécifique.

6. Pour réattribuer un package de stratégie à un groupe, supprimez tout d’abord l’affectation de stratégie de groupe. Ensuite, suivez les étapes ci-dessus pour affecter le package de stratégie à un groupe.

### <a name="work-with-powershell"></a>Travailler avec PowerShell

#### <a name="get-the-teams-powershell-module"></a>Obtenir le module PowerShell Teams’équipe

Pour obtenir des instructions pas à pas, voir [Installer Teams PowerShell.](teams-powershell-install.md)

#### <a name="assign-a-policy-package-to-a-group-of-users"></a>Affecter un package de stratégie à un groupe d’utilisateurs

Utilisez la [cmdlet Grant-CsGroupPolicyPackageAssignment](/powershell/module/teams/grant-csgrouppolicypackageassignment) pour affecter un package de stratégie à un groupe. Vous pouvez spécifier un groupe à l’aide de l’ID d’objet, de l’adresse SIP ou de l’adresse de messagerie. Lorsque vous attribuez le package de stratégie, spécifiez un classement [d’affectation](#group-assignment-ranking) de groupe pour chaque type de stratégie dans le package de stratégie.

Dans cet exemple, nous affectons le package de stratégie Education_Teacher à un groupe avec un classement d’affectations de 1 pour TeamsAppSetupPolicy et TeamsMeetingBroadcastPolicy et un classement de 2 pour TeamsMeetingPolicy.

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a>Affecter un package de stratégie à un lot d’utilisateurs

L’affectation de package de stratégie de lot vous permet d’affecter un package de stratégie à de grands ensembles d’utilisateurs à la fois sans utiliser de script. Vous utilisez la cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) pour envoyer un lot d’utilisateurs et le package de stratégie que vous souhaitez affecter. Les attributions sont traitées comme une opération d’arrière-plan et un ID d’opération est généré pour chaque lot. Vous pouvez ensuite utiliser la cmdlet [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) pour suivre l’avancement et l’état des devoirs d’un lot.

Spécifiez les utilisateurs selon leur ID d’objet ou leur adresse SIP (Session Initiation Protocol). L’adresse SIP d’un utilisateur a souvent la même valeur que le nom d’utilisateur principal (UPN) ou l’adresse de courrier, mais cela n’est pas obligatoire. Si un utilisateur est spécifié à l’aide de son nom d’utilisateur supérieur ou de son adresse de courrier, mais que sa valeur est différente de celle de son adresse SIP, l’attribution de stratégie échoue pour l’utilisateur. Si un lot inclut des utilisateurs en double, les doublons sont supprimés du lot avant que le traitement et l’état ne soient fournis qu’aux utilisateurs uniques restants du lot.

Un lot contient jusqu’à 5 000 utilisateurs. Pour de meilleurs résultats, n’envoyez pas plus de quelques lots à la fois. Autorisez le traitement des lots avant l’envoi d’autres lots.

### <a name="use-the-teams-powershell-module"></a>Utiliser le module Teams PowerShell

Exécutez la commande suivante pour installer [Microsoft Teams module PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (si vous ne l’avez pas déjà fait). Veillez à installer la version 1.0.5 ou ultérieure.

```powershell
Install-Module -Name MicrosoftTeams
```

Exécutez ce qui suit pour vous connecter Teams et démarrer une session.

```powershell
Connect-MicrosoftTeams
```

Lorsque vous y êtes invité, connectez-vous à l’aide de vos informations d’identification d’administrateur.

### <a name="assign-policy-packages-to-a-batch-of-users"></a>Attribuer des packages de stratégie à un lot d’utilisateurs

Dans cet exemple, nous utilisons la cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) pour affecter le package de stratégie Education_PrimaryStudent à un lot d’utilisateurs.

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a>Voir l’état d’une affectation de lot

Exécutez ce qui suit pour obtenir l’état d’une affectation de lot, où OperationId est l’ID d’opération renvoyé par `New-CsBatchPolicyAssignmentOperation` l’cmdlet pour un lot donné.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Si la sortie indique qu’une erreur s’est produite, exécutez l’erreur suivante pour obtenir plus d’informations sur les erreurs, qui se trouver dans la `UserState` propriété.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Pour en savoir plus, [consultez Get-CsBatchPolicyAssignmentOperation.](/powershell/module/teams/get-csbatchpolicyassignmentoperation)

## <a name="related-topics"></a>Sujets associés

[Aperçu de Teams PowerShell](teams-powershell-overview.md)
