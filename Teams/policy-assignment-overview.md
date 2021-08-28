---
title: Attribuer des stratégies dans Teams
author: KarliStites
ms.author: kastites
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
description: Découvrez les différentes façons d’attribuer des stratégies et packages de stratégies à des utilisateurs et groupes dans Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: fb85ae05925a44db75ed63ada899c6fca92cbceb
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58621986"
---
# <a name="assign-policies-in-teams--getting-started"></a>Attribuer des stratégies dans Teams mise en place

En tant qu’administrateur, vous utilisez des stratégies pour contrôler Teams fonctionnalités disponibles pour les utilisateurs de votre organisation. Par exemple, il existe des stratégies d’appel, des stratégies de réunion et des stratégies de messagerie, entre autres.

Les organisations ont différents types d’utilisateurs ayant des besoins uniques. Les stratégies personnalisées que vous créez et attribuez vous personnalisationnt aux différents ensembles d’utilisateurs en fonction de ces besoins.

Pour gérer facilement les stratégies dans votre organisation, Teams plusieurs façons d’affecter des stratégies aux utilisateurs. Affectez une stratégie directement aux utilisateurs, individuellement ou à l’échelle via une affectation de lot, ou à un groupe dont les utilisateurs sont membres. Vous pouvez également utiliser des packages de stratégies pour affecter une collection prédéfinfine de stratégies aux utilisateurs de votre organisation ayant des rôles similaires. L’option que vous choisissez dépend du nombre de stratégies que vous gérez et du nombre d’utilisateurs à qui vous affectez des stratégies. Les stratégies globales (à l’échelle de l’organisation par défaut) s’appliquent au plus grand nombre d’utilisateurs de votre organisation. Il vous s agit uniquement d’affecter des stratégies aux utilisateurs qui ont besoin de stratégies spécialisées.

Cet article décrit les différentes manières d’affecter des stratégies aux utilisateurs et les scénarios recommandés pour l’utilisation des stratégies.

Pour plus d’informations sur **l’attribution de** stratégies aux utilisateurs et groupes, voir Attribution de stratégies à [des utilisateurs et groupes.](assign-policies-users-and-groups.md) Pour plus d’informations sur **l’attribution de packages de stratégie,** voir [Attribuer des packages de stratégie.](assign-policy-packages.md)

## <a name="which-policy-takes-precedence"></a>Quelle stratégie prend le pas ?

Un utilisateur a une stratégie efficace pour chaque type de stratégie. Il est possible, voire probable, qu’une stratégie soit attribuée directement à un utilisateur et qu’il soit également membre d’un ou plusieurs groupes à qui une stratégie du même type a été attribuée. Dans ces types de scénarios, quelle stratégie prend le pas ? La stratégie efficace d’un utilisateur est déterminée selon les règles de priorité, comme suit.

Si un utilisateur est affecté directement à une stratégie (individuellement ou par le biais d’une affectation de lot), cette stratégie est prioritaire. Dans l’exemple visuel suivant, la stratégie efficace de l’utilisateur est la stratégie de réunion carrée qu’il est directement affecté à l’utilisateur.

![Diagramme montrant la priorité d’une stratégie assignée directement](media/assign-policies-example-directly-assigned.png)

Si un utilisateur n’est pas directement affecté à une stratégie d’un type donné, la stratégie assignée à un groupe dont l’utilisateur est membre est prioritaire. Si un utilisateur est membre de plusieurs groupes, la stratégie dont le classement d’affectation de groupe est le plus élevé[pour](assign-policies-users-and-groups.md#group-assignment-ranking)le type de stratégie donné est prioritaire.

Dans cet exemple visuel, la stratégie efficace de l’utilisateur est la stratégie Exec Teams et HD, qui présente le classement d’affectation le plus élevé par rapport aux autres groupes dont l’utilisateur est membre et pour lesquels une stratégie du même type de stratégie est également attribuée.  

![Diagramme montrant comment une stratégie héritée d’un groupe est prioritaire](media/assign-policies-example-group.png)

Si un utilisateur n’est pas directement affecté à une stratégie ou n’est membre d’aucun groupe à qui une stratégie est attribuée, l’utilisateur reçoit la stratégie globale (à l’échelle de l’organisation par défaut) pour ce type de stratégie. Voici un exemple visuel.

![Diagramme montrant la manière dont une stratégie globale prend le pas](media/assign-policies-example-global.png)

Pour en savoir plus, voir ([Règles de priorité).](assign-policies-users-and-groups.md#precedence-rules)

## <a name="ways-to-assign-policies"></a>Méthodes d’affectation des stratégies

Voici une vue d’ensemble des manières d’affecter des stratégies aux utilisateurs et des scénarios recommandés pour chacun d’eux. Sélectionnez les liens pour en savoir plus.

Avant d’affecter des stratégies à des utilisateurs ou groupes individuels, commencez par définir les stratégies globales (à l’échelle de l’organisation [par défaut)](#set-the-global-policies) de sorte qu’elles s’appliquent au plus grand nombre d’utilisateurs de votre organisation.  Une fois les stratégies globales définies, vous devrez seulement affecter des stratégies aux utilisateurs qui ont besoin de stratégies spécialisées.

|Pour ce faire,  |Si...  | Utilisation...
|---------|---------|----|
|[Attribuer une stratégie à des utilisateurs individuels](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users)   | Vous débutez dans Teams vous débutez, ou vous n’avez besoin d’affecter qu’une ou plusieurs stratégies à un petit nombre d’utilisateurs. |The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module
|[Affecter une stratégie à un groupe](assign-policies-users-and-groups.md#assign-a-policy-to-a-group) |Attribuer des stratégies en fonction de l’appartenance d’un utilisateur à un groupe. Par exemple, affectez une stratégie à tous les utilisateurs d’un groupe de sécurité ou d’une liste de distribution.| The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module|
|[Affecter une stratégie à un lot d’utilisateurs](assign-policies-users-and-groups.md#assign-a-policy-to-a-batch-of-users)   | Attribuer des stratégies à de grands ensembles d’utilisateurs. Par exemple, affectez une stratégie à des centaines ou des milliers d’utilisateurs à la fois dans votre organisation. |The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module|
|[Attribuer un package de stratégies aux utilisateurs](assign-policy-packages.md#assign-a-policy-package-to-users)  |Attribuez plusieurs stratégies à des ensembles spécifiques d’utilisateurs de votre organisation qui ont des rôles identiques ou similaires. Par exemple, affectez le package de stratégie Éducation (Enseignant) aux enseignants de votre établissement scolaire pour leur donner un accès total aux conversations, appels et réunions. Affectez le package de stratégie Éducation (étudiant secondaire) aux étudiants secondaires afin de limiter certaines fonctionnalités telles que les appels privés.  |The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module|
|[Affecter un package de stratégie à un groupe](assign-policy-packages.md#assign-a-policy-package-to-a-group) (en prévisualisation privée)   |Attribuer plusieurs stratégies à un groupe d’utilisateurs de votre organisation qui ont des rôles identiques ou similaires. Par exemple, affectez un package de stratégie à tous les utilisateurs d’un groupe de sécurité ou d’une liste de distribution. |Le Microsoft Teams d’administration powershell (bientôt disponible) ou les cmdlets PowerShell dans Teams module PowerShell|
|[Affecter un package de stratégie à un lot d’utilisateurs](assign-policy-packages.md#assign-a-policy-package-to-a-batch-of-users)|Affectez plusieurs stratégies à un lot d’utilisateurs de votre organisation qui ont des rôles identiques ou similaires. Par exemple, affectez le package de stratégie Éducation (Enseignant) à tous les enseignants de votre établissement en utilisant un devoir de lot pour leur donner un accès total aux conversations, appels et réunions. Affectez le package de stratégie Éducation (étudiant secondaire) à un lot d’étudiants secondaires afin de limiter certaines fonctionnalités telles que les appels privés.|Cmdlets PowerShell dans le module Teams PowerShell|

## <a name="set-the-global-policies"></a>Définir les stratégies globales

Pour définir les stratégies globales (à l’échelle de l’organisation par défaut) pour chaque type de stratégie, suivez ces étapes.

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le navigation gauche du Microsoft Teams d’administration, allez sur la page stratégie pour le type de stratégie que vous voulez mettre à jour. Par exemple, vous **Teams** Teams, les stratégies réunions, les stratégies de messagerie  >  ou les   >  **stratégies**    >  **d’appel vocal.**
2. Sélectionnez **la stratégie globale (à l’échelle de l’organisation par défaut)** pour afficher les paramètres actuels.
3. Mettez à jour la stratégie si nécessaire, puis sélectionnez **Appliquer.**

![Mettre à jour la stratégie globale dans Teams centre d’administration](media/assign-globalpolicy.png)

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

## <a name="view-your-policy-assignments-in-the-activity-log"></a>Afficher vos affectations de stratégie dans le journal d’activité

Lorsque vous attribuez des stratégies à des utilisateurs dans le Microsoft Teams d’administration, vous pouvez afficher l’état de ces affectations de stratégie dans le journal d’activité. Le journal d’activité affiche les affectations de stratégie à des lots de plus de 20 utilisateurs via le Centre Microsoft Teams d’administration à partir des 30 derniers jours. Gardez à l’esprit que le journal d’activité n’affiche pas les affectations de packages de stratégie, les affectations de stratégie à des lots de moins de 20 utilisateurs via le Centre d’administration Microsoft Teams ou les affectations de stratégies via PowerShell.

![Capture d’écran de la page du journal d’activité](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>Afficher vos activités d’affectation de stratégie dans le journal d’activité

Pour afficher vos affectations de stratégie dans le journal d’activité :

1. Dans le navigation gauche du centre d Microsoft Teams d’administration, allez dans Tableau de **bord,** puis sous Journal d’activité, sélectionnez Afficher les **détails.**
2. Vous pouvez afficher toutes les affectations de stratégie ou filtrer la liste par état pour afficher uniquement les affectations Non **commencées,** En **cours** ou **Terminées.** Vous verrez les informations suivantes sur chaque devoir :
    - **Nom**: nom de l’affectation de stratégie. Cliquez sur le lien pour afficher plus de détails. Cela inclut le nombre d’utilisateurs à qui la stratégie a été attribuée, ainsi que le nombre d’affectations terminées, en cours et non démarrées. Vous verrez également la liste des utilisateurs dans le lot, ainsi que l’état et le résultat pour chaque utilisateur. Voici un exemple :

        ![Capture d’écran du](media/activity-log-policy-assignment-detail.png)

    - **Soumis**: Date et heure de soumettre l’affectation de stratégie.
    - **Heure d’achèvement**: date et heure d’achèvement de l’affectation de stratégie.
    - **Impact sur**: nombre d’utilisateurs du lot.
    - **État global**: état de l’affectation de stratégie.

> [!NOTE]
> Vous pouvez également ouvrir le journal d’activité à partir de la page **Utilisateurs.** Après avoir **cliqué sur Appliquer** pour envoyer une affectation de stratégie en bloc, une bannière s’affiche en haut de la page. Cliquez sur le **lien Journal d’activité** dans la bannière.

## <a name="related-topics"></a>Rubriques connexes

- [Attribuer des stratégies aux utilisateurs et aux groupes](assign-policies-users-and-groups.md)
- [Attribuer des packages de stratégies à des utilisateurs et groupes](assign-policy-packages.md)
- [Gérer les Teams des stratégies](manage-teams-with-policies.md)
- [Aperçu de Teams PowerShell](teams-powershell-overview.md)