---
title: Planifier la gouvernance dans Teams - Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Dans cet article, vous allez découvrir comment planifier la mise en œuvre des fonctionnalités de gouvernance dans Teams.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ca020de2f2ce96daa3fe213b7b5c0d80b720165b
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728623"
---
# <a name="plan-for-governance-in-teams"></a>Planifier la gouvernance dans Teams

Teams fournit un ensemble enrichi d’outils pour implémenter les fonctionnalités de gouvernance dont votre organisation peut avoir besoin. Cet article aide les professionnels de l’informatique à poser les bonnes questions afin de déterminer leurs exigences de gouvernance et la manière de les répondre. 

> [!Tip] 
> Regardez la session suivante pour en savoir plus sur la gouvernance dans Microsoft Teams : [gouvernance, gestion](https://aka.ms/teams-governance) et cycle de vie dans Microsoft Teams

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>Création de groupes et d’équipes, attribution de noms, classification et accès invité

Votre organisation peut exiger que vous implémentiez des contrôles stricts sur la manière dont les équipes sont nommées et classées, si les invités peuvent être ajoutés en tant que membres d’équipe et qui peut créer des équipes. Vous pouvez configurer ces domaines à l’aide de Azure Active Directory de sensibilité (Azure AD). 

<br>

|-        |-        |-        |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |Points de décision|<ul><li>Votre organisation exige-t-elle une convention d’attribution de noms spécifique pour les équipes ?</li><li>Les créateurs d’équipe ont-ils besoin de pouvoir attribuer des classifications spécifiques à l’organisation aux équipes ?</li><li>Vous avez besoin de limiter la possibilité d’ajouter des invités aux équipes au niveau de chaque équipe ?</li><li>Votre organisation a-t-elle besoin de limiter les personnes autorisées à créer des équipes ?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|Étapes suivantes|<ul><li>Documenter les exigences de votre organisation en matière de création d’équipe, d’attribution de noms, de classification et d’accès invité.</li><li>Planifiez l’implémenter dans le cadre de votre déploiement Teams déploiement.</li><li>Communiquez et publiez vos stratégies pour informer Teams utilisateurs du comportement qu’ils peuvent attendre.</li></ul>|

> [!NOTE]
> Pour vous aider à planifier, découvrez comment définir ces stratégies [et quelles licences elles requièrent.](/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)
> 
> [!NOTE]
> La limitation de la création de groupes et d’équipes peut ralentir la productivité de vos utilisateurs, car de nombreux services Microsoft 365 et Office 365 nécessitent la création de groupes pour que le service fonctionne. Pour plus d’informations, [consultez le plan de gouvernance dans Teams.](/microsoft-365/solutions/manage-creation-of-groups)


#### <a name="additional-information"></a>Informations supplémentaires

Une fois que vous avez déterminé vos besoins, vous pouvez les implémenter à l’aide de contrôles Azure AD. Pour obtenir des conseils techniques sur la façon d’implémenter ces paramètres, voir :

- [Azure Active Directory des cmdlets pour la configuration des paramètres de groupe](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)

- [Appliquer une stratégie de noms pour Microsoft 365 groupes dans Azure Active Directory](/azure/active-directory/users-groups-roles/groups-naming-policy)

- [Microsoft 365 Stratégie de noms de groupes](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

- [Utiliser des étiquettes de sensibilité pour protéger le contenu Microsoft Teams, Microsoft 365 groupes et SharePoint sites](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

- [Options de fin de cycle de vie pour les groupes, les équipes et les Yammer](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)

## <a name="group-and-team-expiration-retention-and-archiving"></a>Expiration, rétention et archivage des équipes et des groupes

Votre organisation peut avoir des exigences supplémentaires pour définir des stratégies d’expiration, de rétention et d’archivage des équipes et des données d’équipe (messages de canal et fichiers de canal). Vous pouvez configurer des stratégies d’expiration de groupe pour gérer automatiquement le cycle de vie du groupe et des stratégies de rétention afin de conserver ou de supprimer les informations au besoin, et vous pouvez archiver les équipes (les configurer en mode lecture seule) afin de conserver un affichage à un moment donné d’une équipe qui n’est plus active. Notez que la stratégie d’expiration des équipes archivées est toujours appliquée et peut être supprimée sauf en cas d’exclusion ou de renouvellement.

|-          |-           |
|-----------|------------|
| ![Icône représentant des points de décision.](media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Votre organisation exige-t-elle que teams spécifie une date d’expiration ?</li><li>Votre organisation exige-t-elle que des stratégies spécifiques de rétention des données soient appliquées aux équipes ?</li><li>Votre organisation souhaite-t-elle avoir besoin de la possibilité d’archiver des équipes inactives afin de conserver le contenu en lecture seule ?</li></ul>|
| ![Icône illustrant les étapes suivantes.](media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Documenter les exigences de votre organisation en matière d’expiration des équipes, de rétention des données et d’archivage.</li><li>Planifiez l’implémenter dans le cadre de votre déploiement Teams déploiement.</li><li>Communiquez et publiez vos stratégies pour informer Teams utilisateurs du comportement qu’ils peuvent attendre.</li></ul>|

> [!TIP]
> Utilisez le tableau suivant pour capturer les besoins de votre organisation.

|Fonctionnalité |Détails |Azure AD Premium licence requise |Decision |
|---------|---------|---------|---------|
|Stratégie d’expiration |Gérez le cycle de vie Microsoft 365 de groupes en fixant une stratégie d’expiration. |P1 |TBD|
|Stratégie de rétention |Conservez ou supprimez des données pour une période spécifique en fixant des stratégies de rétention Teams dans le Centre de sécurité et & conformité. **Remarque**: l’utilisation de cette fonctionnalité nécessite la Microsoft 365 licence Office 365 Entreprise E3 ou une licence supérieure. |Non |TBD |
|Archiver et restaurer |Archivez une équipe quand elle n’est plus active mais que vous souhaitez la conserver pour référence ou pour la réactiver ultérieurement. |Non |TBD |

> [!Note]
> L’expiration de groupe est Azure AD Premium fonctionnalité de regroupement. Pour que cette fonctionnalité soit disponible, votre client doit avoir un abonnement à Azure AD Premium et des licences pour l’administrateur qui configure les paramètres et les membres des groupes concernés.

#### <a name="additional-information"></a>Informations supplémentaires

Pour obtenir des conseils techniques sur la façon d’implémenter ces paramètres, voir :

- [Configurer l’Microsoft 365 expiration des groupes.](/azure/active-directory/users-groups-roles/groups-lifecycle)

- [Configurer Teams stratégies de rétention.](retention-policies.md)

- [Archiver ou restaurer une équipe.](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)

## <a name="group-and-team-membership-management"></a>Gestion des appartenances aux groupes et aux équipes

La gestion cohérente des membres de groupes restreints ou basés sur un projet est nécessaire pour les équipes qui ont besoin d’une intégration et d’un offboard rapides, ou pour les utilisateurs et les invités. Votre organisation peut également avoir besoin de s’assurer que tous les membres actuels ont la justification d’activité pour faire partie d’une équipe. La gestion des membres peut être difficile, car les propriétaires d’équipe peuvent quitter le groupe et les utilisateurs ne quittent généralement pas les groupes de leur propre chef à la fin d’un projet ou lorsqu’ils changent de rôle. La meilleure façon de gérer l’appartenance aux groupes qui permet aux utilisateurs d’y accéder en cas de besoin, mais de s’assurer que le groupe ne risque pas d’accéder de façon inappropriée consiste à passer par deux processus de district : la gestion des droits et les examens de l’accès.

[La gestion des](/azure/active-directory/governance/entitlement-management-overview) droits vous permet de déléguer à une personne, telle qu’un responsable de projet, toutes les ressources nécessaires, y compris les appartenances à des équipes, dans un package unique. Ils peuvent également définir qui peut faire des demandes : utilisateurs dans votre client ou d’autres organisations connectées. Le responsable de projet recevra les demandes d’accès par courrier électronique et approuvera ou refusera les demandes dans le portail MyAccess. Les administrateurs peuvent configurer les conditions d’accès de façon à inclure une date ou une période d’expiration au moment où l’utilisateur ou l’invité sera supprimé de l’équipe, sauf si l’accès est renouvelé. Les administrateurs peuvent également configurer les groupes associés aux équipes pour qu’ils participent aux révisions d’accès. Pour [les avis d’accès,](/azure/active-directory/governance/access-reviews-overview)les propriétaires du groupe reçoivent des rappels réguliers pour passer en revue les membres d’une équipe. Les avis sur Access incluent des recommandations qui facilitent pour les propriétaires de groupe la procédure de révision régulière.

|-|-|-|
|:-|:-|:-|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  | Points de décision | Votre organisation a-t-elle besoin d’un processus cohérent pour gérer l’appartenance à une ou plusieurs équipes ? <br> Votre organisation exige-t-elle que les propriétaires, ou les membres eux-mêmes, justifient régulièrement leur appartenance continue à une ou plusieurs équipes ? <br> Votre organisation a-t-elle besoin d’une approbation pour que les utilisateurs et les invités demandent l’accès à des ressources, y compris des équipes, des groupes, des sites SharePoint et des applications ? |
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>| Étapes suivantes ? | Documenter les exigences de votre organisation pour chaque équipe ou équipe spécifique en vue de l’expiration de l’appartenance.<br>Planifiez la manière dont votre organisation peut regrouper les équipes, les groupes, SharePoint sites et les applications ensemble dans des packages d’accès.<br>Planifiez les personnes, telles que le responsable du demandeur, un responsable de projet, un sponsor pour une organisation connectée ou un responsable de la sécurité de votre organisation, qui devront approuver ou refuser les demandes d’accès. |

> [!TIP]
> Utilisez le tableau suivant pour capturer les besoins de votre organisation.

| Fonctionnalité | Détails | Azure AD Premium licence requise | Decision |
|:-|:-|:-|:-|
| Avis sur Access | Révisions de l’accès à la configuration pour recertifier l’appartenance à intervalles réguliers d’équipes spécifiques | P2 | TBD |
| Gestion des droits | Configurer le package d’accès pour permettre aux utilisateurs et aux invités de demander l’accès aux équipes | P2 | TBD |

> [!NOTE]
> Pour vous aider à planifier, découvrez les [licences dont ils ont besoin.](https://azure.microsoft.com/pricing/details/active-directory/)

### <a name="additional-information"></a>Informations supplémentaires

Pour obtenir des conseils techniques sur la façon d’implémenter ces paramètres, voir :

- [Gestion des droits](/azure/active-directory/governance/entitlement-management-overview)
- [Avis sur Access](/azure/active-directory/governance/access-reviews-overview)

## <a name="teams-feature-management"></a>Teams gestion des fonctionnalités

Un autre aspect important de la gouvernance et de la gestion du cycle de vie Teams est la possibilité de contrôler les fonctionnalités dont vos utilisateurs auront accès. Vous pouvez gérer les fonctionnalités de messagerie, de réunion et d’appel, au niveau Microsoft 365 ou Office 365 de l’organisation ou par utilisateur.


|-        |-        |
|---------|---------|
| ![Icône représentant des points de décision.](media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Votre organisation a-t-elle besoin de limiter Teams fonctionnalités pour l’ensemble de votre client ?</li><li>Votre organisation a-t-elle besoin de limiter Teams fonctionnalités de sécurité pour des utilisateurs spécifiques ?</li></ul>|
| ![Icône illustrant les étapes suivantes.](media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Documenter les exigences de votre organisation en matière de limitation Teams fonctionnalités au niveau du client et de l’utilisateur.</li><li>Planifiez l’implémenter dans le cadre de votre déploiement Teams déploiement.</li><li>Communiquez et publiez vos stratégies pour informer Teams utilisateurs du comportement qu’ils peuvent attendre.</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>Teams zones de focus sur la gestion des fonctionnalités

Teams fournit des fonctionnalités granulaires pour contrôler la messagerie, les réunions, les appels et les événements en direct, et bien plus encore, via des stratégies. Différentes stratégies peuvent être appliquées par défaut ou par utilisateur à tous les utilisateurs, selon les besoins de votre organisation. 

Pour obtenir des listes détaillées de tous les paramètres, y compris des conseils techniques sur leur mise en œuvre pour votre organisation, consultez les articles suivants :

- [Gérer les paramètres de Microsoft Teams pour votre organisation](enable-features-office-365.md)
- [Gérer Teams lors de la transition vers le nouveau Centre d’administration de Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md)
- [Canaux privés dans Microsoft Teams](private-channels.md)
- [Gérer les stratégies de réunion dans Teams](meeting-policies-in-teams.md)
- [Gérer les stratégies de messagerie dans Teams](messaging-policies-in-teams.md)
- [Gérer vos applications dans le Centre Microsoft Teams’administration](manage-apps.md)

En outre, vous pouvez configurer la modération pour un canal et donner des capacités de modérateur à certains utilisateurs afin qu’ils contrôlent qui peut créer des publications de canal et y répondre. Pour [plus d’informations, voir](manage-channel-moderation-in-teams.md) Configurer et gérer la modération Microsoft Teams canal.

## <a name="security-and-compliance"></a>Sécurité et conformité

Teams est intégré aux fonctionnalités avancées de sécurité et de conformité de Microsoft 365 et Office 365 et prend en charge l’audit et la rapports, la recherche de contenu de conformité, la découverte électronique, la conservation légale et les stratégies de rétention.

> [!Important]
> Si votre organisation a des exigences en matière de conformité et de sécurité, examinez le contenu détaillé fourni à ce sujet dans l’article Vue d’ensemble de la sécurité et de la [conformité dans Microsoft Teams.](security-compliance-overview.md)

## <a name="related-topics"></a>Rubriques connexes

[Démarrage rapide de la gouvernance pour Teams](teams-adoption-governance-quick-start.md)

[Microsoft 365 conseils en matière de gestion des licences en matière de sécurité & conformité](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->