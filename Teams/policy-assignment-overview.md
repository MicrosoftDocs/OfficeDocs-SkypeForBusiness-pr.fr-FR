---
title: Attribuer des stratégies dans Teams
author: mkbond007
ms.author: mabond
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
description: Découvrez les différentes façons d’attribuer des stratégies et des packages de stratégie aux utilisateurs et aux groupes dans Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: c618653199a41bc358f4b2a14bdf1c0e8923d9b7
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646413"
---
# <a name="assign-policies-in-teams--getting-started"></a>Affecter des stratégies dans Teams – Prise en main

En tant qu’administrateur, vous utilisez des stratégies pour contrôler les fonctionnalités Teams disponibles pour les utilisateurs de votre organisation. Par exemple, il existe des stratégies d’appel, des stratégies de réunion et des stratégies de messagerie, pour n’en nommer que quelques-unes.

Les organisations ont différents types d’utilisateurs ayant des besoins uniques. Les stratégies personnalisées que vous créez et affectez vous permettent d’adapter les paramètres de stratégie à différents ensembles d’utilisateurs en fonction de ces besoins.

Pour gérer facilement les stratégies au sein de votre organisation, Teams offre plusieurs façons d’attribuer des stratégies aux utilisateurs. Affectez une stratégie directement aux utilisateurs, individuellement ou à grande échelle via une affectation par lots, ou à un groupe dont les utilisateurs sont membres. Vous pouvez également utiliser des packages de stratégie pour affecter une collection prédéfinies de stratégies aux utilisateurs de votre organisation qui ont des rôles similaires. L’option que vous choisissez dépend du nombre de stratégies que vous gérez et du nombre d’utilisateurs auxquels vous attribuez des stratégies. Les stratégies globales (par défaut à l’échelle de l’organisation) s’appliquent au plus grand nombre d’utilisateurs de votre organisation. Vous devez uniquement affecter des stratégies aux utilisateurs qui nécessitent des stratégies spécialisées.

Cet article décrit les différentes façons d’affecter des stratégies aux utilisateurs et les scénarios recommandés pour savoir quand utiliser quoi.

Pour plus d’informations sur **l’affectation de stratégies aux utilisateurs et aux groupes**, consultez [l’attribution de stratégies aux utilisateurs et aux groupes](assign-policies-users-and-groups.md). Pour plus d’informations sur **l’affectation de packages de stratégie**, consultez [Affecter des packages de stratégie](assign-policy-packages.md).

## <a name="which-policy-takes-precedence"></a>Quelle stratégie est prioritaire ?

Un utilisateur a une stratégie efficace pour chaque type de stratégie. Il est possible, voire probable, qu’un utilisateur soit directement affecté à une stratégie et qu’il soit également membre d’un ou de plusieurs groupes auxquels une stratégie du même type est affectée. Dans ces types de scénarios, quelle stratégie est prioritaire ? La stratégie effective d’un utilisateur est déterminée en fonction des règles de priorité, comme suit.

Si une stratégie est directement attribuée à un utilisateur (individuellement ou par le biais d’une affectation par lots), cette stratégie est prioritaire. Dans l’exemple visuel suivant, la stratégie effective de l’utilisateur est la stratégie de réunion Lincoln Square, qui est directement affectée à l’utilisateur.

![Diagramme montrant comment une stratégie affectée directement est prioritaire.](media/assign-policies-example-directly-assigned.png)

Si une stratégie d’un type donné n’est pas attribuée directement à un utilisateur, la stratégie affectée à un groupe dont l’utilisateur est membre est prioritaire. Si un utilisateur est membre de plusieurs groupes, la stratégie la plus élevée (classement des [affectations de groupe](assign-policies-users-and-groups.md#group-assignment-ranking)) pour le type de stratégie donné est prioritaire.

Dans cet exemple visuel, la stratégie effective de l’utilisateur est la stratégie Exec Teams et HD, qui a le classement d’affectation le plus élevé par rapport aux autres groupes dont l’utilisateur est membre et qui sont également affectés à une stratégie du même type de stratégie.  

![Diagramme montrant comment une stratégie héritée d’un groupe est prioritaire.](media/assign-policies-example-group.png)

Si un utilisateur n’est pas directement affecté à une stratégie ou n’est membre d’aucun groupe auquel une stratégie est affectée, l’utilisateur obtient la stratégie globale (par défaut à l’échelle de l’organisation) pour ce type de stratégie. Voici un exemple visuel.

![Diagramme montrant comment une stratégie globale est prioritaire.](media/assign-policies-example-global.png)

Pour plus d’informations, consultez ([Règles de précédence](assign-policies-users-and-groups.md#precedence-rules)).

## <a name="ways-to-assign-policies"></a>Méthodes d’affectation de stratégies

Voici une vue d’ensemble des façons d’affecter des stratégies aux utilisateurs et des scénarios recommandés pour chacun d’eux. Sélectionnez les liens pour en savoir plus.

Avant d’affecter des stratégies à des utilisateurs ou groupes individuels, commencez par [définir les stratégies globales (par défaut à l’échelle](#set-the-global-policies) de l’organisation) afin qu’elles s’appliquent au plus grand nombre d’utilisateurs de votre organisation.  Une fois les stratégies globales définies, vous devez uniquement affecter des stratégies aux utilisateurs qui nécessitent des stratégies spécialisées.

|Procédez comme suit  |Si...  | Utilisant...
|---------|---------|----|
|[Affecter une stratégie à des utilisateurs individuels](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users)   | Vous débutez avec Teams et commencez à peine, ou vous n’avez besoin d’affecter qu’une ou deux stratégies à un petit nombre d’utilisateurs. |Le centre d’administration Microsoft Teams ou les applets de commande PowerShell dans le module Teams PowerShell
|[Affecter une stratégie à un groupe](assign-policies-users-and-groups.md#assign-a-policy-to-a-group) |Attribuez des stratégies en fonction de l’appartenance à un groupe d’utilisateurs. Par exemple, affectez une stratégie à tous les utilisateurs d’un groupe de sécurité ou d’une liste de distribution.| Le centre d’administration Microsoft Teams ou les applets de commande PowerShell dans le module Teams PowerShell|
|[Affecter une stratégie à un lot d’utilisateurs](assign-policies-users-and-groups.md#assign-a-policy-to-a-batch-of-users)   | Affectez des stratégies à de grands ensembles d’utilisateurs. Par exemple, affectez une stratégie à des centaines ou des milliers d’utilisateurs de votre organisation à la fois. |Le centre d’administration Microsoft Teams ou les applets de commande PowerShell dans le module Teams PowerShell|
|[Affecter un package de stratégie aux utilisateurs](assign-policy-packages.md#assign-a-policy-package-to-users)  |Affectez plusieurs stratégies à des ensembles spécifiques d’utilisateurs de votre organisation qui ont les mêmes rôles ou des rôles similaires. Par exemple, affectez le package de stratégie Éducation (Enseignant) aux enseignants de votre école pour leur donner un accès complet aux conversations, aux appels et aux réunions. Attribuez le package de stratégie Éducation (étudiant secondaire) aux étudiants du secondaire pour limiter certaines fonctionnalités telles que l’appel privé.  |Le centre d’administration Microsoft Teams ou les applets de commande PowerShell dans le module Teams PowerShell|
|[Attribuer le package stratégie à un groupe](assign-policy-packages.md#assign-a-policy-package-to-a-group)  |Attribuez plusieurs stratégies à un groupe d’utilisateurs de votre organisation qui ont les mêmes rôles ou des rôles similaires. Par exemple, affectez un package de stratégie à tous les utilisateurs d’un groupe de sécurité ou d’une liste de distribution. |Le centre d’administration Microsoft Teams (bientôt disponible) ou les applets de commande PowerShell dans le module PowerShell Teams|
|[Affecter un package de stratégie à un lot d’utilisateurs](assign-policy-packages.md#assign-a-policy-package-to-a-batch-of-users)|Attribuez plusieurs stratégies à un lot d’utilisateurs de votre organisation qui ont les mêmes rôles ou des rôles similaires. Par exemple, attribuez le package de stratégie Éducation (Enseignant) à tous les enseignants de votre école à l’aide d’une affectation par lots pour leur donner un accès complet aux conversations, aux appels et aux réunions. Affectez le package de stratégie Éducation (étudiant secondaire) à un lot d’étudiants du secondaire pour limiter certaines fonctionnalités telles que l’appel privé.|Applets de commande PowerShell dans le module PowerShell Teams|

## <a name="set-the-global-policies"></a>Définir les stratégies globales

Suivez ces étapes pour définir les stratégies globales (par défaut à l’échelle de l’organisation) pour chaque type de stratégie.

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, accédez à la page de stratégie du type de stratégie à mettre à jour. Par exemple, **Teams** >  **Teams des stratégies**, des stratégies **MeetingsMeetings** > , **des stratégies de messagerie** ou des **stratégies VoiceCalling** > .
2. Sélectionnez la stratégie **globale (par défaut à l’échelle de l’organisation)** pour afficher les paramètres actuels.
3. Mettez à jour la stratégie en fonction des besoins, puis **sélectionnez Appliquer**.

![Mettez à jour la stratégie globale dans Teams centre d’administration.](media/assign-globalpolicy.png)

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

Ensuite, mettez à jour la stratégie globale en fonction des besoins.  Vous devez uniquement spécifier des valeurs pour les paramètres que vous souhaitez modifier.

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="view-your-policy-assignments-in-the-activity-log"></a>Afficher vos affectations de stratégie dans le journal d’activité

Lorsque vous attribuez des stratégies aux utilisateurs du centre d’administration Microsoft Teams, vous pouvez afficher l’état de ces affectations de stratégie dans le [journal d’activité](https://admin.teams.microsoft.com/activitylog). Le journal d’activité affiche les informations de chargement des enregistrements réseau, les opérations de stratégie de groupe de Teams centre d’administration et PowerShell, et les opérations de stratégie par lot (pour plus de 20 utilisateurs) à partir du centre d’administration Teams, au cours des 30 derniers jours.

![Capture d’écran de la page du journal d’activité.](media/Activity_Log.png)

Pour afficher vos opérations de stratégie dans le journal d’activité :

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, accédez au **tableau de bord**, puis sous **Journal d’activité**, sélectionnez **Afficher les détails**.
2. Vous verrez les informations suivantes sur chaque opération de stratégie :
    - **Activité** : nom de l’opération de stratégie. Par exemple : **affectation de stratégie de groupe**
    - **Nom du groupe** : nom du groupe sur lequel l’opération de stratégie a été effectuée.
    - **Type de stratégie** : type de stratégie.
    - **Nom de** la stratégie : nom de l’opération de stratégie. Pour les affectations de stratégie de lot, vous pouvez sélectionner le lien pour afficher plus de détails. Cela inclut le nombre d’utilisateurs auxquels la stratégie a été affectée et le nombre d’affectations terminées, en cours et non démarrées. Vous verrez également la liste des utilisateurs dans le lot, ainsi que l’état et le résultat de chaque utilisateur.
    - **Soumis par** : nom de l’utilisateur qui a envoyé l’opération de stratégie.
    - **Soumis le** : Date et heure de l’envoi de l’opération de stratégie.
    - **Terminé le** : date et heure de fin de l’opération de stratégie.
    - **Impact :** nombre d’utilisateurs dans le lot ou le groupe.
    - **État global** : état de l’opération de stratégie. Une stratégie peut avoir l’un des états suivants :
        - **Non démarré** : l’opération de stratégie a été soumise par l’administrateur.
        - **En cours** : l’opération de stratégie a démarré le traitement.
        - **Déploiement aux utilisateurs** : le système a commencé à appliquer la mise à jour de stratégie aux utilisateurs.
        - **Terminé** : la mise à jour de stratégie a été appliquée à tous les utilisateurs.
        - **Terminé avec des erreurs « x »** : l’opération de stratégie est terminée, mais il y a des erreurs.

> [!NOTE]
> Vous pouvez également accéder au journal d’activité à partir de la page **Utilisateurs** . Une fois que vous avez sélectionné **Appliquer** pour envoyer une affectation de stratégie en bloc, une bannière s’affiche en haut de la page. Sélectionnez le lien **du journal d’activité** dans la bannière.

## <a name="related-topics"></a>Voir aussi

- [Affecter des stratégies à des utilisateurs et des groupes](assign-policies-users-and-groups.md)
- [Affecter des packages de stratégie à des utilisateurs et des groupes](assign-policy-packages.md)
- [Gérer Teams avec des stratégies](manage-teams-with-policies.md)
- [Aperçu de Teams PowerShell](teams-powershell-overview.md)
