---
title: Attribution de stratégies à de grands ensembles d’utilisateurs dans votre établissement scolaire
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: karsmith, angch, cebulnes
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment attribuer des stratégies à des ensembles de personnes importants dans votre établissement scolaire en fonction de l’appartenance à un groupe ou directement par le biais d’une affectation par lot dans le cadre de l’établissement scolaire à distance (télé-établissement).
f1keywords: ''
ms.openlocfilehash: 0b4fd804b51fef9537d30230aed400bb0cb7e0aa
ms.sourcegitcommit: dc3e8ae454c42981f037f4de2e48005428b6078e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/31/2020
ms.locfileid: "46534100"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a>Attribution de stratégies à de grands ensembles d’utilisateurs dans votre établissement scolaire

> [!NOTE]
> Pour plus d’histoire sur l’attribution de stratégies dans Microsoft Teams, voir [attribuer des stratégies à vos utilisateurs dans teams](assign-policies.md).

## <a name="overview"></a>Vue d’ensemble

Avez-vous besoin d’offrir aux étudiants et aux enseignants l’accès à différentes fonctionnalités dans Microsoft teams ? Vous pouvez rapidement identifier les utilisateurs de votre organisation par type de licence, puis leur attribuer la politique appropriée. Ce didacticiel vous explique comment affecter une stratégie de réunion à de nombreux utilisateurs de votre établissement scolaire. Vous pouvez attribuer des stratégies à l’aide du centre d’administration Microsoft teams et de PowerShell et nous allons vous présenter les deux manières.

Vous pouvez assigner une stratégie de réunion à un groupe de sécurité que les utilisateurs sont membres de ou directement aux utilisateurs lors de l’évolution via une affectation de stratégie de lot. Vous apprendrez comment :

- **Utiliser une [affectation de stratégie aux groupes](#assign-a-policy-to-a-group) pour attribuer une stratégie de réunion à un groupe de sécurité (recommandé)**. Cette méthode vous permet d’affecter une stratégie basée sur l’appartenance au groupe. Vous pouvez affecter une stratégie à un groupe de sécurité ou une liste de distribution. Les membres étant ajoutés ou supprimés du groupe, leurs affectations de stratégie héritées sont mises à jour en conséquence. Nous vous recommandons d’utiliser cette méthode, car elle réduit le temps de gestion des stratégies pour les nouveaux utilisateurs ou lorsque les rôles des utilisateurs changent. Cette méthode est idéale pour les groupes d’utilisateurs 50 000, mais elle fonctionne également avec des groupes de plus grande taille.

- **Utiliser une [affectation de stratégie de batch](assign-policies.md#assign-a-policy-to-a-batch-of-users) pour attribuer une stratégie de réunion directement aux utilisateurs en bloc**. Vous pouvez assigner une stratégie pour un maximum de 5 000 utilisateurs à la fois. Si vous disposez de plus de 5 000 utilisateurs, vous pouvez en saisir plusieurs. Avec cette méthode, lorsque vous avez de nouveaux utilisateurs, vous devez réexécuter l’affectation de lot pour affecter la stratégie à ces nouveaux utilisateurs.

Rappelez-vous que dans Teams, les utilisateurs obtiennent automatiquement la stratégie globale par défaut de l’organisation d’un type de stratégie d’équipe, sauf si vous créez et attribuez une stratégie personnalisée. Dans la mesure où la population étudiant est souvent le plus grand nombre d’utilisateurs et qu’ils reçoivent souvent les paramètres les plus restrictifs, nous vous recommandons de procéder comme suit :

- Créez une stratégie personnalisée qui accepte les principales fonctionnalités, telles que la conversation privée et la planification de réunions, et attribuez-la à vos employés et enseignants.
- Affectez la stratégie personnalisée à votre personnel et aux enseignants.
- Modification et application de la stratégie globale par défaut de l’Organisation pour restreindre les capacités des étudiants.

Gardez à l’esprit que la politique globale s’applique à tous les utilisateurs de votre établissement scolaire tant que vous n’avez pas créé de stratégie personnalisée et que vous l’avez affectée à votre personnel et aux enseignants.

Dans ce didacticiel, les étudiants recevront la politique de réunion globale et nous affecterons une stratégie de réunion personnalisée nommée EducatorMeetingPolicy au personnel et aux enseignants. Nous partons du principe que vous avez modifié la politique globale afin d’adapter les paramètres de la réunion aux étudiants et [créé une stratégie personnalisée](policy-packages-edu.md) qui définit l’interface de réunion pour les membres du personnel et les enseignants.

![Capture d’écran de la page stratégies de réunion dans le centre d’administration teams](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a>Assigner une stratégie à un groupe

Suivez ces étapes pour créer un groupe de sécurité pour votre personnel et vos enseignants, puis attribuez une stratégie de réunion personnalisée nommée EducatorMeetingPolicy à ce groupe de sécurité.

### <a name="before-you-get-started"></a>Avant de commencer

> [!IMPORTANT]
> Lorsque vous affectez une stratégie à un groupe, l’affectation de stratégie est propagée aux membres du groupe en fonction des règles de priorité. Par exemple, si un utilisateur dispose d’une stratégie directement affectée (ou par le biais d’une affectation par lot), cette stratégie est prioritaire sur une stratégie héritée d’un groupe. Par ailleurs, si un utilisateur dispose d’une stratégie de réunion qui lui a été directement affectée, vous devez supprimer celle-ci de l’utilisateur pour pouvoir hériter d’une stratégie de réunion d’un groupe de sécurité.

Avant de commencer, il est important de comprendre les [règles de précédence](assign-policies.md#precedence-rules) et le [classement des affectations de groupe](assign-policies.md#group-assignment-ranking). **Vérifiez que vous avez bien lu et compris les concepts décrits dans [ce que vous devez savoir sur l’attribution de stratégies à des groupes](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**.

Pour pouvoir hériter d’une stratégie de réunion à partir d’un groupe de sécurité, vous devez effectuer toutes les étapes suivantes.

1. [Créer des groupes de sécurité](#create-security-groups).
2. [Assigner une stratégie à un groupe de sécurité](#assign-a-policy-to-a-security-group).
3. [Supprimez une stratégie attribuée directement aux utilisateurs](#remove-a-policy-that-was-directly-assigned-to-users).

### <a name="create-security-groups"></a>Créer des groupes de sécurité

Tout d’abord, créez un groupe de sécurité pour votre personnel et vos enseignants.

Avec [School Data Sync](https://docs.microsoft.com/SchoolDataSync/) , vous pouvez [facilement créer des enseignants et des étudiants](https://docs.microsoft.com/SchoolDataSync/edu-security-groups) au sein de votre établissement scolaire. Nous vous recommandons d’utiliser SDS pour créer des groupes de sécurité dont vous avez besoin pour gérer les stratégies de votre établissement scolaire.

Si vous ne parvenez pas à déployer le SD au sein de votre environnement, utilisez [ce script PowerShell](scripts/powershell-script-security-groups-edu.md) pour créer deux groupes de sécurité, l’un pour tous les membres du personnel et les enseignants qui disposent d’une licence pour les enseignants attribués et une autre pour tous les étudiants qui disposent d’une licence étudiant. Vous devez exécuter le script en routine pour que les groupes soient actualisés et à jour.

### <a name="assign-a-policy-to-a-security-group"></a>Assigner une stratégie à un groupe de sécurité

#### <a name="using-the-microsoft-teams-admin-center"></a>Utilisation du centre d’administration Microsoft Teams

> [!NOTE]
> Pour l’instant, l’attribution de stratégies aux groupes à l’aide du centre d’administration Microsoft teams n’est disponible que pour les stratégies d’appel d’équipe, la stratégie de parc d’appels d’équipe, la stratégie d’équipe, la stratégie des événements en direct Teams, la stratégie de réunion équipes et la stratégie de messagerie Pour les autres types de stratégies, utilisez PowerShell.

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, **accédez à**  >  **stratégies de réunion**.
2. Sélectionnez l’onglet **affectation de stratégie de groupe** .
3. Sélectionnez **Ajouter un groupe**, puis, dans le volet **affecter une stratégie à un groupe** , procédez comme suit :

    ![Capture d’écran du volet modifier les paramètres affichant la stratégie de réunion](media/batch-group-policy-assignment-edu-group.png)
    1. Dans la zone **Sélectionner un groupe** , recherchez et ajoutez le groupe de sécurité contenant votre personnel et vos enseignants.
    2. Dans la zone **Sélectionner un rang** , entrez **1**.
    3. Dans la zone **Sélectionner une stratégie** , sélectionnez **EducatorMeetingPolicy**.
    4. Sélectionnez **appliquer**.

Pour supprimer une affectation de stratégie de groupe, dans l’onglet **affectation de stratégie de groupe** de la page de stratégie, sélectionnez l’affectation de groupe, puis sélectionnez **supprimer**.

Pour modifier le classement d’une affectation de groupe, vous devez d’abord supprimer l’affectation de stratégie de groupe. Ensuite, suivez les étapes ci-dessus pour affecter la stratégie à un groupe.

#### <a name="using-powershell"></a>Utiliser PowerShell

> [!NOTE]
> Pour l’instant, l’affectation de stratégie à des groupes à l’aide de PowerShell n’est pas disponible pour tous les types de stratégie d’équipe. Pour obtenir la liste des types de stratégie pris en charge, voir [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) .

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installer le module Microsoft teams PowerShell et s’y connecter

Exécutez la commande suivante pour installer le [module teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (si ce n’est pas déjà fait). Vérifiez que vous avez installé la version 1.0.5 ou une version ultérieure.

```powershell
Install-Module -Name MicrosoftTeams
```

Exécutez la commande suivante pour vous connecter à teams et démarrer une session.

```powershell
Connect-MicrosoftTeams
```

Lorsque vous y êtes invité, connectez-vous à l’aide de vos informations d’identification d’administrateur.

##### <a name="assign-a-policy-to-a-group"></a>Assigner une stratégie à un groupe

Exécutez la commande suivante pour affecter la stratégie de réunion nommée EducatorMeetingPolicy au groupe de sécurité qui contient votre personnel et vos enseignants et définissez le classement des affectations sur 1. Vous pouvez spécifier un groupe de sécurité à l’aide d’un ID d’objet, d’une adresse SIP (Session Initiation Protocol) ou d’une adresse de messagerie. Dans cet exemple, nous utilisons une adresse de messagerie (staff-faculty@contoso.com).

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a>Supprimer une stratégie attribuée directement aux utilisateurs

N’oubliez pas que si un utilisateur a été directement affecté à une stratégie (par le biais d’une affectation individuelle ou par lot), cette stratégie est prioritaire. Autrement dit, si un utilisateur dispose d’une stratégie de réunion qui lui a été directement affectée, vous devez supprimer cette stratégie de réunion de l’utilisateur pour pouvoir hériter d’une stratégie de réunion d’un groupe de sécurité.

Pour en savoir plus, voir [ce que vous devez savoir sur l’attribution de stratégies à des groupes](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups).

Suivez ces étapes pour supprimer la politique de réunion qui a été directement affectée à votre personnel et aux enseignants.

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installer le module Microsoft teams PowerShell et s’y connecter

Exécutez la commande suivante pour installer le [module teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (si ce n’est pas déjà fait). Vérifiez que vous avez installé la version 1.0.5 ou une version ultérieure.

```powershell
Install-Module -Name MicrosoftTeams
```

Exécutez la commande suivante pour vous connecter à teams et démarrer une session.

```powershell
Connect-MicrosoftTeams
```
Lorsque vous y êtes invité, connectez-vous à l’aide des informations d’identification d’administrateur que vous avez utilisées pour vous connecter à Azure AD.

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a>Annuler l’affectation d’une stratégie attribuée directement aux utilisateurs

Exécutez la commande suivante pour supprimer une stratégie de réunion des utilisateurs auxquels cette stratégie a été directement affectée. Vous pouvez spécifier des utilisateurs par adresse de courrier ou ID d’objet.

Dans cet exemple, la stratégie de réunion est supprimée des utilisateurs spécifiés par son adresse de courrier.

```powershell
$users_ids = @("reda@contoso.com", "nikica@contoso.com", "jamie@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

Dans cet exemple, la stratégie de réunion est supprimée de la liste des utilisateurs dans un fichier texte nommé user_ids.txt. 

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

##### <a name="get-policy-assignments-for-a-group"></a>Obtenir des affectations de stratégie pour un groupe

Exécutez la commande suivante pour afficher toutes les stratégies affectées à un groupe de sécurité spécifique. Notez que les groupes sont toujours répertoriés par leur ID de groupe même si l’adresse ou l’adresse de messagerie SIP a été utilisée pour affecter la stratégie.

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a>Obtention des stratégies affectées à un utilisateur

Exécutez la commande suivante pour afficher toutes les stratégies affectées à un utilisateur spécifique. L’exemple suivant vous montre comment obtenir les stratégies affectées à reda@contoso.com.

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>Attribuer une stratégie à un lot d’utilisateurs

Suivez ces étapes pour attribuer une stratégie de réunion personnalisée nommée EducatorMeetingPolicy directement à votre personnel et aux enseignants en bloc.

### <a name="using-powershell"></a>Utiliser PowerShell

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a>Se connecter à Azure AD PowerShell pour le module Graph et au module PowerShell teams

Avant d’effectuer les étapes décrites dans cet article, vous devez installer et vous connecter à Azure AD PowerShell pour le module Graph (afin d’identifier les utilisateurs selon leurs licences affectées) et le module Microsoft teams PowerShell (pour affecter les stratégies à ces utilisateurs).

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a>Installer et se connecter à Azure AD PowerShell pour le module Graph

Ouvrez une invite de commandes Windows PowerShell avec élévation de privilèges (exécutez Windows PowerShell en tant qu’administrateur), puis exécutez la commande suivante pour installer Azure Active Directory PowerShell pour le module Graph.

```powershell
Install-Module -Name AzureAD
```

Exécutez la commande suivante pour vous connecter à Azure AD.

```powershell
Connect-AzureAD
```

Lorsque vous y êtes invité, connectez-vous à l’aide de vos informations d’identification d’administrateur.

Pour en savoir plus, voir [se connecter à l’aide d’Azure Active Directory PowerShell pour le module Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installer le module Microsoft teams PowerShell et s’y connecter

Exécutez la commande suivante pour installer le [module teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (si ce n’est pas déjà fait). Vérifiez que vous avez installé la version 1.0.5 ou une version ultérieure.

```powershell
Install-Module -Name MicrosoftTeams
```

Exécutez la commande suivante pour vous connecter à teams et démarrer une session.

```powershell
Connect-MicrosoftTeams
```
Lorsque vous y êtes invité, connectez-vous à l’aide des informations d’identification d’administrateur que vous avez utilisées pour vous connecter à Azure AD.

#### <a name="identify-your-users"></a>Identifier vos utilisateurs

Tout d’abord, exécutez la commande suivante pour identifier votre personnel et vos enseignants par type de licence. Cette option vous indique les références (SKU) utilisées au sein de votre organisation. Vous pouvez ensuite identifier le personnel et les enseignants qui ont affecté une référence pour les enseignants.

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

Qui renvoie :

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

Dans cet exemple, la sortie indique que la licence Université SkuId est « e97c048c-37a4-45FB-ab50-922fbf07a370 ».

> [!NOTE]
> Pour afficher une liste des références SKU et des références SKU éducation, voir référence des références [SKU éducation](sku-reference-edu.md).

Ensuite, nous exécutons la commande suivante pour identifier les utilisateurs disposant de cette licence et les rassembler.

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a>Assigner une stratégie en bloc

À présent, nous affectons les stratégies appropriées aux utilisateurs en bloc. Le nombre maximal d’utilisateurs pour lesquels vous pouvez attribuer ou mettre à jour des stratégies est 5 000 à la fois. Par exemple, si vous avez plus de 5 000 employé et enseignants, vous devrez ennoter plusieurs lots.

Exécutez la commande suivante pour affecter une stratégie de réunion personnalisée nommée EducatorMeetingPolicy à votre personnel et aux enseignants.

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> Pour attribuer un type de stratégie différent en bloc (par exemple, TeamsMessagingPolicy), vous devez utiliser ```PolicyType``` la stratégie que vous affectez et ```PolicyName``` le nom de la stratégie.

#### <a name="get-the-status-of-a-bulk-assignment"></a>Obtenir l’état d’une affectation en bloc

Chaque affectation en bloc renvoie un ID d’opération, que vous pouvez utiliser pour effectuer le suivi de l’avancement des affectations de stratégie ou identifier les échecs qui peuvent se produire. Par exemple, exécutez la commande suivante :

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

Pour afficher l’état de l’affectation de chaque utilisateur dans l’opération de traitement par lot, exécutez la commande suivante. Les détails de chaque utilisateur sont dans la ```UserState``` propriété.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a>Affecter une stratégie en bloc si vous avez plus de 5 000 utilisateurs

Tout d’abord, exécutez la commande suivante pour voir combien de personnes et de enseignants vous avez :

```powershell
$faculty.count
```

Au lieu de fournir la liste complète des identifiants utilisateur, exécutez la commande suivante pour spécifier le premier 5 000, puis la 5 000 suivante, et ainsi de suite.

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

Vous pouvez modifier la plage d’ID utilisateur jusqu’à ce que vous accédiez à la liste complète des utilisateurs. Par exemple, entrez pour le ```$faculty[0..4999``` premier lot, utilisez ```$faculty[5000..9999``` pour le second lot, entrez ```$faculty[10000..14999``` pour le troisième lot, et ainsi de suite.

#### <a name="get-the-policies-assigned-to-a-user"></a>Obtention des stratégies affectées à un utilisateur

Exécutez la commande suivante pour afficher toutes les stratégies affectées à un utilisateur spécifique. L’exemple suivant vous montre comment obtenir les stratégies affectées à hannah@contoso.com.

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a>FAQ

**Je ne connais pas PowerShell pour Teams. Où trouver d’autres informations ?**

Pour obtenir une vue d’ensemble de l’utilisation de PowerShell pour gérer Teams, voir [vue d’ensemble de teams PowerShell](teams-powershell-overview.md). Pour plus d’informations sur les applets de vue utilisées dans cet article, voir :

- [Nouveau-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)
- [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment)
- [Nouveau-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a>Voir aussi

- [Attribution de stratégies à vos utilisateurs](assign-policies.md)
- [Stratégies d’équipe et packages de stratégie pour l’éducation](policy-packages-edu.md)
- [Gérer les stratégies de réunion dans teams](meeting-policies-in-teams.md)
