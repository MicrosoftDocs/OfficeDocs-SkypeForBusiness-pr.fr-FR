---
title: FAQ sur la gouvernance de Microsoft Éducation pour les informaticiens - Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Réponses aux questions fréquemment posées par les administrateurs de groupes Microsoft Education qui utilisent Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 719f9429d49dfef7a21670c67bad96c9e26c993e
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837434"
---
# <a name="microsoft-education-governance-faq-for-admins"></a>FAQ sur la gouvernance de Microsoft Éducation pour les administrateurs

> [!Tip]
> Regardez la vidéo suivante pour en savoir plus sur la gestion dans Microsoft teams : [gouvernance, gestion et cycle de vie dans Microsoft teams](https://aka.ms/teams-governance)

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>Comment puis-je contrôler la création d’une équipe ? Je suis inquiet pour créer des équipes inappropriées.

Pour éviter d’utiliser des noms inappropriés ou incorrects, ou pour fournir davantage de structure pour la façon dont les équipes sont nommées, vous pouvez utiliser la stratégie d’attribution de noms de groupes Office 365 (actuellement en version préliminaire) :

-   **Stratégie de nom de suffixe de préfixe** Vous pouvez utiliser des préfixes ou des suffixes pour définir la Convention d’affectation de noms Teams (groupes), par exemple **GRP_US_My Group_Engineering**. Les préfixes et suffixes peuvent être des chaînes fixes ou des attributs utilisateur (comme **[Department]**) qui sont ajoutés au nom en fonction de l’utilisateur qui crée l’équipe.
-   **Mots bloqués personnalisés** Vous pouvez charger un ensemble de mots que les utilisateurs d’une organisation spécifique ne peuvent pas utiliser dans les noms des équipes qu’ils créent. Par exemple, vous pouvez bloquer l’utilisation du **PDG** **, de la** **paie**et de l’or dans les noms des équipes auxquelles ils ne s’appliquent pas.
-   **Classement** Vous pouvez créer des classifications que les utilisateurs de votre organisation peuvent configurer lors de la création d’un groupe Office 365. 

> [!IMPORTANT]
> L’utilisation de la stratégie d’attribution de noms de groupes Office 365 nécessite les licences Azure Active Directory Premium P1 ou les licences Azure AD basique EDU pour chaque utilisateur unique membre d’un ou de plusieurs groupes Office 365.

Pour obtenir des instructions détaillées, voir [stratégie d’attribution de noms de groupes Office](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).

> [!Note]
> Si les équipes sont créées automatiquement à l’aide de l’entrée d’un autre système (par exemple, School Data Sync), vérifiez que les données d’entrée sont conformes à la stratégie d’appellation que vous avez configurée. Si ce n’est pas le cas, la création d’équipe échoue.

## <a name="can-i-see-who-created-a-team"></a>Puis-je voir qui a créé une équipe ?

Pour savoir qui a créé une équipe spécifique, voir [effectuer des recherches dans le journal d’audit pour les événements dans Microsoft teams](audit-log-events.md).

## <a name="can-i-control-who-can-create-teams"></a>Puis-je contrôler qui peut créer des équipes ?

En règle générale, nous recommandons de ne pas empêcher quiconque de créer des équipes. Si tout le monde peut créer des équipes, les équipes sont plus susceptibles d’être adoptées. Les enseignants, professeurs ou étudiants peuvent utiliser teams pour créer des groupes d’études ou des groupes d’intérêt spéciaux. Cela permettra aux équipes d’être acceptées à l’intérieur et à l’extérieur de la Classroom.

Dans notre connaissance, l’éducation des utilisateurs contribue à garantir l’utilisation des équipes responsables. Dès que les utilisateurs savent que la création d’équipes n’est pas anonyme, elles comprennent les implications de la création en toute négligence de ces équipes et ont tendance à s’éloigner de l’utilisation de l’outil.

Si vous êtes sûr de vouloir contrôler qui peut créer des équipes, voir [gérer les utilisateurs autorisés à créer des groupes Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>Comment créer automatiquement une équipe pour chaque cours au début du semestre ou du trimestre ?

Au début de chaque semestre ou trimestre, vous aurez besoin de plusieurs nouvelles équipes. Il peut être judicieux d’adopter une approche automatisée pour créer ces équipes automatiquement, les remplir avec les utilisateurs appropriés et définir les autorisations appropriées :

-   School Data Sync peut créer des groupes Office 365 pour Exchange Online et SharePoint Online, équipes de classe pour Microsoft teams et les blocs-notes OneNote pour la classe, groupes School pour Intune pour l’éducation, et intégration de l’authentification unique et de l’authentification unique pour de nombreux autres applications tierces. Pour en savoir plus, voir [vue d’ensemble de School Data Sync](https://docs.microsoft.com/schooldatasync/overview-of-school-data-sync).
-   PowerShell vous permet de créer des équipes et des canaux, et de configurer les paramètres automatiquement. Pour plus d’informations, consultez [Microsoft teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) .
-   Vous pouvez utiliser l’API Microsoft Graph (actuellement disponible en version bêta) pour créer, configurer, cloner et archiver des équipes. Pour plus d’informations, reportez-vous [à utiliser l’API Microsoft Graph pour utiliser Microsoft teams](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) .

> [!TIP]
> School Data Sync crée un groupe Office 365 pour chaque classe synchronisé et [active l’appartenance aux groupes cachés](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) de sorte que seuls les enseignants et les étudiants au sein de la classe puissent voir les membres de la classe. Si vous utilisez un autre processus pour créer des groupes de classes, utilisez le paramètre HiddenGroupMembershipEnabled de l’applet de nouvelle cmdlet New-Unifiedgrouphttps pour répondre aux exigences de confidentialité.

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>Comment puis-je gérer les équipes au terme du semestre ou du trimestre ?

Nous vous recommandons d’abord de réfléchir à la façon dont vous souhaitez gérer les données d’équipe au début du semestre ou du trimestre : Si vous souhaitez le supprimer ou le conserver à la disposition des étudiants, même après avoir suivi le cours. Si vous souhaitez conserver le calendrier scolaire à l’esprit, toutes les stratégies que vous définissez n’entrent pas en conflit avec les jours fériés. Pour implémenter votre stratégie, vous pouvez utiliser les outils suivants :

-   **Stratégie de rétention :** Cette opération permet de supprimer toutes les données antérieures à un âge que vous spécifiez pour vous assurer qu’elles sont supprimées des conversations (pour tous les utilisateurs ou pour tous les utilisateurs) et canaux. Vous pouvez également configurer teams pour conserver le contenu afin qu’il ne puisse pas être supprimé. Pour plus d’informations, voir [stratégies de rétention de Microsoft teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011).
-   **Politique d’expiration :** Configurer teams pour qu’il expire après un certain nombre de jours. Trente jours avant la date d’expiration, tous les propriétaires d’une équipe sont avertis que leur équipe doit être renouvelée, sinon celle-ci est supprimée (un administrateur peut récupérer les équipes supprimées pendant 30 jours supplémentaires). Ce paramètre est très utile pour vous assurer que les équipes inutilisées sont au-dessus. Pour plus d’informations, voir [stratégie d’expiration de groupe Office 365](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733).

-   **Équipe d’archivage :** Ce paramètre place les équipes en mode lecture seule. Ils peuvent toujours être parcourus et recherchés, mais personne ne peut ajouter de nouvelles publications. [Archiver ou restaurer une équipe](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) décrit comment les propriétaires d’équipe peuvent archiver une équipe ; Les propriétaires d’équipe peuvent également utiliser l' [API de Graph (Beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) pour archiver ou restaurer une équipe.
 
> [!IMPORTANT]
> L’utilisation de la stratégie d’expiration des groupes Office 365 requiert des licences Azure Active Directory Premium P1 pour chaque utilisateur unique membre d’un ou de plusieurs groupes Office 365.

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>Est-il possible de créer des modèles d’équipe pour les membres du corps enseignant lors de la création d’une équipe ?

Oui. Les utilisateurs peuvent sélectionner **créer une équipe à partir d’un modèle existant** lors de la création d’une équipe, et les propriétaires d’équipes peuvent également utiliser l' [API de Graph (Beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) pour créer une nouvelle équipe à partir des modèles disponibles.

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>Quelles tâches puis-je automatiser via PowerShell ou Graph ?

L' [API Microsoft Graph (Beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) peut effectuer les opérations suivantes :

-   Créer une équipe
-   Ajouter des membres et des propriétaires.
-   Ajoutez des canaux.
-   Ajouter des applications.
-   Raccourcissez ces étapes en clonant une équipe existante et en obtenant également ses onglets.
-   Donnez à l’utilisateur un lien vers l’équipe que vous venez de créer.
-   Supprimez des membres, propriétaires, canaux et applications lorsque vous n’en avez plus besoin.
-   Archivez l’équipe lorsque celle-ci n’est plus active. 
-   Supprimez l’équipe.
-   Créer un thread de canal

[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) peut procéder comme suit :

-   Créer une équipe
-   Ajouter des membres et des propriétaires.
-   Ajoutez des canaux.
-   Supprimez des membres, des propriétaires et des canaux lorsque vous n’en avez plus besoin.
-   Supprimez l’équipe.

> [!TIP]
> L’API graphique et les applets de cmdlet PowerShell ajoutent constamment des fonctionnalités. Prenez soin de vérifier les articles [Microsoft Graph API (Beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) et [PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) fréquemment pour les améliorations apportées aux fonctionnalités.  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>Puis-je contrôler les fonctionnalités d’équipes auxquelles mes enseignants et leurs élèves ont accès ?

Oui. Vous pouvez utiliser des stratégies pour contrôler des fonctionnalités d’événement, de réunion, d’appel et de messagerie instantanée spécifiques auxquelles vos utilisateurs ont accès. Vous pouvez utiliser les paramètres à l’échelle du client pour appliquer les mêmes paramètres, ou appliquer des stratégies au niveau utilisateur si nécessaire. 

Pour plus d’informations sur les stratégies d’équipe, voir [gérer les paramètres de Microsoft teams pour votre organisation](enable-features-office-365.md).
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>Puis-je contrôler les parties externes avec lesquelles les enseignants et les étudiants collaborent ?

Vous pouvez utiliser l’accès invité pour inviter des utilisateurs en dehors de votre client, ce qui peut être utile pour la collaboration de recherche ou les conférences invitées :

-   Utiliser la fonction de création de domaine pour autoriser ou bloquer des invités en fonction de leur domaine.
-   Activez et désactivez l’accès invité pour des groupes et équipes Office 365 spécifiques pour contrôler les équipes qui peuvent (et non) inviter des invités.
-   Utilisez le journal d’audit pour afficher les alertes envoyées aux invités invités.

Pour plus d’informations, reportez-vous à la rubrique [accès invité dans les groupes Office 365](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage).

## <a name="what-information-can-i-review-about-existing-teams"></a>Quelles informations peuvent être examinées sur les équipes existantes ?

Vous pouvez consulter les journaux d’audit pour afficher les éléments suivants :

-   Personnes invitées comme invité à une équipe.
-   Qui a créé l’équipe.

Pour plus d’informations, reportez-vous [à la rubrique Rechercher des événements dans le journal d’audit de Microsoft teams](audit-log-events.md).

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>Teams évolue de façon rapide. Comment être informé des mises à jour ?

Nous vous recommandons de consulter les ressources suivantes pour obtenir les dernières mises à jour sur teams :

-   [Nouveautés de Microsoft teams](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [Blog Microsoft teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)
