---
title: Planifier la gouvernance dans les équipes - Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 08/10/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Découvrez comment planifier l’implémentation des fonctionnalités de gouvernance dans les équipes.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 29d362771b970c7c654a5bddcd51f2f6c0be257f
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25017710"
---
# <a name="plan-for-governance-in-teams"></a>Planifier la gouvernance dans les équipes

Les équipes fournit un ensemble complet d’outils permettant de mettre en œuvre les fonctionnalités de gouvernance votre organisation peut avoir besoin. Cet article Guide les professionnels de l’informatique à poser les questions pour déterminer les exigences pour la gouvernance et comment y répondre. 

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>Création de groupe et de l’équipe, d’affectation de noms, classification et l’accès invité

Votre organisation peut nécessiter que vous implémentez des contrôles stricts sur comment les équipes sont nommés et classés, que les invités peuvent être ajoutées en tant que membres de l’équipe et qui peut créer des équipes. Vous pouvez configurer chacun de ces domaines à l’aide d’Azure Active Directory (AD Azure). 

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Votre organisation a besoin d’une convention d’affectation de noms spécifique pour les équipes ?</li><li>Créateurs d’équipe est nécessaire d’affecter des classifications spécifiques aux équipes ?</li><li>Avez-vous besoin restreindre la possibilité d’ajouter des invités aux équipes sur par l’équipe ?</li><li>Votre organisation a besoin limitation qui peut créer des équipes ?</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documenter les besoins de votre organisation pour la création de l’équipe, d’affectation de noms, classification et l’accès invité.</li><li>Envisagez d’implémenter ces exigences dans le cadre de votre déploiement d’équipes.</li><li>Communiquer et publier vos stratégies pour informer les utilisateurs des équipes du comportement qu'ils pourront.</li></ul>|

> [!TIP]
Le tableau suivant permet de capturer les besoins de votre organisation.
|Fonctionnalité |Détails |Azure AD Premium <br> licence requise |Décision |
|---------|---------|---------|---------|
|Stratégie d’attribution de noms d’équipe | Utilisez des mots bloqué personnalisée, basée sur le suffixe de préfixe. |P1 |TBD |
|Classement de l’équipe |Affecter des classifications aux équipes. |P1 |TBD |
|Accès invité de l’équipe |Autoriser ou empêcher l’ajout aux équipes invités. |Non |TBD |
|Création d'une équipe |Limite de création d’équipe pour les administrateurs. |Non |TBD|
|Création d'une équipe |Limite de la création de l’équipe aux membres de groupe de sécurité. |P1 |TBD|

> [!NOTE]
> Pour vous aider à planifier [en savoir plus sur la définition de ces stratégies et les licences qu’ils nécessitent](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings).

> [!NOTE]
> Limitation de la création de groupe et de l’équipe peut ralentir la productivité des utilisateurs, car de nombreux services Office 365 nécessitent que les groupes créés pour le fonctionnement du service. Pour plus d’informations, accédez à et développez [Pourquoi contrôler qui crée des groupes d’Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why).


#### <a name="additional-information"></a>Informations supplémentaires

Une fois que vous avez déterminé vos besoins, vous pouvez les implémenter à l’aide de contrôles Azure AD. Pour obtenir des instructions techniques sur l’implémentation de ces paramètres, voir :

-   [Applets de commande azure Active Directory pour la configuration des paramètres de groupe](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets).

-   [Appliquer une stratégie d’attribution de noms pour les groupes d’Office 365 dans Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy).

-   [Stratégie de noms de groupes d’office 365](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).


## <a name="group-and-team-expiration-retention-and-archiving"></a>Expiration de groupe et de l’équipe, de rétention et d’archivage

Votre organisation peut avoir des exigences supplémentaires pour la définition de stratégies d’expiration, la rétention, et l’archivage des équipes et aux équipes de données. Vous pouvez configurer des stratégies d’expiration de groupe pour gérer automatiquement le cycle de vie des stratégies de groupe et de rétention pour conserver ou supprimer des informations selon vos besoins, et vous pouvez archiver les équipes (les définie en mode lecture seule) pour conserver un affichage point-à-temps d’une équipe de n’est plus actif.

|           |            |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Votre organisation requiert la spécification d’une date d’expiration pour les équipes ?</li><li>Votre organisation a besoin des données spécifiques aux équipes appliquer les stratégies de rétention ?</li><li>Votre organisation prévoit d’exiger la possibilité d’archiver des équipes inactifs pour conserver le contenu en lecture seule ?</li></ul>|
| ![](media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Les besoins de votre organisation d’expiration de l’équipe, de rétention des données et de l’archivage du document.</li><li>Envisagez d’implémenter ces exigences dans le cadre de votre déploiement d’équipes.</li><li>Communiquer et publier vos stratégies pour informer les utilisateurs des équipes du comportement qu'ils pourront.</li></ul>|

> [!TIP]
Le tableau suivant permet de capturer les besoins de votre organisation.
|Fonctionnalité |Détails |Azure AD Premium <br>licence requise |Décision |
|---------|---------|---------|---------|
|Stratégie d’expiration |Gérer le cycle de vie des groupes d’Office 365 en définissant une stratégie d’expiration. |P1 |TBD|
|Stratégie de rétention |Conserver ou supprimer des données (fichiers de canal et les messages de canal équipes) pour une période spécifique en définissant des stratégies de rétention pour les équipes dans le centre de sécurité et conformité. **Remarque**: à l’aide de cette fonctionnalité nécessite une licence d’Office 365 entreprise E3 ou supérieure. |Non |TBD |
|Archivage et restauration |Archiver une équipe lorsqu’il n’est plus actif, mais vous souhaitez conserver pour référence ou réactiver ultérieurement. |Non |TBD |

> [!Note]
> Expiration de groupe est une fonctionnalité d’Azure AD Premium. Pour cette fonctionnalité soit disponible, votre client doit avoir un abonnement Azure AD Premium et les licences de l’administrateur qui configure les paramètres et les membres des groupes concernés.

#### <a name="additional-information"></a>Informations supplémentaires

Pour obtenir des instructions techniques sur l’implémentation de ces paramètres, voir :

-   [La valeur d’expiration de groupes d’Office 365](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle).

-   [Définir des stratégies de rétention d’équipes](retention-policies.md).

-   [Archivage ou restauration d’une équipe](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).


## <a name="teams-feature-management"></a>Gestion des fonctionnalités équipes

Un autre aspect important de la gouvernance et de gestion du cycle de vie des équipes est la capacité à contrôler les fonctionnalités de vos utilisateurs auront accès à. Vous pouvez gérer la messagerie, de la réunion et l’appel de fonctionnalités, au niveau du client Office 365 ou par utilisateur. 


|         |         |
|---------|---------|
| ![](media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Votre organisation a besoin limiter les fonctionnalités d’équipes pour votre client entière ?</li><li>Votre organisation a besoin limiter les fonctionnalités d’équipes pour des utilisateurs spécifiques ?</li></ul>|
| ![](media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Documenter les besoins de votre organisation pour limiter les fonctionnalités d’équipes au niveau du client et utilisateur.</li><li>Planifiez l’implémentation de vos besoins spécifiques dans le cadre de votre déploiement d’équipes.</li><li>Communiquer et publier vos stratégies pour informer les utilisateurs des équipes du comportement qu'ils pourront.</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>Les équipes fonctionnalité Gestion des domaines

Fournit des équipes granulaires pour contrôler la messagerie réunion, appel direct et fonctionnalités de l’événement et plus d’informations, par le biais des stratégies. Différentes stratégies peuvent être appliquées à tous les utilisateurs par défaut ou par l’utilisateur requis par votre organisation. 

Pour les listes détaillées de tous les paramètres, notamment des instructions techniques sur la façon de les implémenter pour votre organisation, consultez les articles suivants :

-   [Gérer les fonctionnalités de Microsoft Teams dans votre organisation Office 365](enable-features-office-365.md)
-   [Gérer les équipes pendant la transition vers le nouveau Microsoft Teams et Skype entreprise centre d’administration](manage-teams-skypeforbusiness-admin-center.md)
-   [Gérer les stratégies de la réunion dans les équipes](meeting-policies-in-teams.md)


## <a name="security-and-compliance"></a>Sécurité et conformité

Les équipes repose sur les fonctions avancées de sécurité et les fonctionnalités de conformité d’Office 365 et prend en charge l’audit et création de rapports, recherche de contenu de la conformité, e-discovery, suspens pour raisons juridiques et les stratégies de rétention. 

> [!Important]
> Si votre organisation a des exigences de sécurité et de conformité, consultez le contenu des informations détaillées fourni à ce sujet dans l’article [vue d’ensemble de la sécurité et de conformité dans les équipes Microsoft](security-compliance-overview.md).

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->