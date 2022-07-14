---
title: FAQ sur la gouvernance de Microsoft Éducation pour les administrateurs
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Réponses aux questions fréquemment posées par les administrateurs de groupes Microsoft Éducation qui utilisent Teams.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fe9c0b19e5ba586ac8bfe430295de459c3d836d2
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66790179"
---
# <a name="microsoft-education-governance-faq-for-admins"></a>FAQ sur la gouvernance de Microsoft Éducation pour les administrateurs

> [!Tip]
> Regardez la session suivante pour en savoir plus sur la gestion dans Microsoft Teams : [Gouvernance, gestion et cycle de vie dans Microsoft Teams](https://aka.ms/teams-governance)

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>Comment faire la création d’une équipe de contrôle ? J’ai peur que les étudiants créent des équipes inappropriées.

Pour éviter les noms inappropriés ou trompeurs, ou simplement pour mieux structurer le nom des équipes, vous pouvez utiliser la stratégie d’affectation de noms Groupes Microsoft 365 (actuellement en préversion) :

-   **Stratégie d’affectation de noms de préfixe-suffixe** Vous pouvez utiliser des préfixes ou des suffixes pour définir la convention d’affectation de noms des équipes (groupes), par exemple, **GRP_US_My Group_Engineering**. Les préfixes et suffixes peuvent être des chaînes fixes ou des attributs utilisateur (tels que **[Department]**) qui sont ajoutés au nom en fonction de l’utilisateur qui crée l’équipe.
-   **Mots bloqués personnalisés** Vous pouvez charger un ensemble de mots que les utilisateurs d’une organisation spécifique ne peuvent pas utiliser dans les noms des équipes qu’ils créent. Par exemple, vous pouvez empêcher l’utilisation des termes **CEO**, **Payroll** et **HR** dans les noms d’équipe pour les groupes auxquels ils ne s’appliquent pas.
-   **Classification** Vous pouvez créer des classifications que les utilisateurs de votre organisation peuvent définir lorsqu’ils créent un groupe Microsoft 365. 

> [!IMPORTANT]
> L’utilisation de la stratégie d’affectation de noms Groupes Microsoft 365 nécessite des licences Azure Active Directory Premium P1 ou des licences Azure AD Basic EDU pour chaque utilisateur unique membre d’un ou de plusieurs groupes Microsoft 365.

Pour obtenir des instructions détaillées, consultez la stratégie [de nommage des groupes Office](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).

> [!Note]
> Si des équipes sont créées automatiquement à l’aide de l’entrée d’un autre système (par exemple, School Data Sync), vérifiez que les données d’entrée sont conformes à la stratégie de nommage que vous avez configurée ; Si ce n’est pas le cas, la création d’équipe échoue.

## <a name="can-i-see-who-created-a-team"></a>Puis-je voir qui a créé une équipe ?

Pour savoir qui a créé une équipe spécifique, consultez [rechercher des événements dans Microsoft Teams dans le journal d’audit](audit-log-events.md).

## <a name="can-i-control-who-can-create-teams"></a>Puis-je contrôler qui peut créer des équipes ?

En général, nous vous déconseillons d’empêcher quiconque de créer des équipes. Si tout le monde peut créer des équipes, Teams est plus susceptible d’être largement adopté. Les enseignants, les enseignants ou les étudiants peuvent utiliser Teams pour créer des groupes d’étude ou des groupes d’intérêt spéciaux. Cela aidera Teams à être accepté à l’intérieur et à l’extérieur de la classe.

Dans notre expérience, l’éducation des utilisateurs permet de garantir une utilisation responsable de Teams. Dès que les utilisateurs comprennent que la création d’équipes n’est pas anonyme, ils comprennent les implications de leur création négligemment et ont tendance à éviter de mal utiliser l’outil.

Si vous êtes sûr de vouloir contrôler qui peut créer des équipes, consultez [Gérer qui peut créer Groupes Microsoft 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>Comment faire créer automatiquement une équipe pour chaque cours au début du semestre ou du trimestre ?

Au début de chaque semestre ou trimestre, vous aurez besoin d’un certain nombre de nouvelles équipes. Il peut être judicieux d’adopter une approche automatisée pour créer automatiquement ces équipes, les remplir avec les bons utilisateurs et définir les autorisations appropriées :

-   School Data Sync peut créer des Groupes Microsoft 365 pour Exchange Online et SharePoint Online, des équipes de classe pour Microsoft Teams et des blocs-notes oneNote pour la classe, des groupes scolaires pour Intune pour l’éducation, ainsi que l’inscription et l’intégration de l’authentification unique (SSO) pour de nombreuses autres applications tierces. Pour en savoir plus, consultez [Vue d’ensemble de School Data Sync](/schooldatasync/overview-of-school-data-sync).
-   Avec PowerShell, vous pouvez créer des équipes et des canaux, et configurer automatiquement les paramètres. Pour plus d’informations, consultez [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) .
-   Vous pouvez utiliser microsoft API Graph (actuellement en version bêta) pour créer, configurer, cloner et archiver des équipes. Pour plus [d’informations, consultez Utiliser microsoft API Graph pour travailler avec Microsoft Teams](/graph/api/resources/teams-api-overview).

> [!TIP]
> School Data Sync crée un groupe Microsoft 365 pour chaque classe synchronisée et [active l’appartenance à un groupe masqué afin que seuls](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) les enseignants et les étudiants de la classe puissent voir les membres de cette classe. Si vous utilisez un autre processus pour créer des groupes de classes, utilisez le paramètre HiddenGroupMembershipEnabled de l’applet de commande New-UnifiedGroup pour répondre aux mêmes exigences de confidentialité.

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>Comment faire traiter avec les équipes à la fin du semestre ou du trimestre ?

Nous vous recommandons de commencer par réfléchir à la façon dont vous souhaitez gérer les données Teams lorsque le semestre ou le trimestre scolaire est terminé : s’il faut les supprimer ou les conserver à la disposition des étudiants, même après avoir terminé le cours. Vous devez garder le calendrier scolaire à l’esprit afin que toutes les stratégies que vous définissez ne soient pas en conflit avec les vacances. Vous pouvez utiliser les outils suivants pour implémenter votre stratégie :

-   **Stratégie de rétention :** Utilisez cette option pour supprimer toutes les données antérieures à l’âge que vous spécifiez pour vous assurer que les anciennes données sont supprimées des conversations (pour tous ou certains utilisateurs) et des canaux. Vous pouvez également configurer Teams pour conserver le contenu afin qu’il ne puisse pas être supprimé. Pour plus d’informations, consultez [Stratégies de rétention pour Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011).
-   **Stratégie d’expiration :** Configurez les équipes pour qu’ils expirent après un certain nombre de jours. Trente jours avant l’expiration, tous les propriétaires d’une équipe sont avertis que leur équipe doit être renouvelée, sinon elle sera supprimée (bien qu’un administrateur puisse récupérer les équipes supprimées pendant 30 jours supplémentaires). Ce paramètre est très utile pour s’assurer que les équipes inutilisées sont mises à l’extinction. Pour plus d’informations, consultez la stratégie [d’expiration du groupe Microsoft 365](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733).

-   **Équipe archive :** Ce paramètre place les équipes en mode lecture seule. Ils peuvent toujours être parcourus et recherchés, mais personne ne peut ajouter de nouveaux billets. [Archiver ou restaurer une équipe](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) décrit comment les propriétaires d’équipe peuvent archiver une équipe ; Les propriétaires d’équipe peuvent également utiliser la [API Graph (bêta)](/graph/api/resources/teams-api-overview) pour archiver ou restaurer une équipe.
 
> [!IMPORTANT]
> L’utilisation de la stratégie d’expiration Groupes Microsoft 365 nécessite Azure Active Directory Premium P1 licences pour chaque utilisateur unique membre d’un ou plusieurs groupes Microsoft 365.

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>Existe-t-il des modèles d’équipe que les membres de mon corps professoral doivent utiliser lors de la création d’une équipe ?

Oui. Les utilisateurs peuvent sélectionner **Créer une équipe à partir d’un modèle existant** lors de la création d’une équipe, et les propriétaires teams peuvent également utiliser la [API Graph (bêta)](/graph/api/resources/teams-api-overview) pour créer une équipe à partir des modèles disponibles.

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>Quelles tâches puis-je automatiser via PowerShell ou Graph ?

Microsoft [API Graph (bêta)](/graph/api/resources/teams-api-overview) peut effectuer les opérations suivantes :

-   Créez une équipe.
-   Ajoutez des membres et des propriétaires.
-   Ajouter des canaux.
-   Ajouter des applications.
-   Raccourcissez ces étapes en clonant une équipe existante et obtenez également ses onglets.
-   Donnez à l’utilisateur un lien vers l’équipe que vous venez de créer.
-   Supprimez les membres, les propriétaires, les canaux et les applications lorsque vous n’en avez plus besoin.
-   Archivez l’équipe lorsqu’elle n’est plus active. 
-   Supprimez l’équipe.
-   Créer un thread de canal

[PowerShell](/powershell/module/teams/?view=teams-ps) peut effectuer les opérations suivantes :

-   Créez une équipe.
-   Ajoutez des membres et des propriétaires.
-   Ajouter des canaux.
-   Supprimez les membres, les propriétaires et les canaux lorsque vous n’en avez plus besoin.
-   Supprimez l’équipe.

> [!TIP]
> Les applets de commande API Graph et PowerShell ajoutent constamment des fonctionnalités. Veillez souvent à consulter les articles [Microsoft API Graph (bêta)](/graph/api/resources/teams-api-overview) et [PowerShell](/powershell/module/teams/?view=teams-ps) pour obtenir des améliorations de fonctionnalités.  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>Puis-je contrôler à quelles fonctionnalités Teams mes enseignants et étudiants ont accès ?

Oui. Vous pouvez utiliser des stratégies pour contrôler des fonctionnalités spécifiques de messagerie, de réunion, d’appel et d’événement en direct aux laquelle vos utilisateurs ont accès. Vous pouvez utiliser des paramètres à l’échelle du locataire pour appliquer les mêmes paramètres à tous ou appliquer des stratégies au niveau de l’utilisateur si nécessaire. 

Pour plus d’informations sur les stratégies Teams, consultez [Gérer les paramètres Microsoft Teams pour votre organisation](enable-features-office-365.md).
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>Puis-je contrôler les parties externes avec lesquelles mes enseignants et étudiants collaborent ?

Vous pouvez utiliser l’accès invité pour inviter des utilisateurs en dehors de votre locataire, ce qui peut être utile pour la collaboration de recherche ou les conférences invités :

-   Utilisez une liste d’autorisation de domaine pour autoriser ou bloquer des invités en fonction de leur domaine.
-   Activez et désactivez l’accès invité pour des Groupes Microsoft 365 et des équipes particulières, afin de contrôler les équipes qui peuvent (et ne peuvent pas) inviter des invités.
-   Utilisez le journal d’audit pour voir quelles alertes ont été envoyées aux invités invités.

Pour plus d’informations, consultez [Accès invité dans Groupes Microsoft 365](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage).

## <a name="what-information-can-i-review-about-existing-teams"></a>Quelles informations puis-je examiner sur les équipes existantes ?

Vous pouvez vérifier les journaux d’audit pour voir :

-   Qui a été invité en tant qu’invité dans quelle équipe.
-   Qui a créé l’équipe.

Pour plus d’informations, consultez [rechercher des événements dans Microsoft Teams dans le journal d’audit](audit-log-events.md).

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>Teams évolue si rapidement. Comment puis-je rester à jour ?

Nous vous recommandons les ressources suivantes pour obtenir les dernières mises à jour sur Teams :

-   [Nouveautés de Microsoft Teams](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [Blog Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)