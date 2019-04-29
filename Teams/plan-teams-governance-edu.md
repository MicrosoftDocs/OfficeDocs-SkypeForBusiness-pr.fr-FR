---
title: FAQ sur la gouvernance de Microsoft Éducation pour les informaticiens - Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 08/10/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Réponses aux questions fréquemment posées à partir des groupes Microsoft Education, les administrateurs qui utilisent des équipes.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 425dc91384dd97af1b61ab6c0a19d003e20330be
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2019
ms.locfileid: "33401598"
---
# <a name="microsoft-education-governance-faq-for-admins"></a>FAQ sur la gouvernance de Microsoft Éducation pour les administrateurs

> [!Tip]
> Regarder la session suivante pour en savoir plus sur la gestion de Microsoft Teams : [cycle de vie dans les équipes Microsoft, la gestion et la gouvernance](https://aka.ms/teams-governance)

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>Comment contrôler la création de l’équipe ? Je crains étudiants allez créer les équipes inappropriés.

Pour éviter les noms inappropriés ou trompeuses, ou seulement pour fournir une structure plus de la façon de nommer les équipes, vous pouvez utiliser la stratégie (actuellement en aperçu) de noms Office 365 groupes :

-   **Stratégie de noms préfixe suffixe** Vous pouvez utiliser les préfixes ou suffixes pour définir la convention d’affectation de noms des équipes (groupes), par exemple, **GRP_US_My Group_Engineering**. Les préfixes et les suffixes peuvent être résolus chaînes ou des attributs utilisateur (par exemple, **[service]**) qui sont ajoutés au nom en fonction de l’utilisateur qui crée l’équipe.
-   **Personnalisé bloqués mots** Vous pouvez télécharger un ensemble de mots que les utilisateurs d’une organisation spécifique sont bloqués à partir de l’utiliser dans les noms des équipes qu’ils créent. Par exemple, vous pouvez bloquer les termes **CEO**, **Paie**et **ressources humaines** d’être utilisés dans les noms d’équipe pour qu’ils ne s’appliquent pas les groupes.
-   **Classification** Vous pouvez créer des classifications que les utilisateurs de votre organisation peuvent définir lorsqu’ils créent un groupe d’Office 365. 

> [!IMPORTANT]
> À l’aide de la stratégie d’attribution de noms Office 365 groupes nécessite des licences d’Azure Active Directory Premium P1 ou licences EDU Azure AD base pour chaque utilisateur unique qui est un membre d’un ou plusieurs groupes d’Office 365.

Pour obtenir des instructions détaillées, voir [stratégie de noms de groupes de Office](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).

> [!Note]
> Si les équipes sont créées automatiquement à l’aide de l’entrée d’un autre système (par exemple, synchronisation des données école), vérifiez que les données d’entrée est conforme à la stratégie d’attribution de noms que vous avez configuré ; Si elle ne, de l’équipe création échouera.

## <a name="can-i-see-who-created-a-team"></a>Puis-je voir qui a créé une équipe ?

Pour savoir qui a créé une équipe spécifique, voir [recherche le journal d’audit pour les événements dans les équipes Microsoft](audit-log-events.md).

## <a name="can-i-control-who-can-create-teams"></a>Puis-je contrôler qui peut créer des équipes ?

En général, nous vous déconseillons empêche la création d’équipes. Si tout le monde peut créer des équipes, équipes est plus susceptible d’être largement adopté. Université, enseignants ou élèves permet aux équipes pour créer une étude de groupes ou des groupes d’intérêt spéciaux. Cela permet aux équipes acceptée à l’intérieur et à l’extérieur de la classe.

Dans notre expérience, la formation des utilisateurs garantit utilisation responsable des équipes. Dès que les utilisateurs comprennent que création d’équipes n’est pas anonyme, ils comprennent des implications des cas de leur création et ont tendance à écarté mauvaise utilisation de l’outil.

Si vous êtes sûr de que vouloir à contrôler qui peut créer des équipes, voir [Manage qui peut créer des groupes d’Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>Comment créer automatiquement une équipe pour chaque cours au début du trimestre ou semestre ?

Au début de chaque semestre ou d’un trimestre, vous aurez besoin d’un certain nombre de nouvelles équipes. Il peut être utile pour adopter une approche automatisée pour créer ces équipes automatiquement, les remplir avec les utilisateurs de droite et définir les autorisations appropriées :

-   Synchronisation des données de l’école pouvez créer des groupes d’Office 365 pour Exchange Online et SharePoint Online, équipes de classe pour les ordinateurs portables Teams Microsoft et OneNote classe, des groupes de l’école pour Intune pour l’éducation et rostering et unique (SSO) intégration de connexion pour nombreux autres les applications tierces. Pour plus d’informations en [Vue d’ensemble de synchronisation des données école](https://docs.microsoft.com/schooldatasync/overview-of-school-data-sync).
-   PowerShell, vous pouvez créer des canaux et des équipes et configurer les paramètres automatiquement. Pour plus d’informations, voir [Microsoft équipes PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) .
-   Vous pouvez utiliser l’API de graphique Microsoft (actuellement en version bêta) pour créer, configurer, cloner et archiver les équipes. Pour plus d’informations, voir [utiliser l’API de graphique Microsoft pour travailler avec les équipes Microsoft](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) .

> [!TIP]
> Synchronisation des données de l’école crée un groupe d’Office 365 pour chaque classe synchronisés et [permet l’appartenance au groupe masqué](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) afin que seuls les enseignants et étudiants au sein de la classe peuvent afficher les membres de cette classe. Si vous utilisez un autre processus pour créer des groupes de classe utilisent le paramètre HiddenGroupMembershipEnabled de l’applet de commande New-UnifiedGroup pour satisfaire les exigences de confidentialité même.

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>Comment gérer avec des équipes du trimestre ou semestre fin ?

Il est recommandé que vous pensez tout d’abord comment vous souhaitez gérer les données des équipes lorsque le semestre école ou un trimestre est sur : s’il faut supprimer ou conserver disponibles pour les étudiants même une fois qu’ils ont effectuées au cours. Vous souhaiterez n’oubliez pas le calendrier de l’école afin que les stratégies que vous définissez n’entre en conflit avec les jours fériés. Vous pouvez utiliser les outils suivants pour implémenter votre stratégie :

-   **Stratégie de rétention :** Permet de supprimer toutes les données antérieures à un âge que vous spécifiez pour vous assurer que les anciennes données sont supprimées de salles de conversation (pour les utilisateurs tout ou partie) et les canaux. Vous pouvez également configurer des équipes pour conserver le contenu afin qu’il ne peut pas être supprimée. Pour plus d’informations, voir [stratégies de rétention pour les équipes Microsoft](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011).
-   **Stratégie d’expiration :** Configurer des équipes pour qu’elle expire après un certain nombre de jours. Trente jours avant l’expiration, tous les propriétaires d’une équipe sont avertis que leur équipe doit être renouvelé, sinon il sera supprimé (même si un administrateur peut récupérer supprimés équipes pour 30 jours). Ce paramètre est très utile pour vous assurer que les équipes inutilisés sont sunsetted. En savoir plus sur [Office 365 groupe d’expiration](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733).

-   **Équipe archive :** Ce paramètre place les équipes en mode lecture seule. Peut toujours être explorés et recherchés, mais aucun participant ne peut ajouter les nouvelles publications. [Archivage ou restauration d’une équipe](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) décrit comment les propriétaires de l’équipe peuvent archiver une équipe ; Propriétaires de l’équipe pouvant également utiliser l' [API de graphique (bêta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) à archiver ou restaurer une équipe.
 
> [!IMPORTANT]
> À l’aide de la stratégie d’Expiration de Office 365 groupes nécessite des licences d’Azure Active Directory Premium P1 pour chaque utilisateur unique qui est un membre d’un ou plusieurs groupes d’Office 365.

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>Y a-t-il des modèles d’équipe pour mon enseignants à utiliser lors de la création d’une équipe ?

Oui. Les utilisateurs peuvent sélectionner **Créer une équipe à partir de modèles de sécurité existants** lors de la création d’une nouvelle équipe, et les propriétaires des équipes peuvent également utiliser l' [API de graphique (bêta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) pour créer une nouvelle équipe à partir des modèles disponibles.

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>Quelles sont les tâches puis-je automatiser via PowerShell ou graphique ?

L' [Interface API Microsoft Graph (bêta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) pouvez procédez comme suit :

-   Créer une équipe.
-   Ajouter des membres et propriétaires.
-   Ajouter des chaînes.
-   Ajouter des applications.
-   Raccourci ces étapes en clonant une existante de l’équipe et obtenir ses onglets trop.
-   Donner à l’utilisateur un lien vers l’équipe que vous venez de créer.
-   Supprimer des membres, les propriétaires, canaux et applications lorsque vous n’avez plus besoin.
-   Archiver l’équipe lorsqu’il n’est plus actif. 
-   Supprimer l’équipe.
-   Création d’un thread de canal

[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) peut procédez comme suit :

-   Créer une équipe.
-   Ajouter des membres et propriétaires.
-   Ajouter des chaînes.
-   Supprimer des membres, les propriétaires et les canaux lorsque vous n’avez plus besoin.
-   Supprimer l’équipe.

> [!TIP]
> Les applets de commande PowerShell et les API de graphique sont constamment obligé d’ajouter des fonctionnalités. Vérifiez les articles [Microsoft Graph API (bêta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) et [PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) généralement des améliorations de la fonctionnalité.  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>Puis-je contrôler les fonctionnalités d’équipes mon enseignants et les étudiants ont accès aux ?

Oui. Vous pouvez utiliser des stratégies pour contrôler la messagerie spécifiques, réunion, appel et live vos utilisateurs ont accès aux fonctionnalités d’événement. Vous pouvez utiliser les paramètres au niveau du client pour appliquer les mêmes paramètres à tous ou appliquer des stratégies au niveau de l’utilisateur si nécessaire. 

Pour plus d’informations sur les stratégies d’équipes, voir [les équipes Microsoft gérer les paramètres de votre organisation](enable-features-office-365.md).
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>Puis-je contrôler les enseignants et des étudiants collaborent avec des parties externes ?

Vous pouvez utiliser l’accès invité à inviter des utilisateurs à partir d’à l’extérieur de votre client, ce qui peut être utile pour la collaboration de recherche ou des conférences de l’invité :

-   Création de listes autorisées domaine permet d’autoriser ou bloquer des invités, en fonction de leur domaine.
-   Activer l’accès invité et désactiver pour Office 365 groupes et équipes, notamment contrôler les équipes peuvent (et ne peut pas) invités.
-   Utilisez le journal d’audit pour afficher les alertes qui ont été envoyés aux invités.

Pour plus d’informations, consultez [accès invité dans Office 365 groupes](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage).

## <a name="what-information-can-i-review-about-existing-teams"></a>Quelles informations puis-je consulter sur les équipes existantes ?

Vous pouvez vérifier les journaux d’audit, voir :

-   Qui a été invité en tant qu’invité à l’équipe.
-   Personne qui a créé l’équipe.

Pour plus d’informations, voir [recherche le journal d’audit pour les événements dans les équipes Microsoft](audit-log-events.md).

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>Les équipes évolue très rapidement. Comment puis-je rester à jour ?

Nous vous recommandons les ressources suivantes pour obtenir les dernières mises à jour sur les équipes :

-   [Nouveautés de Microsoft Teams](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [Blog Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)
