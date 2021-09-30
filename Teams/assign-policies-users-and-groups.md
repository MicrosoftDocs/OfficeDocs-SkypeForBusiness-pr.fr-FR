---
title: Attribuer des stratégies aux utilisateurs et aux groupes
author: KarliStites
ms.author: kastites
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
description: Découvrez les différentes façons d’attribuer des stratégies aux utilisateurs et aux groupes dans Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: b896e823339b1b40ff31036c0e53308bbbe1107b
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60011498"
---
# <a name="assign-policies-to-users-and-groups"></a>Attribuer des stratégies aux utilisateurs et aux groupes

Cet article décrit les différentes manières d’affecter des stratégies aux utilisateurs et aux groupes dans Microsoft Teams. Avant de lire, assurez-vous de lire Attribuer [des stratégies dans Teams.](policy-assignment-overview.md)

## <a name="assign-a-policy-to-individual-users"></a>Attribuer une stratégie à des utilisateurs individuels

Pour affecter une stratégie à un utilisateur individuel ou à un petit nombre d’utilisateurs à la fois, suivez ces étapes.

### <a name="use-the-microsoft-teams-admin-center"></a>Utiliser le Centre d’administration Microsoft Teams

Pour affecter une stratégie à un utilisateur :

1. Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, sélectionnez Utilisateurs, puis l’utilisateur.
2. Sélectionnez l’utilisateur en cliquant à gauche du nom d’utilisateur, puis **sélectionnez Modifier les paramètres.**
3. Sélectionnez la stratégie que vous voulez attribuer, puis sélectionnez **Appliquer.**

![Assignez une stratégie à un utilisateur dans le Centre d’administration Teams.](media/assign-policy-user.png)

Vous pouvez également :

1. Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, allez sur la page stratégie.
2. Sélectionnez la stratégie que vous voulez attribuer en cliquant à gauche du nom de la stratégie.
3. Sélectionnez **Gérer les utilisateurs**.
4. Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
5. Lorsque vous avez terminé d’ajouter des utilisateurs, sélectionnez **Appliquer.**

![Affectez une stratégie à un utilisateur dans le Centre d’administration Teams via une deuxième méthode.](media/assign-policy-user2.png)

### <a name="use-powershell"></a>Utiliser PowerShell

Chaque type de stratégie dispose de son propre ensemble d’lets de cmdlets pour le gérer. Utilisez `Grant-` l’cmdlet pour un type de stratégie donné pour affecter la stratégie. Par exemple, utilisez `Grant-CsTeamsMeetingPolicy` l’cmdlet pour affecter une stratégie de réunion Teams aux utilisateurs. Ces cmdlets sont incluses dans le module Teams PowerShell et sont documentées dans la référence de [l’cmdlet Skype Entreprise.](/powershell/skype)

 Téléchargez et installez la version [publique Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) (si vous ne l’avez pas déjà fait), puis exécutez l’application suivante pour vous connecter.

> [!NOTE]
> Skype Entreprise Online Connector fait actuellement partie du dernier module PowerShell Teams.
>
> Si vous utilisez la dernière version publique [de Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)vous n’avez pas besoin d’installer Skype Entreprise Online Connector.

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

Dans cet exemple, nous affectons une stratégie de réunion Teams nommée Stratégie de réunion étudiant à un utilisateur nommé Reda.

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

Le classement d’affectation de groupe est relatif aux autres affectations de groupe du même type. Par exemple, si vous affectez une stratégie d’appel à deux groupes, définissez le classement d’une affectation sur 1 et l’autre sur 2, 1 étant le plus élevé. Le classement d’affectation de groupe indique quelle appartenance au groupe est plus importante ou plus pertinente que d’autres appartenances de groupe en ce qui concerne l’héritage.

Par exemple, vous avez deux groupes, Employés du Store et Responsables de magasin. Les deux groupes ont respectivement une stratégie d’appel Teams, une stratégie d’appel des employés du Store et une stratégie d’appel pour les responsables du Magasin. Pour un responsable de magasin faisant partie des deux groupes, son rôle de responsable est plus pertinent que son rôle d’employé. Par ailleurs, la stratégie d’appel attribuée au groupe Responsables de magasin doit avoir un classement plus élevé.

|Grouper |Nom de la stratégie d’appel Teams  |Classement|
|---------|---------|---|
|Responsables de magasin   |Stratégie d’appel des responsables de magasin         |1|
|Employés du Store    |Stratégie d’appel du Store Employees      |2|

Si vous ne spécifiez pas de classement, l’affectation de stratégie se voir attribué le classement le plus faible.

### <a name="in-the-teams-admin-center"></a>Dans le Centre d’administration Teams

> [!NOTE]
> Pour l’instant, l’affectation de stratégies à des groupes utilisant le Centre d’administration Microsoft Teams est disponible uniquement pour la stratégie d’appel de Teams, la stratégie de parc d’appels Teams, la stratégie Teams, la stratégie d’événements en direct Teams, la stratégie de réunion Teams et la stratégie de messagerie Teams. Pour d’autres types de stratégie, utilisez PowerShell.

1. Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, allez sur la page du type de stratégie. Par exemple, allez à **Stratégies de**  >  **réunion.**
2. Sélectionnez **l’onglet Affectation de stratégie de** groupe.
3. Sélectionnez **Ajouter un** groupe, puis dans le volet **Affecter** une stratégie à un groupe, comme suit :
    1. Recherchez et ajoutez le groupe à qui vous voulez affecter la stratégie.
    2. Définissez le classement pour l’affectation de groupe.
    3. Sélectionnez la stratégie à affecter.
    4. Sélectionnez **Appliquer.**
    
![Assignez une stratégie à un groupe dans le Centre d’administration Teams.](media/assign-policy-group.png)

Pour supprimer une affectation de  stratégie de groupe, dans l’onglet Affectation de stratégie de groupe de la page stratégie, sélectionnez l’affectation de groupe, puis sélectionnez **Supprimer.**

Pour modifier le classement d’une affectation de groupe, vous devez d’abord supprimer l’affectation de stratégie de groupe. Suivez ensuite les étapes ci-dessus pour affecter la stratégie à un groupe.

### <a name="use-the-powershell-option"></a>Utiliser l’option PowerShell

> [!NOTE]
> Actuellement, l’affectation de stratégies à des groupes à l’aide de PowerShell n’est pas disponible pour tous les types de stratégie Teams. Pour obtenir la liste des types de stratégies pris en charge, voir [New-CsGroupPolicyAssignment.](/powershell/module/teams/new-csgrouppolicyassignment)

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installer et se connecter au module Microsoft Teams PowerShell

Pour obtenir une aide étape par étape, voir [Installer Teams PowerShell.](teams-powershell-install.md)

#### <a name="assign-a-policy-to-a-group-of-users"></a>Affecter une stratégie à un groupe d’utilisateurs

Utilisez [l’cmdlet New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) pour affecter une stratégie à un groupe. Vous pouvez spécifier un groupe à l’aide de l’ID d’objet, de l’adresse SIP ou de l’adresse de messagerie.

Dans cet exemple, nous affectons une stratégie de réunion Teams nommée Stratégie de réunion des responsables de vente au détail à un groupe avec un classement d’affectations de 1.

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

Tout d’abord, nous utilisons la cmdlet [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment) avec le paramètre pour obtenir les détails des stratégies de diffusion de réunion Teams associées à `PolicySource` l’utilisateur.

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
$user_ids = Get-Content .\users_ids.txt
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

## <a name="related-topics"></a>Voir aussi

- [Gérer les Teams des stratégies](manage-teams-with-policies.md)
- [Aperçu de Teams PowerShell](teams-powershell-overview.md)
- [Attribuer des stratégies dans Teams - mise en place](policy-assignment-overview.md)
