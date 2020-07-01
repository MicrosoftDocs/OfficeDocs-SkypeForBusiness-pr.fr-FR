---
title: Attribuer des stratégies à vos utilisateurs dans Microsoft Teams.
author: lanachin
ms.author: v-lanac
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
localization_priority: Normal
search.appverid: MET150
description: Découvrez les différentes méthodes d’attribution de stratégies aux utilisateurs de Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 403131fa3e7bd2b3fb2a128640ac49497394d669
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938543"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a>Attribuer des stratégies à vos utilisateurs dans Microsoft Teams.

> [!NOTE]
> **Notez ce qui suit à propos de l’une des fonctionnalités décrites dans cet article intitulé affectation de stratégie aux groupes**: 
> - Une [affectation de stratégie à des groupes à l’aide du centre d’administration Microsoft teams](#using-the-microsoft-teams-admin-center-3)n’a pas encore été publiée. Il a été annoncé et est bientôt disponible. 
> - [Pour l’instant, l’attribution de stratégies aux groupes à l’aide de PowerShell](#using-powershell-3)n’est disponible qu’en version préliminaire privée. Les applets de connexion PowerShell de cette fonctionnalité se trouvent dans le module pre-version PowerShell Teams.
>
> Pour en savoir plus sur l’état de publication de cette fonctionnalité, consultez la [documentation Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185).

En tant qu’administrateur, vous utilisez des stratégies pour contrôler les fonctionnalités d’équipes disponibles pour les utilisateurs de votre organisation. Par exemple, il existe des stratégies d’appel, des stratégies de réunion et des stratégies de messagerie pour n’appeler qu’un seul nom.

Les organisations ont différents types d’utilisateurs dotés de besoins uniques et de stratégies personnalisées que vous créez et attribuez les paramètres de stratégie à différents ensembles d’utilisateurs en fonction de vos besoins.

Pour faciliter la gestion des stratégies au sein de votre organisation, teams permet d’attribuer des stratégies aux utilisateurs de différentes manières. Vous pouvez affecter une stratégie directement aux utilisateurs, individuellement ou à la fois par le biais d’une affectation par lot ou à un groupe dont les utilisateurs sont membres. Vous pouvez également utiliser des packages de stratégie pour affecter une collection prédéfinie de stratégies aux utilisateurs de votre organisation possédant des rôles similaires. L’option que vous choisissez dépend du nombre de stratégies que vous gérez et du nombre d’utilisateurs auxquels vous attribuez. En définissant les stratégies globales par défaut de l’organisation, afin qu’elles s’appliquent au plus grand nombre d’utilisateurs de votre organisation, il vous suffit d’affecter des stratégies aux utilisateurs qui ont besoin de stratégies spécialisées.

Cet article décrit les différentes façons dont vous pouvez attribuer des stratégies aux utilisateurs et les scénarios recommandés pour les situations dans lesquelles utiliser.

## <a name="which-policy-takes-precedence"></a>Quelle est la stratégie prioritaire ?

Un utilisateur dispose d’une stratégie efficace pour chaque type de stratégie. Il est possible, ou même probable, que l’utilisateur dispose d’une stratégie directement affectée et qu’il soit membre d’un ou plusieurs groupes auxquels une stratégie du même type est affectée. Dans ces types de scénarios, quelle stratégie est prioritaire ?  La stratégie d’effectivité d’un utilisateur est déterminée conformément aux règles de priorité, comme suit.

Si un utilisateur dispose d’une stratégie (individuelle ou par le biais d’une affectation de lot), cette stratégie est prioritaire. Dans l’exemple suivant, la stratégie effective de l’utilisateur est la stratégie de réunion carrée d’Lincoln, qui est directement affectée à l’utilisateur.

![Diagramme montrant comment une stratégie attribuée directement est prioritaire](media/assign-policies-example-directly-assigned.png)

Si un utilisateur n’a pas directement affecté une stratégie d’un type donné, la stratégie affectée à un groupe dont l’utilisateur est membre de a la priorité. Si un utilisateur est membre de plusieurs groupes, la stratégie présentant le niveau de [classement des affectations de groupe](#group-assignment-ranking) le plus élevé pour le type de stratégie donné est prioritaire.

Dans cet exemple, la stratégie effective de l’utilisateur est la stratégie d’exécution et la stratégie HD, qui présente le niveau d’attribution le plus élevé par rapport aux autres groupes dont l’utilisateur est membre et auquel une stratégie du même type de stratégie est affectée.  

![Diagramme montrant comment une stratégie héritée du groupe est prioritaire](media/assign-policies-example-group.png)

Si un utilisateur n’est pas directement affecté à une stratégie ou n’est pas membre de tous les groupes auxquels une stratégie est affectée, l’utilisateur obtient la stratégie globale (par défaut de l’organisation par défaut) pour ce type de stratégie. Voici un exemple :

![Diagramme illustrant le niveau de priorité d’une stratégie globale](media/assign-policies-example-global.png)

Pour en savoir plus, voir [règles de précédence](#precedence-rules).

## <a name="ways-to-assign-policies"></a>Méthodes d’attribution de stratégies

Vous trouverez ci-dessous une vue d’ensemble des méthodes permettant d’attribuer des stratégies aux utilisateurs et les scénarios recommandés pour chacun. Cliquez sur les liens pour en savoir plus.

Avant d’affecter des stratégies à des utilisateurs ou des groupes spécifiques, commencez par [définir les stratégies globales par défaut](#set-the-global-policies) de l’organisation afin qu’elles s’appliquent au plus grand nombre d’utilisateurs de votre organisation.  Une fois les stratégies globales définies, vous n’aurez besoin d’affecter des stratégies qu’aux utilisateurs qui ont besoin de stratégies spécialisées.

|Procédez comme suit…  |Si...  | Utilisation de...
|---------|---------|----|
|[Assigner une stratégie à des utilisateurs individuels](#assign-a-policy-to-individual-users)    | Vous débutez en équipe et vous commencez simplement à attribuer une ou plusieurs stratégies à un petit nombre d’utilisateurs. |Centre d’administration Microsoft teams ou cmdlets PowerShell dans le module PowerShell de Skype entreprise Online
| [Assigner un package de stratégie](#assign-a-policy-package)   | Vous devez affecter plusieurs stratégies à des ensembles d’utilisateurs spécifiques de votre organisation qui ont des rôles identiques ou similaires. Par exemple, attribuez le package de stratégie éducation (enseignant) aux enseignants de votre établissement scolaire pour leur permettre d’accéder à l’ensemble des conversations, appels et réunions, ainsi que le package d’étude (étudiant d’école secondaire) aux étudiants secondaires pour limiter certaines fonctionnalités, telles que les appels privés.  |Centre d’administration Microsoft teams ou cmdlets PowerShell dans le module PowerShell teams|
|[Attribuer une stratégie à un lot d’utilisateurs](#assign-a-policy-to-a-batch-of-users)   | Vous devez attribuer des stratégies à d’importants ensembles d’utilisateurs. Par exemple, vous pouvez attribuer une stratégie à des centaines ou des milliers d’utilisateurs de votre organisation à la fois.  |Centre d’administration Microsoft teams ou cmdlets PowerShell dans le module PowerShell teams|
|[Assigner une stratégie à un groupe](#assign-a-policy-to-a-group) (dans Preview ou bientôt disponible)|Vous devez attribuer des stratégies en fonction de l’appartenance d’un utilisateur à un groupe. Par exemple, vous souhaitez attribuer une stratégie à l’ensemble des utilisateurs d’un groupe de sécurité ou d’une unité d’organisation.| Centre d’administration de Microsoft Teams (bientôt disponible) ou cmdlets PowerShell dans le module PowerShell Teams (en version préliminaire)|
| [Affectation d’un package de stratégie à un lot d’utilisateurs](#assign-a-policy-package-to-a-batch-of-users)|Vous devez affecter plusieurs stratégies à un lot d’utilisateurs de votre organisation qui ont des rôles identiques ou similaires. Par exemple, attribuez le package de stratégie éducation (enseignant) à tous les enseignants de votre établissement scolaire à l’aide de la fonctionnalité d’attribution de lot pour leur permettre d’accéder à des conversations, des appels et des réunions, et d’affecter le package de stratégie éducation (école secondaire) à un lot d’étudiants secondaires pour limiter certaines fonctionnalités telles que les appels privés.|Cmdlets PowerShell dans le module PowerShell teams|
| Assigner un package de stratégie à un groupe (bientôt disponible)   | ||

## <a name="set-the-global-policies"></a>Définir les stratégies globales

Pour définir les stratégies globales par défaut de chaque type de stratégie, procédez comme suit.

### <a name="using-the-microsoft-teams-admin-center"></a>Utilisation du centre d’administration Microsoft Teams

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à la page de stratégie correspondant au type de stratégie que vous voulez mettre à jour. Par **exemple, les**politiques teams Teams, les stratégies de  >  **Teams policies** **Meetings**  >  **réunions**, les **stratégies de messagerie**ou les politiques d' **Voice**  >  **appel**vocal.
2. Sélectionnez la stratégie **globale par défaut** de l’Organisation pour afficher les paramètres actuels.
3. Mettez à jour la stratégie selon vos besoins, puis sélectionnez **appliquer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Pour définir les stratégies globales à l’aide de PowerShell, utilisez l’identificateur global.  Commencez par examiner la stratégie globale actuelle pour déterminer le paramètre que vous voulez modifier.

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

Ensuite, mettez à jour la stratégie globale selon vos besoins.  Il vous suffit de spécifier des valeurs pour les paramètres que vous souhaitez modifier. 
 
```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a>Assigner une stratégie à des utilisateurs individuels

Procédez comme suit pour attribuer une stratégie à un utilisateur individuel ou à un petit nombre d’utilisateurs à la fois.

### <a name="using-the-microsoft-teams-admin-center"></a>Utilisation du centre d’administration Microsoft Teams

Pour attribuer une stratégie à un utilisateur :

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, et accédez aux **Utilisateurs**, puis cliquez sur l’utilisateur.
2. Sélectionnez l’utilisateur en cliquant à gauche du nom de celui-ci, puis cliquez sur **Modifier les paramètres**.
3. Sélectionnez la stratégie que vous voulez attribuer, puis cliquez sur **appliquer**.

Vous pouvez également effectuer les opérations suivantes :

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à la page de stratégie.
2. Sélectionnez la stratégie que vous voulez affecter en cliquant à gauche du nom de la stratégie.
3. Sélectionnez **Gérer les utilisateurs**.
4. Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
5. Lorsque vous avez terminé d’ajouter des utilisateurs, sélectionnez **appliquer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Chaque type de stratégie dispose de son propre ensemble d’applets de service pour sa gestion. Utilisez l' ```Grant-``` applet de cmdlet d’un type de stratégie donné pour affecter la stratégie. Par exemple, utilisez l' ```Grant-CsTeamsMeetingPolicy``` applet de cmdlet pour attribuer une stratégie de réunion teams à des utilisateurs. Ces applets de service sont inclus dans le module PowerShell de Skype entreprise Online et sont décrits dans la référence de l’applet de connexion [Skype entreprise](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).

 Téléchargez et installez le [module PowerShell de Skype entreprise Online](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (si vous ne l’avez pas déjà fait), puis exécutez la commande suivante pour vous connecter à Skype entreprise Online et commencer une session.

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

Dans cet exemple, nous affectons une stratégie de réunion teams nommée Stratégie de réunion étudiant à un utilisateur nommé reda.

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

Pour en savoir plus, voir [gestion des stratégies via PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).

## <a name="assign-a-policy-package"></a>Assigner un package de stratégie

Un package de stratégie dans teams est un ensemble de stratégies et de paramètres de stratégie prédéfinis que vous pouvez affecter aux utilisateurs qui ont des rôles similaires ou similaires au sein de votre organisation. Chaque package de stratégie est conçu à l’aide d’un rôle d’utilisateur et comprend des stratégies et des paramètres de stratégie prédéfinis qui prennent en charge les activités typiques pour ce rôle. Voici quelques exemples de packages de stratégie : le package éducation (enseignant) et le module Healthcare (Medical Worker).

Lorsque vous attribuez un package de stratégie aux utilisateurs, les stratégies du package sont créées et vous pouvez personnaliser les paramètres de chaque stratégie du package pour répondre aux besoins des utilisateurs.

Pour en savoir plus sur les packages de stratégie, y compris des instructions détaillées sur la manière de les affecter et de les gérer, voir [gérer les packages de stratégie dans teams](manage-policy-packages.md).

## <a name="assign-a-policy-to-a-batch-of-users"></a>Attribuer une stratégie à un lot d’utilisateurs

### <a name="using-the-microsoft-teams-admin-center"></a>Utilisation du centre d’administration Microsoft Teams

Pour attribuer une stratégie aux utilisateurs en bloc :

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, sélectionnez **utilisateurs**.
2. Recherchez les utilisateurs auxquels vous voulez affecter la stratégie ou filtrez l’affichage pour afficher les utilisateurs souhaités.
3. Dans la colonne **&#x2713;** (coche), sélectionnez les utilisateurs. Pour sélectionner tous les utilisateurs, cliquez sur &#x2713; (coche) en haut du tableau.
4. Cliquez sur **Modifier les paramètres**, apportez les modifications souhaitées, puis cliquez sur **Appliquer**.

Pour afficher l’état de votre affectation de stratégie, dans la bannière qui s’affiche en haut de la page **utilisateurs** après avoir cliqué sur **appliquer** pour valider votre affectation de stratégie, cliquez sur **Journal d’activité**. Ou, dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez au **tableau de bord**, puis sous **Journal d’activité**, cliquez sur Afficher les **Détails**. Le journal d’activité affiche les affectations de stratégie aux lots de plus de 20 utilisateurs par le biais du centre d’administration Microsoft teams depuis les 30 derniers jours. Pour en savoir plus, voir [afficher les affectations de stratégie dans le journal d’activité](activity-log.md).

### <a name="using-powershell"></a>Utiliser PowerShell

> [!NOTE]
> Pour l’instant, l’affectation de stratégie de lot à l’aide de PowerShell n’est pas disponible pour tous les types de stratégie équipes. Pour obtenir la liste des types de stratégie pris en charge, voir [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) .
 
Avec une affectation de stratégie de lot, vous pouvez attribuer une stratégie à un grand nombre d’utilisateurs à la fois sans avoir à utiliser de script. Utilisez l' ```New-CsBatchPolicyAssignmentOperation``` applet de commande pour signaler un lot d’utilisateurs et la stratégie que vous voulez affecter. Les affectations sont traitées en tant qu’opérations en arrière-plan et chaque lot est généré. Vous pouvez ensuite utiliser l' ```Get-CsBatchPolicyAssignmentOperation``` applet de commande pour effectuer le suivi de l’avancement et de l’état des devoirs d’un lot.

Vous pouvez spécifier des utilisateurs en fonction de leur ID d’objet ou de leur adresse SIP (Session Initiation Protocol). Notez que le nom d’utilisateur principal (UPN) ou l’adresse de messagerie de l’utilisateur a souvent la même valeur que le nom d’utilisateur principal (UPN) ou l’adresse de messagerie, mais cela n’est pas obligatoire. Si un utilisateur est spécifié à l’aide de son nom d’utilisateur principal ou de son adresse de messagerie, mais qu’il a une valeur différente de son adresse SIP, l’affectation de stratégie échouera pour l’utilisateur. Si un lot inclut des utilisateurs en double, les doublons seront supprimés du lot avant traitement et le statut ne sera fourni qu’aux utilisateurs uniques figurant dans le lot. 

Un lot peut contenir jusqu’à 5 000 utilisateurs. Pour obtenir de meilleurs résultats, n’envoyez pas plus de quelques lots à la fois. Autorisez le traitement des lots avant de soumettre d’autres lots.

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installer le module Microsoft teams PowerShell et s’y connecter

Exécutez la commande suivante pour installer le [module Microsoft teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams). Vérifiez que vous avez installé la version 1.0.5 ou une version ultérieure.

```powershell
Install-Module -Name MicrosoftTeams
```

Exécutez la commande suivante pour vous connecter à teams et démarrer une session.

```powershell
Connect-MicrosoftTeams
```

Lorsque vous y êtes invité, connectez-vous à l’aide de vos informations d’identification d’administrateur.

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a>Installez et connectez-vous à Azure AD PowerShell pour le module Graph (facultatif)

Vous pouvez également [Télécharger et installer le module Azure ad PowerShell pour Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (le cas échéant) et vous connecter à Azure AD pour récupérer la liste des utilisateurs de votre organisation.

Exécutez la commande suivante pour vous connecter à Azure AD.

```powershell
Connect-AzureAD
```

Lorsque vous y êtes invité, connectez-vous à l’aide des informations d’identification d’administrateur que vous avez utilisées pour vous connecter à Teams.

#### <a name="assign-a-policy-to-a-batch-of-users"></a>Attribuer une stratégie à un lot d’utilisateurs

Dans cet exemple, nous utilisons l' ```New-CsBatchPolicyAssignmentOperation``` applet de commande pour assigner une stratégie d’installation d’application nommée Stratégie de configuration des applications humaines à un lot d’utilisateurs répertoriés dans le fichier Users_ids. Text.

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

Dans cet exemple, nous allons nous connecter à Azure AD pour récupérer une collection d’utilisateurs, puis affecter une stratégie de messagerie nommée nouvelle stratégie de messagerie à un lot d’utilisateurs spécifiés à l’aide de leur adresse SIP.

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

Pour en savoir plus, voir [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).

#### <a name="get-the-status-of-a-batch-assignment"></a>Obtenir l’état d’une affectation par lot

Exécutez la commande suivante pour obtenir l’état d’une affectation de lot, où OperationId est l’ID d’opération renvoyé par l' ```New-CsBatchPolicyAssignmentOperation``` applet de commande pour un lot donné.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Si la sortie indique qu’une erreur s’est produite, exécutez la commande suivante pour obtenir plus d’informations sur les erreurs qui se trouvent dans la ```UserState``` propriété.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Pour en savoir plus, consultez la rubrique [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).

## <a name="assign-a-policy-to-a-group"></a>Assigner une stratégie à un groupe

Attribution de stratégie aux groupes vous permet d’affecter une stratégie à un groupe d’utilisateurs, tel qu’un groupe de sécurité ou une unité d’organisation. L’affectation de stratégie est propagée aux membres du groupe conformément aux règles de priorité. Les membres étant ajoutés ou supprimés d’un groupe, leurs affectations de stratégie héritées sont mises à jour en conséquence.

Une affectation de stratégie à des groupes est recommandée pour des groupes d’utilisateurs 50 000, mais elle fonctionne également avec des groupes de plus grande taille.

Lorsque vous affectez la stratégie, celle-ci est immédiatement affectée au groupe. Toutefois, Notez que la propagation de l’affectation de stratégie aux membres du groupe est effectuée en tant qu’opération en arrière-plan et peut prendre un certain temps selon la taille du groupe. Il en va de même lorsque la stratégie n’est pas attribuée à un groupe, ou lorsque les membres sont ajoutés à un groupe ou supprimés.

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a>Ce que vous devez savoir sur l’attribution de stratégies aux groupes

Avant de commencer, il est important de comprendre les règles de précédence et le classement des affectations de groupe.

#### <a name="precedence-rules"></a>Règles de précédence

Pour un type de stratégie donné, la stratégie effective d’un utilisateur est déterminée conformément aux éléments suivants :

- Une stratégie attribuée directement à un utilisateur est prioritaire sur une autre stratégie du même type affectée à un groupe. En d’autres termes, si un utilisateur reçoit directement une stratégie d’un type donné, il n’hérite pas d’une stratégie du même type d’un groupe. En d’autres termes, si un utilisateur possède une stratégie d’un type donné qui lui a été directement affecté, vous devez supprimer cette stratégie de l’utilisateur pour pouvoir hériter d’une stratégie du même type d’un groupe.
- Si un utilisateur ne dispose pas directement d’une stratégie et est membre de deux groupes ou plus, et qu’il dispose d’une stratégie du même type qui lui est affecté, il hérite de la stratégie du groupe affecté dont le classement est le plus élevé.
- Si un utilisateur n’est pas membre de groupes auxquels une stratégie est affectée, la stratégie globale par défaut de l’Organisation pour ce type de stratégie s’applique à l’utilisateur.

La stratégie effective d’un utilisateur est mise à jour en fonction de ces règles lorsqu’un utilisateur est ajouté ou supprimé d’un groupe auquel est affectée une stratégie, qu’une stratégie n’est pas attribuée à partir d’un groupe ou qu’une stratégie attribuée directement à l’utilisateur est supprimée.

#### <a name="group-assignment-ranking"></a>Classement des affectations de groupe
 
Lorsque vous affectez une stratégie à un groupe, vous spécifiez le classement de l’affectation de groupe. Il est utilisé pour identifier la stratégie qu’un utilisateur doit hériter en tant que stratégie effective si l’utilisateur est membre de deux groupes ou plus et qu’une stratégie du même type est affectée à chaque groupe.

Le classement des affectations de groupe est relatif par rapport à d’autres affectations de groupe du même type. Par exemple, si vous attribuez une stratégie d’appel à deux groupes, définissez le classement d’une affectation sur 1 et l’autre sur 2, avec 1 en tant que classement le plus élevé. Le classement des affectations de groupe indique l’appartenance au groupe qui est la plus importante ou la plus pertinente par rapport à d’autres appartenances aux groupes en ce qui concerne l’héritage.
 
Imaginons, par exemple, que vous avez deux groupes, que vous stockez des employés et des responsables du magasin. Les deux groupes se voient attribuer une stratégie d’appel d’équipes, et les employés de la stratégie d’appel et de la stratégie d’appel des responsables de la boutique sont respectivement. Dans le cas d’un responsable du Windows Store qui se trouve dans les deux groupes, son rôle en tant que responsable est supérieur à celui d’un employé, de sorte que la stratégie d’appel attribuée au groupe responsables du magasin doit présenter un niveau de classement supérieur.

|Groupe |Nom de la stratégie d’appel teams  |Classement|
|---------|---------|---|
|Responsables du Windows Store   |Stratégie d’appel des directeurs du Windows Store         |1|
|Magasin employés    |Politique d’appel des employés du Store      |2|

Si vous ne spécifiez pas de classement, l’affectation de la stratégie est affectée du plus petit classement.

### <a name="using-the-microsoft-teams-admin-center"></a>Utilisation du centre d’administration Microsoft Teams

**Cette fonctionnalité n’a pas encore été publiée. Il a été annoncé et est bientôt disponible.**

> [!NOTE]
> Pour l’instant, l’affectation de stratégie à des groupes à l’aide du centre d’administration Microsoft teams n’est disponible que pour la stratégie d’appel d’équipe, la stratégie de réunion équipes et la stratégie de messagerie Teams. Pour les autres types de stratégies, utilisez PowerShell.

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à la page type de stratégie. Par exemple, accédez à **Meetings**  >  **stratégies de réunion**réunions.
2. Sélectionnez l’onglet **affectation de stratégie de groupe** .
3. Sélectionnez **Ajouter un groupe**, puis, dans le volet **affecter une stratégie à un groupe** , procédez comme suit :
    1. Recherchez et ajoutez le groupe auquel vous voulez affecter la stratégie.
    2. Définissez le classement de l’affectation de groupe.
    3. Sélectionnez la stratégie que vous voulez attribuer. 
    4. Sélectionnez **appliquer**.

Pour supprimer une affectation de stratégie de groupe, dans l’onglet **affectation de stratégie de groupe** de la page de stratégie, sélectionnez l’affectation de groupe, puis sélectionnez **supprimer**.

Pour modifier le classement d’une affectation de groupe, vous devez d’abord supprimer l’affectation de stratégie de groupe. Ensuite, suivez les étapes ci-dessus pour affecter la stratégie à un groupe.

### <a name="using-powershell"></a>Utiliser PowerShell

**Pour le moment, cette fonctionnalité est uniquement disponible dans la version préliminaire privée. Les applets de fonction de cette fonctionnalité se trouvent dans le module pre-version PowerShell Teams.**

> [!NOTE]
> Pour l’instant, l’affectation de stratégie à des groupes à l’aide de PowerShell n’est pas disponible pour tous les types de stratégie d’équipe. Pour obtenir la liste des types de stratégie pris en charge, voir [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) .

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installer le module Microsoft teams PowerShell et s’y connecter

Les applets de contrôle se trouvent dans la version préliminaire du module PowerShell Teams. Suivez ces étapes pour commencer par désinstaller la version disponible en général du module PowerShell Teams (s’il est installé), puis installez la dernière version préliminaire du module à partir de la Galerie de tests PowerShell.

Si ce n’est déjà fait, exécutez la commande suivante pour inscrire la Galerie de tests PowerShell comme source fiable.

```powershell
Register-PSRepository -SourceLocation https://www.poshtestgallery.com/api/v2 -Name PsTestGallery -InstallationPolicy Trusted
```

Si vous avez installé la version disponible en général du module PowerShell Teams, exécutez la commande suivante pour la désinstaller.

```powershell
Uninstall-Module MicrosoftTeams -AllVersions
```

Exécutez la commande suivante pour installer le module Microsoft teams PowerShell le plus récent à partir de la Galerie de tests PowerShell.

```powershell
Install-Module MicrosoftTeams -Repository PSTestGallery
```

Exécutez la commande suivante pour vous connecter à teams et démarrer une session.

```powershell
Connect-MicrosoftTeams
```

Lorsque vous y êtes invité, connectez-vous à l’aide de vos informations d’identification d’administrateur.

#### <a name="assign-a-policy-to-a-group"></a>Assigner une stratégie à un groupe

Vous pouvez utiliser l' ```New-CsGroupPolicyAssignment``` applet de cmdlet pour attribuer une stratégie à un groupe. Vous pouvez spécifier un groupe à l’aide d’un ID d’objet, d’une adresse SIP ou d’une adresse de messagerie.

Dans cet exemple, nous utilisons l' ```New-CsGroupPolicyAssignment``` applet de cmdlet pour assigner une stratégie de réunion équipes nommée Stratégie de réunion des responsables de revente à un groupe dont le classement de devoirs est 1.

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

Pour en savoir plus, voir [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).

#### <a name="get-policy-assignments-for-a-group"></a>Obtenir des affectations de stratégie pour un groupe

Utilisez l' ```Get-CsGroupPolicyAssignment``` applet de cmdlet pour obtenir toutes les stratégies attribuées à un groupe. Notez que les groupes sont toujours répertoriés par leur ID de groupe même si l’adresse ou l’adresse de messagerie SIP a été utilisée pour affecter la stratégie.

Dans cet exemple, nous récupérons toutes les stratégies affectées à un groupe spécifique.

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

Dans cet exemple, nous renvoyons tous les groupes auxquels une stratégie de réunion équipes est affectée.

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

Pour en savoir plus, consultez la rubrique [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).

#### <a name="remove-a-policy-from-a-group"></a>Supprimer une stratégie d’un groupe

Utilisez l' ```Remove-CsGroupPolicyAssignment``` applet de cmdlet pour supprimer une stratégie de groupe. Lorsque vous supprimez une stratégie d’un groupe, les priorités des autres stratégies du même type attribuées à ce groupe et dont le classement est inférieur sont mises à jour. Par exemple, si vous supprimez une stratégie de classement de 2, les stratégies dont le classement est 3 et 4 sont mis à jour pour refléter leur nouveau classement. Les deux tables suivantes montrent cet exemple.

Vous trouverez ci-dessous une liste des affectations et des priorités pour une stratégie de réunion Teams.

|Nom du groupe  |Nom de la stratégie  |Classement|
|---------|---------|---------|
|Ventes    |Politique de vente       | 1        |
|Région ouest     |Politique de la région ouest         |2         |
|Division    |Politique de division         |3         |
|Complémentaire   |Politique subsidiaire        |4         |

Si nous supprimons la politique de la région ouest du groupe région ouest, les affectations et les priorités de la stratégie sont mises à jour comme suit.

|Nom du groupe  |Nom de la stratégie  |Classement|
|---------|---------|---------|
|Ventes    |Politique de vente       | 1        |
|Division    |Politique de division         |2         |
|Complémentaire   |Politique subsidiaire        |3        |

Dans cet exemple, nous supprimons la stratégie de réunion teams d’un groupe.

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

Pour en savoir plus, consultez la rubrique [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).

#### <a name="change-a-policy-assignment-for-a-group"></a>Modifier une affectation de stratégie pour un groupe

Après avoir affecté une stratégie à un groupe, vous pouvez utiliser l' ```Set-CsGroupPolicyAssignment``` applet de cmdlet pour modifier l’affectation de stratégie de ce groupe comme suit :

- Changer le classement
- Modifier la stratégie d’un type de stratégie donné
- Modification de la stratégie d’un type de stratégie donné et du classement

Dans cet exemple, nous affectons à la stratégie de parc d’appels de groupe une stratégie nommée SupportCallPark et le classement de l’affectation à 3.

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

Pour en savoir plus, consultez la rubrique [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).

#### <a name="change-the-effective-policy-for-a-user"></a>Modification de la stratégie d’effectivité d’un utilisateur

Voici un exemple illustrant la modification de la stratégie d’effectivité d’un utilisateur qui a directement affecté une stratégie.

Tout d’abord, nous utilisons l’applet de connexion ```Get-CsUserPolicyAssignment``` conjointement avec le ```PolicySource``` paramètre pour obtenir des informations sur les stratégies de diffusion de réunion associées à l’utilisateur. Pour en savoir plus, consultez la rubrique [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

La sortie montre que l’utilisateur a été directement affecté à une stratégie de diffusion de réunion teams nommée événements de l’employé, qui est prioritaire sur la stratégie nommée événements dynamiques du fournisseur qui est affectée à un groupe auquel l’utilisateur appartient.

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

À présent, nous supprimons la stratégie d’événements des employés de l’utilisateur. Cela signifie que l’utilisateur ne dispose plus d’une stratégie de diffusion de réunion teams et qu’il hérite de la stratégie d’événements en direct du fournisseur qui est affectée au groupe auquel l’utilisateur appartient. 

Utilisez l’applet de commande suivante dans le module PowerShell Skype entreprise pour effectuer cette opération.

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

Pour ce faire, vous pouvez utiliser l’applet de commande suivante dans le module PowerShell teams pour procéder à la mise à niveau en utilisant une affectation de stratégie de lot dans laquelle $users est une liste d’utilisateurs que vous spécifiez.

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a>Affectation d’un package de stratégie à un lot d’utilisateurs

Avec une affectation de package de stratégie de lot, vous pouvez attribuer un package de stratégie à un grand nombre d’utilisateurs à la fois sans avoir à utiliser de script. Utilisez l' ```New-CsBatchPolicyPackageAssignmentOperation``` applet de commande pour transmettre un lot d’utilisateurs et le package de stratégie que vous voulez affecter. Les affectations sont traitées en tant qu’opérations en arrière-plan et chaque lot est généré. Vous pouvez ensuite utiliser l' ```Get-CsBatchPolicyAssignmentOperation``` applet de commande pour effectuer le suivi de l’avancement et de l’état des devoirs d’un lot.

Vous pouvez spécifier des utilisateurs en fonction de leur ID d’objet ou de leur adresse SIP (Session Initiation Protocol). Notez que le nom d’utilisateur principal (UPN) ou l’adresse de messagerie de l’utilisateur a souvent la même valeur que le nom d’utilisateur principal (UPN) ou l’adresse de messagerie, mais cela n’est pas obligatoire. Si un utilisateur est spécifié à l’aide de son nom d’utilisateur principal ou de son adresse de messagerie, mais qu’il a une valeur différente de son adresse SIP, l’affectation de stratégie échouera pour l’utilisateur. Si un lot inclut des utilisateurs en double, les doublons seront supprimés du lot avant traitement et le statut ne sera fourni qu’aux utilisateurs uniques figurant dans le lot. 

Un lot peut contenir jusqu’à 5 000 utilisateurs. Pour obtenir de meilleurs résultats, n’envoyez pas plus de quelques lots à la fois. Autorisez le traitement des lots avant de soumettre d’autres lots.

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installer le module Microsoft teams PowerShell et s’y connecter

Exécutez la commande suivante pour installer le [module Microsoft teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (si vous ne l’avez pas déjà fait). Vérifiez que vous avez installé la version 1.0.5 ou une version ultérieure.

```powershell
Install-Module -Name MicrosoftTeams
```

Exécutez la commande suivante pour vous connecter à teams et démarrer une session.

```powershell
Connect-MicrosoftTeams
```

Lorsque vous y êtes invité, connectez-vous à l’aide de vos informations d’identification d’administrateur.

### <a name="assign-a-policy-package-to-a-batch-of-users"></a>Affectation d’un package de stratégie à un lot d’utilisateurs

Dans cet exemple, nous utilisons l' ```New-CsBatchPolicyPackageAssignmentOperation``` applet de commande pour affecter le package de stratégie de Education_PrimaryStudent à un lot d’utilisateurs.

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

Pour en savoir plus, voir [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).

### <a name="get-the-status-of-a-batch-assignment"></a>Obtenir l’état d’une affectation par lot

Exécutez la commande suivante pour obtenir l’état d’une affectation de lot, où OperationId est l’ID d’opération renvoyé par l' ```New-CsBatchPolicyAssignmentOperation``` applet de commande pour un lot donné.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Si la sortie indique qu’une erreur s’est produite, exécutez la commande suivante pour obtenir plus d’informations sur les erreurs qui se trouvent dans la ```UserState``` propriété.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Pour en savoir plus, consultez la rubrique [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation). 

## <a name="related-topics"></a>Sujets associés

[Aperçu de Teams PowerShell](teams-powershell-overview.md)
