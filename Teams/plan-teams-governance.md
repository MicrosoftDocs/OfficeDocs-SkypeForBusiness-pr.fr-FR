---
title: Planifier la gouvernance dans Teams - Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Dans cet article, vous allez découvrir comment implémenter des fonctionnalités de gouvernance dans Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2180c819491b3067225ada993aec60ec052bc69f
ms.sourcegitcommit: 43823358e7e1c1cece72a69a2ceb4eff86d3f927
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "48416908"
---
# <a name="plan-for-governance-in-teams"></a>Planifier la gouvernance dans Teams

Teams propose un ensemble complet d’outils permettant d’implémenter les fonctionnalités de gouvernance dont votre organisation peut avoir besoin. Cet article indique aux professionnels de l’informatique les personnes qui ont besoin des questions qui vous permettent de déterminer les besoins en matière de gouvernance et comment les respecter. 

> [!Tip] 
> Regardez la session suivante pour en savoir plus sur la gouvernance dans Microsoft teams : [gouvernance, gestion et cycle de vie dans Microsoft teams](https://aka.ms/teams-governance)

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>Création de groupes et d’équipes, attribution de noms, classification et accès invité

Votre organisation peut nécessiter l’implémentation de contrôles stricts sur le nom et le classement des équipes, si les invités peuvent être ajoutés en tant que membres d’équipe et qui peut créer des équipes. Vous pouvez configurer ces zones à l’aide d’Azure Active Directory (Azure AD) et d’étiquettes de sensibilité. 

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |Points de décision|<ul><li>Votre organisation nécessite-t-elle une convention d’affectation des noms spécifique pour teams ?</li><li>Les créateurs d’équipe doivent-ils pouvoir attribuer des classifications spécifiques à l’organisation à teams ?</li><li>Avez-vous besoin de limiter la possibilité d’ajouter des invités à des équipes par équipe ?</li><li>Votre organisation nécessite-t-elle de limiter les utilisateurs pouvant créer des équipes ?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|Étapes suivantes|<ul><li>Documentez les exigences de votre organisation concernant la création d’équipe, l’attribution de noms, la classification et l’accès invité.</li><li>Prévoyez de mettre en œuvre ces exigences dans le cadre de votre déploiement d’équipes.</li><li>Communiquez et publiez vos stratégies afin d’informer les utilisateurs des équipes du comportement qu’ils peuvent attendre.</li></ul>|

> [!TIP]
> Le tableau suivant vous permet de capturer les exigences de votre organisation.

|Fonctionnalité |Détails |Azure AD Premium <br> licence requise |Décision |
|---------|---------|---------|---------|
|Stratégie d’affectation de noms d’équipe | Utilisez des mots bloqués personnalisés en fonction du suffixe. |Envoyé |DÉFINIR |
|Classification d’équipe |Affectez des catégories à Teams. |Envoyé |DÉFINIR |
|Accès invité d’équipe |Autorisez ou empêchez l’ajout d’invités à des équipes. |Non |DÉFINIR |
|Création d'une équipe |Limitez la création d’équipe aux administrateurs. |Non |DÉFINIR|
|Création d'une équipe |Limitez la création d’équipe aux membres du groupe de sécurité. |Envoyé |DÉFINIR|
|Étiquettes de sensibilité|Configurer la confidentialité et le partage d’invités|Non|DÉFINIR|

> [!NOTE]
> Pour vous aider à planifier, [en savoir plus sur la définition de ces stratégies et sur les licences requises](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings).
> 
> [!NOTE]
> Le fait de limiter la création de groupes et d’équipes peut ralentir la productivité de vos utilisateurs, car de nombreux services Microsoft 365 et 365 requièrent la création de groupes pour que le service fonctionne. Pour plus d’informations, accédez à et développez [Pourquoi contrôler les personnes qui créent des groupes Microsoft 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why).


#### <a name="additional-information"></a>Informations supplémentaires

Après avoir déterminé vos exigences, vous pouvez les implémenter à l’aide des contrôles Azure AD. Pour obtenir des conseils techniques sur la mise en œuvre de ces paramètres, voir :

- [Applets de contrôle Azure Active Directory pour la configuration des paramètres de groupe](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)

- [Appliquer une stratégie d’appellation pour les groupes Microsoft 365 dans Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)

- [Stratégie d’attribution de noms de groupes Microsoft 365](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

- [Utiliser des étiquettes de sensibilité pour protéger le contenu de Microsoft Teams, des groupes Microsoft 365 et des sites SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

- [Options de la fin de vie des groupes, équipes et Yammer](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)

## <a name="group-and-team-expiration-retention-and-archiving"></a>Expiration de groupe et d’équipe, rétention et archivage

Votre organisation a peut-être besoin d’exigences supplémentaires pour définir des stratégies d’expiration, de rétention et d’archivage des données des équipes et des équipes (messages de canal et fichiers de canal). Vous pouvez configurer des stratégies d’expiration de groupe pour gérer automatiquement le cycle de vie des stratégies de groupe et de rétention afin de conserver ou de supprimer les informations nécessaires, et vous pouvez archiver les équipes (leur affecter le mode lecture seule) pour conserver une vue ponctuelle d’une équipe qui n’est plus active. Notez que les équipes archivées continuent d’appliquer la stratégie d’expiration et peuvent être supprimées sauf si vous n’avez pas été exclus ou renouvelé.

|           |            |
|-----------|------------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Votre organisation nécessite-t-elle la spécification d’une date d’expiration pour teams ?</li><li>Votre organisation nécessite-t-elle des stratégies spécifiques de rétention des données ?</li><li>Votre organisation peut-elle être amenée à pouvoir archiver des équipes inactives pour conserver le contenu en lecture seule ?</li></ul>|
| ![Icône montrant les étapes suivantes](media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Documentez les exigences de votre organisation en matière d’expiration d’équipe, de conservation des données et d’archivage.</li><li>Prévoyez de mettre en œuvre ces exigences dans le cadre de votre déploiement d’équipes.</li><li>Communiquez et publiez vos stratégies afin d’informer les utilisateurs des équipes du comportement qu’ils peuvent attendre.</li></ul>|

> [!TIP]
> Le tableau suivant vous permet de capturer les exigences de votre organisation.

|Fonctionnalité |Détails |Licence Azure AD Premium requise |Décision |
|---------|---------|---------|---------|
|Stratégie d’expiration |Pour gérer le cycle de vie des groupes Microsoft 365, définissez une stratégie d’expiration. |Envoyé |DÉFINIR|
|Stratégie de rétention |Conserver ou supprimer des données pour une période spécifique en définissant des stratégies de rétention pour les équipes dans le centre de sécurité & conformité. **Remarque**: l’utilisation de cette fonctionnalité nécessite une licence de Microsoft 365 ou Office 365 entreprise E3 ou une version ultérieure. |Non |DÉFINIR |
|Archiver et restaurer |Archivez une équipe lorsque celle-ci n’est plus active mais que vous souhaitez la conserver pour référence ou pour la réactiver ultérieurement. |Non |DÉFINIR |

> [!Note]
> L’expiration du groupe est une fonctionnalité d’Azure AD Premium. Pour que cette fonctionnalité soit disponible, votre client doit disposer d’un abonnement Azure AD Premium et de licences pour l’administrateur qui configure les paramètres et les membres des groupes concernés.

#### <a name="additional-information"></a>Informations supplémentaires

Pour obtenir des conseils techniques sur la mise en œuvre de ces paramètres, voir :

- [Configurer l’expiration des groupes Microsoft 365](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle).

- [Configurez les stratégies de rétention teams](retention-policies.md).

- [Archiver ou restaurer une équipe](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).

## <a name="group-and-team-membership-management"></a>Gestion des appartenances aux groupes et aux équipes

La gestion homogène des membres du projet ou des groupes restreints est nécessaire pour les équipes qui nécessitent une intégration rapide et un déclassement via, des utilisateurs et des invités. Il est également possible que votre organisation ait besoin de vérifier que tous les membres actuels ont la justification commerciale au sein d’une équipe. La gestion des membres peut s’avérer difficile, car les propriétaires de l’équipe peuvent quitter le projet et les utilisateurs ne le laissent pas en règle générale lorsque le projet se termine ou qu’ils changent de rôle. La meilleure façon de gérer l’appartenance aux groupes qui permet aux utilisateurs d’obtenir l’accès lorsque cela est nécessaire, mais vous devez vous assurer que le groupe ne présente aucun risque d’accès inapproprié est par le biais de deux processus circonscription : gestion des habilitations et accès.

La [gestion des habilitations](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) vous permet de déléguer une personne (par exemple, un responsable de projet) à la collecte de toutes les ressources nécessaires, dont l’appartenance aux équipes, dans un seul package. Ils peuvent également définir qui peut formuler des demandes : soit des utilisateurs de votre client, soit d’autres organisations connectées. Le responsable de projet recevra les demandes d’accès dans leur adresse de messagerie, puis approuvez ou refusez les demandes dans le portail MyAccess. Les administrateurs peuvent configurer les conditions d’accès pour inclure une date et une période d’expiration pour la suppression de l’utilisateur ou de l’invité de l’équipe, sauf si l’accès est renouvelé. Les administrateurs peuvent également configurer les groupes associés aux équipes pour qu’ils participent aux révisions dans Access. Pour les [avis sur Access](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview), les propriétaires du groupe reçoivent des rappels périodiques pour passer en revue les membres d’une équipe. Les avis d’accès incluent des recommandations, ce qui permet aux propriétaires de groupe de traverser plus facilement le processus d’attestation standard.

||||
|:-|:-|:-|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  | Points de décision | Votre organisation nécessite-t-elle un processus cohérent pour gérer l’appartenance d’une ou de plusieurs équipes ? <br> Votre organisation nécessite-t-elle des propriétaires ou les membres eux-mêmes pour justifier le maintien de leur appartenance à une ou plusieurs équipes de façon régulière ? <br> Votre organisation nécessite-t-elle l’approbation des utilisateurs et invités pour demander l’accès à des ressources telles que des équipes, des groupes, des sites SharePoint et des applications ? |
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>| Étapes suivantes | Documentez les exigences de votre organisation pour chaque équipe ou pour des équipes spécifiques à la date d’expiration de l’abonnement.<br>Planifiez la façon dont votre organisation peut regrouper les équipes, les groupes, les sites SharePoint et les applications dans les packages Access.<br>Déterminez quels sont les utilisateurs, tels que le gestionnaire de la personne qui est le responsable de projet, le commanditaire d’une organisation connectée ou d’un responsable de la sécurité de votre organisation doit approuver ou refuser des demandes d’accès. |

> [!TIP]
> Le tableau suivant vous permet de capturer les exigences de votre organisation.

| Fonctionnalité | Détails | Licence Azure AD Premium requise | Décision |
|:-|:-|:-|:-|
| Accès aux commentaires | Configurer l’accès aux avis pour certifier l’appartenance à des équipes spécifiques à intervalles réguliers | S2 | DÉFINIR |
| Gestion des habilitations | Configurer un package d’accès pour permettre aux utilisateurs et aux invités de demander l’accès à teams | S2 | DÉFINIR |

> [!NOTE]
> Pour vous aider à planifier votre projet, [Apprenez-en davantage sur les licences dont ils ont besoin](https://azure.microsoft.com/pricing/details/active-directory/).

### <a name="additional-information"></a>Informations supplémentaires

Pour obtenir des conseils techniques sur la mise en œuvre de ces paramètres, voir :

- [Gestion des habilitations](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)
- [Accès aux commentaires](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

## <a name="teams-feature-management"></a>Gestion des fonctionnalités de teams

Un autre aspect important de la gouvernance et de la gestion de la durée de vie des équipes est la possibilité de contrôler les fonctionnalités auxquelles vos utilisateurs auront accès. Vous pouvez gérer les fonctionnalités de messagerie, de réunion et d’appel, soit au niveau de l’organisation Microsoft 365 ou Office 365 par utilisateur.


|         |         |
|---------|---------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Votre organisation nécessite-t-elle des limitations d’équipes pour l’ensemble de votre client ?</li><li>Votre organisation nécessite-t-elle des fonctionnalités de limitation d’équipes pour des utilisateurs spécifiques ?</li></ul>|
| ![Icône montrant les étapes suivantes](media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Documentez les exigences de votre organisation concernant la limitation des fonctionnalités d’équipes au niveau du client et de l’utilisateur.</li><li>Prévoyez de mettre en œuvre vos exigences spécifiques dans le cadre de votre déploiement d’équipes.</li><li>Communiquez et publiez vos stratégies afin d’informer les utilisateurs des équipes du comportement qu’ils peuvent attendre.</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>Zones principales de la gestion des fonctionnalités de Microsoft teams

Teams fournit des fonctionnalités granulaires pour contrôler les fonctionnalités d’événement, de réunion, d’appel et de messagerie instantanée, etc., à l’aide de stratégies. Des stratégies différentes peuvent être appliquées à tous les utilisateurs par défaut ou par utilisateur selon les besoins de votre organisation. 

Pour obtenir la liste détaillée de tous les paramètres, y compris des recommandations techniques sur la manière de les implémenter dans votre organisation, consultez les articles suivants :

- [Gérer les paramètres de Microsoft Teams pour votre organisation](enable-features-office-365.md)
- [Gérer Teams lors de la transition vers le nouveau Centre d’administration de Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md)
- [Canaux privés dans Microsoft Teams](private-channels.md)
- [Gérer les stratégies de réunion dans teams](meeting-policies-in-teams.md)
- [Gérer les stratégies de messagerie dans Teams](messaging-policies-in-teams.md)
- [Gérer vos applications dans le centre d’administration Microsoft teams](manage-apps.md)

Par ailleurs, vous pouvez configurer la modération d’un canal et fournir des fonctionnalités de modérateur à certains utilisateurs afin qu’ils puissent contrôler qui peut créer des billets de canal et y répondre. Pour plus d’informations, reportez-vous à la rubrique [configurer et gérer la modération de canal dans Microsoft teams](manage-channel-moderation-in-teams.md) .

## <a name="security-and-compliance"></a>Sécurité et conformité

Teams repose sur les fonctionnalités avancées de sécurité et de conformité de Microsoft 365 et d’Office 365 et prend en charge les stratégies d’audit et de création de rapports, de recherche de contenu de conformité, de découverte électronique, de conservation et de rétention.

> [!Important]
> Si votre organisation a des exigences de conformité et de sécurité, consultez le contenu détaillé fourni sur cette rubrique dans l’article [Présentation de la sécurité et de la conformité de Microsoft teams](security-compliance-overview.md).

## <a name="related-topics"></a>Rubriques connexes

[Démarrage rapide de la gouvernance pour Teams](teams-adoption-governance-quick-start.md)

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->
