---
title: Attribution de stratégies à de grands ensembles d’utilisateurs dans votre établissement scolaire
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: saragava,karsmith
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
description: Découvrez comment utiliser une affectation de stratégie de lot pour attribuer des stratégies aux utilisateurs de votre établissement d’enseignement en bloc pour les usages de l’établissement scolaire
f1keywords: ''
ms.openlocfilehash: 7e297b6a4b99162fb50564d4f552a06f0dc41a10
ms.sourcegitcommit: 4d376449a75928282373598647f2b82127909c4f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/26/2020
ms.locfileid: "42978516"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a>Attribution de stratégies à de grands ensembles d’utilisateurs dans votre établissement scolaire

Avez-vous besoin d’offrir aux étudiants et aux enseignants l’accès à différentes fonctionnalités dans Microsoft teams ? Vous pouvez rapidement identifier les utilisateurs de votre organisation par type de licence, puis leur attribuer la politique appropriée. Ce didacticiel vous explique comment utiliser une [affectation de stratégie de batch](assign-policies.md#assign-a-policy-to-a-batch-of-users) pour assigner une stratégie de réunion aux utilisateurs en bloc.

Rappelez-vous que dans Teams, les utilisateurs obtiennent automatiquement la stratégie globale par défaut de l’organisation d’un type de stratégie d’équipe, sauf si vous créez et attribuez une stratégie personnalisée. Dans la mesure où la population étudiant est souvent le plus grand nombre d’utilisateurs et qu’ils reçoivent souvent les paramètres les plus restrictifs, nous vous recommandons de procéder comme suit :

- Modification et application de la stratégie globale par défaut de l’Organisation pour restreindre les capacités des étudiants. 
- Créez une stratégie personnalisée qui accepte les principales fonctionnalités, telles que la conversation privée et la planification de réunions, et attribuez-la à vos employés et enseignants.

Gardez à l’esprit que la politique globale s’applique à tous les utilisateurs de votre établissement scolaire tant que vous n’avez pas créé de stratégie personnalisée et que vous l’avez affectée à votre personnel et aux enseignants.

Dans ce didacticiel, les étudiants recevront la stratégie de réunion globale et utiliserons PowerShell pour attribuer une stratégie de réunion personnalisée nommée EducatorMeetingPolicy au personnel et aux enseignants en bloc. Nous partons du principe que vous avez modifié la politique globale afin d’adapter les paramètres de la réunion aux étudiants et créé une stratégie personnalisée qui définit l’interface de réunion pour les membres du personnel et les enseignants.

![Capture d’écran de la page stratégies de réunion dans le centre d’administration teams](media/edu-batch-policy-assignment.png)

Suivez ces étapes pour attribuer une stratégie de réunion personnalisée aux membres du personnel et aux enseignants en bloc.

## <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a>Se connecter à Azure AD PowerShell pour le module Graph et au module PowerShell teams

Avant d’effectuer les étapes décrites dans cet article, vous devez installer et vous connecter à Azure AD PowerShell pour le module Graph (afin d’identifier les utilisateurs selon leurs licences affectées) et le module Microsoft teams PowerShell (pour affecter les stratégies à ces utilisateurs).

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a>Installer et se connecter à Azure AD PowerShell pour le module Graph

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

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installer le module Microsoft teams PowerShell et s’y connecter

Exécutez la commande suivante pour installer le [module Microsoft teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams). Vérifiez que vous avez installé la version 1.0.5 ou une version ultérieure.

```powershell
Install-Module -Name MicrosoftTeams
```

Exécutez la commande suivante pour vous connecter à teams et démarrer une session.

```powershell
Connect-MicrosoftTeams
```
Lorsque vous y êtes invité, connectez-vous à l’aide des informations d’identification d’administrateur que vous avez utilisées pour vous connecter à Azure AD.

## <a name="identify-your-users"></a>Identifier vos utilisateurs

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

## <a name="assign-a-policy-in-bulk"></a>Assigner une stratégie en bloc

À présent, nous affectons les stratégies appropriées aux utilisateurs en bloc. Le nombre maximal d’utilisateurs pour lesquels vous pouvez attribuer ou mettre à jour des stratégies est 20 000 à la fois. Par exemple, si vous avez plus de 20 000 employé et enseignants, vous devrez ennoter plusieurs lots.

> [!IMPORTANT]
> Pour l’instant, nous vous recommandons d’affecter des stratégies par lot d’utilisateurs 5 000 à la fois. Au cours de ces périodes de demande croissante, il est possible que les temps de traitement soient retardés. Pour réduire l’impact de ces délais de traitement, nous vous suggérons d’adresser de plus petites tailles de lot à des utilisateurs 5 000 et de n’en faire qu’après la fin de la précédente. Vous pouvez également obtenir de l’aide pour soumettre des lots en dehors de vos heures de travail normales.

Exécutez la commande suivante pour affecter la stratégie de réunion nommée EducatorMeetingPolicy à votre personnel et aux enseignants.

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> Pour attribuer un type de stratégie différent en bloc (par exemple, TeamsMessagingPolicy), vous ```PolicyType``` devez utiliser la stratégie que vous affectez et ```PolicyName``` le nom de la stratégie.

## <a name="get-the-status-of-a-bulk-assignment"></a>Obtenir l’état d’une affectation en bloc

Chaque affectation en bloc renvoie un ID d’opération, que vous pouvez utiliser pour effectuer le suivi de l’avancement des affectations de stratégie ou identifier les échecs qui peuvent se produire. Par exemple, exécutez la commande suivante :

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

Pour afficher l’état de l’affectation de chaque utilisateur dans l’opération de traitement par lot, exécutez la commande suivante. Les détails de chaque utilisateur sont dans ```UserState``` la propriété.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

## <a name="assign-a-policy-in-bulk-if-you-have-more-than-20000-users"></a>Affecter une stratégie en bloc si vous avez plus de 20 000 utilisateurs

Tout d’abord, exécutez la commande suivante pour voir combien de personnes et de enseignants vous avez :

```powershell
$faculty.count
```

Au lieu de fournir la liste complète des identifiants utilisateur, exécutez la commande suivante pour spécifier le premier 20 000, puis la 20 000 suivante, et ainsi de suite.

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

Vous pouvez modifier la plage d’ID utilisateur jusqu’à ce que vous accédiez à la liste complète des utilisateurs. Par exemple, entrez ```$faculty[0..19999``` pour le premier lot, utilisez ```$faculty[20000..39999``` pour le second lot, entrez ```$faculty[40000..59999``` pour le troisième lot, et ainsi de suite.

## <a name="get-the-policies-assigned-to-a-user"></a>Obtention des stratégies affectées à un utilisateur

Exécutez la commande suivante pour afficher toutes les stratégies affectées à un utilisateur spécifique. L’exemple suivant vous montre comment obtenir les stratégies affectées à hannah@contoso.com.

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a>FAQ

**Je souhaite veiller à ce que tous les utilisateurs qui sont des étudiants, des enseignants et des enseignants obtiennent automatiquement des stratégies affectées. Comment faire ?**

L’équipe de produit équipes effectue son travail pour prendre en charge l’attribution de stratégies aux groupes de sécurité. À ce stade, vous serez en mesure de créer des groupes pour vos étudiants et enseignants, puis les politiques appropriées à ces groupes. Notez que les affectations utilisateur explicites (telles que les stratégies que vous avez affectées à l’aide de ce didacticiel) remplaceront les stratégies héritées d’un groupe. Lorsque cette fonctionnalité est prise en charge, nous vous fournirons des instructions supplémentaires sur la façon d’utiliser une affectation de stratégie aux groupes et de mettre à jour vos utilisateurs pour s’assurer qu’ils reçoivent les stratégies de groupe héritées.

**Je ne connais pas PowerShell pour Teams. Où trouver d’autres informations ?**

Consultez [vue d’ensemble de PowerShell teams](teams-powershell-overview.md).

## <a name="related-topics"></a>Sujets associés

- [Attribution de stratégies à vos utilisateurs](assign-policies.md)
- [Nouveau-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)
