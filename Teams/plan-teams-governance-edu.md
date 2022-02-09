---
title: FAQ sur la gouvernance de Microsoft Éducation pour les administrateurs
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Réponses aux questions fréquemment posées par les administrateurs de groupes Microsoft Education qui utilisent Teams.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f2cae3ba57ca3e6a4c6596ba67ed257f167338ba
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62400048"
---
# <a name="microsoft-education-governance-faq-for-admins"></a>FAQ sur la gouvernance de Microsoft Éducation pour les administrateurs

> [!Tip]
> Regardez la session suivante pour en savoir plus sur la gestion dans Microsoft Teams : gouvernance, gestion et cycle de [vie dans Microsoft Teams](https://aka.ms/teams-governance)

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>Comment contrôler la création d’équipe ? Je suis préoccupé que les étudiants vont créer des équipes inappropriées.

Pour éviter les noms inappropriés ou trompeurs, ou simplement donner une structure plus complexe au nom des équipes, vous pouvez utiliser la stratégie de noms de groupes Microsoft 365 (actuellement en prévisualisation) :

-   **Stratégie de nommage Prefix-Suffix** Vous pouvez utiliser des préfixes ou des suffixes pour définir la convention d’appellation des équipes (groupes), par **exemple, GRP_US_My Group_Engineering**. Les préfixes et suffixes peuvent être des chaînes fixes ou des attributs d’utilisateur (par exemple, **[Service]**) qui sont ajoutés au nom en fonction de l’utilisateur qui crée l’équipe.
-   **Mots bloqués personnalisés** Vous pouvez télécharger un ensemble de mots que les utilisateurs d’une organisation spécifique ne peuvent pas utiliser dans les noms d’équipes qu’ils créent. Par exemple, vous pouvez empêcher le **PDG, les** salaires et les ressources **humaines** d’être utilisés dans les noms d’équipe pour les groupes qu’ils ne s’appliquent pas. 
-   **Classification** Vous pouvez créer des classifications que les utilisateurs de votre organisation peuvent définir lorsqu’ils créent Microsoft 365 groupe. 

> [!IMPORTANT]
> L’utilisation de la stratégie de noms de groupes Microsoft 365 nécessite des licences Azure Active Directory Premium P1 ou des licences Azure AD Basic EDU pour chaque utilisateur unique membre d’un ou plusieurs groupes Microsoft 365 personnel.

Pour obtenir des instructions détaillées, voir [Office de noms de groupes](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).

> [!Note]
> Si des équipes sont créées automatiquement à l’aide de l’entrée d’un autre système (par exemple, Synchronisation des données scolaires), vérifiez que les données d’entrée sont conformes à la stratégie de noms que vous avez configurée. Si ce n’est pas le cas, la création d’équipe échoue.

## <a name="can-i-see-who-created-a-team"></a>Puis-je voir qui a créé une équipe ?

Pour savoir qui a créé une équipe spécifique, consultez [le journal d’audit pour rechercher des événements dans Microsoft Teams](audit-log-events.md).

## <a name="can-i-control-who-can-create-teams"></a>Puis-je contrôler qui peut créer des équipes ?

En règle générale, nous vous recommandons de ne pas empêcher quiconque de créer des équipes. Si tout le monde peut créer des équipes, Teams est plus susceptible d’être largement adoptée. Les enseignants, les enseignants ou les étudiants peuvent utiliser Teams pour créer des groupes d’étude ou des groupes d’intérêt spéciaux. Cela vous permettra Teams’accepter à l’intérieur et à l’extérieur de la classe.

Dans notre expérience, la formation des utilisateurs garantit la responsabilité de Teams’utilisation. Dès que les utilisateurs comprennent que la création d’équipes n’est pas anonyme, ils comprennent les conséquences de leur création inerte et ont tendance à ne pas utiliser mal l’outil.

Si vous êtes sûr de vouloir contrôler qui peut créer des équipes, voir Gérer qui [peut créer Microsoft 365 groupes](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>Comment créer automatiquement une équipe pour chaque cours au début du semestre ou du trimestre ?

Au début de chaque semestre ou trimestre, vous avez besoin d’un certain nombre de nouvelles équipes. Il peut être logique d’utiliser une approche automatisée pour créer ces équipes automatiquement, les remplir avec les utilisateurs autorisés et définir les autorisations qui s’offrent à vous :

-   Synchronisation des données scolaires créer des groupes de Microsoft 365 pour Exchange Online et SharePoint Online, des équipes de classe pour Microsoft Teams et OneNote  Les blocs-notes pour la classe, les groupes scolaires pour Intune pour l’Éducation, la liste de listes et l’intégration de l’ingération unique (SSO) pour de nombreuses autres applications tierces. En savoir plus sur [la vue d’ensemble Synchronisation des données scolaires](/schooldatasync/overview-of-school-data-sync).
-   PowerShell vous permet de créer des équipes et des canaux, et de configurer automatiquement les paramètres. Voir [Microsoft Teams PowerShell pour](/powershell/module/teams/?view=teams-ps) plus d’informations.
-   Vous pouvez utiliser l’API Microsoft Graph (actuellement en version bêta) pour créer, configurer, cloner et archiver des équipes. Pour [plus d’informations, voir Utiliser Graph API Microsoft Microsoft Teams’aide](/graph/api/resources/teams-api-overview) de Microsoft.

> [!TIP]
> Synchronisation des données scolaires un groupe de Microsoft 365 pour chaque classe est synchronisé et autorise l’appartenance masquée au groupe de sorte que [seuls les enseignants](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) et étudiants au sein de la classe peuvent voir les membres de cette classe. Si vous utilisez un autre processus pour créer des groupes de classe, utilisez le paramètre HiddenGroupMembershipEnabled de l'New-UnifiedGroup pour répondre aux mêmes exigences de confidentialité.

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>Comment gérer les équipes à la fin du semestre ou du trimestre ?

Nous vous recommandons de réfléchir à la façon dont vous souhaitez gérer les données Teams au terme d’un semestre ou d’un trimestre scolaire : supprimez-les ou conservez-les disponibles pour les étudiants, même après avoir terminé le cours. Vous devez garder le calendrier scolaire à l’esprit afin que les stratégies que vous définissez ne entrent pas en conflit avec les jours fériés. Vous pouvez utiliser les outils suivants pour implémenter votre stratégie :

-   **Stratégie de rétention :** Utilisez cette ligne pour supprimer toutes les données d’un âge que vous spécifiez afin de vous assurer que les anciennes données sont supprimées des conversations (pour l’ensemble ou certains utilisateurs) et des canaux. Vous pouvez également configurer les Teams conserver le contenu afin qu’il ne puisse pas être supprimé. Pour plus d’informations, voir [Stratégies de rétention pour Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011).
-   **Politique d’expiration :** Configurez les équipes de manière à ce qu’ils expirent après un certain nombre de jours. Trente jours avant l’expiration, tous les propriétaires d’une équipe sont informés de la nécessite de leur renouvellement, faute de quoi ils sont supprimés (même si un administrateur peut récupérer les équipes supprimées pendant 30 jours supplémentaires). Ce paramètre est très utile pour s’assurer que les équipes inutilisées sont en coucher de soleil. Pour en savoir plus[, Microsoft 365 d’expiration du groupe](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733).

-   **Équipe d’archivage :** Ce paramètre place les équipes en mode lecture seule. Ils peuvent toujours être parcourus et recherchés, mais personne ne peut ajouter de nouvelles publications. [Archiver ou restaurer une équipe](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) décrit comment les propriétaires d’équipe peuvent archiver une équipe . Les propriétaires d’équipe peuvent également [utiliser Graph API (bêta)](/graph/api/resources/teams-api-overview) pour archiver ou restaurer une équipe.
 
> [!IMPORTANT]
> L’utilisation Microsoft 365 d’expiration des groupes nécessite Azure Active Directory Premium P1 licences uniques pour chaque utilisateur qui est membre d’un ou plusieurs Microsoft 365 groupes.

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>Existe-t-il des modèles d’équipe que les enseignants peuvent utiliser lors de la création d’une équipe ?

Oui. Les utilisateurs  peuvent sélectionner Créer une équipe à partir d’un modèle existant lors de la création d’une équipe, et les propriétaires de Teams peuvent également utiliser [l’API Graph (bêta)](/graph/api/resources/teams-api-overview) pour créer une équipe à partir des modèles disponibles.

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>Quelles tâches puis-je automatiser via PowerShell ou Graph ?

[L’API Microsoft Graph (bêta)](/graph/api/resources/teams-api-overview) peut faire les choses suivantes :

-   Créer une équipe.
-   Ajoutez des membres et des propriétaires.
-   Ajouter des canaux.
-   Ajoutez des applications.
-   Raccourcissez ces étapes en cloneant une équipe existante et obtenez également ses onglets.
-   Donnez à l’utilisateur un lien vers l’équipe que vous vient de créer.
-   Supprimez des membres, des propriétaires, des canaux et des applications lorsque vous n’en avez plus besoin.
-   Archivez l’équipe quand elle n’est plus active. 
-   Supprimez l’équipe.
-   Créer un fil de discussion de canal

[PowerShell peut](/powershell/module/teams/?view=teams-ps) faire les choses suivantes :

-   Créer une équipe.
-   Ajoutez des membres et des propriétaires.
-   Ajouter des canaux.
-   Supprimez des membres, des propriétaires et des canaux lorsque vous n’en avez plus besoin.
-   Supprimez l’équipe.

> [!TIP]
> Les Graph de l’API et de PowerShell ajoutent constamment des fonctionnalités. Veillez à vérifier souvent les [articles Microsoft Graph API (bêta)](/graph/api/resources/teams-api-overview) et [PowerShell](/powershell/module/teams/?view=teams-ps) pour les améliorations des fonctionnalités.  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>Puis-je contrôler les Teams fonctionnalités accessibles aux enseignants et aux étudiants ?

Oui. Vous pouvez utiliser des stratégies pour contrôler des fonctionnalités spécifiques de messagerie, de réunion, d’appel et d’événement en direct accessibles à vos utilisateurs. Vous pouvez utiliser les paramètres à l’échelle du client pour appliquer les mêmes paramètres à tous, ou appliquer des stratégies au niveau utilisateur si nécessaire. 

Pour plus d’informations sur Teams [stratégies, voir Gérer Microsoft Teams de votre organisation](enable-features-office-365.md).
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>Puis-je contrôler les parties externes avec qui mes enseignants et étudiants collaborent ?

Vous pouvez utiliser l’accès invité pour inviter des utilisateurs extérieurs à votre client, ce qui peut être utile pour la collaboration en matière de recherche ou les conférences invités :

-   Utilisez une liste d’utilisateurs pour autoriser ou bloquer des invités en fonction de leur domaine.
-   Activer ou désactiver l’accès invité pour des groupes Microsoft 365 équipes spécifiques afin de contrôler quelles équipes peuvent (et ne peuvent pas) inviter des invités.
-   Utilisez le journal d’audit pour voir quelles alertes ont été envoyées aux invités.

Pour plus d’informations, [voir Accès invité dans Microsoft 365 groupes.](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage)

## <a name="what-information-can-i-review-about-existing-teams"></a>Quelles informations puis-je passer en revue sur les équipes existantes ?

Vous pouvez consulter les journaux d’audit pour voir :

-   Qui invité en tant qu’invité pour quelle équipe.
-   Qui d’équipe.

Pour plus d’informations, voir [Rechercher des événements dans le journal d’audit Microsoft Teams](audit-log-events.md).

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>Teams évolue si rapidement. Comment rester à jour ?

Nous vous recommandons les ressources suivantes pour obtenir les dernières mises à jour sur Teams :

-   [Nouveautés de Microsoft Teams](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [Microsoft Teams blog](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)